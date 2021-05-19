---
title: Azure Information Protection-Unterstützung für Office 365 betrieben von 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Erfahren Sie mehr über Azure Information Protection (AIP) für Office 365 betrieben von 21Vianet und wie Sie es für Kunden in China konfigurieren.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535842"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Azure Information Protection-Unterstützung für Office 365 betrieben von 21Vianet

Dieser Artikel behandelt die Unterschiede zwischen Azure Information Protection (AIP)-Unterstützung für Office 365 betrieben von 21Vianet und kommerziellen Angeboten sowie spezifische Anweisungen zum Konfigurieren von AIP für Kunden in China, einschließlich der Installation des lokalen AIP-Scanners und verwalten von Inhaltsscanaufträgen. &mdash;

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Unterschiede zwischen AIP für Office 365 von 21Vianet und kommerziellen Angeboten

Unser Ziel ist es zwar, kunden in China alle kommerziellen Features und Funktionen mit unserem AIP für Office 365 betrieben von 21Vianet bereitzustellen, es fehlen jedoch einige Funktionen, die wir hervorheben möchten.

Die folgende Liste enthält die bestehenden Lücken zwischen AIP für Office 365 betrieben von 21Vianet und unseren kommerziellen Angeboten ab Januar 2021:

- Verwaltung von Informationsrechten (Information Rights Management, IRM) wird nur für Microsoft 365 Apps for Enterprise (Build 11731.10000 oder höher) unterstützt. Office 2010, Office 2013 und andere versionen Office 2016 werden nicht unterstützt.

- Die Migration von Active Directory Rights Management Services (AD RMS) zu AIP ist derzeit nicht verfügbar.
  
- Die Freigabe geschützter E-Mails für Benutzer in der kommerziellen Cloud wird unterstützt.
  
- Die Freigabe von Dokumenten und E-Mail-Anlagen für Benutzer in der kommerziellen Cloud ist derzeit nicht verfügbar. Dazu gehören Office 365, die von 21Vianet-Benutzern in der kommerziellen Cloud betrieben werden, nicht von Office 365 betrieben von 21Vianet-Benutzern in der kommerziellen Cloud und Von Benutzern mit einer RMS for Individuals-Lizenz.
  
- IRM mit SharePoint (IRM-geschützte Websites und Bibliotheken) ist derzeit nicht verfügbar.
  
- Die Mobile Device Extension für AD RMS ist derzeit nicht verfügbar.

- Der [mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) wird von Azure China 21Vianet nicht unterstützt.

- Der AIP-Bereich des Azure-Portals ist für Kunden in China nicht verfügbar. Verwenden [Sie PowerShell-Befehle,](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) anstatt Aktionen im Portal auszuführen, z. B. verwalten und ausführen Sie Ihre Inhaltsscanaufträge.

## <a name="configure-aip-for-customers-in-china"></a>Konfigurieren von AIP für Kunden in China

So konfigurieren Sie AIP für Kunden in China:
1. [Aktivieren der Rechteverwaltung für den Mandanten](#step-1-enable-rights-management-for-the-tenant).

1. [Fügen Sie den Dienstprinzipal des Microsoft Information Protection Sync Service hinzu.](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)

1. [Konfigurieren der DNS-Verschlüsselung](#step-3-configure-dns-encryption).

1. [Installieren und Konfigurieren des AIP Unified Labeling-Clients](#step-4-install-and-configure-the-aip-unified-labeling-client).

1. [Konfigurieren von AIP-Apps auf Windows](#step-5-configure-aip-apps-on-windows).

1. [Installieren Sie den lokalen AIP-Scanner, und verwalten Sie Inhaltsscanaufträge.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Schritt 1: Aktivieren der Rechteverwaltung für den Mandanten

Damit die Verschlüsselung ordnungsgemäß funktioniert, muss RMS für den Mandanten aktiviert sein.

1. Überprüfen Sie, ob RMS aktiviert ist:

    1. Starten Sie PowerShell als Administrator.
    2. Wenn das AIPService-Modul nicht installiert ist, führen Sie `Install-Module AipService` aus.
    3. Importieren Sie das Modul mithilfe `Import-Module AipService` von .
    4. Verbinden dem Dienst mithilfe von `Connect-AipService -environmentname azurechinacloud` .
    5. Führen `(Get-AipServiceConfiguration).FunctionalState` Sie aus, und überprüfen Sie, ob der Status `Enabled` ist.

2. Wenn der Funktionszustand `Disabled` ist, führen Sie `Enable-AipService` aus.

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a>Schritt 2: Hinzufügen des Dienstprinzipal des Microsoft Information Protection-Synchronisierungsdiensts

Der **Microsoft Information Protection Sync Service-Dienstprinzipal** ist in Azure China-Mandanten standardmäßig nicht verfügbar und ist für Azure Information Protection erforderlich.

1. Erstellen Sie diesen Dienstprinzipal manuell mit dem [Cmdlet New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) und der Anwendungs-ID für `870c4f2e-85b6-4d43-bdda-6ed9a579b725` den Microsoft Information Protection Sync Service. 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. Fügen Sie nach dem Hinzufügen des Dienstprinzipal die relevanten Berechtigungen hinzu, die für den Dienst erforderlich sind.

### <a name="step-3-configure-dns-encryption"></a>Schritt 3: Konfigurieren der DNS-Verschlüsselung

Damit die Verschlüsselung ordnungsgemäß funktioniert, Office Clientanwendungen eine Verbindung mit der China-Instanz des Diensts herstellen und bootstrap von dort aus. Um Clientanwendungen an die richtige Dienstinstanz umzuleiten, muss der Mandantenadministrator einen DNS-SRV-Eintrag mit Informationen zur Azure RMS-URL konfigurieren. Ohne den DNS-SRV-Eintrag versucht die Clientanwendung standardmäßig, eine Verbindung mit der öffentlichen Cloudinstanz herzustellen, und es wird ein Fehler ausgeführt.

Außerdem wird davon ausgegangen, dass sich Benutzer mit einem Benutzernamen anmelden, der auf der Domäne im Besitz des Mandanten basiert (z. B. ), und nicht mit dem Benutzernamen (z. B. `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` ). Der Domänenname aus dem Benutzernamen wird für die DNS-Umleitung an die richtige Dienstinstanz verwendet.

#### <a name="configure-dns-encryption---windows"></a>Konfigurieren der DNS-Verschlüsselung – Windows

1. Hier erhalten Sie die RMS-ID:

    1. Starten Sie PowerShell als Administrator.
    2. Wenn das AIPService-Modul nicht installiert ist, führen Sie `Install-Module AipService` aus.
    3. Verbinden dem Dienst mithilfe von `Connect-AipService -environmentname azurechinacloud` .
    4. Führen `(Get-AipServiceConfiguration).RightsManagementServiceId` Sie aus, um die RMS-ID zu erhalten.

2. Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.

    - Dienst = `_rmsredir`
    - Protocol = `_http`
    - Name = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (wobei GUID die RMS-ID ist)
    - Priorität, Gewichtung, Sekunden, TTL = Standardwerte

3. Ordnen Sie die benutzerdefinierte Domäne dem Mandanten im [Azure-Portal zu.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Dadurch wird ein Eintrag in DNS hinzugefügt, der einige Minuten dauern kann, um überprüft zu werden, nachdem Sie den Wert zu den DNS-Einstellungen hinzugefügt haben.

4. Melden Sie sich beim Microsoft 365 Admin Center mit den entsprechenden globalen Administratoranmeldeinformationen an, und fügen Sie die Domäne (z. B. ) für die `contoso.cn` Benutzererstellung hinzu. Bei der Überprüfung sind möglicherweise zusätzliche DNS-Änderungen erforderlich. Sobald die Überprüfung erfolgt ist, können Benutzer erstellt werden.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Konfigurieren der DNS-Verschlüsselung – Mac, iOS, Android

Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.

- Dienst = `_rmsdisco`
- Protocol = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- Port = `80`
- Priorität, Gewichtung, Sekunden, TTL = Standardwerte


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a>Schritt 4: Installieren und Konfigurieren des AIP Unified Labeling-Clients

Laden Sie den AIP Unified Labeling-Client aus dem Microsoft Download Center herunter, und [installieren Sie den AIP-Client für einheitliche Bezeichnungen.](https://www.microsoft.com/download/details.aspx?id=53018)

Weitere Informationen finden Sie unter:

- [AIP-Dokumentation](/azure/information-protection/)
- [AIP-Versionsverlauf und Supportrichtlinie](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP-Systemanforderungen](/azure/information-protection/requirements)
- [AIP-Schnellstart: Bereitstellen des AIP-Clients](/azure/information-protection/quickstart-deploy-client)
- [AIP-Administratorhandbuch](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP-Benutzerhandbuch](/azure/information-protection/rms-client/clientv2-user-guide)
- [Informationen zu Microsoft 365 Vertraulichkeitsbezeichnungen](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a>Schritt 5: Konfigurieren von AIP-Apps auf Windows

AIP-apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:

- Registrierungsknoten = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- Wert = `6` (Standard = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie den Registrierungsschlüssel nach einer Deinstallation nicht löschen. Wenn der Schlüssel leer, falsch oder nicht vorhanden ist, verhält sich die Funktionalität als Standardwert (Standardwert = 0 für die kommerzielle Cloud). Wenn der Schlüssel leer oder falsch ist, wird dem Protokoll auch ein Druckfehler hinzugefügt.

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Schritt 6: Installieren des lokalen AIP-Scanners und Verwalten von Inhaltsscanaufträgen

Installieren Sie den lokalen AIP-Scanner, um Ihre Netzwerk- und Inhaltsfreigaben auf vertrauliche Daten zu überprüfen, und wenden Sie Klassifizierungs- und Schutzbezeichnungen an, wie in der Richtlinie Ihrer Organisation konfiguriert.

Verwenden Sie beim Konfigurieren und Verwalten Ihrer Aufträge für Inhaltsscans das folgende Verfahren anstelle der [Azure-Portalschnittstelle,](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) die von den kommerziellen Angeboten verwendet wird.

Weitere Informationen finden Sie unter [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) und Manage your content scan jobs using [PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).

**So installieren und konfigurieren Sie den Scanner:**

1. Melden Sie sich beim Windows Servercomputer an, auf dem der Scanner ausgeführt wird. Verwenden Sie ein Konto, das über lokale Administratorrechte verfügt und über Berechtigungen zum Schreiben in die SQL Server verfügt.

1. Beginnen Sie mit dem Schließen von PowerShell. Wenn Sie den AIP-Client und -Scanner bereits installiert haben, stellen Sie sicher, dass der **AIPScanner-Dienst** beendet wird.

1. Öffnen Sie Windows PowerShell sitzung mit der **Option Als Administrator ausführen.**

1. Führen Sie [das Cmdlet Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) aus, und geben Sie Ihre SQL Server-Instanz an, in der eine Datenbank für den Azure Information Protection-Scanner erstellt werden soll, und einen aussagekräftigen Namen für Ihren Scannercluster.

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > Sie können denselben Clusternamen im [Befehl Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) verwenden, um mehrere Scannerknoten demselben Cluster zuzuordnen. Wenn Sie denselben Cluster für mehrere Scannerknoten verwenden, können mehrere Scanner zusammenarbeiten, um Ihre Scans durchzuführen.
    > 

1. Stellen Sie sicher, dass der Dienst jetzt mithilfe von **Administrative Tools Services installiert**  >  **ist.**

    Der installierte Dienst heißt **Azure Information Protection Scanner** und wird für die Ausführung mithilfe des von Ihnen erstellten Scannerdienstkontos konfiguriert.

1. Erhalten Sie ein Azure-Token, das mit Ihrem Scanner verwendet werden soll. Ein Azure AD-Token ermöglicht es dem Scanner, sich beim Azure Information Protection-Dienst zu authentifizieren, sodass der Scanner nicht interaktiv ausgeführt werden kann. 

    1. Öffnen Sie das Azure-Portal, und erstellen Sie eine Azure AD-Anwendung, um ein Zugriffstoken für die Authentifizierung anzugeben. Weitere Informationen finden Sie unter [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).
    
        > [!TIP]
        > Beim Erstellen und Konfigurieren von Azure AD-Anwendungen für den Befehl  [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) zeigt der Bereich Api-Berechtigungen anfordern die **APIs** an, die meine Organisation verwendet, anstelle der **Registerkarte Microsoft-APIs.** Wählen Sie **die APIs aus,** die meine Organisation verwendet, um dann **Azure Rights Management Services auszuwählen.** 
        >

    1. Melden Sie Windows Servercomputer an, und starten Sie  eine PowerShell-Sitzung, wenn Ihrem Scannerdienstkonto die lokale Anmeldung für die Installation erteilt wurde. 
    
        Wenn Ihrem Scannerdienstkonto das  Lokale Anmelden für die Installation nicht erteilt werden kann, verwenden Sie den *Parameter OnBehalfOf* mit [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), wie unter How [to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)beschrieben.

    1. Führen [Sie Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)aus, und geben Sie Werte an, die aus Ihrer Azure AD-Anwendung kopiert wurden:

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      Beispiel:

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    Der Scanner verfügt jetzt über ein Token zur Authentifizierung bei Azure AD. Dieses Token ist je nach Konfiguration des geheimen **Web-App-/API-Clientgeheimnis** in Azure AD ein Jahr, zwei Jahre oder nie gültig. Wenn das Token abläuft, müssen Sie dieses Verfahren wiederholen.

1. Führen Sie [das Cmdlet Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) aus, um die Funktion des Scanners im Offlinemodus zu aktivieren. Ausführen:

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. Führen Sie [das Cmdlet Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) aus, um einen Standardauftrag zum Überprüfen von Inhalten zu erstellen.

    Der einzige erforderliche Parameter im **Cmdlet Set-AIPScannerContentScanJob** ist **Enforce**. Möglicherweise möchten Sie jedoch zu diesem Zeitpunkt andere Einstellungen für Ihren Inhaltsscanauftrag definieren. Beispiel:

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    Die obige Syntax konfiguriert die folgenden Einstellungen, während Sie die Konfiguration fortsetzen:

    - Sorgt dafür, dass die Planung für die Ausführung des Scanners manuell *ausgeführt wird*
    - Legt die informationstypen fest, die basierend auf der Vertraulichkeitsbezeichnungsrichtlinie ermittelt werden sollen
    - *Erzwingt* keine Vertraulichkeitsbezeichnungsrichtlinie
    - Automatisches Beschriften von Dateien basierend auf Inhalten mithilfe der Standardbezeichnung, die für die Vertraulichkeitsbezeichnungsrichtlinie definiert ist
    - Lässt *keine* Umetikettierung von Dateien zu
    - Behält Dateidetails während der Überprüfung und automatischen Bezeichnung bei, einschließlich datumsbeändet, zuletzt geändert *und* *durch Werte* geändert
    - Legt fest, dass der Scanner MSG- und TMP-Dateien beim Ausführen ausschließt
    - Legt den Standardbesitzer auf das Konto fest, das Sie beim Ausführen des Scanners verwenden möchten

1. Verwenden Sie [das Cmdlet Add-AIPScannerRepository,](/powershell/module/azureinformationprotection/add-aipscannerrepository) um die Repositorys zu definieren, die Sie in Ihrem Inhaltsscanauftrag überprüfen möchten. Führen Sie beispielsweise den folgenden Befehl aus:

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    Verwenden Sie eine der folgenden Syntaxen, abhängig vom Typ des Repositorys, das Sie hinzufügen:

    - Verwenden Sie für eine Netzwerkfreigabe `\\Server\Folder` .
    - Verwenden Sie für SharePoint Bibliothek `http://sharepoint.contoso.com/Shared%20Documents/Folder` .
    - Für einen lokalen Pfad: `C:\Folder`
    - Für einen UNC-Pfad: `\\Server\Folder`

    > [!NOTE]
    > Platzhalter werden nicht unterstützt, und WebDav-Speicherorte werden nicht unterstützt.
    >
    > Verwenden Sie stattdessen das [Cmdlet Set-AIPScannerRepository,](/powershell/module/azureinformationprotection/set-aipscannerrepository) um das Repository später zu ändern. 


Fahren Sie bei Bedarf mit den folgenden Schritten fort:

- [Ausführen eines Suchzyklus und Anzeigen von Berichten für den Scanner](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [Verwenden von PowerShell zum Konfigurieren des Scanners für die Anwendung von Klassifizierung und Schutz](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [Konfigurieren einer DLP-Richtlinie mit dem Scanner mithilfe von PowerShell](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

In der folgenden Tabelle sind powerShell-Cmdlets aufgeführt, die für die Installation des Scanners und die Verwaltung Ihrer Inhaltsscanaufträge relevant sind:

| Cmdlet | Beschreibung |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Fügt Ihrem Inhaltsscanauftrag ein neues Repository hinzu. |
| [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|Gibt Details zu Ihrem Cluster zurück. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Ruft Details zu Ihrem Inhaltsscanauftrag ab. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Ruft Details zu Repositorys ab, die für Ihren Inhaltsscanauftrag definiert sind. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Löscht den Auftrag zum Überprüfen von Inhalten. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Entfernt ein Repository aus Ihrem Inhaltsscanauftrag. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Definiert Einstellungen für Ihren Inhaltsscanauftrag. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Definiert Einstellungen für ein vorhandenes Repository in Ihrem Inhaltsscanauftrag. |
| | |

Weitere Informationen finden Sie unter:

- [Was ist der Einheitliche Bezeichnungsscanner für Azure Information Protection?](/azure/information-protection/deploy-aip-scanner)
- [Konfigurieren und Installieren des Azure Information Protection (AIP)-Scanners für einheitliche Bezeichnungen](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- [Verwalten Sie Ihre Inhaltsscanaufträge nur mit PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)

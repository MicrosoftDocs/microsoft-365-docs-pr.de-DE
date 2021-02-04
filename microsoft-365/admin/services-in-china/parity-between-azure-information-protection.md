---
title: Azure Information Protection-Unterstützung für Office 365, betrieben von 21Vianet
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
description: Erfahren Sie mehr über Azure Information Protection (AIP) für Office 365, betrieben von 21Vianet, und wie Sie es für Kunden in China konfigurieren.
monikerRange: o365-21vianet
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099678"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Azure Information Protection-Unterstützung für Office 365, betrieben von 21Vianet

In diesem Artikel werden die Unterschiede zwischen der Azure Information Protection (AIP)-Unterstützung für Office 365, betrieben von 21Vianet und kommerziellen Angeboten, sowie spezifische Anweisungen zum Konfigurieren von AIP für Kunden in China behandelt, einschließlich der Installation des lokalen AIP-Scanners und der Verwaltung von Aufträgen zum Überprüfen von &mdash; Inhalten.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Unterschiede zwischen AIP für Office 365, betrieben von 21Vianet und kommerziellen Angeboten

Während unser Ziel ist, alle kommerziellen Features und Funktionen für Kunden in China mit unserem AIP für Office 365 betrieben von 21Vianet bereitzustellen, gibt es einige fehlende Funktionen, die wir hervorheben möchten.

Die folgende Liste enthält die bestehenden Lücken zwischen AIP für Office 365, betrieben von 21Vianet und unseren kommerziellen Angeboten ab Januar 2021:

- Verwaltung von Informationsrechten (Information Rights Management, IRM) wird nur für Microsoft 365 Apps for Enterprise (Build 11731.10000 oder höher) unterstützt. Office 2010, Office 2013 und andere Office 2016-Versionen werden nicht unterstützt.

- Die Migration von Active Directory-Rechteverwaltungsdienste (AD RMS) zu AIP ist derzeit nicht verfügbar.
  
- Die Freigabe geschützter E-Mails für Benutzer in der kommerziellen Cloud wird unterstützt.
  
- Die Freigabe von Dokumenten und E-Mail-Anlagen für Benutzer in der kommerziellen Cloud ist derzeit nicht verfügbar. Dies umfasst Office 365, betrieben von 21Vianet-Benutzern in der kommerziellen Cloud, Nicht-Office 365-Benutzer, die von 21Vianet-Benutzern in der kommerziellen Cloud betrieben werden, und Benutzer mit einer RMS für Einzelpersonen-Lizenz.
  
- IRM mit SharePoint (IRM-geschützte Websites und Bibliotheken) ist derzeit nicht verfügbar.
  
- Die Erweiterung für mobile Geräte für AD RMS ist derzeit nicht verfügbar.

- Der [mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) wird von Azure China 21Vianet nicht unterstützt.

- Der AIP-Bereich des Azure-Portals ist für Kunden in China nicht verfügbar. Verwenden [Sie PowerShell-Befehle,](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) anstatt Aktionen im Portal auszuführen, z. B. das Installieren des lokalen Scanners und das Verwalten Ihrer Inhaltsscanaufträge.

## <a name="configure-aip-for-customers-in-china"></a>Konfigurieren von AIP für Kunden in China

So konfigurieren Sie AIP für Kunden in China:
1. [Aktivieren Sie die Rechteverwaltung für den Mandanten.](#step-1-enable-rights-management-for-the-tenant)

2. [Konfigurieren sie die DNS-Verschlüsselung.](#step-2-configure-dns-encryption)

3. [Installieren und konfigurieren Sie den AIP-Client für einheitliche Bezeichnungen.](#step-3-install-and-configure-the-aip-unified-labeling-client)

4. [Konfigurieren Sie die AIP-Apps unter Windows.](#step-4-configure-aip-apps-on-windows)

5. [Installieren Sie den lokalen AIP-Scanner, und verwalten Sie Inhaltsscanaufträge.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Schritt 1: Aktivieren der Rechteverwaltung für den Mandanten

Damit die Verschlüsselung ordnungsgemäß funktioniert, muss RMS für den Mandanten aktiviert sein.

1. Überprüfen Sie, ob RMS aktiviert ist:

    1. Starten Sie PowerShell als Administrator.
    2. Wenn das Modul AIPService nicht installiert ist, führen Sie `Install-Module AipService` .
    3. Importieren Sie das Modul mithilfe `Import-Module AipService` von .
    4. Stellen Sie eine Verbindung mit dem Dienst mithilfe von `Connect-AipService -environmentname azurechinacloud` .
    5. Führen Sie `(Get-AipServiceConfiguration).FunctionalState` die Ausführung aus, und überprüfen Sie, ob der Status `Enabled` .

2. Wenn der Funktionsstatus `Disabled` ist, führen Sie `Enable-AipService` .

### <a name="step-2-configure-dns-encryption"></a>Schritt 2: Konfigurieren der DNS-Verschlüsselung

Damit die Verschlüsselung ordnungsgemäß funktioniert, müssen die Office-Clientanwendungen eine Verbindung mit der Chinesischen Instanz des Diensts herstellen und von dort bootstrapen. Um Clientanwendungen an die richtige Dienstinstanz umzuleiten, muss der Mandantenadministrator einen DNS-SRV-Eintrag mit Informationen zur Azure RMS-URL konfigurieren. Ohne den DNS-SRV-Eintrag versucht die Clientanwendung standardmäßig, eine Verbindung mit der öffentlichen Cloudinstanz herzustellen, und es wird ein Fehler angezeigt.

Außerdem wird davon ausgegangen, dass sich Benutzer mit einem Benutzernamen anmelden, der auf der domäne des Mandanten basiert (z. B. ) und nicht mit dem Benutzernamen (z. B. `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` ). Der Domänenname aus dem Benutzernamen wird für die DNS-Umleitung an die richtige Dienstinstanz verwendet.

#### <a name="configure-dns-encryption---windows"></a>Konfigurieren der DNS-Verschlüsselung – Windows

1. Holen Sie sich die RMS-ID:

    1. Starten Sie PowerShell als Administrator.
    2. Wenn das Modul AIPService nicht installiert ist, führen Sie `Install-Module AipService` .
    3. Stellen Sie eine Verbindung mit dem Dienst mithilfe von `Connect-AipService -environmentname azurechinacloud` .
    4. Führen Sie `(Get-AipServiceConfiguration).RightsManagementServiceId` diese Aus, um die RMS-ID zu erhalten.

2. Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.

    - Dienst = `_rmsredir`
    - Protokoll = `_http`
    - Name = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (wobei GUID die RMS-ID ist)
    - Priorität, Gewichtung, Sekunden, TTL = Standardwerte

3. Ordnen Sie die benutzerdefinierte Domäne dem Mandanten im [Azure-Portal zu.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Dadurch wird ein Eintrag in DNS hinzugefügt, der einige Minuten dauern kann, um überprüft zu werden, nachdem Sie den Wert zu den DNS-Einstellungen hinzugefügt haben.

4. Melden Sie sich beim Microsoft 365 Admin Center mit den entsprechenden globalen Administratoranmeldeinformationen an, und fügen Sie die Domäne (z. B. ) für die `contoso.cn` Benutzererstellung hinzu. Im Überprüfungsprozess sind möglicherweise zusätzliche DNS-Änderungen erforderlich. Sobald die Überprüfung erfolgt ist, können Benutzer erstellt werden.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Konfigurieren der DNS-Verschlüsselung – Mac, iOS, Android

Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.

- Dienst = `_rmsdisco`
- Protokoll = `_http`
- Name = `_tcp`
- Ziel = `api.aadrm.cn`
- Port = `80`
- Priorität, Gewichtung, Sekunden, TTL = Standardwerte

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>Schritt 3: Installieren und Konfigurieren des AIP-Client für einheitliche Bezeichnungen

Laden Sie den AIP-Client für einheitliche Bezeichnungen aus dem [Microsoft Download Center herunter.](https://www.microsoft.com/download/details.aspx?id=53018)

Weitere Informationen finden Sie unter:

- [Dokumentation zu AIP](/azure/information-protection/)
- [AIP-Versionsverlauf und Supportrichtlinie](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP-Systemanforderungen](/azure/information-protection/requirements)
- [AIP-Schnellstart: Bereitstellen des AIP-Clients](/azure/information-protection/quickstart-deploy-client)
- [Leitfaden für den AIP-Administrator](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Benutzerhandbuch für AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Informationen zu Microsoft 365-Vertraulichkeitsbezeichnungen](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a>Schritt 4: Konfigurieren von AIP-Apps unter Windows

AIP-Apps unter Windows benötigen den folgenden Registrierungsschlüssel, um sie auf die richtige, unabhängigen Cloud für Azure China zu verweisen:

- Registrierungsknoten = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- Wert = `6` (Standard = 0)
- Typ = `REG_DWORD`

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie den Registrierungsschlüssel nach einer Deinstallation nicht löschen. Wenn der Schlüssel leer, falsch oder nicht vorhanden ist, verhält sich die Funktionalität als Standardwert (Standardwert = 0 für die kommerzielle Cloud). Wenn der Schlüssel leer oder falsch ist, wird dem Protokoll auch ein Druckfehler hinzugefügt.

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Schritt 5: Installieren des lokalen AIP-Scanners und Verwalten von Inhaltsscanaufträgen

Installieren Sie den lokalen AIP-Scanner, um Ihr Netzwerk und Ihre Inhaltsfreigaben auf vertrauliche Daten zu überprüfen, und wenden Sie Klassifizierungs- und Schutzbezeichnungen an, wie in der Richtlinie Ihrer Organisation konfiguriert.

Verwenden Sie bei der Installation des Scanners und beim Verwalten Ihrer Inhaltsscanaufträge die folgenden Cmdlets anstelle der Azure-Portal-Schnittstelle, die von den kommerziellen Angeboten verwendet wird:<br><br>

| Cmdlet | Beschreibung |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Fügt Ihrem Inhaltsscanauftrag ein neues Repository hinzu. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Ruft Details zu Ihrem Inhaltsscanauftrag ab. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Ruft Details zu Repositorys ab, die für ihren Inhaltsscanauftrag definiert sind. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Löscht den Auftrag zum Überprüfen von Inhalten. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Entfernt ein Repository aus dem Auftrag zum Überprüfen von Inhalten. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Definiert Einstellungen für ihren Inhaltsscanauftrag. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Definiert Einstellungen für ein vorhandenes Repository in Ihrem Inhaltsscanauftrag. |

Weitere Informationen finden Sie unter [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and Manage your content scan jobs using [PowerShell only.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)

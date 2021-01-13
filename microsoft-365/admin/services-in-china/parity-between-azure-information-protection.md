---
title: Parität zwischen Azure Information Protection für Office 365, betrieben von 21Vianet und kommerziellen Angeboten
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
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
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840301"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Parität zwischen Azure Information Protection für Office 365, betrieben von 21Vianet und kommerziellen Angeboten

Während unser Ziel ist, alle kommerziellen Features und Funktionen für Kunden in China mit unserem Azure Information Protection (AIP) für Office 365, betrieben von 21Vianet, bereitzustellen, gibt es einige fehlende Funktionen, die wir hervorheben möchten.

Die folgende Liste enthält die bestehenden Lücken zwischen Azure Information Protection für Office 365, betrieben von 21Vianet und unseren kommerziellen Angeboten ab Januar 2021:

- Verwaltung von Informationsrechten (Information Rights Management, IRM) wird nur für Microsoft 365 Apps for Enterprise (Build 11731.10000 oder höher) unterstützt. Office 2010, Office 2013 und andere Office 2016-Versionen werden nicht unterstützt.

- Die Migration Active Directory-Rechteverwaltungsdienste (AD RMS) zu Azure Information Protection ist derzeit nicht verfügbar.
  
- Die Freigabe geschützter E-Mails an Benutzer in der kommerziellen Cloud wird unterstützt.
  
- Die Freigabe von Dokumenten und E-Mail-Anlagen für Benutzer in der kommerziellen Cloud ist derzeit nicht verfügbar. Dies umfasst Office 365, betrieben von 21Vianet-Benutzern in der kommerziellen Cloud, Nicht-Office 365-Benutzer, die von 21Vianet-Benutzern in der kommerziellen Cloud betrieben werden, und Benutzer mit einer RMS für Einzelpersonen-Lizenz.
  
- IRM mit SharePoint (IRM-geschützte Websites und Bibliotheken) ist derzeit nicht verfügbar.
  
- Die Erweiterung für mobile Geräte für AD RMS ist derzeit nicht verfügbar.

- Der [mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) wird von Azure China 21Vianet nicht unterstützt.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>Konfigurieren von Azure Information Protection für Kunden in China

### <a name="enable-rights-management-for-the-tenant"></a>Aktivieren der Rechteverwaltung für den Mandanten

Damit die Verschlüsselung ordnungsgemäß funktioniert, muss der RMS für den Mandanten aktiviert sein.

- Überprüfen Sie, ob rmS aktiviert ist:
  1. Starten Sie PowerShell als Administrator.
  2. Wenn das Modul AIPService nicht installiert ist, führen Sie `Install-Module AipService` .
  3. Importieren Sie das Modul mithilfe `Import-Module AipService` von .
  4. Stellen Sie eine Verbindung mit dem Dienst mithilfe von `Connect-AipService -environmentname azurechinacloud` .
  5. Führen Sie `(Get-AipServiceConfiguration).FunctionalState` die Ausführung aus, und überprüfen Sie, ob der Status `Enabled` .

- Wenn der Funktionsstatus "ist" `Disabled` ist, führen Sie `Enable-AipService` .

### <a name="dns-configuration-for-encryption-windows"></a>DNS-Konfiguration für Verschlüsselung (Windows)

Damit die Verschlüsselung ordnungsgemäß funktioniert, müssen die Office-Clientanwendungen eine Verbindung mit der Chinesischen Instanz des Diensts herstellen und von dort bootstrapen. Um Clientanwendungen an die richtige Dienstinstanz umzuleiten, muss der Mandantenadministrator einen DNS-SRV-Eintrag mit Informationen zur Azure RMS-URL konfigurieren. Ohne den DNS-SRV-Eintrag versucht die Clientanwendung standardmäßig, eine Verbindung mit der öffentlichen Cloudinstanz herzustellen, und es wird ein Fehler angezeigt.

Außerdem wird davon ausgegangen, dass sich Benutzer mit einem Benutzernamen anmelden, der auf der domäne des Mandanten basiert (z. B. ) und nicht mit dem Benutzernamen (z. B. `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` ). Der Domänenname aus dem Benutzernamen wird für die DNS-Umleitung an die richtige Dienstinstanz verwendet.

- Holen Sie sich die RMS-ID:
  1. Starten Sie PowerShell als Administrator.
  2. Wenn das Modul AIPService nicht installiert ist, führen Sie `Install-Module AipService` .
  3. Stellen Sie eine Verbindung mit dem Dienst mithilfe von `Connect-AipService -environmentname azurechinacloud` .
  4. Führen Sie `(Get-AipServiceConfiguration).RightsManagementServiceId` diese Aus, um die RMS-ID zu erhalten.

- Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.
  - Dienst = `_rmsredir`
  - Protokoll = `_http`
  - Name = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` (wobei GUID die RMS-ID ist)
  - Priorität, Gewichtung, Sekunden, TTL = Standardwerte

- Ordnen Sie die benutzerdefinierte Domäne dem Mandanten im [Azure-Portal zu.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Dadurch wird ein Eintrag in DNS hinzugefügt, der einige Minuten dauern kann, um überprüft zu werden, nachdem Sie den Wert zu den DNS-Einstellungen hinzugefügt haben.

- Melden Sie sich beim Microsoft 365 Admin Center mit den entsprechenden globalen Administratoranmeldeinformationen an, und fügen Sie die Domäne (z. B. ) für die `contoso.cn` Benutzererstellung hinzu. Im Überprüfungsprozess sind möglicherweise zusätzliche DNS-Änderungen erforderlich. Sobald die Überprüfung erfolgt ist, können Benutzer erstellt werden.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>DNS-Konfiguration für Verschlüsselung (Mac, iOS, Android)

Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.

- Dienst = `_rmsdisco`
- Protokoll = `_http`
- Name = `_tcp`
- Ziel = `api.aadrm.cn`
- Port = `80`
- Priorität, Gewichtung, Sekunden, TTL = Standardwerte

### <a name="aip-client-configuration"></a>Konfiguration des AIP-Clients

Der einheitliche AIP-Client kann aus dem [Microsoft Download Center heruntergeladen werden.](https://www.microsoft.com/download/details.aspx?id=53018)

Weitere Informationen finden Sie unter:

- [Dokumentation zu Azure Information Protection](/azure/information-protection/)
- [AIP-Versionsverlauf und Supportrichtlinie](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP-Systemanforderungen](/azure/information-protection/requirements)
- [AIP-Schnellstart: Bereitstellen des AIP-Clients](/azure/information-protection/quickstart-deploy-client)
- [Leitfaden für den AIP-Administrator](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Benutzerhandbuch für AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Informationen zu Microsoft 365-Vertraulichkeitsbezeichnungen](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a>Konfiguration von AIP-Apps (nur Client mit einheitlichen Bezeichnungen)

Für die Einheitliche Bezeichnungslösung benötigen die AIP-Apps unter Windows den folgenden Registrierungsschlüssel, um sie auf die richtige, unabhängigen Cloud für Azure China zu verweisen:

- Registrierungsknoten = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- Wert = `6` (Standard = 0)
- Typ = `REG_DWORD`

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie den Registrierungsschlüssel nach einer Deinstallation nicht löschen. Wenn der Schlüssel leer, falsch oder nicht vorhanden ist, verhält sich die Funktionalität wie der Standardwert (Standardwert = 0 für die kommerzielle Cloud). Wenn der Schlüssel leer oder falsch ist, wird dem Protokoll auch ein Druckfehler hinzugefügt.

### <a name="manage-azure-information-protection-content-scan-jobs"></a>Verwalten von Azure Information Protection-Inhaltsscanaufträgen

Um Ihre Azure Information Protection-Inhaltsscanaufträge mit einem Azure China -Scannerserver zu verwalten, verwenden Sie die folgenden Cmdlets anstelle des Azure-Portals:<br><br>

| Cmdlet | Beschreibung |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Fügt Ihrem Inhaltsscanauftrag ein neues Repository hinzu. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Ruft Details zu Ihrem Inhaltsscanauftrag ab. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Ruft Details zu Repositorys ab, die für ihren Inhaltsscanauftrag definiert sind. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Löscht den Auftrag zum Überprüfen von Inhalten. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Entfernt ein Repository aus dem Auftrag zum Überprüfen von Inhalten. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Definiert Einstellungen für ihren Inhaltsscanauftrag. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Definiert Einstellungen für ein vorhandenes Repository in Ihrem Inhaltsscanauftrag. |

Weitere Informationen finden Sie unter [Verwalten Ihrer Aufträge zum Überprüfen von Inhalten nur mithilfe von PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)
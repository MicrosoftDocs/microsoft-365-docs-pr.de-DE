---
title: Office 365, betrieben von 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEU150
- GEA150
description: Erfahren Sie mehr über Azure Information Protection für Office 365 betrieben von 21Vianet und wie diese für Kunden in China konfiguriert werden.
monikerRange: o365-21vianet
ms.openlocfilehash: a4eb8c3370a123b939fdccc53eec3905f79ee806
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42243999"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Parität zwischen Azure Information Protection für Office 365 betrieben von 21Vianet und kommerziellen angeboten

Unser Ziel ist es, Kunden in China alle kommerziellen Features und Funktionen mit unserem Azure Information Protection für Office 365 zu liefern, die von 21Vianet angeboten betrieben werden, es gibt jedoch einige fehlende Funktionen, die wir hervorheben möchten.

Hierbei handelt es sich um die vorhandenen Lücken zwischen Azure Information Protection für Office 365, die von 21Vianet betrieben werden, und unseren kommerziellen Angeboten ab Juli 2019:

- Die Verwaltung von Informationsrechten (Information Rights Management, IRM) wird nur für Office 365 ProPlus (Build 11731,10000 oder höher) unterstützt. Office 2010, Office 2013 und andere Office 2016 Versionen werden nicht unterstützt.

- Die Migration von Active Directory Rights Management Services (AD RMS) zu Azure Information Protection ist derzeit nicht verfügbar.
  
- Die Freigabe geschützter e-Mails an Benutzer in der kommerziellen Cloud wird unterstützt.
  
- Die Freigabe von Dokumenten und e-Mail-Anlagen für Benutzer in der kommerziellen Cloud ist derzeit nicht verfügbar. Dazu gehören Office 365, die von 21Vianet-Benutzern in der kommerziellen Cloud betrieben werden, nicht Office 365, die von 21Vianet-Benutzern in der kommerziellen Cloud betrieben werden, und Benutzer mit einer RMS for Individuals-Lizenz.
  
- IRM mit SharePoint (IRM-geschützte Websites und Bibliotheken) ist derzeit nicht verfügbar.
  
- Der Rights Management-Connector ist derzeit nicht verfügbar.
  
- Die Erweiterung für mobile Geräte für AD RMS ist derzeit nicht verfügbar.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>Konfigurieren von Azure Information Protection für Kunden in China

### <a name="enable-rights-management-for-the-tenant"></a>Aktivieren der Rechteverwaltung für den Mandanten

Damit die Verschlüsselung ordnungsgemäß funktioniert, muss der RMS-Dienst für den Mandanten aktiviert sein.

- Überprüfen, ob der RMS aktiviert ist:
  1. Starten Sie PowerShell als Administrator.
  2. Wenn das AIPService-Modul nicht installiert ist, `Install-Module AipService`führen Sie aus.
  3. Importieren Sie das Modul `Import-Module AipService`mithilfe von.
  4. Stellen Sie eine Verbindung mit `Connect-AipService -environmentname azurechinacloud`dem Dienst mithilfe von her.
  5. Führen `(Get-AipServiceConfiguration).FunctionalState` Sie aus, und überprüfen `Enabled`Sie, ob der Status lautet.

- Wenn der Funktionszustand lautet `Disabled`, führen `Enable-AipService`Sie aus.

### <a name="dns-configuration-for-encryption-windows"></a>DNS-Konfiguration für die Verschlüsselung (Windows)

Damit die Verschlüsselung ordnungsgemäß funktioniert, müssen Office-Clientanwendungen eine Verbindung mit der China-Instanz des Diensts und dem Bootstrap von dort herstellen. Um Clientanwendungen an die richtige Dienstinstanz umzuleiten, muss der mandantenadministrator einen DNS-SRV-Eintrag mit Informationen zur Azure RMS-URL konfigurieren. Ohne den DNS-SRV-Eintrag versucht die Clientanwendung standardmäßig eine Verbindung mit der öffentlichen Cloud-Instanz herzustellen, und es tritt ein Fehler auf.

Darüber hinaus wird davon ausgegangen, dass sich Benutzer mit einem Benutzernamen anmelden, der auf der Mandantendomäne basiert `joe@contoso.cn`(beispielsweise) und `onmschina` nicht dem Benutzernamen ( `joe@contoso.onmschina.cn`beispielsweise). Der Domänenname aus dem Benutzernamen wird für die DNS-Umleitung zur korrekten Dienstinstanz verwendet.

- Abrufen der RMS-ID:
  1. Starten Sie PowerShell als Administrator.
  2. Wenn das AIPService-Modul nicht installiert ist, `Install-Module AipService`führen Sie aus.
  3. Stellen Sie eine Verbindung mit `Connect-AipService -environmentname azurechinacloud`dem Dienst mithilfe von her.
  4. Ausführen `(Get-AipServiceConfiguration).RightsManagementServiceId` , um die RMS-ID abzurufen.

- Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.
  - Dienst = `_rmsredir`
  - Protocol = `_http`
  - Name = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` (wobei GUID die RMS-ID ist)
  - Priorität, Gewichtung, Sekunden, TTL = Standardwerte

- Ordnen Sie die benutzerdefinierte Domäne dem Mandanten im [Azure-Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)zu. Dadurch wird ein Eintrag in DNS hinzugefügt, der nach dem Hinzufügen des Werts zu den DNS-Einstellungen einige Minuten in Anspruch nehmen kann, um überprüft zu werden.

- Melden Sie sich beim Microsoft 365 Admin Center mit den entsprechenden globalen Administratoranmeldeinformationen an, und fügen Sie die Domäne `contoso.cn`(zum Beispiel) für die Benutzererstellung hinzu. Im Verifizierungsprozess sind möglicherweise zusätzliche DNS-Änderungen erforderlich. Sobald die Überprüfung erfolgt ist, können Benutzer erstellt werden.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>DNS-Konfiguration für die Verschlüsselung (Mac, Ios, Android)

- Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.
  - Dienst = `_rmsdisco`
  - Protocol = `_http`
  - Name = `_tcp`
  - Target = `api.aadrm.cn`
  - Port = `80`
  - Priorität, Gewichtung, Sekunden, TTL = Standardwerte

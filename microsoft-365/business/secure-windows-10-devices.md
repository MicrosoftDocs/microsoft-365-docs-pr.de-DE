---
title: Absichern von Windows 10-Geräten
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Erfahren Sie mehr über das Konfigurieren der Einstellungen der Standardgeräterichtlinie, die jedes Windows 10 gerät erhält, wenn es sich bei ihrem Arbeits- oder Schulkonto einschreibt.
ms.openlocfilehash: 86db1c152f9f6ac1fe6093b4a55a74b69fbd8b0f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579972"
---
# <a name="secure-windows-10-devices"></a>Absichern von Windows 10-Geräten

Dieser Artikel gilt für Microsoft 365 Business Premium.

[] Die Einstellungen, die Sie hier konfigurieren, sind Teil der standardmäßigen Geräterichtlinie für Windows 10. Alle Benutzer, die ein Windows 10, einschließlich mobiler Geräte und PCs, verbinden, indem sie sich mit ihrem Arbeitskonto anmelden, erhalten diese Einstellungen automatisch. Wir empfehlen, während des Setups die Standardrichtlinie zu übernehmen und später Richtlinien für bestimmte Benutzergruppen hinzuzufügen.
  
## <a name="settings-to-secure-windows-10-devices"></a>Einstellungen zum Absichern von Windows 10-Geräten

Standardmäßig sind alle Einstellungen auf **Ein** festgelegt. Die folgenden Einstellungen stehen zur Verfügung:
  
|||
|:-----|:-----|
|Einstellung  <br/> |Beschreibung  <br/> |
|PCs vor Viren und anderen Bedrohungen mithilfe von Windows Defender Antivirus schützen  <br/> |Setzt voraus, dass Windows Defender Antivirus aktiviert ist, um PCs vor den Gefahren bei einer Verbindung mit dem Internet zu schützen.  <br/> |
|PCs vor webbasierten Bedrohungen in Microsoft Edge schützen  <br/> |Aktiviert Einstellungen in Edge, die Benutzer vor Websites und Downloads mit Schadsoftware schützen.  <br/> |
|Dateien und Ordner auf PCs mit BitLocker vor unbefugtem Zugriff schützen  <br/> |BitLocker schützt Daten durch Verschlüsselung der Computerfestplatten und bietet Schutz vor Datenverlusten, falls ein Computer verloren geht oder gestohlen wird. Weitere Informationen finden Sie unter [Bitlocker FAQ](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).  <br/> |
|Bildschirm deaktivieren, wenn ein Gerät im Leerlauf ist seit dieser Zeitdauer  <br/> |Stellt sicher, dass die Unternehmensdaten bei Benutzerinaktivität geschützt sind. Vielleicht arbeitet ein Benutzer an einem Ort mit Publikumsverkehr, z. B. in einem Café, und entfernt sich von seinem Gerät oder ist nur einen Augenblick abgelenkt, wodurch das Gerät für zufällige Blicke anfällig ist. Mit dieser Einstellung können Sie steuern, wie lange der Benutzer inaktiv sein kann, bevor der Bildschirm abgeschaltet wird.  <br/> |
|
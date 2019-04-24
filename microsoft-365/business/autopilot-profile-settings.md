---
title: Informationen zu AutoPilot-Profileinstellungen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Mit autoPilot-Profilen können Sie steuern, wie Windows auf Benutzergeräten installiert wird. Die Profile enthalten standardmäßige und optionale Einstellungen wie Skip Cortana Installation.
ms.openlocfilehash: d43a15e5f3dc83596b5c23dd0ceb416b24810298
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276939"
---
# <a name="about-autopilot-profile-settings"></a>Informationen zu AutoPilot-Profileinstellungen

## <a name="autopilot-profile-settings"></a>AutoPilot-Profileinstellungen

Sie können mithilfe der autoPilot-profile steuern, wie Windows auf Benutzergeräten installiert wird. Die Profile enthalten die folgenden Einstellungen:
  
 **AutoPilot-Standardfeatures (erforderlich), die automatisch festgelegt werden:**
  
|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|Cortana-, OneDrive- und OEM-Registrierung überspringen  <br/> |Überspringt die Installation von Consumer-apps wie Cortana und persönliche OneDrive. Der Geräte Benutzer kann diese später installieren, solange er ein lokaler Administrator auf dem Gerät ist. Die ursprüngliche Herstellerregistrierung wird übersprungen, da das Gerät von Microsoft 365 Business verwaltet wird.  <br/> |
|Anmeldeumgebung mit dem Branding Ihres Unternehmens  <br/> |Wenn in Ihrem Unternehmen ein [Branding auf Office 365-Seite hinzuGefügt](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)wird, erhält der Geräte Benutzer diese Erfahrung bei der Anmeldung.  <br/> |
|Automatische MDM-Registrierung mit konfigurierten AAD-Konten  <br/> |Die Benutzeridentität wird von Azure Active Directory verwaltet, und die Benutzer melden sich mit ihren Microsoft 365 Business-Anmeldeinformationen bei Windows und Office 365 an.  <br/> |
   
 **Optionale Einstellungen:**
  
|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|Datenschutzeinstellungen überspringen (standardmäßig deaktiviert)  <br/> |Wenn diese Option auf **Ein** festgelegt wurde, wird dem Gerätebenutzer bei der Erstanmeldung der Lizenzvertrag für das Gerät und Windows nicht angezeigt.  <br/> |
|Nicht zulassen, dass der Benutzer der lokale Administrator wird  <br/> |Wenn diese Option auf **Ein** festgelegt wurde, kann der Gerätebenutzer keine persönlichen Apps, z. B. Cortana, installieren.      <br/> |
   

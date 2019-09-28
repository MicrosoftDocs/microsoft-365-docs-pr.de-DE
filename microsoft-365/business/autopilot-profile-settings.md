---
title: Informationen zu AutoPilot-Profileinstellungen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Mithilfe von Autopilot-Profilen können Sie steuern, wie Windows auf Benutzergeräten installiert wird. Die Profile enthalten standardmäßige und optionale Einstellungen wie Skip Cortana Installation.
ms.openlocfilehash: cd66627943301f4a4f2410bafeff6074919ec29d
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287473"
---
# <a name="about-autopilot-profile-settings"></a>Informationen zu AutoPilot-Profileinstellungen

## <a name="autopilot-profile-settings"></a>AutoPilot-Profileinstellungen

Sie können steuern, wie Windows auf Benutzergeräten mithilfe der Autopilot-Profile installiert wird. Die Profile enthalten die folgenden Einstellungen:
  
 **Autopilot-Standardfeatures (erforderlich), die automatisch festgelegt werden:**
  
|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|Cortana-, OneDrive- und OEM-Registrierung überspringen  <br/> |Überspringt die Installation von Consumer-apps wie Cortana und persönliche OneDrive. Der Geräte Benutzer kann diese später installieren, solange er ein lokaler Administrator auf dem Gerät ist. Die ursprüngliche Herstellerregistrierung wird übersprungen, da das Gerät von Microsoft 365 Business verwaltet wird.  <br/> |
|Anmeldeumgebung mit dem Branding Ihres Unternehmens  <br/> |Wenn Ihr Unternehmen das [Branding Ihres Unternehmens zu Office 365 Anmeldeseite hinzufügen](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)hat, erhält der Geräte Benutzer diese Erfahrung beim anmelden.  <br/> |
|Automatische MDM-Registrierung mit konfigurierten AAD-Konten  <br/> |Die Benutzeridentität wird von Azure Active Directory verwaltet, und die Benutzer melden sich mit ihren Microsoft 365 Business-Anmeldeinformationen bei Windows und Office 365 an.  <br/> |
   
 **Optionale Einstellungen:**
  
|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|Datenschutzeinstellungen überspringen (standardmäßig deaktiviert)  <br/> |Wenn diese Option auf **Ein** festgelegt wurde, wird dem Gerätebenutzer bei der Erstanmeldung der Lizenzvertrag für das Gerät und Windows nicht angezeigt.  <br/> |
|Nicht zulassen, dass der Benutzer der lokale Administrator wird  <br/> |Wenn diese Option auf **Ein** festgelegt wurde, kann der Gerätebenutzer keine persönlichen Apps, z. B. Cortana, installieren.      <br/> |
   

---
title: Informationen zu AutoPilot-Profileinstellungen
f1.keywords:
- NOCSH
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Mithilfe von Autopilot-Profilen können Sie steuern, wie Windows auf Benutzergeräten installiert wird. Die Profile enthalten standardmäßige und optionale Einstellungen wie Skip Cortana Installation.
ms.openlocfilehash: 100de5e9548f901008d3ae154ac5a237ef265ffb
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401032"
---
# <a name="about-autopilot-profile-settings"></a>Informationen zu AutoPilot-Profileinstellungen

## <a name="autopilot-profile-settings"></a>Autopilot-Profileinstellungen

Sie können Autopilot-Profile verwenden, um zu steuern, wie Windows auf Benutzergeräten installiert wird. Die Profile enthalten die folgenden Einstellungen:
  
 **Autopilot-Standardfeatures (erforderlich), die automatisch festgelegt werden:**
  
|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|Überspringen von Cortana, OneDrive und OEM-Registrierung  <br/> |Überspringt die Installation von Consumer-apps wie Cortana und persönliche OneDrive. Der Geräte Benutzer kann diese später installieren, solange der Benutzer ein lokaler Administrator auf dem Gerät ist. Die ursprüngliche Herstellerregistrierung wird übersprungen, da das Gerät von Microsoft 365 Business Premium verwaltet wird.  <br/> |
|Anmeldeumgebung mit dem Branding Ihres Unternehmens  <br/> |Wenn Ihr Unternehmen ein [Branding Ihres Unternehmens zur Microsoft 365-Anmeldeseite hinzufügt](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page), erhält der Geräte Benutzer diese Erfahrung beim anmelden.  <br/> |
|Automatische MDM-Registrierung mit konfigurierten AAD-Konten  <br/> |Die Benutzeridentität wird von Azure Active Directory verwaltet, und die Benutzer melden sich bei Windows und Microsoft 365 mit Ihren Microsoft 365 Business Premium-Anmeldeinformationen an.  <br/> |
   
 **Optionale Einstellungen:**
  
|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|Datenschutzeinstellungen überspringen (standardmäßig deaktiviert)  <br/> |Wenn diese Option auf **Ein** festgelegt wurde, wird dem Gerätebenutzer bei der Erstanmeldung der Lizenzvertrag für das Gerät und Windows nicht angezeigt.  <br/> |
|Nicht zulassen, dass der Benutzer der lokale Administrator wird  <br/> |Wenn diese Option auf **Ein** festgelegt wurde, kann der Gerätebenutzer keine persönlichen Apps, z. B. Cortana, installieren.    <br/> |
   

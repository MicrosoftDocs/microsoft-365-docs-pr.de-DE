---
title: Informationen zu AutoPilot-Profileinstellungen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Mithilfe von AutoPilot-Profilen können Sie steuern, Windows auf Benutzergeräten installiert wird. Die Profile enthalten Standardeinstellungen und optionale Einstellungen wie die Cortana-Installation überspringen.
ms.openlocfilehash: 86f8718131f0a0b93e18e65e39e02e7d65aded1a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578505"
---
# <a name="about-autopilot-profile-settings"></a>Informationen zu AutoPilot-Profileinstellungen

## <a name="autopilot-profile-settings"></a>AutoPilot-Profileinstellungen

Sie können AutoPilot-Profile verwenden, um zu steuern, Windows auf Benutzergeräten installiert ist. Die Profile enthalten die folgenden Einstellungen:
  
 **AutoPilot-Standardfeatures (erforderlich), die automatisch festgelegt werden:**
  
|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|Cortana-, OneDrive- und OEM-Registrierung überspringen  <br/> |Überspringt die Installation von Consumer-Apps wie Cortana und persönlichen OneDrive. Der Gerätebenutzer kann diese später installieren, solange der Benutzer ein lokaler Administrator auf dem Gerät ist. Die ursprüngliche Herstellerregistrierung wird übersprungen, da das Gerät von einem Microsoft 365 Business Premium.  <br/> |
|Anmeldeumgebung mit dem Branding Ihres Unternehmens  <br/> |Wenn Ihr Unternehmen ein [Firmenbranding](../admin/setup/customize-sign-in-page.md)zu Microsoft 365 Anmeldeseite hinzufügen hat, wird dem Gerätebenutzer diese Erfahrung bei der Anmeldung angezeigt.  <br/> |
|Automatische MDM-Registrierung mit konfigurierten AAD-Konten  <br/> |Die Benutzeridentität wird von Azure Active Directory verwaltet, und Benutzer melden sich bei Windows und Microsoft 365 mit ihren Microsoft 365 Business Premium Anmeldeinformationen an.  <br/> |
   
 **Optionale Einstellungen:**
  
|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|Datenschutzeinstellungen überspringen (standardmäßig deaktiviert)  <br/> |Wenn diese Option auf **Ein** festgelegt wurde, wird dem Gerätebenutzer bei der Erstanmeldung der Lizenzvertrag für das Gerät und Windows nicht angezeigt.  <br/> |
|Nicht zulassen, dass der Benutzer der lokale Administrator wird  <br/> |Wenn diese Option auf **Ein** festgelegt wurde, kann der Gerätebenutzer keine persönlichen Apps, z. B. Cortana, installieren.    <br/> |

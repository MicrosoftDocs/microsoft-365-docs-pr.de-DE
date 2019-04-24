---
title: Erstellen und Bearbeiten von AutoPilot-Geräten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
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
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Erfahren Sie, wie Sie Geräte mit autoPilot in Microsoft 365 Business hochladen. Sie können einem Gerät oder einer Gruppe von Geräten ein Profil zuweisen.
ms.openlocfilehash: fff2dbc6af45ef9d4189f23849d638172c19dfb2
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277027"
---
# <a name="create-and-edit-autopilot-devices"></a>Erstellen und Bearbeiten von AutoPilot-Geräten

## <a name="upload-a-list-of-devices"></a>Hochladen einer Liste der Geräte

Sie können die [schrittweise Anleitung](add-autopilot-devices-and-profile.md) befolgen, um Geräte hochzuladen. Sie können aber auch die Geräte auf der Registerkarte **Geräte** hochladen. 
  
Geräte müssen diese Anforderungen erfüllen:
  
- Windows 10, Version 1703 oder höher.
    
- Neue Geräte, die nicht auf der Windows-Willkommensseite angezeigt werden.

1. wählen sie im Microsoft 365 Business Admin center die **** \> option devices autopilot **** \> **Add**aus.
  
2. On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. Navigieren Sie im Bereich **Geräte hinzufügen** zu einer [Gerätelisten-CSV-Datei](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) , die Sie \> in Vorbereitung **Speichern** \> **geschlossen**haben.
    
    Diese Informationen erhalten Sie von Ihrem Hardwareanbieter oder durch Verwendung des [PowerShell-Skripts Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), das eine CSV-Datei generiert. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Zuweisen eines Profils zu einem Gerät oder einer Gruppe von Geräten

1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**, und aktivieren Sie das Kontrollkästchen neben einem oder mehreren Geräten. 
    
2. Wählen Sie im Bereich **Gerät** ein Profil in der Dropdownliste **Zugewiesenes Profil** aus. 
    
    Wenn Sie noch keine Profile haben, finden Sie unter [Erstellen und Bearbeiten von AutoPilot-Profilen](create-and-edit-autopilot-profiles.md) Anweisungen. 
    

---
title: Erstellen und Bearbeiten von AutoPilot-Geräten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Hier erfahren Sie, wie Sie Geräte mithilfe von Autopilot in Microsoft 365 Business hochladen. Sie können einem Gerät oder einer Gruppe von Geräten ein Profil zuweisen.
ms.openlocfilehash: 1dd6b1a574166379e29465bf3699e47e3b155e0b
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320256"
---
# <a name="create-and-edit-autopilot-devices"></a>Erstellen und Bearbeiten von AutoPilot-Geräten

## <a name="upload-a-list-of-devices"></a>Hochladen einer Liste der Geräte

Sie können die [Schritt-für-Schritt-Anleitung](add-autopilot-devices-and-profile.md) zum Hochladen von Geräten verwenden, aber Sie können auch Geräte auf der Registerkarte " **Geräte** " hochladen. 
  
Geräte müssen diese Anforderungen erfüllen:
  
- Windows 10, Version 1703 oder höher
    
- Neue Geräte, die die Out-of-Box-Erfahrung von Windows noch nicht durchlaufen haben

1. Wählen Sie im Microsoft 365 Business Admin Center die Option **Geräte** \> **Autopilot**aus.
  
2. Klicken Sie auf der Seite **Autopilot** auf **** der Register \> Karte Geräte auf **Geräte hinzufügen**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. Navigieren Sie im Bereich **Geräte hinzufügen** zu einer [CSV-Datei für die Geräteliste](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) , die Sie gespeichert haben, \> **Speichern** \> Sie **Close**.
    
    Sie können diese Informationen von Ihrem Hardwareanbieter abrufen, oder Sie können das [PowerShell-Skript Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) verwenden, um eine CSV-Datei zu generieren. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Zuweisen eines Profils zu einem Gerät oder einer Gruppe von Geräten

1. Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte** aus, und aktivieren Sie das Kontrollkästchen neben einem oder mehreren Geräten. 
    
2. Wählen Sie im Bereich **Gerät** ein Profil in der Dropdownliste **Zugewiesenes Profil** aus. 
    
    Wenn Sie noch keine Profile haben, finden Sie unter [Erstellen und Bearbeiten von AutoPilot-Profilen](create-and-edit-autopilot-profiles.md) Anweisungen. 
    

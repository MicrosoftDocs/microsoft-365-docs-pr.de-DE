---
title: Erstellen und Bearbeiten von AutoPilot-Geräten
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Erfahren Sie, wie Sie Geräte mit AutoPilot in Microsoft 365 Business Premium hochladen. Sie können einem Gerät oder einer Gruppe von Geräten ein Profil zuweisen.
ms.openlocfilehash: 506ff44e3cb6656b19174e82688b5af141ea2b79
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578485"
---
# <a name="create-and-edit-autopilot-devices"></a>Erstellen und Bearbeiten von AutoPilot-Geräten

## <a name="upload-a-list-of-devices"></a>Hochladen einer Liste der Geräte

Sie können die [Schritt-für-Schritt-Anleitung](add-autopilot-devices-and-profile.md) zum Hochladen von Geräten verwenden, sie können jedoch auch Geräte auf der Registerkarte **Geräte** hochladen. 
  
Geräte müssen die folgenden Anforderungen erfüllen:
  
- Windows 10, Version 1703 oder höher
    
- Neue Geräte, die windows-out-of-box noch nicht erlebt haben

1. Wählen Sie im Microsoft 365 Admin Center **Geräte** \> **AutoPilot aus.**
  
2. Wählen Sie **auf der Seite AutoPilot** die Registerkarte **Geräte** Hinzufügen von \> **Geräten aus.**
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. Navigieren Sie **im Bereich** Geräte hinzufügen zu einer [GERÄTElisten-CSV-Datei,](../admin/misc/device-list.md) die Sie \> **Speichern schließen vorbereitet** \> **haben.**
    
    Sie können diese Informationen vom Hardwareanbieter abrufen oder das [Get-WindowsAutoPilotInfo PowerShell-Skript](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) verwenden, um eine CSV-Datei zu generieren. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Zuweisen eines Profils zu einem Gerät oder einer Gruppe von Geräten

1. Wählen Sie **auf der** Seite Vorbereiten von Windows die Registerkarte **Geräte** aus, und aktivieren Sie das Kontrollkästchen neben einem oder mehreren Geräten. 
    
2. Wählen Sie im Bereich **Gerät** ein Profil in der Dropdownliste **Zugewiesenes Profil** aus. 
    
    Wenn Sie noch keine Profile haben, finden Sie unter [Erstellen und Bearbeiten von AutoPilot-Profilen](create-and-edit-autopilot-profiles.md) Anweisungen. 

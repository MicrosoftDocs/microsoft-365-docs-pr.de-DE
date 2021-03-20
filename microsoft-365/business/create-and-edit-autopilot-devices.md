---
title: Erstellen und Bearbeiten von AutoPilot-Geräten
f1.keywords:
- NOCSH
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Erfahren Sie, wie Sie Geräte mit AutoPilot in Microsoft 365 Business Premium hochladen. Sie können einem Gerät oder einer Gruppe von Geräten ein Profil zuweisen.
ms.openlocfilehash: 910abb98b94b749177b04cd12c766f82d348e379
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913396"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="bcec2-104">Erstellen und Bearbeiten von AutoPilot-Geräten</span><span class="sxs-lookup"><span data-stu-id="bcec2-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="bcec2-105">Hochladen einer Liste der Geräte</span><span class="sxs-lookup"><span data-stu-id="bcec2-105">Upload a list of devices</span></span>

<span data-ttu-id="bcec2-106">Sie können die [Schritt-für-Schritt-Anleitung](add-autopilot-devices-and-profile.md) zum Hochladen von Geräten verwenden, sie können jedoch auch Geräte auf der Registerkarte **Geräte** hochladen.</span><span class="sxs-lookup"><span data-stu-id="bcec2-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="bcec2-107">Geräte müssen die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="bcec2-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="bcec2-108">Windows 10, Version 1703 oder höher</span><span class="sxs-lookup"><span data-stu-id="bcec2-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="bcec2-109">Neue Geräte, die windows-out-of-box noch nicht erlebt haben</span><span class="sxs-lookup"><span data-stu-id="bcec2-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="bcec2-110">Wählen Sie im Microsoft 365 Admin Center **Geräte** \> **AutoPilot aus.**</span><span class="sxs-lookup"><span data-stu-id="bcec2-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="bcec2-111">Wählen Sie **auf der Seite AutoPilot** die Registerkarte **Geräte** Hinzufügen von \> **Geräten aus.**</span><span class="sxs-lookup"><span data-stu-id="bcec2-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="bcec2-113">Navigieren Sie **im Bereich** Geräte hinzufügen zu einer [GERÄTElisten-CSV-Datei,](../admin/misc/device-list.md) die Sie \> **Speichern schließen vorbereitet** \> **haben.**</span><span class="sxs-lookup"><span data-stu-id="bcec2-113">On the **Add devices** panel, browse to a [Device list CSV file](../admin/misc/device-list.md) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="bcec2-114">Sie können diese Informationen vom Hardwareanbieter abrufen oder das [Get-WindowsAutoPilotInfo PowerShell-Skript](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) verwenden, um eine CSV-Datei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="bcec2-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="bcec2-115">Zuweisen eines Profils zu einem Gerät oder einer Gruppe von Geräten</span><span class="sxs-lookup"><span data-stu-id="bcec2-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="bcec2-116">Wählen Sie **auf der** Seite Vorbereiten von Windows die Registerkarte **Geräte** aus, und aktivieren Sie das Kontrollkästchen neben einem oder mehreren Geräten.</span><span class="sxs-lookup"><span data-stu-id="bcec2-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="bcec2-117">Wählen Sie im Bereich **Gerät** ein Profil in der Dropdownliste **Zugewiesenes Profil** aus.</span><span class="sxs-lookup"><span data-stu-id="bcec2-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="bcec2-118">Wenn Sie noch keine Profile haben, finden Sie unter [Erstellen und Bearbeiten von AutoPilot-Profilen](create-and-edit-autopilot-profiles.md) Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="bcec2-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 

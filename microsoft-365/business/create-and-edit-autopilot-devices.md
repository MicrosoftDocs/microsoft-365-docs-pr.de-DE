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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Hier erfahren Sie, wie Sie Geräte mithilfe von Autopilot in Microsoft 365 Business Premium hochladen. Sie können einem Gerät oder einer Gruppe von Geräten ein Profil zuweisen.
ms.openlocfilehash: 83c027cfe019e037518c4ca13eb331e5300fc2c1
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165859"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="f0940-104">Erstellen und Bearbeiten von AutoPilot-Geräten</span><span class="sxs-lookup"><span data-stu-id="f0940-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="f0940-105">Hochladen einer Liste der Geräte</span><span class="sxs-lookup"><span data-stu-id="f0940-105">Upload a list of devices</span></span>

<span data-ttu-id="f0940-106">Sie können die [Schritt-für-Schritt-Anleitung](add-autopilot-devices-and-profile.md) zum Hochladen von Geräten verwenden, aber Sie können auch Geräte auf der Registerkarte " **Geräte** " hochladen.</span><span class="sxs-lookup"><span data-stu-id="f0940-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="f0940-107">Geräte müssen diese Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="f0940-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="f0940-108">Windows 10, Version 1703 oder höher</span><span class="sxs-lookup"><span data-stu-id="f0940-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="f0940-109">Neue Geräte, die die Out-of-Box-Erfahrung von Windows noch nicht durchlaufen haben</span><span class="sxs-lookup"><span data-stu-id="f0940-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="f0940-110">Wählen Sie im Microsoft 365 Admin Center die Option **Geräte** \> **Autopilot**aus.</span><span class="sxs-lookup"><span data-stu-id="f0940-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="f0940-111">Klicken Sie auf der Seite **Autopilot** auf **Devices** der Register \> Karte Geräte auf **Geräte hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f0940-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="f0940-113">Navigieren Sie im Bereich **Geräte hinzufügen** zu einer [CSV-Datei für die Geräteliste](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) , die Sie gespeichert haben, \> **Speichern** \> Sie **Close**.</span><span class="sxs-lookup"><span data-stu-id="f0940-113">On the **Add devices** panel, browse to a [Device list CSV file](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="f0940-114">Sie können diese Informationen von Ihrem Hardwareanbieter abrufen, oder Sie können das [PowerShell-Skript Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) verwenden, um eine CSV-Datei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f0940-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="f0940-115">Zuweisen eines Profils zu einem Gerät oder einer Gruppe von Geräten</span><span class="sxs-lookup"><span data-stu-id="f0940-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="f0940-116">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte** aus, und aktivieren Sie das Kontrollkästchen neben einem oder mehreren Geräten.</span><span class="sxs-lookup"><span data-stu-id="f0940-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="f0940-117">Wählen Sie im Bereich **Gerät** ein Profil in der Dropdownliste **Zugewiesenes Profil** aus.</span><span class="sxs-lookup"><span data-stu-id="f0940-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="f0940-118">Wenn Sie noch keine Profile haben, finden Sie unter [Erstellen und Bearbeiten von AutoPilot-Profilen](create-and-edit-autopilot-profiles.md) Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="f0940-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    

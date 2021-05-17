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
description: Informationen zum Hochladen von Geräten mithilfe von AutoPilot in Microsoft 365 Business Premium. Sie können einem Gerät oder einer Gruppe von Geräten ein Profil zuweisen.
ms.openlocfilehash: 506ff44e3cb6656b19174e82688b5af141ea2b79
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578485"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="99232-104">Erstellen und Bearbeiten von AutoPilot-Geräten</span><span class="sxs-lookup"><span data-stu-id="99232-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="99232-105">Hochladen einer Liste der Geräte</span><span class="sxs-lookup"><span data-stu-id="99232-105">Upload a list of devices</span></span>

<span data-ttu-id="99232-106">Sie können die [Schritt-für-Schritt-Anleitung](add-autopilot-devices-and-profile.md) zum Hochladen von Geräten verwenden, sie können jedoch auch Geräte auf der Registerkarte **Geräte** hochladen.</span><span class="sxs-lookup"><span data-stu-id="99232-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="99232-107">Geräte müssen die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="99232-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="99232-108">Windows 10, Version 1703 oder höher</span><span class="sxs-lookup"><span data-stu-id="99232-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="99232-109">Neue Geräte, die noch nicht über eine Windows-out-of-Box-Erfahrung verfügen</span><span class="sxs-lookup"><span data-stu-id="99232-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="99232-110">Wählen Sie Microsoft 365 Admin Center **Geräte** \> **AutoPilot aus.**</span><span class="sxs-lookup"><span data-stu-id="99232-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="99232-111">Wählen Sie **auf der Seite AutoPilot** die Registerkarte **Geräte** Hinzufügen von \> **Geräten aus.**</span><span class="sxs-lookup"><span data-stu-id="99232-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="99232-113">Navigieren Sie **im Bereich** Geräte hinzufügen zu einer [GERÄTElisten-CSV-Datei,](../admin/misc/device-list.md) die Sie \> **Speichern schließen vorbereitet** \> **haben.**</span><span class="sxs-lookup"><span data-stu-id="99232-113">On the **Add devices** panel, browse to a [Device list CSV file](../admin/misc/device-list.md) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="99232-114">Sie können diese Informationen vom Hardwareanbieter abrufen oder das [Get-WindowsAutoPilotInfo PowerShell-Skript](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) verwenden, um eine CSV-Datei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="99232-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="99232-115">Zuweisen eines Profils zu einem Gerät oder einer Gruppe von Geräten</span><span class="sxs-lookup"><span data-stu-id="99232-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="99232-116">Wählen Sie **auf Windows** Seite Vorbereiten die Registerkarte **Geräte** aus, und aktivieren Sie das Kontrollkästchen neben einem oder mehreren Geräten.</span><span class="sxs-lookup"><span data-stu-id="99232-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="99232-117">Wählen Sie im Bereich **Gerät** ein Profil in der Dropdownliste **Zugewiesenes Profil** aus.</span><span class="sxs-lookup"><span data-stu-id="99232-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="99232-118">Wenn Sie noch keine Profile haben, finden Sie unter [Erstellen und Bearbeiten von AutoPilot-Profilen](create-and-edit-autopilot-profiles.md) Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="99232-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 

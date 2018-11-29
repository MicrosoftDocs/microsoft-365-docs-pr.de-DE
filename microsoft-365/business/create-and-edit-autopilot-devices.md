---
title: Erstellen und Bearbeiten von AutoPilot-Geräten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: Erfahren Sie, wie Geräte mithilfe des AutoPilot in Microsoft 365 Business hochladen. Sie können ein Gerät oder eine Gruppe von Geräten ein Profil zuweisen.
ms.openlocfilehash: cc1f81e9efd9b16e27b8abfbb0927d241535077e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867808"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="97dac-104">Erstellen und Bearbeiten von AutoPilot-Geräten</span><span class="sxs-lookup"><span data-stu-id="97dac-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="97dac-105">Hochladen einer Liste der Geräte</span><span class="sxs-lookup"><span data-stu-id="97dac-105">Upload a list of devices</span></span>

<span data-ttu-id="97dac-106">Sie können die [schrittweise Anleitung](add-autopilot-devices-and-profile.md) befolgen, um Geräte hochzuladen. Sie können aber auch die Geräte auf der Registerkarte **Geräte** hochladen.</span><span class="sxs-lookup"><span data-stu-id="97dac-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="97dac-107">Geräte müssen diese Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="97dac-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="97dac-108">Windows 10, Version 1703 oder höher.</span><span class="sxs-lookup"><span data-stu-id="97dac-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="97dac-109">Neue Geräte, die nicht auf der Windows-Willkommensseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="97dac-109">New devices that have not been through Windows out-of-box experience.</span></span>
    
1. <span data-ttu-id="97dac-110">Wählen Sie im Microsoft 365 Business Admin Center auf der Karte **Geräteaktionen** die Option **Windows mit AutoPilot bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="97dac-110">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="97dac-112">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte** \> **Geräte hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="97dac-112">On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="97dac-114">Navigieren Sie im Bereich **Geräte hinzufügen** zu einer [Liste der CSV-Datei](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) , die Sie vorbereitet haben \> **Speichern** \> **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="97dac-114">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="97dac-115">Diese Informationen erhalten Sie von Ihrem Hardwareanbieter oder durch Verwendung des [PowerShell-Skripts Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), das eine CSV-Datei generiert.</span><span class="sxs-lookup"><span data-stu-id="97dac-115">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="97dac-116">Zuweisen eines Profils zu einem Gerät oder einer Gruppe von Geräten</span><span class="sxs-lookup"><span data-stu-id="97dac-116">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="97dac-117">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**, und aktivieren Sie das Kontrollkästchen neben einem oder mehreren Geräten.</span><span class="sxs-lookup"><span data-stu-id="97dac-117">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="97dac-118">Wählen Sie im Bereich **Gerät** ein Profil in der Dropdownliste **Zugewiesenes Profil** aus.</span><span class="sxs-lookup"><span data-stu-id="97dac-118">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="97dac-119">Wenn Sie noch keine Profile haben, finden Sie unter [Erstellen und Bearbeiten von AutoPilot-Profilen](create-and-edit-autopilot-profiles.md) Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="97dac-119">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    

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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Erfahren Sie, wie Sie Geräte mit Autopilot in Microsoft 365 Business hochladen. Sie können einem Gerät oder einer Gruppe von Geräten ein Profil zuweisen.
ms.openlocfilehash: dee77a014ef519f3487a082edc3cf81058ec1c00
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071638"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="4e548-104">Erstellen und Bearbeiten von AutoPilot-Geräten</span><span class="sxs-lookup"><span data-stu-id="4e548-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="4e548-105">Hochladen einer Liste der Geräte</span><span class="sxs-lookup"><span data-stu-id="4e548-105">Upload a list of devices</span></span>

<span data-ttu-id="4e548-106">Sie können die [schrittweise Anleitung](add-autopilot-devices-and-profile.md) befolgen, um Geräte hochzuladen. Sie können aber auch die Geräte auf der Registerkarte **Geräte** hochladen.</span><span class="sxs-lookup"><span data-stu-id="4e548-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="4e548-107">Geräte müssen diese Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="4e548-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="4e548-108">Windows 10, Version 1703 oder höher.</span><span class="sxs-lookup"><span data-stu-id="4e548-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="4e548-109">Neue Geräte, die nicht auf der Windows-Willkommensseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4e548-109">New devices that have not been through Windows out-of-box experience.</span></span>

1. <span data-ttu-id="4e548-110">Wählen Sie im Microsoft 365 Business Admin Center die Option **Geräte** \> **Autopilot**aus.</span><span class="sxs-lookup"><span data-stu-id="4e548-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="4e548-111">Klicken Sie \*\*\*\* auf der Seite Autopilot auf die Register \> Karte **Geräte** , und **fügen Sie Geräte hinzu**.</span><span class="sxs-lookup"><span data-stu-id="4e548-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="4e548-113">Navigieren Sie im Bereich **Geräte hinzufügen** zu einer [Gerätelisten-CSV-Datei](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) , die Sie \> in Vorbereitung **Speichern** \> **geschlossen**haben.</span><span class="sxs-lookup"><span data-stu-id="4e548-113">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="4e548-114">Diese Informationen erhalten Sie von Ihrem Hardwareanbieter oder durch Verwendung des [PowerShell-Skripts Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), das eine CSV-Datei generiert.</span><span class="sxs-lookup"><span data-stu-id="4e548-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="4e548-115">Zuweisen eines Profils zu einem Gerät oder einer Gruppe von Geräten</span><span class="sxs-lookup"><span data-stu-id="4e548-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="4e548-116">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**, und aktivieren Sie das Kontrollkästchen neben einem oder mehreren Geräten.</span><span class="sxs-lookup"><span data-stu-id="4e548-116">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="4e548-117">Wählen Sie im Bereich **Gerät** ein Profil in der Dropdownliste **Zugewiesenes Profil** aus.</span><span class="sxs-lookup"><span data-stu-id="4e548-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="4e548-118">Wenn Sie noch keine Profile haben, finden Sie unter [Erstellen und Bearbeiten von AutoPilot-Profilen](create-and-edit-autopilot-profiles.md) Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="4e548-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    

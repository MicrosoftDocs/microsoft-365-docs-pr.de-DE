---
title: Erstellen und Bearbeiten von AutoPilot-Profilen
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
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Informationen Sie zum Erstellen, bearbeiten, löschen oder Entfernen von AutoPilot Profile. '
ms.openlocfilehash: 4658a27e5f2c64a52f8a7d08b3fc13df5e239dc3
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867863"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="6daa6-103">Erstellen und Bearbeiten von AutoPilot-Profilen</span><span class="sxs-lookup"><span data-stu-id="6daa6-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="6daa6-104">Erstellen eines Profils</span><span class="sxs-lookup"><span data-stu-id="6daa6-104">Create a profile</span></span>

<span data-ttu-id="6daa6-105">Ein Profil gilt für ein Gerät oder eine Gerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="6daa6-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="6daa6-106">Wählen Sie im Microsoft 365 Business Admin Center auf der Karte **Geräteaktionen** die Option **Windows mit AutoPilot bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="6daa6-106">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="6daa6-108">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile** \> **Profil erstellen**.</span><span class="sxs-lookup"><span data-stu-id="6daa6-108">On the **Prepare Windows** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="6daa6-109">Geben Sie auf der Seite **Profil erstellen** einen Namen für das Profil ein, mit dem Sie es identifizieren können, z.B. Marketing. Aktivieren Sie die gewünschte Einstellung (weitere Informationen finden Sie unter [Informationen zu AutoPilot-Profileinstellungen](autopilot-profile-settings.md)), und wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6daa6-109">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="6daa6-111">Zuweisen eines Profils zu einem Gerät</span><span class="sxs-lookup"><span data-stu-id="6daa6-111">Apply profile to a device</span></span>

<span data-ttu-id="6daa6-p101">Nachdem Sie ein Profil erstellt haben, können Sie es einem Gerät oder einer Gruppe von Geräten zuweisen. Sie können ein vorhandenes Profil in der [schrittweisen Anleitung](add-autopilot-devices-and-profile.md) auswählen, es neuen Geräten zuordnen oder ein vorhandenes Profil für ein Gerät oder eine Gerätegruppe ersetzen.</span><span class="sxs-lookup"><span data-stu-id="6daa6-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="6daa6-114">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**.</span><span class="sxs-lookup"><span data-stu-id="6daa6-114">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="6daa6-115">Klicken Sie auf das Kontrollkästchen neben den Namen eines Geräts und in der Systemsteuerung **Gerät** , wählen Sie aus der Dropdownliste **zugewiesene Profil** ein Profil \> **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6daa6-115">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="6daa6-117">Bearbeiten, Löschen oder Entfernen eines Profils</span><span class="sxs-lookup"><span data-stu-id="6daa6-117">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="6daa6-p102">Nachdem Sie einem Gerät ein Profil zugewiesen haben, können Sie es aktualisieren, auch wenn Sie das Gerät bereits einem Benutzer zugewiesen haben. Wenn sich das Gerät mit dem Internet verbindet, lädt es während des Setupvorgangs die neueste Version Ihres Profils herunter. Wenn der Benutzer das Gerät auf die werkseitigen Standardeinstellungen zurücksetzt, lädt das Gerät erneut die neuesten Updates in Ihr Profil herunter.</span><span class="sxs-lookup"><span data-stu-id="6daa6-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="6daa6-121">Bearbeiten eines Profils</span><span class="sxs-lookup"><span data-stu-id="6daa6-121">Edit a profile</span></span>

1. <span data-ttu-id="6daa6-122">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile**.</span><span class="sxs-lookup"><span data-stu-id="6daa6-122">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="6daa6-123">Klicken Sie auf das Kontrollkästchen neben den Namen eines Geräts und im **Profil** Bereich aktualisieren, die verfügbaren Werte \> **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6daa6-123">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="6daa6-124">Wenn Sie dies tun, bevor ein Benutzer das Gerät mit dem Internet verbindet, wird das Profil auf den Setupvorgang angewendet.</span><span class="sxs-lookup"><span data-stu-id="6daa6-124">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="6daa6-125">Löschen eines Profils</span><span class="sxs-lookup"><span data-stu-id="6daa6-125">Delete a profile</span></span>

1. <span data-ttu-id="6daa6-126">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile**.</span><span class="sxs-lookup"><span data-stu-id="6daa6-126">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="6daa6-127">Klicken Sie auf das Kontrollkästchen neben dem Gerätenamen, und klicken Sie in der Systemsteuerung **Profil** auf **Profil löschen** \> **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6daa6-127">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="6daa6-128">Wenn Sie ein Profil löschen, wird es von einem Gerät oder einer Gruppe von Geräten entfernt, denen es zugewiesen war.</span><span class="sxs-lookup"><span data-stu-id="6daa6-128">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="6daa6-129">Entfernen eines Profils</span><span class="sxs-lookup"><span data-stu-id="6daa6-129">Remove a profile</span></span>

1. <span data-ttu-id="6daa6-130">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**.</span><span class="sxs-lookup"><span data-stu-id="6daa6-130">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="6daa6-131">Klicken Sie auf das Kontrollkästchen neben den Namen eines Geräts und in der Systemsteuerung **Gerät** , wählen Sie **keine** aus der Dropdownliste **zugewiesene Profil** \> **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6daa6-131">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    

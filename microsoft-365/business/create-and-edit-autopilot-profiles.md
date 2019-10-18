---
title: Erstellen und Bearbeiten von AutoPilot-Profilen
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
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Hier erfahren Sie, wie Sie Autopilot-Profile erstellen, bearbeiten, löschen oder entfernen.
ms.openlocfilehash: 4305340a2fc5df8202cf4d85f9e2541690bf9ed0
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37574716"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="f9d81-103">Erstellen und Bearbeiten von AutoPilot-Profilen</span><span class="sxs-lookup"><span data-stu-id="f9d81-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="f9d81-104">Erstellen eines Profils</span><span class="sxs-lookup"><span data-stu-id="f9d81-104">Create a profile</span></span>

<span data-ttu-id="f9d81-105">Ein Profil gilt für ein Gerät oder eine Gerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="f9d81-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="f9d81-106">Wählen Sie im Microsoft 365 Business Admin Center die Option **Geräte** \> **Autopilot**aus.</span><span class="sxs-lookup"><span data-stu-id="f9d81-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="f9d81-107">Klicken Sie auf der Seite **Autopilot** auf \*\*\*\* die Register \> Karte Profile Profil **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f9d81-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="f9d81-108">Geben Sie auf der Seite **Profil erstellen** einen Namen für das Profil ein, mit dem Sie es identifizieren können, z.B. Marketing. Aktivieren Sie die gewünschte Einstellung (weitere Informationen finden Sie unter [Informationen zu AutoPilot-Profileinstellungen](autopilot-profile-settings.md)), und wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f9d81-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="f9d81-110">Zuweisen eines Profils zu einem Gerät</span><span class="sxs-lookup"><span data-stu-id="f9d81-110">Apply profile to a device</span></span>

<span data-ttu-id="f9d81-p101">Nachdem Sie ein Profil erstellt haben, können Sie es einem Gerät oder einer Gruppe von Geräten zuweisen. Sie können ein vorhandenes Profil in der [schrittweisen Anleitung](add-autopilot-devices-and-profile.md) auswählen, es neuen Geräten zuordnen oder ein vorhandenes Profil für ein Gerät oder eine Gerätegruppe ersetzen.</span><span class="sxs-lookup"><span data-stu-id="f9d81-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="f9d81-113">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**.</span><span class="sxs-lookup"><span data-stu-id="f9d81-113">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="f9d81-114">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="f9d81-114">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="f9d81-116">Bearbeiten, Löschen oder Entfernen eines Profils</span><span class="sxs-lookup"><span data-stu-id="f9d81-116">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="f9d81-p102">Nachdem Sie einem Gerät ein Profil zugewiesen haben, können Sie es aktualisieren, auch wenn Sie das Gerät bereits einem Benutzer zugewiesen haben. Wenn sich das Gerät mit dem Internet verbindet, lädt es während des Setupvorgangs die neueste Version Ihres Profils herunter. Wenn der Benutzer das Gerät auf die werkseitigen Standardeinstellungen zurücksetzt, lädt das Gerät erneut die neuesten Updates in Ihr Profil herunter.</span><span class="sxs-lookup"><span data-stu-id="f9d81-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="f9d81-120">Bearbeiten eines Profils</span><span class="sxs-lookup"><span data-stu-id="f9d81-120">Edit a profile</span></span>

1. <span data-ttu-id="f9d81-121">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile**.</span><span class="sxs-lookup"><span data-stu-id="f9d81-121">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="f9d81-122">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="f9d81-122">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="f9d81-123">Wenn Sie dies tun, bevor ein Benutzer das Gerät mit dem Internet verbindet, wird das Profil auf den Setupvorgang angewendet.</span><span class="sxs-lookup"><span data-stu-id="f9d81-123">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="f9d81-124">Löschen eines Profils</span><span class="sxs-lookup"><span data-stu-id="f9d81-124">Delete a profile</span></span>

1. <span data-ttu-id="f9d81-125">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile**.</span><span class="sxs-lookup"><span data-stu-id="f9d81-125">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="f9d81-126">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="f9d81-126">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="f9d81-127">Wenn Sie ein Profil löschen, wird es von einem Gerät oder einer Gruppe von Geräten entfernt, denen es zugewiesen war.</span><span class="sxs-lookup"><span data-stu-id="f9d81-127">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="f9d81-128">Entfernen eines Profils</span><span class="sxs-lookup"><span data-stu-id="f9d81-128">Remove a profile</span></span>

1. <span data-ttu-id="f9d81-129">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**.</span><span class="sxs-lookup"><span data-stu-id="f9d81-129">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="f9d81-130">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="f9d81-130">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    

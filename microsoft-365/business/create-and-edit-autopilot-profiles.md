---
title: Erstellen und Bearbeiten von AutoPilot-Profilen
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Erfahren Sie, wie Sie ein AutoPilot-Profil erstellen und auf ein Gerät anwenden sowie ein Profil bearbeiten oder löschen oder ein Profil von einem Gerät entfernen.
ms.openlocfilehash: 414243da88fb6f39f8e6067d19d49ffe955f725f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580252"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="4ac15-103">Erstellen und Bearbeiten von AutoPilot-Profilen</span><span class="sxs-lookup"><span data-stu-id="4ac15-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="4ac15-104">Erstellen eines Profils</span><span class="sxs-lookup"><span data-stu-id="4ac15-104">Create a profile</span></span>

<span data-ttu-id="4ac15-105">Ein Profil gilt für ein Gerät oder eine Gerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="4ac15-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="4ac15-106">Wählen Sie Microsoft 365 Admin Center **Geräte** \> **AutoPilot aus.**</span><span class="sxs-lookup"><span data-stu-id="4ac15-106">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="4ac15-107">Wählen Sie **auf der Seite AutoPilot** die **Registerkarte** Profile profil \> **erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="4ac15-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="4ac15-108">Geben Sie **auf der** Seite Profil erstellen einen Namen für das Profil ein, mit dem Sie es identifizieren können, z. B. Marketing.</span><span class="sxs-lookup"><span data-stu-id="4ac15-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing.</span></span> <span data-ttu-id="4ac15-109">Aktivieren Sie die einstellung, die Sie möchten, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="4ac15-109">Turn on the setting you want, and then choose **Save**.</span></span> <span data-ttu-id="4ac15-110">Weitere Informationen zu AutoPilot-Profileinstellungen finden Sie unter [Informationen zu AutoPilot-Profileinstellungen](autopilot-profile-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4ac15-110">For more information about AutoPilot profile settings, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="4ac15-112">Zuweisen eines Profils zu einem Gerät</span><span class="sxs-lookup"><span data-stu-id="4ac15-112">Apply profile to a device</span></span>

<span data-ttu-id="4ac15-113">Nachdem Sie ein Profil erstellt haben, können Sie es auf ein Gerät oder eine Gruppe von Geräten anwenden.</span><span class="sxs-lookup"><span data-stu-id="4ac15-113">After you create a profile, you can apply it to a device or a group of devices.</span></span> <span data-ttu-id="4ac15-114">Sie können ein vorhandenes [](add-autopilot-devices-and-profile.md) Profil in der schrittweisen Anleitung auswählen und auf neue Geräte anwenden oder ein vorhandenes Profil für ein Gerät oder eine Gruppe von Geräten ersetzen.</span><span class="sxs-lookup"><span data-stu-id="4ac15-114">You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md) and apply it to new devices, or replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="4ac15-115">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**.</span><span class="sxs-lookup"><span data-stu-id="4ac15-115">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="4ac15-116">Aktivieren Sie das Kontrollkästchen neben einem  Gerätenamen, und wählen  Sie im Gerätebereich ein Profil aus der Dropdownliste Zugewiesenes Profil \> **speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="4ac15-116">Select the check box next to a device name, and in the **Device** panel, choose a profile from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="4ac15-118">Bearbeiten, Löschen oder Entfernen eines Profils</span><span class="sxs-lookup"><span data-stu-id="4ac15-118">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="4ac15-p103">Nachdem Sie einem Gerät ein Profil zugewiesen haben, können Sie es aktualisieren, auch wenn Sie das Gerät bereits einem Benutzer zugewiesen haben. Wenn sich das Gerät mit dem Internet verbindet, lädt es während des Setupvorgangs die neueste Version Ihres Profils herunter. Wenn der Benutzer das Gerät auf die werkseitigen Standardeinstellungen zurücksetzt, lädt das Gerät erneut die neuesten Updates in Ihr Profil herunter.</span><span class="sxs-lookup"><span data-stu-id="4ac15-p103">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="4ac15-122">Bearbeiten eines Profils</span><span class="sxs-lookup"><span data-stu-id="4ac15-122">Edit a profile</span></span>

1. <span data-ttu-id="4ac15-123">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile**.</span><span class="sxs-lookup"><span data-stu-id="4ac15-123">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="4ac15-124">Aktivieren Sie das Kontrollkästchen neben einem Gerätenamen, und aktualisieren Sie im **Profilbereich** alle verfügbaren Einstellungen \> **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4ac15-124">Select the check box next to a device name, and in the **Profile** panel, update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="4ac15-125">Wenn Sie dies tun, bevor ein Benutzer das Gerät mit dem Internet verbindet, wird das Profil auf den Setupvorgang angewendet.</span><span class="sxs-lookup"><span data-stu-id="4ac15-125">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="4ac15-126">Löschen eines Profils</span><span class="sxs-lookup"><span data-stu-id="4ac15-126">Delete a profile</span></span>

1. <span data-ttu-id="4ac15-127">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Profile**.</span><span class="sxs-lookup"><span data-stu-id="4ac15-127">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="4ac15-128">Aktivieren Sie das Kontrollkästchen neben einem Gerätenamen, und wählen Sie im **Profilbereich** Profil **speichern** \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="4ac15-128">Select the check box next to a device name, and in the **Profile** panel, select **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="4ac15-129">Wenn Sie ein Profil löschen, wird es von einem Gerät oder einer Gruppe von Geräten entfernt, denen es zugewiesen war.</span><span class="sxs-lookup"><span data-stu-id="4ac15-129">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="4ac15-130">Entfernen eines Profils</span><span class="sxs-lookup"><span data-stu-id="4ac15-130">Remove a profile</span></span>

1. <span data-ttu-id="4ac15-131">Wählen Sie auf der Seite **Windows vorbereiten** die Registerkarte **Geräte**.</span><span class="sxs-lookup"><span data-stu-id="4ac15-131">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="4ac15-132">Aktivieren Sie das Kontrollkästchen neben einem  Gerätenamen, und wählen  Sie im Gerätebereich in der Dropdownliste Zugewiesenes Profil Speichern die Option **Keine** \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="4ac15-132">Select the check box next to a device name, and in the **Device** panel, choose **None** from the **Assigned profile** drop-down list \> **Save**.</span></span>
    

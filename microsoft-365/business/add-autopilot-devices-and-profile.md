---
title: Verwenden der schrittweisen Anleitung zum Hinzufügen von AutoPilot-Geräten und -Profilen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Erfahren Sie, wie Windows AutoPilot verwenden, um neue Windows 10 Geräte für Ihr Unternehmen einzurichten.
ms.openlocfilehash: 56225424125e9eed9f46867837c564aa5d1c4adc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867557"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="5f7d9-103">Verwenden der schrittweisen Anleitung zum Hinzufügen von AutoPilot-Geräten und -Profilen</span><span class="sxs-lookup"><span data-stu-id="5f7d9-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="5f7d9-104">[] Mit Windows AutoPilot können Sie neue Windows 10-Geräte für Ihr Unternehmen so einrichten, dass sie sofort nach Übergabe an Ihre Mitarbeiter produktiv eingesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-104">You can use Windows AutoPilot to set up new Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="5f7d9-105">Anforderungen an Geräte</span><span class="sxs-lookup"><span data-stu-id="5f7d9-105">Device requirements</span></span>

<span data-ttu-id="5f7d9-106">Geräte müssen diese Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="5f7d9-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="5f7d9-107">Windows 10, Version 1703 oder höher.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="5f7d9-108">Neue Geräte, die nicht auf der Windows-Willkommensseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="5f7d9-109">Befolgen der Setupanleitung zum Erstellen von Geräten und Profilen</span><span class="sxs-lookup"><span data-stu-id="5f7d9-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="5f7d9-110">Wenn Sie noch keine Gerätegruppen oder Profile erstellt haben, beginnen Sie am besten mit der schrittweisen Anleitung. Doch Sie können auch ohne die Anleitung [Geräte hinzufügen](create-and-edit-autopilot-devices.md) und ihnen [Profile zuweisen](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5f7d9-110">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="5f7d9-111">Suchen Sie im Microsoft 365 Business Admin Center die Karte **Geräteaktionen**, und wählen Sie **Windows mit AutoPilot bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-111">In the Microsoft 365 Business admin center, locate the **Device actions** card, and choose **Deploy Windows with Autopilot**.</span></span>
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="5f7d9-113">Klicken oder tippen Sie auf der Seite **Windows vorbereiten** auf **Schnellstarthandbuch**.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-113">On the **Prepare Windows** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="5f7d9-p101">Navigieren Sie auf der Seite **CSV-Datei mit Liste der Geräte hochladen** zu den Speicherorten, an denen Sie die vorbereitete CSV-Datei gespeichert haben, und wählen Sie **Öffnen** \> **Weiter**. Die Datei sollte drei Überschriften aufweisen:</span><span class="sxs-lookup"><span data-stu-id="5f7d9-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="5f7d9-117">Spalte A: Seriennummer des Geräts</span><span class="sxs-lookup"><span data-stu-id="5f7d9-117">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="5f7d9-118">Spalte B: Windows-Produkt-ID</span><span class="sxs-lookup"><span data-stu-id="5f7d9-118">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="5f7d9-119">Spalte C: Hardwarehash</span><span class="sxs-lookup"><span data-stu-id="5f7d9-119">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="5f7d9-120">Diese Informationen erhalten Sie von Ihrem Hardwareanbieter oder durch Verwendung des [PowerShell-Skripts Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), das eine CSV-Datei generiert.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-120">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="5f7d9-p102">Weitere Informationen finden Sie unter [CSV-Datei mit Geräteliste](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Sie können auf der Seite **CSV-Datei mit Liste der Geräte hochladen** auch eine Beispieldatei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="5f7d9-p103">Auf der Seite **Profil zuweisen** können Sie entweder ein vorhandenes Profil auswählen oder ein neues Profil erstellen. Wenn Sie noch keines haben, werden Sie aufgefordert, ein neues zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="5f7d9-125">Ein Profil ist eine Sammlung von Einstellungen, die für ein einzelnes Gerät oder eine Gruppe von Geräten gelten können.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-125">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="5f7d9-p104">Die Standardfunktionen sind erforderlich und werden automatisch festgelegt. Es folgen die Standardfunktionen:</span><span class="sxs-lookup"><span data-stu-id="5f7d9-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="5f7d9-128">Cortana, OneDrive und OEM-Registrierung werden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-128">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="5f7d9-129">Erstellen Sie eine Anmeldeumgebung mit Ihrem Unternehmensbranding.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-129">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="5f7d9-130">Ihre Geräte werden mit Azure Active Directory-Konten verbunden und automatisch für die Verwaltung mit Microsoft 365 Business registriert.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-130">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="5f7d9-131">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="5f7d9-131">For more information, see</span></span>
    
    <span data-ttu-id="5f7d9-132">[Informationen zu AutoPilot-Profileinstellungen](autopilot-profile-settings.md) .</span><span class="sxs-lookup"><span data-stu-id="5f7d9-132">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="5f7d9-133">Die anderen Einstellungen sind **Datenschutzeinstellungen überspringen** und **Nicht zulassen, dass der Benutzer der lokale Administrator wird**. Beide sind standardmäßig auf **Aus** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-133">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="5f7d9-134">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-134">Choose **Next**.</span></span>
    
6. <span data-ttu-id="5f7d9-p105">Die Seite **Fertig** zeigt an, dass das von Ihnen erstellte (oder ausgewählte) Profil auf die Gerätegruppe angewendet wird, die Sie durch das Hochladen der Liste der Geräte erstellt haben. Diese Einstellungen werden wirksam, wenn sich die Benutzer des Geräts als Nächstes wieder anmelden. Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    
---
title: Verwenden der schrittweisen Anleitung zum Hinzufügen von AutoPilot-Geräten und -Profilen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
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
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Erfahren Sie, wie Sie Windows AutoPilot verwenden, um neue Windows 10 für Ihr Unternehmen zu einrichten, damit sie für die Verwendung durch Mitarbeiter bereit sind.
ms.openlocfilehash: e178e7df220e89605502d9ed400265bcd963e57e
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636104"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="8c65d-103">Verwenden der schrittweisen Anleitung zum Hinzufügen von AutoPilot-Geräten und -Profilen</span><span class="sxs-lookup"><span data-stu-id="8c65d-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="8c65d-104">Sie können Windows AutoPilot verwenden, um neue **Windows 10** für Ihr Unternehmen zu einrichten, damit sie einsatzbereit sind, wenn Sie sie Ihren Mitarbeitern zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="8c65d-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="8c65d-105">Geräteanforderungen</span><span class="sxs-lookup"><span data-stu-id="8c65d-105">Device requirements</span></span>

<span data-ttu-id="8c65d-106">Geräte müssen die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="8c65d-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="8c65d-107">Windows 10, Version 1703 oder höher</span><span class="sxs-lookup"><span data-stu-id="8c65d-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="8c65d-108">Neue Geräte, die noch nicht über eine Windows-out-of-Box-Erfahrung verfügen</span><span class="sxs-lookup"><span data-stu-id="8c65d-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="8c65d-109">Befolgen der Setupanleitung zum Erstellen von Geräten und Profilen</span><span class="sxs-lookup"><span data-stu-id="8c65d-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="8c65d-110">Wenn Sie noch keine Gerätegruppen oder Profile erstellt haben, können Sie am besten die schrittweise Anleitung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c65d-110">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="8c65d-111">Sie können auch [Geräte hinzufügen](create-and-edit-autopilot-devices.md) und [ihnen Profile](create-and-edit-autopilot-profiles.md) zuweisen, ohne die Anleitung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c65d-111">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="8c65d-112">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="8c65d-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="8c65d-113">Wählen Sie im linken Navigationsbereich **Geräte** \> **AutoPilot aus.**</span><span class="sxs-lookup"><span data-stu-id="8c65d-113">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![Wählen Sie im Admin Center Geräte und dann AutoPilot aus.](../media/AutoPilot.png)
  
2. <span data-ttu-id="8c65d-115">Klicken oder tippen Sie auf der Seite **AutoPilot** auf **Start guide**.</span><span class="sxs-lookup"><span data-stu-id="8c65d-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="8c65d-117">Navigieren Sie **auf Hochladen .csv Seite "Datei** mit Liste der Geräte" zu einem Speicherort, an dem Sie die vorbereitete .CSV haben, und öffnen Sie **dann** \> **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8c65d-117">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="8c65d-118">Die Datei muss drei Kopfzeilen enthalten:</span><span class="sxs-lookup"><span data-stu-id="8c65d-118">The file must have three headers:</span></span>
    
    - <span data-ttu-id="8c65d-119">Spalte A: Seriennummer des Geräts</span><span class="sxs-lookup"><span data-stu-id="8c65d-119">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="8c65d-120">Spalte B: Windows-Produkt-ID</span><span class="sxs-lookup"><span data-stu-id="8c65d-120">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="8c65d-121">Spalte C: Hardwarehash</span><span class="sxs-lookup"><span data-stu-id="8c65d-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="8c65d-122">Sie können diese Informationen vom Hardwareanbieter abrufen oder das [Get-WindowsAutoPilotInfo PowerShell-Skript](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) verwenden, um eine CSV-Datei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="8c65d-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="8c65d-p103">Weitere Informationen finden Sie unter [CSV-Datei mit Geräteliste](../admin/misc/device-list.md). Sie können auf der Seite **CSV-Datei mit Liste der Geräte hochladen** auch eine Beispieldatei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="8c65d-p103">For more information, see [Device list CSV-file](../admin/misc/device-list.md). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8c65d-125">Dieses Skript verwendet WMI, um Eigenschaften abzurufen, die ein Kunde zum Registrieren eines Geräts bei Windows Autopilot benötigt.</span><span class="sxs-lookup"><span data-stu-id="8c65d-125">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="8c65d-126">Beachten Sie, dass es normal ist, dass die resultierende #A0 keinen Windows Product ID (PKID)-Wert sammelt, da dies nicht erforderlich ist, um ein Gerät zu registrieren, und PKID, die null in der Ausgabe-CSV ist, ist vollkommen in Ordnung.</span><span class="sxs-lookup"><span data-stu-id="8c65d-126">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="8c65d-127">Nur die Seriennummer und der Hardwarehash werden aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="8c65d-127">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="8c65d-128">Auf der **Seite Profil zuweisen** können Sie entweder ein vorhandenes Profil auswählen oder ein neues erstellen.</span><span class="sxs-lookup"><span data-stu-id="8c65d-128">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="8c65d-129">Wenn Sie noch keines haben, werden Sie aufgefordert, eine zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8c65d-129">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="8c65d-130">Ein Profil ist eine Sammlung von Einstellungen, die für ein einzelnes Gerät oder eine Gruppe von Geräten gelten können.</span><span class="sxs-lookup"><span data-stu-id="8c65d-130">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="8c65d-131">Die Standardfeatures sind erforderlich und werden automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8c65d-131">The default features are required and are set automatically.</span></span> <span data-ttu-id="8c65d-132">Es folgen die Standardfunktionen:</span><span class="sxs-lookup"><span data-stu-id="8c65d-132">The default features are:</span></span>
    
    - <span data-ttu-id="8c65d-133">Überspringen Sie Cortana, OneDrive und OEM-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="8c65d-133">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="8c65d-134">Erstellen Sie eine Anmeldeumgebung mit Ihrem Unternehmensbranding.</span><span class="sxs-lookup"><span data-stu-id="8c65d-134">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="8c65d-135">Verbinden Ihre Geräte, Azure Active Directory Konten zu erstellen, und registrieren Sie sie automatisch, damit sie von den Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="8c65d-135">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="8c65d-136">Weitere Informationen finden Sie unter [Informationen zu AutoPilot-Profileinstellungen](autopilot-profile-settings.md).</span><span class="sxs-lookup"><span data-stu-id="8c65d-136">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="8c65d-137">Die anderen Einstellungen sind **Datenschutzeinstellungen überspringen** und **Nicht zulassen, dass der Benutzer der lokale Administrator wird**. Beide sind standardmäßig auf **Aus** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8c65d-137">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="8c65d-138">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="8c65d-138">Choose **Next**.</span></span>
    
6. <span data-ttu-id="8c65d-139">**Sie sind fertig,** gibt an, dass das profil, das Sie erstellt (oder ausgewählt) haben, auf die Gerätegruppe angewendet wird, die Sie erstellt haben, indem Sie die Liste der Geräte hochladen.</span><span class="sxs-lookup"><span data-stu-id="8c65d-139">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="8c65d-140">Die Einstellungen werden wirksam, wenn sich die Gerätebenutzer als Nächstes anmelden.</span><span class="sxs-lookup"><span data-stu-id="8c65d-140">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="8c65d-141">Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="8c65d-141">Choose **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="8c65d-142">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="8c65d-142">Related content</span></span>

<span data-ttu-id="8c65d-143">[Informationen zu AutoPilot-Profileinstellungen](autopilot-profile-settings.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="8c65d-143">[About AutoPilot Profile settings](autopilot-profile-settings.md) (article)</span></span>\
<span data-ttu-id="8c65d-144">[Optionen zum Schutz Ihrer Geräte und App-Daten](../admin/devices/choose-device-security.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="8c65d-144">[Options for protecting your devices and app data](../admin/devices/choose-device-security.md) (article)</span></span>

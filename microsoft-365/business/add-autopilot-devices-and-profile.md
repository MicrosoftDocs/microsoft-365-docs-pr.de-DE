---
title: Verwenden der schrittweisen Anleitung zum Hinzufügen von AutoPilot-Geräten und -Profilen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: In diesem Artikel erfahren Sie, wie Sie Windows Autopilot zum Einrichten neuer Windows 10-Geräte für Ihr Unternehmen verwenden.
ms.openlocfilehash: e5774b1e2079a5249e0f6e9e7142de19268253b5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068531"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="9997e-103">Verwenden der schrittweisen Anleitung zum Hinzufügen von AutoPilot-Geräten und -Profilen</span><span class="sxs-lookup"><span data-stu-id="9997e-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="9997e-104">Sie können Windows Autopilot verwenden, um **neue** Windows 10-Geräte für Ihr Unternehmen einzurichten, damit diese bereitgestellt werden, wenn Sie Sie an Ihre Mitarbeiter weitergeben.</span><span class="sxs-lookup"><span data-stu-id="9997e-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="9997e-105">Geräteanforderungen</span><span class="sxs-lookup"><span data-stu-id="9997e-105">Device requirements</span></span>

<span data-ttu-id="9997e-106">Geräte müssen diese Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="9997e-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="9997e-107">Windows 10, Version 1703 oder höher</span><span class="sxs-lookup"><span data-stu-id="9997e-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="9997e-108">Neue Geräte, die die Out-of-Box-Erfahrung von Windows noch nicht durchlaufen haben</span><span class="sxs-lookup"><span data-stu-id="9997e-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="9997e-109">Befolgen der Setupanleitung zum Erstellen von Geräten und Profilen</span><span class="sxs-lookup"><span data-stu-id="9997e-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="9997e-110">[![Hinweis, der Sie darüber informiert, dass sich das Admin Center ändert und Sie unter "aka.ms/aboutM365preview" weitere Details finden.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="9997e-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="9997e-111">Wenn Sie noch keine Gerätegruppen oder Profile erstellt haben, ist die beste Möglichkeit, mit der ersten Schritte zu beginnen, die schrittweise Anleitung.</span><span class="sxs-lookup"><span data-stu-id="9997e-111">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="9997e-112">Sie können auch [Geräte hinzufügen](create-and-edit-autopilot-devices.md) und Ihnen [profile zuweisen](create-and-edit-autopilot-profiles.md) , ohne die Anleitung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9997e-112">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="9997e-113">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="9997e-113">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="9997e-114">Wählen Sie im linken Navigationsbereich **Geräte** \> **Autopilot**aus.</span><span class="sxs-lookup"><span data-stu-id="9997e-114">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![Wählen Sie im Admin Center Geräte und dann Autopilot aus.](../media/AutoPilot.png)
  
2. <span data-ttu-id="9997e-116">Klicken oder tippen Sie auf der Seite **Autopilot** auf **Start Guide**.</span><span class="sxs-lookup"><span data-stu-id="9997e-116">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="9997e-118">Navigieren Sie auf der Seite **Upload. CSV-Datei mit Geräteliste** zu einem Speicherort, an dem Sie die vorbereitete bereit haben. CSV-Datei, und **Öffnen** \> Sie dann **Next**.</span><span class="sxs-lookup"><span data-stu-id="9997e-118">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="9997e-119">Die Datei muss drei Kopfzeilen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="9997e-119">The file must have three headers:</span></span>
    
    - <span data-ttu-id="9997e-120">Spalte A: Seriennummer des Geräts</span><span class="sxs-lookup"><span data-stu-id="9997e-120">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="9997e-121">Spalte B: Windows-Produkt-ID</span><span class="sxs-lookup"><span data-stu-id="9997e-121">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="9997e-122">Spalte C: Hardwarehash</span><span class="sxs-lookup"><span data-stu-id="9997e-122">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="9997e-123">Sie können diese Informationen von Ihrem Hardwareanbieter abrufen, oder Sie können das [PowerShell-Skript Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) verwenden, um eine CSV-Datei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="9997e-123">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="9997e-p103">Weitere Informationen finden Sie unter [CSV-Datei mit Geräteliste](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Sie können auf der Seite **CSV-Datei mit Liste der Geräte hochladen** auch eine Beispieldatei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9997e-p103">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="9997e-126">Auf der Seite **Profil zuweisen** können Sie entweder ein vorhandenes Profil auswählen oder einen neuen erstellen.</span><span class="sxs-lookup"><span data-stu-id="9997e-126">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="9997e-127">Wenn Sie noch nicht über eine verfügen, werden Sie aufgefordert, eine zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9997e-127">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="9997e-128">Ein Profil ist eine Sammlung von Einstellungen, die für ein einzelnes Gerät oder eine Gruppe von Geräten gelten können.</span><span class="sxs-lookup"><span data-stu-id="9997e-128">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="9997e-129">Die Standardfeatures sind erforderlich und werden automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9997e-129">The default features are required and are set automatically.</span></span> <span data-ttu-id="9997e-130">Es folgen die Standardfunktionen:</span><span class="sxs-lookup"><span data-stu-id="9997e-130">The default features are:</span></span>
    
    - <span data-ttu-id="9997e-131">Überspringen Sie Cortana, OneDrive und OEM-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="9997e-131">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="9997e-132">Erstellen Sie eine Anmeldeumgebung mit Ihrem Unternehmensbranding.</span><span class="sxs-lookup"><span data-stu-id="9997e-132">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="9997e-133">Verbinden Sie Ihre Geräte mit Azure Active Directory-Konten, und registrieren Sie Sie automatisch für die Verwaltung durch Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="9997e-133">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="9997e-134">Weitere Informationen finden Sie unter [Informationen zu Autopilot-Profileinstellungen](autopilot-profile-settings.md).</span><span class="sxs-lookup"><span data-stu-id="9997e-134">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="9997e-135">Die anderen Einstellungen sind **Datenschutzeinstellungen überspringen** und **Nicht zulassen, dass der Benutzer der lokale Administrator wird**. Beide sind standardmäßig auf **Aus** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9997e-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="9997e-136">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="9997e-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="9997e-137">**Sie haben** angegeben, dass das Profil, das Sie erstellt (oder ausgewählt haben), auf die Gerätegruppe angewendet wird, die Sie durch Hochladen der Geräteliste erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="9997e-137">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="9997e-138">Die Einstellungen werden wirksam, wenn sich die Geräte Benutzer als nächstes anmelden.</span><span class="sxs-lookup"><span data-stu-id="9997e-138">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="9997e-139">Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="9997e-139">Choose **Close**.</span></span>
    

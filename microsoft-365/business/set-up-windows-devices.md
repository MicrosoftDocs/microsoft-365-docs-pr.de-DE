---
title: Einrichten von Windows-Geräten für Microsoft 365 Business Premium-Benutzer
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Erfahren Sie, wie Sie Windows-Geräte mit Windows 10 Pro für Microsoft 365 Business Premium-Benutzer einrichten und zentrale Verwaltungs- und Sicherheitssteuerelemente aktivieren.
ms.openlocfilehash: 3e268d81ff6fb7113b7e0b0fe5d0545ff5c72b1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244774"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="b5a6b-103">Einrichten von Windows-Geräten für Microsoft 365 Business Premium-Benutzer</span><span class="sxs-lookup"><span data-stu-id="b5a6b-103">Set up Windows devices for Microsoft 365 Business Premium users</span></span>

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="b5a6b-104">Voraussetzungen für das Einrichten von Windows-Geräten für Microsoft 365 Business Premium-Benutzer</span><span class="sxs-lookup"><span data-stu-id="b5a6b-104">Prerequisites for setting up Windows devices for Microsoft 365 Business Premium users</span></span>

<span data-ttu-id="b5a6b-105">Bevor Sie Windows-Geräte für Microsoft 365 Business Premium-Benutzer einrichten können, stellen Sie sicher, dass auf allen Windows-Geräten Windows 10 Pro, Version 1703 (Creators Update) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-105">Before you can set up Windows devices for Microsoft 365 Business Premium users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update).</span></span> <span data-ttu-id="b5a6b-106">Windows 10 Pro ist eine Voraussetzung für die Bereitstellung von Windows 10 Business, einer Reihe von Clouddiensten und Geräteverwaltungsfunktionen, die Windows 10 Pro ergänzen und die zentralisierten Verwaltungs- und Sicherheitskontrollen von Microsoft 365 Business Premium aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-106">Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business Premium.</span></span>
  
<span data-ttu-id="b5a6b-107">Wenn Sie über Windows-Geräte mit Windows 7 Pro, Windows 8 Pro oder Windows 8.1 Pro verfügen, berechtigt Sie Ihr Microsoft 365 Business Premium-Abonnement zu einem Windows 10-Upgrade.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business Premium subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="b5a6b-108">Weitere Informationen zum Upgrade von Windows-Geräten auf Windows 10 Pro Creators Update erhalten Sie, indem Sie die Schritte in diesem Thema ausführen: [Aktualisieren von Windows-Geräten auf Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="b5a6b-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="b5a6b-109">Weitere Informationen finden Sie unter Überprüfen, ob das Gerät mit [Azure AD](#verify-the-device-is-connected-to-azure-ad) verbunden ist, um sicherzustellen, dass das Upgrade ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="b5a6b-110">Sehen Sie sich ein kurzes Video zum Verbinden von Windows mit Microsoft 365 an.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="b5a6b-111">Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](../business-video/index.yml) an.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../business-video/index.yml).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="b5a6b-112">Verbinden von Windows 10-Geräten in Ihrer Organisation mit Azure AD</span><span class="sxs-lookup"><span data-stu-id="b5a6b-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="b5a6b-113">Wenn alle Windows-Geräte in Ihrer Organisation entweder auf Windows 10 Pro Creators Update aktualisiert wurden oder bereits Windows 10 Pro Creators Update ausgeführt werden, können Sie diese Geräte dem Azure Active Directory Ihrer Organisation hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="b5a6b-114">Sobald die Geräte beigetreten sind, werden sie automatisch auf Windows 10 Business aktualisiert, das Teil Ihres Microsoft 365 Business Premium-Abonnements ist.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business Premium subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="b5a6b-115">Ganz neue oder neu aktualisierte Windows 10 Pro-Geräte</span><span class="sxs-lookup"><span data-stu-id="b5a6b-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="b5a6b-116">Führen Sie für ganze neue Geräte mit Windows 10 Pro Creators Update oder für Geräte, die auf Windows 10 Pro Creators Update aktualisiert wurden, für die die Windows 10-Geräteinstallation jedoch noch nicht ausgeführt wurde, die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="b5a6b-117">Führen Sie die Windows 10-Geräteinstallation aus, bis die Seite **Wie soll das Setup erfolgen** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="b5a6b-119">Wählen Sie hier **Einrichten für eine Organisation aus,** und geben Sie dann Ihren Benutzernamen und Ihr Kennwort für Microsoft 365 Business Premium ein.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business Premium.</span></span> 
    
3. <span data-ttu-id="b5a6b-120">Beenden Sie die Windows 10-Geräteinstallation.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="b5a6b-p103">Sobald Sie fertig sind, wird der Benutzer in Ihrer Organisation mit Azure AD verbunden. Ziehen Sie zur Sicherheit [Sicherstellen, dass das Gerät mit Azure AD verbunden ist](#verify-the-device-is-connected-to-azure-ad) zurate.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="b5a6b-123">Geräte, die bereits eingerichtet wurden und Windows 10 Pro ausführen</span><span class="sxs-lookup"><span data-stu-id="b5a6b-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="b5a6b-124">**Herstellen der Verbindung der Benutzer zu Azure AD:**</span><span class="sxs-lookup"><span data-stu-id="b5a6b-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="b5a6b-125">Klicken Sie auf dem Windows-PC des Benutzers, auf dem Windows 10 Pro, Version 1703 (Creators Update) ausgeführt wird (siehe [Voraussetzungen](pre-requisites-for-data-protection.md)), auf das Windows-Logo und dann auf das Symbol "Einstellungen".</span><span class="sxs-lookup"><span data-stu-id="b5a6b-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="b5a6b-127">Wechseln Sie unter **Einstellungen** zu **Konten**.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="b5a6b-129">Klicken Sie auf der Seite **Ihre Informationen** auf **Auf Arbeits- oder Schulkonto zugreifen** \> **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="b5a6b-131">Wählen Sie im Dialogfeld **Geschäfts-, Schul- oder Unikonto einrichten** unter **Alternative Aktionen** die Option **Dieses Gerät in Azure Active Directory einbinden**.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="b5a6b-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="b5a6b-134">On the **Enter password** page, enter your password \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="b5a6b-136">Überprüfen Sie **auf der** Seite Stellen Sie sicher, dass es sich um Ihre Organisation handelt, ob die Informationen korrekt sind, und wählen Sie Beitreten **aus.**</span><span class="sxs-lookup"><span data-stu-id="b5a6b-136">On the **Make sure this is your organization** page, verify that the information is correct, and choose **Join**.</span></span>
  
   <span data-ttu-id="b5a6b-137">Klicken Sie auf der Seite **Sie sind fertig!**</span><span class="sxs-lookup"><span data-stu-id="b5a6b-137">On the **You're all set!**</span></span> <span data-ttu-id="b5a6b-138">page, chosse **Done**.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-138">page, chosse **Done**.</span></span>
  
   ![Wählen Sie auf dem Bildschirm Stellen Sie sicher, dass dies Ihre Organisation ist, beitreten aus.](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="b5a6b-140">Wenn Sie Dateien nach OneDrive for Business hochgeladen haben, synchronisieren Sie diese wieder.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="b5a6b-141">Wenn Sie ein Drittanbietertool zum Migrieren von Profil und Dateien verwendet haben, synchronisieren Sie diese auch mit dem neuen Profil.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="b5a6b-142">Stellen Sie sicher, dass das Gerät mit Azure AD verbunden ist</span><span class="sxs-lookup"><span data-stu-id="b5a6b-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="b5a6b-143">Um den Synchronisierungsstatus  zu überprüfen, wählen Sie auf der Seite Arbeits- oder Schulzugriff unter **Einstellungen** den Bereich Verbunden mit **_** _ aus, um die \<organization name\> Schaltflächen **Info** und Trennen **verfügbar zu machen.**</span><span class="sxs-lookup"><span data-stu-id="b5a6b-143">To verify your sync status, on the **Access work or school** page in **Settings**, select the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**.</span></span> <span data-ttu-id="b5a6b-144">Wählen **Sie Info** aus, um ihren Synchronisierungsstatus zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-144">Choose **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="b5a6b-145">Wählen Sie **auf der** Seite Synchronisierungsstatus die Option **Synchronisieren** aus, um die neuesten Verwaltungsrichtlinien für mobile Geräte auf dem PC zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-145">On the **Sync status** page, choose **Sync** to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="b5a6b-146">Um mit der Verwendung des Microsoft 365 Business Premium-Kontos zu beginnen, wechseln Sie zur **Windows-Startschaltfläche,** klicken Sie mit der rechten Maustaste auf Ihr aktuelles Kontobild, und wechseln Sie **dann auf Konto wechseln.**</span><span class="sxs-lookup"><span data-stu-id="b5a6b-146">To start using the Microsoft 365 Business Premium account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="b5a6b-147">Melden Sie sich mit der E-Mail-Adresse und dem Kennwort Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a><span data-ttu-id="b5a6b-149">Überprüfen, ob der PC auf Windows 10 Business aktualisiert wurde</span><span class="sxs-lookup"><span data-stu-id="b5a6b-149">Verify the PC is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="b5a6b-150">Stellen Sie sicher, dass Ihre Azure AD-Geräte, die Windows 10-Geräten beigetreten sind, im Rahmen Ihres Microsoft 365 Business Premium-Abonnements auf Windows 10 Business aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-150">Verify that your Azure AD joined Windows 10 devices are upgraded to Windows 10 Business as part of your Microsoft 365 Business Premium subscription.</span></span>
  
1. <span data-ttu-id="b5a6b-151">Wechseln Sie zu **Einstellungen** \> **System** \> **Info**.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="b5a6b-152">Überprüfen Sie, ob unter **Edition** **Windows 10 Business** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b5a6b-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="b5a6b-154">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b5a6b-154">Next steps</span></span>

<span data-ttu-id="b5a6b-155">Informationen zum Einrichten Ihrer mobilen Geräte finden Sie unter Einrichten mobiler Geräte für [Microsoft 365 Business Premium-Benutzer](set-up-mobile-devices.md), Informationen zum Festlegen von Geräteschutz- oder App-Schutzrichtlinien finden Sie unter [Verwalten von Microsoft 365 Business](manage.md).</span><span class="sxs-lookup"><span data-stu-id="b5a6b-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 for business](manage.md).</span></span>
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a><span data-ttu-id="b5a6b-156">Weitere Informationen zum Einrichten und Verwenden von Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="b5a6b-156">For more on setting up and using Microsoft 365 Business Premium</span></span>

[<span data-ttu-id="b5a6b-157">Microsoft 365 für Unternehmen-Schulungsvideos</span><span class="sxs-lookup"><span data-stu-id="b5a6b-157">Microsoft 365 for business training videos</span></span>](../business-video/index.yml)

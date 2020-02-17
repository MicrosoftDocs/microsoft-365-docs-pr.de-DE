---
title: Einrichten von Windows-Geräten für Benutzer von Microsoft 365 Business
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 'Hier erfahren Sie, wie Sie Windows-Geräte mit Windows 10 pro für Microsoft 365 Business-Benutzer einrichten. '
ms.openlocfilehash: 427e1c25b5c6ad52ab280502133a0e2808bb48b1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42090674"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a><span data-ttu-id="7118d-103">Einrichten von Windows-Geräten für Benutzer von Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="7118d-103">Set up Windows devices for Microsoft 365 Business users</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7118d-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7118d-104">Prerequisites</span></span>

<span data-ttu-id="7118d-p101">Bevor Sie die Windows-Geräte für Microsoft 365 Business-Benutzer einrichten können, stellen Sie sicher, dass auf allen Windows-Geräten Windows 10 Pro, Version 1703 (Creators Update)) ausgeführt wird. Windows 10 Pro ist Voraussetzung für die Bereitstellung von Windows 10 Business. Windows 10 Business besteht aus einer Reihe von Clouddiensten und Funktionen zur Geräteverwaltung, die Windows 10 Pro ergänzen und die zentrale Verwaltung und Sicherheitskontrollen von Microsoft 365 Business ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7118d-p101">Before you can set up Windows devices for Microsoft 365 Business users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update). Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business.</span></span>
  
<span data-ttu-id="7118d-107">Wenn Sie Windows-Geräte unter Windows 7 Pro, Windows 8 Pro oder Windows 8.1 Pro einsetzen, sind Sie im Rahmen Ihres Microsoft 365 Business-Abonnements berechtigt, auf Windows 10 zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7118d-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="7118d-108">Weitere Informationen zum Upgrade von Windows-Geräten auf Windows 10 Pro Creators Update erhalten Sie, indem Sie die Schritte in diesem Thema ausführen: [Aktualisieren von Windows-Geräten auf Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="7118d-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="7118d-109">Stellen Sie sicher, dass das [Gerät mit Azure AD verbunden ist](#verify-the-device-is-connected-to-azure-ad) , um zu überprüfen, ob das Upgrade ausgeführt wurde, oder ob das Upgrade erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="7118d-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="7118d-110">Sehen Sie sich ein kurzes Video über die Verbindung von Windows mit Microsoft 365 an.</span><span class="sxs-lookup"><span data-stu-id="7118d-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="7118d-111">Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816), an.</span><span class="sxs-lookup"><span data-stu-id="7118d-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="7118d-112">Verbinden von Windows 10-Geräten in Ihrer Organisation mit Azure AD</span><span class="sxs-lookup"><span data-stu-id="7118d-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="7118d-113">Wenn alle Windows-Geräte in Ihrer Organisation entweder auf Windows 10 pro Creators-Update aktualisiert wurden oder bereits Windows 10 pro Creators Update ausgeführt wurden, können Sie diese Geräte mit der Azure-Active Directory Ihrer Organisation verbinden.</span><span class="sxs-lookup"><span data-stu-id="7118d-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="7118d-114">Sobald die Geräte verbunden sind, werden Sie automatisch auf Windows 10 Business aktualisiert, das Teil Ihres Microsoft 365 Business-Abonnements ist.</span><span class="sxs-lookup"><span data-stu-id="7118d-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="7118d-115">Ganz neue oder neu aktualisierte Windows 10 Pro-Geräte</span><span class="sxs-lookup"><span data-stu-id="7118d-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="7118d-116">Führen Sie für ganze neue Geräte mit Windows 10 Pro Creators Update oder für Geräte, die auf Windows 10 Pro Creators Update aktualisiert wurden, für die die Windows 10-Geräteinstallation jedoch noch nicht ausgeführt wurde, die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="7118d-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="7118d-117">Führen Sie die Windows 10-Geräteinstallation aus, bis die Seite **Wie soll das Setup erfolgen** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7118d-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="7118d-119">Wählen Sie hier **Für eine Organisation einrichten** aus, und geben Sie Ihren Benutzernamen und das Kennwort für Microsoft 365 Business ein.</span><span class="sxs-lookup"><span data-stu-id="7118d-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business.</span></span> 
    
3. <span data-ttu-id="7118d-120">Beenden Sie die Windows 10-Geräteinstallation.</span><span class="sxs-lookup"><span data-stu-id="7118d-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="7118d-p103">Sobald Sie fertig sind, wird der Benutzer in Ihrer Organisation mit Azure AD verbunden. Ziehen Sie zur Sicherheit [Sicherstellen, dass das Gerät mit Azure AD verbunden ist](#verify-the-device-is-connected-to-azure-ad) zurate.</span><span class="sxs-lookup"><span data-stu-id="7118d-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="7118d-123">Geräte, die bereits eingerichtet wurden und Windows 10 Pro ausführen</span><span class="sxs-lookup"><span data-stu-id="7118d-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="7118d-124">**Herstellen der Verbindung der Benutzer zu Azure AD:**</span><span class="sxs-lookup"><span data-stu-id="7118d-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="7118d-125">Klicken Sie auf dem Windows-PC des Benutzers, auf dem Windows 10 Pro, Version 1703 (Creators Update) ausgeführt wird (siehe [Voraussetzungen](pre-requisites-for-data-protection.md)), auf das Windows-Logo und dann auf das Symbol "Einstellungen".</span><span class="sxs-lookup"><span data-stu-id="7118d-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="7118d-127">Wechseln Sie unter **Einstellungen** zu **Konten**.</span><span class="sxs-lookup"><span data-stu-id="7118d-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="7118d-129">Klicken Sie auf der Seite **Ihre Informationen** auf **Auf Arbeits- oder Schulkonto zugreifen** \> **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="7118d-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="7118d-131">Wählen Sie im Dialogfeld **Geschäfts-, Schul- oder Unikonto einrichten** unter **Alternative Aktionen** die Option **Dieses Gerät in Azure Active Directory einbinden**.</span><span class="sxs-lookup"><span data-stu-id="7118d-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="7118d-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="7118d-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="7118d-134">On the **Enter password** page, enter your password \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="7118d-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="7118d-136">Überprüfen Sie auf der Seite **Stellen Sie sicher, dass es sich um Ihre Organisation handelt** , dass die Informationen richtig sind, und klicken Sie auf **beitreten**.</span><span class="sxs-lookup"><span data-stu-id="7118d-136">On the **Make sure this is your organization** page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="7118d-p104">Klicken Sie auf der Seite **Sie sind fertig!** auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="7118d-p104">On the **You're all set!** page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="7118d-140">Wenn Sie Dateien nach OneDrive for Business hochgeladen haben, synchronisieren Sie diese wieder.</span><span class="sxs-lookup"><span data-stu-id="7118d-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="7118d-141">Wenn Sie ein Drittanbietertool zum Migrieren von Profil und Dateien verwendet haben, synchronisieren Sie diese ebenfalls mit dem neuen Profil.</span><span class="sxs-lookup"><span data-stu-id="7118d-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="7118d-142">Stellen Sie sicher, dass das Gerät mit Azure AD verbunden ist</span><span class="sxs-lookup"><span data-stu-id="7118d-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="7118d-p106">Um Ihren Synchronisierungsstatus zu überprüfen, klicken Sie auf der Seite **Auf Arbeits- oder Schulkonto zugreifen** unter **Einstellungen** in den Bereich **Verbunden mit** _ \<organization name\> _, um die Schaltflächen **Info** und **Trennen** verfügbar zu machen. Klicken Sie auf **Info**, um Ihren Synchronisierungsstatus abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7118d-p106">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**. Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="7118d-145">Klicken Sie auf der Seite "Synchronisierungsstatus" auf "Synchronisieren", um die neuesten Verwaltungsrichtlinien für Mobilgeräte auf den Computer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7118d-145">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="7118d-146">Um mit dem Microsoft 365 Business-Konto zu beginnen, wechseln Sie zur Windows-Schaltfläche **Start** , klicken Sie mit der rechten Maustaste auf Ihr aktuelles Kontobild, und wechseln Sie dann zu **Konto**.</span><span class="sxs-lookup"><span data-stu-id="7118d-146">To start using the Microsoft 365 Business account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="7118d-147">Melden Sie sich mit der E-Mail-Adresse und dem Kennwort Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="7118d-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="7118d-149">Sicherstellen, dass das Gerät auf Windows 10 Business aktualisiert wurde</span><span class="sxs-lookup"><span data-stu-id="7118d-149">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="7118d-150">Stellen Sie sicher, dass Ihre mit Azure AD verbundenen Windows 10-Geräte im Rahmen Ihres Microsoft 365 Business-Abonnements auf Windows 10 Business aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="7118d-150">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business subscription.</span></span>
  
1. <span data-ttu-id="7118d-151">Wechseln Sie zu **Einstellungen** \> **System** \> **Info**.</span><span class="sxs-lookup"><span data-stu-id="7118d-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="7118d-152">Überprüfen Sie, ob unter **Edition** **Windows 10 Business** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7118d-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="7118d-154">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7118d-154">Next steps</span></span>

<span data-ttu-id="7118d-155">Informationen zum Einrichten von mobilen Geräten finden Sie unter [Einrichten von mobilen Geräten für Microsoft 365 Business-Benutzer](set-up-mobile-devices.md). Informationen zum Festlegen von Richtlinien zum Schutz von Geräten oder Apps finden Sie unter [Verwalten von Microsoft 365 Business](manage.md).</span><span class="sxs-lookup"><span data-stu-id="7118d-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 Business](manage.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7118d-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7118d-156">See also</span></span>

[<span data-ttu-id="7118d-157">Microsoft 365 Business-Schulungsvideos</span><span class="sxs-lookup"><span data-stu-id="7118d-157">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)

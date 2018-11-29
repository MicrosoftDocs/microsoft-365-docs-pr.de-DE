---
title: Einrichten von Windows-Geräten für Benutzer von Microsoft 365 Business
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
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 'Hier erfahren Sie, wie Sie Windows-Geräte unter Windows 10 Pro für Microsoft 365 Geschäftsbenutzer einrichten. '
ms.openlocfilehash: 482199b175c568bfae420619aa02024303894789
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867772"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a><span data-ttu-id="431ac-103">Einrichten von Windows-Geräten für Benutzer von Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="431ac-103">Set up Windows devices for Microsoft 365 Business users</span></span>

## <a name="prerequisites"></a><span data-ttu-id="431ac-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="431ac-104">Prerequisites</span></span>

<span data-ttu-id="431ac-p101">Bevor Sie die Windows-Geräte für Microsoft 365 Business-Benutzer einrichten können, stellen Sie sicher, dass auf allen Windows-Geräten Windows 10 Pro, Version 1703 (Creators Update)) ausgeführt wird. Windows 10 Pro ist Voraussetzung für die Bereitstellung von Windows 10 Business. Windows 10 Business besteht aus einer Reihe von Clouddiensten und Funktionen zur Geräteverwaltung, die Windows 10 Pro ergänzen und die zentrale Verwaltung und Sicherheitskontrollen von Microsoft 365 Business ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="431ac-p101">Before you can set up Windows devices for Microsoft 365 Business users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update). Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business.</span></span>
  
<span data-ttu-id="431ac-107">Wenn Sie Windows-Geräte unter Windows 7 Pro, Windows 8 Pro oder Windows 8.1 Pro einsetzen, sind Sie im Rahmen Ihres Microsoft 365 Business-Abonnements berechtigt, auf Windows 10 zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="431ac-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="431ac-108">Weitere Informationen zum Upgrade von Windows-Geräten auf Windows 10 Pro Creators Update erhalten Sie, indem Sie die Schritte in diesem Thema ausführen: [Aktualisieren von Windows-Geräten auf Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="431ac-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="431ac-109">Ziehen Sie [Sicherstellen, dass das Gerät auf Windows 10 Business aktualisiert wurde](set-up-windows-devices.md#bkmk_verifywin10) zurate, um sich zu vergewissern, dass Sie über das Upgrade verfügen bzw. dass das Upgrade erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="431ac-109">See [Verify the device is upgraded to Windows 10 Business](set-up-windows-devices.md#bkmk_verifywin10) to verify you have the upgrade, or to make sure the upgrade worked.</span></span> 
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="431ac-110">Verbinden von Windows 10-Geräten in Ihrer Organisation mit Azure AD</span><span class="sxs-lookup"><span data-stu-id="431ac-110">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="431ac-p102">Nachdem alle Windows-Geräte in Ihrer Organisation entweder auf Windows 10 Pro Creators Update aktualisiert wurden oder bereits Windows 10 Pro Creators Update ausführen, können Sie diese Geräte in Ihrer Organisation mit Azure Active Directory verbinden. Sobald die Geräte verbunden sind, werden sie automatisch auf Windows 10 Business aktualisiert, das Teil Ihres Microsoft 365 Business-Abonnements ist.</span><span class="sxs-lookup"><span data-stu-id="431ac-p102">Once all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory. Once the devices are joined, they will automatically be upgraded to Windows 10 Business, which is part of your Microsoft 365 Business subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="431ac-113">Ganz neue oder neu aktualisierte Windows 10 Pro-Geräte</span><span class="sxs-lookup"><span data-stu-id="431ac-113">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="431ac-114">Führen Sie für ganze neue Geräte mit Windows 10 Pro Creators Update oder für Geräte, die auf Windows 10 Pro Creators Update aktualisiert wurden, für die die Windows 10-Geräteinstallation jedoch noch nicht ausgeführt wurde, die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="431ac-114">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="431ac-115">Führen Sie die Windows 10-Geräteinstallation aus, bis die Seite **Wie soll das Setup erfolgen** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="431ac-115">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="431ac-117">Wählen Sie hier **Für eine Organisation einrichten** aus, und geben Sie Ihren Benutzernamen und das Kennwort für Microsoft 365 Business ein.</span><span class="sxs-lookup"><span data-stu-id="431ac-117">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business.</span></span> 
    
3. <span data-ttu-id="431ac-118">Beenden Sie die Windows 10-Geräteinstallation.</span><span class="sxs-lookup"><span data-stu-id="431ac-118">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="431ac-p103">Sobald Sie fertig sind, wird der Benutzer in Ihrer Organisation mit Azure AD verbunden. Ziehen Sie zur Sicherheit [Sicherstellen, dass das Gerät mit Azure AD verbunden ist](set-up-windows-devices.md#bkmk_verifyaad) zurate.</span><span class="sxs-lookup"><span data-stu-id="431ac-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](set-up-windows-devices.md#bkmk_verifyaad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="431ac-121">Geräte, die bereits eingerichtet wurden und Windows 10 Pro ausführen</span><span class="sxs-lookup"><span data-stu-id="431ac-121">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="431ac-122">**Herstellen der Verbindung der Benutzer zu Azure AD:**</span><span class="sxs-lookup"><span data-stu-id="431ac-122">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="431ac-123">Klicken Sie auf dem Windows-PC des Benutzers, auf dem Windows 10 Pro, Version 1703 (Creators Update) ausgeführt wird (siehe [Voraussetzungen](pre-requisites-for-data-protection.md)), auf das Windows-Logo und dann auf das Symbol "Einstellungen".</span><span class="sxs-lookup"><span data-stu-id="431ac-123">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="431ac-125">Wechseln Sie unter **Einstellungen** zu **Konten**.</span><span class="sxs-lookup"><span data-stu-id="431ac-125">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="431ac-127">Klicken Sie auf der Seite **Ihre Informationen** auf **Auf Arbeits- oder Schulkonto zugreifen** \> **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="431ac-127">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="431ac-129">Wählen Sie im Dialogfeld **Geschäfts-, Schul- oder Unikonto einrichten** unter **Alternative Aktionen** die Option **Dieses Gerät in Azure Active Directory einbinden**.</span><span class="sxs-lookup"><span data-stu-id="431ac-129">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="431ac-131">Geben Sie auf der Seite **Fangen Sie angemeldet** Ihr Konto arbeiten oder Schule \> **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="431ac-131">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="431ac-132">Geben Sie auf der Seite **Kennwort eingeben** , Ihr Kennwort \> **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="431ac-132">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="431ac-134">Klicken Sie auf die \*\* sicherstellen, dass dies ist Ihre Organisation \*\* Seite, stellen Sie sicher, dass die Informationen korrekt sind, und klicken Sie auf **teilnehmen**.</span><span class="sxs-lookup"><span data-stu-id="431ac-134">On the \*\* Make sure this is your organization \*\* page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="431ac-p104">Klicken Sie auf der Seite **Sie sind fertig!** auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="431ac-p104">On the **You're all set!** page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="431ac-p105">Wenn Sie Dateien nach OneDrive for Business hochgeladen haben, synchronisieren Sie diese wieder. Wenn Sie ein Drittanbietertool zum Migrieren von Profil und Dateien verwendet haben, synchronisieren Sie diese auch in das neue Profil.</span><span class="sxs-lookup"><span data-stu-id="431ac-p105">If you uploaded files to OneDrive for Business, sync them back down. If you used a third party tool to migrate profile and files, sync those also to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="431ac-140">Sicherstellen, dass das Gerät mit Azure AD verbunden ist</span><span class="sxs-lookup"><span data-stu-id="431ac-140">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="431ac-p106">Um Ihren Synchronisierungsstatus zu überprüfen, klicken Sie auf der Seite **Auf Arbeits- oder Schulkonto zugreifen** unter **Einstellungen** in den Bereich **Verbunden mit** _ \<organization name\> _, um die Schaltflächen **Info** und **Trennen** verfügbar zu machen. Klicken Sie auf **Info**, um Ihren Synchronisierungsstatus abzurufen.</span><span class="sxs-lookup"><span data-stu-id="431ac-p106">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**. Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="431ac-143">Klicken Sie auf der Seite "Synchronisierungsstatus" auf "Synchronisieren", um die neuesten Verwaltungsrichtlinien für Mobilgeräte auf den Computer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="431ac-143">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="431ac-p107">Um mit der Verwendung des Microsoft 365 Business-Kontos zu beginen, klicken Sie auf die Windows-Schaltfläche **Start**, klicken Sie mit der rechten Maustaste auf das Bild Ihres aktuellen Kontos, und klicken Sie dann auf **Konto wechseln**. Melden Sie sich mit der E-Mail-Adresse und dem Kennwort Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="431ac-p107">To start using the Microsoft 365 Business account, go to the Windows **Start** button, right-click your current account picture and then **Switch account**. Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="431ac-147">Sicherstellen, dass das Gerät auf Windows 10 Business aktualisiert wurde</span><span class="sxs-lookup"><span data-stu-id="431ac-147">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="431ac-148">Stellen Sie sicher, dass Ihre mit Azure AD verbundenen Windows 10-Geräte im Rahmen Ihres Microsoft 365 Business-Abonnements auf Windows 10 Business aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="431ac-148">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business subscription.</span></span>
  
1. <span data-ttu-id="431ac-149">Wechseln Sie zu **Einstellungen** \> **System** \> **Info**.</span><span class="sxs-lookup"><span data-stu-id="431ac-149">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="431ac-150">Überprüfen Sie, ob unter **Edition** **Windows 10 Business** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="431ac-150">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="431ac-152">Weitere Schritte</span><span class="sxs-lookup"><span data-stu-id="431ac-152">Next steps</span></span>

<span data-ttu-id="431ac-153">Informationen zum Einrichten von mobilen Geräten finden Sie unter [Einrichten von mobilen Geräten für Microsoft 365 Business-Benutzer](set-up-mobile-devices.md). Informationen zum Festlegen von Richtlinien zum Schutz von Geräten oder Apps finden Sie unter [Verwalten von Microsoft 365 Business](manage.md).</span><span class="sxs-lookup"><span data-stu-id="431ac-153">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 Business](manage.md).</span></span>
  

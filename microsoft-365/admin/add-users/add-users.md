---
title: Benutzer einzeln oder in Massen hinzufügen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1970f7d6-03b5-442f-b385-5880b9c256ec
description: In diesem Artikel erfahren Sie, wie Sie Benutzer gleichzeitig oder mehrere Benutzer gleichzeitig aus einer CSV-Datei zu Microsoft 365 hinzufügen.
ms.openlocfilehash: af160b78317171bec98dcfa3d5877b53560f75a2
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780661"
---
# <a name="add-users-individually-or-in-bulk"></a><span data-ttu-id="dcc7d-103">Benutzer einzeln oder in Massen hinzufügen</span><span class="sxs-lookup"><span data-stu-id="dcc7d-103">Add users individually or in bulk</span></span>

<span data-ttu-id="dcc7d-104">Die Personen in Ihrem Team benötigen jeweils ein Benutzerkonto, bevor Sie sich anmelden und auf [Microsoft 365 for Business](https://go.microsoft.com/fwlink/?LinkID=519395)zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-104">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="dcc7d-105">Die einfachste Methode zum Hinzufügen von Benutzerkonten besteht darin, sie im Microsoft 365 Admin Center nacheinander hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-105">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="dcc7d-106">Nachdem Sie diesen Schritt durchführen, verfügen Ihre Benutzer über Microsoft 365-Lizenzen, Anmeldeinformationen und Microsoft 365-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-106">After you do this step, your users will have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="dcc7d-107">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-107">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="dcc7d-108">Wählen Sie **Benutzer** > **Aktive Benutzer** und **Benutzer hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-108">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
3. <span data-ttu-id="dcc7d-109">Geben Sie im Bereich **Grundlagen einrichten** die nachstehenden Informationen ein, und wählen Sie dann**Weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-109">In the **Set up the basics** pane, fill in the following information, and then select **Next**.</span></span> 
  
- <span data-ttu-id="dcc7d-110">**Name** Geben Sie Vornamen, Nachnamen, Anzeigenamen und Benutzernamen ein.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-110">**Name** Fill in first, last, display name, and username.</span></span> 
    
- <span data-ttu-id="dcc7d-111">**Domäne** Wenn beispielsweise der Benutzername Jakob ist und seine Domäne contoso.com ist, meldet er sich bei durch Eingabe von Jakob@contoso.com an.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-111">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="dcc7d-112">**Kennworteinstellungen** Wählen Sie das automatisch generierte Kennwort aus, oder erstellen Sie ein sicheres Kennwort für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-112">**Password settings** Choose to the use auto-generated password or create your own strong password for the user.</span></span> 
    
    - <span data-ttu-id="dcc7d-113">Dieser muss sein Kennwort nach 90 Tagen ändern. </span><span class="sxs-lookup"><span data-stu-id="dcc7d-113">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="dcc7d-114">Sie können aber auch die folgende Option auswählen: **Anfordern, dass dieser Benutzer bei der ersten Anmeldung sein Kennwort ändert**.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-114">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    
    - <span data-ttu-id="dcc7d-115">Wählen Sie aus, ob das Kennwort per E-Mail gesendet werden soll, nachdem der Benutzer hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-115">Choose whether you want to  send the password in email when the user has been added.</span></span> 
    
4. <span data-ttu-id="dcc7d-116">Wählen Sie im Bereich **Produktlizenzen zuweisen** den Speicherort und die entsprechende Lizenz für den Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-116">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="dcc7d-117">Wenn Sie keine Lizenzen zur Verfügung haben, können Sie trotzdem einen Benutzer hinzufügen und zusätzliche Lizenzen kaufen.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-117">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="dcc7d-118">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-118">Select **Next**.</span></span>

5. <span data-ttu-id="dcc7d-119">Erweitern Sie auf der Seite **Optionale Einstellungen** die Option **Rollen**, wenn Sie diesen Benutzer als Administrator festlegen möchten, und erweitern Sie **Profilinformationen**, wenn Sie weitere Informationen zum Benutzer hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-119">In the **Optional settings** page, expand **Roles** if you want to make this user an admin, and expand **Profile info** if you want to add additional information about the user.</span></span> 

6. <span data-ttu-id="dcc7d-120">Wählen Sie **Weiter**aus, überprüfen Sie die Einstellungen des neuen Benutzers, nehmen Sie eventuell Änderungen vor, und wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-120">Select **Next**, review your new user's settings, make any changes you like, and then select **Finish adding**.</span></span> 

::: moniker-end


::: moniker range="o365-germany"

1. <span data-ttu-id="dcc7d-121">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-121">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

2. <span data-ttu-id="dcc7d-122">Wählen Sie **Benutzer** > **Aktive Benutzer** und **Benutzer hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-122">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="dcc7d-123">Geben Sie im Bereich **Neuer Benutzer** die nachstehenden Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-123">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="dcc7d-124">Wenn Sie damit fertig sind, wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-124">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="dcc7d-125">**Name** Geben Sie den Vornamen, Nachnamen, Anzeigenamen und Benutzernamen ein. </span><span class="sxs-lookup"><span data-stu-id="dcc7d-125">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="dcc7d-126">**Domäne** Wenn beispielsweise der Benutzername Jakob ist und seine Domäne contoso.com ist, meldet er sich bei durch Eingabe von Jakob@contoso.com an.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-126">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="dcc7d-127">**Kontaktinformationen** Erweitern Sie diesen Abschnitt, um eine Mobiltelefonnummer, Anschrift usw. einzugeben. </span><span class="sxs-lookup"><span data-stu-id="dcc7d-127">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="dcc7d-128">**Kennwort** Verwenden Sie das automatisch generierte Kennwort, oder erweitern Sie den Abschnitt, um ein sicheres Kennwort für den Benutzer festzulegen. </span><span class="sxs-lookup"><span data-stu-id="dcc7d-128">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="dcc7d-129">They'll need to change their password after 90 days.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-129">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="dcc7d-130">Or you can choose to **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-130">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="dcc7d-131">**Rollen** Erweitern Sie diesen Abschnitt, wenn der betreffende Benutzer ein Administrator werden soll. </span><span class="sxs-lookup"><span data-stu-id="dcc7d-131">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="dcc7d-132">**Product licenses** Expand this section and select the appropriate license.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-132">**Product licenses** Expand this section and select the appropriate license.</span></span> <span data-ttu-id="dcc7d-133">If you don't have any licenses available, you can still add a user and buy additional licenses.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-133">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="dcc7d-134">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-134">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

2. <span data-ttu-id="dcc7d-135">Wählen Sie **Benutzer** > **Aktive Benutzer** und **Benutzer hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-135">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="dcc7d-136">Geben Sie im Bereich **Neuer Benutzer** die nachstehenden Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-136">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="dcc7d-137">Wenn Sie damit fertig sind, wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-137">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="dcc7d-138">**Name** Geben Sie den Vornamen, Nachnamen, Anzeigenamen und Benutzernamen ein. </span><span class="sxs-lookup"><span data-stu-id="dcc7d-138">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="dcc7d-139">**Domäne** Wenn beispielsweise der Benutzername Jakob ist und seine Domäne contoso.com ist, meldet er sich bei durch Eingabe von Jakob@contoso.com an.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-139">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="dcc7d-140">**Kontaktinformationen** Erweitern Sie diesen Abschnitt, um eine Mobiltelefonnummer, Anschrift usw. einzugeben. </span><span class="sxs-lookup"><span data-stu-id="dcc7d-140">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="dcc7d-141">**Kennwort** Verwenden Sie das automatisch generierte Kennwort, oder erweitern Sie den Abschnitt, um ein sicheres Kennwort für den Benutzer festzulegen. </span><span class="sxs-lookup"><span data-stu-id="dcc7d-141">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="dcc7d-142">They'll need to change their password after 90 days.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-142">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="dcc7d-143">Or you can choose to **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-143">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="dcc7d-144">**Rollen** Erweitern Sie diesen Abschnitt, wenn der betreffende Benutzer ein Administrator werden soll. </span><span class="sxs-lookup"><span data-stu-id="dcc7d-144">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="dcc7d-145">**Product licenses** Expand this section and select the appropriate license.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-145">**Product licenses** Expand this section and select the appropriate license.</span></span> <span data-ttu-id="dcc7d-146">If you don't have any licenses available, you can still add a user and buy additional licenses.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-146">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end 
  
<span data-ttu-id="dcc7d-147">Nachdem Sie einen Benutzer hinzugefügt haben, erhalten Sie eine E-Mail-Benachrichtigung vom Microsoft Online Services-Team.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-147">After you add a user, you'll get an email notification from the Microsoft Online Services Team.</span></span> <span data-ttu-id="dcc7d-148">Die e-Mail enthält die Benutzer-ID und das Kennwort der Person, damit Sie sich bei Microsoft 365 anmelden können.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-148">The email will contain the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="dcc7d-149">Sie müssen ihren neuen Benutzer über die Microsoft 365-Anmeldeinformationen informieren.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-149">You need to tell your new user about their Microsoft 365 sign in information.</span></span> <span data-ttu-id="dcc7d-150">Verwenden Sie hierzu Ihre normale Vorgehensweise für die Übermittlung neuer Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-150">Use your normal process for communicating new passwords.</span></span>

> [!NOTE]
><span data-ttu-id="dcc7d-151">Wenn Sie Benutzer durch die Migration von e-Mail-Boxen erstellen, müssen Sie Benutzerkonten durch die Zuweisung von Lizenzen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-151">If you create users by migrating mail boxes, you will need to activate user accounts by assigning licenses.</span></span> <span data-ttu-id="dcc7d-152">Wenn Sie einem Benutzer keine Lizenz zuweisen, wird sein Postfach nach Ablauf einer 30-tägigen Kulanzzeit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-152">If you don't assign a license to a user, their mailbox will be disabled after a grace period of 30 days.</span></span> <span data-ttu-id="dcc7d-153">Erfahren Sie, wie Sie [Benutzern Lizenzen zuweisen](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) unter Verwendung des Microsoft 365 Admin Centers.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-153">See how to [assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) using the Microsoft 365 admin center.</span></span>

### <a name="video-add-and-manage-users-in-the-admin-center"></a><span data-ttu-id="dcc7d-154">Video: Benutzer im Admin Center hinzufügen und verwalten</span><span class="sxs-lookup"><span data-stu-id="dcc7d-154">Video: Add and manage users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]
  
## <a name="next-steps"></a><span data-ttu-id="dcc7d-155">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="dcc7d-155">Next steps</span></span>

<span data-ttu-id="dcc7d-156">Geben Sie das [Schnellstarthandbuch für Mitarbeiter](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) für Ihre neuen Benutzer frei, um etwas einzurichten, z. B. [Office auf einem PC oder Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) und [mobile Office-Apps](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="dcc7d-156">Share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your new users to set things up, like [Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [Office mobile apps](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>
  
## <a name="need-help"></a><span data-ttu-id="dcc7d-157">Benötigen Sie Hilfe?</span><span class="sxs-lookup"><span data-stu-id="dcc7d-157">Need help?</span></span>

<span data-ttu-id="dcc7d-158">[Wenden Sie sich an Microsoft 365 for Business Support](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="dcc7d-158">[Contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>  

## <a name="have-hundreds-or-thousands-of-users-to-add"></a><span data-ttu-id="dcc7d-159">Müssen Sie Hunderte oder Tausende von Benutzern hinzufügen?</span><span class="sxs-lookup"><span data-stu-id="dcc7d-159">Have hundreds or thousands of users to add?</span></span>


<span data-ttu-id="dcc7d-160">Wenn Sie mehrere Benutzer gleichzeitig hinzufügen möchten, führen Sie die folgenden Schritte aus: </span><span class="sxs-lookup"><span data-stu-id="dcc7d-160">To add multiple users at the same time, follow these steps:</span></span>
  
- <span data-ttu-id="dcc7d-161">**Mithilfe einer Kalkulationstabelle können Sie Benutzer in Massen hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="dcc7d-161">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="dcc7d-162">Weitere Informationen hierzu finden Sie unter [Gleichzeitiges Hinzufügen von mehreren Benutzern](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span><span class="sxs-lookup"><span data-stu-id="dcc7d-162">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
    
- <span data-ttu-id="dcc7d-163">**Automatisieren Sie das Hinzufügen von Konten und Zuweisen von Lizenzen.**</span><span class="sxs-lookup"><span data-stu-id="dcc7d-163">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="dcc7d-164">Informationen hierzu finden Sie unter [Erstellen von Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="dcc7d-164">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="dcc7d-165">Wählen Sie diese Methode aus, wenn Sie mit der Nutzung von Windows PowerShell-Cmdlets bereits vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-165">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
    
- <span data-ttu-id="dcc7d-166">**Sie verwenden Active Directory?**</span><span class="sxs-lookup"><span data-stu-id="dcc7d-166">**Using ActiveDirectory?**</span></span> <span data-ttu-id="dcc7d-167">[Richten Sie die Verzeichnissynchronisierung für Office 365 ein](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="dcc7d-167">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="dcc7d-168">Mithilfe des Azure AD Connect-Tools können Sie Active Directory-Benutzerkonten (und andere Active Directory-Objekte) in Office 365 replizieren.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-168">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Office 365.</span></span> <span data-ttu-id="dcc7d-169">Bei der Synchronisierung werden nur die Benutzerkonten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-169">The sync only adds the user accounts.</span></span> <span data-ttu-id="dcc7d-170">Sie müssen den synchronisierten Benutzern Lizenzen zuweisen, damit sie E-Mail und andere Office-Apps verwenden können.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-170">You will need to assign licenses to the synced users before they can use email and other Office apps.</span></span>
    
- <span data-ttu-id="dcc7d-171">**Sie migrieren aus Exchange?**</span><span class="sxs-lookup"><span data-stu-id="dcc7d-171">**Migrating from Exchange?**</span></span> <span data-ttu-id="dcc7d-172">Informieren Sie sich über [Methoden zum Migrieren mehrerer E-Mail-Konten zu Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="dcc7d-172">[Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="dcc7d-173">Wenn Sie mehrere Postfächer mithilfe von Cutover, Staged oder einer Exchange-Hybridmethode zu Microsoft 365 migrieren, werden Sie Benutzer automatisch als Teil der Migration hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-173">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you will add users automatically as part of the migration.</span></span> <span data-ttu-id="dcc7d-174">Bei der Migration werden nur die Benutzerkonten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-174">The migration only adds the user accounts.</span></span> <span data-ttu-id="dcc7d-175">Sie müssen den Benutzern Lizenzen zuweisen, damit sie E-Mail und andere Office-Apps verwenden können.</span><span class="sxs-lookup"><span data-stu-id="dcc7d-175">You will need assign licenses to the users before they can use email and other Office apps.</span></span>

## <a name="related-articles"></a><span data-ttu-id="dcc7d-176">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="dcc7d-176">Related articles</span></span>

[<span data-ttu-id="dcc7d-177">Zuweisen von Lizenzen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="dcc7d-177">Assign licenses to users</span></span>](../manage/assign-licenses-to-users.md)

[<span data-ttu-id="dcc7d-178">Hinzufügen eines neuen Mitarbeiters zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dcc7d-178">Add a new employee to Microsoft 365</span></span>](add-new-employee.md)

[<span data-ttu-id="dcc7d-179">Löschen eines Benutzers aus Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="dcc7d-179">Delete a user from your organization</span></span>](delete-a-user.md)

[<span data-ttu-id="dcc7d-180">Wiederherstellen eines Benutzers in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dcc7d-180">Restore a user in Microsoft 365</span></span>](restore-user.md)

[<span data-ttu-id="dcc7d-181">Gleichzeitiges Hinzufügen mehrerer Benutzer zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dcc7d-181">Add several users at the same time to Microsoft 365</span></span>](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)


---
title: Hinzufügen von einzelnen Benutzern oder Massenhinzufügen von Benutzern zu Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1970f7d6-03b5-442f-b385-5880b9c256ec
description: Hier erfahren Sie, wie Sie Benutzer zu Office 365 hinzufügen können. Fügen Sie die Benutzer einzeln oder mehrere Benutzer gleichzeitig unter Verwendung einer CSV-Datei hinzu.
ms.openlocfilehash: 708bce2cb5a2c1b6a621bffc3ce56a2744bb518d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241688"
---
# <a name="add-users-individually-or-in-bulk-to-office-365"></a><span data-ttu-id="f4be1-103">Hinzufügen von einzelnen Benutzern oder Massenhinzufügen von Benutzern zu Office 365</span><span class="sxs-lookup"><span data-stu-id="f4be1-103">Add users individually or in bulk to Office 365</span></span>

<span data-ttu-id="f4be1-104">Jede Person in Ihrem Team benötigt ein Benutzerkonto, um sich bei [Office 365 for Business](https://go.microsoft.com/fwlink/?LinkID=519395) anmelden und darauf zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="f4be1-104">The people on your team each need a user account before they can sign in and access [Office 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="f4be1-105">Die einfachste Methode zum Hinzufügen von Benutzerkonten besteht darin, sie im Microsoft 365 Admin Center nacheinander hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f4be1-105">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f4be1-106">Nachdem Sie diesen Schritt durchgeführt haben, werden die Benutzer über Office 365-Lizenzen, Anmeldeinformationen und Office 365-Postfächer verfügen.</span><span class="sxs-lookup"><span data-stu-id="f4be1-106">After you do this step, your users will have Office 365 licenses, sign in credentials, and Office 365 mailboxes.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="f4be1-107">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="f4be1-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="f4be1-108">Wechseln Sie zum Admin Center auf <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="f4be1-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="f4be1-109">Wählen Sie **Benutzer** > **Aktive Benutzer** und **Benutzer hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f4be1-109">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
3. <span data-ttu-id="f4be1-110">Geben Sie im Bereich **Grundlagen einrichten** die nachstehenden Informationen ein, und wählen Sie dann**Weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="f4be1-110">In the **Set up the basics** pane, fill in the following information, and then select **Next**.</span></span> 
  
- <span data-ttu-id="f4be1-111">**Name** Geben Sie Vornamen, Nachnamen, Anzeigenamen und Benutzernamen ein.</span><span class="sxs-lookup"><span data-stu-id="f4be1-111">**Name** Fill in first, last, display name, and username.</span></span> 
    
- <span data-ttu-id="f4be1-112">**Domäne** Wenn beispielsweise der Benutzername des Benutzers "Jan" ist und seine Domäne "contoso.com" heißt, meldet er sich bei Office 365 durch Eingabe von "jan@contoso.com" an.</span><span class="sxs-lookup"><span data-stu-id="f4be1-112">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="f4be1-113">**Kennworteinstellungen** Wählen Sie das automatisch generierte Kennwort aus, oder erstellen Sie ein sicheres Kennwort für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f4be1-113">**Password settings** Choose to the use auto-generated password or create your own strong password for the user.</span></span> 
    
    - <span data-ttu-id="f4be1-114">Dieser muss sein Kennwort nach 90 Tagen ändern. </span><span class="sxs-lookup"><span data-stu-id="f4be1-114">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="f4be1-115">Sie können aber auch die folgende Option auswählen: **Anfordern, dass dieser Benutzer bei der ersten Anmeldung sein Kennwort ändert**.</span><span class="sxs-lookup"><span data-stu-id="f4be1-115">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    
    - <span data-ttu-id="f4be1-116">Wählen Sie aus, ob das Kennwort per E-Mail gesendet werden soll, nachdem der Benutzer hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="f4be1-116">Choose whether you want to  send the password in email when the user has been added.</span></span> 
    
4. <span data-ttu-id="f4be1-117">Wählen Sie im Bereich **Produktlizenzen zuweisen** den Speicherort und die entsprechende Lizenz für den Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="f4be1-117">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="f4be1-118">Wenn Sie keine Lizenzen zur Verfügung haben, können Sie trotzdem einen Benutzer hinzufügen und zusätzliche Lizenzen kaufen.</span><span class="sxs-lookup"><span data-stu-id="f4be1-118">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="f4be1-119">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f4be1-119">Select **Next**.</span></span>

5. <span data-ttu-id="f4be1-120">Erweitern Sie auf der Seite **Optionale Einstellungen** die Option **Rollen**, wenn Sie diesen Benutzer als Administrator festlegen möchten, und erweitern Sie **Profilinformationen**, wenn Sie weitere Informationen zum Benutzer hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="f4be1-120">In the **Optional settings** page, expand **Roles** if you want to make this user an admin, and expand **Profile info** if you want to add additional information about the user.</span></span> 

6. <span data-ttu-id="f4be1-121">Wählen Sie **Weiter**aus, überprüfen Sie die Einstellungen des neuen Benutzers, nehmen Sie eventuell Änderungen vor, und wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f4be1-121">Select **Next**, review your new user's settings, make any changes you like, and then select **Finish adding**.</span></span> 

::: moniker-end


::: moniker range="o365-germany"

1. <span data-ttu-id="f4be1-122">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="f4be1-122">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

2. <span data-ttu-id="f4be1-123">Wählen Sie **Benutzer** > **Aktive Benutzer** und **Benutzer hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f4be1-123">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="f4be1-124">Geben Sie im Bereich **Neuer Benutzer** die nachstehenden Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="f4be1-124">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="f4be1-125">Wenn Sie damit fertig sind, wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f4be1-125">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="f4be1-126">**Name** Geben Sie den Vornamen, Nachnamen, Anzeigenamen und Benutzernamen ein. </span><span class="sxs-lookup"><span data-stu-id="f4be1-126">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="f4be1-127">**Domäne** Wenn beispielsweise der Benutzername des Benutzers "Jan" ist und seine Domäne "contoso.com" heißt, meldet er sich bei Office 365 durch Eingabe von "jan@contoso.com" an.</span><span class="sxs-lookup"><span data-stu-id="f4be1-127">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="f4be1-128">**Kontaktinformationen** Erweitern Sie diesen Abschnitt, um eine Mobiltelefonnummer, Anschrift usw. einzugeben. </span><span class="sxs-lookup"><span data-stu-id="f4be1-128">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="f4be1-129">**Kennwort** Verwenden Sie das automatisch generierte Kennwort, oder erweitern Sie den Abschnitt, um ein sicheres Kennwort für den Benutzer festzulegen. </span><span class="sxs-lookup"><span data-stu-id="f4be1-129">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="f4be1-p105">Er muss sein Kennwort nach 90 Tagen ändern.  Sie können aber auch die folgende Option auswählen: **Der Benutzer muss sein Kennwort bei der ersten Anmeldung ändern**.</span><span class="sxs-lookup"><span data-stu-id="f4be1-p105">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="f4be1-132">**Rollen** Erweitern Sie diesen Abschnitt, wenn der betreffende Benutzer ein Administrator werden soll. </span><span class="sxs-lookup"><span data-stu-id="f4be1-132">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="f4be1-p106">**Produktlizenzen** Erweitern Sie diesen Abschnitt, und wählen Sie die entsprechende Lizenz aus.  Wenn Sie keine Lizenzen zur Verfügung haben, können Sie trotzdem einen Benutzer hinzufügen und zusätzliche Lizenzen kaufen.</span><span class="sxs-lookup"><span data-stu-id="f4be1-p106">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f4be1-135">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="f4be1-135">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

2. <span data-ttu-id="f4be1-136">Wählen Sie **Benutzer** > **Aktive Benutzer** und **Benutzer hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f4be1-136">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="f4be1-137">Geben Sie im Bereich **Neuer Benutzer** die nachstehenden Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="f4be1-137">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="f4be1-138">Wenn Sie damit fertig sind, wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f4be1-138">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="f4be1-139">**Name** Geben Sie den Vornamen, Nachnamen, Anzeigenamen und Benutzernamen ein. </span><span class="sxs-lookup"><span data-stu-id="f4be1-139">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="f4be1-140">**Domäne** Wenn beispielsweise der Benutzername des Benutzers "Jan" ist und seine Domäne "contoso.com" heißt, meldet er sich bei Office 365 durch Eingabe von "jan@contoso.com" an.</span><span class="sxs-lookup"><span data-stu-id="f4be1-140">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="f4be1-141">**Kontaktinformationen** Erweitern Sie diesen Abschnitt, um eine Mobiltelefonnummer, Anschrift usw. einzugeben. </span><span class="sxs-lookup"><span data-stu-id="f4be1-141">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="f4be1-142">**Kennwort** Verwenden Sie das automatisch generierte Kennwort, oder erweitern Sie den Abschnitt, um ein sicheres Kennwort für den Benutzer festzulegen. </span><span class="sxs-lookup"><span data-stu-id="f4be1-142">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="f4be1-p108">Er muss sein Kennwort nach 90 Tagen ändern.  Sie können aber auch die folgende Option auswählen: **Der Benutzer muss sein Kennwort bei der ersten Anmeldung ändern**.</span><span class="sxs-lookup"><span data-stu-id="f4be1-p108">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="f4be1-145">**Rollen** Erweitern Sie diesen Abschnitt, wenn der betreffende Benutzer ein Administrator werden soll. </span><span class="sxs-lookup"><span data-stu-id="f4be1-145">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="f4be1-p109">**Produktlizenzen** Erweitern Sie diesen Abschnitt, und wählen Sie die entsprechende Lizenz aus.  Wenn Sie keine Lizenzen zur Verfügung haben, können Sie trotzdem einen Benutzer hinzufügen und zusätzliche Lizenzen kaufen.</span><span class="sxs-lookup"><span data-stu-id="f4be1-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end 
  
<span data-ttu-id="f4be1-148">Nachdem Sie einen Benutzer hinzugefügt haben, erhalten Sie eine E-Mail-Benachrichtigung vom Microsoft Online Services-Team.</span><span class="sxs-lookup"><span data-stu-id="f4be1-148">After you add a user, you'll get an email notification from the Microsoft Online Services Team.</span></span> <span data-ttu-id="f4be1-149">Die E-Mail enthält die Office 365-Benutzer-ID und das Kennwort der Person, damit sie sich bei Office 365 anmelden kann.</span><span class="sxs-lookup"><span data-stu-id="f4be1-149">The email will contain the person's Office 365 user ID and password so they can sign in to Office 365.</span></span> <span data-ttu-id="f4be1-150">Sie müssen Ihren neuen Benutzer über seine Office 365-Anmeldeinformationen informieren.</span><span class="sxs-lookup"><span data-stu-id="f4be1-150">You need to tell your new user about their Office 365 sign in information.</span></span> <span data-ttu-id="f4be1-151">Verwenden Sie hierzu Ihre normale Vorgehensweise für die Übermittlung neuer Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="f4be1-151">Use your normal process for communicating new passwords.</span></span>

> [!NOTE]
><span data-ttu-id="f4be1-152">Wenn Sie Benutzer durch das Migrieren von E-Mail-Postfächern erstellen, müssen Sie Office 365-Benutzerkonten durch das Zuweisen von Lizenzen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f4be1-152">If you create users by migrating mail boxes, you will need to activate Office 365 user accounts by assigning licenses.</span></span> <span data-ttu-id="f4be1-153">Wenn Sie einem Benutzer keine Lizenz zuweisen, wird sein Postfach nach Ablauf einer 30-tägigen Kulanzzeit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f4be1-153">If you don't assign a license to a user, their mailbox will be disabled after a grace period of 30 days.</span></span> <span data-ttu-id="f4be1-154">Erfahren Sie, wie Sie [Benutzern Lizenzen zuweisen](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) unter Verwendung des Microsoft 365 Admin Centers.</span><span class="sxs-lookup"><span data-stu-id="f4be1-154">See how to [assign licenses to users](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) using the Microsoft 365 admin center.</span></span>

### <a name="video-add-and-manage-users-in-the-admin-center"></a><span data-ttu-id="f4be1-155">Video: Benutzer im Admin Center hinzufügen und verwalten</span><span class="sxs-lookup"><span data-stu-id="f4be1-155">Video: Add and manage users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]
  
## <a name="next-steps"></a><span data-ttu-id="f4be1-156">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f4be1-156">Next steps</span></span>

<span data-ttu-id="f4be1-157">Geben Sie das [Schnellstarthandbuch für Mitarbeiter](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) für Ihre neuen Benutzer frei, um etwas einzurichten, z. B. [Office auf einem PC oder Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) und [mobile Office-Apps](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span><span class="sxs-lookup"><span data-stu-id="f4be1-157">Share the [Employee quick start guide](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) with your new users to set things up, like [Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) and [Office mobile apps](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span></span>
  
## <a name="need-help"></a><span data-ttu-id="f4be1-158">Benötigen Sie Hilfe?</span><span class="sxs-lookup"><span data-stu-id="f4be1-158">Need help?</span></span>

<span data-ttu-id="f4be1-159">[Wenden Sie sich an den Support für Office 365 Business](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="f4be1-159">[Contact Office 365 for business support](../contact-support-for-business-products.md).</span></span>  

## <a name="have-hundreds-or-thousands-of-users-to-add"></a><span data-ttu-id="f4be1-160">Müssen Sie Hunderte oder Tausende von Benutzern hinzufügen?</span><span class="sxs-lookup"><span data-stu-id="f4be1-160">Have hundreds or thousands of users to add?</span></span>


<span data-ttu-id="f4be1-161">Wenn Sie mehrere Benutzer gleichzeitig hinzufügen möchten, führen Sie die folgenden Schritte aus: </span><span class="sxs-lookup"><span data-stu-id="f4be1-161">To add multiple users at the same time, follow these steps:</span></span>
  
- <span data-ttu-id="f4be1-162">**Mithilfe einer Kalkulationstabelle können Sie Benutzer in Massen hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="f4be1-162">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="f4be1-163">Weitere Informationen hierzu finden Sie unter [Gleichzeitiges Hinzufügen von mehreren Benutzern](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span><span class="sxs-lookup"><span data-stu-id="f4be1-163">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
    
- <span data-ttu-id="f4be1-164">**Automatisieren Sie das Hinzufügen von Konten und Zuweisen von Lizenzen.**</span><span class="sxs-lookup"><span data-stu-id="f4be1-164">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="f4be1-165">Informationen hierzu finden Sie unter [Erstellen von Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="f4be1-165">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="f4be1-166">Wählen Sie diese Methode aus, wenn Sie mit der Nutzung von Windows PowerShell-Cmdlets bereits vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="f4be1-166">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
    
- <span data-ttu-id="f4be1-167">**Sie verwenden Active Directory?**</span><span class="sxs-lookup"><span data-stu-id="f4be1-167">**Using ActiveDirectory?**</span></span> <span data-ttu-id="f4be1-168">[Richten Sie die Verzeichnissynchronisierung für Office 365 ein](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="f4be1-168">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="f4be1-169">Mithilfe des Azure AD Connect-Tools können Sie Active Directory-Benutzerkonten (und andere Active Directory-Objekte) in Office 365 replizieren.</span><span class="sxs-lookup"><span data-stu-id="f4be1-169">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Office 365.</span></span> <span data-ttu-id="f4be1-170">Bei der Synchronisierung werden nur die Benutzerkonten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f4be1-170">The sync only adds the user accounts.</span></span> <span data-ttu-id="f4be1-171">Sie müssen den synchronisierten Benutzern Lizenzen zuweisen, damit sie E-Mail und andere Office-Apps verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f4be1-171">You will need to assign licenses to the synced users before they can use email and other Office apps.</span></span>
    
- <span data-ttu-id="f4be1-172">**Sie migrieren aus Exchange?**</span><span class="sxs-lookup"><span data-stu-id="f4be1-172">**Migrating from Exchange?**</span></span> <span data-ttu-id="f4be1-173">Informieren Sie sich über [Methoden zum Migrieren mehrerer E-Mail-Konten zu Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="f4be1-173">[Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="f4be1-174">Wenn Sie mithilfe einer Übernahmemigration oder mit einer mehrstufigen bzw. hybriden Exchange-Methode mehrere Postfächer zu Office 365 migrieren, werden die Benutzer als Teil der Migration automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f4be1-174">When you migrate multiple mailboxes to Office 365 by using either cutover, staged, or a hybrid Exchange method, you will add users automatically as part of the migration.</span></span> <span data-ttu-id="f4be1-175">Bei der Migration werden nur die Benutzerkonten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f4be1-175">The migration only adds the user accounts.</span></span> <span data-ttu-id="f4be1-176">Sie müssen den Benutzern Lizenzen zuweisen, damit sie E-Mail und andere Office-Apps verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f4be1-176">You will need assign licenses to the users before they can use email and other Office apps.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f4be1-177">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="f4be1-177">Related articles</span></span>

[<span data-ttu-id="f4be1-178">Hinzufügen eines neuen Mitarbeiters zu Office 365</span><span class="sxs-lookup"><span data-stu-id="f4be1-178">Add a new employee to Office 365</span></span>](add-new-employee.md)

[<span data-ttu-id="f4be1-179">Löschen eines Benutzers aus Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="f4be1-179">Delete a user from your organization</span></span>](delete-a-user.md)

[<span data-ttu-id="f4be1-180">Wiederherstellen eines Benutzers in Office 365</span><span class="sxs-lookup"><span data-stu-id="f4be1-180">Restore a user in Office 365</span></span>](restore-user.md)

[<span data-ttu-id="f4be1-181">Gleichzeitiges Hinzufügen mehrerer Benutzer zu Office 365</span><span class="sxs-lookup"><span data-stu-id="f4be1-181">Add several users at the same time to Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)



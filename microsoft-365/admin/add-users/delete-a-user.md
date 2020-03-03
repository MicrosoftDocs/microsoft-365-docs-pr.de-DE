---
title: Löschen eines Benutzers aus Ihrer Organisation
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Erfahren Sie, wie Sie ein Benutzerkonto löschen. Entscheiden Sie, was mit den E-Mails und OneDrive-Inhalten des Benutzers geschehen soll, und ob Sie die Produktlizenz behalten oder die Zahlung für die Lizenz beenden wollen.
ms.openlocfilehash: 2c87f04675ec92e964acb6fc9aef7171b6d7d510
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353136"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="f7ca8-104">Löschen eines Benutzers aus Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="f7ca8-104">Delete a user from your organization</span></span>
  
||
|:-----|
|<span data-ttu-id="f7ca8-105">**Suchen Sie nach einer Möglichkeit, Ihr *eigenes* Office 365-Benutzerkonto, das Sie bei der Arbeit oder in der Schule/Uni verwenden, zu löschen? Bitten Sie den technischen Support Ihres Arbeitgebers oder Ihrer Bildungseinrichtung, diese Schritte für Sie ausführen.**</span><span class="sxs-lookup"><span data-stu-id="f7ca8-105">**Looking for how to delete your *own* Office 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>|
   
## <a name="what-you-need-to-know-about-deleting-users"></a><span data-ttu-id="f7ca8-106">Wissenswertes über das Löschen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="f7ca8-106">What you need to know about deleting users</span></span>

- <span data-ttu-id="f7ca8-107">Nur Personen, die über Berechtigungen eines [globalen Office 365-Administrators](about-admin-roles.md) oder über Benutzerverwaltungsberechtigungen für das Unternehmen oder die Schule/Uni verfügen, können Benutzerkonten löschen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-107">Only people who have [Office 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span> 
    
- <span data-ttu-id="f7ca8-108">Sie haben 30 Tage Zeit, das Konto [wiederherzustellen](restore-user.md), bevor die Daten des Benutzers endgültig gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-108">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span> 
    
- <span data-ttu-id="f7ca8-p102">Wenn Sie die OneDrive-Daten des Benutzers behalten möchten, verschieben Sie sie an einen anderen Speicherort. Dies können Sie sogar bis zu 30 Tage nach dem Löschen des Kontos tun. Weitere Informationen finden Sie unter [Zugreifen auf die und Sichern der Daten eines ehemaligen Mitarbeiters](get-access-to-and-back-up-a-former-user-s-data.md). Die SharePoint-Dateien brauchen Sie nicht zu verschieben. Sie haben weiterhin Zugriff darauf.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-p102">If you want to keep the user's OneDrive data, move it to a different location. You can even do this up to 30 days after deleting the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md). You don't need to move their SharePoint files; you'll still have access to them.</span></span>
    
- <span data-ttu-id="f7ca8-p103">Wenn Sie die E-Mails des Benutzers behalten möchten, müssen Sie diese an einen anderen Speicherort verschieben, **BEVOR** Sie das Konto löschen. Wenn Sie das Konto bereits gelöscht haben und dies weniger als 30 Tage her ist, können Sie das Konto wiederherstellen und dann die E-Mail-Daten verschieben. Anschließend löschen Sie das Konto. Weitere Informationen finden Sie unter [Zugreifen auf die und Sichern der Daten eines ehemaligen Mitarbeiters](get-access-to-and-back-up-a-former-user-s-data.md).</span><span class="sxs-lookup"><span data-stu-id="f7ca8-p103">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
    
- <span data-ttu-id="f7ca8-116">Wenn Sie über ein Enterprise-Abonnement verfügen, z. B. Office 365 Enterprise E3, können Sie die Postfachdaten eines gelöschten Office 365-Benutzerkonto beibehalten, indem Sie es in ein *inaktives Postfach* umwandeln.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-116">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted Office 365 user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="f7ca8-117">Weitere Informationen dazu finden Sie unter [Verwalten inaktiver Postfächer in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="f7ca8-117">To learn more, see [Manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span>


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="f7ca8-118">Globaler Administrator: Löschen eines Benutzers, Beenden der Zahlung für seine Lizenz und Auswählen, was mit seinen E-Mails und OneDrive-Inhalten geschehen soll.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-118">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="f7ca8-119">Wenn Sie ein globaler Administrator sind und einen Benutzer löschen, können Sie auch einem anderen Benutzer Zugriff auf die E-Mails des gelöschten Benutzers gewähren und auswählen, was mit einem OneDrive-Inhalt geschehen soll.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-119">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span> 

  
### <a name="things-to-consider"></a><span data-ttu-id="f7ca8-120">Zu berücksichtigende Faktoren...</span><span class="sxs-lookup"><span data-stu-id="f7ca8-120">Things to consider...</span></span>

<span data-ttu-id="f7ca8-121">Bevor Sie beginnen, sollten Sie sich überlegen, was mit den E-Mails und OneDrive-Inhalten des Benutzers geschehen soll, und ob die Lizenz beibehalten oder die Zahlung für die Lizenz beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-121">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f7ca8-122">Produktlizenzen</span><span class="sxs-lookup"><span data-stu-id="f7ca8-122">Product licenses</span></span>  <br/> |<span data-ttu-id="f7ca8-123">Sie können die Lizenz des Benutzers entfernen und aus ihren Abonnements löschen, damit keine weiteren Kosten dafür anfallen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-123">You can remove the license from the user and remove it from your subscriptions to stop paying for that license.</span></span> <span data-ttu-id="f7ca8-124">Wenn Sie diese Option auswählen, wird die Lizenz automatisch aus ihren Abonnements entfernt.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-124">If you select this option, the license will be removed automatically from your subscriptions.</span></span>  <br/><br/> <span data-ttu-id="f7ca8-125">**Sie können die Lizenz nicht entfernen**, wenn Sie sie über einen Partner oder eine Volumenlizenzierung erworben haben.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-125">**You can't remove the license** if you bought it through a Partner or volume licensing.</span></span> <span data-ttu-id="f7ca8-126">Wenn Sie für einen jährlichen Plan bezahlen oder sich in der Mitte eines Abrechnungszyklus befinden, können Sie die Lizenz nicht aus Ihrem Abonnement entfernen, bis ihre vertraglichen Verpflichtungen beendet sind.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-126">If you are paying for an annual plan or if you are in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.</span></span>  <br/> |
|<span data-ttu-id="f7ca8-127">OneDrive-Inhalt</span><span class="sxs-lookup"><span data-stu-id="f7ca8-127">OneDrive content</span></span>  <br/> |<span data-ttu-id="f7ca8-128">Wenn der Benutzer seine Dateien auf OneDrive gespeichert hat, können Sie einem anderen Benutzer Zugriff auf diese Dateien gewähren.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-128">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="f7ca8-129">Sie müssen die Dateien, die Sie behalten möchten, innerhalb des für OneDrive-Dateien festgelegten Aufbewahrungszeitraums, der verschieben.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-129">You'll need to move the files you want to keep within the retention period that is set for OneDrive files.</span></span> <span data-ttu-id="f7ca8-130">**Die Standardeinstellung für den Aufbewahrungszeitraum ist 30 Tage.**</span><span class="sxs-lookup"><span data-stu-id="f7ca8-130">**By default, the retention period is 30 days.**</span></span> <span data-ttu-id="f7ca8-131">Wenn Sie die Dateien nach dem Löschen des Benutzers nicht innerhalb des Aufbewahrungszeitraums verschieben, wird der OneDrive-Inhalt endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-131">If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted.</span></span> <span data-ttu-id="f7ca8-132">Wenn Sie den Aufbewahrungszeitraum für die OneDrive-Dateien gelöschter Konten erhöhen möchten, lesen Sie [Festlegen der OneDrive-Aufbewahrung für gelöschte Benutzer](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).</span><span class="sxs-lookup"><span data-stu-id="f7ca8-132">To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).</span></span>  <br/><br/> <span data-ttu-id="f7ca8-133">**Wichtig!**</span><span class="sxs-lookup"><span data-stu-id="f7ca8-133">**Important!**</span></span> <span data-ttu-id="f7ca8-134">Wenn der gelöschte Benutzer seinen privaten PC zum Herunterladen von Dateien aus SharePoint und OneDrive verwendet hat, haben Sie keine Möglichkeit, die auf diesem Computer gespeicherten Dateien zu bereinigen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-134">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="f7ca8-135">Er hat weiterhin Zugriff auf alle Dateien, die mit OneDrive synchronisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-135">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="f7ca8-136">E-Mail</span><span class="sxs-lookup"><span data-stu-id="f7ca8-136">Email</span></span>  <br/> | <span data-ttu-id="f7ca8-137">Wenn Sie einem anderen Benutzer den Zugriff auf die E-Mails des gelöschten Benutzers gewähren, wird das Postfach des gelöschten Benutzers in ein freigegebenes Postfach konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-137">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="f7ca8-138">Der neue Postfachbesitzer kann dann auf das Postfach zugreifen und es auf neue E-Mails überwachen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-138">The new mailbox owner can then access the mailbox and monitor for new email.</span></span> <span data-ttu-id="f7ca8-139">Sie haben zudem folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="f7ca8-139">You'll also have the following options:</span></span>  <br/>  <br/><span data-ttu-id="f7ca8-140">Ändern des Anzeigenamens – Es empfiehlt sich, den Anzeigenamen so zu ändern, dass das freigegebene Postfach in der Liste "Aktive Benutzer" leicht zu identifizieren ist.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-140">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the Active users list.</span></span>  <br/>  <span data-ttu-id="f7ca8-141">Aktivieren von automatischen Antworten – Wir haben bereits eine höfliche automatische Antwort für Sie geschrieben.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-141">Turn on automatic replies - We've already written a polite automatic reply for you.</span></span> <span data-ttu-id="f7ca8-142">Sie können unterschiedliche automatische Antworten an Personen innerhalb und außerhalb Ihrer Organisation senden.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-142">You can send a different automatic replies to people within your organization and people from outside your organization.</span></span>  <br/> <br/> <span data-ttu-id="f7ca8-143">Bereinigen von Aliasnamen – Aliasnamen sind zusätzliche E-Mail-Adressen für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-143">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="f7ca8-144">In einigen Organisationen werden sie nicht verwendet. Wenn Sie also keine Aliasnamen verwenden, müssen Sie nichts weiter tun.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-144">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="f7ca8-145">Wenn der Benutzer über Aliasnamen verfügt, empfiehlt es sich, diese zu entfernen, damit die entsprechenden E-Mail-Adressen wieder verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-145">If the user does have aliases, we recommend removing them so that you can re-use those email addresses.</span></span> <span data-ttu-id="f7ca8-146">Andernfalls können Sie diese E-Mail-Adressen erst wiederverwenden, wenn der Aufbewahrungszeitraum für die gelöschte Postfächer abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-146">Otherwise, you can’t re-use those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="f7ca8-147">Standardmäßig kann ein gelöschtes Postfach 30 Tage lang wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-147">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="f7ca8-148">Weitere Informationen finden Sie unter [Exchange Online-Benutzerpostfächer löschen oder wiederherstellen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span><span class="sxs-lookup"><span data-stu-id="f7ca8-148">For more information, see  [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="f7ca8-149">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="f7ca8-149">Active Directory</span></span>  <br/> |<span data-ttu-id="f7ca8-150">Wenn Ihr Unternehmen **Active Directory** verwendet und mit Azure AD synchronisiert, müssen Sie das Benutzerkonto aus Active Directory löschen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-150">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="f7ca8-151">Dies ist nicht über Office 365 möglich.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-151">You can't do it through Office 365.</span></span> <span data-ttu-id="f7ca8-152">Entsprechende Anweisungen finden Sie unter [Löschen eines Benutzerkontos](https://go.microsoft.com/fwlink/p/?linkid=841808).</span><span class="sxs-lookup"><span data-stu-id="f7ca8-152">For instructions, see [Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808).</span></span>  <br/> |
   
### <a name="get-started"></a><span data-ttu-id="f7ca8-153">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="f7ca8-153">Get started</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="f7ca8-154">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-154">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="f7ca8-155">Da Sie in der geführten Oberfläche durch die Schritte zum Löschen eines Benutzers geleitet werden, beginnen Sie folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="f7ca8-155">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f7ca8-156">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="f7ca8-157">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f7ca8-158">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="f7ca8-159">Wählen Sie den Benutzer aus, den Sie löschen möchten, und dann **Benutzer löschen**.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-159">Select the user you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="f7ca8-160">Benutzerverwaltungsadministrator – Löschen von Benutzern aus Office 365</span><span class="sxs-lookup"><span data-stu-id="f7ca8-160">User management admin: Delete one or more users from Office 365</span></span>


 <span data-ttu-id="f7ca8-p113">**WICHTIG** Löschen Sie das Konto eines Benutzers nicht, wenn Sie [das Konto in ein freigegebenes Postfach konvertiert](../email/convert-user-mailbox-to-shared-mailbox.md) oder eine E-Mail-Weiterleitung für das Konto eingerichtet haben. Für diese Funktionen wird das Konto benötigt. Wenn Sie es in ein freigegebenes Postfach konvertiert haben, können Sie [Beenden der Zahlung für die Lizenz](#stop-paying-for-the-license), damit Sie nicht dafür bezahlen. Wenn Sie eine E-Mail-Weiterleitung eingerichtet haben, können Sie die Lizenz nicht entfernen. Durch das Entfernen wird die E-Mail-Weiterleitung beendet und das Postfach deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-p113">**IMPORTANT**: Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account. Those functions need the account there. If you've converted it to a shared mailbox, you can [Stop paying for the license](#stop-paying-for-the-license) from it so you aren't paying for it. If you set up email forwarding, you cannot remove the license. Doing so will stop the email forwarding and inactivate the mailbox.</span></span> 
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="f7ca8-166">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="f7ca8-167">Wählen Sie die Namen der zu löschenden Benutzer aus und dann **Weitere Optionen** (**...**). Wählen Sie anschließend **Benutzer löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-167">Select the names of the users that you want to delete, select **More options** (**...**), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="f7ca8-168">Obwohl Sie das Konto des Benutzers gelöscht haben, **bezahlen Sie weiterhin für die Lizenz**.  </span><span class="sxs-lookup"><span data-stu-id="f7ca8-168">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="f7ca8-169">Im nächsten Verfahren wird erläutert, was Sie tun müssen, um nicht mehr für die Lizenz zu bezahlen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-169">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="f7ca8-170">Sie können die Lizenz auch einem anderen Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-170">Or, you can assign the license to another user.</span></span> <span data-ttu-id="f7ca8-171">Er wird nicht automatisch einer Person zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-171">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="f7ca8-172">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-172">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="f7ca8-173">Wählen Sie die Namen der Benutzer, die Sie löschen möchten, und dann im Bereich **Massenaktionen** die Option **Benutzer löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-173">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="f7ca8-174">Obwohl Sie das Konto des Benutzers gelöscht haben, **bezahlen Sie weiterhin für die Lizenz**.  </span><span class="sxs-lookup"><span data-stu-id="f7ca8-174">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="f7ca8-175">Im nächsten Verfahren wird erläutert, was Sie tun müssen, um nicht mehr für die Lizenz zu bezahlen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-175">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="f7ca8-176">Sie können die Lizenz auch einem anderen Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-176">Or, you can assign the license to another user.</span></span> <span data-ttu-id="f7ca8-177">Er wird nicht automatisch einer Person zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-177">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f7ca8-178">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-178">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="f7ca8-179">Wählen Sie die Namen der Benutzer, die Sie löschen möchten, und dann im Bereich **Massenaktionen** die Option **Benutzer löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-179">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="f7ca8-180">Obwohl Sie das Konto des Benutzers gelöscht haben, **bezahlen Sie weiterhin für die Lizenz**.  </span><span class="sxs-lookup"><span data-stu-id="f7ca8-180">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="f7ca8-181">Im nächsten Verfahren wird erläutert, was Sie tun müssen, um nicht mehr für die Lizenz zu bezahlen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-181">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="f7ca8-182">Sie können die Lizenz auch einem anderen Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-182">Or, you can assign the license to another user.</span></span> <span data-ttu-id="f7ca8-183">Er wird nicht automatisch einer Person zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-183">It won't be assigned to someone automatically.</span></span>

::: moniker-end

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="f7ca8-184">Beenden der Zahlung für die Lizenz</span><span class="sxs-lookup"><span data-stu-id="f7ca8-184">Stop paying for the license</span></span>

<span data-ttu-id="f7ca8-185">Das Verringern der Anzahl von Lizenzen ist ein separater Schritt, der nur vom globalen Administrator oder dem Abrechnungsadministrator ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-185">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span> 
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="f7ca8-186">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Produkte und Dienste</a>.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-186">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span> <span data-ttu-id="f7ca8-187">Wird diese Option nicht angezeigt, sind Sie kein globaler Administrator oder Abrechnungsadministrator und können diesen Schritt nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-187">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="f7ca8-188">Wenn Sie über mehrere Abonnements verfügen, wählen Sie das gewünschte Abonnement und dann **Lizenzen hinzufügen/entfernen** aus, um die Lizenz zu löschen und so die Zahlung für die Lizenz zu beenden, bis Sie einen neuen Mitarbeiter einstellen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-188">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="f7ca8-189">Wenn Sie später die Schritte zum Hinzufügen einer anderen Person zu Ihrem Unternehmen ausführen, werden Sie aufgefordert, gleichzeitig eine Lizenz mit nur einem Schritt zu erwerben!</span><span class="sxs-lookup"><span data-stu-id="f7ca8-189">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="f7ca8-190">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnements</a>.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-190">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="f7ca8-191">Wird diese Option nicht angezeigt, sind Sie kein globaler Administrator oder Abrechnungsadministrator und können diesen Schritt nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-191">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="f7ca8-192">Wenn Sie über mehrere Abonnements verfügen, wählen Sie das gewünschte Abonnement und dann **Lizenzen hinzufügen/entfernen** aus, um die Lizenz zu löschen und so die Zahlung für die Lizenz zu beenden, bis Sie einen neuen Mitarbeiter einstellen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-192">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="f7ca8-193">Wenn Sie später die Schritte zum Hinzufügen einer anderen Person zu Ihrem Unternehmen ausführen, werden Sie aufgefordert, gleichzeitig eine Lizenz mit nur einem Schritt zu erwerben!</span><span class="sxs-lookup"><span data-stu-id="f7ca8-193">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f7ca8-194">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnements</a>.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-194">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="f7ca8-195">Wird diese Option nicht angezeigt, sind Sie kein globaler Administrator oder Abrechnungsadministrator und können diesen Schritt nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-195">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="f7ca8-196">Wenn Sie über mehrere Abonnements verfügen, wählen Sie das gewünschte Abonnement und dann **Lizenzen hinzufügen/entfernen** aus, um die Lizenz zu löschen und so die Zahlung für die Lizenz zu beenden, bis Sie einen neuen Mitarbeiter einstellen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-196">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="f7ca8-197">Wenn Sie später die Schritte zum Hinzufügen einer anderen Person zu Ihrem Unternehmen ausführen, werden Sie aufgefordert, gleichzeitig eine Lizenz mit nur einem Schritt zu erwerben!</span><span class="sxs-lookup"><span data-stu-id="f7ca8-197">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="f7ca8-198">Gleichzeitiges Löschen von vielen Benutzern</span><span class="sxs-lookup"><span data-stu-id="f7ca8-198">Delete many users at the same time</span></span>

<span data-ttu-id="f7ca8-199">Informationen hierzu finden Sie in den Informationen zum PowerShell-Cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230).</span><span class="sxs-lookup"><span data-stu-id="f7ca8-199">See the [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="f7ca8-200">Beheben von Problemen mit dem Löschen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="f7ca8-200">Fix issues with deleting a user</span></span>

<span data-ttu-id="f7ca8-201">Nachfolgend sind die beim Löschen eines Benutzers am häufigsten auftretenden Probleme aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="f7ca8-201">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="f7ca8-202">**Sie erhalten eine Fehlermeldung mit den Zeilen "Benutzer kann nicht gelöscht werden. Versuchen Sie es später erneut."**</span><span class="sxs-lookup"><span data-stu-id="f7ca8-202">**You get an error message along the lines of "User cannot be deleted. Please try again later."**</span></span> <span data-ttu-id="f7ca8-203">Überprüfen Sie sorgfältig, ob für das Konto die E-Mail-Weiterleitung eingerichtet wurde, oder ob es in ein freigegebenes Postfach konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-203">Doublecheck whether the account has email forwarding set up on it, or it's been converted to a shared mailbox.</span></span> <span data-ttu-id="f7ca8-204">Beide Fällen verursachen diesen Fehler.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-204">Both of these will cause that error.</span></span> <span data-ttu-id="f7ca8-205">Wenn für das Konto die E-Mail-Weiterleitung eingerichtet wurde oder es in ein freigegebenes Postfach konvertiert wurde, löschen Sie es nicht.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-205">Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="f7ca8-206">**Sie verfügen nicht über die entsprechenden Berechtigungen zum Löschen eines Benutzer**s.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-206">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="f7ca8-207">Nur Personen, die [globale Office 365-Administratoren oder Benutzerverwaltungsadministrator](about-admin-roles.md) sind, können Benutzer löschen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-207">Only people who are [Office 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="f7ca8-208">Normalerweise ist dies der technische Support in Ihrer Schule oder in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-208">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="f7ca8-p122">**Sie haben den Benutzer gelöscht, aber dessen Name wird weiterhin in Ihrem globalen Adressbuch angezeigt**. Dies ist der Fall, wenn ein Unternehmen Active Directory verwendet. Sie müssen das Benutzerkonto aus Active Directory löschen. Entsprechende Anweisungen finden Sie im TechNet-Artikel [Löschen eines Benutzerkontos](https://go.microsoft.com/fwlink/p/?linkid=841808).</span><span class="sxs-lookup"><span data-stu-id="f7ca8-p122">**You delete the user but their name continues appear in your global address book**. This happens when a business is using Active Directory. You have to delete the users account from Active Directory. For instructions, see this TechNet article: [Delete a User Account.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span></span>

||
|:-----|
|<span data-ttu-id="f7ca8-213">**Möchten Sie Office 365 von Ihrem Computer löschen? Wechseln Sie zu [Kündigen Ihres Abonnements](../../commerce/subscriptions/cancel-your-subscription.md).**</span><span class="sxs-lookup"><span data-stu-id="f7ca8-213">**Do you want to delete Office 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="f7ca8-214">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="f7ca8-214">Related articles</span></span>

[<span data-ttu-id="f7ca8-215">Wiederherstellen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="f7ca8-215">Restore a user</span></span>](restore-user.md)
  
[<span data-ttu-id="f7ca8-216">Endgültiges Löschen eines Postfachs</span><span class="sxs-lookup"><span data-stu-id="f7ca8-216">Permanently delete a mailbox</span></span>](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[<span data-ttu-id="f7ca8-217">Entfernen eines ehemaligen Mitarbeiters aus Office 365</span><span class="sxs-lookup"><span data-stu-id="f7ca8-217">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="f7ca8-218">Hinzufügen eines neuen Mitarbeiters zu Office 365</span><span class="sxs-lookup"><span data-stu-id="f7ca8-218">Add a new employee to Office 365</span></span>](add-new-employee.md)

<span data-ttu-id="f7ca8-219">[Löschen eines Benutzerkontos](https://go.microsoft.com/fwlink/p/?linkid=841808): Folgen Sie diesen Anweisungen, wenn Ihr Unternehmen **Active Directory** verwendet und mit Azure AD synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-219">[Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="f7ca8-220">Dies ist nicht über Office 365 möglich.</span><span class="sxs-lookup"><span data-stu-id="f7ca8-220">You can't do it through Office 365.</span></span>

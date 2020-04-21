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
ms.openlocfilehash: 59d06a075b5badeda410b4b25d60fa135b9ce5f7
ms.sourcegitcommit: a955324e33097bbd2fc4ad7f2b8d1f3d87bc8580
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43608126"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="78222-104">Löschen eines Benutzers aus Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="78222-104">Delete a user from your organization</span></span>
  
||
|:-----|
|<span data-ttu-id="78222-105">**Suchen Sie nach einer Möglichkeit, Ihr *eigenes* Office 365-Benutzerkonto, das Sie bei der Arbeit oder in der Schule/Uni verwenden, zu löschen? Bitten Sie den technischen Support Ihres Arbeitgebers oder Ihrer Bildungseinrichtung, diese Schritte für Sie ausführen.**</span><span class="sxs-lookup"><span data-stu-id="78222-105">**Looking for how to delete your *own* Office 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>|
   
## <a name="what-you-need-to-know-about-deleting-users"></a><span data-ttu-id="78222-106">Wissenswertes über das Löschen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="78222-106">What you need to know about deleting users</span></span>

- <span data-ttu-id="78222-107">Nur Personen, die über Berechtigungen eines [globalen Office 365-Administrators](about-admin-roles.md) oder über Benutzerverwaltungsberechtigungen für das Unternehmen oder die Schule/Uni verfügen, können Benutzerkonten löschen.</span><span class="sxs-lookup"><span data-stu-id="78222-107">Only people who have [Office 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span> 
    
- <span data-ttu-id="78222-108">Sie haben 30 Tage Zeit, das Konto [wiederherzustellen](restore-user.md), bevor die Daten des Benutzers endgültig gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="78222-108">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span> 
    
- <span data-ttu-id="78222-p102">Wenn Sie die OneDrive-Daten des Benutzers behalten möchten, verschieben Sie sie an einen anderen Speicherort. Dies können Sie sogar bis zu 30 Tage nach dem Löschen des Kontos tun. Weitere Informationen finden Sie unter [Zugreifen auf die und Sichern der Daten eines ehemaligen Mitarbeiters](get-access-to-and-back-up-a-former-user-s-data.md). Die SharePoint-Dateien brauchen Sie nicht zu verschieben. Sie haben weiterhin Zugriff darauf.</span><span class="sxs-lookup"><span data-stu-id="78222-p102">If you want to keep the user's OneDrive data, move it to a different location. You can even do this up to 30 days after deleting the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md). You don't need to move their SharePoint files; you'll still have access to them.</span></span>
    
- <span data-ttu-id="78222-p103">Wenn Sie die E-Mails des Benutzers behalten möchten, müssen Sie diese an einen anderen Speicherort verschieben, **BEVOR** Sie das Konto löschen. Wenn Sie das Konto bereits gelöscht haben und dies weniger als 30 Tage her ist, können Sie das Konto wiederherstellen und dann die E-Mail-Daten verschieben. Anschließend löschen Sie das Konto. Weitere Informationen finden Sie unter [Zugreifen auf die und Sichern der Daten eines ehemaligen Mitarbeiters](get-access-to-and-back-up-a-former-user-s-data.md).</span><span class="sxs-lookup"><span data-stu-id="78222-p103">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
    
- <span data-ttu-id="78222-116">Wenn Sie über ein Enterprise-Abonnement verfügen, z. B. Office 365 Enterprise E3, können Sie die Postfachdaten eines gelöschten Office 365-Benutzerkonto beibehalten, indem Sie es in ein *inaktives Postfach* umwandeln.</span><span class="sxs-lookup"><span data-stu-id="78222-116">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted Office 365 user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="78222-117">Weitere Informationen dazu finden Sie unter [Verwalten inaktiver Postfächer in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="78222-117">To learn more, see [Manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span>


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="78222-118">Globaler Administrator: Löschen eines Benutzers, Beenden der Zahlung für seine Lizenz und Auswählen, was mit seinen E-Mails und OneDrive-Inhalten geschehen soll.</span><span class="sxs-lookup"><span data-stu-id="78222-118">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="78222-119">Wenn Sie ein globaler Administrator sind und einen Benutzer löschen, können Sie auch einem anderen Benutzer Zugriff auf die E-Mails des gelöschten Benutzers gewähren und auswählen, was mit einem OneDrive-Inhalt geschehen soll.</span><span class="sxs-lookup"><span data-stu-id="78222-119">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span> 

  
### <a name="things-to-consider"></a><span data-ttu-id="78222-120">Zu berücksichtigende Faktoren...</span><span class="sxs-lookup"><span data-stu-id="78222-120">Things to consider...</span></span>

<span data-ttu-id="78222-121">Bevor Sie beginnen, sollten Sie sich überlegen, was mit den E-Mails und OneDrive-Inhalten des Benutzers geschehen soll, und ob die Lizenz beibehalten oder die Zahlung für die Lizenz beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="78222-121">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="78222-122">Produktlizenzen</span><span class="sxs-lookup"><span data-stu-id="78222-122">Product licenses</span></span>  <br/> |<span data-ttu-id="78222-123">Sie können die Lizenz des Benutzers entfernen und aus ihren Abonnements löschen, damit keine weiteren Kosten dafür anfallen.</span><span class="sxs-lookup"><span data-stu-id="78222-123">You can remove the license from the user and remove it from your subscriptions to stop paying for that license.</span></span> <span data-ttu-id="78222-124">Wenn Sie diese Option auswählen, wird die Lizenz automatisch aus ihren Abonnements entfernt.</span><span class="sxs-lookup"><span data-stu-id="78222-124">If you select this option, the license will be removed automatically from your subscriptions.</span></span>  <br/><br/> <span data-ttu-id="78222-125">**Sie können die Lizenz nicht entfernen**, wenn Sie sie über einen Partner oder eine Volumenlizenzierung erworben haben.</span><span class="sxs-lookup"><span data-stu-id="78222-125">**You can't remove the license** if you bought it through a Partner or volume licensing.</span></span> <span data-ttu-id="78222-126">Wenn Sie für einen jährlichen Plan bezahlen oder sich in der Mitte eines Abrechnungszyklus befinden, können Sie die Lizenz nicht aus Ihrem Abonnement entfernen, bis ihre vertraglichen Verpflichtungen beendet sind.</span><span class="sxs-lookup"><span data-stu-id="78222-126">If you are paying for an annual plan or if you are in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.</span></span>  <br/> |
|<span data-ttu-id="78222-127">OneDrive-Inhalt</span><span class="sxs-lookup"><span data-stu-id="78222-127">OneDrive content</span></span>  <br/> |<span data-ttu-id="78222-128">Wenn der Benutzer seine Dateien auf OneDrive gespeichert hat, können Sie einem anderen Benutzer Zugriff auf diese Dateien gewähren.</span><span class="sxs-lookup"><span data-stu-id="78222-128">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="78222-129">Sie müssen die Dateien, die Sie behalten möchten, innerhalb des für OneDrive-Dateien festgelegten Aufbewahrungszeitraums, der verschieben.</span><span class="sxs-lookup"><span data-stu-id="78222-129">You'll need to move the files you want to keep within the retention period that is set for OneDrive files.</span></span> <span data-ttu-id="78222-130">**Die Standardeinstellung für den Aufbewahrungszeitraum ist 30 Tage.**</span><span class="sxs-lookup"><span data-stu-id="78222-130">**By default, the retention period is 30 days.**</span></span> <span data-ttu-id="78222-131">Wenn Sie die Dateien nach dem Löschen des Benutzers nicht innerhalb des Aufbewahrungszeitraums verschieben, wird der OneDrive-Inhalt endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="78222-131">If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted.</span></span> <span data-ttu-id="78222-132">Wenn Sie den Aufbewahrungszeitraum für die OneDrive-Dateien gelöschter Konten erhöhen möchten, lesen Sie [Festlegen der OneDrive-Aufbewahrung für gelöschte Benutzer](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).</span><span class="sxs-lookup"><span data-stu-id="78222-132">To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).</span></span>  <br/><br/> <span data-ttu-id="78222-133">**Wichtig!**</span><span class="sxs-lookup"><span data-stu-id="78222-133">**Important!**</span></span> <span data-ttu-id="78222-134">Wenn der gelöschte Benutzer seinen privaten PC zum Herunterladen von Dateien aus SharePoint und OneDrive verwendet hat, haben Sie keine Möglichkeit, die auf diesem Computer gespeicherten Dateien zu bereinigen.</span><span class="sxs-lookup"><span data-stu-id="78222-134">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="78222-135">Er hat weiterhin Zugriff auf alle Dateien, die mit OneDrive synchronisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="78222-135">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="78222-136">E-Mail</span><span class="sxs-lookup"><span data-stu-id="78222-136">Email</span></span>  <br/> | <span data-ttu-id="78222-137">Wenn Sie einem anderen Benutzer den Zugriff auf die E-Mails des gelöschten Benutzers gewähren, wird das Postfach des gelöschten Benutzers in ein freigegebenes Postfach konvertiert.</span><span class="sxs-lookup"><span data-stu-id="78222-137">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="78222-138">Der neue Postfachbesitzer kann dann auf das Postfach zugreifen und es auf neue E-Mails überwachen.</span><span class="sxs-lookup"><span data-stu-id="78222-138">The new mailbox owner can then access the mailbox and monitor for new email.</span></span> <span data-ttu-id="78222-139">Sie haben zudem folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="78222-139">You'll also have the following options:</span></span>  <br/>  <br/><span data-ttu-id="78222-140">Ändern des Anzeigenamens – Es empfiehlt sich, den Anzeigenamen so zu ändern, dass das freigegebene Postfach in der Liste "Aktive Benutzer" leicht zu identifizieren ist.</span><span class="sxs-lookup"><span data-stu-id="78222-140">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the Active users list.</span></span>  <br/>  <span data-ttu-id="78222-141">Aktivieren von automatischen Antworten – Wir haben bereits eine höfliche automatische Antwort für Sie geschrieben.</span><span class="sxs-lookup"><span data-stu-id="78222-141">Turn on automatic replies - We've already written a polite automatic reply for you.</span></span> <span data-ttu-id="78222-142">Sie können unterschiedliche automatische Antworten an Personen innerhalb und außerhalb Ihrer Organisation senden.</span><span class="sxs-lookup"><span data-stu-id="78222-142">You can send a different automatic replies to people within your organization and people from outside your organization.</span></span>  <br/> <br/> <span data-ttu-id="78222-143">Bereinigen von Aliasnamen – Aliasnamen sind zusätzliche E-Mail-Adressen für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="78222-143">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="78222-144">In einigen Organisationen werden sie nicht verwendet. Wenn Sie also keine Aliasnamen verwenden, müssen Sie nichts weiter tun.</span><span class="sxs-lookup"><span data-stu-id="78222-144">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="78222-145">Wenn der Benutzer über Aliasnamen verfügt, empfiehlt es sich, diese zu entfernen, damit die entsprechenden E-Mail-Adressen wieder verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="78222-145">If the user does have aliases, we recommend removing them so that you can re-use those email addresses.</span></span> <span data-ttu-id="78222-146">Andernfalls können Sie diese E-Mail-Adressen erst wiederverwenden, wenn der Aufbewahrungszeitraum für die gelöschte Postfächer abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="78222-146">Otherwise, you can’t re-use those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="78222-147">Standardmäßig kann ein gelöschtes Postfach 30 Tage lang wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="78222-147">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="78222-148">Weitere Informationen finden Sie unter [Exchange Online-Benutzerpostfächer löschen oder wiederherstellen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span><span class="sxs-lookup"><span data-stu-id="78222-148">For more information, see  [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="78222-149">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="78222-149">Active Directory</span></span>  <br/> |<span data-ttu-id="78222-150">Wenn Ihr Unternehmen **Active Directory** verwendet und mit Azure AD synchronisiert, müssen Sie das Benutzerkonto aus Active Directory löschen.</span><span class="sxs-lookup"><span data-stu-id="78222-150">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="78222-151">Dies ist nicht über Office 365 möglich.</span><span class="sxs-lookup"><span data-stu-id="78222-151">You can't do it through Office 365.</span></span> <span data-ttu-id="78222-152">Entsprechende Anweisungen finden Sie unter [Löschen eines Benutzerkontos](https://go.microsoft.com/fwlink/p/?linkid=841808).</span><span class="sxs-lookup"><span data-stu-id="78222-152">For instructions, see [Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808).</span></span>  <br/> |
   
### <a name="get-started"></a><span data-ttu-id="78222-153">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="78222-153">Get started</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="78222-154">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="78222-154">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="78222-155">Da Sie in der geführten Oberfläche durch die Schritte zum Löschen eines Benutzers geleitet werden, beginnen Sie folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="78222-155">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="78222-156">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="78222-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="78222-157">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="78222-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="78222-158">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="78222-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="78222-159">Wählen Sie den Benutzer aus, den Sie löschen möchten, und dann **Benutzer löschen**.</span><span class="sxs-lookup"><span data-stu-id="78222-159">Select the user you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="78222-160">Benutzerverwaltungsadministrator – Löschen von Benutzern aus Office 365</span><span class="sxs-lookup"><span data-stu-id="78222-160">User management admin: Delete one or more users from Office 365</span></span>


> [!IMPORTANT]
> <span data-ttu-id="78222-p113">Löschen Sie das Konto eines Benutzers nicht, wenn Sie [es in ein freigegebenes Postfach konvertiert](../email/convert-user-mailbox-to-shared-mailbox.md) haben oder wenn Sie die e-Mail-Weiterleitung für das Konto eingerichtet haben. Diese Funktionen benötigen weiterhin das Konto. Für ein freigegebenes Postfach ist keine Lizenz erforderlich. Wenn Sie das Konto in ein freigegebenes Postfach konvertiert haben, können Sie [die Zahlung für die Lizenz beenden](#stop-paying-for-the-license). Wenn Sie die e-Mail-Weiterleitung für das Konto eingerichtet haben, können Sie die Lizenz nicht entfernen. Dadurch wird die e-Mail-Weiterleitung beendet und das Postfach deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="78222-p113">Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account. Those functions still need the account. A shared mailbox doesn't require a license. If you've converted the account to a shared mailbox you can [Stop paying for the license](#stop-paying-for-the-license). If you've set up email forwarding on the account, you can't remove the license. Doing so will stop email forwarding and deactivate the mailbox.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="78222-167">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="78222-167">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="78222-168">Wählen Sie die Namen der zu löschenden Benutzer aus und dann **Weitere Optionen** (**...**). Wählen Sie anschließend **Benutzer löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="78222-168">Select the names of the users that you want to delete, select **More options** (**...**), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="78222-169">Obwohl Sie das Konto des Benutzers gelöscht haben, **bezahlen Sie weiterhin für die Lizenz**.  </span><span class="sxs-lookup"><span data-stu-id="78222-169">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="78222-170">Im nächsten Verfahren wird erläutert, was Sie tun müssen, um nicht mehr für die Lizenz zu bezahlen.</span><span class="sxs-lookup"><span data-stu-id="78222-170">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="78222-171">Sie können die Lizenz auch einem anderen Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="78222-171">Or, you can assign the license to another user.</span></span> <span data-ttu-id="78222-172">Er wird nicht automatisch einer Person zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="78222-172">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="78222-173">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="78222-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="78222-174">Wählen Sie die Namen der Benutzer, die Sie löschen möchten, und dann im Bereich **Massenaktionen** die Option **Benutzer löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="78222-174">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="78222-175">Obwohl Sie das Konto des Benutzers gelöscht haben, **bezahlen Sie weiterhin für die Lizenz**.  </span><span class="sxs-lookup"><span data-stu-id="78222-175">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="78222-176">Im nächsten Verfahren wird erläutert, was Sie tun müssen, um nicht mehr für die Lizenz zu bezahlen.</span><span class="sxs-lookup"><span data-stu-id="78222-176">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="78222-177">Sie können die Lizenz auch einem anderen Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="78222-177">Or, you can assign the license to another user.</span></span> <span data-ttu-id="78222-178">Er wird nicht automatisch einer Person zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="78222-178">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="78222-179">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="78222-179">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="78222-180">Wählen Sie die Namen der Benutzer, die Sie löschen möchten, und dann im Bereich **Massenaktionen** die Option **Benutzer löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="78222-180">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="78222-181">Obwohl Sie das Konto des Benutzers gelöscht haben, **bezahlen Sie weiterhin für die Lizenz**.  </span><span class="sxs-lookup"><span data-stu-id="78222-181">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="78222-182">Im nächsten Verfahren wird erläutert, was Sie tun müssen, um nicht mehr für die Lizenz zu bezahlen.</span><span class="sxs-lookup"><span data-stu-id="78222-182">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="78222-183">Sie können die Lizenz auch einem anderen Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="78222-183">Or, you can assign the license to another user.</span></span> <span data-ttu-id="78222-184">Er wird nicht automatisch einer Person zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="78222-184">It won't be assigned to someone automatically.</span></span>

::: moniker-end

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="78222-185">Beenden der Zahlung für die Lizenz</span><span class="sxs-lookup"><span data-stu-id="78222-185">Stop paying for the license</span></span>

<span data-ttu-id="78222-186">Das Verringern der Anzahl von Lizenzen ist ein separater Schritt, der nur vom globalen Administrator oder dem Abrechnungsadministrator ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="78222-186">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span> 
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="78222-187">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Produkte und Dienste</a>.</span><span class="sxs-lookup"><span data-stu-id="78222-187">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span> <span data-ttu-id="78222-188">Wird diese Option nicht angezeigt, sind Sie kein globaler Administrator oder Abrechnungsadministrator und können diesen Schritt nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="78222-188">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="78222-189">Wenn Sie über mehrere Abonnements verfügen, wählen Sie das gewünschte Abonnement und dann **Lizenzen hinzufügen/entfernen** aus, um die Lizenz zu löschen und so die Zahlung für die Lizenz zu beenden, bis Sie einen neuen Mitarbeiter einstellen.</span><span class="sxs-lookup"><span data-stu-id="78222-189">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="78222-190">Wenn Sie später die Schritte zum Hinzufügen einer anderen Person zu Ihrem Unternehmen ausführen, werden Sie aufgefordert, gleichzeitig eine Lizenz mit nur einem Schritt zu erwerben!</span><span class="sxs-lookup"><span data-stu-id="78222-190">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="78222-191">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnements</a>.</span><span class="sxs-lookup"><span data-stu-id="78222-191">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="78222-192">Wird diese Option nicht angezeigt, sind Sie kein globaler Administrator oder Abrechnungsadministrator und können diesen Schritt nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="78222-192">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="78222-193">Wenn Sie über mehrere Abonnements verfügen, wählen Sie das gewünschte Abonnement und dann **Lizenzen hinzufügen/entfernen** aus, um die Lizenz zu löschen und so die Zahlung für die Lizenz zu beenden, bis Sie einen neuen Mitarbeiter einstellen.</span><span class="sxs-lookup"><span data-stu-id="78222-193">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="78222-194">Wenn Sie später die Schritte zum Hinzufügen einer anderen Person zu Ihrem Unternehmen ausführen, werden Sie aufgefordert, gleichzeitig eine Lizenz mit nur einem Schritt zu erwerben!</span><span class="sxs-lookup"><span data-stu-id="78222-194">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="78222-195">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnements</a>.</span><span class="sxs-lookup"><span data-stu-id="78222-195">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="78222-196">Wird diese Option nicht angezeigt, sind Sie kein globaler Administrator oder Abrechnungsadministrator und können diesen Schritt nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="78222-196">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="78222-197">Wenn Sie über mehrere Abonnements verfügen, wählen Sie das gewünschte Abonnement und dann **Lizenzen hinzufügen/entfernen** aus, um die Lizenz zu löschen und so die Zahlung für die Lizenz zu beenden, bis Sie einen neuen Mitarbeiter einstellen.</span><span class="sxs-lookup"><span data-stu-id="78222-197">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="78222-198">Wenn Sie später die Schritte zum Hinzufügen einer anderen Person zu Ihrem Unternehmen ausführen, werden Sie aufgefordert, gleichzeitig eine Lizenz mit nur einem Schritt zu erwerben!</span><span class="sxs-lookup"><span data-stu-id="78222-198">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="78222-199">Gleichzeitiges Löschen von vielen Benutzern</span><span class="sxs-lookup"><span data-stu-id="78222-199">Delete many users at the same time</span></span>

<span data-ttu-id="78222-200">Informationen hierzu finden Sie in den Informationen zum PowerShell-Cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230).</span><span class="sxs-lookup"><span data-stu-id="78222-200">See the [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="78222-201">Beheben von Problemen mit dem Löschen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="78222-201">Fix issues with deleting a user</span></span>

<span data-ttu-id="78222-202">Nachfolgend sind die beim Löschen eines Benutzers am häufigsten auftretenden Probleme aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="78222-202">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="78222-203">**Sie erhalten eine Fehlermeldung mit den Zeilen "Benutzer kann nicht gelöscht werden. Versuchen Sie es später erneut."**</span><span class="sxs-lookup"><span data-stu-id="78222-203">**You get an error message along the lines of "User cannot be deleted. Please try again later."**</span></span> <span data-ttu-id="78222-204">Überprüfen Sie sorgfältig, ob für das Konto die E-Mail-Weiterleitung eingerichtet wurde, oder ob es in ein freigegebenes Postfach konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="78222-204">Doublecheck whether the account has email forwarding set up on it, or it's been converted to a shared mailbox.</span></span> <span data-ttu-id="78222-205">Beide Fällen verursachen diesen Fehler.</span><span class="sxs-lookup"><span data-stu-id="78222-205">Both of these will cause that error.</span></span> <span data-ttu-id="78222-206">Wenn für das Konto die E-Mail-Weiterleitung eingerichtet wurde oder es in ein freigegebenes Postfach konvertiert wurde, löschen Sie es nicht.</span><span class="sxs-lookup"><span data-stu-id="78222-206">Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="78222-207">**Sie verfügen nicht über die entsprechenden Berechtigungen zum Löschen eines Benutzer**s.</span><span class="sxs-lookup"><span data-stu-id="78222-207">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="78222-208">Nur Personen, die [globale Office 365-Administratoren oder Benutzerverwaltungsadministrator](about-admin-roles.md) sind, können Benutzer löschen.</span><span class="sxs-lookup"><span data-stu-id="78222-208">Only people who are [Office 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="78222-209">Normalerweise ist dies der technische Support in Ihrer Schule oder in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="78222-209">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="78222-p122">**Sie haben den Benutzer gelöscht, aber dessen Name wird weiterhin in Ihrem globalen Adressbuch angezeigt**. Dies ist der Fall, wenn ein Unternehmen Active Directory verwendet. Sie müssen das Benutzerkonto aus Active Directory löschen. Entsprechende Anweisungen finden Sie im TechNet-Artikel [Löschen eines Benutzerkontos](https://go.microsoft.com/fwlink/p/?linkid=841808).</span><span class="sxs-lookup"><span data-stu-id="78222-p122">**You delete the user but their name continues appear in your global address book**. This happens when a business is using Active Directory. You have to delete the users account from Active Directory. For instructions, see this TechNet article: [Delete a User Account.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span></span>

||
|:-----|
|<span data-ttu-id="78222-214">**Möchten Sie Office 365 von Ihrem Computer löschen? Wechseln Sie zu [Kündigen Ihres Abonnements](../../commerce/subscriptions/cancel-your-subscription.md).**</span><span class="sxs-lookup"><span data-stu-id="78222-214">**Do you want to delete Office 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="78222-215">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="78222-215">Related articles</span></span>

[<span data-ttu-id="78222-216">Wiederherstellen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="78222-216">Restore a user</span></span>](restore-user.md)
  
[<span data-ttu-id="78222-217">Endgültiges Löschen eines Postfachs</span><span class="sxs-lookup"><span data-stu-id="78222-217">Permanently delete a mailbox</span></span>](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[<span data-ttu-id="78222-218">Entfernen eines ehemaligen Mitarbeiters aus Office 365</span><span class="sxs-lookup"><span data-stu-id="78222-218">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="78222-219">Hinzufügen eines neuen Mitarbeiters zu Office 365</span><span class="sxs-lookup"><span data-stu-id="78222-219">Add a new employee to Office 365</span></span>](add-new-employee.md)

<span data-ttu-id="78222-220">[Löschen eines Benutzerkontos](https://go.microsoft.com/fwlink/p/?linkid=841808): Folgen Sie diesen Anweisungen, wenn Ihr Unternehmen **Active Directory** verwendet und mit Azure AD synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="78222-220">[Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="78222-221">Dies ist nicht über Office 365 möglich.</span><span class="sxs-lookup"><span data-stu-id="78222-221">You can't do it through Office 365.</span></span>

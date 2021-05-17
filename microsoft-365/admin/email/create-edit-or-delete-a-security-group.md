---
title: Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Erfahren Sie, wie Sie eine Sicherheitsgruppe erstellen, bearbeiten oder löschen.
ms.openlocfilehash: 03e391727f9a61b1fc8e819e92d5a119017c38e0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579338"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="868a4-103">Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="868a4-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="868a4-104">Auf der seite Microsoft 365 **Gruppen** können Sie Gruppen von Benutzerkonten erstellen, die Sie zum Zuweisen der gleichen Berechtigungen in SharePoint Online und CRM Online verwenden können.</span><span class="sxs-lookup"><span data-stu-id="868a4-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="868a4-105">Beispielsweise kann ein Administrator eine Sicherheitsgruppe erstellen, um einer bestimmten Gruppe von Personen Zugriff auf eine SharePoint erteilen.</span><span class="sxs-lookup"><span data-stu-id="868a4-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="868a4-106">Nur globale Administratoren und Benutzerverwaltungsadministratoren verfügen über Berechtigungen zum Erstellen, Bearbeiten oder Löschen von Sicherheitsgruppen. Weitere Informationen zu Administratorrollen finden Sie unter [Zuweisen von Administratorrollen](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="868a4-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="868a4-107">Darüber hinaus gibt es [Gruppen in Exchange Online und SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), mit denen Sie an eine Benutzergruppe E-Mails senden oder der Gruppe Berechtigungen zuweisen können, und [Gruppen in Exchange Online und SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), mit denen Benutzern Rechte zugewiesen sowie der Zugriff auf Websites und Websitesammlungen gewährt werden kann.</span><span class="sxs-lookup"><span data-stu-id="868a4-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="868a4-108">Planen der Verwendung von Websitepostfächern?</span><span class="sxs-lookup"><span data-stu-id="868a4-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="868a4-109">Alle Benutzer, die über eine Sicherheitsgruppe zu einer SharePoint hinzugefügt werden, anstatt einzeln hinzugefügt zu werden, können nur das Websitepostfach aus SharePoint.</span><span class="sxs-lookup"><span data-stu-id="868a4-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="868a4-110">Diese Benutzer können nicht von der Website aus auf das Websitepostfach Outlook.</span><span class="sxs-lookup"><span data-stu-id="868a4-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="868a4-111">Weitere Informationen finden Sie unter [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span><span class="sxs-lookup"><span data-stu-id="868a4-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="868a4-112">Verwalten von Sicherheitsgruppen im Admin Center</span><span class="sxs-lookup"><span data-stu-id="868a4-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="868a4-113">Hinzufügen einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="868a4-113">Add a security group</span></span>

1. <span data-ttu-id="868a4-114">Wechseln Sie Microsoft 365 Admin Center zur Seite **Gruppen.**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="868a4-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="868a4-115">Wählen Sie **auf der** Seite Gruppen die Option Gruppe **hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="868a4-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="868a4-116">Wählen Sie **auf der Seite Gruppentyp auswählen** die Option Sicherheit **aus.**</span><span class="sxs-lookup"><span data-stu-id="868a4-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="868a4-117">Führen Sie die Schritte aus, um die Erstellung der Gruppe zu abschließen.</span><span class="sxs-lookup"><span data-stu-id="868a4-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="868a4-118">Hinzufügen von Mitgliedern zu einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="868a4-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="868a4-119">Wählen Sie auf der  Seite Gruppen den  Namen der Sicherheitsgruppe aus, und wählen Sie auf der Registerkarte Mitglieder die Option **Alle anzeigen und Mitglieder verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="868a4-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="868a4-120">Wählen Sie im  Gruppenbereich Mitglieder hinzufügen aus, und wählen Sie die Person aus  der Liste aus, oder geben Sie den Namen der Person ein, die Sie hinzufügen möchten, in das Feld Suche, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="868a4-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="868a4-121">Um Mitglieder zu entfernen, wählen Sie das X neben ihrem Namen aus.</span><span class="sxs-lookup"><span data-stu-id="868a4-121">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="868a4-122">Wählen Sie auf der  Seite Gruppen den Namen der Sicherheitsgruppe aus, und wählen Sie dann **Bearbeiten** neben **Mitglieder aus.**</span><span class="sxs-lookup"><span data-stu-id="868a4-122">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="868a4-123">Wählen Sie im  Gruppenbereich Mitglieder hinzufügen aus, und wählen Sie die Person aus  der Liste aus, oder geben Sie den Namen der Person ein, die Sie hinzufügen möchten, in das Feld Suche, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="868a4-123">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="868a4-124">Um Mitglieder zu entfernen, wählen Sie das X neben ihrem Namen aus.</span><span class="sxs-lookup"><span data-stu-id="868a4-124">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="868a4-125">Wählen Sie auf der  Seite Gruppen den Namen der Sicherheitsgruppe aus, und wählen Sie dann **Bearbeiten** neben **Mitglieder aus.**</span><span class="sxs-lookup"><span data-stu-id="868a4-125">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="868a4-126">Wählen Sie im  Gruppenbereich Mitglieder hinzufügen aus, und wählen Sie die Person aus  der Liste aus, oder geben Sie den Namen der Person ein, die Sie hinzufügen möchten, in das Feld Suche, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="868a4-126">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="868a4-127">Um Mitglieder zu entfernen, wählen Sie das X neben ihrem Namen aus.</span><span class="sxs-lookup"><span data-stu-id="868a4-127">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="868a4-128">Bearbeiten einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="868a4-128">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="868a4-129">Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.</span><span class="sxs-lookup"><span data-stu-id="868a4-129">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="868a4-130">Wählen Sie **auf** der Seite Gruppen den Namen der Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="868a4-130">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="868a4-131">Wählen Sie im Einstellungsbereich die Registerkarte **Allgemein** oder die Registerkarte **Mitglieder** aus, um Gruppendetails oder Mitglieder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="868a4-131">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="868a4-132">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="868a4-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="868a4-133">Wählen Sie **auf** der Seite Gruppen den Namen der Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="868a4-133">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="868a4-134">Wählen Sie im Bereich Sicherheitsgruppe die Option **Bearbeiten** neben der Registerkarte **Name** oder **Mitglieder** aus, um Gruppendetails oder Mitglieder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="868a4-134">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="868a4-135">Nachdem Sie Änderungen vorgenommen haben, wählen Sie **Speichern** \> **Schließen aus.**</span><span class="sxs-lookup"><span data-stu-id="868a4-135">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="868a4-136">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="868a4-136">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="868a4-137">Wählen Sie **auf** der Seite Gruppen den Namen der Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="868a4-137">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="868a4-138">Wählen Sie im Bereich Sicherheitsgruppe die Option **Bearbeiten** neben der Registerkarte **Name** oder **Mitglieder** aus, um Gruppendetails oder Mitglieder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="868a4-138">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="868a4-139">Nachdem Sie Änderungen vorgenommen haben, wählen Sie **Speichern** > **Schließen aus.**</span><span class="sxs-lookup"><span data-stu-id="868a4-139">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="868a4-140">Löschen einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="868a4-140">Delete a security group</span></span>

1. <span data-ttu-id="868a4-141">Wechseln Sie im Admin Center zur Seite **Gruppen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.</span><span class="sxs-lookup"><span data-stu-id="868a4-141">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="868a4-142">Wählen Sie **auf** der Seite Gruppen den Namen der Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="868a4-142">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="868a4-143">Wählen **Sie Gruppe löschen** (Wasetbinsymbol) aus, und bestätigen Sie dann, indem Sie Löschen **auswählen.**</span><span class="sxs-lookup"><span data-stu-id="868a4-143">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="868a4-144">Wählen **Sie Schließen** aus, nachdem die Gruppe gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="868a4-144">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="868a4-145">Gruppen in Exchange Online und SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="868a4-145">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="868a4-146">Wenn Sie Benutzergruppen erstellen möchten, damit Sie alle gleichzeitig E-Mails an sie senden können, können Sie dies im Exchange Admin Center tun, indem Sie zu **Admin** \> **Exchange** \> **Recipients** Groups \> **gehen.**</span><span class="sxs-lookup"><span data-stu-id="868a4-146">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="868a4-147">Wählen Sie als **Nächstes Neue** Hinzufügen aus, und wählen Sie die Art der Gruppe ![ ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) aus, die Sie erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="868a4-147">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="868a4-148">**Verteilergruppe**: Wird verwendet, um Nachrichten an eine Benutzergruppe zu senden.</span><span class="sxs-lookup"><span data-stu-id="868a4-148">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="868a4-149">Sie wird auch als *E-Mail-aktivierte Verteilergruppe* oder *Verteilerliste bezeichnet.*</span><span class="sxs-lookup"><span data-stu-id="868a4-149">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="868a4-150">Weitere Informationen finden Sie unter [Verwalten von Verteilergruppen](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="868a4-150">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="868a4-151">**Sicherheitsgruppe**: Kann verwendet werden, um Nachrichten an eine Benutzergruppe zu senden oder um Berechtigungen zum Zugriff auf Ressourcen zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="868a4-151">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="868a4-152">Diese Gruppe wird auch als *E-Mail-aktivierte Sicherheitsgruppe bezeichnet.*</span><span class="sxs-lookup"><span data-stu-id="868a4-152">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="868a4-153">Weitere Informationen finden Sie unter [Verwalten von E-Mail-aktivierten Sicherheitsgruppen](/Exchange/recipients/mail-enabled-security-groups).</span><span class="sxs-lookup"><span data-stu-id="868a4-153">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="868a4-154">**Dynamische Verteilergruppe**: Eine Art von Verteilergruppe, bei der die Empfängerliste jedes Mal, wenn Sie eine Nachricht senden, basierend auf von Ihnen definierten Filtern und Bedingungen neu berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="868a4-154">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="868a4-155">Weitere Informationen finden Sie unter [Verwalten dynamischer Verteilergruppen](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="868a4-155">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="868a4-156">Nachdem Sie Verteilergruppen und E-Mail-aktivierte Sicherheitsgruppen im Exchange Admin Center erstellt haben, werden ihre Namen und Benutzerlisten auf der Seite **Sicherheitsgruppen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="868a4-156">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="868a4-157">Sie können diese Gruppen an beiden Positionen löschen, können sie jedoch nur im Exchange Admin Center bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="868a4-157">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="868a4-158">Dynamische Verteilergruppen werden nicht auf der Seite **Sicherheitsgruppen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="868a4-158">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="868a4-159">SharePoint-Gruppen werden automatisch beim Erstellen einer Websitesammlung erstellt.</span><span class="sxs-lookup"><span data-stu-id="868a4-159">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="868a4-160">Den Standardgruppen werden mithilfe der SharePoint-Standardberechtigungsstufen (auch als SharePoint-Rollen bezeichnet) Rechte erteilt und wird Zugriff gewährt.</span><span class="sxs-lookup"><span data-stu-id="868a4-160">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="868a4-161">Weitere Informationen finden Sie unter [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span><span class="sxs-lookup"><span data-stu-id="868a4-161">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="868a4-162">Wie unterscheiden sich sicherheitsgruppen von Sicherheitsgruppen, die ich in SharePoint?</span><span class="sxs-lookup"><span data-stu-id="868a4-162">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="868a4-163">Sicherheitsgruppen können mit SharePoint, Exchange, MDM, Windows und mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="868a4-163">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="868a4-164">Eine Sicherheitsgruppe, die Sie in SharePoint erstellen, wird nur von der SharePoint-Websitesammlung erkannt.</span><span class="sxs-lookup"><span data-stu-id="868a4-164">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="868a4-165">Muss ich Sicherheitsgruppen verwenden, damit meine Organisation sicher ist?</span><span class="sxs-lookup"><span data-stu-id="868a4-165">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="868a4-p110">Nein. Dies ist nur eine weitere Möglichkeit zum Verwalten der Sicherheit für Ihre Organisation. Sie können immer individuell Benutzerberechtigungen erteilen und den Zugriff auf Websites zulassen. Mit Sicherheitsgruppen können Sie jedoch größere Benutzergruppen einfacher verwalten.</span><span class="sxs-lookup"><span data-stu-id="868a4-p110">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="868a4-170">Kann ich E-Mails an eine Sicherheitsgruppe senden?</span><span class="sxs-lookup"><span data-stu-id="868a4-170">Can I send email to a security group?</span></span>

<span data-ttu-id="868a4-171">Ja.</span><span class="sxs-lookup"><span data-stu-id="868a4-171">Yes.</span></span> <span data-ttu-id="868a4-172">Wenn Sie jedoch Gruppen für E-Mail und Zusammenarbeit verwenden möchten, empfehlen wir, stattdessen [eine Microsoft 365 erstellen.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="868a4-172">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 

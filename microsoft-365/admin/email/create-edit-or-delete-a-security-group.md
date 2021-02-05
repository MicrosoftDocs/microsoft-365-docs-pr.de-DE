---
title: Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Erfahren Sie, wie Sie eine Sicherheitsgruppe erstellen, bearbeiten oder löschen.
ms.openlocfilehash: df3d8fde0c487663237b3858aa0bf049ba4db045
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114045"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="d4493-103">Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="d4493-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d4493-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="d4493-104">The admin center is changing.</span></span> <span data-ttu-id="d4493-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="d4493-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="d4493-106">Auf der Seite "Microsoft 365-Gruppen" können Sie Gruppen von Benutzerkonten erstellen, die Sie zum Zuweisen derselben Berechtigungen in SharePoint Online und CRM Online verwenden können. </span><span class="sxs-lookup"><span data-stu-id="d4493-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="d4493-107">Beispielsweise kann ein Administrator eine Sicherheitsgruppe erstellen, um einer bestimmten Gruppe von Personen Zugriff auf eine SharePoint-Website zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="d4493-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="d4493-108">Nur globale Administratoren und Benutzerverwaltungsadministratoren verfügen über Berechtigungen zum Erstellen, Bearbeiten oder Löschen von Sicherheitsgruppen. Weitere Informationen zu Administratorrollen finden Sie unter [Zuweisen von Administratorrollen.](../add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="d4493-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="d4493-109">Darüber hinaus gibt es [Gruppen in Exchange Online und SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), mit denen Sie an eine Benutzergruppe E-Mails senden oder der Gruppe Berechtigungen zuweisen können, und [Gruppen in Exchange Online und SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), mit denen Benutzern Rechte zugewiesen sowie der Zugriff auf Websites und Websitesammlungen gewährt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d4493-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="d4493-110">Planen Sie die Verwendung von Websitepostfächern?</span><span class="sxs-lookup"><span data-stu-id="d4493-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="d4493-111">Alle Benutzer, die einer SharePoint-Website über eine Sicherheitsgruppe und nicht einzeln hinzugefügt werden, können nur das Websitepostfach aus SharePoint verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4493-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="d4493-112">Diese Benutzer können nicht von Outlook aus auf das Websitepostfach zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d4493-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="d4493-113">Weitere Informationen finden Sie unter [Verwenden von Microsoft 365-Gruppen anstelle von Websitepostfächern.](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)</span><span class="sxs-lookup"><span data-stu-id="d4493-113">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="d4493-114">Verwalten von Sicherheitsgruppen im Admin Center</span><span class="sxs-lookup"><span data-stu-id="d4493-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="d4493-115">Hinzufügen einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="d4493-115">Add a security group</span></span>

1. <span data-ttu-id="d4493-116">Wechseln Sie im Microsoft 365 Admin Center zur Seite  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">"Gruppengruppen".</a></span><span class="sxs-lookup"><span data-stu-id="d4493-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="d4493-117">Wählen Sie **auf der Seite "Gruppen"** die Option **"Gruppe hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="d4493-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="d4493-118">Wählen Sie **auf der Seite "Gruppentyp auswählen"** die **Option Sicherheit aus.**</span><span class="sxs-lookup"><span data-stu-id="d4493-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="d4493-119">Führen Sie die Schritte zum Abschließen der Erstellung der Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="d4493-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="d4493-120">Hinzufügen von Mitgliedern zu einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="d4493-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="d4493-121">Wählen Sie den Namen der Sicherheitsgruppe  auf der Seite **"Gruppen"** aus, und wählen Sie auf der Registerkarte "Mitglieder" die Option "Alle anzeigen" und **"Mitglieder verwalten" aus.**</span><span class="sxs-lookup"><span data-stu-id="d4493-121">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="d4493-122">Wählen Sie im  Gruppenbereich "Mitglieder hinzufügen" aus, und wählen Sie die Person  aus der Liste aus, oder geben Sie den Namen der Person, die Sie hinzufügen möchten, in das Suchfeld ein, und wählen Sie dann "Speichern" **aus.**</span><span class="sxs-lookup"><span data-stu-id="d4493-122">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="d4493-123">Um Mitglieder zu entfernen, wählen Sie das X neben ihrem Namen aus.</span><span class="sxs-lookup"><span data-stu-id="d4493-123">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d4493-124">Wählen Sie auf der  Seite "Gruppen" den Namen der Sicherheitsgruppe aus, und wählen Sie dann **"Neben** Mitgliedern **bearbeiten" aus.**</span><span class="sxs-lookup"><span data-stu-id="d4493-124">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="d4493-125">Wählen Sie im  Gruppenbereich "Mitglieder hinzufügen" aus, und wählen Sie die Person  aus der Liste aus, oder geben Sie den Namen der Person, die Sie hinzufügen möchten, in das Suchfeld ein, und wählen Sie dann "Speichern" **aus.**</span><span class="sxs-lookup"><span data-stu-id="d4493-125">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="d4493-126">Um Mitglieder zu entfernen, wählen Sie das X neben ihrem Namen aus.</span><span class="sxs-lookup"><span data-stu-id="d4493-126">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="d4493-127">Wählen Sie auf der  Seite "Gruppen" den Namen der Sicherheitsgruppe aus, und wählen Sie dann **"Neben** Mitgliedern **bearbeiten" aus.**</span><span class="sxs-lookup"><span data-stu-id="d4493-127">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="d4493-128">Wählen Sie im  Gruppenbereich "Mitglieder hinzufügen" aus, und wählen Sie die Person  aus der Liste aus, oder geben Sie den Namen der Person, die Sie hinzufügen möchten, in das Suchfeld ein, und wählen Sie dann "Speichern" **aus.**</span><span class="sxs-lookup"><span data-stu-id="d4493-128">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="d4493-129">Um Mitglieder zu entfernen, wählen Sie das X neben ihrem Namen aus.</span><span class="sxs-lookup"><span data-stu-id="d4493-129">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="d4493-130">Bearbeiten einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="d4493-130">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d4493-131">Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.</span><span class="sxs-lookup"><span data-stu-id="d4493-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="d4493-132">Wählen Sie **auf der** Seite "Gruppen" den Namen der Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="d4493-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="d4493-133">Wählen Sie im Einstellungsbereich die  Registerkarte **"Allgemein"** oder "Mitglieder" aus, um Gruppendetails oder Mitglieder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d4493-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d4493-134">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="d4493-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="d4493-135">Wählen Sie **auf der** Seite "Gruppen" den Namen der Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="d4493-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="d4493-136">Wählen Sie im Sicherheitsgruppenbereich "Bearbeiten"  neben der Registerkarte **"Name"** oder "Mitglieder" aus, um entweder Gruppendetails oder Mitglieder zu bearbeiten. </span><span class="sxs-lookup"><span data-stu-id="d4493-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="d4493-137">Nachdem Sie Änderungen vorgenommen haben, wählen Sie **"Speichern** \> **schließen" aus.**</span><span class="sxs-lookup"><span data-stu-id="d4493-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d4493-138">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="d4493-138">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="d4493-139">Wählen Sie **auf der** Seite "Gruppen" den Namen der Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="d4493-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="d4493-140">Wählen Sie im Sicherheitsgruppenbereich "Bearbeiten"  neben der Registerkarte **"Name"** oder "Mitglieder" aus, um entweder Gruppendetails oder Mitglieder zu bearbeiten. </span><span class="sxs-lookup"><span data-stu-id="d4493-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="d4493-141">Nachdem Sie Änderungen vorgenommen haben, wählen Sie **"Speichern** > **schließen" aus.**</span><span class="sxs-lookup"><span data-stu-id="d4493-141">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="d4493-142">Löschen einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="d4493-142">Delete a security group</span></span>

1. <span data-ttu-id="d4493-143">Wechseln Sie im Admin Center zur Seite **Gruppen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.</span><span class="sxs-lookup"><span data-stu-id="d4493-143">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="d4493-144">Wählen Sie **auf der** Seite "Gruppen" den Namen der Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="d4493-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="d4493-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span><span class="sxs-lookup"><span data-stu-id="d4493-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="d4493-146">Wählen **Sie "Schließen"** aus, nachdem die Gruppe gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="d4493-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="d4493-147">Gruppen in Exchange Online und SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d4493-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="d4493-148">Wenn Sie Benutzergruppen erstellen möchten, damit Sie alle gleichzeitig E-Mails an sie senden können,  können Sie dies im Exchange Admin Center tun, indem Sie zu \> **"Exchange-Empfängergruppen** verwalten" \>  \> **gehen.**</span><span class="sxs-lookup"><span data-stu-id="d4493-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="d4493-149">Wählen Sie als Nächstes **"Neu** hinzufügen" aus, und wählen Sie die Art der Gruppe aus, ![ ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) die Sie erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="d4493-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="d4493-150">**Verteilergruppe**: Wird verwendet, um Nachrichten an eine Benutzergruppe zu senden.</span><span class="sxs-lookup"><span data-stu-id="d4493-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="d4493-151">Sie wird auch als *E-Mail-aktivierte Verteilergruppe* oder *Verteilerliste bezeichnet.*</span><span class="sxs-lookup"><span data-stu-id="d4493-151">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="d4493-152">Weitere Informationen finden Sie unter [Verwalten von Verteilergruppen](https://technet.microsoft.com/library/bb124513.aspx).</span><span class="sxs-lookup"><span data-stu-id="d4493-152">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="d4493-153">**Sicherheitsgruppe**: Kann verwendet werden, um Nachrichten an eine Benutzergruppe zu senden oder um Berechtigungen zum Zugriff auf Ressourcen zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="d4493-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="d4493-154">Diese Gruppe wird auch als *E-Mail-aktivierte Sicherheitsgruppe bezeichnet.*</span><span class="sxs-lookup"><span data-stu-id="d4493-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="d4493-155">Weitere Informationen finden Sie unter [Verwalten von E-Mail-aktivierten Sicherheitsgruppen](https://technet.microsoft.com/library/bb123521.aspx).</span><span class="sxs-lookup"><span data-stu-id="d4493-155">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="d4493-156">**Dynamische Verteilergruppe**: Eine Art von Verteilergruppe, bei der die Empfängerliste jedes Mal, wenn Sie eine Nachricht senden, basierend auf von Ihnen definierten Filtern und Bedingungen neu berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="d4493-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="d4493-157">Weitere Informationen finden Sie unter [Verwalten dynamischer Verteilergruppen](https://technet.microsoft.com/library/bb123722.aspx).</span><span class="sxs-lookup"><span data-stu-id="d4493-157">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="d4493-158">Nachdem Sie Verteilergruppen und E-Mail-aktivierte Sicherheitsgruppen im Exchange Admin Center erstellt haben, werden deren Namen und Benutzerlisten auf der Seite **"Sicherheitsgruppen"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d4493-158">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="d4493-159">Sie können diese Gruppen an beiden Positionen löschen, können sie jedoch nur im Exchange Admin Center bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d4493-159">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="d4493-160">Dynamische Verteilergruppen werden nicht auf der Seite **"Sicherheitsgruppen"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d4493-160">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="d4493-161">SharePoint-Gruppen werden automatisch beim Erstellen einer Websitesammlung erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4493-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="d4493-162">Den Standardgruppen werden mithilfe der SharePoint-Standardberechtigungsstufen (auch als SharePoint-Rollen bezeichnet) Rechte erteilt und wird Zugriff gewährt.</span><span class="sxs-lookup"><span data-stu-id="d4493-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="d4493-163">Weitere Informationen finden Sie unter [Standard-SharePoint-Gruppen in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span><span class="sxs-lookup"><span data-stu-id="d4493-163">For more information, see [Default SharePoint groups in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="d4493-164">Wie unterscheiden sich Sicherheitsgruppen von Sicherheitsgruppen, die ich in SharePoint erstelle?</span><span class="sxs-lookup"><span data-stu-id="d4493-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="d4493-165">Sicherheitsgruppen können mit SharePoint, Exchange, MDM, Windows und mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d4493-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="d4493-166">Eine Sicherheitsgruppe, die Sie in SharePoint erstellen, wird nur von der SharePoint-Websitesammlung erkannt.</span><span class="sxs-lookup"><span data-stu-id="d4493-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="d4493-167">Muss ich Sicherheitsgruppen verwenden, damit meine Organisation sicher ist?</span><span class="sxs-lookup"><span data-stu-id="d4493-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="d4493-p111">Nein. Dies ist nur eine weitere Möglichkeit zum Verwalten der Sicherheit für Ihre Organisation. Sie können immer individuell Benutzerberechtigungen erteilen und den Zugriff auf Websites zulassen. Mit Sicherheitsgruppen können Sie jedoch größere Benutzergruppen einfacher verwalten.</span><span class="sxs-lookup"><span data-stu-id="d4493-p111">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="d4493-172">Kann ich E-Mails an eine Sicherheitsgruppe senden?</span><span class="sxs-lookup"><span data-stu-id="d4493-172">Can I send email to a security group?</span></span>

<span data-ttu-id="d4493-173">Ja.</span><span class="sxs-lookup"><span data-stu-id="d4493-173">Yes.</span></span> <span data-ttu-id="d4493-174">Wenn Sie jedoch Gruppen für E-Mail und Zusammenarbeit verwenden möchten, empfehlen wir, stattdessen eine [Microsoft 365-Gruppe zu](../create-groups/create-groups.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="d4493-174">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
  

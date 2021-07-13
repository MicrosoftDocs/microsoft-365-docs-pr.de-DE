---
title: Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe in der Microsoft 365 Admin Center
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Erfahren Sie, wie Sie eine Sicherheitsgruppe erstellen, bearbeiten oder löschen.
ms.openlocfilehash: 525acc45b293563f58bb9aa12c40bec1438cb055
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393955"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="f0bc1-103">Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe in der Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="f0bc1-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="f0bc1-104">Auf der Seite Microsoft 365 **Gruppen** können Sie Gruppen von Benutzerkonten erstellen, denen Sie in SharePoint Online und CRM Online die gleichen Berechtigungen zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="f0bc1-105">Beispielsweise kann ein Administrator eine Sicherheitsgruppe erstellen, um einer bestimmten Gruppe von Personen Zugriff auf eine SharePoint Website zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="f0bc1-106">Nur globale Und Benutzerverwaltungsadministratoren verfügen über Berechtigungen zum Erstellen, Bearbeiten oder Löschen von Sicherheitsgruppen. Weitere Informationen zu Administratorrollen finden Sie unter [Zuweisen von Administratorrollen.](../add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="f0bc1-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="f0bc1-107">Darüber hinaus gibt es [Gruppen in Exchange Online und SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), mit denen Sie an eine Benutzergruppe E-Mails senden oder der Gruppe Berechtigungen zuweisen können, und [Gruppen in Exchange Online und SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), mit denen Benutzern Rechte zugewiesen sowie der Zugriff auf Websites und Websitesammlungen gewährt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="f0bc1-108">Planen der Verwendung von Websitepostfächern?</span><span class="sxs-lookup"><span data-stu-id="f0bc1-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="f0bc1-109">Alle Benutzer, die einer SharePoint Website über eine Sicherheitsgruppe hinzugefügt werden, anstatt einzeln hinzugefügt zu werden, können nur das Websitepostfach aus SharePoint verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="f0bc1-110">Diese Benutzer können nicht über Outlook auf das Websitepostfach zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="f0bc1-111">Weitere Informationen finden Sie unter [Verwenden Microsoft 365 Gruppen anstelle von Websitepostfächern.](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)</span><span class="sxs-lookup"><span data-stu-id="f0bc1-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="f0bc1-112">Verwalten von Sicherheitsgruppen im Admin Center</span><span class="sxs-lookup"><span data-stu-id="f0bc1-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="f0bc1-113">Hinzufügen einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="f0bc1-113">Add a security group</span></span>

1. <span data-ttu-id="f0bc1-114">Wechseln Sie im Microsoft 365 Admin Center zur Seite **"Gruppengruppen".**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="f0bc1-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="f0bc1-115">Wählen Sie auf der Seite **"Gruppen"** die Option **"Gruppe hinzufügen"** aus.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="f0bc1-116">Wählen Sie auf der Seite **"Gruppentyp auswählen"** die Option **"Sicherheit"** aus.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="f0bc1-117">Führen Sie die Schritte aus, um die Erstellung der Gruppe abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="f0bc1-118">Hinzufügen von Mitgliedern zu einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="f0bc1-118">Add members to a security group</span></span>
    
1. <span data-ttu-id="f0bc1-119">Wählen Sie den Namen der Sicherheitsgruppe auf der Seite **"Gruppen"** und auf der Registerkarte **"Mitglieder"** die Option **"Alle anzeigen" und "Mitglieder verwalten"** aus.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="f0bc1-120">Wählen Sie im Gruppenbereich **"Mitglieder hinzufügen"** aus, wählen Sie die Person aus der Liste aus, oder geben Sie den Namen der Person ein, die Sie im **Suchfeld** hinzufügen möchten, und wählen Sie dann **"Speichern"** aus.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="f0bc1-121">Um Mitglieder zu entfernen, wählen Sie das X neben ihrem Namen aus.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-121">To remove members, select the X next to their name.</span></span> 
  
### <a name="edit-a-security-group"></a><span data-ttu-id="f0bc1-122">Bearbeiten einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="f0bc1-122">Edit a security group</span></span>

1. <span data-ttu-id="f0bc1-123">Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="f0bc1-124">Wählen Sie auf der Seite **"Gruppen"** den Namen der Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-124">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="f0bc1-125">Wählen Sie im Einstellungsbereich die Registerkarte **"Allgemein"** oder die Registerkarte **"Mitglieder"** aus, um Gruppendetails oder Mitglieder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-125">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

### <a name="delete-a-security-group"></a><span data-ttu-id="f0bc1-126">Löschen einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="f0bc1-126">Delete a security group</span></span>

1. <span data-ttu-id="f0bc1-127">Wechseln Sie im Admin Center zur Seite **Gruppen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-127">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="f0bc1-128">Wählen Sie auf der Seite **"Gruppen"** den Namen der Gruppe aus.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-128">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="f0bc1-129">Wählen Sie **"Gruppe löschen"** (Wasetbin-Symbol) aus, und bestätigen Sie dann, indem Sie **"Löschen"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-129">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="f0bc1-130">Wählen Sie **"Schließen"** aus, nachdem die Gruppe gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-130">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="f0bc1-131">Gruppen in Exchange Online und SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f0bc1-131">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="f0bc1-132">Wenn Sie Benutzergruppen erstellen möchten, damit Sie ihnen alle gleichzeitig E-Mails senden können, können Sie dies im Exchange Admin Center tun, indem Sie zu **Admin** \> **Exchange** \> **Recipients** \> **Groups** wechseln.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-132">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="f0bc1-133">Wählen Sie als Nächstes **"Neu** ![ hinzufügen" ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) aus, und wählen Sie die Art der Gruppe aus, die Sie erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="f0bc1-133">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="f0bc1-134">**Verteilergruppe**: Wird verwendet, um Nachrichten an eine Benutzergruppe zu senden.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-134">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="f0bc1-135">Es wird auch als  *E-Mail-aktivierte Verteilergruppe* oder  *Verteilerliste* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-135">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="f0bc1-136">Weitere Informationen finden Sie unter [Verwalten von Verteilergruppen](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="f0bc1-136">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="f0bc1-137">**Sicherheitsgruppe**: Kann verwendet werden, um Nachrichten an eine Benutzergruppe zu senden oder um Berechtigungen zum Zugriff auf Ressourcen zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-137">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="f0bc1-138">Diese Gruppe wird auch als *E-Mail-aktivierte Sicherheitsgruppe* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-138">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="f0bc1-139">Weitere Informationen finden Sie unter [Verwalten von E-Mail-aktivierten Sicherheitsgruppen](/Exchange/recipients/mail-enabled-security-groups).</span><span class="sxs-lookup"><span data-stu-id="f0bc1-139">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="f0bc1-140">**Dynamische Verteilergruppe**: Eine Art von Verteilergruppe, bei der die Empfängerliste jedes Mal, wenn Sie eine Nachricht senden, basierend auf von Ihnen definierten Filtern und Bedingungen neu berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-140">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="f0bc1-141">Weitere Informationen finden Sie unter [Verwalten dynamischer Verteilergruppen](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="f0bc1-141">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="f0bc1-142">Nachdem Sie Verteilergruppen und E-Mail-aktivierte Sicherheitsgruppen im Exchange Admin Center erstellt haben, werden deren Namen und Benutzerlisten auf der Seite **"Sicherheitsgruppen"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-142">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="f0bc1-143">Sie können diese Gruppen an beiden Positionen löschen, können sie jedoch nur im Exchange Admin Center bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-143">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="f0bc1-144">Dynamische Verteilergruppen werden nicht auf der Seite **"Sicherheitsgruppen"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-144">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="f0bc1-145">SharePoint-Gruppen werden automatisch beim Erstellen einer Websitesammlung erstellt.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-145">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="f0bc1-146">Den Standardgruppen werden mithilfe der SharePoint-Standardberechtigungsstufen (auch als SharePoint-Rollen bezeichnet) Rechte erteilt und wird Zugriff gewährt.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-146">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="f0bc1-147">Weitere Informationen finden Sie unter [Standard-SharePoint-Gruppen in SharePoint Online.](/sharepoint/default-sharepoint-groups)</span><span class="sxs-lookup"><span data-stu-id="f0bc1-147">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="f0bc1-148">Wie unterscheidet sich eine Sicherheitsgruppe von Sicherheitsgruppen, die ich in SharePoint erstelle?</span><span class="sxs-lookup"><span data-stu-id="f0bc1-148">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="f0bc1-149">Sicherheitsgruppen können mit SharePoint, Exchange, MDM, Windows und mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-149">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="f0bc1-150">Eine Sicherheitsgruppe, die Sie in SharePoint erstellen, wird nur von der SharePoint-Websitesammlung erkannt.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-150">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="f0bc1-151">Muss ich Sicherheitsgruppen verwenden, damit meine Organisation sicher ist?</span><span class="sxs-lookup"><span data-stu-id="f0bc1-151">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="f0bc1-p110">Nein. Dies ist nur eine weitere Möglichkeit zum Verwalten der Sicherheit für Ihre Organisation. Sie können immer individuell Benutzerberechtigungen erteilen und den Zugriff auf Websites zulassen. Mit Sicherheitsgruppen können Sie jedoch größere Benutzergruppen einfacher verwalten.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-p110">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="f0bc1-156">Kann ich E-Mails an eine Sicherheitsgruppe senden?</span><span class="sxs-lookup"><span data-stu-id="f0bc1-156">Can I send email to a security group?</span></span>

<span data-ttu-id="f0bc1-157">Ja.</span><span class="sxs-lookup"><span data-stu-id="f0bc1-157">Yes.</span></span> <span data-ttu-id="f0bc1-158">Wenn Sie jedoch Gruppen für E-Mails und Zusammenarbeit verwenden möchten, empfehlen wir, stattdessen [eine Microsoft 365 Gruppe zu erstellen.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="f0bc1-158">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 

## <a name="related-content"></a><span data-ttu-id="f0bc1-159">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="f0bc1-159">Related content</span></span>

<span data-ttu-id="f0bc1-160">[Erstellen einer Gruppe im Microsoft 365 Admin Center](../create-groups/create-groups.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="f0bc1-160">[Create a group in the Microsoft 365 admin center](../create-groups/create-groups.md) (article)</span></span>\
<span data-ttu-id="f0bc1-161">[Erläutern Microsoft 365 Gruppen für Ihre Benutzer](../create-groups/explain-groups-knowledge-worker.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="f0bc1-161">[Explaining Microsoft 365 Groups to your users](../create-groups/explain-groups-knowledge-worker.md) (article)</span></span>\
<span data-ttu-id="f0bc1-162">[Verwalten einer Gruppe im Microsoft 365 Admin Center](../create-groups/manage-groups.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="f0bc1-162">[Manage a group in the Microsoft 365 admin center](../create-groups/manage-groups.md) (article)</span></span>
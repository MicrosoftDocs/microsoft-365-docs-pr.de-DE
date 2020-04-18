---
title: Wiederherstellen einer gelöschten Office 365 Gruppe
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Hier erfahren Sie, wie Sie eine gelöschte Office 365 Gruppe wiederherstellen.
ms.openlocfilehash: 2efd8c35286d224c6a3ed185043c82ab4b8e954e
ms.sourcegitcommit: 0da80ba7b504841c502ab06fea659a985c06fe8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "43547532"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="c0f1d-103">Wiederherstellen einer gelöschten Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="c0f1d-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="c0f1d-104">Wenn Sie eine Gruppe gelöscht haben, wird Sie standardmäßig 30 Tage lang aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="c0f1d-105">Dieser 30-Tage-Zeitraum wird als Aufbewahrungsfrist für das vorläufige Löschen betrachtet, weil ein Wiederherstellen der Gruppe während dieses Zeitraums noch möglich ist.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="c0f1d-106">Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="c0f1d-107">Beim Wiederherstellen einer Gruppe werden folgende Inhalte wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="c0f1d-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="c0f1d-108">Objekte, Eigenschaften und Mitglieder von Office 365-Gruppen in Azure Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="c0f1d-108">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="c0f1d-109">E-Mail-Adressen von Gruppen.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="c0f1d-110">Der freigegebene Posteingang und Kalender in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="c0f1d-111">Die SharePoint Online-Teamwebsite und die entsprechenden Dateien.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="c0f1d-112">OneNote-Notizbuch</span><span class="sxs-lookup"><span data-stu-id="c0f1d-112">OneNote notebook</span></span>
    
- <span data-ttu-id="c0f1d-113">Planner</span><span class="sxs-lookup"><span data-stu-id="c0f1d-113">Planner</span></span>
    
- <span data-ttu-id="c0f1d-114">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0f1d-114">Teams</span></span>

- <span data-ttu-id="c0f1d-115">Yammer-Gruppe und Gruppeninhalt (wenn die Office 365-Gruppe aus Yammer erstellt wurde)</span><span class="sxs-lookup"><span data-stu-id="c0f1d-115">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook"></a><span data-ttu-id="c0f1d-116">Wiederherstellen einer eigenen Gruppe mithilfe von Outlook</span><span class="sxs-lookup"><span data-stu-id="c0f1d-116">Restore a group that you own by using Outlook</span></span>

<span data-ttu-id="c0f1d-117">Wenn Sie der Besitzer einer Office 365 Gruppe sind, können Sie die Gruppe selbst in Outlook wiederherstellen, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c0f1d-117">If you are the owner of an Office 365 group, you can restore the group yourself in Outlook by following these steps:</span></span>

1. <span data-ttu-id="c0f1d-118">Wählen Sie auf der Seite [Gelöschte Gruppen](https://outlook.office.com/people/group/deleted)die Option **Gruppen verwalten** unter dem Knoten **Gruppen** und dann **Gelöscht** aus.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-118">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="c0f1d-119">Klicken Sie auf die Schaltfläche **Wiederherstellen** neben der Gruppe, die Sie wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-119">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="c0f1d-120">Wenn die gelöschte Gruppe hier nicht angezeigt wird, wenden Sie sich an einen Administrator.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-120">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="c0f1d-121">Wiederherstellen einer Gruppe im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="c0f1d-121">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="c0f1d-122">Wenn Sie globaler Administrator oder Gruppenadministrator sind, können Sie eine gelöschte Gruppe im Microsoft 365 Admin Center wiederherstellen:</span><span class="sxs-lookup"><span data-stu-id="c0f1d-122">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="c0f1d-123">Wechseln Sie zum [Admin Center](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c0f1d-123">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="c0f1d-124">Erweitern Sie **Gruppen**, und klicken Sie dann auf **Gelöschte Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-124">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="c0f1d-125">Wählen Sie die Gruppe aus, die Sie wiederherstellen möchten, und klicken Sie dann auf **Gruppe wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-125">Select the group that you want to restore, and then click **Restore group**.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="c0f1d-126">Endgültiges Löschen einer Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="c0f1d-126">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="c0f1d-127">Manchmal möchten Sie vielleicht eine Gruppe endgültig löschen, ohne den Ablauf der 30-Tage-Frist für das vorläufige Löschen abzuwarten.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-127">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="c0f1d-128">Starten Sie hierzu PowerShell, und führen Sie den folgenden Befehl aus, um die Objekt-ID der Gruppe abzurufen:</span><span class="sxs-lookup"><span data-stu-id="c0f1d-128">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="c0f1d-129">Notieren Sie sich die Objekt-ID der Gruppe(n), die Sie endgültig löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-129">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c0f1d-130">Durch das endgültige Löschen der Gruppe werden die Gruppe und alle zugehörigen Daten für immer entfernt.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-130">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="c0f1d-131">Führen Sie in PowerShell den folgenden Befehl aus, um die Gruppe endgültig zu löschen:</span><span class="sxs-lookup"><span data-stu-id="c0f1d-131">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="c0f1d-p103">Führen Sie zur Bestätigung, dass die Gruppe erfolgreich endgültig gelöscht wurde, das Cmdlet  *Get-AzureADMSDeletedGroup*  erneut aus, um sicherzustellen, dass die Gruppe nicht mehr in der Liste vorläufig gelöschter Gruppen angezeigt wird. In einigen Fällen kann es bis zu 24 Stunden dauern, bis die Gruppe und alle zugehörigen Daten endgültig gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-p103">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="c0f1d-134">Haben Sie Fragen zu Office 365-Gruppen?</span><span class="sxs-lookup"><span data-stu-id="c0f1d-134">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="c0f1d-135">Besuchen Sie die [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups), um Fragen zu posten und an Unterhaltungen zu Office 365-Gruppen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c0f1d-135">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="c0f1d-136">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="c0f1d-136">Related articles</span></span>

[<span data-ttu-id="c0f1d-137">Verwalten von Office 365-Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0f1d-137">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="c0f1d-138">Löschen von Gruppen mit dem Cmdlet "Remove-UnifiedGroup"</span><span class="sxs-lookup"><span data-stu-id="c0f1d-138">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="c0f1d-139">Verwalten Ihrer gruppenabhängigen Teamwebsiteeinstellungen</span><span class="sxs-lookup"><span data-stu-id="c0f1d-139">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="c0f1d-140">Löschen einer Gruppe in Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c0f1d-140">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)

---
title: Wiederherstellen einer gelöschten Gruppe
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Informationen zum Wiederherstellen einer gelöschten Microsoft 365-Gruppe.
ms.openlocfilehash: d7cf548816af1661298458f27c704d654845075d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818507"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="3ca3e-103">Wiederherstellen einer gelöschten Gruppe</span><span class="sxs-lookup"><span data-stu-id="3ca3e-103">Restore a deleted Group</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3ca3e-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-104">The admin center is changing.</span></span> <span data-ttu-id="3ca3e-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="3ca3e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="3ca3e-106">Wenn Sie eine Gruppe gelöscht haben, wird Sie standardmäßig 30 Tage lang aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-106">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="3ca3e-107">Dieser 30-Tage-Zeitraum wird als Aufbewahrungsfrist für das vorläufige Löschen betrachtet, weil ein Wiederherstellen der Gruppe während dieses Zeitraums noch möglich ist.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-107">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="3ca3e-108">Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-108">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="3ca3e-109">Beim Wiederherstellen einer Gruppe werden folgende Inhalte wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="3ca3e-109">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="3ca3e-110">Azure Active Directory (AD) Microsoft 365 Groups-Objekt, Eigenschaften und Member.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-110">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="3ca3e-111">E-Mail-Adressen von Gruppen.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-111">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="3ca3e-112">Der freigegebene Posteingang und Kalender in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-112">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="3ca3e-113">Die SharePoint Online-Teamwebsite und die entsprechenden Dateien.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-113">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="3ca3e-114">OneNote-Notizbuch</span><span class="sxs-lookup"><span data-stu-id="3ca3e-114">OneNote notebook</span></span>
    
- <span data-ttu-id="3ca3e-115">Planner</span><span class="sxs-lookup"><span data-stu-id="3ca3e-115">Planner</span></span>
    
- <span data-ttu-id="3ca3e-116">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ca3e-116">Teams</span></span>

- <span data-ttu-id="3ca3e-117">Jammern von Gruppen-und Gruppeninhalten (wenn die Microsoft 365-Gruppe aus jammern erstellt wurde)</span><span class="sxs-lookup"><span data-stu-id="3ca3e-117">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a><span data-ttu-id="3ca3e-118">Wiederherstellen einer eigenen Gruppe mithilfe von Outlook im Internet</span><span class="sxs-lookup"><span data-stu-id="3ca3e-118">Restore a group that you own by using Outlook on the web</span></span>

<span data-ttu-id="3ca3e-119">Wenn Sie der Besitzer einer Microsoft 365-Gruppe sind, können Sie die Gruppe selbst in Outlook im Internet wiederherstellen, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="3ca3e-119">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="3ca3e-120">Wählen Sie auf der Seite [Gelöschte Gruppen](https://outlook.office.com/people/group/deleted)die Option **Gruppen verwalten** unter dem Knoten **Gruppen** und dann **Gelöscht** aus.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-120">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="3ca3e-121">Klicken Sie auf die Schaltfläche **Wiederherstellen** neben der Gruppe, die Sie wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-121">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="3ca3e-122">Wenn die gelöschte Gruppe hier nicht angezeigt wird, wenden Sie sich an einen Administrator.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-122">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="3ca3e-123">Wiederherstellen einer Gruppe im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="3ca3e-123">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="3ca3e-124">Wenn Sie globaler Administrator oder Gruppenadministrator sind, können Sie eine gelöschte Gruppe im Microsoft 365 Admin Center wiederherstellen:</span><span class="sxs-lookup"><span data-stu-id="3ca3e-124">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="3ca3e-125">Wechseln Sie zum [Admin Center](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3ca3e-125">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="3ca3e-126">Erweitern Sie **Gruppen**, und klicken Sie dann auf **Gelöschte Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-126">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="3ca3e-127">Wählen Sie die Gruppe aus, die Sie wiederherstellen möchten, und klicken Sie dann auf **Gruppe wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-127">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="3ca3e-128">In einigen Fällen kann es bis zu 24 Stunden dauern, bis die Gruppe und alle Daten wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-128">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="3ca3e-129">Dauerhaftes Löschen einer Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="3ca3e-129">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="3ca3e-130">Manchmal möchten Sie vielleicht eine Gruppe endgültig löschen, ohne den Ablauf der 30-Tage-Frist für das vorläufige Löschen abzuwarten.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-130">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="3ca3e-131">Starten Sie hierzu PowerShell, und führen Sie den folgenden Befehl aus, um die Objekt-ID der Gruppe abzurufen:</span><span class="sxs-lookup"><span data-stu-id="3ca3e-131">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="3ca3e-132">Notieren Sie sich die Objekt-ID der Gruppe(n), die Sie endgültig löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-132">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3ca3e-133">Durch das endgültige Löschen der Gruppe werden die Gruppe und alle zugehörigen Daten für immer entfernt.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-133">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="3ca3e-134">Führen Sie in PowerShell den folgenden Befehl aus, um die Gruppe endgültig zu löschen:</span><span class="sxs-lookup"><span data-stu-id="3ca3e-134">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="3ca3e-135">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-135">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups.</span></span> <span data-ttu-id="3ca3e-136">In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-136">In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="3ca3e-137">Haben Sie Fragen zu Microsoft 365-Gruppen?</span><span class="sxs-lookup"><span data-stu-id="3ca3e-137">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="3ca3e-138">Besuchen Sie die [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) , um Fragen zu veröffentlichen und an Unterhaltungen zu Microsoft 365-Gruppen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="3ca3e-138">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="3ca3e-139">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="3ca3e-139">Related articles</span></span>

[<span data-ttu-id="3ca3e-140">Verwalten von Microsoft 365-Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ca3e-140">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
[<span data-ttu-id="3ca3e-141">Löschen von Gruppen mit dem Cmdlet "Remove-UnifiedGroup"</span><span class="sxs-lookup"><span data-stu-id="3ca3e-141">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="3ca3e-142">Verwalten Ihrer gruppenabhängigen Teamwebsiteeinstellungen</span><span class="sxs-lookup"><span data-stu-id="3ca3e-142">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="3ca3e-143">Löschen einer Gruppe in Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3ca3e-143">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)

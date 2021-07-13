---
title: Wiederherstellen einer gelöschten Microsoft 365-Gruppe
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Eine gelöschte Gruppe wird 30 Tage lang aufbewahrt, und Sie können die Gruppe trotzdem wiederherstellen. Nach 30 Tagen werden die Gruppe und ihre Inhalte endgültig gelöscht.
ms.openlocfilehash: ddc3da57c05b7c5f54c10a0cc429c9a3f24b859c
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394051"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="1b424-104">Wiederherstellen einer gelöschten Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="1b424-104">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="1b424-105">Wenn Sie eine Gruppe gelöscht haben, wird Sie standardmäßig 30 Tage lang aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="1b424-105">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="1b424-106">Dieser 30-Tage-Zeitraum wird als Aufbewahrungsfrist für das vorläufige Löschen betrachtet, weil ein Wiederherstellen der Gruppe während dieses Zeitraums noch möglich ist.</span><span class="sxs-lookup"><span data-stu-id="1b424-106">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="1b424-107">Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1b424-107">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="1b424-108">Beim Wiederherstellen einer Gruppe werden folgende Inhalte wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="1b424-108">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="1b424-109">Objekte, Eigenschaften und Mitglieder von Microsoft 365-Gruppen in Azure Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="1b424-109">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="1b424-110">E-Mail-Adressen von Gruppen.</span><span class="sxs-lookup"><span data-stu-id="1b424-110">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="1b424-111">Der freigegebene Posteingang und Kalender in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1b424-111">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="1b424-112">Die SharePoint Online-Teamwebsite und die entsprechenden Dateien.</span><span class="sxs-lookup"><span data-stu-id="1b424-112">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="1b424-113">OneNote-Notizbuch</span><span class="sxs-lookup"><span data-stu-id="1b424-113">OneNote notebook</span></span>
    
- <span data-ttu-id="1b424-114">Planner</span><span class="sxs-lookup"><span data-stu-id="1b424-114">Planner</span></span>
    
- <span data-ttu-id="1b424-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1b424-115">Teams</span></span>

- <span data-ttu-id="1b424-116">Yammer-Gruppe und Gruppeninhalt (wenn die Microsoft 365-Gruppe aus Yammer erstellt wurde)</span><span class="sxs-lookup"><span data-stu-id="1b424-116">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="1b424-117">In diesem Artikel wird nur die Wiederherstellung von Microsoft 365-Gruppen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1b424-117">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="1b424-118">Alle anderen Gruppen können nach dem Löschen nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1b424-118">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="1b424-119">Wiederherstellen einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="1b424-119">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="1b424-120">Outlook</span><span class="sxs-lookup"><span data-stu-id="1b424-120">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="1b424-121">Wenn Sie der Besitzer einer Microsoft 365-Gruppe sind, können Sie die Gruppe selbst in Outlook im Web wiederherstellen, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="1b424-121">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="1b424-122">Wählen Sie auf der Seite [Gelöschte Gruppen](https://outlook.office.com/people/group/deleted)die Option **Gruppen verwalten** unter dem Knoten **Gruppen** und dann **Gelöscht** aus.</span><span class="sxs-lookup"><span data-stu-id="1b424-122">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="1b424-123">Klicken Sie auf die Schaltfläche **Wiederherstellen** neben der Gruppe, die Sie wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1b424-123">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="1b424-124">Wenn die gelöschte Gruppe hier nicht angezeigt wird, wenden Sie sich an einen Administrator.</span><span class="sxs-lookup"><span data-stu-id="1b424-124">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="1b424-125">Admin Center</span><span class="sxs-lookup"><span data-stu-id="1b424-125">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="1b424-126">Wenn Sie ein globaler Administrator oder ein Gruppenadministrator sind, können Sie eine gelöschte Gruppe im Microsoft 365 Admin Center wiederherstellen:</span><span class="sxs-lookup"><span data-stu-id="1b424-126">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="1b424-127">Wechseln Sie zum [Admin Center](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="1b424-127">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="1b424-128">Erweitern Sie **Gruppen**, und klicken Sie dann auf **Gelöschte Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="1b424-128">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="1b424-129">Wählen Sie die Gruppe aus, die Sie wiederherstellen möchten, und klicken Sie dann auf **Gruppe wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="1b424-129">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="1b424-130">In einigen Fällen kann es bis zu 24 Stunden dauern, bis die Gruppe und alle zugehörigen Daten wiederhergestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="1b424-130">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="1b424-131">Haben Sie Fragen zu Microsoft 365-Gruppen?</span><span class="sxs-lookup"><span data-stu-id="1b424-131">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="1b424-132">Besuchen Sie die [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups), um Fragen zu posten und an Unterhaltungen zu Microsoft 365-Gruppen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="1b424-132">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="1b424-133">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="1b424-133">Related content</span></span>

<span data-ttu-id="1b424-134">[Verwalten von Microsoft 365-Gruppen mit PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="1b424-134">[Manage Microsoft 365 Groups with PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (article)</span></span>\
<span data-ttu-id="1b424-135">[Löschen von Gruppen mithilfe des Cmdlets Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="1b424-135">[Delete groups using the Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup) (article)</span></span>\
<span data-ttu-id="1b424-136">[Verwalten der Einstellungen ihrer mit einer Gruppe verbundenen Teamwebsite](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="1b424-136">[Manage your group-connected team site settings](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (article)</span></span>\
<span data-ttu-id="1b424-137">[Löschen einer Gruppe in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="1b424-137">[Delete a group in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (article)</span></span>
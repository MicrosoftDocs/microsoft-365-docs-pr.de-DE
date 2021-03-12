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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Erfahren Sie, wie Sie eine gelöschte Microsoft 365-Gruppe wiederherstellen können.
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753243"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="d601c-103">Wiederherstellen einer gelöschten Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="d601c-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="d601c-104">Wenn Sie eine Gruppe gelöscht haben, wird Sie standardmäßig 30 Tage lang aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="d601c-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="d601c-105">Dieser 30-Tage-Zeitraum wird als Aufbewahrungsfrist für das vorläufige Löschen betrachtet, weil ein Wiederherstellen der Gruppe während dieses Zeitraums noch möglich ist.</span><span class="sxs-lookup"><span data-stu-id="d601c-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="d601c-106">Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d601c-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="d601c-107">Beim Wiederherstellen einer Gruppe werden folgende Inhalte wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="d601c-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="d601c-108">Objekte, Eigenschaften und Mitglieder von Microsoft 365-Gruppen in Azure Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="d601c-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="d601c-109">E-Mail-Adressen von Gruppen.</span><span class="sxs-lookup"><span data-stu-id="d601c-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="d601c-110">Der freigegebene Posteingang und Kalender in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d601c-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="d601c-111">Die SharePoint Online-Teamwebsite und die entsprechenden Dateien.</span><span class="sxs-lookup"><span data-stu-id="d601c-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="d601c-112">OneNote-Notizbuch</span><span class="sxs-lookup"><span data-stu-id="d601c-112">OneNote notebook</span></span>
    
- <span data-ttu-id="d601c-113">Planner</span><span class="sxs-lookup"><span data-stu-id="d601c-113">Planner</span></span>
    
- <span data-ttu-id="d601c-114">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d601c-114">Teams</span></span>

- <span data-ttu-id="d601c-115">Yammer-Gruppe und Gruppeninhalt (wenn die Microsoft 365-Gruppe aus Yammer erstellt wurde)</span><span class="sxs-lookup"><span data-stu-id="d601c-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="d601c-116">In diesem Artikel wird nur die Wiederherstellung von Microsoft 365-Gruppen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d601c-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="d601c-117">Alle anderen Gruppen können nach dem Löschen nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d601c-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="d601c-118">Wiederherstellen einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="d601c-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="d601c-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="d601c-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="d601c-120">Wenn Sie der Besitzer einer Microsoft 365-Gruppe sind, können Sie die Gruppe selbst in Outlook im Web wiederherstellen, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="d601c-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="d601c-121">Wählen Sie auf der Seite [Gelöschte Gruppen](https://outlook.office.com/people/group/deleted)die Option **Gruppen verwalten** unter dem Knoten **Gruppen** und dann **Gelöscht** aus.</span><span class="sxs-lookup"><span data-stu-id="d601c-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="d601c-122">Klicken Sie auf die Schaltfläche **Wiederherstellen** neben der Gruppe, die Sie wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d601c-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="d601c-123">Wenn die gelöschte Gruppe hier nicht angezeigt wird, wenden Sie sich an einen Administrator.</span><span class="sxs-lookup"><span data-stu-id="d601c-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="d601c-124">Admin Center</span><span class="sxs-lookup"><span data-stu-id="d601c-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="d601c-125">Wenn Sie ein globaler Administrator oder ein Gruppenadministrator sind, können Sie eine gelöschte Gruppe im Microsoft 365 Admin Center wiederherstellen:</span><span class="sxs-lookup"><span data-stu-id="d601c-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="d601c-126">Wechseln Sie zum [Admin Center](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d601c-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="d601c-127">Erweitern Sie **Gruppen**, und klicken Sie dann auf **Gelöschte Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="d601c-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="d601c-128">Wählen Sie die Gruppe aus, die Sie wiederherstellen möchten, und klicken Sie dann auf **Gruppe wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="d601c-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="d601c-129">In einigen Fällen kann es bis zu 24 Stunden dauern, bis die Gruppe und alle zugehörigen Daten wiederhergestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="d601c-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="d601c-130">Haben Sie Fragen zu Microsoft 365-Gruppen?</span><span class="sxs-lookup"><span data-stu-id="d601c-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="d601c-131">Besuchen Sie die [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups), um Fragen zu posten und an Unterhaltungen zu Microsoft 365-Gruppen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d601c-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="d601c-132">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="d601c-132">Related articles</span></span>

[<span data-ttu-id="d601c-133">Verwalten von Microsoft 365-Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="d601c-133">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="d601c-134">Löschen von Gruppen mit dem Cmdlet "Remove-UnifiedGroup"</span><span class="sxs-lookup"><span data-stu-id="d601c-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="d601c-135">Verwalten Ihrer gruppenabhängigen Teamwebsiteeinstellungen</span><span class="sxs-lookup"><span data-stu-id="d601c-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="d601c-136">Löschen einer Gruppe in Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d601c-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)

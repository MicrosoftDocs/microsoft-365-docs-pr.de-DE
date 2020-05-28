---
title: Lösen von Lizenzkonflikten
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Hier erfahren Sie, wie Sie Lizenz Konflikte mit Ihrem Microsoft 365 for Business-Abonnement beheben.
ms.openlocfilehash: 05efe9e75b051ece900ba9defe047f1244b713a9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399668"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="270d3-103">Lösen von Lizenzkonflikten</span><span class="sxs-lookup"><span data-stu-id="270d3-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="270d3-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="270d3-104">The admin center is changing.</span></span> <span data-ttu-id="270d3-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="270d3-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="270d3-106">Es wird empfohlen, dass Sie die Lizenzen erwerben, die Sie für Ihr Abonnement benötigen, bevor Sie neue Benutzer erstellen.</span><span class="sxs-lookup"><span data-stu-id="270d3-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="270d3-107">Auf diese Weise kann neuen Benutzern beim Erstellen der Benutzerkonten eine Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="270d3-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="270d3-108">Wenn Sie Benutzern bereits alle Lizenzen zugewiesen haben, einige der Lizenzen jedoch abgelaufen sind, oder wenn Sie versuchen, eine Lizenz zu entfernen, die bereits einem Benutzer zugewiesen ist, treten Lizenzkonflikte auf.</span><span class="sxs-lookup"><span data-stu-id="270d3-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="270d3-109">Weitere Informationen finden Sie unter [Entfernen von Lizenzen aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="270d3-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="270d3-110">Wie kann ich Lizenzkonflikte anzeigen?</span><span class="sxs-lookup"><span data-stu-id="270d3-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="270d3-111">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="270d3-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="270d3-112">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="270d3-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="270d3-113">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="270d3-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="270d3-114">Prüfen Sie die Spalte **Status** auf Informationen zum Konflikt.</span><span class="sxs-lookup"><span data-stu-id="270d3-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="270d3-115">Wenn ein Konflikt vorliegt, wird eine Warnmeldung angezeigt, die besagt, dass ein oder mehrere Benutzer eine gültige Lizenz benötigen.</span><span class="sxs-lookup"><span data-stu-id="270d3-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="270d3-116">Die Spalte **Status** wird nicht angezeigt, wenn keine Konflikte vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="270d3-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="270d3-117">Wie kann ich Lizenzkonflikte lösen?</span><span class="sxs-lookup"><span data-stu-id="270d3-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="270d3-118">Sie können Lizenz Konflikte lösen, indem Sie entweder [mehr Lizenzen kaufen](../../commerce/licenses/buy-licenses.md) oder [Lizenzen von Benutzern entfernen, die diese nicht mehr benötigen](remove-licenses-from-users.md).</span><span class="sxs-lookup"><span data-stu-id="270d3-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="270d3-119">Optional können Sie auch [ein Benutzerkonto löschen, um eine Lizenz freizugeben](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="270d3-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="270d3-120">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="270d3-120">Related articles</span></span> 

[<span data-ttu-id="270d3-121">Zuweisen von Lizenzen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="270d3-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="270d3-122">Entfernen von Benutzerlizenzen</span><span class="sxs-lookup"><span data-stu-id="270d3-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)

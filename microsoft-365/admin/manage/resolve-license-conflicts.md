---
title: Lösen von Lizenzkonflikten
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Erfahren Sie, wie Sie Lizenzkonflikte mit Ihrem Microsoft 365 Business-Abonnement beheben.
ms.openlocfilehash: e2b5daa71164b41825282bd5652549347b8307c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915182"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="d88a3-103">Lösen von Lizenzkonflikten</span><span class="sxs-lookup"><span data-stu-id="d88a3-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d88a3-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="d88a3-104">The admin center is changing.</span></span> <span data-ttu-id="d88a3-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="d88a3-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="d88a3-106">Es wird empfohlen, die Lizenzen zu erwerben, die Sie für Ihr Abonnement benötigen, bevor Sie neue Benutzer erstellen.</span><span class="sxs-lookup"><span data-stu-id="d88a3-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="d88a3-107">Auf diese Weise kann neuen Benutzern beim Erstellen der Benutzerkonten eine Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d88a3-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="d88a3-108">Wenn Sie Benutzern bereits alle Lizenzen zugewiesen haben, einige der Lizenzen jedoch abgelaufen sind, oder wenn Sie versuchen, eine Lizenz zu entfernen, die bereits einem Benutzer zugewiesen ist, treten Lizenzkonflikte auf.</span><span class="sxs-lookup"><span data-stu-id="d88a3-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="d88a3-109">Weitere Informationen finden Sie unter [Entfernen von Lizenzen aus Ihrem Abonnement](../../commerce/licenses/buy-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="d88a3-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="d88a3-110">Wie kann ich Lizenzkonflikte anzeigen?</span><span class="sxs-lookup"><span data-stu-id="d88a3-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d88a3-111">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="d88a3-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d88a3-112">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="d88a3-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d88a3-113">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="d88a3-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="d88a3-114">Prüfen Sie die Spalte **Status** auf Informationen zum Konflikt.</span><span class="sxs-lookup"><span data-stu-id="d88a3-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="d88a3-115">Wenn ein Konflikt besteht, wird eine Warnmeldung angezeigt, dass mindestens ein Benutzer eine gültige Lizenz benötigt.</span><span class="sxs-lookup"><span data-stu-id="d88a3-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d88a3-116">Die Spalte **Status** wird nicht angezeigt, wenn keine Konflikte vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d88a3-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="d88a3-117">Wie kann ich Lizenzkonflikte lösen?</span><span class="sxs-lookup"><span data-stu-id="d88a3-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="d88a3-118">Sie können Lizenzkonflikte [lösen,](../../commerce/licenses/buy-licenses.md) indem Sie entweder mehr Lizenzen kaufen oder Lizenzen von Benutzern entfernen, die sie nicht [mehr benötigen.](remove-licenses-from-users.md)</span><span class="sxs-lookup"><span data-stu-id="d88a3-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="d88a3-119">Optional können Sie auch [ein Benutzerkonto löschen, um eine Lizenz freizugeben](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="d88a3-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="d88a3-120">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="d88a3-120">Related articles</span></span>

[<span data-ttu-id="d88a3-121">Zuweisen von Lizenzen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="d88a3-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="d88a3-122">Entfernen von Benutzerlizenzen</span><span class="sxs-lookup"><span data-stu-id="d88a3-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)
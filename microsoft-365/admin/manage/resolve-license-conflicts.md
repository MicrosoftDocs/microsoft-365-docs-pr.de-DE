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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Hier erfahren Sie, wie Sie Lizenz Konflikte mit Ihrem Microsoft 365 for Business-Abonnement beheben.
ms.openlocfilehash: 51f87c055402d9e6e3bd732a99abf2c155887290
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628088"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="4f599-103">Lösen von Lizenzkonflikten</span><span class="sxs-lookup"><span data-stu-id="4f599-103">Resolve license conflicts</span></span>

<span data-ttu-id="4f599-104">Es wird empfohlen, dass Sie die Lizenzen erwerben, die Sie für Ihr Abonnement benötigen, bevor Sie neue Benutzer erstellen.</span><span class="sxs-lookup"><span data-stu-id="4f599-104">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="4f599-105">Auf diese Weise kann neuen Benutzern beim Erstellen der Benutzerkonten eine Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4f599-105">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="4f599-106">Wenn Sie Benutzern bereits alle Lizenzen zugewiesen haben, einige der Lizenzen jedoch abgelaufen sind, oder wenn Sie versuchen, eine Lizenz zu entfernen, die bereits einem Benutzer zugewiesen ist, treten Lizenzkonflikte auf.</span><span class="sxs-lookup"><span data-stu-id="4f599-106">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="4f599-107">Weitere Informationen finden Sie unter [Entfernen von Lizenzen aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="4f599-107">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="4f599-108">Wie kann ich Lizenzkonflikte anzeigen?</span><span class="sxs-lookup"><span data-stu-id="4f599-108">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4f599-109">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="4f599-109">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4f599-110">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="4f599-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4f599-111">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="4f599-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="4f599-112">Prüfen Sie die Spalte **Status** auf Informationen zum Konflikt.</span><span class="sxs-lookup"><span data-stu-id="4f599-112">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="4f599-113">Wenn ein Konflikt vorliegt, wird eine Warnmeldung angezeigt, die besagt, dass ein oder mehrere Benutzer eine gültige Lizenz benötigen.</span><span class="sxs-lookup"><span data-stu-id="4f599-113">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4f599-114">Die Spalte **Status** wird nicht angezeigt, wenn keine Konflikte vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="4f599-114">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="4f599-115">Wie kann ich Lizenzkonflikte lösen?</span><span class="sxs-lookup"><span data-stu-id="4f599-115">How do I resolve license conflicts?</span></span>

<span data-ttu-id="4f599-116">Sie können Lizenz Konflikte lösen, indem Sie entweder [mehr Lizenzen kaufen](../../commerce/licenses/buy-licenses.md) oder [Lizenzen von Benutzern entfernen, die diese nicht mehr benötigen](remove-licenses-from-users.md).</span><span class="sxs-lookup"><span data-stu-id="4f599-116">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="4f599-117">Optional können Sie auch [ein Benutzerkonto löschen, um eine Lizenz freizugeben](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="4f599-117">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="4f599-118">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="4f599-118">Related articles</span></span> 

[<span data-ttu-id="4f599-119">Zuweisen von Lizenzen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="4f599-119">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="4f599-120">Entfernen von Benutzerlizenzen</span><span class="sxs-lookup"><span data-stu-id="4f599-120">Remove licenses from users</span></span>](remove-licenses-from-users.md)

---
title: Lösen von Lizenzkonflikten in Office 365 Business
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
description: Hier erfahren Sie, wie Sie Lizenz Konflikte mit Ihrem Office 365 für Unternehmen-Abonnement lösen.
ms.openlocfilehash: de0a6c988b9ca2ae033a24c012b7f36bc1db58a3
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43540915"
---
# <a name="resolve-license-conflicts-in-office-365-for-business"></a><span data-ttu-id="cbcf5-103">Lösen von Lizenzkonflikten in Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="cbcf5-103">Resolve license conflicts in Office 365 for business</span></span>

<span data-ttu-id="cbcf5-104">Es wird empfohlen, dass Sie die Lizenzen erwerben, die Sie für Ihr Abonnement benötigen, bevor Sie neue Benutzer erstellen.</span><span class="sxs-lookup"><span data-stu-id="cbcf5-104">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="cbcf5-105">Auf diese Weise kann neuen Benutzern beim Erstellen der Benutzerkonten eine Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="cbcf5-105">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="cbcf5-106">Wenn Sie Benutzern bereits alle Lizenzen zugewiesen haben, einige der Lizenzen jedoch abgelaufen sind, oder wenn Sie versuchen, eine Lizenz zu entfernen, die bereits einem Benutzer zugewiesen ist, treten Lizenzkonflikte auf.</span><span class="sxs-lookup"><span data-stu-id="cbcf5-106">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="cbcf5-107">Weitere Informationen finden Sie unter [Entfernen von Lizenzen aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="cbcf5-107">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="cbcf5-108">Wie kann ich Lizenzkonflikte anzeigen?</span><span class="sxs-lookup"><span data-stu-id="cbcf5-108">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cbcf5-109">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="cbcf5-109">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cbcf5-110">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="cbcf5-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cbcf5-111">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="cbcf5-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="cbcf5-112">Prüfen Sie die Spalte **Status** auf Informationen zum Konflikt.</span><span class="sxs-lookup"><span data-stu-id="cbcf5-112">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="cbcf5-113">Wenn ein Konflikt vorliegt, wird eine Warnmeldung angezeigt, die besagt, dass ein oder mehrere Benutzer eine gültige Lizenz benötigen.</span><span class="sxs-lookup"><span data-stu-id="cbcf5-113">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cbcf5-114">Die Spalte **Status** wird nicht angezeigt, wenn keine Konflikte vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="cbcf5-114">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="cbcf5-115">Wie kann ich Lizenzkonflikte lösen?</span><span class="sxs-lookup"><span data-stu-id="cbcf5-115">How do I resolve license conflicts?</span></span>

<span data-ttu-id="cbcf5-116">Sie können Lizenz Konflikte lösen, indem Sie entweder [mehr Lizenzen kaufen](../../commerce/licenses/buy-licenses.md) oder [Lizenzen von Benutzern entfernen, die diese nicht mehr benötigen](remove-licenses-from-users.md).</span><span class="sxs-lookup"><span data-stu-id="cbcf5-116">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="cbcf5-117">Optional können Sie auch [ein Benutzerkonto löschen, um eine Lizenz freizugeben](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="cbcf5-117">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="cbcf5-118">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="cbcf5-118">Related articles</span></span> 

[<span data-ttu-id="cbcf5-119">Zuweisen von Lizenzen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="cbcf5-119">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="cbcf5-120">Entfernen von Benutzerlizenzen</span><span class="sxs-lookup"><span data-stu-id="cbcf5-120">Remove licenses from users</span></span>](remove-licenses-from-users.md)

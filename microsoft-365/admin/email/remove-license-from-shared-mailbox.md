---
title: Entfernen der Lizenz aus einem freigegebenen Postfach
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Entfernen Sie die Lizenz aus einem freigegebenen Postfach, um Sie einem anderen Benutzer zuzuweisen. '
ms.openlocfilehash: 11d5185cc3f79899a737ddccc0a93160acb380bc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698303"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="b4616-103">Entfernen einer Lizenz aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="b4616-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b4616-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="b4616-104">The admin center is changing.</span></span> <span data-ttu-id="b4616-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="b4616-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="b4616-106">Freigegebene Postfächer benötigen normalerweise keine Lizenz.</span><span class="sxs-lookup"><span data-stu-id="b4616-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="b4616-107">Befolgen Sie diese Anweisungen, um eine Lizenz aus einem freigegebenen Postfach zu entfernen, damit Sie Sie entweder einem Benutzer zuweisen oder die Lizenz zurückgeben können, damit Sie nicht für eine Lizenz bezahlen, die Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="b4616-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="b4616-108">In den folgenden Szenarien ist eine Lizenz erforderlich:</span><span class="sxs-lookup"><span data-stu-id="b4616-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="b4616-109">Das freigegebene Postfach verfügt über mehr als 50 GB Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="b4616-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="b4616-110">Das freigegebene Postfach verwendet die in-Place-Archivierung.</span><span class="sxs-lookup"><span data-stu-id="b4616-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="b4616-111">Das freigegebene Postfach wird in einem Beweissicherungsverfahren aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="b4616-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="b4616-112">Dem freigegebenen Postfach wird eine Microsoft Defender-Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b4616-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="b4616-113">Entfernen der Lizenz</span><span class="sxs-lookup"><span data-stu-id="b4616-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b4616-114">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="b4616-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b4616-115">Sie müssen die Lizenz von der Seite "aktive Benutzer" entfernen.</span><span class="sxs-lookup"><span data-stu-id="b4616-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="b4616-116">Sie können die Lizenz nicht von der Seite freigegebene Postfächer entfernen, da Lizenzen Benutzereinstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="b4616-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="b4616-117">Wählen Sie das freigegebene Postfach aus.</span><span class="sxs-lookup"><span data-stu-id="b4616-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="b4616-118">Erweitern Sie auf der Registerkarte **Lizenzen und apps** den Knoten **Lizenzen** , und deaktivieren Sie das Kontrollkästchen für die Lizenz, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="b4616-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="b4616-119">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="b4616-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="b4616-120">Wenn Sie zur Seite **aktive Benutzer** zurückkehren, wird der Status des freigegebenen Postfachs nicht **lizenziert**.</span><span class="sxs-lookup"><span data-stu-id="b4616-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="b4616-121">Sie zahlen noch immer für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="b4616-121">You're still paying for the license.</span></span> <span data-ttu-id="b4616-122">Um das bezahlen zu beenden, [Entfernen Sie die Lizenz aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="b4616-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="b4616-123">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="b4616-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4616-124">Sie müssen die Lizenz von der Seite "aktive Benutzer" entfernen.</span><span class="sxs-lookup"><span data-stu-id="b4616-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="b4616-125">Sie können die Lizenz nicht von der Seite freigegebene Postfächer entfernen, da Lizenzen Benutzereinstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="b4616-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="b4616-126">Wählen Sie das freigegebene Postfach aus, und wählen Sie neben **Produktlizenzen** **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="b4616-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="b4616-127">Legen Sie auf der Seite **Produktlizenzen** die Umschaltfläche für die Lizenz, die Sie entfernen möchten, auf **aus** fest.</span><span class="sxs-lookup"><span data-stu-id="b4616-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="b4616-128">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b4616-128">Select **Save**.</span></span>

5. <span data-ttu-id="b4616-129">Wenn Sie zur Seite **aktive Benutzer** zurückkehren, wird der Status des freigegebenen Postfachs nicht **lizenziert**.</span><span class="sxs-lookup"><span data-stu-id="b4616-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="b4616-130">Sie zahlen noch immer für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="b4616-130">You're still paying for the license.</span></span> <span data-ttu-id="b4616-131">Um das bezahlen zu beenden, [Entfernen Sie die Lizenz aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="b4616-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="b4616-132">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="b4616-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4616-133">Sie müssen die Lizenz von der Seite "aktive Benutzer" entfernen.</span><span class="sxs-lookup"><span data-stu-id="b4616-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="b4616-134">Sie können die Lizenz nicht von der Seite freigegebene Postfächer entfernen, da Lizenzen Benutzereinstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="b4616-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="b4616-135">Wählen Sie das freigegebene Postfach aus, und wählen Sie neben **Produktlizenzen** **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="b4616-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="b4616-136">Legen Sie auf der Seite **Produktlizenzen** die Umschaltfläche für die Lizenz, die Sie entfernen möchten, auf **aus** fest.</span><span class="sxs-lookup"><span data-stu-id="b4616-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="b4616-137">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b4616-137">Select **Save**.</span></span>

5. <span data-ttu-id="b4616-138">Wenn Sie zur Seite **aktive Benutzer** zurückkehren, wird der Status des freigegebenen Postfachs nicht **lizenziert**.</span><span class="sxs-lookup"><span data-stu-id="b4616-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="b4616-139">Sie zahlen noch immer für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="b4616-139">You're still paying for the license.</span></span> <span data-ttu-id="b4616-140">Um das bezahlen zu beenden, [Entfernen Sie die Lizenz aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="b4616-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="b4616-141">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="b4616-141">Related articles</span></span>

[<span data-ttu-id="b4616-142">Informationen zu freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="b4616-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="b4616-143">Erstellen eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="b4616-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="b4616-144">Konfigurieren eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="b4616-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="b4616-145">Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="b4616-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="b4616-146">Beheben von Problemen mit freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="b4616-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)

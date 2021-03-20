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
description: 'Entfernen Sie die Lizenz aus einem freigegebenen Postfach, um sie einem anderen Benutzer zuzuordnen. '
ms.openlocfilehash: 1acd549936212db7f722355ed1f2518ff6bbac18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915686"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="e18a6-103">Entfernen einer Lizenz aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="e18a6-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e18a6-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="e18a6-104">The admin center is changing.</span></span> <span data-ttu-id="e18a6-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="e18a6-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e18a6-106">Für freigegebene Postfächer ist in der Regel keine Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e18a6-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="e18a6-107">Befolgen Sie diese Anweisungen, um eine Lizenz aus einem freigegebenen Postfach zu entfernen, damit Sie sie entweder einem Benutzer zuweisen oder die Lizenz zurückgeben können, damit Sie keine Lizenz bezahlen, die Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="e18a6-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="e18a6-108">In den folgenden Szenarien ist eine Lizenz erforderlich:</span><span class="sxs-lookup"><span data-stu-id="e18a6-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="e18a6-109">Das freigegebene Postfach verfügt über mehr als 50 GB Speicher.</span><span class="sxs-lookup"><span data-stu-id="e18a6-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="e18a6-110">Das freigegebene Postfach verwendet die in-place-Archivierung.</span><span class="sxs-lookup"><span data-stu-id="e18a6-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="e18a6-111">Das freigegebene Postfach befindet sich in einem Rechtsstreit.</span><span class="sxs-lookup"><span data-stu-id="e18a6-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="e18a6-112">Dem freigegebenen Postfach ist eine Microsoft Defender-Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e18a6-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="e18a6-113">Entfernen der Lizenz</span><span class="sxs-lookup"><span data-stu-id="e18a6-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e18a6-114">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="e18a6-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e18a6-115">Sie müssen die Lizenz von der Seite Aktive Benutzer entfernen.</span><span class="sxs-lookup"><span data-stu-id="e18a6-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="e18a6-116">Sie können die Lizenz nicht von der Seite Freigegebenes Postfach entfernen, da Lizenzen Benutzereinstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="e18a6-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="e18a6-117">Wählen Sie das freigegebene Postfach aus.</span><span class="sxs-lookup"><span data-stu-id="e18a6-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="e18a6-118">Erweitern Sie eine der Registerkarte Lizenzen und **Apps,** **und** deaktivieren Sie das Kontrollkästchen für die Lizenz, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="e18a6-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="e18a6-119">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e18a6-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="e18a6-120">Wenn Sie zur Seite **Aktive** Benutzer zurückkehren, wird der Status des **freigegebenen Postfachs nicht lizenziert.**</span><span class="sxs-lookup"><span data-stu-id="e18a6-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="e18a6-121">Sie zahlen weiterhin für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="e18a6-121">You're still paying for the license.</span></span> <span data-ttu-id="e18a6-122">Um die Zahlung zu beenden, [entfernen Sie die Lizenz aus Ihrem Abonnement.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="e18a6-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="e18a6-123">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="e18a6-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e18a6-124">Sie müssen die Lizenz von der Seite Aktive Benutzer entfernen.</span><span class="sxs-lookup"><span data-stu-id="e18a6-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="e18a6-125">Sie können die Lizenz nicht von der Seite Freigegebenes Postfach entfernen, da Lizenzen Benutzereinstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="e18a6-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="e18a6-126">Wählen Sie das freigegebene Postfach aus, und wählen Sie dann **Bearbeiten neben** **Produktlizenzen aus.**</span><span class="sxs-lookup"><span data-stu-id="e18a6-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="e18a6-127">Legen Sie **auf der Seite** Produktlizenzen den Umschalter auf **Aus** für die Lizenz, die Sie entfernen möchten, ein.</span><span class="sxs-lookup"><span data-stu-id="e18a6-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="e18a6-128">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e18a6-128">Select **Save**.</span></span>

5. <span data-ttu-id="e18a6-129">Wenn Sie zur Seite **Aktive** Benutzer zurückkehren, wird der Status des **freigegebenen Postfachs nicht lizenziert.**</span><span class="sxs-lookup"><span data-stu-id="e18a6-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="e18a6-130">Sie zahlen weiterhin für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="e18a6-130">You're still paying for the license.</span></span> <span data-ttu-id="e18a6-131">Um die Zahlung zu beenden, [entfernen Sie die Lizenz aus Ihrem Abonnement.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="e18a6-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="e18a6-132">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="e18a6-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e18a6-133">Sie müssen die Lizenz von der Seite Aktive Benutzer entfernen.</span><span class="sxs-lookup"><span data-stu-id="e18a6-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="e18a6-134">Sie können die Lizenz nicht von der Seite Freigegebenes Postfach entfernen, da Lizenzen Benutzereinstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="e18a6-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="e18a6-135">Wählen Sie das freigegebene Postfach aus, und wählen Sie dann **Bearbeiten neben** **Produktlizenzen aus.**</span><span class="sxs-lookup"><span data-stu-id="e18a6-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="e18a6-136">Legen Sie **auf der Seite** Produktlizenzen den Umschalter auf **Aus** für die Lizenz, die Sie entfernen möchten, ein.</span><span class="sxs-lookup"><span data-stu-id="e18a6-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="e18a6-137">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e18a6-137">Select **Save**.</span></span>

5. <span data-ttu-id="e18a6-138">Wenn Sie zur Seite **Aktive** Benutzer zurückkehren, wird der Status des **freigegebenen Postfachs nicht lizenziert.**</span><span class="sxs-lookup"><span data-stu-id="e18a6-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="e18a6-139">Sie zahlen weiterhin für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="e18a6-139">You're still paying for the license.</span></span> <span data-ttu-id="e18a6-140">Um die Zahlung zu beenden, [entfernen Sie die Lizenz aus Ihrem Abonnement.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="e18a6-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="e18a6-141">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="e18a6-141">Related articles</span></span>

[<span data-ttu-id="e18a6-142">Informationen zu freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="e18a6-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="e18a6-143">Erstellen eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="e18a6-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="e18a6-144">Konfigurieren eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="e18a6-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="e18a6-145">Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="e18a6-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="e18a6-146">Beheben von Problemen mit freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="e18a6-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
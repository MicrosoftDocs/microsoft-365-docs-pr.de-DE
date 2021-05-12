---
title: Entfernen der Lizenz aus einem freigegebenen Postfach
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Entfernen Sie die Lizenz aus einem freigegebenen Postfach, um sie einem anderen Benutzer zuzuordnen. '
ms.openlocfilehash: 2d0e6e6b1d6222bea80265bf6cc008e21ac3239c
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332654"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="7ee30-103">Entfernen einer Lizenz aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="7ee30-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="7ee30-104">Für freigegebene Postfächer ist in der Regel keine Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7ee30-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="7ee30-105">Befolgen Sie diese Anweisungen, um eine Lizenz aus einem freigegebenen Postfach zu entfernen, damit Sie sie entweder einem Benutzer zuweisen oder die Lizenz zurückgeben können, damit Sie keine Lizenz bezahlen, die Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="7ee30-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
>
> <span data-ttu-id="7ee30-106">In den folgenden Szenarien ist eine Lizenz erforderlich:</span><span class="sxs-lookup"><span data-stu-id="7ee30-106">A license is required in the following scenarios:</span></span>
>
> 1. <span data-ttu-id="7ee30-107">Das freigegebene Postfach verfügt über mehr als 50 GB Speicher.</span><span class="sxs-lookup"><span data-stu-id="7ee30-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="7ee30-108">Das freigegebene Postfach verwendet die in-place-Archivierung.</span><span class="sxs-lookup"><span data-stu-id="7ee30-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="7ee30-109">Das freigegebene Postfach befindet sich in einem Rechtsstreit.</span><span class="sxs-lookup"><span data-stu-id="7ee30-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="7ee30-110">Dem freigegebenen Postfach ist eine Microsoft Defender-Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7ee30-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

## <a name="remove-the-license"></a><span data-ttu-id="7ee30-111">Entfernen der Lizenz</span><span class="sxs-lookup"><span data-stu-id="7ee30-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7ee30-112">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="7ee30-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7ee30-113">Sie müssen die Lizenz von der Seite Aktive Benutzer entfernen.</span><span class="sxs-lookup"><span data-stu-id="7ee30-113">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="7ee30-114">Sie können die Lizenz nicht von der Seite Freigegebenes Postfach entfernen, da Lizenzen Benutzereinstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="7ee30-114">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>
  
2. <span data-ttu-id="7ee30-115">Wählen Sie das freigegebene Postfach aus.</span><span class="sxs-lookup"><span data-stu-id="7ee30-115">Select the shared mailbox.</span></span>

3. <span data-ttu-id="7ee30-116">Erweitern Sie eine der Registerkarte Lizenzen und **Apps,** **und** deaktivieren Sie das Kontrollkästchen für die Lizenz, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="7ee30-116">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="7ee30-117">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="7ee30-117">Select **Save changes**.</span></span>

5. <span data-ttu-id="7ee30-118">Wenn Sie zur Seite **Aktive** Benutzer zurückkehren, wird der Status des **freigegebenen Postfachs nicht lizenziert.**</span><span class="sxs-lookup"><span data-stu-id="7ee30-118">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="7ee30-119">Sie zahlen weiterhin für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="7ee30-119">You're still paying for the license.</span></span> <span data-ttu-id="7ee30-120">Um die Zahlung zu beenden, [entfernen Sie die Lizenz aus Ihrem Abonnement.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="7ee30-120">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="7ee30-121">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="7ee30-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7ee30-122">Sie müssen die Lizenz von der Seite Aktive Benutzer entfernen.</span><span class="sxs-lookup"><span data-stu-id="7ee30-122">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="7ee30-123">Sie können die Lizenz nicht von der Seite Freigegebenes Postfach entfernen, da Lizenzen Benutzereinstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="7ee30-123">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="7ee30-124">Wählen Sie das freigegebene Postfach aus, und wählen Sie dann **Bearbeiten neben** **Produktlizenzen aus.**</span><span class="sxs-lookup"><span data-stu-id="7ee30-124">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="7ee30-125">Legen Sie **auf der Seite** Produktlizenzen den Umschalter auf **Aus** für die Lizenz, die Sie entfernen möchten, ein.</span><span class="sxs-lookup"><span data-stu-id="7ee30-125">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="7ee30-126">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="7ee30-126">Select **Save**.</span></span>

5. <span data-ttu-id="7ee30-127">Wenn Sie zur Seite **Aktive** Benutzer zurückkehren, wird der Status des **freigegebenen Postfachs nicht lizenziert.**</span><span class="sxs-lookup"><span data-stu-id="7ee30-127">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="7ee30-128">Sie zahlen weiterhin für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="7ee30-128">You're still paying for the license.</span></span> <span data-ttu-id="7ee30-129">Um die Zahlung zu beenden, [entfernen Sie die Lizenz aus Ihrem Abonnement.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="7ee30-129">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="7ee30-130">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="7ee30-130">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7ee30-131">Sie müssen die Lizenz von der Seite Aktive Benutzer entfernen.</span><span class="sxs-lookup"><span data-stu-id="7ee30-131">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="7ee30-132">Sie können die Lizenz nicht von der Seite Freigegebenes Postfach entfernen, da Lizenzen Benutzereinstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="7ee30-132">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="7ee30-133">Wählen Sie das freigegebene Postfach aus, und wählen Sie dann **Bearbeiten neben** **Produktlizenzen aus.**</span><span class="sxs-lookup"><span data-stu-id="7ee30-133">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="7ee30-134">Legen Sie **auf der Seite** Produktlizenzen den Umschalter auf **Aus** für die Lizenz, die Sie entfernen möchten, ein.</span><span class="sxs-lookup"><span data-stu-id="7ee30-134">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="7ee30-135">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="7ee30-135">Select **Save**.</span></span>

5. <span data-ttu-id="7ee30-136">Wenn Sie zur Seite **Aktive** Benutzer zurückkehren, wird der Status des **freigegebenen Postfachs nicht lizenziert.**</span><span class="sxs-lookup"><span data-stu-id="7ee30-136">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="7ee30-137">Sie zahlen weiterhin für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="7ee30-137">You're still paying for the license.</span></span> <span data-ttu-id="7ee30-138">Um die Zahlung zu beenden, [entfernen Sie die Lizenz aus Ihrem Abonnement.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="7ee30-138">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="7ee30-139">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="7ee30-139">Related articles</span></span>

[<span data-ttu-id="7ee30-140">Informationen zu freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="7ee30-140">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="7ee30-141">Erstellen eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="7ee30-141">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="7ee30-142">Konfigurieren eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="7ee30-142">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="7ee30-143">Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="7ee30-143">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="7ee30-144">Beheben von Problemen mit freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="7ee30-144">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)

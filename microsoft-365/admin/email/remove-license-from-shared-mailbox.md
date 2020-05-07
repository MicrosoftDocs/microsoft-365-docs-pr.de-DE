---
title: Entfernen der Lizenz aus einem freigegebenen Postfach
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Entfernen Sie die Lizenz aus einem freigegebenen Postfach, um Sie einem anderen Benutzer zuzuweisen. '
ms.openlocfilehash: fb09036fc28ea3d9c182395d0a85e467f611dfdc
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140429"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="5698e-103">Entfernen einer Lizenz aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="5698e-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5698e-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="5698e-104">The admin center is changing.</span></span> <span data-ttu-id="5698e-105">Wenn Ihre Erfahrung nicht mit den hier dargestellten Details übereinstimmt, lesen Sie [Informationen zum neuen Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="5698e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="5698e-106">Freigegebene Postfächer benötigen keine Lizenz, es sei denn, das Postfach hat mehr als 50 GB Daten.</span><span class="sxs-lookup"><span data-stu-id="5698e-106">Shared mailboxes don't need a license unless the mailbox has over 50GB of data.</span></span> <span data-ttu-id="5698e-107">Befolgen Sie diese Anweisungen, um eine Lizenz aus einem freigegebenen Postfach zu entfernen, damit Sie Sie entweder einem Benutzer zuweisen oder die Lizenz zurückgeben können, damit Sie nicht für eine Lizenz bezahlen, die Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="5698e-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>
  
## <a name="remove-the-license"></a><span data-ttu-id="5698e-108">Entfernen der Lizenz</span><span class="sxs-lookup"><span data-stu-id="5698e-108">Remove the license</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="5698e-109">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="5698e-109">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="5698e-110">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="5698e-110">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5698e-111">Sie müssen die Lizenz von der Seite "aktive Benutzer" entfernen.</span><span class="sxs-lookup"><span data-stu-id="5698e-111">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="5698e-112">Sie können die Lizenz nicht von der Seite freigegebene Postfächer entfernen, da Lizenzen Benutzereinstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="5698e-112">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="5698e-113">Wählen Sie das freigegebene Postfach aus.</span><span class="sxs-lookup"><span data-stu-id="5698e-113">Select the shared mailbox.</span></span>

3. <span data-ttu-id="5698e-114">Erweitern Sie auf der Registerkarte **Lizenzen und apps** den Knoten **Lizenzen** , und deaktivieren Sie das Kontrollkästchen für die Lizenz, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="5698e-114">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="5698e-115">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="5698e-115">Select **Save changes**.</span></span>

5. <span data-ttu-id="5698e-116">Wenn Sie zur Seite **aktive Benutzer** zurückkehren, wird der Status des freigegebenen Postfachs nicht **lizenziert**.</span><span class="sxs-lookup"><span data-stu-id="5698e-116">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="5698e-117">Sie zahlen noch immer für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="5698e-117">You're still paying for the license.</span></span> <span data-ttu-id="5698e-118">Um das bezahlen zu beenden, [Entfernen Sie die Lizenz aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="5698e-118">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="5698e-119">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="5698e-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5698e-120">Sie müssen die Lizenz von der Seite "aktive Benutzer" entfernen.</span><span class="sxs-lookup"><span data-stu-id="5698e-120">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="5698e-121">Sie können die Lizenz nicht von der Seite freigegebene Postfächer entfernen, da Lizenzen Benutzereinstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="5698e-121">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="5698e-122">Wählen Sie das freigegebene Postfach aus, und wählen Sie neben **Produktlizenzen** **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="5698e-122">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="5698e-123">Legen Sie auf der Seite **Produktlizenzen** die Umschaltfläche für die Lizenz, die Sie entfernen möchten, auf **aus** fest.</span><span class="sxs-lookup"><span data-stu-id="5698e-123">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="5698e-124">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5698e-124">Select **Save**.</span></span>

5. <span data-ttu-id="5698e-125">Wenn Sie zur Seite **aktive Benutzer** zurückkehren, wird der Status des freigegebenen Postfachs nicht **lizenziert**.</span><span class="sxs-lookup"><span data-stu-id="5698e-125">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="5698e-126">Sie zahlen noch immer für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="5698e-126">You're still paying for the license.</span></span> <span data-ttu-id="5698e-127">Um das bezahlen zu beenden, [Entfernen Sie die Lizenz aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="5698e-127">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="5698e-128">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="5698e-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5698e-129">Sie müssen die Lizenz von der Seite "aktive Benutzer" entfernen.</span><span class="sxs-lookup"><span data-stu-id="5698e-129">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="5698e-130">Sie können die Lizenz nicht von der Seite freigegebene Postfächer entfernen, da Lizenzen Benutzereinstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="5698e-130">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="5698e-131">Wählen Sie das freigegebene Postfach aus, und wählen Sie neben **Produktlizenzen** **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="5698e-131">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="5698e-132">Legen Sie auf der Seite **Produktlizenzen** die Umschaltfläche für die Lizenz, die Sie entfernen möchten, auf **aus** fest.</span><span class="sxs-lookup"><span data-stu-id="5698e-132">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="5698e-133">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5698e-133">Select **Save**.</span></span>

5. <span data-ttu-id="5698e-134">Wenn Sie zur Seite **aktive Benutzer** zurückkehren, wird der Status des freigegebenen Postfachs nicht **lizenziert**.</span><span class="sxs-lookup"><span data-stu-id="5698e-134">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="5698e-135">Sie zahlen noch immer für die Lizenz.</span><span class="sxs-lookup"><span data-stu-id="5698e-135">You're still paying for the license.</span></span> <span data-ttu-id="5698e-136">Um das bezahlen zu beenden, [Entfernen Sie die Lizenz aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="5698e-136">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="5698e-137">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="5698e-137">Related articles</span></span>

[<span data-ttu-id="5698e-138">Informationen zu freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="5698e-138">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="5698e-139">Erstellen eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="5698e-139">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="5698e-140">Konfigurieren eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="5698e-140">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="5698e-141">Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="5698e-141">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="5698e-142">Beheben von Problemen mit freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="5698e-142">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)

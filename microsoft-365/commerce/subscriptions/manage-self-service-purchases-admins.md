---
title: Verwalten von Self-Service-Käufen (Admins)
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- commerce
search.appverid:
- MET150
description: Administratoren können erfahren, wie Sie Self-Service-Käufe von Benutzern in ihrer Organisation verwalten.
ms.openlocfilehash: 5378d14affd074bfad356fea4bb2adbd6ca104dd
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293571"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="1a5c3-103">Self-Service-Einkäufe (Administrator) verwalten</span><span class="sxs-lookup"><span data-stu-id="1a5c3-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="1a5c3-104">Als Administrator können Sie Self-Service-Käufe von Personen in Ihrer Organisation sehen.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="1a5c3-105">Der Produktname, der Käufername, die erworbenen Abonnements, das Ablaufdatum, der Einkaufspreis und die zugewiesenen Benutzer werden für jeden Self-Service-Kauf angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-105">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="1a5c3-106">Falls von Ihrer Organisation erforderlich, können Sie den Self-Service-Kauf pro Produktbasis über PowerShell deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-106">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="1a5c3-107">Sie verfügen über dieselben Datenverwaltungs- und Zugriffsrichtlinien über Produkte, die über den Self-Service-Kauf oder zentral erworben wurden.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="1a5c3-108">Sie können auch steuern, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="1a5c3-109">Weitere Informationen finden Sie unter [Use AllowSelfServicePurchase for the MS Commerce PowerShell module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1a5c3-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="1a5c3-110">Anzeigen von Self-Service-Abonnements</span><span class="sxs-lookup"><span data-stu-id="1a5c3-110">View self-service subscriptions</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1a5c3-111">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1a5c3-112">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-112">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1a5c3-113">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-113">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end

2. <span data-ttu-id="1a5c3-114">Wählen Sie **auf der** Registerkarte Produkte das Filtersymbol aus, und wählen Sie **dann Self-Service aus.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="1a5c3-115">Wenn Sie weitere Details zu einem Abonnement anzeigen möchten, wählen Sie eines aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="1a5c3-116">Anzeigen von Lizenzen für ein Self-Service-Kaufabonnement</span><span class="sxs-lookup"><span data-stu-id="1a5c3-116">View who has licenses for a self-service purchase subscription</span></span>

> [!NOTE]
> <span data-ttu-id="1a5c3-117">Als Administrator können Sie keine Lizenzen für ein Self-Service-Kaufabonnement zuweisen oder aufheben, die von einem Benutzer in Ihrer Organisation erworben wurden.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-117">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="1a5c3-118">Sie können ein [Self-Service-Kaufabonnement übernehmen](#take-over-a-self-service-purchase-subscription)und dann Lizenzen zuweisen oder die Zuweisung von Lizenzen kündigen.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-118">You can [take over a self-service purchase subscription](#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1a5c3-119">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="1a5c3-120">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="1a5c3-121">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Lizenzen</a>.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="1a5c3-122">Wählen Sie das Filtersymbol aus, und wählen Sie **dann Self-Service aus.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-122">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="1a5c3-123">Wählen Sie ein Produkt aus, um Den Personen zugewiesene Lizenzen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-123">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="1a5c3-124">Wenn mehrere Einkäufe für ein Produkt vorhanden sind, wird  dieses Produkt nur einmal aufgeführt, und die Spalte Verfügbare Menge zeigt die Gesamtzahl aller Abonnements an, die für dieses Produkt gekauft wurden.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-124">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="1a5c3-125">Die **Liste Benutzer** wird nach den Namen der Personen, die Self-Service-Käufe getätigt haben, gruppieren.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-125">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="1a5c3-126">Wenn Sie eine Liste der Benutzer mit Lizenzen für diese Abonnements exportieren möchten, wählen Sie die Abonnements aus, die Sie exportieren möchten, und wählen Sie **dann Benutzer exportieren aus.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-126">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="1a5c3-127">Deaktivieren oder Aktivieren von Self-Service-Käufen</span><span class="sxs-lookup"><span data-stu-id="1a5c3-127">Disable or enable self-service purchases</span></span>

<span data-ttu-id="1a5c3-128">Sie können Self-Service-Käufe für Benutzer in Ihrer Organisation deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-128">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="1a5c3-129">Das **MS Commerce** PowerShell-Modul enthält einen **PolicyID-Parameterwert** für **AllowSelfServicePurchase,** mit dem Sie steuern können, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können und für welche Produkte.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-129">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="1a5c3-130">Sie können das **MS Commerce PowerShell-Modul** verwenden, um:</span><span class="sxs-lookup"><span data-stu-id="1a5c3-130">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="1a5c3-131">Anzeigen des Standardstatus des **Parameterwerts AllowSelfServicePurchase** – unabhängig davon, ob er nach Produkt aktiviert oder deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="1a5c3-131">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="1a5c3-132">Anzeigen einer Liste der zutreffenden Produkte und ob der Self-Service-Kauf aktiviert oder deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="1a5c3-132">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="1a5c3-133">Anzeigen oder Ändern der aktuellen Einstellung für ein bestimmtes Produkt, um sie entweder zu aktivieren oder zu deaktivieren</span><span class="sxs-lookup"><span data-stu-id="1a5c3-133">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="1a5c3-134">Weitere Informationen finden Sie unter [Use AllowSelfServicePurchase for the MS Commerce PowerShell module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1a5c3-134">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="1a5c3-135">Zentralisieren von Lizenzen unter einem einzigen Abonnement</span><span class="sxs-lookup"><span data-stu-id="1a5c3-135">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="1a5c3-136">Sie können vorhandene Lizenzen zuweisen oder zusätzliche Abonnements über vorhandene Vereinbarungen für Benutzer erwerben, die Self-Service-Käufen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-136">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="1a5c3-137">Nachdem Sie diese zentral erworbenen Lizenzen zugewiesen haben, können Sie anfordern, dass Käufer ihre vorhandenen Abonnements kündigen.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-137">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1a5c3-138">Wechseln Sie im Admin  Center zur Seite > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Abrechnungskaufdienste.</a></span><span class="sxs-lookup"><span data-stu-id="1a5c3-138">In the admin center go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1a5c3-139">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">im Admin Center</a>zur Seite  > **Abrechnungskaufdienste.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-139">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1a5c3-140">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">im Admin Center</a>zur Seite  > **Abrechnungskaufdienste.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-140">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

2. <span data-ttu-id="1a5c3-141">Suchen Sie das Produkt, das Sie kaufen möchten, und wählen Sie dann **Kaufen aus.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-141">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="1a5c3-142">Führen Sie die verbleibenden Schritte aus, um Ihren Kauf zu abschließen.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-142">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="1a5c3-143">Führen Sie die Schritte in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) aus, um eine Liste von Benutzern zu exportieren, auf die im nächsten Schritt verwiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-143">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="1a5c3-144">Weisen Sie allen Benutzern, die über eine Lizenz im anderen Abonnement verfügen, Lizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-144">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="1a5c3-145">Vollständige Schritte finden Sie unter [Zuweisen von Lizenzen zu Benutzern](../../admin/manage/assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="1a5c3-145">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="1a5c3-146">Wenden Sie sich an die Person, die das Self-Service-Kaufabonnement erworben hat, und bitten Sie sie, es [zu kündigen.](manage-self-service-purchases-users.md#cancel-a-subscription)</span><span class="sxs-lookup"><span data-stu-id="1a5c3-146">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="1a5c3-147">Übernehmen eines Self-Service-Kaufabonnements</span><span class="sxs-lookup"><span data-stu-id="1a5c3-147">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="1a5c3-148">Sie können ein Self-Service-Kaufabonnement übernehmen, das von einem Benutzer in Ihrer Organisation vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-148">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="1a5c3-149">Wenn Sie ein Self-Service-Kaufabonnement übernehmen, haben Sie zwei Optionen:</span><span class="sxs-lookup"><span data-stu-id="1a5c3-149">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="1a5c3-150">Verschieben Sie die Benutzer in ein anderes Abonnement, und kündigen Sie das ursprüngliche Abonnement.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-150">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="1a5c3-151">Kündigen Sie das Self-Service-Kaufabonnement, und entfernen Sie Lizenzen von zugewiesenen Benutzern.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-151">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="1a5c3-152">Verschieben von Benutzern zu einem anderen Abonnement</span><span class="sxs-lookup"><span data-stu-id="1a5c3-152">Move users to a different subscription</span></span>

<span data-ttu-id="1a5c3-153">Wenn Sie Benutzer in ein anderes Abonnement verschieben, wird das alte Abonnement automatisch gekündigt.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-153">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="1a5c3-154">Der Benutzer, der das Self-Service-Kaufabonnement ursprünglich erworben hat, erhält eine E-Mail mit der Nachricht, dass das Abonnement gekündigt wurde.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-154">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="1a5c3-155">Sie müssen über eine verfügbare Lizenz für jeden Benutzer verfügen, in den Sie das Abonnement verschieben, zu dem Sie Benutzer verschieben.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-155">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1a5c3-156">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1a5c3-157">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">im Admin Center</a>zur Seite **Abrechnung** > **Ihre Produkte.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-157">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1a5c3-158">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">im Admin Center</a>zur Seite **Abrechnung** > **Ihre Produkte.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-158">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="1a5c3-159">Wählen Sie **auf der** Registerkarte Produkte das Filtersymbol aus, und wählen Sie **dann Self-Service aus.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-159">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="1a5c3-160">Wählen Sie das Abonnement aus, das Sie übernehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-160">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="1a5c3-161">Wählen Sie auf der Seite Abonnementdetails im Abschnitt **Abonnements und** Einstellungen die Option Kontrolle über dieses Abonnement **übernehmen aus.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-161">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="1a5c3-162">Wählen Sie im rechten Bereich Benutzer **verschieben aus.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-162">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="1a5c3-163">Wählen Sie das Produkt aus, in das Sie die Benutzer verschieben möchten, und wählen Sie **dann Benutzer verschieben aus.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-163">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="1a5c3-164">Wählen Sie **im Feld Benutzer in** verschieben die Option Benutzer verschieben **aus.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-164">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="1a5c3-165">Der Verschiebevorgang kann einige Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-165">The move process might take several minutes.</span></span> <span data-ttu-id="1a5c3-166">Schließen Sie den Browser nicht, während der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-166">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="1a5c3-167">Schließen Sie nach Abschluss des Verschiebens den **Bereich Abgeschlossen verschieben.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-167">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="1a5c3-168">Auf der Seite Abonnementdetails wird **der Abonnementstatus** für das gekaufte Self-Service-Abonnement als **Gelöscht angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-168">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="1a5c3-169">Kündigen eines Self-Service-Kaufabonnements</span><span class="sxs-lookup"><span data-stu-id="1a5c3-169">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="1a5c3-170">Wenn Sie ein Self-Service-Kaufabonnement kündigen, verlieren Benutzer mit Lizenzen den Zugriff auf das Produkt.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-170">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="1a5c3-171">Der Benutzer, der das Self-Service-Kaufabonnement ursprünglich erworben hat, erhält eine E-Mail mit der Nachricht, dass das Abonnement gekündigt wurde.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-171">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1a5c3-172">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-172">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1a5c3-173">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">im Admin Center</a>zur Seite **Abrechnung** > **Ihre Produkte.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-173">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1a5c3-174">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">im Admin Center</a>zur Seite **Abrechnung** > **Ihre Produkte.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-174">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="1a5c3-175">Wählen Sie **auf der** Registerkarte Produkte das Filtersymbol aus, und wählen Sie **dann Self-Service aus.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-175">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="1a5c3-176">Wählen Sie das Abonnement aus, das Sie stornieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-176">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="1a5c3-177">Wählen Sie auf der Seite Abonnementdetails im Abschnitt **Abonnements und** Einstellungen die Option Kontrolle über dieses Abonnement **übernehmen aus.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-177">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="1a5c3-178">Wählen Sie im rechten Bereich Abonnement **abbrechen aus.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-178">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="1a5c3-179">Wählen Sie in der Dropdownliste einen Grund für Ihre Kündigung aus, und wählen Sie Dann **Abonnement abbrechen aus.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-179">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="1a5c3-180">Wählen Sie im Feld Sind **Sie sicher, dass Sie kündigen möchten?** die Option **Abonnement abbrechen aus.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-180">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="1a5c3-181">Schließen Sie den rechten Bereich.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-181">Close the right pane.</span></span>
9. <span data-ttu-id="1a5c3-182">Auf der Seite Abonnementdetails wird der **Abonnementstatus** als **Gelöscht angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="1a5c3-182">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="1a5c3-183">Benötigen Sie Hilfe?</span><span class="sxs-lookup"><span data-stu-id="1a5c3-183">Need help?</span></span> <span data-ttu-id="1a5c3-184">Kontaktieren Sie uns.</span><span class="sxs-lookup"><span data-stu-id="1a5c3-184">Contact us.</span></span>

<span data-ttu-id="1a5c3-185">Allgemeine Fragen zu Self-Service-Käufen finden Sie unter Häufig gestellte Fragen zu [Self-Service-Käufen.](self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="1a5c3-185">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="1a5c3-186">Wenn Sie Fragen haben oder Hilfe bei Self-Service-Käufen benötigen, wenden [Sie sich an den Support.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="1a5c3-186">If you have questions or need help with self-service purchases, [contact support](../../business-video/get-help-support.md).</span></span>
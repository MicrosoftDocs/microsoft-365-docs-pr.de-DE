---
title: Verwalten von Lizenzanforderungen
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: Erfahren Sie, wie Sie Lizenzanforderungen von Benutzern für Ihr Microsoft 365 Business-Abonnement überprüfen und genehmigen oder verweigern.
ms.date: 08/07/2020
ms.openlocfilehash: 06ee210b39c19c1f2c8a2041c463568e55001b6e
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331550"
---
# <a name="manage-license-requests"></a><span data-ttu-id="9c9e3-103">Verwalten von Lizenzanforderungen</span><span class="sxs-lookup"><span data-stu-id="9c9e3-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="9c9e3-104">Die Informationen in diesem Artikel gelten nur für gekaufte Self-Service-Produkte.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="9c9e3-105">Weitere Informationen finden Sie unter [Self-Service Purchase FAQ](../subscriptions/self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="9c9e3-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.md).</span></span>

<span data-ttu-id="9c9e3-106">Wenn Sie Self-Service-Käufe in Ihrer Organisation deaktivieren, können Sie Lizenzanforderungen verwenden, um den Lizenzanforderungsprozess für Ihre Benutzer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="9c9e3-107">Wenn ein Benutzer versucht, einen Self-Service-Kauf für ein blockiertes Produkt zu tätigen, kann er eine Lizenzanforderung an Sie, den Administrator, senden. Wenn sie eine Anforderung stellen, können sie die Namen anderer Benutzer hinzufügen, die ebenfalls Lizenzen für das Produkt benötigen.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="9c9e3-108">Wenn Sie Benutzer am Tätigen von Self-Service-Käufen blockieren, sendet Microsoft ihnen keine Marketing-E-Mails.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="9c9e3-109">Wenn sie außerdem eine Testversion eines Produkts verwenden, werden keine Aufforderungen zum Kauf angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="9c9e3-110">Weitere Informationen finden Sie unter [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span><span class="sxs-lookup"><span data-stu-id="9c9e3-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="9c9e3-111">Zum Anzeigen und Verwalten von Lizenzanforderungen verwendet der Administrator die Registerkarte **Anforderungen** auf der **Seite Lizenzierung.**</span><span class="sxs-lookup"><span data-stu-id="9c9e3-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="9c9e3-112">Die Liste enthält den Namen des angeforderten Produkts, den Namen der Person, die eine Lizenz anfordert, das angeforderte Datum und den Status der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="9c9e3-113">Administratoren können die Liste so filtern, dass ausstehende oder abgeschlossene Anforderungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="9c9e3-114">Anforderungen werden für 30 Tage gehalten.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9c9e3-115">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="9c9e3-115">Before you begin</span></span>

<span data-ttu-id="9c9e3-116">Sie müssen ein globaler Administrator sein, um die Aufgaben in diesem Artikel ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="9c9e3-117">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9c9e3-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="9c9e3-118">Verwenden Eines eigenen Anforderungsprozesses</span><span class="sxs-lookup"><span data-stu-id="9c9e3-118">Use your own request process</span></span>

<span data-ttu-id="9c9e3-119">Wenn Ihre Organisation über einen eigenen Anforderungsprozess verfügt, können Sie ihn stattdessen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="9c9e3-120">Sie erstellen eine Meldung, die Benutzern angezeigt wird, wenn sie eine Lizenz anfordern.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c9e3-121">Wenn Sie Ihren eigenen Anforderungsprozess verwenden, werden auf der Registerkarte Anforderungen **keine Anforderungen** angezeigt. Vorhandene Anforderungen vor dem Hinzufügen der Nachricht werden weiterhin angezeigt, bis Sie sie genehmigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="9c9e3-122">Wechseln Sie im Admin Center zur Seite Abrechnungslizenzen,  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> und wählen Sie dann die Registerkarte **Anforderungen** aus.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="9c9e3-123">Wählen **Sie Stattdessen den vorhandenen Anforderungsprozess verwenden aus.**</span><span class="sxs-lookup"><span data-stu-id="9c9e3-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="9c9e3-124">Geben Sie im rechten Bereich im **Feld** Nachricht die Nachricht ein, die Benutzern angezeigt werden soll, wenn sie eine Lizenz anfordern.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="9c9e3-125">Wenn Sie auch einen Link zu Ihrer Organisationsrichtlinie oder anderen Dokumentation hinzufügen möchten, geben Sie die URL in das Textfeld **Link zur Dokumentation (optional)** ein.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="9c9e3-126">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-126">Select **Save**.</span></span>

<span data-ttu-id="9c9e3-127">Wenn Sie zur Liste Anforderungen **zurückkehren,** wird die Meldung Angezeigt, dass Sie Ihren eigenen **Lizenzanforderungsprozess verwenden.**</span><span class="sxs-lookup"><span data-stu-id="9c9e3-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="9c9e3-128">Wenn Sie Änderungen an der Nachricht vornehmen möchten, die an Benutzer gesendet wird, wählen Sie **Stattdessen Den vorhandenen Anforderungsprozess verwenden aus.**</span><span class="sxs-lookup"><span data-stu-id="9c9e3-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="9c9e3-129">Beenden der Verwendung Ihres eigenen Anforderungsprozesses</span><span class="sxs-lookup"><span data-stu-id="9c9e3-129">Stop using your own request process</span></span>

1. <span data-ttu-id="9c9e3-130">Wechseln Sie im Admin Center zur Seite Abrechnungslizenzen,  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> und wählen Sie dann die Registerkarte **Anforderungen** aus.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="9c9e3-131">Wählen **Sie Stattdessen den vorhandenen Anforderungsprozess verwenden aus.**</span><span class="sxs-lookup"><span data-stu-id="9c9e3-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="9c9e3-132">Aktivieren Sie im rechten  Bereich das Kontrollkästchen Anforderungsprozess meiner Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="9c9e3-133">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="9c9e3-134">Genehmigen oder Verweigern einer Lizenzanforderung</span><span class="sxs-lookup"><span data-stu-id="9c9e3-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="9c9e3-135">Wechseln Sie im Admin Center zur Seite Abrechnungslizenzen,  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> und wählen Sie dann die Registerkarte **Anforderungen** aus.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="9c9e3-136">Wählen Sie die Zeile aus, die die Anforderung enthält, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="9c9e3-137">Im rechten Bereich werden Details dazu angezeigt, welche Benutzer Lizenzen für das Produkt wünschen.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="9c9e3-138">Um die gesamte Anforderung zu verweigern, wählen **Sie Nicht** genehmigen aus, und wählen Sie im Dialogfeld Nicht **genehmigen aus.**</span><span class="sxs-lookup"><span data-stu-id="9c9e3-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="9c9e3-139">Um einige Benutzer für die Anforderung zu verweigern, andere jedoch zu genehmigen, wählen Sie das X nach dem Namen der Benutzer aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="9c9e3-140">Ihre Namen werden unter Diesen Benutzern **nicht zuweisen verschoben.**</span><span class="sxs-lookup"><span data-stu-id="9c9e3-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="9c9e3-141">Wenn Sie mehrere Produkte haben, wählen Sie unter **Produkt auswählen** das Produkt aus, für das Sie Lizenzen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="9c9e3-142">Um Benutzern den Zugriff auf bestimmte Apps und Dienste zu verweigern, erweitern Sie **Apps** und Dienste aktivieren oder deaktivieren, und deaktivieren Sie dann die Kontrollkästchen für die, die Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="9c9e3-143">Geben Sie unten im Bereich eine optionale Nachricht in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="9c9e3-144">Wenn Sie fertig sind, wählen Sie **Genehmigen aus.**</span><span class="sxs-lookup"><span data-stu-id="9c9e3-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="9c9e3-145">Im rechten Bereich werden die Details der Anforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="9c9e3-146">Schließen Sie den rechten Bereich.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-146">Close the right pane.</span></span>
    <span data-ttu-id="9c9e3-147">Benutzer erhalten eine E-Mail mit der Nachricht, dass ihre Anforderung genehmigt oder abgelehnt wurde.</span><span class="sxs-lookup"><span data-stu-id="9c9e3-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="9c9e3-148">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="9c9e3-148">Related content</span></span>

<span data-ttu-id="9c9e3-149">[Zuweisen von Lizenzen zu Benutzern ](../../admin/manage/assign-licenses-to-users.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="9c9e3-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="9c9e3-150">[Verschieben von Benutzern in ein anderes Abonnement](../subscriptions/move-users-different-subscription.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="9c9e3-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="9c9e3-151">[Kaufen oder Entfernen von Abonnementlizenzen](buy-licenses.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="9c9e3-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>

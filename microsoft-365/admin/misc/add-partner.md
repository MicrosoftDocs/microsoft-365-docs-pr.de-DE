---
title: Hinzufügen, Ändern oder Löschen eines Abonnementberaterpartners
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
- GEA150
ms.assetid: f86e8177-936e-491e-9024-44dea2b296ff
description: Fügen Sie zum Zeitpunkt des Kaufs Microsoft 365 einen Datensatzpartner hinzu, ändern Sie den Partner, oder löschen Sie einen Partner aus einem Abonnement.
ms.openlocfilehash: 4cebbce41cbd2a500cc502b808734f6056271d12
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683343"
---
# <a name="add-change-or-delete-a-subscription-advisor-partner"></a><span data-ttu-id="71b53-103">Hinzufügen, Ändern oder Löschen eines Abonnementberaterpartners</span><span class="sxs-lookup"><span data-stu-id="71b53-103">Add, change, or delete a subscription advisor partner</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="71b53-104">Dieser Artikel gilt für Office 365 betrieben von 21Vianet in China.</span><span class="sxs-lookup"><span data-stu-id="71b53-104">This article applies to Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="71b53-105">Es ist für Organisationen, die einem 21Vianet-Partner die Verwaltung ihrer Office 365 ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="71b53-105">It is for organizations who want to allow a 21Vianet Partner to administer their Office 365 subscription for them.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="71b53-106">[] Ein autorisierter Microsoft-Partner, der als Abonnementberater fungiert, verfügt in den Bereichen Verkauf, Support und Technik über das Fachwissen, das Sie benötigen, um Ihr Abonnement einzurichten und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="71b53-106">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription.</span></span> <span data-ttu-id="71b53-107">Sie können einen Abonnementberaterpartner als Datensatzpartner hinzufügen, wenn Sie Microsoft 365 oder zu einem anderen Zeitpunkt erwerben.</span><span class="sxs-lookup"><span data-stu-id="71b53-107">You can add a subscription advisor partner as a partner of record when you purchase Microsoft 365 or at another time.</span></span> <span data-ttu-id="71b53-108">Wenn Sie derzeit nicht mit einem Partner arbeiten, finden Sie diese auch auf der [Microsoft Pinpoint-Website.](https://pinpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="71b53-108">If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="71b53-109">[] Ein autorisierter Microsoft-Partner, der als Abonnementberater fungiert, verfügt in den Bereichen Verkauf, Support und Technik über das Fachwissen, das Sie benötigen, um Ihr Abonnement einzurichten und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="71b53-109">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription.</span></span> <span data-ttu-id="71b53-110">Sie können einen Abonnementberaterpartner beim Erwerb von Office 365 oder zu einem anderen Zeitpunkt als Partner of Record hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="71b53-110">You can add a subscription advisor partner as a partner of record when you purchase Office 365 or at another time.</span></span> <span data-ttu-id="71b53-111">Wenn Sie derzeit nicht mit einem Partner arbeiten, finden Sie diese auch auf der [Microsoft Pinpoint-Website.](https://pinpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="71b53-111">If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="71b53-112">Vorabinformationen</span><span class="sxs-lookup"><span data-stu-id="71b53-112">Before you begin</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="71b53-113">Der von Ihnen bzw. Ihnen Microsoft-Dienste Partner hängt von der von Ihnen verwendeten Umgebung und dem Land oder der Region ab, in dem Sie diese Dienste nutzen.</span><span class="sxs-lookup"><span data-stu-id="71b53-113">The partner you choose depends on the Microsoft services you use and the country or region where you'll use those services.</span></span> <span data-ttu-id="71b53-114">Wenn Sie einen Partner hinzufügen oder den Partner für Ihr Abonnement ändern, müssen Sie den Partner zuerst nach seiner Microsoft Partner-ID fragen.</span><span class="sxs-lookup"><span data-stu-id="71b53-114">If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="71b53-p105">Ihre Wahl des Partners ist von den von Ihnen verwendeten Office 365-Diensten sowie von dem Land oder der Region abhängig, in dem/der Sie die Dienste verwenden. Wenn Sie einen Partner hinzufügen oder den Partner für Ihr Abonnement ändern, müssen Sie den Partner zuerst nach seiner Microsoft Partner-ID fragen.</span><span class="sxs-lookup"><span data-stu-id="71b53-p105">The partner you choose depends on the Office 365 services you use and the country or region where you'll use those services. If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="71b53-117">Als Administrator für Office 365 können Sie u. a. Benutzer erstellen oder bearbeiten, Benutzerkennwörter zurücksetzen, Benutzerlizenzen verwalten, Domänen verwalten und anderen Benutzern in Ihrer Organisation Administratorberechtigungen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="71b53-117">As an admin for Office 365, you can create or edit users, reset user passwords, manage user licenses, manage domains, and assign admin permissions to other users in your organization, among other things.</span></span> <span data-ttu-id="71b53-118">Wenn Sie jedoch möchten, dass eine andere Person diese Administrativen Aufgaben ausführen soll, können Sie diese Rolle an einen autorisierten Partner von 21Vianet delegieren, indem Sie eine Partnerbeziehung erstellen.</span><span class="sxs-lookup"><span data-stu-id="71b53-118">However, if you want someone else to do these administrative tasks, you can delegate this role to an authorized partner of 21Vianet by creating a partner relationship.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="71b53-119">Hinzufügen eines Partners beim Erwerb</span><span class="sxs-lookup"><span data-stu-id="71b53-119">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="71b53-120">Wechseln Sie im Admin  Center zur Seite \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**Abrechnungskaufdienste.**</a></span><span class="sxs-lookup"><span data-stu-id="71b53-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**Purchase services**</a> page.</span></span>
2. <span data-ttu-id="71b53-121">Wählen Sie das Produkt aus, das Sie kaufen möchten, und wählen Sie dann **Kaufen aus.**</span><span class="sxs-lookup"><span data-stu-id="71b53-121">Select the product that you want to purchase, and then select **Buy**.</span></span>
3. <span data-ttu-id="71b53-122">Um einen neuen Partner hinzuzufügen, erweitern **Sie Hilfe bei Ihrer Bestellung benötigen?** und wählen Sie Unterstützung von einem Microsoft Partner erhalten **aus.**</span><span class="sxs-lookup"><span data-stu-id="71b53-122">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="71b53-123">Führen Sie die Schritte auf der Seite Anbieter aus, um nach einem Partner zu suchen oder einen Partner zu finden.</span><span class="sxs-lookup"><span data-stu-id="71b53-123">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
4. <span data-ttu-id="71b53-124">Wenn Sie bereits über einen Partner verfügen, wählen Sie im zweiten Schritt des Auscheck-Assistenten im rechten Bereich unter Partnerinformationen die Option **Hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="71b53-124">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>
5. <span data-ttu-id="71b53-p107">Geben Sie die Microsoft Partner-ID des Partners ein, den Sie hinzufügen. Sie können die entsprechende Microsoft Partner-ID erhalten, indem Sie den Partner danach fragen.</span><span class="sxs-lookup"><span data-stu-id="71b53-p107">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
6. <span data-ttu-id="71b53-127">Führen Sie die restlichen Schritte des Assistenten aus, um den Erwerb Ihrer Abonnements abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="71b53-127">Complete the rest of the wizard to finish buying your subscriptions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="71b53-128">Hinzufügen eines Partners beim Erwerb</span><span class="sxs-lookup"><span data-stu-id="71b53-128">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="71b53-129">Wechseln Sie [im Admin Center](https://go.microsoft.com/fwlink/p/?linkid=848041)zur Seite  \> **Abrechnungskaufdienste.**</span><span class="sxs-lookup"><span data-stu-id="71b53-129">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Billing** \> **Purchase services**  page.</span></span>
2. <span data-ttu-id="71b53-130">Wählen Sie das Produkt aus, das Sie kaufen möchten, und wählen Sie dann **Kaufen aus.**</span><span class="sxs-lookup"><span data-stu-id="71b53-130">Select the product that you want to purchase, and then select **Buy**.</span></span>
3. <span data-ttu-id="71b53-131">Um einen neuen Partner hinzuzufügen, erweitern **Sie Hilfe bei Ihrer Bestellung benötigen?** und wählen Sie Unterstützung von einem Microsoft Partner erhalten **aus.**</span><span class="sxs-lookup"><span data-stu-id="71b53-131">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="71b53-132">Führen Sie die Schritte auf der Seite Anbieter aus, um nach einem Partner zu suchen oder einen Partner zu finden.</span><span class="sxs-lookup"><span data-stu-id="71b53-132">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
4. <span data-ttu-id="71b53-133">Wenn Sie bereits über einen Partner verfügen, wählen Sie im zweiten Schritt des Auscheck-Assistenten im rechten Bereich unter Partnerinformationen die Option **Hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="71b53-133">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>
5. <span data-ttu-id="71b53-p108">Geben Sie die Microsoft Partner-ID des Partners ein, den Sie hinzufügen. Sie können die entsprechende Microsoft Partner-ID erhalten, indem Sie den Partner danach fragen.</span><span class="sxs-lookup"><span data-stu-id="71b53-p108">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
6. <span data-ttu-id="71b53-136">Führen Sie die restlichen Schritte des Assistenten aus, um den Erwerb Ihrer Abonnements abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="71b53-136">Complete the rest of the wizard to finish buying your subscriptions.</span></span>

::: moniker-end

## <a name="add-a-partner-to-an-existing-subscription"></a><span data-ttu-id="71b53-137">Hinzufügen eines Partners zu einem vorhandenen Abonnement</span><span class="sxs-lookup"><span data-stu-id="71b53-137">Add a partner to an existing subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="71b53-138">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="71b53-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="71b53-139">Wählen Sie **auf der** Registerkarte Produkte das Abonnement aus, das Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="71b53-139">On the **Products** tab, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="71b53-140">Geben Sie auf der Seite Abonnementdetails unter **Partnerinformationen** die **Partnernetzwerk-ID ein.**</span><span class="sxs-lookup"><span data-stu-id="71b53-140">On the subscription details page, under **Partner information**, type the **Partner Network ID**.</span></span> <span data-ttu-id="71b53-141">Sie können die Microsoft Partner Network ID des Partners erhalten, indem Sie den Partner dazu fragen.</span><span class="sxs-lookup"><span data-stu-id="71b53-141">You can get the partner's Microsoft Partner Network ID by asking the partner for it.</span></span>
4. <span data-ttu-id="71b53-142">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="71b53-142">Select **Add**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="71b53-143">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnements</a>.</span><span class="sxs-lookup"><span data-stu-id="71b53-143">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="71b53-144">Wenn Sie über mehr als ein Abonnement verfügen, wählen Sie das Abonnement aus, das Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="71b53-144">If you have more than one subscription, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="71b53-145">Wählen Sie auf der rechten Seite unter den Abonnementkosten die drei Punkte (weitere Aktionen) > Partner des **Datensatzes hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="71b53-145">On the right, under the subscription cost, select the three dots (more actions) > **Add partner of record**.</span></span>
4. <span data-ttu-id="71b53-p110">Geben Sie die Microsoft Partner-ID des Partners ein, den Sie hinzufügen, wählen Sie **ID überprüfen** und dann **Absenden** aus. Sie können die entsprechende Microsoft Partner-ID erhalten, indem Sie den Partner danach fragen.</span><span class="sxs-lookup"><span data-stu-id="71b53-p110">Type the Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
5. <span data-ttu-id="71b53-148">Die Partner-ID wird auf der Seite **Abonnements** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="71b53-148">The partner ID displays on the **Subscriptions** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="71b53-149">Dieser Prozess wird von Ihrem autorisierten Partner initiiert.</span><span class="sxs-lookup"><span data-stu-id="71b53-149">This process is initiated by your authorized partner.</span></span> <span data-ttu-id="71b53-150">Der Partner sendet Ihnen eine E-Mail, um Sie zu fragen, ob Sie ihm die Berechtigung zum Handeln als Datensatzpartner erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="71b53-150">The partner sends you an email to ask you if you want to give them permission to act as a partner of record.</span></span>
  
<span data-ttu-id="71b53-151">So akzeptieren Sie dieses Angebot</span><span class="sxs-lookup"><span data-stu-id="71b53-151">To accept this offer</span></span>
  
1. <span data-ttu-id="71b53-152">Lesen Sie die Bedingungen des Partners in der E-Mail.</span><span class="sxs-lookup"><span data-stu-id="71b53-152">Read the partner's terms in the email.</span></span>
2. <span data-ttu-id="71b53-153">Wählen Sie zum Autorisieren der Vereinbarung den Link aus, der zu einer Autorisierungsseite in Office 365.</span><span class="sxs-lookup"><span data-stu-id="71b53-153">To authorize the agreement, select the link, which goes to an authorization page in Office 365.</span></span>
3. <span data-ttu-id="71b53-154">Wählen **Sie unter Partnerbeziehungen** **Ja** aus, um den Partner als delegierten Administrator zu autorisieren, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="71b53-154">Under **Partner Relationships**, select **Yes** to authorize the partner to be your delegated admin, and then select **Next**.</span></span>
4. <span data-ttu-id="71b53-155">Wenn das Angebot für die Partnerbeziehung mit einem Testabonnement oder einem Kaufangebot kam, erstellen Sie Ihr Test- oder Abonnementkonto.</span><span class="sxs-lookup"><span data-stu-id="71b53-155">If the offer for partner relationship came with a trial subscription or a purchase offer, create your trial or subscription account.</span></span>

::: moniker-end

## <a name="change-the-partner-for-a-subscription"></a><span data-ttu-id="71b53-156">Ändern des Partners für ein Abonnement</span><span class="sxs-lookup"><span data-stu-id="71b53-156">Change the partner for a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="71b53-157">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="71b53-157">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="71b53-158">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="71b53-158">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="71b53-159">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="71b53-159">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end
2. <span data-ttu-id="71b53-160">Wählen Sie auf der Seite Abonnementsdetails unter **Partnerinformationen** die Option **Entfernen aus.**</span><span class="sxs-lookup"><span data-stu-id="71b53-160">On the subscriptions details page, under **Partner information**, select **Remove**.</span></span>
3. <span data-ttu-id="71b53-161">Geben Sie die **Microsoft Partner Network ID** für den neuen Partner ein.</span><span class="sxs-lookup"><span data-stu-id="71b53-161">Type the **Microsoft Partner Network ID** for the new partner.</span></span> <span data-ttu-id="71b53-162">Fragen Sie den Partner nach seiner Microsoft Partner-ID.</span><span class="sxs-lookup"><span data-stu-id="71b53-162">You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
4. <span data-ttu-id="71b53-163">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="71b53-163">Select **Add**.</span></span>
  
## <a name="view-your-partner-relationships"></a><span data-ttu-id="71b53-164">Anzeigen Ihrer Partnerbeziehungen</span><span class="sxs-lookup"><span data-stu-id="71b53-164">View your partner relationships</span></span>

- <span data-ttu-id="71b53-165">Wechseln Sie im Admin Center zur Seite **Einstellungen**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partnerbeziehungen.</a></span><span class="sxs-lookup"><span data-stu-id="71b53-165">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner relationships</a> page.</span></span> <span data-ttu-id="71b53-166">Ihre Partner sind auf dieser Seite aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="71b53-166">Your partners are listed on this page.</span></span>

  <span data-ttu-id="71b53-167">Wenn Sie keinen Partner haben, wird eine Meldung mit der Meldung "Hier ist nichts" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="71b53-167">If you don't have a partner, you'll see a message that says "There's nothing here."</span></span>
  
## <a name="delete-a-partner-from-a-subscription"></a><span data-ttu-id="71b53-168">Löschen eines Partners aus einem Abonnement</span><span class="sxs-lookup"><span data-stu-id="71b53-168">Delete a partner from a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="71b53-169">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="71b53-169">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="71b53-170">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="71b53-170">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="71b53-171">Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="71b53-171">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end
2. <span data-ttu-id="71b53-172">Wählen Sie **auf der** Registerkarte Produkte das Abonnement aus, das Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="71b53-172">On the **Products** tab, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="71b53-173">Wählen Sie auf der Seite Abonnementdetails unter **Partnerinformationen** die Option **Entfernen aus.**</span><span class="sxs-lookup"><span data-stu-id="71b53-173">On the subscription details page, under **Partner information**, select **Remove**.</span></span>

## <a name="remove-a-reseller-relationship"></a><span data-ttu-id="71b53-174">Entfernen einer Vertriebspartnerschaft</span><span class="sxs-lookup"><span data-stu-id="71b53-174">Remove a reseller relationship</span></span>

<span data-ttu-id="71b53-175">Händlerbeziehungen können Sie nicht selbst entfernen.</span><span class="sxs-lookup"><span data-stu-id="71b53-175">You can't remove a reseller relationship yourself.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="71b53-176">Wenn Sie eine Vertriebspartnerschaft entfernen, ist die Option Löschen ausgegraut, und Sie müssen Ihren Vertriebspartner bitten, die folgenden Anweisungen zu [befolgen:](/partner-center/remove-a-relationship)Entfernen einer Vertriebspartnerschaft mit partner . </span><span class="sxs-lookup"><span data-stu-id="71b53-176">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>

::: moniker-end

::: moniker range="o365-germany"
  
<span data-ttu-id="71b53-177">Wenn Sie eine Vertriebspartnerschaft entfernen, ist die Option Löschen ausgegraut, und Sie müssen Ihren Vertriebspartner bitten, die folgenden Anweisungen zu [befolgen:](/partner-center/remove-a-relationship)Entfernen einer Vertriebspartnerschaft mit partner . </span><span class="sxs-lookup"><span data-stu-id="71b53-177">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

::: moniker range="o365-21vianet"
  
<span data-ttu-id="71b53-178">Sie müssen Ihren Vertriebspartner bitten, die folgenden Anweisungen zu befolgen: [Entfernen einer Vertriebspartnerschaft mit partner](/partner-center/remove-a-relationship).</span><span class="sxs-lookup"><span data-stu-id="71b53-178">You will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

## <a name="related-content"></a><span data-ttu-id="71b53-179">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="71b53-179">Related content</span></span>

<span data-ttu-id="71b53-180">[Suchen Sie Microsoft 365 Partner oder Händler](../manage/find-your-partner-or-reseller.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="71b53-180">[Find your Microsoft 365 partner or reseller](../manage/find-your-partner-or-reseller.md) (article)</span></span>\
<span data-ttu-id="71b53-181">[Planen der Einrichtung von Microsoft 365 business](../setup/plan-your-setup.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="71b53-181">[Plan your setup of Microsoft 365 for business](../setup/plan-your-setup.md) (article)</span></span>
---
title: Verwalten von Software-as-a-Service-Apps für Ihre Organisation
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
search.appverid: MET150
description: Informationen zum Aktivieren und Verwalten von Drittanbieter-apps im Microsoft 365 Admin Center.
ms.openlocfilehash: eb2826a4b0c69d61eb35a9dfff37e9dc2dd6ad71
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141188"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="91d88-103">Verwalten von Drittanbieter-App-Abonnements für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="91d88-103">Manage third-party app subscriptions for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="91d88-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="91d88-104">The admin center is changing.</span></span> <span data-ttu-id="91d88-105">Wenn Ihre Erfahrung nicht mit den hier dargestellten Details übereinstimmt, lesen Sie [Informationen zum neuen Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="91d88-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="91d88-106">Sie können Lizenzen und Abrechnung für Drittanbieter-apps im Microsoft 365 Admin Center mit aktiviertem Vorschaumodus verwalten.</span><span class="sxs-lookup"><span data-stu-id="91d88-106">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="91d88-107">Zu den aktualisierten Features gehören eine erweiterte Abonnementverwaltung, ein verbesserter Zugriff auf Abrechnungsinformationen sowie eine verbesserte Flexibilität bei der Verwaltung von Rechnungen.</span><span class="sxs-lookup"><span data-stu-id="91d88-107">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="91d88-108">Die Abonnementverwaltung basiert auf der aktualisierten Commerce-Plattform von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91d88-108">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="91d88-109">Dies gilt für Software-as-a-Service-apps, die Kunden direkt kaufen oder von einem Drittanbieter.</span><span class="sxs-lookup"><span data-stu-id="91d88-109">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="91d88-110">So erhalten Sie Software-as-a-Service-apps</span><span class="sxs-lookup"><span data-stu-id="91d88-110">How to get software-as-a-service apps</span></span>

<span data-ttu-id="91d88-111">Es gibt einige Möglichkeiten, Apps von Drittanbietern zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="91d88-111">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="91d88-112">**Direkterwerb** – Kunden können direkt Abonnements von [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)oder [AppSource](https://www.appsource.com/)kaufen.</span><span class="sxs-lookup"><span data-stu-id="91d88-112">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="91d88-113">**Partner Einkauf** – arbeiten Sie mit einem Partner über das Partner Center zusammen, um Abonnements zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="91d88-113">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="91d88-114">**Microsoft Proposal** – reagieren Sie auf einen Vorschlag von Microsoft Sales, der apps von Drittanbietern enthält.</span><span class="sxs-lookup"><span data-stu-id="91d88-114">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="91d88-115">Sobald Kunden die apps kaufen und die Microsoft-Kundenvereinbarung akzeptieren, können Sie diese im Microsoft 365 Admin Center oder im Microsoft Store for Business verwalten.</span><span class="sxs-lookup"><span data-stu-id="91d88-115">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="91d88-116">App-Anbieter verkaufen Ihre apps entweder pauschal oder durch den Erwerb von Lizenzen für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="91d88-116">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="91d88-117">**Flat Rate** – auch als Website basierte Preisgestaltung bezeichnet-apps werden mit einem monatlichen oder jährlichen Preis bewertet.</span><span class="sxs-lookup"><span data-stu-id="91d88-117">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="91d88-118">Auf der APP-Seite wird die Lizenzmenge unbegrenzt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="91d88-118">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="91d88-119">**Lizenzen** – apps werden nach lizenzpreisen angeboten.</span><span class="sxs-lookup"><span data-stu-id="91d88-119">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="91d88-120">Kunden weisen jedem Benutzer in seiner Organisation Lizenzen zu</span><span class="sxs-lookup"><span data-stu-id="91d88-120">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="91d88-121">Unterstützte Regionen</span><span class="sxs-lookup"><span data-stu-id="91d88-121">Supported regions</span></span>

<span data-ttu-id="91d88-122">Unterstützung für Drittanbieter-Apps ist in diesen Regionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="91d88-122">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="91d88-123">Argentinien</span><span class="sxs-lookup"><span data-stu-id="91d88-123">Argentina</span></span>
- <span data-ttu-id="91d88-124">Australien</span><span class="sxs-lookup"><span data-stu-id="91d88-124">Australia</span></span>
- <span data-ttu-id="91d88-125">Kanada</span><span class="sxs-lookup"><span data-stu-id="91d88-125">Canada</span></span>
- <span data-ttu-id="91d88-126">Chile</span><span class="sxs-lookup"><span data-stu-id="91d88-126">Chile</span></span>
- <span data-ttu-id="91d88-127">Frankreich</span><span class="sxs-lookup"><span data-stu-id="91d88-127">France</span></span>
- <span data-ttu-id="91d88-128">Deutschland</span><span class="sxs-lookup"><span data-stu-id="91d88-128">Germany</span></span>
- <span data-ttu-id="91d88-129">Griechenland</span><span class="sxs-lookup"><span data-stu-id="91d88-129">Greece</span></span>
- <span data-ttu-id="91d88-130">Puerto Rico</span><span class="sxs-lookup"><span data-stu-id="91d88-130">Puerto Rico</span></span>
- <span data-ttu-id="91d88-131">Südafrika</span><span class="sxs-lookup"><span data-stu-id="91d88-131">South Africa</span></span>
- <span data-ttu-id="91d88-132">Vereinigtes Königreich</span><span class="sxs-lookup"><span data-stu-id="91d88-132">United Kingdom</span></span>
- <span data-ttu-id="91d88-133">Vereinigte Staaten</span><span class="sxs-lookup"><span data-stu-id="91d88-133">United States</span></span>
- <span data-ttu-id="91d88-134">Westeuropa</span><span class="sxs-lookup"><span data-stu-id="91d88-134">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="91d88-135">Aktivieren von Drittanbieter-apps</span><span class="sxs-lookup"><span data-stu-id="91d88-135">Activate third-party apps</span></span>

<span data-ttu-id="91d88-136">Administratoren müssen apps von Drittanbietern aktivieren, bevor Sie Sie Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="91d88-136">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="91d88-137">Diese apps werden im Portal des Drittanbieters des Herausgebers aktiviert.</span><span class="sxs-lookup"><span data-stu-id="91d88-137">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="91d88-138">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > **Produkte** > -<a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">apps</a> .</span><span class="sxs-lookup"><span data-stu-id="91d88-138">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91d88-139">Suchen Sie die APP, die Sie verwalten möchten, und wählen Sie Sie aus.</span><span class="sxs-lookup"><span data-stu-id="91d88-139">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91d88-140">Wählen Sie unter **Einstellungen & Aktionen** **die Option im Portal des Herausgebers verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="91d88-140">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="91d88-141">Sie werden zur Website des App-Herausgebers weitergeleitet, auf der Sie die APP aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="91d88-141">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="91d88-142">Apps von Drittanbietern verwalten</span><span class="sxs-lookup"><span data-stu-id="91d88-142">Manage third-party apps</span></span>

<span data-ttu-id="91d88-143">Administratoren verwalten Drittanbieter-apps an zwei Standorten: Microsoft 365 Admin Center und das Portal des Drittanbieter-App-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="91d88-143">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="91d88-144">Hier sehen Sie, was Sie in jedem Portal tun können.</span><span class="sxs-lookup"><span data-stu-id="91d88-144">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="91d88-145">Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="91d88-145">Microsoft 365 admin center</span></span> | <span data-ttu-id="91d88-146">App-Publisher-Portal</span><span class="sxs-lookup"><span data-stu-id="91d88-146">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="91d88-147">Lizenzmenge ändern</span><span class="sxs-lookup"><span data-stu-id="91d88-147">Change license quantity</span></span> <br> <span data-ttu-id="91d88-148">Verwalten der Bezahlung Ihrer Rechnung</span><span class="sxs-lookup"><span data-stu-id="91d88-148">Manage how you pay your bill</span></span> <br> <span data-ttu-id="91d88-149">Verwalten der Bezahlung Ihrer Rechnung</span><span class="sxs-lookup"><span data-stu-id="91d88-149">Manage how you pay your bill</span></span> <br> <span data-ttu-id="91d88-150">Zahlungsmethode ändern (Kreditkarte)</span><span class="sxs-lookup"><span data-stu-id="91d88-150">Change payment method (credit card)</span></span> <br> <span data-ttu-id="91d88-151">Rechnung anzeigen</span><span class="sxs-lookup"><span data-stu-id="91d88-151">View invoice</span></span> <br> <span data-ttu-id="91d88-152">App-Abonnement kündigen</span><span class="sxs-lookup"><span data-stu-id="91d88-152">Cancel app subscription</span></span> | <span data-ttu-id="91d88-153">Einrichten der APP (einmal für jede APP)</span><span class="sxs-lookup"><span data-stu-id="91d88-153">Set up app (once for each app)</span></span> <br> <span data-ttu-id="91d88-154">Zuweisen von Lizenzen an Benutzer</span><span class="sxs-lookup"><span data-stu-id="91d88-154">Assign licenses to users</span></span> <br> <span data-ttu-id="91d88-155">Technischer Support</span><span class="sxs-lookup"><span data-stu-id="91d88-155">Technical support</span></span> |

<span data-ttu-id="91d88-156">Nachdem die App aktiviert wurde, bleibt sie aktiv, es sei denn, Sie wird abgebrochen, läuft ab oder wenn die Zahlung nicht aktuell gehalten wird.</span><span class="sxs-lookup"><span data-stu-id="91d88-156">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="91d88-157">Diese Ereignisse ändern den App-Status in "deaktiviert".</span><span class="sxs-lookup"><span data-stu-id="91d88-157">These events change the app status to disabled.</span></span> <span data-ttu-id="91d88-158">Wenn eine APP deaktiviert ist, kann Sie nicht erneut aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="91d88-158">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="91d88-159">Um die APP weiterhin zu verwenden, kaufen Sie eine weitere Kopie davon.</span><span class="sxs-lookup"><span data-stu-id="91d88-159">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="91d88-160">Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="91d88-160">Assign licenses</span></span>

<span data-ttu-id="91d88-161">Administratoren müssen apps von Drittanbietern aktivieren, bevor Sie Sie Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="91d88-161">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="91d88-162">Sie werden im Portal des Drittanbieters des Herausgebers aktiviert.</span><span class="sxs-lookup"><span data-stu-id="91d88-162">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="91d88-163">Wählen Sie auf der Seite app unter **Einstellungen & Aktionen**den Link zum Zuweisen von Lizenzen aus.</span><span class="sxs-lookup"><span data-stu-id="91d88-163">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="91d88-164">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > **Produkte** > -<a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">apps</a> .</span><span class="sxs-lookup"><span data-stu-id="91d88-164">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91d88-165">Suchen Sie die APP, die Sie verwalten möchten, und wählen Sie Sie aus.</span><span class="sxs-lookup"><span data-stu-id="91d88-165">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91d88-166">Wählen Sie unter **Einstellungen & Aktionen**den Link aus, der **im Portal von Publisher verwaltet**werden soll.</span><span class="sxs-lookup"><span data-stu-id="91d88-166">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="91d88-167">Lizenzmenge ändern</span><span class="sxs-lookup"><span data-stu-id="91d88-167">Change license quantity</span></span>

<span data-ttu-id="91d88-168">Administratoren können die Anzahl der Lizenzen ändern, die Ihrer Organisation gehören.</span><span class="sxs-lookup"><span data-stu-id="91d88-168">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="91d88-169">Dies gilt nur für apps, die mit Sitz basierter Preisgestaltung erworben wurden.</span><span class="sxs-lookup"><span data-stu-id="91d88-169">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="91d88-170">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > **Produkte** > -<a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">apps</a> .</span><span class="sxs-lookup"><span data-stu-id="91d88-170">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91d88-171">Suchen Sie die APP, die Sie verwalten möchten, und wählen Sie Sie aus.</span><span class="sxs-lookup"><span data-stu-id="91d88-171">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91d88-172">Wählen Sie **Lizenzmenge ändern**aus.</span><span class="sxs-lookup"><span data-stu-id="91d88-172">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="91d88-173">Verwalten von Zahlungsmethoden</span><span class="sxs-lookup"><span data-stu-id="91d88-173">Manage payment methods</span></span>

<span data-ttu-id="91d88-174">Software-as-a-Service-apps haben jeweils ein Abrechnungsprofil zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="91d88-174">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="91d88-175">Mit Abrechnungs Profilen können Sie anpassen, welche Produkte auf Ihrer Rechnung enthalten sind und wie Sie Ihre Rechnungen bezahlen.</span><span class="sxs-lookup"><span data-stu-id="91d88-175">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="91d88-176">Hierzu zählen unter anderem folgende bewährte Methoden:</span><span class="sxs-lookup"><span data-stu-id="91d88-176">They include:</span></span>

- <span data-ttu-id="91d88-177">**Zahlungsmethoden** – Kreditkarten oder Schecks/Überweisungen</span><span class="sxs-lookup"><span data-stu-id="91d88-177">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="91d88-178">**Kontaktinformationen** – Rechnungsadresse und Kontakt Name</span><span class="sxs-lookup"><span data-stu-id="91d88-178">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="91d88-179">**Rollen** – Rollen, mit denen Sie das Abrechnungsprofil ändern, Rechnungen bezahlen oder die Zahlungsmethode für das Abrechnungsprofil verwenden können, um den Erwerb zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="91d88-179">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="91d88-180">Weitere Informationen zu Abrechnungs Profilen finden Sie unter [Understanding Billing Profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span><span class="sxs-lookup"><span data-stu-id="91d88-180">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="91d88-181">Ändern des Abrechnungs Profils für ein Software-as-a-Service-APP-Abonnement</span><span class="sxs-lookup"><span data-stu-id="91d88-181">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="91d88-182">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > **Produkte** > -<a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">apps</a> .</span><span class="sxs-lookup"><span data-stu-id="91d88-182">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91d88-183">Suchen Sie die APP, die Sie verwalten möchten, und wählen Sie Sie aus.</span><span class="sxs-lookup"><span data-stu-id="91d88-183">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91d88-184">Wählen Sie neben **Abrechnungsprofil**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="91d88-184">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="91d88-185">Weitere Informationen zu Rechnungen finden Sie Untergrund [Legendes zu Ihrer Rechnung](billing-and-payments/understand-your-invoice.md).</span><span class="sxs-lookup"><span data-stu-id="91d88-185">For more information on invoices, see [Understand your invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="91d88-186">Abbrechen eines Software-as-a-Service-APP-Abonnements</span><span class="sxs-lookup"><span data-stu-id="91d88-186">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="91d88-187">Sie können eine Software-as-a-Service-APP von der APP-Seite abbrechen.</span><span class="sxs-lookup"><span data-stu-id="91d88-187">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="91d88-188">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > **Produkte** > -<a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">apps</a> .</span><span class="sxs-lookup"><span data-stu-id="91d88-188">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="91d88-189">Suchen Sie die APP, die Sie verwalten möchten, und wählen Sie Sie aus.</span><span class="sxs-lookup"><span data-stu-id="91d88-189">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="91d88-190">Wählen Sie unter **Einstellungen & Aktionen**die Option **Abonnement kündigen**aus.</span><span class="sxs-lookup"><span data-stu-id="91d88-190">Under **Settings & actions**, select **Cancel subscription**.</span></span>

---
title: Verwalten von Zahlungsmethoden
f1.keywords:
- CSH
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
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Erfahren Sie, wie Sie Ihre Zahlungsmethoden im Microsoft 365 Admin Center verwalten.
ms.openlocfilehash: 0320f71180a5c2c127217ebf01854943409e6386
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403678"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="fc1d3-103">Verwalten von Zahlungsmethoden</span><span class="sxs-lookup"><span data-stu-id="fc1d3-103">Manage payment methods</span></span>

::: moniker range="o365-21vianet"
> [!NOTE]
> <span data-ttu-id="fc1d3-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-104">The admin center is changing.</span></span> <span data-ttu-id="fc1d3-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="fc1d3-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>
::: moniker-end

<span data-ttu-id="fc1d3-106">Wenn Sie Geschäftsprodukte oder-Dienste von Microsoft kaufen, können Sie eine vorhandene Zahlungsmethode verwenden oder einen neuen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="fc1d3-107">Sie können eine Kredit-oder Debitkarte oder ein Bankkonto verwenden, um die von Ihnen erworbenen Dinge zu bezahlen.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="fc1d3-108">Wenn Ihr Geschäftskonto über ein Abrechnungsprofil verfügt und Sie ein Abrechnungsprofil Besitzer oder ein Abrechnungsprofil Mitwirkender sind, können Sie das Abrechnungsprofil verwenden, das von einer Kreditkarte oder einer Rechnungszahlung unterstützt wird, um Einkäufe zu tätigen oder Rechnungen zu bezahlen.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="fc1d3-109">Wenn Sie Rechnungs Rechnungs-Manager sind, können Sie nur ein Abrechnungsprofil verwenden, um Rechnungen zu bezahlen.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="fc1d3-110">Weitere Informationen zu Abrechnungs Profilen und Rollen finden Sie unter [Verwalten von Abrechnungs Profilen](manage-billing-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="fc1d3-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="fc1d3-111">Wenn Ihr Geschäftskonto nicht über ein Abrechnungsprofil verfügt, kann ein globaler oder abrechnungsadministrator alle Bankkonten verwalten und verwenden, die dem Geschäftskonto hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-111">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account.</span></span> <span data-ttu-id="fc1d3-112">Sie können jedoch nur Kreditkarten verwalten oder verwenden, die Sie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-112">However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="fc1d3-113">Die Option zur Zahlung mit einem Bankkonto steht in einigen Ländern oder Regionen nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="fc1d3-114">Sie müssen eine Zahlungsmethode verwenden, die aus demselben Land wie Ihr Mandant ausgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="fc1d3-115">Zahlungsmethode hinzufügen</span><span class="sxs-lookup"><span data-stu-id="fc1d3-115">Add a payment method</span></span>

<span data-ttu-id="fc1d3-116">Durch das Hinzufügen einer Zahlungsmethode werden keine Abonnements zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-116">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="fc1d3-117">Informationen zum Zuweisen eines einzelnen Abonnements zur Zahlungsmethode finden Sie unter [Ändern einer Zahlungsmethode für ein einzelnes Abonnement](#change-a-payment-method-for-a-single-subscription).</span><span class="sxs-lookup"><span data-stu-id="fc1d3-117">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="fc1d3-118">Informationen zum Ersetzen aller Abonnements, die eine andere Zahlungsmethode mit der neuen Zahlung verwenden, finden Sie unter [Replace a Payment Method](#replace-a-payment-method).</span><span class="sxs-lookup"><span data-stu-id="fc1d3-118">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="fc1d3-119">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-119">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="fc1d3-120">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-120">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="fc1d3-121">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-121">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="fc1d3-122">Wählen Sie **Zahlungsmethode hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-122">Select **Add a payment method**.</span></span>

3. <span data-ttu-id="fc1d3-123">Wählen Sie auf der Seite **Zahlungsmethoden** im Dropdownmenü eine Zahlungsmethode aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-123">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>

4. <span data-ttu-id="fc1d3-124">Geben Sie die Informationen für das neue Kreditkarten-oder Bank Konto ein, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-124">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="fc1d3-125">Zahlungsmethodendetails aktualisieren</span><span class="sxs-lookup"><span data-stu-id="fc1d3-125">Update payment method details</span></span>

<span data-ttu-id="fc1d3-126">Sie können den Namen auf der Kredit-oder Debitkarte, der Rechnungsadresse oder dem Ablaufdatum für eine vorhandene Zahlungsmethode ändern.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-126">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="fc1d3-127">Sie können die Karten-oder Kontonummer jedoch nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-127">However, you can't change the card or account number.</span></span> <span data-ttu-id="fc1d3-128">Wenn sich die Kontonummer geändert hat, [Ersetzen Sie Sie durch eine andere Zahlungsmethode](#replace-a-payment-method), und [Löschen Sie die alte](#delete-a-payment-method).</span><span class="sxs-lookup"><span data-stu-id="fc1d3-128">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="fc1d3-129">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-129">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="fc1d3-130">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-130">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="fc1d3-131">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-131">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="fc1d3-132">Wählen Sie die Zeile der Zahlungsmethode aus, die aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-132">Select the row of the payment method to update.</span></span> <span data-ttu-id="fc1d3-133">Wählen Sie im rechten Bereich die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-133">In the right pane, select **Edit**.</span></span>

3. <span data-ttu-id="fc1d3-134">Aktualisieren Sie Ihre Angaben zur Zahlungsmethode, einschließlich des Namens auf der Kredit- oder Debitkarte, der Rechnungsadresse oder des Ablaufdatums, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-134">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="fc1d3-135">Ersetzen einer Zahlungsmethode</span><span class="sxs-lookup"><span data-stu-id="fc1d3-135">Replace a payment method</span></span>

<span data-ttu-id="fc1d3-136">Wenn Sie eine Zahlungsmethode ersetzen, ersetzen Sie Sie für alle Abonnements und Abrechnungsprofile, die dieselbe Zahlungsmethode verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-136">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="fc1d3-137">Wenn Sie eine Zahlungsmethode ersetzen, wird die vorhandene Zahlungsmethode nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-137">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="fc1d3-138">Es steht Ihnen weiterhin zur Auswahl und Verwendung für andere Abonnements und Abrechnungsprofile zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-138">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="fc1d3-139">Informationen zum Ändern der Zahlungsmethode für ein einzelnes Abonnement finden Sie unter [Ändern einer Zahlungsmethode für ein einzelnes Abonnement](#change-a-payment-method-for-a-single-subscription).</span><span class="sxs-lookup"><span data-stu-id="fc1d3-139">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="fc1d3-140">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-140">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="fc1d3-141">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-141">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="fc1d3-142">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-142">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="fc1d3-143">Wählen Sie die Zeile der Zahlungsmethode aus, die ersetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-143">Select the row of the payment method to replace.</span></span> <span data-ttu-id="fc1d3-144">Im rechten Bereich werden alle Abrechnungsprofile und einzelne Abonnements mit der ausgewählten Zahlungsmethode aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-144">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>

3. <span data-ttu-id="fc1d3-145">Wählen Sie im rechten Bereich **Zahlungsmethode für alle Elemente ersetzen** aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-145">In the right pane, select **Replace payment method for all items**.</span></span>

4. <span data-ttu-id="fc1d3-146">Wenn Sie eine vorhandene Zahlungsmethode verwenden möchten, wählen Sie in der Dropdownliste eine aus und wählen Sie dann **Ersetzen**.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-146">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="fc1d3-147">Wenn Sie Abonnements haben, die mit einem Abrechnungsprofil verknüpft sind, können Sie diese nur mit einer Kredit- oder Debitkarte bezahlen.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-147">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="fc1d3-148">Wenn Sie auf der Seite **Zahlungsmethoden** Bankkonten aufgelistet haben, können diese in der Dropdownliste nicht ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-148">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>

5. <span data-ttu-id="fc1d3-149">Wenn Sie eine neue Zahlungsmethode hinzufügen möchten, wählen Sie **Zahlungsmethode hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-149">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="fc1d3-150">Geben Sie im Bereich **Zahlungsmethode hinzufügen** die Kontoinformationen ein und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-150">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="fc1d3-151">Sie müssen eine Zahlungsmethode aus dem gleichen Land wie Ihr Mandant verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-151">You must use a payment method from the same country as your tenant.</span></span>

7. <span data-ttu-id="fc1d3-152">Die neue Zahlungsmethode ist bereits in der Dropdownliste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-152">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="fc1d3-153">Wählen Sie **Ersetzen**.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-153">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="fc1d3-154">Ändern einer Zahlungsmethode für ein einzelnes Abonnement</span><span class="sxs-lookup"><span data-stu-id="fc1d3-154">Change a payment method for a single subscription</span></span>

<span data-ttu-id="fc1d3-155">Sie können die Zahlungsmethode ändern, die für das bezahlen eines einzelnen Abonnements verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-155">You can change the payment method used to pay for a single subscription.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="fc1d3-156">Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="fc1d3-157">Navigieren Sie im Admin Center zur Seite **Abrechnung** > **Ihre Produkte**.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-157">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="fc1d3-158">Navigieren Sie im Admin Center zur Seite **Abrechnung** > **Ihre Produkte**.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-158">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

2. <span data-ttu-id="fc1d3-159">Wählen Sie auf der Registerkarte **Abonnements** das Abonnement aus, für das Sie mit der alternativen Zahlungsmethode bezahlen möchten.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-159">On the **Subscriptions** tab, select the subscription that you want to pay for with the alternate payment method.</span></span>

3. <span data-ttu-id="fc1d3-160">Wählen Sie unter **Abrechnung**neben der Zahlungsmethode die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-160">Under **Billing**, next to the payment method, select **Edit**.</span></span>

4. <span data-ttu-id="fc1d3-161">Wählen Sie neben der vorhandenen Zahlungsmethode die Option **Change**aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-161">Next to your existing payment method, select **Change**.</span></span>

5. <span data-ttu-id="fc1d3-162">Wählen Sie in der Dropdownliste eine alternative Zahlungsmethode aus, oder wählen Sie aus, um eine Zahlungsmethode hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-162">From the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>

6. <span data-ttu-id="fc1d3-163">Wenn Sie eine Zahlungsmethode hinzufügen, geben Sie die Karten-oder Kontodetails ein, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-163">If you add a payment method, enter the card or account details, then select **Save**.</span></span>

7. <span data-ttu-id="fc1d3-164">Stellen Sie sicher, dass die ausgewählte Zahlungsmethode richtig ist, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-164">Verify that the selected payment method is correct, then select **Save**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="fc1d3-165">Löschen einer Zahlungsmethode</span><span class="sxs-lookup"><span data-stu-id="fc1d3-165">Delete a payment method</span></span>

<span data-ttu-id="fc1d3-166">Sie können nur eine Zahlungsmethode löschen, die nicht an ein Abonnement oder ein Abrechnungsprofil angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-166">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="fc1d3-167">Dies gilt für alle Abonnements unabhängig von Ihrem Status.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-167">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="fc1d3-168">Löschen einer Zahlungsmethode ohne zugeordnete Abonnements oder Abrechnungsprofile</span><span class="sxs-lookup"><span data-stu-id="fc1d3-168">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="fc1d3-169">Wenn eine Zahlungsmethode keinem Abonnement oder Abrechnungsprofil zugeordnet ist, können Sie Sie sofort löschen.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-169">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="fc1d3-170">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-170">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="fc1d3-171">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-171">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="fc1d3-172">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-172">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="fc1d3-173">Suchen Sie die zu löschende Zahlungsmethode, wählen Sie die drei Punkte aus, und wählen Sie dann **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-173">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>

3. <span data-ttu-id="fc1d3-174">Wählen Sie unten im rechten Bereich **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-174">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="fc1d3-175">Löschen einer Zahlungsmethode mit angefügten Abonnements oder Abrechnungs Profilen</span><span class="sxs-lookup"><span data-stu-id="fc1d3-175">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="fc1d3-176">Wenn eine Zahlungsmethode an alle Abonnements oder Abrechnungsprofile angehängt ist, ersetzen Sie Sie zunächst durch eine vorhandene Zahlungsmethode, oder fügen Sie eine neue Zahlung hinzu, und löschen Sie dann die alte Zahlungsmethode.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-176">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="fc1d3-177">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-177">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="fc1d3-178">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-178">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="fc1d3-179">Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .</span><span class="sxs-lookup"><span data-stu-id="fc1d3-179">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="fc1d3-180">Wählen Sie die Zeile für die zu löschende Zahlungsmethode aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-180">Select the row for the payment method to delete.</span></span> <span data-ttu-id="fc1d3-181">Im rechten Bereich werden vorhandene Abonnements aufgelistet, die diese Zahlungsmethode verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-181">The right pane lists existing subscriptions that use that payment method.</span></span>

3. <span data-ttu-id="fc1d3-182">Wählen Sie im rechten Bereich **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-182">In the right pane, select **Delete**.</span></span>

4. <span data-ttu-id="fc1d3-183">Um eine vorhandene Zahlungsmethode zu verwenden, wählen Sie eine aus der Dropdownliste aus, wählen Sie dann **weiter**aus, und wählen Sie dann **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-183">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="fc1d3-184">Wenn Sie einem Abrechnungsprofil Abonnements zugeordnet haben, können Sie diese nur mit einer Kreditkarte bezahlen.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-184">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="fc1d3-185">Wenn auf der Seite **Zahlungsmethoden** Bankkonten aufgeführt sind, stehen Sie in der Dropdownliste nicht zur Auswahl.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-185">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>

5. <span data-ttu-id="fc1d3-186">Wenn Sie eine neue Zahlungsmethode hinzufügen möchten, wählen Sie **Zahlungsmethode hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-186">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="fc1d3-187">Wählen Sie den Typ der Zahlungsmethode aus, den Sie hinzufügen möchten, geben Sie die Kontoinformationen ein, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-187">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>

7. <span data-ttu-id="fc1d3-188">Die neue Zahlungsmethode ist bereits in der Dropdownliste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-188">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="fc1d3-189">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-189">Select **Next**.</span></span>

8. <span data-ttu-id="fc1d3-190">Wählen Sie **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-190">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="fc1d3-191">Behandlung von Problemen mit Zahlungsmethoden</span><span class="sxs-lookup"><span data-stu-id="fc1d3-191">Troubleshoot payment methods</span></span>

|<span data-ttu-id="fc1d3-192">**Problem**</span><span class="sxs-lookup"><span data-stu-id="fc1d3-192">**Issue**</span></span>|<span data-ttu-id="fc1d3-193">**Schritte zur Problembehandlung**</span><span class="sxs-lookup"><span data-stu-id="fc1d3-193">**Troubleshooting steps**</span></span>|
|:----------|:-----|
|<span data-ttu-id="fc1d3-194">**Ich erhalte eine Fehlermeldung mit dem Hinweis "der Browser ist derzeit auf Cookies blockieren" festgelegt.**</span><span class="sxs-lookup"><span data-stu-id="fc1d3-194">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="fc1d3-195">Konfigurieren Sie Ihren Browser so, dass er Cookies von Drittanbietern zulässt, und versuchen Sie es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-195">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="fc1d3-196">**Meine Kreditkarte oder Debitkarte wurde abgelehnt.**</span><span class="sxs-lookup"><span data-stu-id="fc1d3-196">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="fc1d3-197">Wenn Sie per Kreditkarte oder Debitkarte bezahlen und Ihre Karte abgelehnt wird, erhalten Sie eine e-Mail, die besagt, dass Microsoft die Zahlung nicht verarbeiten konnte.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-197">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="fc1d3-198">Stellen Sie sicher, dass die Karten &mdash; Nummer, das Ablaufdatum, der Name auf der Karte und die Adresse, einschließlich Stadt, Bundesland und Postleitzahl &mdash; genau so angezeigt werden, wie auf der Karte und ihrer Erklärung.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-198">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="fc1d3-199">Sie können Ihre Karteninformationen aktualisieren und die Zahlung sofort über den Link **Ausgleichs Saldo** im Abschnitt **Abrechnung** auf der Seite Abonnementdetails übermitteln.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-199">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="fc1d3-200">Weitere Informationen finden Sie unter [Was passiert, wenn meine Kreditkarte abgelehnt wurde und meine Zahlung überfällig ist?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span><span class="sxs-lookup"><span data-stu-id="fc1d3-200">For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span></span>  <br/><br/>  <span data-ttu-id="fc1d3-201">Wenn die Kreditkarte dann immer noch abgelehnt wird, wenden Sie sich an Ihre Bank.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-201">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="fc1d3-202">Es ist möglich, dass Ihre Karte nicht aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-202">It's possible that your card isn't active.</span></span> <span data-ttu-id="fc1d3-203">Wenn Sie die Karte kürzlich in der e-Mail mit einem aktualisierten Ablaufdatum erhalten haben, stellen Sie sicher, dass Sie aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-203">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="fc1d3-204">Ihre Bank kann Ihnen auch mitteilen, ob Ihre Karte nicht für Online-, internationale oder wiederkehrende Transaktionen genehmigt wurde.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-204">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="fc1d3-205">**Ich möchte eine Karten-oder Bank Kontonummer aktualisieren.**</span><span class="sxs-lookup"><span data-stu-id="fc1d3-205">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="fc1d3-206">Sie können die Karten-oder Kontonummer für eine vorhandene Zahlungsmethode nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-206">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="fc1d3-207">Wenn sich Ihre Karte oder Kontonummer geändert hat, [Ersetzen Sie Sie durch eine andere Zahlungsmethode](#replace-a-payment-method), die alle aktiven Abonnements von der Zahlungsmethode in die neue verlagert und dann [die alte Zahlungsmethode löscht](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span><span class="sxs-lookup"><span data-stu-id="fc1d3-207">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="fc1d3-208">**Ich habe nur eine Karte oder ein Bankkonto in meinem Konto und möchte es entfernen.**</span><span class="sxs-lookup"><span data-stu-id="fc1d3-208">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="fc1d3-209">Wenn Sie nur über eine Zahlungsmethode verfügen, müssen Sie Sie [durch eine neue Zahlungsmethode ersetzen](#replace-a-payment-method) , bevor Sie Sie löschen können.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-209">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="fc1d3-210">**Meine Karte oder Ihr Bankkonto kann nicht hinzugefügt werden.**</span><span class="sxs-lookup"><span data-stu-id="fc1d3-210">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="fc1d3-211">Sie müssen eine Zahlungsmethode verwenden, die aus demselben Land wie Ihr Mandant ausgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-211">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="fc1d3-212">Wenn Sie Probleme bei der Eingabe Ihrer Kreditkarten-oder Bankkontoinformationen haben, können Sie [sich an den Support wenden](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="fc1d3-212">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-articles"></a><span data-ttu-id="fc1d3-213">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="fc1d3-213">Related articles</span></span>

[<span data-ttu-id="fc1d3-214">Bezahlen Ihres Geschäfts Abonnements</span><span class="sxs-lookup"><span data-stu-id="fc1d3-214">Pay for your business subscription</span></span>](pay-for-your-subscription.md)

[<span data-ttu-id="fc1d3-215">Verwalten von Abrechnungsprofilen</span><span class="sxs-lookup"><span data-stu-id="fc1d3-215">Manage billing profiles</span></span>](manage-billing-profiles.md)

[<span data-ttu-id="fc1d3-216">Ändern der Zahlungshäufigkeit</span><span class="sxs-lookup"><span data-stu-id="fc1d3-216">Change your payment frequency</span></span>](change-payment-frequency.md)
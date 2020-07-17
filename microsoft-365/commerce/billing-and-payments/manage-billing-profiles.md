---
title: Verwalten von Abrechnungsprofilen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Erfahren Sie, wie Rechnungen durch Abrechnungsprofile unterstützt werden.
keywords: Abrechnungsprofil, Rechnungen, Gebühren, verwaltete Gebühren
ms.openlocfilehash: 2979909e3b916cc4bc8704f32a821b13fa6090e0
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741711"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="25bdb-104">Verwalten von Abrechnungsprofilen</span><span class="sxs-lookup"><span data-stu-id="25bdb-104">Manage billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="25bdb-105">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="25bdb-105">The admin center is changing.</span></span> <span data-ttu-id="25bdb-106">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="25bdb-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="25bdb-107">Für kommerzielle Kunden, die Produkte und Dienste von Microsoft kaufen, können Sie mit Abrechnungs Profilen anpassen, welche Elemente in Ihrer Rechnung enthalten sind, und wie Sie Ihre Rechnungen bezahlen.</span><span class="sxs-lookup"><span data-stu-id="25bdb-107">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="25bdb-108">Abrechnungsprofile umfassen die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="25bdb-108">Billing profiles include the following information:</span></span>

- <span data-ttu-id="25bdb-109">**Abrechnungskonto** &ndash; Name des Abrechnungskontos, mit dem das Profil verknüpft ist</span><span class="sxs-lookup"><span data-stu-id="25bdb-109">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="25bdb-110">**Zahlungsmethoden** &ndash; Kredit-oder Debitkarten, Bankkonten, Schecks oder Überweisungen</span><span class="sxs-lookup"><span data-stu-id="25bdb-110">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="25bdb-111">**Kontaktinformationen** &ndash; Rechnungsadresse und Kontakt Name</span><span class="sxs-lookup"><span data-stu-id="25bdb-111">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="25bdb-112">**Rechnungseinstellungen** &ndash; Währung basierend auf dem Land des Abrechnungskontos, einer optionalen Bestellnummer und der Option zum Empfangen von Rechnungen als e-Mail-Anlagen</span><span class="sxs-lookup"><span data-stu-id="25bdb-112">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="25bdb-113">**Berechtigungen** &ndash; Berechtigungen, mit denen Sie das Abrechnungsprofil ändern, Rechnungen bezahlen oder die Zahlungsmethode für das Abrechnungsprofil verwenden können, um Einkäufe zu tätigen</span><span class="sxs-lookup"><span data-stu-id="25bdb-113">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="25bdb-114">Verwenden Sie Abrechnungsprofile, um Ihre Käufe zu steuern und ihre Rechnung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="25bdb-114">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="25bdb-115">Für die Produkte, die mit dem Abrechnungsprofil gekauft wurden, wird eine monatliche Rechnung generiert.</span><span class="sxs-lookup"><span data-stu-id="25bdb-115">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="25bdb-116">Sie können die Rechnung wie das Aktualisieren der Bestellnummer und der e-Mail-Rechnungs Präferenz anpassen.</span><span class="sxs-lookup"><span data-stu-id="25bdb-116">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="25bdb-117">Bei Ihrem ersten Einkauf wird automatisch ein Abrechnungsprofil für Ihr Abrechnungskonto erstellt.</span><span class="sxs-lookup"><span data-stu-id="25bdb-117">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="25bdb-118">Sie können auf der Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Abrechnungsprofile</a> Abrechnungsprofile erstellen, um weitere Rechnungen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="25bdb-118">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="25bdb-119">Beispielsweise können Sie unterschiedliche Abrechnungsprofile verwenden, wenn Sie Einkäufe für jede Abteilung in Ihrer Organisation tätigen.</span><span class="sxs-lookup"><span data-stu-id="25bdb-119">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="25bdb-120">Bei Ihrem nächsten Abrechnungsdatum erhalten Sie eine Rechnung für jedes Abrechnungsprofil.</span><span class="sxs-lookup"><span data-stu-id="25bdb-120">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="25bdb-121">Abrechnungsprofil Rollen</span><span class="sxs-lookup"><span data-stu-id="25bdb-121">Billing profile roles</span></span>

<span data-ttu-id="25bdb-122">Rollen in Abrechnungs Profilen besitzen Berechtigungen zum Steuern von Käufen sowie zum Anzeigen und Verwalten von Rechnungen.</span><span class="sxs-lookup"><span data-stu-id="25bdb-122">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="25bdb-123">Weisen Sie diese Rollen Benutzern zu, die Rechnungen nachverfolgen, organisieren und bezahlen, wie Mitglieder des Beschaffungsteams in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="25bdb-123">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="25bdb-124">Rolle</span><span class="sxs-lookup"><span data-stu-id="25bdb-124">Role</span></span>                          | <span data-ttu-id="25bdb-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25bdb-125">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="25bdb-126">Abrechnungsprofil Besitzer</span><span class="sxs-lookup"><span data-stu-id="25bdb-126">Billing profile owner</span></span>         | <span data-ttu-id="25bdb-127">Alles für ein Abrechnungsprofil verwalten</span><span class="sxs-lookup"><span data-stu-id="25bdb-127">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="25bdb-128">Abrechnungsprofil Mitwirkende</span><span class="sxs-lookup"><span data-stu-id="25bdb-128">Billing profile contributor</span></span>   | <span data-ttu-id="25bdb-129">Alles außer Berechtigungen in einem Abrechnungsprofil verwalten</span><span class="sxs-lookup"><span data-stu-id="25bdb-129">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="25bdb-130">Abrechnungsprofil Leser</span><span class="sxs-lookup"><span data-stu-id="25bdb-130">Billing profile reader</span></span>        | <span data-ttu-id="25bdb-131">Schreibgeschützte Ansicht aller Elemente in einem Abrechnungsprofil</span><span class="sxs-lookup"><span data-stu-id="25bdb-131">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="25bdb-132">Rechnungs-Manager</span><span class="sxs-lookup"><span data-stu-id="25bdb-132">Invoice manager</span></span>               | <span data-ttu-id="25bdb-133">Anzeigen und bezahlen von Rechnungen und verfügen über eine schreibgeschützte Ansicht aller Elemente in einem Abrechnungsprofil</span><span class="sxs-lookup"><span data-stu-id="25bdb-133">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="25bdb-134">Anzeigen von Abrechnungs Profilen</span><span class="sxs-lookup"><span data-stu-id="25bdb-134">View billing profiles</span></span>

1. <span data-ttu-id="25bdb-135">Gehen Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Rechnungen & Zahlungen</a>.</span><span class="sxs-lookup"><span data-stu-id="25bdb-135">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="25bdb-136">Wählen Sie **Abrechnungsprofile**aus, und wählen Sie dann ein Abrechnungsprofil aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="25bdb-136">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="25bdb-137">Auf der Registerkarte **Übersicht** können Sie Abrechnungsprofil Details bearbeiten und das Senden einer Rechnung per e-Mail aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="25bdb-137">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="25bdb-138">Auf der Registerkarte **Berechtigungen** können Sie Benutzern Rollen zuweisen, um Rechnungen zu bezahlen.</span><span class="sxs-lookup"><span data-stu-id="25bdb-138">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="25bdb-139">Auf der Registerkarte **Azure Credit Balance** können Azure-Kunden den Transaktionssaldo Verlauf für die Azure-Gutschriften anzeigen, die von diesem Abrechnungsprofil verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="25bdb-139">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="25bdb-140">Auf der Registerkarte **Azure Credits** können Azure-Kunden eine Liste der Azure-Gutschriften angezeigt werden, die diesem Abrechnungsprofil zugeordnet sind, sowie deren Ablaufdaten.</span><span class="sxs-lookup"><span data-stu-id="25bdb-140">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="25bdb-141">Wenn Sie keine Azure-Gutschriften haben, werden die Registerkarten **Azure Credit Balance** oder **Azure Credits** nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25bdb-141">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="25bdb-142">Benötigen Sie Hilfe?</span><span class="sxs-lookup"><span data-stu-id="25bdb-142">Need help?</span></span> <span data-ttu-id="25bdb-143">Kontaktieren Sie den Support.</span><span class="sxs-lookup"><span data-stu-id="25bdb-143">Contact support.</span></span>

<span data-ttu-id="25bdb-144">Wenn Sie Fragen haben oder Hilfe zu ihren Azure-Gebühren benötigen, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Erstellen Sie eine Supportanfrage mit Azure-Unterstützung</a>.</span><span class="sxs-lookup"><span data-stu-id="25bdb-144">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="25bdb-145">Wenn Sie Fragen haben oder Hilfe zu Ihrem Abrechnungsprofil im Microsoft 365 Admin Center benötigen, [wenden Sie sich an den Support für Business-Produkte](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="25bdb-145">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

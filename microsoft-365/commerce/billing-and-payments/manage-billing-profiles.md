---
title: Informationen zu Abrechnungsprofilen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: Erfahren Sie, wie Abrechnungsprofile Rechnungen unterstützen.
ms.date: 04/02/2021
ms.openlocfilehash: e66efe12e05d2aaf286b689c955f17c8401144f1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537331"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="139db-103">Informationen zu Abrechnungsprofilen</span><span class="sxs-lookup"><span data-stu-id="139db-103">Understand billing profiles</span></span>

<span data-ttu-id="139db-104">Ein Abrechnungsprofil enthält eine Zahlungsmethode, Rechnungsinformationen und andere Rechnungseinstellungen, z. B. Bestellnummer und E-Mail-Rechnungseinstellung.</span><span class="sxs-lookup"><span data-stu-id="139db-104">A billing profile contains a payment method, Bill-to information, and other invoice settings, such as purchase order number and email invoice preference.</span></span> <span data-ttu-id="139db-105">Sie verwenden ein Abrechnungsprofil, um die Produkte zu bezahlen, die Sie bei Microsoft kaufen.</span><span class="sxs-lookup"><span data-stu-id="139db-105">You use a billing profile to pay for the products that you buy from Microsoft.</span></span> <span data-ttu-id="139db-106">Ein Abrechnungsprofil wird automatisch erstellt, wenn ein Benutzer einen Self-Service-Kauf vor sich hat.</span><span class="sxs-lookup"><span data-stu-id="139db-106">A billing profile is automatically created when a user makes a self-service purchase.</span></span> <span data-ttu-id="139db-107">Jedes Abrechnungsprofil wird separat in Rechnung gestellt.</span><span class="sxs-lookup"><span data-stu-id="139db-107">Each billing profile is invoiced separately.</span></span>

> [!NOTE]
>
> <span data-ttu-id="139db-108">Abrechnungsprofile sind nicht für Kunden verfügbar, die Produkte und  Dienste von Microsoft.com oder auf der Seite Dienste kaufen im Microsoft 365 erwerben.</span><span class="sxs-lookup"><span data-stu-id="139db-108">Billing profiles are not available to customers who buy products and services from Microsoft.com or on the **Purchase services** page of the Microsoft 365 admin center.</span></span>

## <a name="what-are-billing-profile-roles"></a><span data-ttu-id="139db-109">Was sind Abrechnungsprofilrollen?</span><span class="sxs-lookup"><span data-stu-id="139db-109">What are billing profile roles?</span></span>

<span data-ttu-id="139db-110">Rollen in Abrechnungsprofilen verfügen über Berechtigungen zum Steuern von Einkäufen sowie zum Anzeigen und Verwalten von Rechnungen.</span><span class="sxs-lookup"><span data-stu-id="139db-110">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="139db-111">Weisen Sie diese Rollen Benutzern zu, die Rechnungen nachverfolgen, organisieren und bezahlen.</span><span class="sxs-lookup"><span data-stu-id="139db-111">Assign these roles to users who track, organize, and pay invoices.</span></span> <span data-ttu-id="139db-112">Beispielsweise Mitglieder des Beschaffungsteams in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="139db-112">For example, members of the procurement team in your organization.</span></span>

| <span data-ttu-id="139db-113">Rolle</span><span class="sxs-lookup"><span data-stu-id="139db-113">Role</span></span>                         | <span data-ttu-id="139db-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="139db-114">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="139db-115">Abrechnungsprofilbesitzer</span><span class="sxs-lookup"><span data-stu-id="139db-115">Billing profile owner</span></span>        | <span data-ttu-id="139db-116">Verwalten alles für ein Abrechnungsprofil</span><span class="sxs-lookup"><span data-stu-id="139db-116">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="139db-117">Mitwirkender des Abrechnungsprofils</span><span class="sxs-lookup"><span data-stu-id="139db-117">Billing profile contributor</span></span>  | <span data-ttu-id="139db-118">Verwalten alles außer Berechtigungen in einem Abrechnungsprofil</span><span class="sxs-lookup"><span data-stu-id="139db-118">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="139db-119">Abrechnungsprofilleser</span><span class="sxs-lookup"><span data-stu-id="139db-119">Billing profile reader</span></span>       | <span data-ttu-id="139db-120">Schreibgeschützte Ansicht aller Daten in einem Abrechnungsprofil</span><span class="sxs-lookup"><span data-stu-id="139db-120">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="139db-121">Rechnungs-Manager</span><span class="sxs-lookup"><span data-stu-id="139db-121">Invoice manager</span></span>              | <span data-ttu-id="139db-122">Anzeigen und Bezahlen von Rechnungen und eine schreibgeschützte Ansicht aller Daten in einem Abrechnungsprofil</span><span class="sxs-lookup"><span data-stu-id="139db-122">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-my-billing-profiles"></a><span data-ttu-id="139db-123">Anzeigen meiner Abrechnungsprofile</span><span class="sxs-lookup"><span data-stu-id="139db-123">View my billing profiles</span></span>

> [!NOTE]
>
> <span data-ttu-id="139db-124">Wenn Sie diese Schritte ausführen und die Liste der Abrechnungsprofile leer ist, bedeutet dies, dass Sie kein Abrechnungsprofil haben und dieses Feature nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="139db-124">If you follow these steps and the billing profiles list is empty, it means that you don’t have a billing profile, and can’t use this feature.</span></span>

1. <span data-ttu-id="139db-125">Gehen Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Rechnungen & Zahlungen</a>.</span><span class="sxs-lookup"><span data-stu-id="139db-125">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="139db-126">Wählen Sie **die Registerkarte Abrechnungsprofil** aus, und wählen Sie dann ein Abrechnungsprofil aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="139db-126">Select the **Billing profile** tab, then select a billing profile from the list.</span></span>

<span data-ttu-id="139db-127">Jedes Abrechnungsprofil enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="139db-127">Each billing profile includes the following information:</span></span>

- <span data-ttu-id="139db-128">**Name und Status des Abrechnungsprofils** &ndash; Der eindeutige Name des Abrechnungsprofils und ob das Abrechnungsprofil für den Kauf aktiv oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="139db-128">**Billing profile name and status** &ndash; The unique name of the billing profile, and whether the billing profile is active or disabled for purchasing.</span></span>
- <span data-ttu-id="139db-129">**Rechnungseinstellungen** &ndash; Währung basierend auf dem Land des Abrechnungskontos, Informationen zur Häufigkeit und dem Datum der Rechnung, der Option, Rechnungen als E-Mail-Anlagen zu empfangen, und einem optionalen Feld für die Postfachnummer</span><span class="sxs-lookup"><span data-stu-id="139db-129">**Invoice settings** &ndash; Currency based on the country of the billing account, information about invoice frequency and date, the option to receive invoices as email attachments, and an optional PO number field</span></span>
- <span data-ttu-id="139db-130">**Zahlungsmethoden** &ndash; Zeigt die primäre zahlungsmethode und die Sicherungszahlungsmethode für das Profil an, falls dies der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="139db-130">**Payment methods** &ndash; Shows the primary and backup payment method, if any, for the profile</span></span>
- <span data-ttu-id="139db-131">**Abrechnungskonto** &ndash; Name des Abrechnungskontos, mit dem das Profil verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="139db-131">**Billing account** &ndash; Name of the billing account the profile is related to.</span></span> <span data-ttu-id="139db-132">Weitere Informationen zu Abrechnungskonten finden Sie unter [Verstehen von Abrechnungskonten](../manage-billing-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="139db-132">For more information about billing accounts, see [Understand billing accounts](../manage-billing-accounts.md).</span></span>
- <span data-ttu-id="139db-133">**Kontaktinformationen** &ndash; Rechnungsadresse und Kontaktname und E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="139db-133">**Contact information** &ndash; Billing address and contact name and email address</span></span>
- <span data-ttu-id="139db-134">**Abrechnungsprofilrollen** &ndash; Eine Liste der Personen, denen eine der Abrechnungsprofilrollen zugewiesen ist, um Aufgaben für dieses Profil zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="139db-134">**Billing profile roles** &ndash; A list of people who are assigned one of the billing profile roles to do things for that profile.</span></span> <span data-ttu-id="139db-135">Zahlen Sie beispielsweise Rechnungen, fügen Sie eine Postfachnummer hinzu, oder ersetzen Sie die Zahlungsmethode, die zum Tätigen von Einkäufen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="139db-135">For example, pay bills, add a PO number, or replace the payment method that is used to make purchases.</span></span>

> [!NOTE]
>
> <span data-ttu-id="139db-136">Sie können Nur Benutzern in Ihrer Organisation Abrechnungsprofilrollen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="139db-136">You can only assign billing profile roles to users in your organization.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="139db-137">Benötigen Sie Hilfe?</span><span class="sxs-lookup"><span data-stu-id="139db-137">Need help?</span></span> <span data-ttu-id="139db-138">Support kontaktieren</span><span class="sxs-lookup"><span data-stu-id="139db-138">Contact support</span></span>

<span data-ttu-id="139db-139">Wenn Sie Fragen haben oder Hilfe zu Ihren Azure-Gebühren benötigen, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">erstellen Sie eine Supportanfrage mit dem Azure-Support.</a></span><span class="sxs-lookup"><span data-stu-id="139db-139">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="139db-140">Wenn Sie Fragen haben oder Hilfe zu Ihrem Abrechnungsprofil im Microsoft 365 benötigen, wenden Sie [sich an den Support](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="139db-140">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support](../../business-video/get-help-support.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="139db-141">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="139db-141">Related content</span></span>

<span data-ttu-id="139db-142">[So bezahlen Sie Ihr Abonnement mit einem Abrechnungsprofil](pay-for-subscription-billing-profile.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="139db-142">[How to pay for your subscription with a billing profile](pay-for-subscription-billing-profile.md) (article)</span></span>\
<span data-ttu-id="139db-143">[Verstehen von Abrechnungskonten](../manage-billing-accounts.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="139db-143">[Understand billing accounts](../manage-billing-accounts.md) (article)</span></span>\
<span data-ttu-id="139db-144">[Verwalten von Zahlungsmethoden](manage-payment-methods.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="139db-144">[Manage payment methods](manage-payment-methods.md) (article)</span></span>

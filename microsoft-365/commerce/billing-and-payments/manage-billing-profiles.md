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
- AdminTemplateSet
search.appverid: MET150
description: Erfahren Sie, wie Abrechnungsprofile Rechnungen unterstützen.
ms.date: 04/02/2021
ms.openlocfilehash: ecea09a9ceea12fa92b92eac3e5a7595b2510042
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394629"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="41b85-103">Informationen zu Abrechnungsprofilen</span><span class="sxs-lookup"><span data-stu-id="41b85-103">Understand billing profiles</span></span>

<span data-ttu-id="41b85-104">Ein Abrechnungsprofil enthält eine Zahlungsmethode, Rechnungsinformationen und andere Rechnungseinstellungen, z. B. Bestellnummer und E-Mail-Rechnungseinstellung.</span><span class="sxs-lookup"><span data-stu-id="41b85-104">A billing profile contains a payment method, Bill-to information, and other invoice settings, such as purchase order number and email invoice preference.</span></span> <span data-ttu-id="41b85-105">Sie verwenden ein Abrechnungsprofil, um die Produkte zu bezahlen, die Sie von Microsoft kaufen.</span><span class="sxs-lookup"><span data-stu-id="41b85-105">You use a billing profile to pay for the products that you buy from Microsoft.</span></span> <span data-ttu-id="41b85-106">Ein Abrechnungsprofil wird automatisch erstellt, wenn ein Benutzer einen Self-Service-Kauf vornimmt.</span><span class="sxs-lookup"><span data-stu-id="41b85-106">A billing profile is automatically created when a user makes a self-service purchase.</span></span> <span data-ttu-id="41b85-107">Jedes Abrechnungsprofil wird separat in Rechnung gestellte.</span><span class="sxs-lookup"><span data-stu-id="41b85-107">Each billing profile is invoiced separately.</span></span>

> [!NOTE]
>
> <span data-ttu-id="41b85-108">Abrechnungsprofile sind für Kunden, die Produkte und Dienste über Microsoft.com oder auf der Seite **"Dienste kaufen"** des Microsoft 365 Admin Center kaufen, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="41b85-108">Billing profiles are not available to customers who buy products and services from Microsoft.com or on the **Purchase services** page of the Microsoft 365 admin center.</span></span>

## <a name="what-are-billing-profile-roles"></a><span data-ttu-id="41b85-109">Was sind Die Rollen des Abrechnungsprofils?</span><span class="sxs-lookup"><span data-stu-id="41b85-109">What are billing profile roles?</span></span>

<span data-ttu-id="41b85-110">Rollen in Abrechnungsprofilen verfügen über Berechtigungen zum Steuern von Einkäufen sowie zum Anzeigen und Verwalten von Rechnungen.</span><span class="sxs-lookup"><span data-stu-id="41b85-110">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="41b85-111">Weisen Sie diese Rollen Benutzern zu, die Rechnungen nachverfolgen, organisieren und bezahlen.</span><span class="sxs-lookup"><span data-stu-id="41b85-111">Assign these roles to users who track, organize, and pay invoices.</span></span> <span data-ttu-id="41b85-112">Beispielsweise Mitglieder des Beschaffungsteams in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="41b85-112">For example, members of the procurement team in your organization.</span></span>

| <span data-ttu-id="41b85-113">Rolle</span><span class="sxs-lookup"><span data-stu-id="41b85-113">Role</span></span>                         | <span data-ttu-id="41b85-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41b85-114">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="41b85-115">Besitzer des Abrechnungsprofils</span><span class="sxs-lookup"><span data-stu-id="41b85-115">Billing profile owner</span></span>        | <span data-ttu-id="41b85-116">Verwalten aller Elemente für ein Abrechnungsprofil</span><span class="sxs-lookup"><span data-stu-id="41b85-116">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="41b85-117">Abrechnungsprofilmitwirkender</span><span class="sxs-lookup"><span data-stu-id="41b85-117">Billing profile contributor</span></span>  | <span data-ttu-id="41b85-118">Verwalten aller Elemente mit Ausnahme von Berechtigungen in einem Abrechnungsprofil</span><span class="sxs-lookup"><span data-stu-id="41b85-118">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="41b85-119">Leser des Abrechnungsprofils</span><span class="sxs-lookup"><span data-stu-id="41b85-119">Billing profile reader</span></span>       | <span data-ttu-id="41b85-120">Schreibgeschützte Ansicht aller Elemente in einem Abrechnungsprofil</span><span class="sxs-lookup"><span data-stu-id="41b85-120">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="41b85-121">Rechnungsmanager</span><span class="sxs-lookup"><span data-stu-id="41b85-121">Invoice manager</span></span>              | <span data-ttu-id="41b85-122">Anzeigen und Bezahlen von Rechnungen und eine schreibgeschützte Ansicht aller Elemente in einem Abrechnungsprofil</span><span class="sxs-lookup"><span data-stu-id="41b85-122">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-my-billing-profiles"></a><span data-ttu-id="41b85-123">Anzeigen meiner Abrechnungsprofile</span><span class="sxs-lookup"><span data-stu-id="41b85-123">View my billing profiles</span></span>

> [!NOTE]
>
> <span data-ttu-id="41b85-124">Wenn Sie diese Schritte ausführen und die Liste der Abrechnungsprofile leer ist, bedeutet dies, dass Sie kein Abrechnungsprofil haben und dieses Feature nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="41b85-124">If you follow these steps and the billing profiles list is empty, it means that you don’t have a billing profile, and can’t use this feature.</span></span>

1. <span data-ttu-id="41b85-125">Gehen Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Rechnungen & Zahlungen</a>.</span><span class="sxs-lookup"><span data-stu-id="41b85-125">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="41b85-126">Wählen Sie die Registerkarte **"Abrechnungsprofil"** und dann ein Abrechnungsprofil aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="41b85-126">Select the **Billing profile** tab, then select a billing profile from the list.</span></span>

<span data-ttu-id="41b85-127">Jedes Abrechnungsprofil enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="41b85-127">Each billing profile includes the following information:</span></span>

- <span data-ttu-id="41b85-128">**Name und Status** &ndash; des Abrechnungsprofils Der eindeutige Name des Abrechnungsprofils und ob das Abrechnungsprofil aktiv oder für den Kauf deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="41b85-128">**Billing profile name and status** &ndash; The unique name of the billing profile, and whether the billing profile is active or disabled for purchasing.</span></span>
- <span data-ttu-id="41b85-129">**Rechnungseinstellungen** &ndash; Währung basierend auf dem Land des Abrechnungskontos, Informationen zur Rechnungshäufigkeit und zum Datum, der Option zum Empfangen von Rechnungen als E-Mail-Anlagen und einem optionalen Feld für die Bestellnummer</span><span class="sxs-lookup"><span data-stu-id="41b85-129">**Invoice settings** &ndash; Currency based on the country of the billing account, information about invoice frequency and date, the option to receive invoices as email attachments, and an optional PO number field</span></span>
- <span data-ttu-id="41b85-130">**Zahlungsmethoden** &ndash; Zeigt die primäre und ggf. sicherungsweise Zahlungsmethode für das Profil an.</span><span class="sxs-lookup"><span data-stu-id="41b85-130">**Payment methods** &ndash; Shows the primary and backup payment method, if any, for the profile</span></span>
- <span data-ttu-id="41b85-131">**Abrechnungskonto** &ndash; Name des Abrechnungskontos, mit dem das Profil verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="41b85-131">**Billing account** &ndash; Name of the billing account the profile is related to.</span></span> <span data-ttu-id="41b85-132">Weitere Informationen zu Abrechnungskonten finden Sie unter ["Grundlegendes zu Abrechnungskonten".](../manage-billing-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="41b85-132">For more information about billing accounts, see [Understand billing accounts](../manage-billing-accounts.md).</span></span>
- <span data-ttu-id="41b85-133">**Kontaktinformationen** &ndash; Rechnungsadresse, Kontaktname und E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="41b85-133">**Contact information** &ndash; Billing address and contact name and email address</span></span>
- <span data-ttu-id="41b85-134">Rollen des **Abrechnungsprofils** &ndash; Eine Liste der Personen, denen eine der Rollen für das Abrechnungsprofil zugewiesen ist, um Aufgaben für dieses Profil zu erledigen.</span><span class="sxs-lookup"><span data-stu-id="41b85-134">**Billing profile roles** &ndash; A list of people who are assigned one of the billing profile roles to do things for that profile.</span></span> <span data-ttu-id="41b85-135">Bezahlen Sie beispielsweise Rechnungen, fügen Sie eine Auftragsnummer hinzu, oder ersetzen Sie die Zahlungsmethode, die zum Tätigen von Einkäufen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="41b85-135">For example, pay bills, add a PO number, or replace the payment method that is used to make purchases.</span></span>

> [!NOTE]
>
> <span data-ttu-id="41b85-136">Sie können Benutzern in Ihrer Organisation nur Abrechnungsprofilrollen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="41b85-136">You can only assign billing profile roles to users in your organization.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="41b85-137">Benötigen Sie Hilfe?</span><span class="sxs-lookup"><span data-stu-id="41b85-137">Need help?</span></span> <span data-ttu-id="41b85-138">Support kontaktieren</span><span class="sxs-lookup"><span data-stu-id="41b85-138">Contact support</span></span>

<span data-ttu-id="41b85-139">Wenn Sie Fragen haben oder Hilfe zu Ihren Azure-Gebühren benötigen, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">erstellen Sie eine Supportanfrage mit Azure-Support.</a></span><span class="sxs-lookup"><span data-stu-id="41b85-139">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="41b85-140">Wenn Sie Fragen haben oder Hilfe zu Ihrem Abrechnungsprofil in Microsoft 365 Admin Center benötigen, [wenden Sie sich an den Support.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="41b85-140">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support](../../business-video/get-help-support.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="41b85-141">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="41b85-141">Related content</span></span>

<span data-ttu-id="41b85-142">[So zahlen Sie für Ihr Abonnement mit einem Abrechnungsprofil](pay-for-subscription-billing-profile.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="41b85-142">[How to pay for your subscription with a billing profile](pay-for-subscription-billing-profile.md) (article)</span></span>\
<span data-ttu-id="41b85-143">[Grundlegendes zu Abrechnungskonten](../manage-billing-accounts.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="41b85-143">[Understand billing accounts](../manage-billing-accounts.md) (article)</span></span>\
<span data-ttu-id="41b85-144">[Verwalten von Zahlungsmethoden](manage-payment-methods.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="41b85-144">[Manage payment methods](manage-payment-methods.md) (article)</span></span>

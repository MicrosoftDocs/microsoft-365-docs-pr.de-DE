---
title: Payment Services-Direktive 2 und starke Kundenauthentifizierung für kommerzielle Kunden
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Am 2019. September sind Banken in den 31 Ländern des Europäischen Wirtschaftsraums verpflichtet, die Identität der Person zu überprüfen, die Online kauft, bevor die Zahlung verarbeitet werden kann. "
keywords: Payment Services-Direktive 2, starke Kundenauthentifizierung, mehrstufige Authentifizierung
ms.openlocfilehash: d6564a8c6d31bd0758f1084e7ee9b6857aed034e
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906609"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="80f9d-104">Payment Services-Direktive 2 und starke Kundenauthentifizierung für kommerzielle Kunden</span><span class="sxs-lookup"><span data-stu-id="80f9d-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="80f9d-105">Am 2019. September sind die Banken in den 31 Ländern des Europäischen Wirtschaftsraums verpflichtet, die Identität der Person zu überprüfen, die Online kauft, bevor die Zahlung verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="80f9d-105">As of September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="80f9d-106">Bei dieser Überprüfung ist die mehrstufige Authentifizierung erforderlich, um sicherzustellen, dass Ihre Online Käufe sicher und geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="80f9d-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="80f9d-107">Das Datum für diese Überprüfungsanforderung wird für einige Länder verzögert.</span><span class="sxs-lookup"><span data-stu-id="80f9d-107">The date for this verification requirement will be delayed for some countries.</span></span>

<span data-ttu-id="80f9d-108">Weitere Informationen finden Sie in der [Microsoft-FAQ zur Payment Services-Direktive 2 und zur starken Kundenauthentifizierung](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span><span class="sxs-lookup"><span data-stu-id="80f9d-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="80f9d-109">Wann ist mehrstufige Authentifizierung erforderlich?</span><span class="sxs-lookup"><span data-stu-id="80f9d-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="80f9d-110">Derzeit gelten die Überprüfungsanforderungen für diese Direktive mit mehrstufiger Authentifizierung nur für Kunden, die Kreditkarten von Banken in den 31 Ländern des Europäischen Wirtschaftsraums verwenden.</span><span class="sxs-lookup"><span data-stu-id="80f9d-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="80f9d-111">Manchmal werden Kunden aufgrund einer Aktion aufgefordert, die Sie ergriffen haben, und manchmal werden Sie aufgrund von Ereignissen mit Ihren vorhandenen Abonnements oder Diensten dazu aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="80f9d-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="80f9d-112">Kundenaktionen</span><span class="sxs-lookup"><span data-stu-id="80f9d-112">Customer Actions</span></span>

<span data-ttu-id="80f9d-113">Für Ihre Bank ist möglicherweise eine Überprüfung durch mehrstufige Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="80f9d-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="80f9d-114">Beispiele hierfür sind:</span><span class="sxs-lookup"><span data-stu-id="80f9d-114">Some examples include:</span></span>
- <span data-ttu-id="80f9d-115">Registrieren für ein neues Abonnement</span><span class="sxs-lookup"><span data-stu-id="80f9d-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="80f9d-116">Hinzufügen von Lizenzen zu einem Abonnement</span><span class="sxs-lookup"><span data-stu-id="80f9d-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="80f9d-117">Hinzufügen oder Ersetzen der Kreditkarte, die für ein Abonnement oder eine Dienstzahlung verwendet wurde</span><span class="sxs-lookup"><span data-stu-id="80f9d-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="80f9d-118">Hinzufügen oder Ersetzen einer Kreditkarte in einem Abrechnungsprofil</span><span class="sxs-lookup"><span data-stu-id="80f9d-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="80f9d-119">Apps kaufen</span><span class="sxs-lookup"><span data-stu-id="80f9d-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="80f9d-120">Ereignisse des Abonnement Lebenszyklus</span><span class="sxs-lookup"><span data-stu-id="80f9d-120">Subscription lifecycle events</span></span>

<span data-ttu-id="80f9d-121">Zuschläge für wiederkehrende Zahlungen können fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="80f9d-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="80f9d-122">Wenn dies der Fall ist, erhalten Sie eine e-Mail mit Anweisungen zum folgen.</span><span class="sxs-lookup"><span data-stu-id="80f9d-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="80f9d-123">Sie werden aufgefordert, auf die Überprüfungsanforderung zu Antworten und Ihre aktuelle Zahlung zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="80f9d-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="80f9d-124">Benötigen Sie weitere Hilfe?</span><span class="sxs-lookup"><span data-stu-id="80f9d-124">Need more help?</span></span>

<span data-ttu-id="80f9d-125">Ihr Finanzinstitut ist der beste Ansprechpartner für diese Szenarien:</span><span class="sxs-lookup"><span data-stu-id="80f9d-125">Your financial institution is the best contact for these scenarios:</span></span>
- <span data-ttu-id="80f9d-126">Sie haben keinen Bestätigungscode erhalten.</span><span class="sxs-lookup"><span data-stu-id="80f9d-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="80f9d-127">Der Überprüfungsprozess funktionierte nicht, nachdem Sie den Überprüfungscode gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="80f9d-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="80f9d-128">Sie sind nicht sicher, ob die Kontaktinformationen für Ihre Kreditkarte korrekt sind.</span><span class="sxs-lookup"><span data-stu-id="80f9d-128">You're not sure if the contact info for your credit card is correct.</span></span>

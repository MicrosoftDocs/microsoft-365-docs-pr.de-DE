---
title: Verbinden Ihrer Domäne zu Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie, wie Sie Ihre Domäne bestätigen und DNS-Einträge mit Microsoft 365 erstellen.
ms.custom:
- AdminSurgePortfolio
ms.openlocfilehash: 506ee887edbc59956aee11059a7085bc4b22624e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914594"
---
# <a name="connect-your-domain-to-microsoft-365"></a><span data-ttu-id="5bd0c-103">Verbinden Ihrer Domäne zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5bd0c-103">Connect your domain to Microsoft 365</span></span>

> [!NOTE]
> <span data-ttu-id="5bd0c-104">Wenn Sie keine Domäne hinzufügen, verwenden Personen in Ihrer Organisation die Domäne „onmicrosoft.com“ für ihre E-Mail-Adressen, bis Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-104">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="5bd0c-105">Es ist wichtig, dass Sie Ihre Domäne hinzufügen, bevor Sie Benutzer hinzufügen, damit Sie diese nicht zweimal einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-105">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="5bd0c-106">[Lesen Sie in den die häufig gestellten Fragen (FAQ) zu Domänen nach](../setup/domains-faq.yml), wenn Sie unten nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-106">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="5bd0c-107">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-107">Add an MX record so email for your domain will come to Microsoft</span></span>

<span data-ttu-id="5bd0c-108">Sie erhalten nun die Informationen zu dem MX-Eintrag vom Assistenten für die Domäneneinrichtung im Admin Center.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-108">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="5bd0c-109">Fügen Sie auf der Website Ihres Hostinganbieters einen neuen MX-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-109">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="5bd0c-110">Stellen Sie sicher, dass die Felder auf die folgenden Werte festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="5bd0c-110">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="5bd0c-111">Eintragstyp: `MX`</span><span class="sxs-lookup"><span data-stu-id="5bd0c-111">Record Type: `MX`</span></span>
- <span data-ttu-id="5bd0c-112">Priorität: Legen Sie dies auf den höchsten verfügbaren Wert fest, in der Regel `0`.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-112">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="5bd0c-113">Hostname: `@`</span><span class="sxs-lookup"><span data-stu-id="5bd0c-113">Host Name: `@`</span></span>
- <span data-ttu-id="5bd0c-114">Verweist auf die Adresse: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-114">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="5bd0c-115">TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)</span><span class="sxs-lookup"><span data-stu-id="5bd0c-115">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="5bd0c-116">Speichern Sie den Eintrag, und entfernen Sie dann alle anderen MX-Einträge.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-116">Save the record, and then remove any other MX records.</span></span>

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a><span data-ttu-id="5bd0c-117">CNAME-Eintrag hinzufügen, um Benutzer zu ihren Postfächern zu verbinden</span><span class="sxs-lookup"><span data-stu-id="5bd0c-117">Add a CNAME record to connect users to their mailboxes</span></span>
<span data-ttu-id="5bd0c-118">Sie erhalten die Informationen zu den CNAME-Einträgen vom Assistenten für die Domäneneinrichtung im Admin Center.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-118">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="5bd0c-119">Fügen Sie auf der Website Ihres Hosting-Anbieters die folgenden CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-119">On your hosting provider's website, add the following CNAME record.</span></span> <span data-ttu-id="5bd0c-120">Stellen Sie sicher, dass jedes der Felder auf die jeweiligen folgenden Werte festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="5bd0c-120">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="5bd0c-121">Eintragstyp: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="5bd0c-121">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="5bd0c-122">Host: Fügen Sie hier die Werte ein, die Sie aus dem Admin Center kopieren.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-122">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="5bd0c-123">Verweist auf die Adresse: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-123">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="5bd0c-124">TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)</span><span class="sxs-lookup"><span data-stu-id="5bd0c-124">TTL: `3600‎` (or your provider default)</span></span>

## <a name="add-a-txt-record-to-help-prevent-spam"></a><span data-ttu-id="5bd0c-125">Hinzufügen eines TXT-Eintrags, um Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="5bd0c-125">Add a TXT record to help prevent spam</span></span>
<span data-ttu-id="5bd0c-126">**Bevor Sie beginnen:** Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft 365 keinen neuen.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-126">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="5bd0c-127">Fügen Sie stattdessen die erforderlichen Microsoft 365-Werte dem aktuellen Eintrag auf der Website Ihres Hostinganbieters hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-127">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="5bd0c-128">Bearbeiten Sie auf der Website Ihres Hostinganbieters den vorhandenen SPF-Eintrag, oder erstellen Sie einen neuen SPF-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-128">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="5bd0c-129">Stellen Sie sicher, dass die Felder auf die folgenden Werte festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="5bd0c-129">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="5bd0c-130">Eintragstyp: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="5bd0c-130">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="5bd0c-131">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="5bd0c-131">Host: `@`</span></span>
- <span data-ttu-id="5bd0c-132">TXT-Wert: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="5bd0c-132">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="5bd0c-133">TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)</span><span class="sxs-lookup"><span data-stu-id="5bd0c-133">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="5bd0c-134">Speichern Sie den Eintrag.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-134">Save the record.</span></span>

<span data-ttu-id="5bd0c-135">Überprüfen Sie Ihren SPF-Eintrag, indem Sie eines dieser [SPF-Überprüfungstools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) verwenden.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-135">Validate your SPF record by using one of these [SPF validation tools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="5bd0c-136">SPF ist dafür vorgesehen, Spoofing möglichst zu verhindern, es gibt aber Spoofing-Techniken, vor denen SPF nicht schützen kann.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-136">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="5bd0c-137">Zum Schutz vor diesen Techniken sollten Sie, nachdem Sie SPF eingerichtet haben, auch DKIM und DMARC für Microsoft 365 einrichten.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-137">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span>

<span data-ttu-id="5bd0c-138">Um hiermit zu beginnen, lesen Sie [Verwenden von DKIM zur Überprüfung von ausgehenden E-Mails, die von Ihrer Domäne in Microsoft 365 gesendet wurden](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) und [Verwenden von DMARC zum Überprüfen von E-Mail in Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="5bd0c-138">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) and [Use DMARC to validate email in Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).</span></span>

<span data-ttu-id="5bd0c-139">Wechseln Sie schlussendlich zurück zum Assistenten für die Domäneneinrichtung im Admin Center, um Ihre Einrichtung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5bd0c-139">Finally, head back to the admin center domain setup wizard to complete your setup.</span></span>
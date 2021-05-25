---
title: Sammeln der Informationen, die Sie zum Erstellen von DNS-Einträgen benötigen
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Sammeln Sie die Werte/Informationen, die Sie zum Erstellen von DNS-Einträgen benötigen, um Ihre Domäne mit Ihrem Microsoft 365 verbinden.
ms.openlocfilehash: e65d53269f5fb8625b12c4eb22f78516818045be
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635726"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="a689b-103">Sammeln der Informationen, die Sie zum Erstellen von DNS-Einträgen benötigen</span><span class="sxs-lookup"><span data-stu-id="a689b-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="a689b-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="a689b-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="a689b-105">Schritt 1: Suchen des WERTs des TXT-Eintrags und Überprüfen</span><span class="sxs-lookup"><span data-stu-id="a689b-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a689b-106">Wechseln Sie Microsoft 365 Admin Center zur  Seite \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Setupdomänen.</a></span><span class="sxs-lookup"><span data-stu-id="a689b-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a689b-107">Wechseln Sie im Admin  Center zur Seite > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Setupdomänen.</a></span><span class="sxs-lookup"><span data-stu-id="a689b-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a689b-108">Wechseln Sie im Admin  Center zur Seite > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Setupdomänen.</a></span><span class="sxs-lookup"><span data-stu-id="a689b-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="a689b-109">Wählen Sie **auf** der Seite Domänen Ihre Domäne aus, und wählen Sie **dann Setup starten aus.**</span><span class="sxs-lookup"><span data-stu-id="a689b-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="a689b-110">Sie gelangen wieder zum Assistenten für die Domäneneinrichtung und sehen dort den spezifischen Wert, den Sie hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="a689b-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="a689b-111">Wählen Sie **auf der Seite** Domäne überprüfen stattdessen Hinzufügen eines **TXT-Eintrags** aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="a689b-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="a689b-112">Kopieren Sie den **angezeigten TXT-Wert.**</span><span class="sxs-lookup"><span data-stu-id="a689b-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="a689b-113">Es sieht so aus: **MS=msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="a689b-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="a689b-114">Wechseln Sie [zu Erstellen](create-dns-records-at-any-dns-hosting-provider.md)von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter, und wählen Sie Ihren DNS-Host aus der Liste der Registrierungsstellen aus, um die schrittweisen Anweisungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a689b-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="a689b-115">Führen Sie die Schritte zum Erstellen des TXT-Eintrags (oder MX-Eintrags) auf Ihrem DNS-Host aus, und überprüfen Sie dann die Domäne wieder in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a689b-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="a689b-116">Entfernen Sie den TXT-Eintrag (oder MX-Eintrag) von Ihrem DNS-Host, sobald die Domäne in der Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a689b-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="a689b-117">Schritt 2: Suchen des MX-Eintragswerts für E-Mails und mehr</span><span class="sxs-lookup"><span data-stu-id="a689b-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a689b-118">Wechseln Sie Microsoft 365 Admin Center zur  Seite \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Setupdomänen.</a></span><span class="sxs-lookup"><span data-stu-id="a689b-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="a689b-119">Wechseln Sie im Admin  Center zur Seite > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Setupdomänen.</a></span><span class="sxs-lookup"><span data-stu-id="a689b-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a689b-120">Wechseln Sie im Admin  Center zur Seite > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Setupdomänen.</a></span><span class="sxs-lookup"><span data-stu-id="a689b-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="a689b-121">Wählen Sie auf der Seite **Domänen** Ihre Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="a689b-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="a689b-122">Unter **Erforderliche DNS-Einstellungen** werden die hinzuzufügenden DNS-Einträge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a689b-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="a689b-123">Sie sollten diese Informationen zur Verfügung haben, wenn Sie Änderungen bei Ihrem DNS-Hostinganbieter vornehmen, damit Sie die Werte kopieren und einfügen können.</span><span class="sxs-lookup"><span data-stu-id="a689b-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="a689b-124">Die auf dieser Seite aufgelisteten Gruppen von DNS-Einträgen sind von den unter **Domänenzweck** aufgelisteten Optionen abhängig.</span><span class="sxs-lookup"><span data-stu-id="a689b-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="a689b-125">Wechseln Sie [zu Erstellen](create-dns-records-at-any-dns-hosting-provider.md)von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter, und wählen Sie dann Ihren DNS-Host aus der Liste der Registrierungsstellen aus, um schrittweise Anweisungen zum Hinzufügen von Datensätzen auf der Website dieses DNS-Hosts zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a689b-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="a689b-126">Führen Sie die Schritte zum Erstellen der DNS-Einträge bei Ihrem DNS-Hostinganbieter aus.</span><span class="sxs-lookup"><span data-stu-id="a689b-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="a689b-127">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="a689b-127">Related content</span></span>

<span data-ttu-id="a689b-128">[Häufig gestellte Fragen](../setup/domains-faq.yml) zu Domänen (Artikel)</span><span class="sxs-lookup"><span data-stu-id="a689b-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>\
<span data-ttu-id="a689b-129">[Suchen und Beheben von Problemen nach dem Hinzufügen Ihrer Domäne oder Ihrer DNS-Einträge](find-and-fix-issues.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="a689b-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="a689b-130">[Domänen verwalten](index.yml) (Linkseite)</span><span class="sxs-lookup"><span data-stu-id="a689b-130">[Manage domains](index.yml) (link page)</span></span>
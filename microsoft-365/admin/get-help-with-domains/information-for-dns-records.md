---
title: Sammeln der Zum Erstellen von DNS-Einträgen benötigten Informationen
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
description: 'Erfahren Sie, wie Sie die Werte/Informationen finden, die Sie zum Erstellen von DNS-Einträgen für Microsoft 365 benötigen. '
ms.openlocfilehash: 45994139b11a2fd5a03b2e979dd6af334bc1f00b
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126371"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="39d7a-103">Sammeln der Zum Erstellen von DNS-Einträgen benötigten Informationen</span><span class="sxs-lookup"><span data-stu-id="39d7a-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="39d7a-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="39d7a-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="39d7a-105">Schritt 1: Suchen des Werts des TXT-Eintrags und Überprüfen</span><span class="sxs-lookup"><span data-stu-id="39d7a-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="39d7a-106">Wechseln Sie im Microsoft 365 Admin Center zur **Seite "Setupdomänen".** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="39d7a-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="39d7a-107">Wechseln Sie im Admin Center zur Seite **"Setupdomänen".** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="39d7a-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="39d7a-108">Wechseln Sie im Admin Center zur Seite **"Setupdomänen".** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="39d7a-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="39d7a-109">Wählen Sie **auf der Seite "Domänen"** Ihre Domäne aus, und wählen Sie dann **"Setup starten" aus.**</span><span class="sxs-lookup"><span data-stu-id="39d7a-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="39d7a-110">Sie gelangen wieder zum Assistenten für die Domäneneinrichtung und sehen dort den spezifischen Wert, den Sie hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="39d7a-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="39d7a-111">On the **Verify domain** page, select Add a TXT **record instead,** then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="39d7a-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="39d7a-112">Kopieren Sie den **angezeigten TXT-Wert.**</span><span class="sxs-lookup"><span data-stu-id="39d7a-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="39d7a-113">It looks like this: **MS=msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="39d7a-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="39d7a-114">Wechseln Sie [zu Create DNS records at any DNS hosting provider,](create-dns-records-at-any-dns-hosting-provider.md)and select your DNS host from the list of registrars to see the step-by-step instructions.</span><span class="sxs-lookup"><span data-stu-id="39d7a-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="39d7a-115">Befolgen Sie die Schritte zum Erstellen des TXT-Eintrags (oder MX-Eintrags) bei Ihrem DNS-Host, und überprüfen Sie dann die Domäne wieder in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="39d7a-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="39d7a-116">Entfernen Sie den TXT-Eintrag (oder MX-Eintrag) von Ihrem DNS-Host, nachdem die Domäne in Microsoft 365 überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="39d7a-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="39d7a-117">Schritt 2: Suchen des Werts des MX-Eintrags für E-Mails und vieles mehr</span><span class="sxs-lookup"><span data-stu-id="39d7a-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="39d7a-118">Wechseln Sie im Microsoft 365 Admin Center zur **Seite "Setupdomänen".** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="39d7a-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="39d7a-119">Wechseln Sie im Admin Center zur Seite **"Setupdomänen".** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="39d7a-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="39d7a-120">Wechseln Sie im Admin Center zur Seite **"Setupdomänen".** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="39d7a-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="39d7a-121">Wählen Sie auf der Seite **Domänen** Ihre Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="39d7a-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="39d7a-122">Unter **Erforderliche DNS-Einstellungen** werden die hinzuzufügenden DNS-Einträge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39d7a-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="39d7a-123">Sie sollten diese Informationen zur Verfügung haben, wenn Sie Änderungen bei Ihrem DNS-Hostinganbieter vornehmen, damit Sie die Werte kopieren und einfügen können.</span><span class="sxs-lookup"><span data-stu-id="39d7a-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="39d7a-124">Die auf dieser Seite aufgelisteten Gruppen von DNS-Einträgen sind von den unter **Domänenzweck** aufgelisteten Optionen abhängig.</span><span class="sxs-lookup"><span data-stu-id="39d7a-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="39d7a-125">Wechseln Sie zu [Create DNS records at any DNS hosting provider,](create-dns-records-at-any-dns-hosting-provider.md)and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span><span class="sxs-lookup"><span data-stu-id="39d7a-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="39d7a-126">Führen Sie die Schritte zum Erstellen der DNS-Einträge bei Ihrem DNS-Hostinganbieter aus.</span><span class="sxs-lookup"><span data-stu-id="39d7a-126">Follow the steps for creating the records at your DNS host.</span></span>

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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Sammeln Sie die Werte/Informationen, die Sie zum Erstellen von DNS-Einträgen benötigen, um Ihre Domäne mit Ihrem Microsoft 365 Abonnement zu verbinden.
ms.openlocfilehash: c9869444da2ccb7f96ee01576d966767681c5b49
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393883"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="9331f-103">Sammeln der Informationen, die Sie zum Erstellen von DNS-Einträgen benötigen</span><span class="sxs-lookup"><span data-stu-id="9331f-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="9331f-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="9331f-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="9331f-105">Schritt 1: Suchen des TXT-Eintragswerts und Überprüfen</span><span class="sxs-lookup"><span data-stu-id="9331f-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9331f-106">Wechseln Sie im Microsoft 365 Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen.</a></span><span class="sxs-lookup"><span data-stu-id="9331f-106">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9331f-107">Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="9331f-107">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9331f-108">Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="9331f-108">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="9331f-109">Wählen Sie auf der Seite **"Domänen"** Ihre Domäne aus, und wählen Sie dann **"Setup starten"** aus.</span><span class="sxs-lookup"><span data-stu-id="9331f-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="9331f-110">Sie gelangen wieder zum Assistenten für die Domäneneinrichtung und sehen dort den spezifischen Wert, den Sie hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="9331f-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="9331f-111">Wählen Sie auf der Seite **"Domänenüberprüfung"** **einen TXT-Eintrag zu den DNS-Einträgen der Domäne** hinzufügen aus, und wählen Sie dann **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="9331f-111">On the **Domain Verification** page, select **Add a TXT record to the domain's DNS records**, then select **Continue**.</span></span>
    
4. <span data-ttu-id="9331f-112">Kopieren Sie den angezeigten **TXT-Wert.**</span><span class="sxs-lookup"><span data-stu-id="9331f-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="9331f-113">Es sieht wie folgt aus: **MS=msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="9331f-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="9331f-114">Wechseln Sie zum [Hinzufügen von DNS-Einträgen, um Ihre Domäne zu verbinden,](create-dns-records-at-any-dns-hosting-provider.md)und führen Sie die Schritte aus, um Einträge auf der Website Ihres DNS-Hosts hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9331f-114">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>
    
6. <span data-ttu-id="9331f-115">Führen Sie die Schritte zum Erstellen des TXT-Eintrags (oder MX-Eintrags) auf Ihrem DNS-Host aus, und überprüfen Sie dann die Domäne wieder in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9331f-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="9331f-116">Entfernen Sie den TXT-Eintrag (oder MX-Eintrag) von Ihrem DNS-Host, sobald die Domäne in Microsoft 365 überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="9331f-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="9331f-117">Schritt 2: Suchen des MX-Eintragswerts für E-Mails und mehr</span><span class="sxs-lookup"><span data-stu-id="9331f-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9331f-118">Wechseln Sie im Microsoft 365 Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen.</a></span><span class="sxs-lookup"><span data-stu-id="9331f-118">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="9331f-119">Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="9331f-119">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9331f-120">Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="9331f-120">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="9331f-121">Wählen Sie auf der Seite **Domänen** Ihre Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="9331f-121">On the **Domains** page, select your domain.</span></span>
    
3. <span data-ttu-id="9331f-122">Wählen Sie **"DNS verwalten"** aus, wählen Sie **"Weitere Optionen**  >  **hinzufügen"** aus, und wählen Sie **"Weiter"** aus, um die hinzuzufügenden DNS-Einträge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9331f-122">Choose  **Manage DNS**, select **More Options** > **Add your own DNS** and select **Continue** to see the DNS records to add.</span></span>
    
    <span data-ttu-id="9331f-123">Sie sollten diese Informationen zur Verfügung haben, wenn Sie Änderungen bei Ihrem DNS-Hostinganbieter vornehmen, damit Sie die Werte kopieren und einfügen können.</span><span class="sxs-lookup"><span data-stu-id="9331f-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="9331f-124">Die auf dieser Seite aufgelisteten Gruppen von DNS-Einträgen sind von den unter **Domänenzweck** aufgelisteten Optionen abhängig.</span><span class="sxs-lookup"><span data-stu-id="9331f-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="9331f-125">Wechseln Sie zum [Hinzufügen von DNS-Einträgen, um Ihre Domäne zu verbinden,](create-dns-records-at-any-dns-hosting-provider.md)und führen Sie die Schritte aus, um Einträge auf der Website Ihres DNS-Hosts hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9331f-125">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>

5. <span data-ttu-id="9331f-126">Führen Sie die Schritte zum Erstellen der DNS-Einträge bei Ihrem DNS-Hostinganbieter aus.</span><span class="sxs-lookup"><span data-stu-id="9331f-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="9331f-127">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="9331f-127">Related content</span></span>

<span data-ttu-id="9331f-128">[Häufig gestellte Fragen zu Domänen](../setup/domains-faq.yml) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="9331f-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>\
<span data-ttu-id="9331f-129">[Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](find-and-fix-issues.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="9331f-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="9331f-130">[Domänen verwalten](index.yml) (Linkseite)</span><span class="sxs-lookup"><span data-stu-id="9331f-130">[Manage domains](index.yml) (link page)</span></span>
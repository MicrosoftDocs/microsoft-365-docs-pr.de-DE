---
title: Sammeln der zum Erstellen von Office 365-DNS-Einträgen erforderlichen Informationen
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Erfahren Sie, wie Sie die Werte/Informationen finden, die Sie zum Erstellen von DNS-Einträgen für Office 365 benötigen. '
ms.custom: okr_smb
ms.openlocfilehash: 2490532894ef00bab5de3f406b0c104529423382
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210380"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a><span data-ttu-id="ec349-103">Sammeln der zum Erstellen von Office 365-DNS-Einträgen erforderlichen Informationen</span><span class="sxs-lookup"><span data-stu-id="ec349-103">Gather the information you need to create Office 365 DNS records</span></span>

 <span data-ttu-id="ec349-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="ec349-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="ec349-105">Schritt 1: Suchen des txt-Eintrags Werts und überprüfen</span><span class="sxs-lookup"><span data-stu-id="ec349-105">Step 1: Find the TXT record value and verify</span></span>

1. <span data-ttu-id="ec349-106">Wechseln Sie im Microsoft 365 Admin Center zur Seite **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="ec349-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker range="o365-germany"

1. <span data-ttu-id="ec349-107">Wechseln Sie im Admin Center zu dieser <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a> Seite.</span><span class="sxs-lookup"><span data-stu-id="ec349-107">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ec349-108">Wechseln Sie im Admin Center zu dieser <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a> Seite.</span><span class="sxs-lookup"><span data-stu-id="ec349-108">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="ec349-109">Wählen Sie auf der Seite **Domänen** die Domäne aus, und wählen Sie dann **Setup starten**aus.</span><span class="sxs-lookup"><span data-stu-id="ec349-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="ec349-110">Sie gelangen wieder zum Assistenten für die Domäneneinrichtung und sehen dort den spezifischen Wert, den Sie hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="ec349-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="ec349-111">Wählen Sie auf der Seite **Domäne überprüfen** die Option **TXT-Eintrag hinzufügen**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="ec349-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="ec349-112">Kopieren Sie den angezeigten **txt-Wert** .</span><span class="sxs-lookup"><span data-stu-id="ec349-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="ec349-113">Es sieht wie folgt aus: **MS = msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="ec349-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="ec349-114">Wechseln Sie zu [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter](create-dns-records-at-any-dns-hosting-provider.md), und wählen Sie Ihren DNS-Host aus der Liste der Registrierungsstellen aus, um die Schritt-für-Schritt-Anleitungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ec349-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="ec349-115">Führen Sie die Schritte zum Erstellen des TXT-Eintrags (oder des MX-Eintrags) bei Ihrem DNS-Hostinganbieter aus, und überprüfen Sie die Domäne, wenn Sie sich wieder in Office 365 befinden.</span><span class="sxs-lookup"><span data-stu-id="ec349-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Office 365.</span></span>

7. <span data-ttu-id="ec349-116">Entfernen Sie den TXT-Eintrag (oder den MX-Eintrag) von Ihrem DNS-Host, nachdem die Domäne in Office 365 überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="ec349-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Office 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="ec349-117">Schritt 2: Suchen des MX-Eintrags Werts für e-Mail und mehr</span><span class="sxs-lookup"><span data-stu-id="ec349-117">Step 2: Find the MX record value for email and more</span></span>

1. <span data-ttu-id="ec349-118">Wechseln Sie im Microsoft 365 Admin Center zur Seite **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="ec349-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
::: moniker range="o365-germany"

1. <span data-ttu-id="ec349-119">Wechseln Sie im Admin Center zu dieser <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a> Seite.</span><span class="sxs-lookup"><span data-stu-id="ec349-119">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ec349-120">Wechseln Sie im Admin Center zu dieser <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a> Seite.</span><span class="sxs-lookup"><span data-stu-id="ec349-120">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="ec349-121">Wählen Sie auf der Seite **Domänen** Ihre Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ec349-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="ec349-122">Unter **Erforderliche DNS-Einstellungen** werden die hinzuzufügenden DNS-Einträge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec349-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="ec349-123">Sie sollten diese Informationen zur Verfügung haben, wenn Sie Änderungen bei Ihrem DNS-Hostinganbieter vornehmen, damit Sie die Werte kopieren und einfügen können.</span><span class="sxs-lookup"><span data-stu-id="ec349-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="ec349-124">Die auf dieser Seite aufgelisteten Gruppen von DNS-Einträgen sind von den unter **Domänenzweck** aufgelisteten Optionen abhängig.</span><span class="sxs-lookup"><span data-stu-id="ec349-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="ec349-125">Wechseln Sie zu [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter](create-dns-records-at-any-dns-hosting-provider.md), und wählen Sie dann den DNS-Host aus der Liste der Registrierungsstellen aus, um Schritt-für-Schritt-Anweisungen zum Hinzufügen von Datensätzen auf der Website dieses DNS-Hosts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ec349-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="ec349-126">Führen Sie die Schritte zum Erstellen der DNS-Einträge bei Ihrem DNS-Hostinganbieter aus.</span><span class="sxs-lookup"><span data-stu-id="ec349-126">Follow the steps for creating the records at your DNS host.</span></span>

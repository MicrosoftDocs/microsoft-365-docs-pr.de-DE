---
title: Suchen der Domänenregistrierungsstelle
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Erfahren Sie, wie Sie Ihre Domänenregistrierungsstelle und den DNS-Hostinganbieter mithilfe der InterNIC-Suche finden.
ms.openlocfilehash: 434e30709b112cf591159a1692540b8ef2b6bb65
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655542"
---
# <a name="find-your-domain-registrar"></a><span data-ttu-id="49773-103">Suchen der Domänenregistrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="49773-103">Find your domain registrar</span></span>

 <span data-ttu-id="49773-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="49773-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="49773-105">Domänenregistrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="49773-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="49773-106">Finden Ihrer Domänenregistrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="49773-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="49773-107">Nur Domänen, die mit *.COM*, *.NET* und *.EDU* enden, funktionieren mit diesem Tool.</span><span class="sxs-lookup"><span data-stu-id="49773-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="49773-108">Geben Sie auf der [InterNIC-Suchseite](https://go.microsoft.com/fwlink/p/?LinkId=402770) im Feld **Whois Search** Ihre Domäne ein.</span><span class="sxs-lookup"><span data-stu-id="49773-108">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="49773-109">Zum Beispiel *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="49773-109">For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="49773-110">Wählen Sie die Option **Domain** aus, und klicken Sie dann auf **Submit**.</span><span class="sxs-lookup"><span data-stu-id="49773-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="49773-111">Suchen Sie auf der Seite **Whois Search Results** nach dem Eintrag **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="49773-111">On the **Whois Search Results** page, locate the **Registrar** entry.</span></span> <span data-ttu-id="49773-112">Hier finden Sie die Organisation, die den Registrierungsstellendienst für Ihre Domäne bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="49773-112">This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="49773-113">DNS-Hostinganbieter</span><span class="sxs-lookup"><span data-stu-id="49773-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="49773-114">Finden Ihres DNS-Hostinganbieters</span><span class="sxs-lookup"><span data-stu-id="49773-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="49773-115">Nur Domänen, die mit *.COM*, *.NET* und *.EDU* enden, funktionieren mit diesem Tool.</span><span class="sxs-lookup"><span data-stu-id="49773-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="49773-116">Geben Sie auf der [InterNIC-Suchseite]( https://go.microsoft.com/fwlink/p/?LinkId=402770) im Feld **Whois Search** Ihre Domäne ein.</span><span class="sxs-lookup"><span data-stu-id="49773-116">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="49773-117">Zum Beispiel „contoso.com“.</span><span class="sxs-lookup"><span data-stu-id="49773-117">For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="49773-118">Wählen Sie die Option **Domain** aus, und klicken Sie dann auf **Submit**.</span><span class="sxs-lookup"><span data-stu-id="49773-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="49773-119">Suchen Sie auf der Seite **Whois Search Results** nach dem ersten **Name Server**-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="49773-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="49773-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span><span class="sxs-lookup"><span data-stu-id="49773-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span></span> <span data-ttu-id="49773-121">Wählen Sie **Nameserver** und dann **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="49773-121">Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="49773-p105">Suchen Sie auf der Seite **Whois Search Results** nach dem Eintrag **Registrar**. Hier finden Sie Ihren DNS-Hostinganbieter, den DNS-Dienstanbieter, dem der Namenserver für Ihre Domäne gehört.</span><span class="sxs-lookup"><span data-stu-id="49773-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---


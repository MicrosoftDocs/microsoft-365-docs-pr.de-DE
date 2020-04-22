---
title: Suchen der Domänenregistrierungsstelle
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Erfahren Sie, wie Sie Ihre Domänenregistrierungsstelle und den DNS-Hostinganbieter mithilfe der InterNIC-Suche finden.
ms.openlocfilehash: 234578c5622a883296a001ce7f226627dd9d93b5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628458"
---
# <a name="find-your-domain-registrar"></a><span data-ttu-id="cf955-103">Suchen der Domänenregistrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="cf955-103">Find your domain registrar</span></span>

 <span data-ttu-id="cf955-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="cf955-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="cf955-105">Domänenregistrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="cf955-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="cf955-106">Finden Ihrer Domänenregistrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="cf955-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="cf955-107">Nur Domänen, die mit *.COM*, *.NET* und *.EDU* enden, funktionieren mit diesem Tool.</span><span class="sxs-lookup"><span data-stu-id="cf955-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="cf955-108">Geben Sie auf der [InterNIC-Suchseite](https://go.microsoft.com/fwlink/p/?LinkId=402770) im Feld **Whois Search** Ihre Domäne ein.</span><span class="sxs-lookup"><span data-stu-id="cf955-108">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="cf955-109">Zum Beispiel *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="cf955-109">For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="cf955-110">Wählen Sie die Option **Domain** aus, und klicken Sie dann auf **Submit**.</span><span class="sxs-lookup"><span data-stu-id="cf955-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="cf955-111">Suchen Sie auf der Seite **Whois Search Results** nach dem Eintrag **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="cf955-111">On the **Whois Search Results** page, locate the **Registrar** entry.</span></span> <span data-ttu-id="cf955-112">Hier finden Sie die Organisation, die den Registrierungsstellendienst für Ihre Domäne bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="cf955-112">This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="cf955-113">DNS-Hostinganbieter</span><span class="sxs-lookup"><span data-stu-id="cf955-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="cf955-114">Finden Ihres DNS-Hostinganbieters</span><span class="sxs-lookup"><span data-stu-id="cf955-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="cf955-115">Nur Domänen, die mit *.COM*, *.NET* und *.EDU* enden, funktionieren mit diesem Tool.</span><span class="sxs-lookup"><span data-stu-id="cf955-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="cf955-116">Geben Sie auf der [InterNIC-Suchseite]( https://go.microsoft.com/fwlink/p/?LinkId=402770) im Feld **Whois Search** Ihre Domäne ein.</span><span class="sxs-lookup"><span data-stu-id="cf955-116">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="cf955-117">Zum Beispiel „contoso.com“.</span><span class="sxs-lookup"><span data-stu-id="cf955-117">For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="cf955-118">Wählen Sie die Option **Domain** aus, und klicken Sie dann auf **Submit**.</span><span class="sxs-lookup"><span data-stu-id="cf955-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="cf955-119">Suchen Sie auf der Seite **Whois Search Results** nach dem ersten **Name Server**-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="cf955-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="cf955-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span><span class="sxs-lookup"><span data-stu-id="cf955-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span></span> <span data-ttu-id="cf955-121">Wählen Sie **Nameserver**und dann **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="cf955-121">Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="cf955-p105">Suchen Sie auf der Seite **Whois Search Results** nach dem Eintrag **Registrar**. Hier finden Sie Ihren DNS-Hostinganbieter, den DNS-Dienstanbieter, dem der Namenserver für Ihre Domäne gehört.</span><span class="sxs-lookup"><span data-stu-id="cf955-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---


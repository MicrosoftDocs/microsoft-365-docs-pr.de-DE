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
ms.openlocfilehash: 77e4776946d51cb4f8dfe1a746e85d74a9e0a700
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228027"
---
# <a name="find-your-domain-registrar"></a><span data-ttu-id="c9923-103">Suchen der Domänenregistrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="c9923-103">Find your domain registrar</span></span>

 <span data-ttu-id="c9923-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="c9923-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

## <a name="domain-registrar"></a><span data-ttu-id="c9923-105">Domänenregistrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="c9923-105">Domain registrar</span></span>

### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="c9923-106">Finden Ihrer Domänenregistrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="c9923-106">Find your domain name registrar</span></span>

> [!NOTE]
> <span data-ttu-id="c9923-107">Nur Domänen, die mit *.COM*, *.NET* und *.EDU* enden, funktionieren mit diesem Tool.</span><span class="sxs-lookup"><span data-stu-id="c9923-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>

1. <span data-ttu-id="c9923-p101">Geben Sie auf der [InterNIC-Suchseite](https://go.microsoft.com/fwlink/p/?LinkId=402770) im Feld **Whois-Suche** Ihre Domäne ein, beispielsweise *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="c9923-p101">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example,  *contoso.com.*</span></span>

2. <span data-ttu-id="c9923-110">Wählen Sie die Option **Domäne** aus, und klicken Sie dann auf **Übermitteln**.</span><span class="sxs-lookup"><span data-stu-id="c9923-110">Select the **Domain** option, and then select **Submit**.</span></span>

3. <span data-ttu-id="c9923-p102">Suchen Sie auf der Seite **Whois-Suchergebnisse** nach dem Eintrag **Registrierungsstelle**. Hier finden Sie die Organisation, die den Registrierungsstellendienst für Ihre Domäne bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c9923-p102">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists the organization that provides registrar service for your domain.</span></span>

## <a name="dns-hosting-provider"></a><span data-ttu-id="c9923-113">DNS-Hostinganbieter</span><span class="sxs-lookup"><span data-stu-id="c9923-113">DNS hosting provider</span></span>

### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="c9923-114">Finden Ihres DNS-Hostinganbieters</span><span class="sxs-lookup"><span data-stu-id="c9923-114">Find your DNS hosting provider</span></span>

> [!NOTE]
> <span data-ttu-id="c9923-115">Nur Domänen, die mit *.COM*, *.NET* und *.EDU* enden, funktionieren mit diesem Tool.</span><span class="sxs-lookup"><span data-stu-id="c9923-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>

1. <span data-ttu-id="c9923-p103">Geben Sie auf der [InterNIC-Suchseite](https://go.microsoft.com/fwlink/p/?LinkId=402770) im Feld **Whois-Suche** Ihre Domäne ein, beispielsweise contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c9923-p103">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example, contoso.com.</span></span>

2. <span data-ttu-id="c9923-118">Wählen Sie die Option **Domain** aus, und klicken Sie dann auf **Submit**.</span><span class="sxs-lookup"><span data-stu-id="c9923-118">Select the **Domain** option, and then select **Submit**.</span></span>

3. <span data-ttu-id="c9923-119">Suchen Sie auf der Seite **Whois Search Results** nach dem ersten **Name Server**-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="c9923-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span>

4. <span data-ttu-id="c9923-p104">Kopieren Sie die nach dem Doppelpunkt (:) angezeigten Informationen zum Namensserver (Name Server, NS), und fügen Sie diese oben auf der Seite in das Feld **Suche** ein. Wählen Sie **Namensserver** aus, und klicken Sie dann auf **Übermitteln**.</span><span class="sxs-lookup"><span data-stu-id="c9923-p104">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page. Select **Nameserver**, and then select **Submit**.</span></span>

5. <span data-ttu-id="c9923-p105">Suchen Sie auf der Seite **Whois Search Results** nach dem Eintrag **Registrar**. Hier finden Sie Ihren DNS-Hostinganbieter, den DNS-Dienstanbieter, dem der Namenserver für Ihre Domäne gehört.</span><span class="sxs-lookup"><span data-stu-id="c9923-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span>

---


---
title: Das Optimieren von Seiten ruft moderne und klassische Veröffentlichungswebsiteseiten von SharePoint Online auf
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Erfahren Sie, wie Sie moderne und klassische Veröffentlichungswebsiteseiten in SharePoint Online optimieren können, indem Sie die Anzahl der Aufrufe von SharePoint Online-Service-Endpunkten begrenzen.
ms.openlocfilehash: cab0f6a020bd1148a0e852b5a393a6ad907f9771
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921618"
---
# <a name="optimize-page-calls-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a><span data-ttu-id="b0e02-103">Das Optimieren von Seiten ruft moderne und klassische Veröffentlichungswebsiteseiten von SharePoint Online auf</span><span class="sxs-lookup"><span data-stu-id="b0e02-103">Optimize page calls in SharePoint Online modern and classic publishing site pages</span></span>

<span data-ttu-id="b0e02-104">Sowohl moderne als auch klassische SharePoint Online VVeröffentlichungswebsiteseiten enthalten Links, die Daten von SharePoint-Funktionen und CDNs laden (oder anrufen).</span><span class="sxs-lookup"><span data-stu-id="b0e02-104">Both SharePoint Online modern and classic publishing sites contain links that load data from (or make calls to) SharePoint features and CDNs.</span></span> <span data-ttu-id="b0e02-105">Je mehr Aufrufe von einer Seite gemacht werden, desto länger dauert das Laden der Seite.</span><span class="sxs-lookup"><span data-stu-id="b0e02-105">The more calls made by a page, the longer the page takes to load.</span></span> <span data-ttu-id="b0e02-106">Dies wird als **vom Endverbraucher wahrgenommene Latenzzeit** oder **EUPL** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b0e02-106">This is known as **end user perceived latency** or **EUPL**.</span></span>

<span data-ttu-id="b0e02-107">Dieser Artikel beschreibt, wie Sie die Anzahl und Auswirkung von Aufrufen auf externe Endpunkte von Ihren modernen und klassischen Veröffentlichungswebsiteseiten bestimmen und wie Sie deren Auswirkungen auf die vom Endbenutzer wahrgenommene Latenzzeit begrenzen können.</span><span class="sxs-lookup"><span data-stu-id="b0e02-107">This article will help you understand how to determine the number and impact of calls to external endpoints from your modern and classic publishing site pages and how to limit their effect on end user perceived latency.</span></span>

>[!NOTE]
><span data-ttu-id="b0e02-108">Weitere Informationen zur Leistung in modernen SharePoint Online-Portalen finden Sie unter [Leistung in der modernen SharePoint-Umgebung](/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="b0e02-108">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-calls"></a><span data-ttu-id="b0e02-109">Verwenden Sie das Tool „Seitendiagnose für SharePoint“, um die Seitenaufrufe zu analysieren</span><span class="sxs-lookup"><span data-stu-id="b0e02-109">Use the Page Diagnostics for SharePoint tool to analyze page calls</span></span>

<span data-ttu-id="b0e02-110">Das Tool "Seitendiagnose für SharePoint" ist eine Browsererweiterung für den neuen Microsoft Edge- (https://www.microsoft.com/edge) und Chrome-Browser, mit der Sie SharePoint Online-Seiten sowohl in modernen Portal- als auch in klassischen Veröffentlichungs-Websites analysieren können.</span><span class="sxs-lookup"><span data-stu-id="b0e02-110">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="b0e02-111">Das Tool stellt für jede analysierte Seite einen Bericht bereit, in dem die Leistung der Seite anhand einer definierten Gruppe von Leistungskriterien dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b0e02-111">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="b0e02-112">Wenn Sie das Tool "Seitendiagnose für SharePoint" installieren und mehr darüber erfahren möchten, besuchen Sie [Verwenden des Seitendiagnose-Tools für SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="b0e02-112">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="b0e02-113">Das Seitendiagnose-Tool funktioniert nur für SharePoint Online und kann nicht auf einer SharePoint-Systemseite verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0e02-113">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="b0e02-114">Wenn Sie eine SharePoint-Website Seite mit dem Tool „Seitendiagnose für SharePoint“ analysieren, finden Sie Informationen zu externen Aufrufen im **Anforderungen für SharePoint** Ergebnis im Bereich _Diagnosetests_.</span><span class="sxs-lookup"><span data-stu-id="b0e02-114">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about external calls in the **Requests to SharePoint** result in the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="b0e02-115">Die Zeile wird grün angezeigt, wenn die Standortseite weniger als die Grundwert-Nummer der Aufrufe enthält, und rot, wenn die Seite die Grundwert-Nummer überschreitet.</span><span class="sxs-lookup"><span data-stu-id="b0e02-115">The line will appear in green if the site page contains fewer than the baseline number of calls, and red if the page exceeds the baseline number.</span></span> <span data-ttu-id="b0e02-116">Die Grundwert-Nummer ist für moderne und klassische Seiten unterschiedlich, da klassische Seiten HTTP1.1 und moderne Seiten HTTP2.0 verwenden:</span><span class="sxs-lookup"><span data-stu-id="b0e02-116">The baseline number is different for modern and classic pages because classic site pages use HTTP1.1 and modern pages use HTTP2.0:</span></span>

- <span data-ttu-id="b0e02-117">Moderne Seiten der Website sollten nicht mehr als **25** Aufrufe enthalten.</span><span class="sxs-lookup"><span data-stu-id="b0e02-117">Modern site pages should contain no more than **25** calls</span></span>
- <span data-ttu-id="b0e02-118">Klassische Veröffentlichungsseiten sollten nicht mehr als **6** Aufrufe enthalten.</span><span class="sxs-lookup"><span data-stu-id="b0e02-118">Classic publishing pages should contain no more than **6** calls</span></span>

<span data-ttu-id="b0e02-119">Mögliche Ergebnisse beinhalten:</span><span class="sxs-lookup"><span data-stu-id="b0e02-119">Possible results include:</span></span>

- <span data-ttu-id="b0e02-120">**Aktion erforderlich** (rot): Die Seite überschreitet den Grundwert der Anfragen.</span><span class="sxs-lookup"><span data-stu-id="b0e02-120">**Attention required** (red): The page exceeds the baseline number of calls</span></span>
- <span data-ttu-id="b0e02-121">**Keine Aktion erforderlich** (grün): Die Seite enthält weniger als den Grundwert der Anfragen.</span><span class="sxs-lookup"><span data-stu-id="b0e02-121">**No action required** (green): The page contains fewer than the baseline number of calls</span></span>

<span data-ttu-id="b0e02-122">Wenn das Ergebnis **Anforderungen für SharePoint** im Abschnitt **Aktion erforderlich** erscheint, können Sie auf das Ergebnis klicken, um Details zu erhalten, einschließlich der Gesamtzahl der Aufrufe auf der Seite und einer Liste der URLs.</span><span class="sxs-lookup"><span data-stu-id="b0e02-122">If the **Requests to SharePoint** result appears in the **Attention required** section, you can click the result for details, including the total number of calls on the page and a list of the URLs.</span></span>

![Anforderungen für SharePoint-Ergebnisse](../media/modern-portal-optimization/pagediag-requests.png)

## <a name="remediate-performance-issues-related-to-too-many-calls-on-a-page"></a><span data-ttu-id="b0e02-124">Beheben von Leistungsproblemen im Zusammenhang mit zu vielen Aufrufen auf einer Seite</span><span class="sxs-lookup"><span data-stu-id="b0e02-124">Remediate performance issues related to too many calls on a page</span></span>

<span data-ttu-id="b0e02-125">Wenn eine Seite zu viele Aufrufe enthält, können Sie anhand der Liste der URLs in den Ergebnissen der **Anforderungen für Sharepoint** feststellen, ob es sich um wiederholte Aufrufe, Aufrufe, die gebündelt werden sollen, oder Aufrufe handelt, die Daten zurückgeben, die zwischengespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0e02-125">If a page contains too many calls, you can use the list of URLs in the **Requests to Sharepoint** results to determine whether there are any repeated calls, calls that should be batched, or calls that return data that should be cached.</span></span>

<span data-ttu-id="b0e02-126">**Die Batchverarbeitung von REST-Aufrufen** kann dazu beitragen, den Verwaltungsaufwand zu verringern.</span><span class="sxs-lookup"><span data-stu-id="b0e02-126">**Batching REST calls** can help to reduce performance overhead.</span></span> <span data-ttu-id="b0e02-127">Weitere Informationen über die Batchverarbeitung von API-Aufrufen finden Sie unter [Erstellen von Batchanforderungen mit den REST-APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span><span class="sxs-lookup"><span data-stu-id="b0e02-127">For more information about API call batching, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span></span>

<span data-ttu-id="b0e02-128">**Die Verwendung eines Caches** zum Speichern der Ergebnisse eines API-Aufrufs kann die Leistung einer warmen Anforderung verbessern, indem der Client die zwischengespeicherten Daten verwenden kann, anstatt für jeden nachfolgenden Seitenaufruf einen zusätzlichen Aufruf zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="b0e02-128">**Using a cache** to store the results of an API call can improve the performance of a warm request by allowing the client to use the cached data instead of making an additional call for each subsequent page load.</span></span> <span data-ttu-id="b0e02-129">Je nach Geschäftsanforderung gibt es verschiedene Möglichkeiten, diese Lösung anzugehen.</span><span class="sxs-lookup"><span data-stu-id="b0e02-129">There are multiple ways to approach this solution depending on the business requirement.</span></span> <span data-ttu-id="b0e02-130">Wenn die Daten für alle Benutzer gleich sind, ist die Verwendung eines Middle-Tier-Caching-Dienstes wie [_Azure Redis_ Cache](https://azure.microsoft.com/services/cache/) eine gute Option, um den API-Verkehr mit einer Website deutlich zu reduzieren, da die Benutzer die Daten vom Caching-Dienst statt direkt vom SPO anfordern würden.</span><span class="sxs-lookup"><span data-stu-id="b0e02-130">Typically if the data will be the same for all users, using a middle-tier caching service like [_Azure Redis_ cache](https://azure.microsoft.com/services/cache/) is a great option to significantly reduce API traffic against a site, as the users would request the data from the caching service instead of directly from SPO.</span></span> <span data-ttu-id="b0e02-131">Die einzigen SPO-Aufrufe, die benötigt werden, sind das Aktualisieren des Middle-Tier-Cache.</span><span class="sxs-lookup"><span data-stu-id="b0e02-131">The only SPO calls needed would be to refresh the middle-tier's cache.</span></span> <span data-ttu-id="b0e02-132">Wenn die Daten je nach Benutzer variieren, kann es sinnvoll sein, einen clientseitigen Cache wie LocalStorage oder sogar ein Cookie zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="b0e02-132">If the data will fluctuate on an individual user basis, it may be best to implement a client side cache, like LocalStorage or even a Cookie.</span></span> <span data-ttu-id="b0e02-133">Dies reduziert dennoch das Anrufvolumen, indem nachfolgende Anforderungen durch den gleichen Benutzer für die Cachedauer beseitigt werden, ist aber weniger effizient als ein spezieller Caching-Dienst.</span><span class="sxs-lookup"><span data-stu-id="b0e02-133">This will still reduce call volumes by eliminating subsequent requests made by the same user for the cache duration, but will be less efficient than a dedicated caching service.</span></span> <span data-ttu-id="b0e02-134">PnP ermöglicht es Ihnen, LocalStorage mit geringem Entwicklungsaufwand zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="b0e02-134">PnP allows you to use LocalStorage with little additional development required.</span></span>

<span data-ttu-id="b0e02-135">Bevor Sie Seitenrevisionen zur Behebung von Leistungsproblemen durchführen, notieren Sie sich die Ladezeit der Seite in den Analyseergebnissen.</span><span class="sxs-lookup"><span data-stu-id="b0e02-135">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="b0e02-136">Führen Sie das Tool nach Ihrer Revision erneut aus, um zu sehen, ob das neue Ergebnis innerhalb des Grenzwertes liegt, und überprüfen Sie die Ladezeit der neuen Seite, um festzustellen, ob eine Verbesserung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="b0e02-136">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Ergebnisse der Seitenladezeiten](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="b0e02-138">Die Seitenladezeit kann aufgrund einer Vielzahl von Faktoren wie Netzwerklast, Tageszeit und anderen vorübergehenden Schwierigkeiten variieren.</span><span class="sxs-lookup"><span data-stu-id="b0e02-138">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="b0e02-139">Sie sollten die Seitenladezeit einige Male vor und nach der Durchführung von Änderungen testen, um einen Mittelwert zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="b0e02-139">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b0e02-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b0e02-140">Related topics</span></span>

[<span data-ttu-id="b0e02-141">Optimieren der Leistung von SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0e02-141">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="b0e02-142">Optimieren der Leistung von Office 365</span><span class="sxs-lookup"><span data-stu-id="b0e02-142">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="b0e02-143">Leistung in der modernen SharePoint-Oberfläche</span><span class="sxs-lookup"><span data-stu-id="b0e02-143">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)

[<span data-ttu-id="b0e02-144">Netzwerke für die Inhaltsübermittlung</span><span class="sxs-lookup"><span data-stu-id="b0e02-144">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="b0e02-145">Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0e02-145">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
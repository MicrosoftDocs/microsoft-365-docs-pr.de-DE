---
title: Optimieren Sie die Seitenstärke von modernen Websiteseiten in SharePoint Online
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
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: Erfahren Sie, wie Sie das Seiten Diagnosetool verwenden, um die Seitengewichtung in SharePoint Online modernen Website Seiten zu optimieren.
ms.openlocfilehash: 64fb3c90db78a23c7f1c3fcfe604c8ef58703be0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690335"
---
# <a name="optimize-page-weight-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="b42c1-103">Optimieren Sie die Seitenstärke von modernen Websiteseiten in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b42c1-103">Optimize page weight in SharePoint Online modern site pages</span></span>

<span data-ttu-id="b42c1-104">Die modernen Websiteseiten von SharePoint Online enthalten serialisierten Code, der erforderlich ist, um den Seiteninhalt der Seite darzustellen, einschließlich Bilder, Text, Objekte im Inhaltsbereich unter der Navigations-/Befehlsleiste und anderen HTML-Code, der den Rahmen der Seite bildet.</span><span class="sxs-lookup"><span data-stu-id="b42c1-104">SharePoint Online modern site pages contain serialized code that is required to render page content of the page, including images, text, objects in the content area underneath navigation/command bars and other HTML code that forms the framework of the page.</span></span> <span data-ttu-id="b42c1-105">Die Seitenstärke ist eine Maßeinheit für diesen HTML-Code und sollte begrenzt sein, um optimale Seitenladezeiten sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="b42c1-105">Page weight is a measurement of this HTML code, and should be limited to ensure optimal page load times.</span></span>

<span data-ttu-id="b42c1-106">Dieser Artikel wird Ihnen helfen zu verstehen, wie Sie die Seitenstärke in Ihren modernen Websiteseiten reduzieren können.</span><span class="sxs-lookup"><span data-stu-id="b42c1-106">This article will help you understand how to reduce page weight in your modern site pages.</span></span>

>[!NOTE]
><span data-ttu-id="b42c1-107">Weitere Informationen zur Leistung in modernen SharePoint Online-Portalen finden Sie unter [Leistung in der modernen SharePoint-Umgebung](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="b42c1-107">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-weight"></a><span data-ttu-id="b42c1-108">Verwenden Sie das Tool „Seitendiagnose für SharePoint“, um die Seitenstärke zu analysieren</span><span class="sxs-lookup"><span data-stu-id="b42c1-108">Use the Page Diagnostics for SharePoint tool to analyze page weight</span></span>

<span data-ttu-id="b42c1-109">Das Tool "Seitendiagnose für SharePoint" ist eine Browsererweiterung für das neue Microsoft Edge (https://www.microsoft.com/edge) und Chrome, mit der Sie SharePoint-Seiten sowohl in modernen Portal- als auch in klassischen Veröffentlichungs-Websites analysieren können.</span><span class="sxs-lookup"><span data-stu-id="b42c1-109">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="b42c1-110">Das Tool stellt für jede analysierte Seite einen Bericht bereit, in dem die Leistung der Seite anhand einer definierten Gruppe von Leistungskriterien dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b42c1-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="b42c1-111">Wenn Sie das Tool "Seitendiagnose für SharePoint" installieren und mehr darüber erfahren möchten, besuchen Sie [Verwenden des Seitendiagnose-Tools für SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="b42c1-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="b42c1-112">Das Seitendiagnose-Tool funktioniert nur für SharePoint Online und kann nicht auf einer SharePoint-Systemseite verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b42c1-112">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="b42c1-113">Wenn Sie eine SharePoint-Websiteseite mit dem Tool für die Seitendiagnose für SharePoint analysieren, sehen Sie Informationen über die Seite im Ergebnis **Seitenstärke unter 500 KB** des Bereichs _Diagnosetests_.</span><span class="sxs-lookup"><span data-stu-id="b42c1-113">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about page in the **Page weight under 500KB** result of the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="b42c1-114">Das Ergebnis wird grün angezeigt, wenn die Seitenstärke unter dem Basiswert liegt, und rot, wenn die Seitenstärke den Basiswert überschreitet.</span><span class="sxs-lookup"><span data-stu-id="b42c1-114">The result will appear in green if the page weight is under the baseline value, and red if the page weight exceeds the baseline value.</span></span>

<span data-ttu-id="b42c1-115">Mögliche Ergebnisse beinhalten:</span><span class="sxs-lookup"><span data-stu-id="b42c1-115">Possible results include:</span></span>

- <span data-ttu-id="b42c1-116">**Aufmerksamkeit erforderlich** (rot): Die Seitenstärke überschreitet 500 KB</span><span class="sxs-lookup"><span data-stu-id="b42c1-116">**Attention required** (red): Page weight exceeds 500KB</span></span>
- <span data-ttu-id="b42c1-117">**Keine Aktion erforderlich** (grün): Die Seitenstärke liegt unter 500 KB</span><span class="sxs-lookup"><span data-stu-id="b42c1-117">**No action required** (green): Page weight is under 500KB</span></span>

<span data-ttu-id="b42c1-118">Wenn das Ergebnis **Seitenstärke unter 500 KB** im Abschnitt **Aufmerksamkeit erforderlich** angezeigt wird, können Sie auf das Ergebnis klicken, um Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b42c1-118">If the **Page weight under 500KB** result appears in the **Attention required** section, you can click the result for details.</span></span>

![Anforderungen für SharePoint-Ergebnisse](../media/modern-portal-optimization/pagediag-page-weight.png)

## <a name="remediate-page-weight-issues"></a><span data-ttu-id="b42c1-120">Beheben von Problemen mit der Seitenstärke</span><span class="sxs-lookup"><span data-stu-id="b42c1-120">Remediate page weight issues</span></span>

<span data-ttu-id="b42c1-121">Wenn die Seitenstärke 500 KB überschreitet, können Sie die Gesamtladezeit der Seite verbessern, indem Sie die Anzahl der Webparts reduzieren und den Seiteninhalt auf ein angemessenes Maß beschränken.</span><span class="sxs-lookup"><span data-stu-id="b42c1-121">If page weight exceeds 500KB, you can improve overall page load time by reducing the number of web parts and limiting page content to an appropriate degree.</span></span>

<span data-ttu-id="b42c1-122">Allgemeine Anleitungen zum Reduzieren der Seitenstärke umfassen:</span><span class="sxs-lookup"><span data-stu-id="b42c1-122">General guidance for reducing page weight includes:</span></span>

- <span data-ttu-id="b42c1-123">Beschränken Sie den Seiteninhalt auf eine angemessene Menge und verwenden Sie mehrere Seiten für verwandte Inhalte.</span><span class="sxs-lookup"><span data-stu-id="b42c1-123">Limit the page content to a reasonable amount and use multiple pages for related content.</span></span>
- <span data-ttu-id="b42c1-124">Minimieren Sie den Einsatz von Webparts mit großen Eigenschaftenbehälter.</span><span class="sxs-lookup"><span data-stu-id="b42c1-124">Minimize the use of web parts that have large property bags.</span></span>
- <span data-ttu-id="b42c1-125">Verwenden Sie nach Möglichkeit nicht interaktive Rollup-Ansichten.</span><span class="sxs-lookup"><span data-stu-id="b42c1-125">Use non-interactive rollup views when possible.</span></span>
- <span data-ttu-id="b42c1-126">Optimieren Sie die Bildgrößen, indem Sie die Bilder entsprechend dimensionieren, komprimierte Bildformate verwenden und sicherstellen, dass sie von einem CDN heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="b42c1-126">Optimize image sizes by sizing images appropriately, using compressed image formats and ensuring that they are downloaded from a CDN.</span></span>

<span data-ttu-id="b42c1-127">Weitere Anleitungen zum Einschränken der Seitenstärke finden Sie im folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="b42c1-127">You can find additional guidance for limiting page weight in the following article:</span></span>

- [<span data-ttu-id="b42c1-128">Optimieren der Seitenleistung in SharePoint</span><span class="sxs-lookup"><span data-stu-id="b42c1-128">Optimize page performance in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint)

<span data-ttu-id="b42c1-129">Bevor Sie Seitenrevisionen zur Behebung von Leistungsproblemen durchführen, notieren Sie sich die Ladezeit der Seite in den Analyseergebnissen.</span><span class="sxs-lookup"><span data-stu-id="b42c1-129">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="b42c1-130">Führen Sie das Tool nach Ihrer Revision erneut aus, um zu sehen, ob das neue Ergebnis innerhalb des Grenzwertes liegt, und überprüfen Sie die Ladezeit der neuen Seite, um festzustellen, ob eine Verbesserung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="b42c1-130">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Ergebnisse der Seitenladezeiten](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="b42c1-132">Die Seitenladezeit kann aufgrund einer Vielzahl von Faktoren wie Netzwerklast, Tageszeit und anderen vorübergehenden Schwierigkeiten variieren.</span><span class="sxs-lookup"><span data-stu-id="b42c1-132">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="b42c1-133">Sie sollten die Seitenladezeit einige Male vor und nach der Durchführung von Änderungen testen, um einen Mittelwert zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="b42c1-133">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b42c1-134">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b42c1-134">Related topics</span></span>

[<span data-ttu-id="b42c1-135">Optimieren der Leistung von SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b42c1-135">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="b42c1-136">Optimieren der Leistung von Office 365</span><span class="sxs-lookup"><span data-stu-id="b42c1-136">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="b42c1-137">Leistung in der modernen SharePoint-Oberfläche</span><span class="sxs-lookup"><span data-stu-id="b42c1-137">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="b42c1-138">Netzwerke für die Inhaltsübermittlung</span><span class="sxs-lookup"><span data-stu-id="b42c1-138">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="b42c1-139">Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b42c1-139">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

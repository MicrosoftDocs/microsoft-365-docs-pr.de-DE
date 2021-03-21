---
title: Optimieren Sie iFrames für moderne und klassische Veröffentlichungswebsiteseiten von SharePoint Online
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
description: Erfahren Sie, wie Sie die Leistung von iFrames in modernen und klassischen Veröffentlichungswebsiteseiten in SharePoint Online optimieren können.
ms.openlocfilehash: d6e9aefa23972589c752540959b17f5d20ed0889
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923058"
---
# <a name="optimize-iframes-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a><span data-ttu-id="5e3d2-103">Optimieren Sie iFrames für moderne und klassische Veröffentlichungswebsiteseiten von SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5e3d2-103">Optimize iFrames in SharePoint Online modern and classic publishing site pages</span></span>

<span data-ttu-id="5e3d2-104">iFrames können hilfreich sein, wenn Sie umfangreiche Inhalte wie Videos oder andere Medien anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-104">iFrames can be useful for previewing rich content such as videos or other media.</span></span> <span data-ttu-id="5e3d2-105">Da iFrames jedoch eine separate Seite innerhalb der SharePoint-Websiteseite laden, können in den iFrame geladene Inhalte große Bilder, Videos oder andere Elemente enthalten, die zur Gesamtladezeit der Seite beitragen können und die Sie nicht auf der Seite steuern können.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-105">However, because iFrames load a separate page within the SharePoint site page, content loaded in the iFrame could contain large images, videos or other elements that can contribute to overall page load times and that you cannot control on the page.</span></span> <span data-ttu-id="5e3d2-106">In diesem Artikel erfahren Sie, wie Sie die Auswirkungen von iFrames auf Ihren Seiten auf die vom Benutzer empfundene Latenz bestimmen und häufig auftretende Probleme beheben können.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-106">This article will help you understand how to determine how iFrames in your pages affect user perceived latency, and how to remediate common issues.</span></span>

>[!NOTE]
><span data-ttu-id="5e3d2-107">Weitere Informationen zur Leistung in modernen SharePoint Online-Websites finden Sie unter [Leistung in der modernen SharePoint-Umgebung](/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="5e3d2-107">For more information about performance in SharePoint Online modern sites, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts-using-iframes"></a><span data-ttu-id="5e3d2-108">Verwenden des Tools "Seitendiagnose für SharePoint" zum Analysieren von Webparts mithilfe von iFrames</span><span class="sxs-lookup"><span data-stu-id="5e3d2-108">Use the Page Diagnostics for SharePoint tool to analyze web parts using iFrames</span></span>

<span data-ttu-id="5e3d2-109">Das Tool "Seitendiagnose für SharePoint" ist eine Browsererweiterung für das neue Microsoft Edge (https://www.microsoft.com/edge) und Chrome, mit der Sie SharePoint-Seiten sowohl in modernen Portal- als auch in klassischen Veröffentlichungs-Websites analysieren können.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-109">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="5e3d2-110">Das Tool stellt für jede analysierte Seite einen Bericht bereit, in dem die Leistung der Seite anhand einer definierten Gruppe von Leistungskriterien dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="5e3d2-111">Wenn Sie das Tool "Seitendiagnose für SharePoint" installieren und mehr darüber erfahren möchten, besuchen Sie [Verwenden des Seitendiagnose-Tools für SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="5e3d2-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="5e3d2-112">Das Seitendiagnose-Tool funktioniert nur für SharePoint Online und kann nicht auf einer SharePoint-Systemseite verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-112">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="5e3d2-113">Wenn Sie eine SharePoint-Websiteseite mit dem Tool für die Seitendiagnose für SharePoint analysieren, sehen Sie Informationen über die Webparts mit iFrames im Bereich _Diagnosetests_.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-113">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about web parts containing iFrames in the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="5e3d2-114">Die Baseline-Metrik ist für moderne und klassische Websites identisch.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-114">The baseline metric is the same for modern and classic pages.</span></span>

<span data-ttu-id="5e3d2-115">Mögliche Ergebnisse sind:</span><span class="sxs-lookup"><span data-stu-id="5e3d2-115">Possible results include:</span></span>

- <span data-ttu-id="5e3d2-116">**Aufmerksamkeit erforderlich** (rot): Die Seite enthält **drei oder mehr** Webparts mit iFrames</span><span class="sxs-lookup"><span data-stu-id="5e3d2-116">**Attention required** (red): The page contains **three or more** web parts using iFrames</span></span>
- <span data-ttu-id="5e3d2-117">**Verbesserungsmöglichkeiten** (gelb): Die Seite enthält **ein oder zwei** Webparts mit iFrames</span><span class="sxs-lookup"><span data-stu-id="5e3d2-117">**Improvement opportunities** (yellow): The page contains **one or two** web parts using iFrames</span></span>
- <span data-ttu-id="5e3d2-118">**Keine Aktion erforderlich** (grün): Die Seite enthält keine Webparts mit iFrames</span><span class="sxs-lookup"><span data-stu-id="5e3d2-118">**No action required** (green): The page contains no web parts using iFrames</span></span>

<span data-ttu-id="5e3d2-119">Wenn das Ergebnis **Webparts mit iFrames erkannt** entweder im Abschnitt **Verbesserungsmöglichkeiten** oder **Aufmerksamkeit erforderlich** der Ergebnisse erscheint, können Sie auf das Ergebnis klicken, um die Webparts anzuzeigen, die iFrames enthalten.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-119">If the **Web parts using iFrames detected** result appears in either the **Improvement opportunities** or **Attention required)** section of the results, you can click the result to see the web parts that contain iFrames.</span></span>

![Tool für die Seitendiagnose – Ergebnisse](../media/modern-portal-optimization/pagediag-iframe-yellow.png)

## <a name="remediate-iframe-performance-issues"></a><span data-ttu-id="5e3d2-121">Beheben von Problemen mit der Leistung von iFrame</span><span class="sxs-lookup"><span data-stu-id="5e3d2-121">Remediate iFrame performance issues</span></span>

<span data-ttu-id="5e3d2-122">Verwenden Sie das Ergebnis **Webparts mit iFrames erkannt** im Tool "Seitendiagnose", um festzustellen, welche Webparts iFrames enthalten und möglicherweise zu langsameren Seitenladezeiten beitragen.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-122">Use the **Web parts using iFrames detected** result in the Page Diagnostic tool to determine which web parts contain iFrames and may be contributing to slow page load times.</span></span>

<span data-ttu-id="5e3d2-123">iFrames sind von Natur aus langsam, da sie eine separate externe Seite laden, die alle zugehörigen Inhalte wie Javascript, CSS und Framework-Elemente enthält, was den Overhead der Seiten um den Faktor zwei oder mehr erhöhen kann.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-123">iFrames are inherently slow because they load a separate external page including all associated content such as javascript, CSS and framework elements, potentially increasing the overhead of the site page by a factor of two or more.</span></span>

<span data-ttu-id="5e3d2-124">Folgen Sie den nachstehenden Anleitungen, um die optimale Verwendung von iFrames zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-124">Follow the guidance below to ensure optimal use of iFrames.</span></span>

- <span data-ttu-id="5e3d2-125">Verwenden Sie nach Möglichkeit Bilder anstelle von iFrames, wenn die Vorschau zunächst klein oder nicht interaktiv ist.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-125">When possible, use images instead of iFrames if the preview is small to begin with or non-interactive.</span></span>
- <span data-ttu-id="5e3d2-126">Wenn iFrames verwendet werden müssen, minimieren Sie die Anzahl und/oder verschieben Sie diese aus dem Ansichtsfenster.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-126">If iFrames must be used, minimize the number and/or move them out of the viewport.</span></span>
- <span data-ttu-id="5e3d2-127">Eingebettete Office-Dateien wie Word, Excel und PowerPoint, sind interaktiv, aber werden nur langsam geladen.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-127">Embedded Office files like Word, Excel and PowerPoint are interactive, but are slow to load.</span></span> <span data-ttu-id="5e3d2-128">Bildminiaturansichten mit einem Link zum vollständigen Dokument werden häufig besser ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-128">Image thumbnails with a link to the full document will often perform better.</span></span>
- <span data-ttu-id="5e3d2-129">Eingebettete YouTube-Videos und Twitter-Feeds sind in der Regel besser in iFrames, aber verwenden Sie diese Arten von Einbettungen mit Bedacht.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-129">Embedded YouTube videos and Twitter feeds tend to perform better in iFrames, but use these kinds of embeds judiciously.</span></span>
- <span data-ttu-id="5e3d2-130">Isolierte Webparts sind eine vernünftige Ausnahme, verringern aber deren Anzahl und Position im Ansichtsbereich.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-130">Isolated web parts are a reasonable exception, but minimize their number and placement in the viewport.</span></span>
- <span data-ttu-id="5e3d2-131">Wenn sich ein iFrame außerhalb des Ansichtsfensters befindet, sollten Sie einen _IntersectionObserver_ verwenden, um das Rendern des iFrame zu verzögern, bis er in Sicht kommt.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-131">If an iFrame is located out of the viewport, consider using an _IntersectionObserver_ to delay rendering the iFrame until it comes into view.</span></span>

<span data-ttu-id="5e3d2-132">Bevor Sie Seitenrevisionen zur Behebung von Leistungsproblemen durchführen, notieren Sie sich die Ladezeit der Seite in den Analyseergebnissen.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-132">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="5e3d2-133">Führen Sie das Tool nach Ihrer Revision erneut aus, um zu sehen, ob das neue Ergebnis innerhalb des Grenzwertes liegt, und überprüfen Sie die Ladezeit der neuen Seite, um festzustellen, ob eine Verbesserung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-133">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Ergebnisse der Seitenladezeiten](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="5e3d2-135">Die Seitenladezeit kann aufgrund einer Vielzahl von Faktoren wie Netzwerklast, Tageszeit und anderen vorübergehenden Schwierigkeiten variieren.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-135">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="5e3d2-136">Sie sollten die Seitenladezeit einige Male vor und nach der Durchführung von Änderungen testen, um einen Mittelwert zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="5e3d2-136">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5e3d2-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="5e3d2-137">Related topics</span></span>

[<span data-ttu-id="5e3d2-138">Optimieren der Leistung von SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5e3d2-138">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="5e3d2-139">Optimieren der Leistung von Office 365</span><span class="sxs-lookup"><span data-stu-id="5e3d2-139">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="5e3d2-140">Leistung in der modernen SharePoint-Oberfläche</span><span class="sxs-lookup"><span data-stu-id="5e3d2-140">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)
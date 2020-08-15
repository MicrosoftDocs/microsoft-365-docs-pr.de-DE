---
title: Optimieren der Leistung von Webparts in modernen SharePoint Online-Websites
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: Admin
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
description: In diesem Artikel erfahren Sie, wie Sie mithilfe der Seiten Diagnose die Leistung von Webparts in SharePoint Online modernen Website Seiten optimieren.
ms.openlocfilehash: 7dcfcbfe033ef5f4257cc9688b61aca3227ade8b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690574"
---
# <a name="optimize-web-part-performance-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="be71b-103">Optimieren der Leistung von Webparts in modernen SharePoint Online-Websites</span><span class="sxs-lookup"><span data-stu-id="be71b-103">Optimize web part performance in SharePoint Online modern site pages</span></span>

<span data-ttu-id="be71b-104">Die Seiten von modernen SharePoint Online-Website enthalten Webparts, die sich auf die allgemeinen Seitenladezeiten auswirken können.</span><span class="sxs-lookup"><span data-stu-id="be71b-104">SharePoint Online modern site pages contain web parts that can contribute to overall page load times.</span></span> <span data-ttu-id="be71b-105">In diesem Artikel erfahren Sie, wie Sie die Auswirkungen von Webparts auf Ihren Seiten auf die vom Benutzer empfundene Latenz bestimmen und häufig auftretende Probleme beheben können.</span><span class="sxs-lookup"><span data-stu-id="be71b-105">This article will help you understand how to determine how web parts in your pages affect user perceived latency, and how to remediate common issues.</span></span>

>[!NOTE]
><span data-ttu-id="be71b-106">Weitere Informationen zur Leistung in modernen SharePoint Online-Portalen finden Sie unter [Leistung in der modernen SharePoint-Umgebung](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="be71b-106">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts"></a><span data-ttu-id="be71b-107">Verwenden des Tools "Seitendiagnose für SharePoint" zum Analysieren von Webparts</span><span class="sxs-lookup"><span data-stu-id="be71b-107">Use the Page Diagnostics for SharePoint tool to analyze web parts</span></span>

<span data-ttu-id="be71b-108">Das Tool "Seitendiagnose für SharePoint" ist eine Browsererweiterung für neue Microsoft Edge- (https://www.microsoft.com/edge) und Chrome-Browser, mit der Sie SharePoint Online-Seiten sowohl in modernen Portal- als auch in klassischen Veröffentlichungs-Websites analysieren können.</span><span class="sxs-lookup"><span data-stu-id="be71b-108">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="be71b-109">Das Tool stellt für jede analysierte Seite einen Bericht bereit, in dem die Leistung der Seite anhand einer definierten Gruppe von Leistungskriterien dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="be71b-109">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="be71b-110">Wenn Sie das Tool "Seitendiagnose für SharePoint" installieren und mehr darüber erfahren möchten, besuchen Sie [Verwenden des Seitendiagnose-Tools für SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="be71b-110">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="be71b-111">Das Seitendiagnose-Tool funktioniert nur für SharePoint Online und kann nicht auf einer SharePoint-Systemseite verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be71b-111">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="be71b-112">Wenn Sie eine Seite einer SharePoint-Website mit dem Tool "Seitendiagnose für SharePoint" analysieren, werden im Ergebnis **Webparts, die sich auf die Seitenladezeit auswirken** im Bereich _Diagnosetests_ Informationen über Webparts angezeigt, die die Baselinemetrik überschreiten.</span><span class="sxs-lookup"><span data-stu-id="be71b-112">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about web parts that exceed the baseline metric in the **Web parts are impacting page load time** result in the _Diagnostic tests_ pane.</span></span>

<span data-ttu-id="be71b-113">Mögliche Ergebnisse sind:</span><span class="sxs-lookup"><span data-stu-id="be71b-113">Possible results include:</span></span>

- <span data-ttu-id="be71b-114">**Handlungsbedarf** (rot): alle _benutzerdefinierten_-Webparts, die im Ansichtsfenster (dem sichtbaren Bereich des Bildschirms, der zuerst geladen wird) sichtbar sind und zum Laden länger als **zwei** Sekunden benötigen.</span><span class="sxs-lookup"><span data-stu-id="be71b-114">**Attention required** (red): Any _custom_ web part that is visible in the viewport (screen visible portion of the page which is loaded first) that takes longer than **two** seconds to load.</span></span> <span data-ttu-id="be71b-115">Alle _benutzerdefinierten_ Webparts außerhalb des Ansichtsfensters, die zum Laden länger als **vier** Sekunden benötigen.</span><span class="sxs-lookup"><span data-stu-id="be71b-115">Any _custom_ web parts outside of the viewport that take longer than **four** seconds to load.</span></span> <span data-ttu-id="be71b-116">Die Gesamtladezeit wird in den Testergebnissen angezeigt und nach "Modul laden", "Lazy Load", "Initialisieren" und "Rendern" unterteilt.</span><span class="sxs-lookup"><span data-stu-id="be71b-116">Total load time is displayed in test results and is broken down by module load, lazy load, init and render.</span></span>
- <span data-ttu-id="be71b-117">**Verbesserung möglich** (gelb): Elemente, die sich möglicherweise auf die Seitenladezeit auswirken, werden in diesem Abschnitt angezeigt und sollten überprüft und überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="be71b-117">**Improvement opportunities** (yellow): Items that may be impacting page load time are shown in this section and should be reviewed and monitored.</span></span> <span data-ttu-id="be71b-118">Dazu können Microsoft-"Out-of-Box"-Webparts (OOTB) gehören.</span><span class="sxs-lookup"><span data-stu-id="be71b-118">This may include "out of the box" (OOTB) Microsoft web parts.</span></span> <span data-ttu-id="be71b-119">Die Ergebnisse für alle in diesem Abschnitt angezeigten Microsoft-Webparts werden automatisch an Microsoft gemeldet, daher **sind keine Maßnahmen erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="be71b-119">Results for any Microsoft web parts shown in this section are automatically reported to Microsoft, so **no action is required**.</span></span> <span data-ttu-id="be71b-120">Sie sollten nur dann ein Supportticket für die Untersuchung öffnen, wenn die Leistung auf der Seite sehr schlecht ist und **alle Microsoft-Webparts** auf der Seite in den Ergebnissen im Abschnitt **Verbesserung möglich** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="be71b-120">You should only log a support ticket for investigation if you are experiencing very slow performance on the page and **all Microsoft web parts** on the page appear in the results in the **Improvement opportunities** section.</span></span> <span data-ttu-id="be71b-121">Beachten Sie, dass die Ergebnisse in einem künftigen Update der Seitendiagnose für SharePoint auf Grundlage der spezifischen Konfiguration des Microsoft-Webparts weiter aufgeschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="be71b-121">Note that a future Page Diagnostics for SharePoint tool update will further break down the results based on the specific configuration of the Microsoft web part.</span></span>
- <span data-ttu-id="be71b-122">**Keine Aktion erforderlich** (grün): Kein Webpart braucht länger als **zwei** Sekunden, um Daten zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="be71b-122">**No action required** (green): No web part is taking longer than **two** seconds to return data.</span></span>

<span data-ttu-id="be71b-123">Wenn das Ergebnis **Webparts, die sich auf die Seitenladezeit auswirken** entweder im Abschnitt **Handlungsbedarf** oder im Abschnitt **Verbesserung möglich** angezeigt wird, klicken Sie auf das Ergebnis, um Details zu den Webparts anzuzeigen, die langsam geladen werden.</span><span class="sxs-lookup"><span data-stu-id="be71b-123">If the **Web parts are impacting page load time** result appears in either the **Attention required** or **Improvement opportunities** section of the results, click the result to see details about which web parts are loading slowly.</span></span> <span data-ttu-id="be71b-124">Zukünftige Updates des Tools "Seitendiagnose für SharePoint" können Aktualisierungen der Analyseregeln enthalten. Stellen Sie daher sicher, dass Sie immer über die neueste Version des Tools verfügen.</span><span class="sxs-lookup"><span data-stu-id="be71b-124">Future updates to the Page Diagnostics for SharePoint tool may include updates to analysis rules, so please ensure you always have the latest version of the tool.</span></span>

![Ergebnisse der Seitendiagnose-Tools](../media/modern-portal-optimization/pagediag-web-part.png)

<span data-ttu-id="be71b-126">Die verfügbaren Informationen in den Ergebnissen umfassen:</span><span class="sxs-lookup"><span data-stu-id="be71b-126">Information available in the results includes:</span></span>

- <span data-ttu-id="be71b-127">**Erstellt von** zeigt an, ob es sich bei dem Webpart um ein benutzerdefiniertes oder ein Microsoft-OOTB-Webpart handelt.</span><span class="sxs-lookup"><span data-stu-id="be71b-127">**Made by** shows whether the web part is custom or Microsoft OOTB</span></span>
- <span data-ttu-id="be71b-128">**Name und ID** zeigt identifizierende Informationen an, die Ihnen beim Auffinden des Webparts auf der Seite helfen können.</span><span class="sxs-lookup"><span data-stu-id="be71b-128">**Name and ID** shows identifying information that can help you find the web part on the page</span></span>
- <span data-ttu-id="be71b-129">**Gesamt** zeigt die Gesamtzeit für das Laden des Webparts an.</span><span class="sxs-lookup"><span data-stu-id="be71b-129">**Total** shows the total time for the web part to load</span></span>
- <span data-ttu-id="be71b-130">**Modul laden** zeigt die Zeit an, die zum Abrufen und Laden der Webpartkomponenten benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="be71b-130">**Module Load** shows the time taken to fetch and load the web part components</span></span>
- <span data-ttu-id="be71b-131">**Lazy Load** zeigt die Zeit für das verzögerte Laden von Webparts an, die im Hauptabschnitt der Seite nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="be71b-131">**Lazy Load** shows the time for deferred loading of web parts not seen in the main section of the page</span></span>
- <span data-ttu-id="be71b-132">**Initialisieren** zeigt die Zeit an, die für das Initialisieren eines Webparts benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="be71b-132">**Init** shows the time taken for web part initialization</span></span>
- <span data-ttu-id="be71b-133">**Rendern** zeigt die Zeit an, die das Webpart zum Abrufen und Rendern von Ergebnissen benötigt.</span><span class="sxs-lookup"><span data-stu-id="be71b-133">**Render** shows the time taken for the web part to fetch and render results</span></span>

<span data-ttu-id="be71b-134">Diese Informationen dienen Designern und Entwicklern zum Beheben von Problemen.</span><span class="sxs-lookup"><span data-stu-id="be71b-134">This information is provided to help designers and developers troubleshoot issues.</span></span> <span data-ttu-id="be71b-135">Diese Informationen sollten Ihrem Entwurfs- und Entwicklungsteam bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="be71b-135">This information should be provided to your design and development team.</span></span>

## <a name="remediate-web-part-performance-issues"></a><span data-ttu-id="be71b-136">Beheben von Problemen mit der Leistung von Webparts</span><span class="sxs-lookup"><span data-stu-id="be71b-136">Remediate web part performance issues</span></span>

<span data-ttu-id="be71b-137">Befolgen Sie die Anweisungen in diesem Abschnitt, um Leistungsprobleme mit Webparts zu erkennen und zu beheben, die in den Ergebnissen **Webparts, die sich auf die Seitenladezeit auswirken** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="be71b-137">Follow the guidance in this section to identify and remediate performance issues with web parts listed in the **Web parts are impacting page load time** results.</span></span>

<span data-ttu-id="be71b-138">Es gibt drei Kategorien möglicher Ursachen für eine schlechte Webpartleistung.</span><span class="sxs-lookup"><span data-stu-id="be71b-138">There are three categories of possible causes for poor web part performance.</span></span> <span data-ttu-id="be71b-139">Verwenden Sie die folgenden Informationen, um zu bestimmen, welche Probleme auf Ihr Szenario zutreffen, und um diese zu beheben.</span><span class="sxs-lookup"><span data-stu-id="be71b-139">Use the information below to determine which issues apply to your scenario and remediate them.</span></span>

- <span data-ttu-id="be71b-140">Skriptgröße und Abhängigkeiten von Webparts</span><span class="sxs-lookup"><span data-stu-id="be71b-140">Web part script size and dependencies</span></span>
  - <span data-ttu-id="be71b-141">Optimieren des anfänglichen Skripts, mit dem das Hauptszenario für _Nur Ansichtsmodus_ gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="be71b-141">Optimize the initial script that renders the mainline scenario for _view mode only_.</span></span>
  - <span data-ttu-id="be71b-142">Verschieben Sie die weniger häufigen Szenarien und den Code für den Bearbeitungsmodus (z. B. den Eigenschaftenbereich) mithilfe der _import()_-Anweisung in separate Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="be71b-142">Move the less frequent scenarios and edit mode code (like the property pane) to separate chunks using the _import()_ statement.</span></span>
  - <span data-ttu-id="be71b-143">Überprüfen Sie die Abhängigkeiten der Datei _package.json_, um sämtlichen ungenutzten Code vollständig zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="be71b-143">Review dependencies of the _package.json_ file to remove any dead code completely.</span></span> <span data-ttu-id="be71b-144">Verschieben Sie alle nur auf Test/Build-Versionen bezogenen Abhängigkeiten nach "devDependencies".</span><span class="sxs-lookup"><span data-stu-id="be71b-144">Move any test/build only dependencies to devDependencies.</span></span>
  - <span data-ttu-id="be71b-145">Die Verwendung von Office 365 CDN ist für den optimalen statischen Ressourcendownload erforderlich.</span><span class="sxs-lookup"><span data-stu-id="be71b-145">Use of the Office 365 CDN is required for optimal static resource download.</span></span> <span data-ttu-id="be71b-146">Öffentliche CDN-Quellen sind für _js/css_-Dateien vorzuziehen.</span><span class="sxs-lookup"><span data-stu-id="be71b-146">Public CDN origins are preferable for _js/css_ files.</span></span> <span data-ttu-id="be71b-147">Weitere Informationen zur Verwendung von Office 365 CDN finden Sie unter [Verwendung von Office 365 Content Delivery Network (CDN) mit SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="be71b-147">For more information about using the Office 365 CDN, see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>
  - <span data-ttu-id="be71b-148">Verwenden Sie Frameworks wie _React_ und _Fabric-Importe_, die Bestandteil des SharePoint-Frameworks (SPFx) sind.</span><span class="sxs-lookup"><span data-stu-id="be71b-148">Reuse frameworks like _React_ and _Fabric imports_ that come as part of the SharePoint Framework (SPFx).</span></span> <span data-ttu-id="be71b-149">Weitere Informationen finden Sie unter [Übersicht über das SharePoint-Framework](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview).</span><span class="sxs-lookup"><span data-stu-id="be71b-149">For more information, see [Overview of the SharePoint Framework](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview).</span></span>
  - <span data-ttu-id="be71b-150">Stellen Sie sicher, dass Sie die neueste Version des SharePoint-Frameworks verwenden, und führen Sie stets Aktualisierungen auf neue Versionen durch, sobald diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="be71b-150">Ensure that you are using the latest version of the SharePoint Framework, and upgrade to new versions as they become available.</span></span>
- <span data-ttu-id="be71b-151">Datenabruf/-zwischenspeicherung</span><span class="sxs-lookup"><span data-stu-id="be71b-151">Data fetching/caching</span></span>
  - <span data-ttu-id="be71b-152">Wenn sich das Webpart auf zusätzliche Serveraufrufe stützt, um Daten für die Anzeige abzurufen, stellen Sie sicher, dass diese Server-APIs schnell sind und/oder clientseitige Zwischenspeicherung implementieren ( z. B. die Verwendung von _localStorage_ oder _IndexDB_ für größere Datenmengen).</span><span class="sxs-lookup"><span data-stu-id="be71b-152">If the web part relies on extra server calls to fetch data for display, ensure those server APIs are fast and/or implement client side caching (such as using _localStorage_ or _IndexDB_ for larger sets).</span></span>
  - <span data-ttu-id="be71b-153">Wenn zum Rendern wichtiger Daten mehrere Aufrufe erforderlich sind, sollten Sie die Batchverarbeitung auf dem Server oder andere Methoden zum Konsolidieren von Anforderungen in einen einzigen Anruf erwägen.</span><span class="sxs-lookup"><span data-stu-id="be71b-153">If multiple calls are required to render critical data, consider batching on the server or other methods of consolidating requests to a single call.</span></span>
  - <span data-ttu-id="be71b-154">Wenn bestimmte Datenelemente eine langsamere API benötigen, für das anfängliche Rendern aber nicht kritisch sind, entkoppeln Sie diese mit einem separaten Aufruf, der nach dem Rendern kritischer Daten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="be71b-154">Alternatively, if some elements of data require a slower API, but are not critical to initial rendering, decouple these to a separate call that is executed after critical data is rendered.</span></span>
  - <span data-ttu-id="be71b-155">Wenn mehrere Webparts dieselben Daten nutzen, verwenden Sie eine gemeinsame Datenschicht, um doppelte Aufrufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="be71b-155">If multiple parts use the same data, utilize a common data layer to avoid duplicate calls.</span></span>
- <span data-ttu-id="be71b-156">Renderingzeit</span><span class="sxs-lookup"><span data-stu-id="be71b-156">Rendering time</span></span>
  - <span data-ttu-id="be71b-157">Alle Medienquellen wie Bilder und Videos sollten an die Grenzen des Containers, Geräts und/oder Netzwerks angepasst sein, um das Herunterladen unnötig großer Anlagen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="be71b-157">Any media sources like images and videos should be sized to the limits of the container, device and/or network to avoid downloading unnecessary large assets.</span></span> <span data-ttu-id="be71b-158">Weitere Informationen zu Inhaltsabhängigkeiten finden Sie unter [Verwendung von Office 365 Content Delivery Network (CDN) mit SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="be71b-158">For more information about content dependencies, see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>
  - <span data-ttu-id="be71b-159">Vermeiden Sie API-Aufrufe, die einen Umbruch, komplexe CSS-Regeln oder komplizierte Animationen verursachen.</span><span class="sxs-lookup"><span data-stu-id="be71b-159">Avoid API calls that cause re-flow, complex CSS rules or complicated animations.</span></span> <span data-ttu-id="be71b-160">Weitere Informationen finden Sie unter [Minimizing browser reflow](https://developers.google.com/speed/docs/insights/browser-reflow) (Minimieren von Browserumbrüchen).</span><span class="sxs-lookup"><span data-stu-id="be71b-160">For more information, see [Minimizing browser reflow](https://developers.google.com/speed/docs/insights/browser-reflow).</span></span>
  - <span data-ttu-id="be71b-161">Vermeiden Sie die Verwendung von verketteten Aufgaben mit langen Ausführungszeiten.</span><span class="sxs-lookup"><span data-stu-id="be71b-161">Avoid use of chained long running tasks.</span></span> <span data-ttu-id="be71b-162">Verteilen Sie Aufgaben mit langen Ausführungszeiten stattdessen auf separate Warteschlangen.</span><span class="sxs-lookup"><span data-stu-id="be71b-162">Instead, break long running tasks apart into separate queues.</span></span> <span data-ttu-id="be71b-163">Weitere Informationen finden Sie unter [Optimize JavaScript Execution](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution) (Optimieren der JavaScript-Ausführung).</span><span class="sxs-lookup"><span data-stu-id="be71b-163">For more information, see [Optimize JavaScript Execution](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution).</span></span>
  - <span data-ttu-id="be71b-164">Reservieren Sie entsprechenden Speicherplatz für asynchrones Rendern von Medien oder visuellen Elementen, um übersprungene Frames und Stottern zu vermeiden (auch als _Jank_ bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="be71b-164">Reserve corresponding space for asynchronously rendering media or visual elements to avoid skipped frames and stuttering (also known as _jank_).</span></span>
  - <span data-ttu-id="be71b-165">Wenn ein bestimmter Browser ein für das Rendern verwendetes Feature nicht unterstützt, laden Sie ein Polyfill, oder schließen Sie die Ausführung von abhängigem Code aus.</span><span class="sxs-lookup"><span data-stu-id="be71b-165">If a certain browser doesn't support a feature used in rendering, either load a polyfill or exclude running dependent code.</span></span> <span data-ttu-id="be71b-166">Wenn das Feature nicht kritisch ist, entfernen Sie Ressourcen wie Ereignishandler, um Speicherlecks zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="be71b-166">If the feature is not critical, dispose resources such as event handlers to avoid memory leaks.</span></span>

<span data-ttu-id="be71b-167">Bevor Sie Seitenrevisionen zur Behebung von Leistungsproblemen durchführen, notieren Sie sich die Ladezeit der Seite in den Analyseergebnissen.</span><span class="sxs-lookup"><span data-stu-id="be71b-167">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="be71b-168">Führen Sie das Tool nach Ihrer Revision erneut aus, um zu sehen, ob das neue Ergebnis innerhalb des Grenzwertes liegt, und überprüfen Sie die Ladezeit der neuen Seite, um festzustellen, ob eine Verbesserung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="be71b-168">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Ergebnisse der Seitenladezeiten](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="be71b-170">Die Seitenladezeit kann aufgrund einer Vielzahl von Faktoren wie Netzwerklast, Tageszeit und anderen vorübergehenden Schwierigkeiten variieren.</span><span class="sxs-lookup"><span data-stu-id="be71b-170">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="be71b-171">Sie sollten die Seitenladezeit einige Male vor und nach der Durchführung von Änderungen testen, um einen Mittelwert zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="be71b-171">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="be71b-172">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="be71b-172">Related topics</span></span>

[<span data-ttu-id="be71b-173">Optimieren der Leistung von SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="be71b-173">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="be71b-174">Optimieren der Leistung von Office 365</span><span class="sxs-lookup"><span data-stu-id="be71b-174">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="be71b-175">Leistung in der modernen SharePoint-Oberfläche</span><span class="sxs-lookup"><span data-stu-id="be71b-175">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="be71b-176">Netzwerke für die Inhaltsübermittlung</span><span class="sxs-lookup"><span data-stu-id="be71b-176">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="be71b-177">Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="be71b-177">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
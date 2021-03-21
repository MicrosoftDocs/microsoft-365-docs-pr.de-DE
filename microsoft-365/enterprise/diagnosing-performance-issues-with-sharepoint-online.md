---
title: Diagnose von Leistungsproblemen mit SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: In diesem Artikel erfahren Sie, wie Sie häufige Probleme mit Ihrer SharePoint Online-Website mithilfe von Internet Explorer-Entwicklertools diagnostizieren können.
ms.openlocfilehash: 6a29b8b2df54d74d8237418828a7aa89efdbcfaf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927612"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="927bd-103">Diagnose von Leistungsproblemen mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="927bd-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="927bd-104">In diesem Artikel erfahren Sie, wie Sie häufige Probleme mit Ihrer SharePoint Online-Website mithilfe von Internet Explorer-Entwicklertools diagnostizieren können.</span><span class="sxs-lookup"><span data-stu-id="927bd-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="927bd-105">Es gibt drei verschiedene Möglichkeiten, um zu identifizieren, dass eine Seite auf einer SharePoint Online-Website ein Leistungsproblem mit den Anpassungen hat.</span><span class="sxs-lookup"><span data-stu-id="927bd-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="927bd-106">Der Netzwerkmonitor der F12-Toolleiste</span><span class="sxs-lookup"><span data-stu-id="927bd-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="927bd-107">Vergleich mit einem nicht angepassten Basisplan</span><span class="sxs-lookup"><span data-stu-id="927bd-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="927bd-108">SharePoint Online-Antwortheadermetriken</span><span class="sxs-lookup"><span data-stu-id="927bd-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="927bd-109">In diesem Thema wird beschrieben, wie Sie mit jeder dieser Methoden Leistungsprobleme diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="927bd-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="927bd-110">Nachdem Sie die Ursache des Problems gefunden haben, können Sie mithilfe der Artikel zur Verbesserung der SharePoint-Leistung, die Sie finden, an einer Lösung https://aka.ms/tune arbeiten.</span><span class="sxs-lookup"><span data-stu-id="927bd-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="927bd-111">Verwenden der F12-Toolleiste zum Diagnostizieren der Leistung in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="927bd-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="927bd-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="927bd-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="927bd-113">In diesem Artikel verwenden wir Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="927bd-113">In this article we use Internet Explorer 11.</span></span> <span data-ttu-id="927bd-114">Versionen der F12-Entwicklertools in anderen Browsern verfügen über ähnliche Features, obwohl sie leicht unterschiedlich aussehen können.</span><span class="sxs-lookup"><span data-stu-id="927bd-114">Versions of the F12 developer tools on other browsers have similar features though they may look slightly different.</span></span> <span data-ttu-id="927bd-115">Informationen zu den F12-Entwicklertools finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="927bd-115">For information on the F12 developer tools, see:</span></span>
  
- <span data-ttu-id="927bd-116">[Neues in den F12-Tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="927bd-116">[What's new in F12 Tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span></span>

- <span data-ttu-id="927bd-117">[Verwenden der F12-Entwicklertools](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="927bd-117">[Using the F12 developer tools](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span></span>

<span data-ttu-id="927bd-118">Drücken Sie **F12,** um die Entwicklertools hoch zu bringen, und klicken Sie dann auf Wi-Fi Symbol:</span><span class="sxs-lookup"><span data-stu-id="927bd-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![Screenshot des WLAN-Symbols für F12-Entwicklertools](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="927bd-120">Drücken Sie **auf der** Registerkarte Netzwerk die grüne Wiedergabeschaltfläche, um eine Seite zu laden.</span><span class="sxs-lookup"><span data-stu-id="927bd-120">On the **Network** tab, press the green play button to load a page.</span></span> <span data-ttu-id="927bd-121">Das Tool gibt alle Dateien zurück, die der Browser anfordert, um die seite zu erhalten, nach der Sie gefragt haben.</span><span class="sxs-lookup"><span data-stu-id="927bd-121">The tool returns all of the files that the browser requests in order to get the page you asked for.</span></span> <span data-ttu-id="927bd-122">Der folgende Screenshot zeigt eine solche Liste.</span><span class="sxs-lookup"><span data-stu-id="927bd-122">The following screen shot shows one such list.</span></span>
  
![Screenshot der Liste der mit einer Seitenanforderung zurückgegebenen Dateien.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="927bd-124">Sie können auch die Downloadzeiten der Dateien auf der rechten Seite sehen, wie in diesem Screenshot gezeigt.</span><span class="sxs-lookup"><span data-stu-id="927bd-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![Diagramm zum Laden der angeforderten Seiten aus SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="927bd-126">Dadurch erhalten Sie eine visuelle Darstellung der Ladezeit der Datei.</span><span class="sxs-lookup"><span data-stu-id="927bd-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="927bd-127">Die grüne Linie gibt an, wann die Seite vom Browser gerendert werden kann.</span><span class="sxs-lookup"><span data-stu-id="927bd-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="927bd-128">Dadurch erhalten Sie eine schnelle Ansicht der verschiedenen Dateien, die möglicherweise zu langsamen Seitenlasten auf Ihrer Website führen.</span><span class="sxs-lookup"><span data-stu-id="927bd-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="927bd-129">Einrichten eines nicht angepassten Basisplans für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="927bd-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="927bd-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="927bd-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="927bd-131">Die beste Möglichkeit, die Leistungsschwächen Ihrer Website zu ermitteln, besteht in der Einrichtung einer vollständig out-of-the-box-Websitesammlung in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="927bd-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="927bd-132">Auf diese Weise können Sie alle verschiedenen Aspekte Ihrer Website mit dem vergleichen, was Sie ohne Anpassung auf der Seite erhalten würden.</span><span class="sxs-lookup"><span data-stu-id="927bd-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="927bd-133">Die OneDrive for #A0 ist ein gutes Beispiel für eine separate Websitesammlung, die wahrscheinlich keine Anpassungen hat.</span><span class="sxs-lookup"><span data-stu-id="927bd-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="927bd-134">Anzeigen von SharePoint-Antwortheaderinformationen</span><span class="sxs-lookup"><span data-stu-id="927bd-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="927bd-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="927bd-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="927bd-136">In SharePoint Online können Sie auf die Informationen zugreifen, die im Antwortheader für jede Datei an den Browser gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="927bd-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="927bd-137">Der nützlichste Wert zum Diagnostizieren von Leistungsproblemen ist **SPRequestDuration**, der den Zeitraum anzeigt, den die Anforderung auf dem Server für die Verarbeitung in Sich nahm.</span><span class="sxs-lookup"><span data-stu-id="927bd-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="927bd-138">Dadurch kann ermittelt werden, ob die Anforderung sehr schwer und ressourcenintensiv ist.</span><span class="sxs-lookup"><span data-stu-id="927bd-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="927bd-139">Dies ist der beste Einblick, wie viel Arbeit der Server zum Bedienen der Seite macht.</span><span class="sxs-lookup"><span data-stu-id="927bd-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="927bd-140">So zeigen Sie Informationen zum SharePoint-Antwortheader an</span><span class="sxs-lookup"><span data-stu-id="927bd-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="927bd-141">Stellen Sie sicher, dass die F12-Tools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="927bd-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="927bd-142">Weitere Informationen zum Herunterladen und Installieren dieser Tools finden Sie unter [What's new in F12 tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="927bd-142">For more information on downloading and installing these tools, see [What's new in F12 tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85)).</span></span>

2. <span data-ttu-id="927bd-143">Drücken Sie in den F12-Tools auf der Registerkarte **Netzwerk** die grüne Wiedergabeschaltfläche, um eine Seite zu laden.</span><span class="sxs-lookup"><span data-stu-id="927bd-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="927bd-144">Klicken Sie auf eine der vom Tool zurückgegebenen ASPX-Dateien, und klicken Sie dann auf **DETAILS**.</span><span class="sxs-lookup"><span data-stu-id="927bd-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![Zeigt Details des Antwortheaders an](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="927bd-146">Klicken Sie **auf Antwortkopfzeilen**.</span><span class="sxs-lookup"><span data-stu-id="927bd-146">Click **Response headers**.</span></span>

    ![Diagramm mit der URL des Antwortheaders](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="927bd-148">Was verursacht Leistungsprobleme in SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="927bd-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="927bd-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="927bd-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="927bd-150">Der Artikel [Navigationsoptionen für SharePoint Online](navigation-options-for-sharepoint-online.md) zeigt ein Beispiel für die Verwendung des SPRequestDuration-Werts, um zu ermitteln, dass die komplizierte strukturell navigationsleiste dazu führt, dass die Seite lange auf dem Server verarbeiten musste.</span><span class="sxs-lookup"><span data-stu-id="927bd-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="927bd-151">Wenn Sie einen Wert für eine Basiswebsite (ohne Anpassung) verwenden, können Sie ermitteln, ob das Laden einer bestimmten Datei sehr viel Zeit in Sich nimmt.</span><span class="sxs-lookup"><span data-stu-id="927bd-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="927bd-152">Das in [Navigationsoptionen für SharePoint Online](navigation-options-for-sharepoint-online.md) verwendete Beispiel ist die haupt-ASPX-Datei.</span><span class="sxs-lookup"><span data-stu-id="927bd-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="927bd-153">Diese Datei enthält den großteil ASP.NET Code, der für das Laden der Seite ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="927bd-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="927bd-154">Je nach verwendeter Websitevorlage kann dies start.aspx, home.aspx, default.aspx oder ein anderer Name sein, wenn Sie die Startseite anpassen.</span><span class="sxs-lookup"><span data-stu-id="927bd-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="927bd-155">Wenn diese Anzahl deutlich höher als Ihre Basiswebsite ist, ist dies ein guter Hinweis darauf, dass auf Ihrer Seite etwas komplexes vor sich geht, das Leistungsprobleme verursacht.</span><span class="sxs-lookup"><span data-stu-id="927bd-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="927bd-156">Nachdem Sie festgestellt haben, dass es sich um ein spezifisches Problem für Ihre Website handelt, empfiehlt es sich, herauszufinden, was zu einer leistungsärmeren Leistung führt, indem Sie alle möglichen Ursachen beseitigen, z. B. Seitenanpassungen, und diese dann der Website nach und nach hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="927bd-156">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one.</span></span> <span data-ttu-id="927bd-157">Nachdem Sie genügend Anpassungen entfernt haben, dass die Seite gut funktioniert, können Sie bestimmte Anpassungen nach und nach hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="927bd-157">Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="927bd-158">Wenn Sie beispielsweise über eine sehr komplexe Navigation verfügen, versuchen Sie, die Navigation so zu ändern, dass Keine Unterwebsites angezeigt werden, überprüfen Sie die Entwicklertools, um zu sehen, ob dies einen Unterschied macht.</span><span class="sxs-lookup"><span data-stu-id="927bd-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="927bd-159">Oder wenn Sie über eine große Menge von Inhaltsrollups verfügen, versuchen Sie, sie von Ihrer Seite zu entfernen und zu sehen, ob dies die Dinge verbessert.</span><span class="sxs-lookup"><span data-stu-id="927bd-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="927bd-160">Wenn Sie alle möglichen Ursachen eliminieren und sie in einem nach dem anderen hinzufügen, können Sie ganz einfach ermitteln, welche Features das größte Problem sind, und dann auf eine Lösung hinarbeiten.</span><span class="sxs-lookup"><span data-stu-id="927bd-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>
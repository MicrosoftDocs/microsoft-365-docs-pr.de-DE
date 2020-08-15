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
description: In diesem Artikel erfahren Sie, wie Sie häufig auftretende Probleme mit Ihrer SharePoint Online Website mithilfe Internet Explorer Entwicklertools diagnostizieren können.
ms.openlocfilehash: a8a79afd860006a16874370b1124696550dab029
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690514"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="ea663-103">Diagnose von Leistungsproblemen mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ea663-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="ea663-104">In diesem Artikel erfahren Sie, wie Sie häufig auftretende Probleme mit Ihrer SharePoint Online Website mithilfe Internet Explorer Entwicklertools diagnostizieren können.</span><span class="sxs-lookup"><span data-stu-id="ea663-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="ea663-105">Es gibt drei verschiedene Möglichkeiten, um festzustellen, ob eine Seite auf einer SharePoint Online Website ein Leistungsproblem mit den Anpassungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="ea663-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="ea663-106">Die F12-Toolleiste Netzwerkmonitor</span><span class="sxs-lookup"><span data-stu-id="ea663-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="ea663-107">Vergleich mit einer nicht angepassten Baseline</span><span class="sxs-lookup"><span data-stu-id="ea663-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="ea663-108">Metriken für SharePoint Online Antwortheader</span><span class="sxs-lookup"><span data-stu-id="ea663-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="ea663-109">In diesem Thema wird beschrieben, wie Sie diese Methoden zum Diagnostizieren von Leistungsproblemen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea663-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="ea663-110">Nachdem Sie die Ursache des Problems herausgefunden haben, können Sie mit den Artikeln zur Verbesserung der SharePoint-Leistung, die Sie finden können, auf eine Lösung hinarbeiten https://aka.ms/tune .</span><span class="sxs-lookup"><span data-stu-id="ea663-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="ea663-111">Diagnostizieren der Leistung in SharePoint Online mithilfe der F12-Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="ea663-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="ea663-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ea663-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ea663-113">In diesem Artikel verwenden wir Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="ea663-113">In this article we use Internet Explorer 11.</span></span> <span data-ttu-id="ea663-114">Versionen der F12-Entwicklertools in anderen Browsern weisen ähnliche Features auf, die sich jedoch möglicherweise geringfügig unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="ea663-114">Versions of the F12 developer tools on other browsers have similar features though they may look slightly different.</span></span> <span data-ttu-id="ea663-115">Informationen zu den F12-Entwicklertools finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="ea663-115">For information on the F12 developer tools, see:</span></span>
  
- [<span data-ttu-id="ea663-116">Neuerungen in F12-Tools</span><span class="sxs-lookup"><span data-stu-id="ea663-116">What's new in F12 Tools</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=522545)

- [<span data-ttu-id="ea663-117">Verwenden der F12-Entwicklertools</span><span class="sxs-lookup"><span data-stu-id="ea663-117">Using the F12 developer tools</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=522546)

<span data-ttu-id="ea663-118">Drücken Sie **F12** , um die Entwicklertools aufzurufen, und klicken Sie dann auf das Symbol WLAN:</span><span class="sxs-lookup"><span data-stu-id="ea663-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![Screenshot von F12 Developer Tools WiFi-Symbol](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="ea663-120">Drücken Sie auf der Registerkarte **Netzwerk** die grüne Wiedergabe-Schaltfläche, um eine Seite zu laden.</span><span class="sxs-lookup"><span data-stu-id="ea663-120">On the **Network** tab, press the green play button to load a page.</span></span> <span data-ttu-id="ea663-121">Das Tool gibt alle Dateien zurück, die der Browser anfordert, um die von Ihnen gewünschte Seite abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ea663-121">The tool returns all of the files that the browser requests in order to get the page you asked for.</span></span> <span data-ttu-id="ea663-122">Der folgende Screenshot zeigt eine solche Liste.</span><span class="sxs-lookup"><span data-stu-id="ea663-122">The following screen shot shows one such list.</span></span>
  
![Screenshot der Liste der Dateien, die mit einer Seitenanforderung zurückgegeben werden.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="ea663-124">Sie können auch die Downloadzeiten der Dateien auf der rechten Seite sehen, wie in diesem Screenshot gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea663-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![Diagramm mit der Zeit, die zum Laden der angeforderten Seiten aus SharePoint benötigt wird](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="ea663-126">Dadurch erhalten Sie eine visuelle Darstellung der Dauer der Datei zum Laden.</span><span class="sxs-lookup"><span data-stu-id="ea663-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="ea663-127">Die grüne Leiste stellt dar, wann die Seite für den Browser gerendert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ea663-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="ea663-128">Dadurch erhalten Sie einen schnellen Überblick über die verschiedenen Dateien, die zu langsamen Seitenlasten auf Ihrer Website führen könnten.</span><span class="sxs-lookup"><span data-stu-id="ea663-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="ea663-129">Einrichten einer nicht angepassten Baseline für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ea663-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="ea663-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ea663-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ea663-131">Die beste Möglichkeit, die Leistung Schwachstellen Ihrer Website zu ermitteln, besteht darin, eine vollständig vordefinierte Websitesammlung in SharePoint Online einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ea663-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="ea663-132">Auf diese Weise können Sie alle verschiedenen Aspekte Ihrer Website mit dem vergleichen, was Sie ohne Anpassung auf der Seite erhalten würden.</span><span class="sxs-lookup"><span data-stu-id="ea663-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="ea663-133">Die OneDrive für Unternehmen Homepage ist ein gutes Beispiel für eine separate Websitesammlung, die wahrscheinlich keine Anpassungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="ea663-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="ea663-134">Anzeigen von SharePoint-Antwortheader Informationen</span><span class="sxs-lookup"><span data-stu-id="ea663-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="ea663-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ea663-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ea663-136">In SharePoint Online können Sie auf die Informationen zugreifen, die in der Antwort Kopfzeile für jede Datei an den Browser zurückgesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ea663-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="ea663-137">Der nützlichste Wert für die Diagnose von Leistungsproblemen ist **SPRequestDuration**, mit dem die Zeitdauer angezeigt wird, die die Anforderung auf dem zu verarbeitenden Server benötigt.</span><span class="sxs-lookup"><span data-stu-id="ea663-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="ea663-138">Dies kann helfen, festzustellen, ob die Anforderung sehr schwer ist und ressourcenintensiv ist.</span><span class="sxs-lookup"><span data-stu-id="ea663-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="ea663-139">Dies ist die beste Einblicke in die Arbeit, die der Server für die Bereitstellung der Seite leistet.</span><span class="sxs-lookup"><span data-stu-id="ea663-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="ea663-140">So zeigen Sie Informationen zum SharePoint-Antwortheader an</span><span class="sxs-lookup"><span data-stu-id="ea663-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="ea663-141">Stellen Sie sicher, dass die F12-Tools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ea663-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="ea663-142">Weitere Informationen zum herunterladen und Installieren dieser Tools finden Sie unter [What es New in F12 Tools](https://go.microsoft.com/fwlink/p/?LinkId=522545).</span><span class="sxs-lookup"><span data-stu-id="ea663-142">For more information on downloading and installing these tools, see [What's new in F12 tools](https://go.microsoft.com/fwlink/p/?LinkId=522545).</span></span>

2. <span data-ttu-id="ea663-143">Drücken Sie in den F12-Tools auf der Registerkarte **Netzwerk** die grüne Wiedergabe-Schaltfläche, um eine Seite zu laden.</span><span class="sxs-lookup"><span data-stu-id="ea663-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="ea663-144">Klicken Sie auf eine der ASPX-Dateien, die vom Tool zurückgegeben werden, und klicken Sie dann auf **Details**.</span><span class="sxs-lookup"><span data-stu-id="ea663-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![Zeigt Details des Antwortheaders an.](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="ea663-146">Klicken Sie auf **Antwortheader**.</span><span class="sxs-lookup"><span data-stu-id="ea663-146">Click **Response headers**.</span></span>

    ![Diagramm mit der URL des Antwortheaders](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="ea663-148">Was verursacht Leistungsprobleme in SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="ea663-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="ea663-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ea663-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ea663-150">Die Artikel [Navigationsoptionen für SharePoint Online](navigation-options-for-sharepoint-online.md) zeigen ein Beispiel für die Verwendung des SPRequestDuration-Werts, um festzustellen, ob die komplizierte strukturelle Navigation dazu führte, dass die Verarbeitung auf dem Server auf der Seite lange dauert.</span><span class="sxs-lookup"><span data-stu-id="ea663-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="ea663-151">Durch die Verwendung eines Werts für eine Baseline-Website (ohne Anpassung) können Sie ermitteln, ob eine bestimmte Datei viel Zeit zum Laden braucht.</span><span class="sxs-lookup"><span data-stu-id="ea663-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="ea663-152">Das Beispiel, das in [Navigationsoptionen für SharePoint Online](navigation-options-for-sharepoint-online.md) verwendet wird, ist die Datei "Main. aspx".</span><span class="sxs-lookup"><span data-stu-id="ea663-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="ea663-153">Diese Datei enthält die meisten ASP.NET-Code, der für die Seiten Lade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ea663-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="ea663-154">Je nach verwendeter Websitevorlage kann dies "Start. aspx", "Home. aspx", "default. aspx" oder ein anderer Name sein, wenn Sie die Homepage anpassen.</span><span class="sxs-lookup"><span data-stu-id="ea663-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="ea663-155">Wenn diese Zahl erheblich höher ist als die Baseline-Website, ist dies ein guter Hinweis darauf, dass in Ihrer Seite ein Komplex vorgeht, der Leistungsprobleme verursacht.</span><span class="sxs-lookup"><span data-stu-id="ea663-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="ea663-156">Nachdem Sie festgestellt haben, dass es sich um ein für Ihre Website spezifisches Problem handelt, ist die empfohlene Vorgehensweise, um herauszufinden, was eine schlechte Leistung verursacht, darin, alle möglichen Ursachen wie Seiten Anpassungen zu beseitigen und Sie dann nacheinander wieder der Website hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ea663-156">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one.</span></span> <span data-ttu-id="ea663-157">Nachdem Sie genügend Anpassungen entfernt haben, die die Seite gut ausführt, können Sie einzelne Anpassungen nacheinander hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ea663-157">Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="ea663-158">Wenn Sie beispielsweise eine sehr komplexe Navigation haben, versuchen Sie, die Navigation so zu ändern, dass Unterwebsites nicht angezeigt werden, und überprüfen Sie die Entwicklertools, um zu sehen, ob dies einen Unterschied macht.</span><span class="sxs-lookup"><span data-stu-id="ea663-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="ea663-159">Oder wenn Sie eine große Menge an Inhalts-Roll-ups haben, versuchen Sie, diese von Ihrer Seite zu entfernen und zu sehen, ob dies die Dinge verbessert.</span><span class="sxs-lookup"><span data-stu-id="ea663-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="ea663-160">Wenn Sie alle möglichen Ursachen beseitigen und gleichzeitig wieder hinzufügen, können Sie ganz einfach ermitteln, welche Funktionen das größte Problem darstellen, und dann auf eine Lösung hinarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ea663-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>

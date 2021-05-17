---
title: Verwenden des Inhaltssuchwebteils anstelle des Inhaltsabfragewebteils zur Verbesserung der Leistung in SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: Erfahren Sie, wie Sie die Leistung steigern, indem Sie das Inhaltsabfragewebteil durch das Inhaltssuchwebteil in SharePoint Server 2013 und SharePoint Online ersetzen.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690885"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a><span data-ttu-id="463ba-103">Verwenden des Inhaltssuchwebteils anstelle des Inhaltsabfragewebteils zur Verbesserung der Leistung in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="463ba-103">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>

<span data-ttu-id="463ba-104">In diesem Artikel wird beschrieben, wie Sie die Leistung steigern, indem sie das Inhaltsabfragewebteil durch das Inhaltssuchwebteil in SharePoint Server 2013 und SharePoint Online ersetzt.</span><span class="sxs-lookup"><span data-stu-id="463ba-104">This article describes how to increase performance by replacing the Content Query Web Part with the Content Search Web Part in SharePoint Server 2013 and SharePoint Online.</span></span>
  
<span data-ttu-id="463ba-105">Eines der leistungsstärksten neuen Features von SharePoint Server 2013 und SharePoint Online ist das Web part für die Inhaltssuche (Content Search Web Part, CSWP).</span><span class="sxs-lookup"><span data-stu-id="463ba-105">One of the most powerful new features of SharePoint Server 2013 and SharePoint Online is the Content Search Web Part (CSWP).</span></span> <span data-ttu-id="463ba-106">Dieses Webteil verwendet den Suchindex, um schnell Ergebnisse abzurufen, die dem Benutzer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="463ba-106">This Web Part uses the search index to quickly retrieve results which are shown to the user.</span></span> <span data-ttu-id="463ba-107">Verwenden Sie das Web part für die Inhaltssuche anstelle des Inhaltsabfragewebteils (Content Query Web Part, CQWP) auf Ihren Seiten, um die Leistung für Ihre Benutzer zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="463ba-107">Use the Content Search Web Part instead of the Content Query Web Part (CQWP) in your pages to improve performance for your users.</span></span>
  
<span data-ttu-id="463ba-108">Die Verwendung eines Inhaltssuchwebteils über ein Inhaltsabfragewebteil führt fast immer zu einer deutlich besseren Seitenladeleistung auf SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="463ba-108">Using a Content Search Web Part over a Content Query Web Part will almost always result in significantly better page load performance on SharePoint Online.</span></span> <span data-ttu-id="463ba-109">Es gibt ein wenig zusätzliche Konfiguration, um die richtige Abfrage zu erhalten, aber die Vorteile sind verbesserte Leistung und zufriedenere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="463ba-109">There is a little additional configuration to get the right query, but the rewards are improved performance and happier users.</span></span>
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a><span data-ttu-id="463ba-110">Vergleichen des Leistungsgewinns, den Sie durch die Verwendung des Inhaltssuchwebteils anstelle des Inhaltsabfragewebteils erzielen</span><span class="sxs-lookup"><span data-stu-id="463ba-110">Comparing the performance gain you get from using Content Search Web Part instead of Content Query Web Part</span></span>

<span data-ttu-id="463ba-111">Die folgenden Beispiele zeigen die relativen Leistungsgewinne, die Sie erhalten können, wenn Sie ein Inhaltssuchwebteil anstelle eines Inhaltsabfragewebteils verwenden.</span><span class="sxs-lookup"><span data-stu-id="463ba-111">The following examples show the relative performance gains you may receive when you use a Content Search Web Part instead of a Content Query Web Part.</span></span> <span data-ttu-id="463ba-112">Die Effekte sind mit einer komplexen Websitestruktur und sehr breiten Inhaltsabfragen offensichtlicher.</span><span class="sxs-lookup"><span data-stu-id="463ba-112">The effects are more obvious with a complex site structure and very broad content queries.</span></span>
  
<span data-ttu-id="463ba-113">Diese Beispielwebsite hat die folgenden Merkmale:</span><span class="sxs-lookup"><span data-stu-id="463ba-113">This example site has the following characteristics:</span></span>
  
- <span data-ttu-id="463ba-114">8 Ebenen von Unterwebsites.</span><span class="sxs-lookup"><span data-stu-id="463ba-114">8 levels of subsites.</span></span>
    
- <span data-ttu-id="463ba-115">Listet mithilfe eines benutzerdefinierten Inhaltstyps "Obst" auf.</span><span class="sxs-lookup"><span data-stu-id="463ba-115">Lists using a custom "fruit" content type.</span></span>
    
- <span data-ttu-id="463ba-116">Im Web part ist die Inhaltsabfrage breit und gibt alle Elemente mit dem Inhaltstyp "fruit" zurück.</span><span class="sxs-lookup"><span data-stu-id="463ba-116">In the Web Part, the content query is broad, returning all items with the content type of "fruit".</span></span>
    
- <span data-ttu-id="463ba-117">Das Beispiel verwendet nur 50 Elemente auf den 8 Websites.</span><span class="sxs-lookup"><span data-stu-id="463ba-117">The example only uses 50 items across the 8 sites.</span></span> <span data-ttu-id="463ba-118">Die Auswirkungen werden für Websites mit mehr Inhalt noch stärker.</span><span class="sxs-lookup"><span data-stu-id="463ba-118">The effects will be even more pronounced for sites with more content.</span></span>
    
<span data-ttu-id="463ba-119">Hier sehen Sie einen Screenshot der Ergebnisse des Inhaltsabfragewebteils.</span><span class="sxs-lookup"><span data-stu-id="463ba-119">Here is a screen shot of the results of the Content Query Web Part.</span></span>
  
![Grafik mit Inhaltsabfragen für web part](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
<span data-ttu-id="463ba-121">Verwenden Sie in Internet Explorer die Registerkarte **Netzwerk** der F12-Entwicklertools, um die Details für den Antwortheader zu sehen.</span><span class="sxs-lookup"><span data-stu-id="463ba-121">In Internet Explorer, use the **Network** tab of the F12 developer tools to look at the details for the response header.</span></span> <span data-ttu-id="463ba-122">Im folgenden Screenshot beträgt der Wert für **die SPRequestDuration** für diese Seitenlast 924 Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="463ba-122">In the following screen shot, the value for the **SPRequestDuration** for this page load is 924 milliseconds.</span></span> 
  
![Screenshot mit der Anforderungsdauer von 924](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 <span data-ttu-id="463ba-124">**SPRequestDuration** gibt an, wie viel Arbeit auf dem Server zum Vorbereiten der Seite erledigt wird.</span><span class="sxs-lookup"><span data-stu-id="463ba-124">**SPRequestDuration** indicates the amount of work that is done on the server to prepare the page.</span></span> <span data-ttu-id="463ba-125">Das Wechseln von Inhalten nach Abfrage Webparts Inhaltssuche Webparts die Zeit für das Rendern der Seite erheblich reduziert.</span><span class="sxs-lookup"><span data-stu-id="463ba-125">Switching Content by Query Web Parts with Content by Search Web Parts dramatically reduces the time it takes to render the page.</span></span> <span data-ttu-id="463ba-126">Im Gegensatz dazu hat eine Seite mit einem entsprechenden Inhaltssuchwebteil, das dieselbe Anzahl von Ergebnissen zurück gibt, einen **SPRequestDuration-Wert** von 106 Millisekunden, wie in diesem Screenshot gezeigt:</span><span class="sxs-lookup"><span data-stu-id="463ba-126">By contrast, a page with an equivalent Content Search Web Part, returning the same number of results has an **SPRequestDuration** value of 106 milliseconds as shown in this screen shot:</span></span> 
  
![Screenshot der Anforderungsdauer von 106](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a><span data-ttu-id="463ba-128">Hinzufügen eines Inhaltssuchwebteils in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="463ba-128">Adding a Content Search Web Part in SharePoint Online</span></span>

<span data-ttu-id="463ba-129">Das Hinzufügen eines Inhaltssuchwebteils ähnelt einem regulären Web part für Inhaltsabfragen.</span><span class="sxs-lookup"><span data-stu-id="463ba-129">Adding a Content Search Web Part is very similar to a regular Content Query Web Part.</span></span> <span data-ttu-id="463ba-130">Weitere Informationen finden Sie im Abschnitt *"Add a Content Search Web Part"* unter [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span><span class="sxs-lookup"><span data-stu-id="463ba-130">See the section  *"Add a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a><span data-ttu-id="463ba-131">Erstellen der richtigen Suchabfrage für Ihr Inhaltssuchwebteil</span><span class="sxs-lookup"><span data-stu-id="463ba-131">Creating the right search query for your Content Search Web Part</span></span>

<span data-ttu-id="463ba-132">Nachdem Sie ein Web part für die Inhaltssuche hinzugefügt haben, können Sie die Suche verfeinern und die gesuchten Elemente zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="463ba-132">Once you have added a Content Search Web Part, you can refine the search and return the items you want.</span></span> <span data-ttu-id="463ba-133">Ausführliche Anweisungen dazu finden Sie im Abschnitt "Anzeigen von Inhalten durch Konfigurieren einer erweiterten Abfrage in einem Inhaltssuchwebteil" unter [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a). </span><span class="sxs-lookup"><span data-stu-id="463ba-133">For detailed instructions on how to do this, see the section,  *"Display content by configuring an advanced query in a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="query-building-and-testing-tool"></a><span data-ttu-id="463ba-134">Tool zum Erstellen und Testen von Abfragen</span><span class="sxs-lookup"><span data-stu-id="463ba-134">Query building and testing tool</span></span>

<span data-ttu-id="463ba-135">Ein Tool zum Erstellen und Testen komplexer Abfragen finden Sie im [Suchabfragetool auf](https://sp2013searchtool.codeplex.com/) Codeplex.</span><span class="sxs-lookup"><span data-stu-id="463ba-135">For a tool to build and test complex queries, see the [Search Query Tool](https://sp2013searchtool.codeplex.com/) on Codeplex.</span></span> 
  


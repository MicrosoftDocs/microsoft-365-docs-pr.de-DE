---
title: Einführung in die Leistungsoptimierung für SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: In diesem Artikel werden die spezifischen Aspekte erläutert, die Sie beim Entwerfen von Seiten für eine optimale Leistung in SharePoint Online berücksichtigen müssen.
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909738"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="7968f-103">Einführung in die Leistungsoptimierung für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7968f-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="7968f-104">In diesem Artikel werden die spezifischen Aspekte erläutert, die Sie beim Entwerfen von Seiten für eine optimale Leistung in SharePoint Online berücksichtigen müssen.</span><span class="sxs-lookup"><span data-stu-id="7968f-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="7968f-105">SharePoint Online-Metriken</span><span class="sxs-lookup"><span data-stu-id="7968f-105">SharePoint Online metrics</span></span>

<span data-ttu-id="7968f-106">Die folgenden breiten Metriken für SharePoint Online bieten reale Daten zur Leistung:</span><span class="sxs-lookup"><span data-stu-id="7968f-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="7968f-107">Wie schnell Seiten geladen werden</span><span class="sxs-lookup"><span data-stu-id="7968f-107">How fast pages load</span></span>
    
- <span data-ttu-id="7968f-108">Wie viele Roundtrips pro Seite erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="7968f-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="7968f-109">Probleme mit dem Dienst</span><span class="sxs-lookup"><span data-stu-id="7968f-109">Issues with the service</span></span>
    
- <span data-ttu-id="7968f-110">Andere Dinge, die leistungsbeeinträchtigungen verursachen</span><span class="sxs-lookup"><span data-stu-id="7968f-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="7968f-111">Schlussfolgerungen aufgrund der Daten</span><span class="sxs-lookup"><span data-stu-id="7968f-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="7968f-112">Die Daten sagen uns:</span><span class="sxs-lookup"><span data-stu-id="7968f-112">The data tells us:</span></span>
  
- <span data-ttu-id="7968f-113">Die meisten Seiten können in SharePoint Online gut verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7968f-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="7968f-114">Nicht angepasste Seiten werden sehr schnell geladen.</span><span class="sxs-lookup"><span data-stu-id="7968f-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="7968f-115">OneDrive for Business, Teamwebsites und Systemseiten wie _layouts usw. können schnell geladen werden.</span><span class="sxs-lookup"><span data-stu-id="7968f-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="7968f-116">Die langsamsten 1 % der SharePoint Online-Seiten dauern mehr als 5.000 Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="7968f-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="7968f-117">Ein einfacher Benchmarktest, den Sie verwenden können, wäre das Messen der Leistung, indem Sie die Ladezeit Ihres eigenen Portals mit der Ladezeit der OneDrive for #A0 vergleichen, da nur wenige angepasste Features verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7968f-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="7968f-118">Dies ist häufig der erste Schritt, den der Support bei der Problembehandlung bei der Netzwerkleistung durchführen muss.</span><span class="sxs-lookup"><span data-stu-id="7968f-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="7968f-119">Verwenden eines Standardbenutzerkontos beim Überprüfen der Leistung</span><span class="sxs-lookup"><span data-stu-id="7968f-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="7968f-120">Ein Websitesammlungsadministrator, Websitebesitzer, Editor oder Mitwirkender gehört zu weiteren Sicherheitsgruppen, verfügt über zusätzliche Berechtigungen und verfügt daher über zusätzliche Elemente, die SharePoint auf einer Seite lädt.</span><span class="sxs-lookup"><span data-stu-id="7968f-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="7968f-121">Dies gilt für lokale SharePoint- und SharePoint Online-Dienste, aber in einem lokalen Szenario werden die Unterschiede nicht so leicht bemerkt wie in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7968f-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="7968f-122">Um die Funktionsweise einer Seite für Benutzer richtig auszuwerten, sollten Sie ein Standardbenutzerkonto verwenden, um das Laden der Erstellungssteuerelemente und zusätzlichen Datenverkehr im Zusammenhang mit Sicherheitsgruppen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7968f-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="7968f-123">Verbindungskategorien für leistungsoptimierung</span><span class="sxs-lookup"><span data-stu-id="7968f-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="7968f-124">Sie können die Verbindungen zwischen dem Server und dem Benutzer in drei Hauptkomponenten kategorisieren.</span><span class="sxs-lookup"><span data-stu-id="7968f-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="7968f-125">Berücksichtigen Sie diese beim Entwerfen von SharePoint Online-Seiten, um einen Einblick in die Ladezeiten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7968f-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="7968f-126">**Server** Die Server, die Microsoft in Rechenzentren hostet.</span><span class="sxs-lookup"><span data-stu-id="7968f-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="7968f-127">**Netzwerk** Das Microsoft-Netzwerk, das Internet und Ihr lokales Netzwerk zwischen dem Datencenter und Ihren Benutzern.</span><span class="sxs-lookup"><span data-stu-id="7968f-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="7968f-128">**Browser** Der Ort, an dem die Seite geladen wird.</span><span class="sxs-lookup"><span data-stu-id="7968f-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="7968f-129">Innerhalb dieser drei Verbindungen gibt es in der Regel fünf Gründe, die 95 % der langsamen Seiten verursachen.</span><span class="sxs-lookup"><span data-stu-id="7968f-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="7968f-130">Jeder dieser Gründe wird in diesem Artikel erläutert:</span><span class="sxs-lookup"><span data-stu-id="7968f-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="7968f-131">Navigationsprobleme</span><span class="sxs-lookup"><span data-stu-id="7968f-131">Navigation issues</span></span>
    
- <span data-ttu-id="7968f-132">Inhaltsrollup</span><span class="sxs-lookup"><span data-stu-id="7968f-132">Content roll up</span></span>
    
- <span data-ttu-id="7968f-133">Große Dateien</span><span class="sxs-lookup"><span data-stu-id="7968f-133">Large files</span></span>
    
- <span data-ttu-id="7968f-134">Viele Anforderungen an den Server</span><span class="sxs-lookup"><span data-stu-id="7968f-134">Many requests to the server</span></span>
    
- <span data-ttu-id="7968f-135">Web part processing</span><span class="sxs-lookup"><span data-stu-id="7968f-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="7968f-136">Serververbindung</span><span class="sxs-lookup"><span data-stu-id="7968f-136">Server connection</span></span>

<span data-ttu-id="7968f-137">Viele der Probleme, die sich auf die Leistung mit sharePoint lokal auswirken, gelten auch für SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7968f-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="7968f-138">Wie Sie erwarten, haben Sie viel mehr Kontrolle über die Leistung von Servern mit lokalem SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7968f-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="7968f-139">Bei SharePoint Online sieht dies etwas anders aus.</span><span class="sxs-lookup"><span data-stu-id="7968f-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="7968f-140">Je mehr Arbeit Sie für einen Server erstellen, um so länger dauert das Rendern einer Seite.</span><span class="sxs-lookup"><span data-stu-id="7968f-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="7968f-141">Bei SharePoint sind komplexe Seiten mit mehreren Webparts der größte Fehler in dieser Hinsicht.</span><span class="sxs-lookup"><span data-stu-id="7968f-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="7968f-142">Lokales SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="7968f-142">SharePoint Server on-premises</span></span>
  
![Screenshot des lokalen Servers](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="7968f-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7968f-144">SharePoint Online</span></span>
  
![Screenshot des Servers online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="7968f-146">Bei SharePoint Online können bestimmte Seitenanforderungen tatsächlich mehrere Server aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7968f-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="7968f-147">Sie könnten am Ende eine Matrix von Anforderungen zwischen Servern für eine einzelne Anforderung erhalten.</span><span class="sxs-lookup"><span data-stu-id="7968f-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="7968f-148">Diese Interaktionen sind aus Sicht des Seitenlades kostspielig und werden langsam.</span><span class="sxs-lookup"><span data-stu-id="7968f-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="7968f-149">Beispiele für diese Server-zu-Server-Interaktionen sind:</span><span class="sxs-lookup"><span data-stu-id="7968f-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="7968f-150">Web to SQL Server</span><span class="sxs-lookup"><span data-stu-id="7968f-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="7968f-151">Web zu Anwendungsservern</span><span class="sxs-lookup"><span data-stu-id="7968f-151">Web to application servers</span></span>
    
<span data-ttu-id="7968f-152">Die andere Sache, die Serverinteraktionen verlangsamen kann, sind Cache-Verpasste.</span><span class="sxs-lookup"><span data-stu-id="7968f-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="7968f-153">Im Gegensatz zu lokalen SharePoint besteht eine sehr geringe Wahrscheinlichkeit, dass Sie auf denselben Server für eine Seite treffen, die Sie zuvor besucht haben. Dadurch wird die Objektspeicherung veraltet.</span><span class="sxs-lookup"><span data-stu-id="7968f-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="7968f-154">Netzwerkverbindung </span><span class="sxs-lookup"><span data-stu-id="7968f-154">Network connection</span></span>

<span data-ttu-id="7968f-155">Bei lokalem SharePoint, das kein WAN verwendet, können Sie eine Hochgeschwindigkeitsverbindung zwischen Rechenzentren und Endbenutzern verwenden.</span><span class="sxs-lookup"><span data-stu-id="7968f-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="7968f-156">Im Allgemeinen ist die Verwaltung aus Netzwerksicht einfach.</span><span class="sxs-lookup"><span data-stu-id="7968f-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="7968f-157">Mit SharePoint Online müssen einige weitere Faktoren berücksichtigt werden. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7968f-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="7968f-158">Das Microsoft-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="7968f-158">The Microsoft network</span></span>
    
- <span data-ttu-id="7968f-159">Das Internet</span><span class="sxs-lookup"><span data-stu-id="7968f-159">The Internet</span></span>
    
- <span data-ttu-id="7968f-160">Der ISP</span><span class="sxs-lookup"><span data-stu-id="7968f-160">The ISP</span></span>
    
<span data-ttu-id="7968f-161">Unabhängig davon, welche Version von SharePoint (und welches Netzwerk) Sie verwenden, gehören folgende Dinge, die in der Regel dazu führen, dass das Netzwerk ausgelastet ist:</span><span class="sxs-lookup"><span data-stu-id="7968f-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="7968f-162">Große Nutzlast</span><span class="sxs-lookup"><span data-stu-id="7968f-162">Large payload</span></span>
    
- <span data-ttu-id="7968f-163">Viele Dateien</span><span class="sxs-lookup"><span data-stu-id="7968f-163">Many files</span></span>
    
- <span data-ttu-id="7968f-164">Großer physischer Abstand zum Server</span><span class="sxs-lookup"><span data-stu-id="7968f-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="7968f-165">Ein Feature, das Sie in SharePoint Online nutzen können, ist das Microsoft CDN (Content Delivery Network).</span><span class="sxs-lookup"><span data-stu-id="7968f-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="7968f-166">Ein CDN ist im Wesentlichen eine verteilte Sammlung von Servern, die über mehrere Rechenzentren bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7968f-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="7968f-167">Mit einem CDN können Inhalte auf Seiten auf einem Server in der Nähe des Clients gehostet werden, auch wenn der Client weit vom ursprünglichen SharePoint Server entfernt ist.</span><span class="sxs-lookup"><span data-stu-id="7968f-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="7968f-168">Microsoft verwendet dies in Zukunft mehr, um lokale Instanzen von Seiten zu speichern, die nicht angepasst werden können, z. B. die SharePoint Online-Administrator-Homepage.</span><span class="sxs-lookup"><span data-stu-id="7968f-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="7968f-169">Weitere Informationen zu CDNs finden Sie unter [Content Delivery Networks](content-delivery-networks.md).</span><span class="sxs-lookup"><span data-stu-id="7968f-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="7968f-170">Etwas, das Sie beachten müssen, aber möglicherweise nicht in der Lage sind, viel zu tun, ist die Verbindungsgeschwindigkeit Ihres Internetdienstanbieters.</span><span class="sxs-lookup"><span data-stu-id="7968f-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="7968f-171">Ein einfaches Geschwindigkeitstesttool gibt Die Verbindungsgeschwindigkeit an.</span><span class="sxs-lookup"><span data-stu-id="7968f-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="7968f-172">Browserverbindung</span><span class="sxs-lookup"><span data-stu-id="7968f-172">Browser connection</span></span>

<span data-ttu-id="7968f-173">Es gibt einige Faktoren, die bei Webbrowsern aus Leistungssicht berücksichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7968f-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="7968f-174">Das Besuchen komplexer Seiten wirkt sich auf die Leistung aus.</span><span class="sxs-lookup"><span data-stu-id="7968f-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="7968f-175">Die meisten Browser verfügen nur über einen kleinen Cache (ca. 90 MB), während die durchschnittliche Webseite in der Regel etwa 1,6 MB beträgt.</span><span class="sxs-lookup"><span data-stu-id="7968f-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="7968f-176">Dies dauert nicht lange, bis sie sich ernennen.</span><span class="sxs-lookup"><span data-stu-id="7968f-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="7968f-177">Bandbreite kann auch ein Problem sein.</span><span class="sxs-lookup"><span data-stu-id="7968f-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="7968f-178">Wenn ein Benutzer beispielsweise Videos in einer anderen Sitzung anschaut, wirkt sich dies auf die Leistung Ihrer SharePoint-Seite aus.</span><span class="sxs-lookup"><span data-stu-id="7968f-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="7968f-179">Sie können zwar nicht verhindern, dass Benutzer Medien streamen, sie können jedoch steuern, wie eine Seite für Benutzer geladen wird.</span><span class="sxs-lookup"><span data-stu-id="7968f-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="7968f-180">In den folgenden Artikeln finden Sie verschiedene Anpassungstechniken für SharePoint Online-Seiten und andere bewährte Methoden, die Ihnen dabei helfen, eine optimale Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="7968f-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="7968f-181">Navigationsoptionen für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7968f-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="7968f-182">Verwenden des Tools "Seitendiagnose" für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7968f-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="7968f-183">Bildoptimierung für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7968f-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="7968f-184">Verzögerung beim Laden von Bildern und JavaScript in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7968f-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="7968f-185">Minimierung und Bündelung in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7968f-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="7968f-186">Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7968f-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="7968f-187">Verwenden des Inhaltssuchwebteils anstelle des Inhaltsabfragewebteils zur Verbesserung der Leistung in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7968f-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="7968f-188">Kapazitätsplanung und Auslastungstests für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7968f-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="7968f-189">Diagnose von Leistungsproblemen mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7968f-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="7968f-190">Verwenden des Objektcaches mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7968f-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="7968f-191">Gewusst wie: Vermeiden von Einschränkungen oder Sperren in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7968f-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)

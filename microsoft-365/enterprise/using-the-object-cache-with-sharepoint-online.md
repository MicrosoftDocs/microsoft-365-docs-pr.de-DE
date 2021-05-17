---
title: Verwenden des Objektcaches mit SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
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
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: In diesem Artikel wird der Unterschied zwischen der Verwendung des Objektcaches in SharePoint Server 2013 lokal und SharePoint Online erläutert.
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695995"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a><span data-ttu-id="a8708-103">Verwenden des Objektcaches mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a8708-103">Using the object cache with SharePoint Online</span></span>

<span data-ttu-id="a8708-104">In diesem Artikel wird der Unterschied zwischen der Verwendung des Objektcaches in SharePoint Server 2013 lokal und SharePoint Online erläutert.</span><span class="sxs-lookup"><span data-stu-id="a8708-104">This article explains the difference between using the object cache in SharePoint Server 2013 on-premises and SharePoint Online.</span></span>
  
<span data-ttu-id="a8708-105">Dies hat erhebliche negative Auswirkungen auf den Objektcache in SharePoint Onlinebereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a8708-105">There is significant negative impact of relying on the object cache in SharePoint Online deployment.</span></span> <span data-ttu-id="a8708-106">Jede Abhängigkeit vom Objektcache in SharePoint Online verringert die Zuverlässigkeit Ihrer Seite.</span><span class="sxs-lookup"><span data-stu-id="a8708-106">Any dependency on object cache in SharePoint Online will reduce the reliability of your page.</span></span> 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a><span data-ttu-id="a8708-107">Funktionsweise des SharePoint Online- und SharePoint Server 2013-Objektcaches</span><span class="sxs-lookup"><span data-stu-id="a8708-107">How the SharePoint Online and SharePoint Server 2013 object cache works</span></span>

<span data-ttu-id="a8708-108">Wenn SharePoint Server 2013 lokal gehostet wird, verfügt der Kunde über private Front-End-Webserver, die den Objektcache hosten.</span><span class="sxs-lookup"><span data-stu-id="a8708-108">When SharePoint Server 2013 is hosted on-premises, the customer has private front-end web servers that host the object cache.</span></span> <span data-ttu-id="a8708-109">Dies bedeutet, dass der Cache für einen Kunden reserviert ist und nur durch den verfügbaren Speicher begrenzt ist, der dem Objektcache zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="a8708-109">This means the cache is dedicated to one customer and is only limited by how much memory is available and allocated to the object cache.</span></span> <span data-ttu-id="a8708-110">Da im lokalen Szenario nur ein Kunde bedient wird, haben die Front-End-Webserver in der Regel Benutzer, die immer wieder Anforderungen an dieselben Websites stellen.</span><span class="sxs-lookup"><span data-stu-id="a8708-110">Because only one customer is served in the on-premises scenario the front-end web servers typically have users making requests to the same sites over and over.</span></span> <span data-ttu-id="a8708-111">Dies bedeutet, dass der Cache schnell voll wird und voll mit den Listenabfrageergebnissen und SharePoint objekten bleibt, die Ihre Benutzer regelmäßig anfordern.</span><span class="sxs-lookup"><span data-stu-id="a8708-111">This means that the cache gets full quickly and remains full of the list query results and SharePoint objects that your users are requesting on a regular basis.</span></span>
  
![Zeigt Datenverkehr und Last an lokale Front-End-Webserver an](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
<span data-ttu-id="a8708-113">Wenn ein Benutzer also zum zweiten Mal eine Seite besucht, wird die Ladezeit der Seite verbessert.</span><span class="sxs-lookup"><span data-stu-id="a8708-113">As a result, the second time a user visits a page, the page load time improves.</span></span> <span data-ttu-id="a8708-114">Nach mindestens vier Lasten derselben Seite wird die Seite auf allen Front-End-Webservern zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="a8708-114">After a minimum of four loads of the same page, the page is cached on all of the front-end web servers.</span></span>
  
<span data-ttu-id="a8708-115">Im Gegensatz dazu gibt es in SharePoint Online viel mehr Server, aber auch viele weitere Websites.</span><span class="sxs-lookup"><span data-stu-id="a8708-115">In contrast, in SharePoint Online there are many more servers but also many more sites.</span></span> <span data-ttu-id="a8708-116">Jeder Benutzer kann eine Verbindung mit einem anderen Front-End-Webserver herstellen, auf dem der Cache nicht aufgefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="a8708-116">Each user may connect to a different front-end web server that doesn't have the cache populated.</span></span> <span data-ttu-id="a8708-117">Möglicherweise wird der Cache für einen Server aufgefüllt, aber der nächste Benutzer dieses Front-End-Webservers fordert eine Seite von einer anderen Website an.</span><span class="sxs-lookup"><span data-stu-id="a8708-117">Or, perhaps the cache does get populated for a server, but the next user to that front-end web server requests a page from a different site.</span></span> <span data-ttu-id="a8708-118">Auch wenn der nächste Benutzer dieselbe Seite wie bei seinem vorherigen Besuch anfordert, wird der Lastenausgleich für einen anderen Front-End-Webserver ausgeführt, auf dem diese Seite nicht im Cache vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a8708-118">Or, even if the next user requests the same page as on their previous visit, they are load-balanced to a different front-end web server that doesn't have that page in its cache.</span></span> <span data-ttu-id="a8708-119">In diesem letzten Fall hilft die Zwischenspeicherung den Benutzern überhaupt nicht.</span><span class="sxs-lookup"><span data-stu-id="a8708-119">In this last case, caching doesn't help the users at all.</span></span>
  
<span data-ttu-id="a8708-120">In der folgenden Abbildung stellt jeder Punkt eine Seite dar, die ein Benutzer anfordert und wo er zwischengespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="a8708-120">In the following figure, each dot represents a page that a user is requesting and where it cached.</span></span> <span data-ttu-id="a8708-121">Unterschiedliche Farben stellen unterschiedliche Kunden dar, die gemeinsam die SaaS-Infrastruktur nutzen.</span><span class="sxs-lookup"><span data-stu-id="a8708-121">Different colors represent different customers making shared use of the SaaS infrastructure.</span></span>
  
![Zeigt die Ergebnisse der Objekt zwischenspeicherung in SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
<span data-ttu-id="a8708-123">Wie Sie aus dem Diagramm sehen können, ist die Wahrscheinlichkeit gering, dass ein Benutzer mit der zwischengespeicherten Version seiner Seite auf einen Server trifft.</span><span class="sxs-lookup"><span data-stu-id="a8708-123">As you can see from the diagram, the chances of any given user hitting a server with the cached version of their page are slim.</span></span> <span data-ttu-id="a8708-124">Aufgrund des großen Durchsatzes und der Tatsache, dass die Server von vielen Standorten gemeinsam genutzt werden, dauert der Cache nicht lange, da nur so viel Speicherplatz für die Zwischenspeicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a8708-124">Also, due to the large throughput and fact that the servers are shared between many sites, the cache doesn't last long since there is only so much space for caching available.</span></span>
  
<span data-ttu-id="a8708-125">Aus all diesen Gründen ist es nicht effektiv, sich darauf zu verlassen, dass Benutzer zwischengespeicherte Objekte erhalten, um eine qualitativ hochwertige Benutzeroberfläche und Ladezeiten von Seiten in SharePoint online zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="a8708-125">For all of these reasons, relying on users getting cached objects is not an effective way to ensure a quality user experience and page load times in SharePoint Online.</span></span>
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a><span data-ttu-id="a8708-126">Wenn wir uns nicht auf den Objektcache verlassen können, um die Leistung in SharePoint Online zu verbessern, was wird stattdessen verwendet?</span><span class="sxs-lookup"><span data-stu-id="a8708-126">If we can't rely on the object cache to improve performance in SharePoint Online, what do we use instead?</span></span>

<span data-ttu-id="a8708-127">Da Sie sich nicht auf die Zwischenspeicherung in SharePoint Online verlassen sollten, sollten Sie alternative Entwurfsansätze für SharePoint, die den Objektcache verwenden, auswerten.</span><span class="sxs-lookup"><span data-stu-id="a8708-127">Since you shouldn't rely on caching in SharePoint Online, you should evaluate alternative design approaches for SharePoint customizations that use the object cache.</span></span> <span data-ttu-id="a8708-128">Dies bedeutet, dass Sie Ansätze für Leistungsprobleme verwenden, die nicht auf der Objektspeicherung beruhen, um gute Ergebnisse für Benutzer zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="a8708-128">This means using approaches for performance issues which do not rely on the object caching in order to produce good results for users.</span></span> <span data-ttu-id="a8708-129">Dies wird in einigen der anderen Artikel in dieser Reihe beschrieben und umfasst:</span><span class="sxs-lookup"><span data-stu-id="a8708-129">This is described in some of the other articles in this series and include:</span></span>
  
- [<span data-ttu-id="a8708-130">Navigationsoptionen für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a8708-130">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="a8708-131">Minimierung und Bündelung in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a8708-131">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="a8708-132">Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a8708-132">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="a8708-133">Verzögerung beim Laden von Bildern und JavaScript in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a8708-133">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    


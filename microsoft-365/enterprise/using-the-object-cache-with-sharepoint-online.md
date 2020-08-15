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
# <a name="using-the-object-cache-with-sharepoint-online"></a><span data-ttu-id="cc57f-103">Verwenden des Objektcaches mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cc57f-103">Using the object cache with SharePoint Online</span></span>

<span data-ttu-id="cc57f-104">In diesem Artikel wird der Unterschied zwischen der Verwendung des Objektcaches in SharePoint Server 2013 lokal und SharePoint Online erläutert.</span><span class="sxs-lookup"><span data-stu-id="cc57f-104">This article explains the difference between using the object cache in SharePoint Server 2013 on-premises and SharePoint Online.</span></span>
  
<span data-ttu-id="cc57f-105">Es gibt erhebliche negative Auswirkungen, wenn der Objektcache in SharePoint Online Bereitstellung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="cc57f-105">There is significant negative impact of relying on the object cache in SharePoint Online deployment.</span></span> <span data-ttu-id="cc57f-106">Durch jede Abhängigkeit vom Objektcache in SharePoint Online wird die Zuverlässigkeit Ihrer Seite verringert.</span><span class="sxs-lookup"><span data-stu-id="cc57f-106">Any dependency on object cache in SharePoint Online will reduce the reliability of your page.</span></span> 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a><span data-ttu-id="cc57f-107">Funktionsweise des SharePoint Online-und SharePoint Server 2013-Objektcaches</span><span class="sxs-lookup"><span data-stu-id="cc57f-107">How the SharePoint Online and SharePoint Server 2013 object cache works</span></span>

<span data-ttu-id="cc57f-108">Wenn SharePoint Server 2013 lokal gehostet wird, verfügt der Kunde über private Front-End-Webserver, die als Host für den Objektcache fungieren.</span><span class="sxs-lookup"><span data-stu-id="cc57f-108">When SharePoint Server 2013 is hosted on-premises, the customer has private front-end web servers that host the object cache.</span></span> <span data-ttu-id="cc57f-109">Dies bedeutet, dass der Cache für einen einzelnen Kunden reserviert ist und nur dadurch beschränkt ist, wie viel Arbeitsspeicher verfügbar und dem Objektcache zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="cc57f-109">This means the cache is dedicated to one customer and is only limited by how much memory is available and allocated to the object cache.</span></span> <span data-ttu-id="cc57f-110">Da nur ein Kunde im lokalen Szenario bedient wird, haben die Front-End-Webserver in der Regel Benutzer, die Anforderungen an dieselben Websites immer und immer wieder treffen.</span><span class="sxs-lookup"><span data-stu-id="cc57f-110">Because only one customer is served in the on-premises scenario the front-end web servers typically have users making requests to the same sites over and over.</span></span> <span data-ttu-id="cc57f-111">Dies bedeutet, dass der Cache vollständig schnell wird und voll von den Listen Abfrageergebnissen und SharePoint-Objekten bleibt, die Ihre Benutzer regelmäßig anfordern.</span><span class="sxs-lookup"><span data-stu-id="cc57f-111">This means that the cache gets full quickly and remains full of the list query results and SharePoint objects that your users are requesting on a regular basis.</span></span>
  
![Zeigt Datenverkehr und Last an lokale Front-End-Webserver](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
<span data-ttu-id="cc57f-113">Dadurch wird beim zweiten Mal, wenn ein Benutzer eine Seite besucht, die Ladezeit der Seite verbessert.</span><span class="sxs-lookup"><span data-stu-id="cc57f-113">As a result, the second time a user visits a page, the page load time improves.</span></span> <span data-ttu-id="cc57f-114">Nach mindestens vier Lasten derselben Seite wird die Seite auf allen Front-End-Webservern zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="cc57f-114">After a minimum of four loads of the same page, the page is cached on all of the front-end web servers.</span></span>
  
<span data-ttu-id="cc57f-115">Im Gegensatz dazu gibt es in SharePoint Online viele weitere Server, aber auch viele weitere Websites.</span><span class="sxs-lookup"><span data-stu-id="cc57f-115">In contrast, in SharePoint Online there are many more servers but also many more sites.</span></span> <span data-ttu-id="cc57f-116">Jeder Benutzer kann eine Verbindung mit einem anderen Front-End-Webserver herstellen, auf dem der Cache nicht aufgefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="cc57f-116">Each user may connect to a different front-end web server that doesn't have the cache populated.</span></span> <span data-ttu-id="cc57f-117">Oder vielleicht wird der Cache für einen Server aufgefüllt, aber der nächste Benutzer des Front-End-Webservers fordert eine Seite von einer anderen Website an.</span><span class="sxs-lookup"><span data-stu-id="cc57f-117">Or, perhaps the cache does get populated for a server, but the next user to that front-end web server requests a page from a different site.</span></span> <span data-ttu-id="cc57f-118">Oder auch dann, wenn der nächste Benutzer dieselbe Seite anfordert wie bei Ihrem vorherigen Besuch, wird der Lastenausgleich auf einen anderen Front-End-Webserver festgestellt, der diese Seite nicht im Cache hat.</span><span class="sxs-lookup"><span data-stu-id="cc57f-118">Or, even if the next user requests the same page as on their previous visit, they are load-balanced to a different front-end web server that doesn't have that page in its cache.</span></span> <span data-ttu-id="cc57f-119">In diesem letzten Fall hilft die Zwischenspeicherung den Benutzern überhaupt nicht.</span><span class="sxs-lookup"><span data-stu-id="cc57f-119">In this last case, caching doesn't help the users at all.</span></span>
  
<span data-ttu-id="cc57f-120">In der folgenden Abbildung steht jeder Punkt für eine Seite, die ein Benutzer anfordert und wo er zwischengespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="cc57f-120">In the following figure, each dot represents a page that a user is requesting and where it cached.</span></span> <span data-ttu-id="cc57f-121">Unterschiedliche Farben stellen unterschiedliche Kunden dar, die die gemeinsame Nutzung der SaaS-Infrastruktur nutzen.</span><span class="sxs-lookup"><span data-stu-id="cc57f-121">Different colors represent different customers making shared use of the SaaS infrastructure.</span></span>
  
![Zeigt die Ergebnisse der Objektzwischenspeicherung in SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
<span data-ttu-id="cc57f-123">Wie Sie aus dem Diagramm sehen können, sind die Chancen eines bestimmten Benutzers, einen Server mit der zwischengespeicherten Version Ihrer Seite zu treffen, gering.</span><span class="sxs-lookup"><span data-stu-id="cc57f-123">As you can see from the diagram, the chances of any given user hitting a server with the cached version of their page are slim.</span></span> <span data-ttu-id="cc57f-124">Aufgrund des hohen Durchsatzes und der Tatsache, dass die Server von vielen Standorten gemeinsam genutzt werden, dauert der Cache auch nicht lange, da nur so viel Speicherplatz für die Zwischenspeicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="cc57f-124">Also, due to the large throughput and fact that the servers are shared between many sites, the cache doesn't last long since there is only so much space for caching available.</span></span>
  
<span data-ttu-id="cc57f-125">Aus allen diesen Gründen ist das verlassen von Benutzern, die zwischengespeicherte Objekte erhalten, kein effektiver Weg, um eine qualitativ hochwertige Benutzeroberfläche und Seitenladezeiten in SharePoint Online sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="cc57f-125">For all of these reasons, relying on users getting cached objects is not an effective way to ensure a quality user experience and page load times in SharePoint Online.</span></span>
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a><span data-ttu-id="cc57f-126">Wenn wir nicht auf den Objektcache zurückgreifen können, um die Leistung in SharePoint Online zu verbessern, was verwenden wir stattdessen?</span><span class="sxs-lookup"><span data-stu-id="cc57f-126">If we can't rely on the object cache to improve performance in SharePoint Online, what do we use instead?</span></span>

<span data-ttu-id="cc57f-127">Da Sie sich nicht auf die Zwischenspeicherung in SharePoint Online verlassen sollten, sollten Sie alternative Entwurfsansätze für SharePoint-Anpassungen evaluieren, die den Objektcache verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc57f-127">Since you shouldn't rely on caching in SharePoint Online, you should evaluate alternative design approaches for SharePoint customizations that use the object cache.</span></span> <span data-ttu-id="cc57f-128">Dies bedeutet, dass Sie Methoden für Leistungsprobleme verwenden, die nicht auf die Objektzwischenspeicherung abzielen, um gute Ergebnisse für Benutzer zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="cc57f-128">This means using approaches for performance issues which do not rely on the object caching in order to produce good results for users.</span></span> <span data-ttu-id="cc57f-129">Dies wird in einigen der anderen Artikel in dieser Reihe beschrieben und umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cc57f-129">This is described in some of the other articles in this series and include:</span></span>
  
- [<span data-ttu-id="cc57f-130">Navigationsoptionen für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cc57f-130">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="cc57f-131">Minimierung und Bündelung in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cc57f-131">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="cc57f-132">Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cc57f-132">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="cc57f-133">Verzögerung beim Laden von Bildern und JavaScript in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cc57f-133">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    


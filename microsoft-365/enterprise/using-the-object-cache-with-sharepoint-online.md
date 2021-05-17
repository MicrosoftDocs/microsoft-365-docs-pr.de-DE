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
# <a name="using-the-object-cache-with-sharepoint-online"></a>Verwenden des Objektcaches mit SharePoint Online

In diesem Artikel wird der Unterschied zwischen der Verwendung des Objektcaches in SharePoint Server 2013 lokal und SharePoint Online erläutert.
  
Dies hat erhebliche negative Auswirkungen auf den Objektcache in SharePoint Onlinebereitstellung. Jede Abhängigkeit vom Objektcache in SharePoint Online verringert die Zuverlässigkeit Ihrer Seite. 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a>Funktionsweise des SharePoint Online- und SharePoint Server 2013-Objektcaches

Wenn SharePoint Server 2013 lokal gehostet wird, verfügt der Kunde über private Front-End-Webserver, die den Objektcache hosten. Dies bedeutet, dass der Cache für einen Kunden reserviert ist und nur durch den verfügbaren Speicher begrenzt ist, der dem Objektcache zugewiesen ist. Da im lokalen Szenario nur ein Kunde bedient wird, haben die Front-End-Webserver in der Regel Benutzer, die immer wieder Anforderungen an dieselben Websites stellen. Dies bedeutet, dass der Cache schnell voll wird und voll mit den Listenabfrageergebnissen und SharePoint objekten bleibt, die Ihre Benutzer regelmäßig anfordern.
  
![Zeigt Datenverkehr und Last an lokale Front-End-Webserver an](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
Wenn ein Benutzer also zum zweiten Mal eine Seite besucht, wird die Ladezeit der Seite verbessert. Nach mindestens vier Lasten derselben Seite wird die Seite auf allen Front-End-Webservern zwischengespeichert.
  
Im Gegensatz dazu gibt es in SharePoint Online viel mehr Server, aber auch viele weitere Websites. Jeder Benutzer kann eine Verbindung mit einem anderen Front-End-Webserver herstellen, auf dem der Cache nicht aufgefüllt ist. Möglicherweise wird der Cache für einen Server aufgefüllt, aber der nächste Benutzer dieses Front-End-Webservers fordert eine Seite von einer anderen Website an. Auch wenn der nächste Benutzer dieselbe Seite wie bei seinem vorherigen Besuch anfordert, wird der Lastenausgleich für einen anderen Front-End-Webserver ausgeführt, auf dem diese Seite nicht im Cache vorhanden ist. In diesem letzten Fall hilft die Zwischenspeicherung den Benutzern überhaupt nicht.
  
In der folgenden Abbildung stellt jeder Punkt eine Seite dar, die ein Benutzer anfordert und wo er zwischengespeichert wird. Unterschiedliche Farben stellen unterschiedliche Kunden dar, die gemeinsam die SaaS-Infrastruktur nutzen.
  
![Zeigt die Ergebnisse der Objekt zwischenspeicherung in SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
Wie Sie aus dem Diagramm sehen können, ist die Wahrscheinlichkeit gering, dass ein Benutzer mit der zwischengespeicherten Version seiner Seite auf einen Server trifft. Aufgrund des großen Durchsatzes und der Tatsache, dass die Server von vielen Standorten gemeinsam genutzt werden, dauert der Cache nicht lange, da nur so viel Speicherplatz für die Zwischenspeicherung verfügbar ist.
  
Aus all diesen Gründen ist es nicht effektiv, sich darauf zu verlassen, dass Benutzer zwischengespeicherte Objekte erhalten, um eine qualitativ hochwertige Benutzeroberfläche und Ladezeiten von Seiten in SharePoint online zu gewährleisten.
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a>Wenn wir uns nicht auf den Objektcache verlassen können, um die Leistung in SharePoint Online zu verbessern, was wird stattdessen verwendet?

Da Sie sich nicht auf die Zwischenspeicherung in SharePoint Online verlassen sollten, sollten Sie alternative Entwurfsansätze für SharePoint, die den Objektcache verwenden, auswerten. Dies bedeutet, dass Sie Ansätze für Leistungsprobleme verwenden, die nicht auf der Objektspeicherung beruhen, um gute Ergebnisse für Benutzer zu erzielen. Dies wird in einigen der anderen Artikel in dieser Reihe beschrieben und umfasst:
  
- [Navigationsoptionen für SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Minimierung und Bündelung in SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Verzögerung beim Laden von Bildern und JavaScript in SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    


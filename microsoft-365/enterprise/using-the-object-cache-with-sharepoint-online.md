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
  
Es gibt erhebliche negative Auswirkungen, wenn der Objektcache in SharePoint Online Bereitstellung unterstützt wird. Durch jede Abhängigkeit vom Objektcache in SharePoint Online wird die Zuverlässigkeit Ihrer Seite verringert. 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a>Funktionsweise des SharePoint Online-und SharePoint Server 2013-Objektcaches

Wenn SharePoint Server 2013 lokal gehostet wird, verfügt der Kunde über private Front-End-Webserver, die als Host für den Objektcache fungieren. Dies bedeutet, dass der Cache für einen einzelnen Kunden reserviert ist und nur dadurch beschränkt ist, wie viel Arbeitsspeicher verfügbar und dem Objektcache zugewiesen ist. Da nur ein Kunde im lokalen Szenario bedient wird, haben die Front-End-Webserver in der Regel Benutzer, die Anforderungen an dieselben Websites immer und immer wieder treffen. Dies bedeutet, dass der Cache vollständig schnell wird und voll von den Listen Abfrageergebnissen und SharePoint-Objekten bleibt, die Ihre Benutzer regelmäßig anfordern.
  
![Zeigt Datenverkehr und Last an lokale Front-End-Webserver](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
Dadurch wird beim zweiten Mal, wenn ein Benutzer eine Seite besucht, die Ladezeit der Seite verbessert. Nach mindestens vier Lasten derselben Seite wird die Seite auf allen Front-End-Webservern zwischengespeichert.
  
Im Gegensatz dazu gibt es in SharePoint Online viele weitere Server, aber auch viele weitere Websites. Jeder Benutzer kann eine Verbindung mit einem anderen Front-End-Webserver herstellen, auf dem der Cache nicht aufgefüllt ist. Oder vielleicht wird der Cache für einen Server aufgefüllt, aber der nächste Benutzer des Front-End-Webservers fordert eine Seite von einer anderen Website an. Oder auch dann, wenn der nächste Benutzer dieselbe Seite anfordert wie bei Ihrem vorherigen Besuch, wird der Lastenausgleich auf einen anderen Front-End-Webserver festgestellt, der diese Seite nicht im Cache hat. In diesem letzten Fall hilft die Zwischenspeicherung den Benutzern überhaupt nicht.
  
In der folgenden Abbildung steht jeder Punkt für eine Seite, die ein Benutzer anfordert und wo er zwischengespeichert wurde. Unterschiedliche Farben stellen unterschiedliche Kunden dar, die die gemeinsame Nutzung der SaaS-Infrastruktur nutzen.
  
![Zeigt die Ergebnisse der Objektzwischenspeicherung in SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
Wie Sie aus dem Diagramm sehen können, sind die Chancen eines bestimmten Benutzers, einen Server mit der zwischengespeicherten Version Ihrer Seite zu treffen, gering. Aufgrund des hohen Durchsatzes und der Tatsache, dass die Server von vielen Standorten gemeinsam genutzt werden, dauert der Cache auch nicht lange, da nur so viel Speicherplatz für die Zwischenspeicherung verfügbar ist.
  
Aus allen diesen Gründen ist das verlassen von Benutzern, die zwischengespeicherte Objekte erhalten, kein effektiver Weg, um eine qualitativ hochwertige Benutzeroberfläche und Seitenladezeiten in SharePoint Online sicherzustellen.
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a>Wenn wir nicht auf den Objektcache zurückgreifen können, um die Leistung in SharePoint Online zu verbessern, was verwenden wir stattdessen?

Da Sie sich nicht auf die Zwischenspeicherung in SharePoint Online verlassen sollten, sollten Sie alternative Entwurfsansätze für SharePoint-Anpassungen evaluieren, die den Objektcache verwenden. Dies bedeutet, dass Sie Methoden für Leistungsprobleme verwenden, die nicht auf die Objektzwischenspeicherung abzielen, um gute Ergebnisse für Benutzer zu erzielen. Dies wird in einigen der anderen Artikel in dieser Reihe beschrieben und umfasst Folgendes:
  
- [Navigationsoptionen für SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Minimierung und Bündelung in SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Verzögerung beim Laden von Bildern und JavaScript in SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    


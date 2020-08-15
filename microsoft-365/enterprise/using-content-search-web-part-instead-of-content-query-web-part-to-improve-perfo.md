---
title: Verwenden des Inhaltssuche-Webparts anstelle des Webpart für Inhaltsabfragen zum Verbessern der Leistung in SharePoint Online
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
description: In diesem Artikel erfahren Sie, wie Sie die Leistung steigern, indem Sie das Webpart für Inhaltsabfragen durch das Webpart für die Inhaltssuche in SharePoint Server 2013 und SharePoint Online ersetzen.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690885"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a>Verwenden des Inhaltssuche-Webparts anstelle des Webpart für Inhaltsabfragen zum Verbessern der Leistung in SharePoint Online

In diesem Artikel wird beschrieben, wie Sie die Leistung verbessern, indem Sie das Webpart für Inhaltsabfragen durch das Webpart für die Inhaltssuche in SharePoint Server 2013 und SharePoint Online ersetzen.
  
Eines der leistungsstärksten neuen Features von SharePoint Server 2013 und SharePoint Online ist das Inhaltssuche-Webpart (CSWP). Dieses Webpart verwendet den Suchindex, um schnell Ergebnisse abzurufen, die dem Benutzer angezeigt werden. Verwenden Sie das Inhaltssuche-Webpart anstelle des Inhaltsabfrage-Webparts (CQWP) auf Ihren Seiten, um die Leistung für Ihre Benutzer zu verbessern.
  
Die Verwendung eines Inhaltssuche-Webparts über ein Inhaltsabfrage-Webpart führt fast immer zu einer deutlich besseren Seiten Ladeleistung für SharePoint Online. Es gibt eine kleine zusätzliche Konfiguration, um die richtige Abfrage zu erhalten, aber die Belohnungen sind verbesserte Leistung und glücklicher Benutzer.
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a>Vergleichen der Leistungssteigerung, die Sie mit dem Webpart "Inhaltssuche" anstelle des Webparts für Inhaltsabfragen erzielen

Die folgenden Beispiele zeigen die relativen Leistungsgewinne, die Sie möglicherweise erhalten, wenn Sie ein Webpart für die Inhaltssuche anstelle eines Inhaltsabfrage-Webparts verwenden. Die Effekte sind mit einer komplexen Websitestruktur und sehr umfangreichen Inhaltsabfragen deutlicher.
  
Diese Beispielwebsite weist die folgenden Merkmale auf:
  
- 8 Ebenen von Unterwebsites.
    
- Listet die Verwendung eines benutzerdefinierten Inhaltstyps "Fruit" auf.
    
- Im Webpart ist die Inhaltsabfrage breit und gibt alle Elemente mit dem Inhaltstyp "Fruit" zurück.
    
- Im Beispiel werden nur 50-Elemente auf den 8 Websites verwendet. Die Effekte werden für Websites mit mehr Inhalt noch ausgeprägter.
    
Es folgt ein Screenshot der Ergebnisse des Webpart für Inhaltsabfragen.
  
![Grafik mit Inhaltsabfrage für WebPart](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
Suchen Sie in Internet Explorer auf der Registerkarte " **Netzwerk** " der F12-Entwicklertools die Details für den Antwortheader. Im folgenden Screenshot beträgt der Wert für die **SPRequestDuration** für diese Seite 924 Millisekunden. 
  
![Screenshot mit Anforderungsdauer von 924](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 **SPRequestDuration** gibt an, wie viel Arbeit auf dem Server ausgeführt wird, um die Seite vorzubereiten. Durch das Wechseln von Inhalten nach Abfrage Webparts mit Inhalten durch Such-Webparts wird die Zeit für das Rendern der Seite drastisch reduziert. Im Gegensatz dazu weist eine Seite mit einem äquivalenten Inhaltssuche-Webpart, das die gleiche Anzahl von Ergebnissen zurückgibt, einen **SPRequestDuration** -Wert von 106 Millisekunden auf, wie in diesem Screenshot gezeigt: 
  
![Screenshot mit Anforderungsdauer von 106](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a>Hinzufügen eines Inhaltssuche-Webparts in SharePoint Online

Das Hinzufügen eines Inhaltssuche-Webparts ähnelt einem Webpart für reguläre Inhaltsabfragen sehr. Weitere Informationen finden Sie im Abschnitt  *"Hinzufügen eines Inhaltssuche-Webparts"*  unter [Konfigurieren eines Inhaltssuche-Webparts in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a>Erstellen der richtigen Suchabfrage für das Webpart für die Inhaltssuche

Nachdem Sie das Webpart für die Inhaltssuche hinzugefügt haben, können Sie die Suche verfeinern und die gewünschten Elemente zurückgeben. Ausführliche Anweisungen dazu finden Sie im Abschnitt  *"Anzeigen von Inhalten durch Konfigurieren einer erweiterten Abfrage in einem Inhaltssuche-Webpart"*  unter [Konfigurieren eines Inhaltssuche-Webparts in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).
  
## <a name="query-building-and-testing-tool"></a>Tool zum Erstellen und Testen von Abfragen

Ein Tool zum Erstellen und Testen komplexer Abfragen finden Sie unter dem [Suchabfrage Tool](https://sp2013searchtool.codeplex.com/) auf CodePlex. 
  


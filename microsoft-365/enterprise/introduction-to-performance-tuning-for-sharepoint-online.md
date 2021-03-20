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
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>Einführung in die Leistungsoptimierung für SharePoint Online

In diesem Artikel werden die spezifischen Aspekte erläutert, die Sie beim Entwerfen von Seiten für eine optimale Leistung in SharePoint Online berücksichtigen müssen.
     
## <a name="sharepoint-online-metrics"></a>SharePoint Online-Metriken

Die folgenden breiten Metriken für SharePoint Online bieten reale Daten zur Leistung:
  
- Wie schnell Seiten geladen werden
    
- Wie viele Roundtrips pro Seite erforderlich sind
    
- Probleme mit dem Dienst
    
- Andere Dinge, die leistungsbeeinträchtigungen verursachen
    
### <a name="conclusions-reached-because-of-the-data"></a>Schlussfolgerungen aufgrund der Daten

Die Daten sagen uns:
  
- Die meisten Seiten können in SharePoint Online gut verwendet werden.
    
- Nicht angepasste Seiten werden sehr schnell geladen.
    
- OneDrive for Business, Teamwebsites und Systemseiten wie _layouts usw. können schnell geladen werden.
    
- Die langsamsten 1 % der SharePoint Online-Seiten dauern mehr als 5.000 Millisekunden.
    
Ein einfacher Benchmarktest, den Sie verwenden können, wäre das Messen der Leistung, indem Sie die Ladezeit Ihres eigenen Portals mit der Ladezeit der OneDrive for #A0 vergleichen, da nur wenige angepasste Features verwendet werden. Dies ist häufig der erste Schritt, den der Support bei der Problembehandlung bei der Netzwerkleistung durchführen muss.
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>Verwenden eines Standardbenutzerkontos beim Überprüfen der Leistung

Ein Websitesammlungsadministrator, Websitebesitzer, Editor oder Mitwirkender gehört zu weiteren Sicherheitsgruppen, verfügt über zusätzliche Berechtigungen und verfügt daher über zusätzliche Elemente, die SharePoint auf einer Seite lädt.
  
Dies gilt für lokale SharePoint- und SharePoint Online-Dienste, aber in einem lokalen Szenario werden die Unterschiede nicht so leicht bemerkt wie in SharePoint Online.
  
Um die Funktionsweise einer Seite für Benutzer richtig auszuwerten, sollten Sie ein Standardbenutzerkonto verwenden, um das Laden der Erstellungssteuerelemente und zusätzlichen Datenverkehr im Zusammenhang mit Sicherheitsgruppen zu vermeiden.
  
## <a name="connection-categories-for-performance-tuning"></a>Verbindungskategorien für leistungsoptimierung

Sie können die Verbindungen zwischen dem Server und dem Benutzer in drei Hauptkomponenten kategorisieren. Berücksichtigen Sie diese beim Entwerfen von SharePoint Online-Seiten, um einen Einblick in die Ladezeiten zu erhalten.
  
- **Server** Die Server, die Microsoft in Rechenzentren hostet.
    
- **Netzwerk** Das Microsoft-Netzwerk, das Internet und Ihr lokales Netzwerk zwischen dem Datencenter und Ihren Benutzern.
    
- **Browser** Der Ort, an dem die Seite geladen wird.
    
Innerhalb dieser drei Verbindungen gibt es in der Regel fünf Gründe, die 95 % der langsamen Seiten verursachen. Jeder dieser Gründe wird in diesem Artikel erläutert:
  
- Navigationsprobleme
    
- Inhaltsrollup
    
- Große Dateien
    
- Viele Anforderungen an den Server
    
- Web part processing
    
### <a name="server-connection"></a>Serververbindung

Viele der Probleme, die sich auf die Leistung mit sharePoint lokal auswirken, gelten auch für SharePoint Online.
  
Wie Sie erwarten, haben Sie viel mehr Kontrolle über die Leistung von Servern mit lokalem SharePoint. Bei SharePoint Online sieht dies etwas anders aus. Je mehr Arbeit Sie für einen Server erstellen, um so länger dauert das Rendern einer Seite. Bei SharePoint sind komplexe Seiten mit mehreren Webparts der größte Fehler in dieser Hinsicht.
  
Lokales SharePoint Server
  
![Screenshot des lokalen Servers](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint Online
  
![Screenshot des Servers online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
Bei SharePoint Online können bestimmte Seitenanforderungen tatsächlich mehrere Server aufrufen. Sie könnten am Ende eine Matrix von Anforderungen zwischen Servern für eine einzelne Anforderung erhalten. Diese Interaktionen sind aus Sicht des Seitenlades kostspielig und werden langsam.
  
Beispiele für diese Server-zu-Server-Interaktionen sind:
  
- Web to SQL Server
    
- Web zu Anwendungsservern
    
Die andere Sache, die Serverinteraktionen verlangsamen kann, sind Cache-Verpasste. Im Gegensatz zu lokalen SharePoint besteht eine sehr geringe Wahrscheinlichkeit, dass Sie auf denselben Server für eine Seite treffen, die Sie zuvor besucht haben. Dadurch wird die Objektspeicherung veraltet.
  
### <a name="network-connection"></a>Netzwerkverbindung 

Bei lokalem SharePoint, das kein WAN verwendet, können Sie eine Hochgeschwindigkeitsverbindung zwischen Rechenzentren und Endbenutzern verwenden. Im Allgemeinen ist die Verwaltung aus Netzwerksicht einfach.
  
Mit SharePoint Online müssen einige weitere Faktoren berücksichtigt werden. Zum Beispiel:
  
- Das Microsoft-Netzwerk
    
- Das Internet
    
- Der ISP
    
Unabhängig davon, welche Version von SharePoint (und welches Netzwerk) Sie verwenden, gehören folgende Dinge, die in der Regel dazu führen, dass das Netzwerk ausgelastet ist:
  
- Große Nutzlast
    
- Viele Dateien
    
- Großer physischer Abstand zum Server
    
Ein Feature, das Sie in SharePoint Online nutzen können, ist das Microsoft CDN (Content Delivery Network). Ein CDN ist im Wesentlichen eine verteilte Sammlung von Servern, die über mehrere Rechenzentren bereitgestellt werden. Mit einem CDN können Inhalte auf Seiten auf einem Server in der Nähe des Clients gehostet werden, auch wenn der Client weit vom ursprünglichen SharePoint Server entfernt ist. Microsoft verwendet dies in Zukunft mehr, um lokale Instanzen von Seiten zu speichern, die nicht angepasst werden können, z. B. die SharePoint Online-Administrator-Homepage. Weitere Informationen zu CDNs finden Sie unter [Content Delivery Networks](content-delivery-networks.md).
  
Etwas, das Sie beachten müssen, aber möglicherweise nicht in der Lage sind, viel zu tun, ist die Verbindungsgeschwindigkeit Ihres Internetdienstanbieters. Ein einfaches Geschwindigkeitstesttool gibt Die Verbindungsgeschwindigkeit an.
  
### <a name="browser-connection"></a>Browserverbindung

Es gibt einige Faktoren, die bei Webbrowsern aus Leistungssicht berücksichtigt werden müssen.
  
Das Besuchen komplexer Seiten wirkt sich auf die Leistung aus. Die meisten Browser verfügen nur über einen kleinen Cache (ca. 90 MB), während die durchschnittliche Webseite in der Regel etwa 1,6 MB beträgt. Dies dauert nicht lange, bis sie sich ernennen.
  
Bandbreite kann auch ein Problem sein. Wenn ein Benutzer beispielsweise Videos in einer anderen Sitzung anschaut, wirkt sich dies auf die Leistung Ihrer SharePoint-Seite aus. Sie können zwar nicht verhindern, dass Benutzer Medien streamen, sie können jedoch steuern, wie eine Seite für Benutzer geladen wird.
  
In den folgenden Artikeln finden Sie verschiedene Anpassungstechniken für SharePoint Online-Seiten und andere bewährte Methoden, die Ihnen dabei helfen, eine optimale Leistung zu erzielen.
  
- [Navigationsoptionen für SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Verwenden des Tools "Seitendiagnose" für SharePoint Online](page-diagnostics-for-spo.md)
    
- [Bildoptimierung für SharePoint Online](image-optimization-for-sharepoint-online.md)
    
- [Verzögerung beim Laden von Bildern und JavaScript in SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [Minimierung und Bündelung in SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Verwenden des Inhaltssuchwebteils anstelle des Inhaltsabfragewebteils zur Verbesserung der Leistung in SharePoint Online](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [Kapazitätsplanung und Auslastungstests für SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [Diagnose von Leistungsproblemen mit SharePoint Online](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [Verwenden des Objektcaches mit SharePoint Online](using-the-object-cache-with-sharepoint-online.md)
    
- [Gewusst wie: Vermeiden von Einschränkungen oder Sperren in SharePoint Online](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)

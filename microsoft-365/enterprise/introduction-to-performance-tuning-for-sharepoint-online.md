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
description: In diesem Artikel wird erläutert, welche Aspekte beim Entwerfen von Seiten für eine optimale Leistung in SharePoint Online berücksichtigt werden müssen.
ms.openlocfilehash: d3a9dedbd5812774b81494af0f8defa5568f7dac
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690785"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>Einführung in die Leistungsoptimierung für SharePoint Online

In diesem Artikel wird erläutert, welche Aspekte beim Entwerfen von Seiten für eine optimale Leistung in SharePoint Online berücksichtigt werden müssen.
     
## <a name="sharepoint-online-metrics"></a>SharePoint Online Metriken

Die folgenden allgemeinen Metriken für SharePoint Online bieten reale Daten zur Leistung:
  
- Wie schnelle Seiten laden
    
- Wie viele Rundfahrten pro Seite erforderlich sind
    
- Probleme mit dem Dienst
    
- Andere Faktoren, die zu Leistungseinbußen führen
    
### <a name="conclusions-reached-because-of-the-data"></a>Schlussfolgerungen, die aufgrund der Daten erzielt wurden

Die Daten erzählen uns:
  
- Die meisten Seiten werden auf SharePoint Online gut ausgeführt.
    
- Nicht angepasste Seiten werden sehr schnell belastet.
    
- OneDrive für Unternehmen, Teamwebsites und System Seiten wie _layouts usw. sind schnell zu laden.
    
- Die langsamsten 1% SharePoint Online Seiten benötigen mehr als 5.000 Millisekunden zum Laden.
    
Ein einfacher Benchmark-Test, den Sie verwenden können, wäre die Messung der Leistung durch Vergleich der Ladezeit Ihres eigenen Portals mit der Ladezeit der OneDrive für Unternehmen Homepage, da einige angepasste Features verwendet werden. Dies wird häufig der erste Schritt sein, den Sie bei der Behebung von Problemen mit der Netzwerkleistung durchführen werden.
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>Verwenden eines Standardbenutzerkontos beim Überprüfen der Leistung

Ein Website Sammlungs Administrator, Websitebesitzer, Editor oder Mitwirkende gehört zu weiteren Sicherheitsgruppen, verfügt über zusätzliche Berechtigungen und verfügt daher über zusätzliche Elemente, die SharePoint auf einer Seite lädt.
  
Dies gilt für lokale SharePoint-und SharePoint Online, aber in einem lokalen Szenario werden die Unterschiede nicht so leicht bemerkt wie in SharePoint Online.
  
Um die Leistung einer Seite für Benutzer richtig auszuwerten, sollten Sie ein Standardbenutzerkonto verwenden, um zu vermeiden, dass die Erstellungs Steuerelemente und der zusätzliche Datenverkehr in Bezug auf Sicherheitsgruppen geladen werden.
  
## <a name="connection-categories-for-performance-tuning"></a>Verbindungskategorien für die Leistungsoptimierung

Sie können die Verbindungen zwischen dem Server und dem Benutzer in drei Hauptkomponenten kategorisieren. Berücksichtigen Sie diese beim Entwerfen SharePoint Online Seiten für Einblicke in Ladezeiten.
  
- **Server** Die Server, die Microsoft in Rechenzentren hostet.
    
- **Netzwerk** Das Microsoft-Netzwerk, das Internet und Ihr lokales Netzwerk zwischen dem Rechenzentrum und ihren Benutzern.
    
- **Browser** Wo die Seite geladen wird.
    
Innerhalb dieser drei Verbindungen gibt es in der Regel fünf Gründe, die 95% der langsamen Seiten verursachen. Jeder dieser Gründe wird in diesem Artikel behandelt:
  
- Navigationsprobleme
    
- Inhalts-Rollup
    
- Große Dateien
    
- Viele Anforderungen an den Server
    
- Webparts-Verarbeitung
    
### <a name="server-connection"></a>Server Verbindung

Viele der Probleme, die sich auf die Leistung mit SharePoint lokal auswirken, gelten auch für SharePoint Online.
  
Wie Sie es erwarten, haben Sie weitaus mehr Kontrolle darüber, wie Server mit lokalem SharePoint ausgeführt werden. Mit SharePoint Online sind die Dinge ein wenig anders. Je mehr Arbeit ein Server macht, desto länger dauert das Rendern einer Seite. Bei SharePoint ist der größte Übeltäter in dieser Hinsicht komplexe Seiten mit mehreren Webparts.
  
SharePoint Server lokal
  
![Screenshot des Servers lokal](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint Online
  
![Screenshot von Server Online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
Mit SharePoint Online können bestimmte Seitenanforderungen tatsächlich mehrere Server aufrufen. Sie können am Ende eine Matrix von Anforderungen zwischen Servern für eine einzelne Anforderung erhalten. Diese Interaktionen sind aus Sicht der Seitenauslastung teuer und machen die Dinge langsam.
  
Beispiele für diese Server-zu-Server-Interaktionen sind:
  
- Webserver zu SQL Server
    
- Webserver zu Anwendungsservern
    
Die andere Sache, die Serverinteraktionen verlangsamen kann, ist Cache fehlungen. Im Gegensatz zu lokalen SharePoint gibt es eine sehr geringe Chance, dass Sie auf denselben Server für eine Seite treffen, die Sie zuvor besucht haben. Dadurch wird die Objektzwischenspeicherung obsolet.
  
### <a name="network-connection"></a>Netzwerkverbindung 

Bei einer lokalen SharePoint-Bereitstellung, die kein WAN verwendet, können Sie eine Hochgeschwindigkeitsverbindung zwischen Rechenzentrum und Endbenutzern verwenden. Im Allgemeinen ist das Verwalten von Dingen aus netzwerksicht einfach.
  
Bei SharePoint Online müssen einige weitere Faktoren berücksichtigt werden. Zum Beispiel:
  
- Das Microsoft-Netzwerk
    
- Das Internet
    
- Der ISP
    
Unabhängig davon, welche Version von SharePoint (und welches Netzwerk) Sie verwenden, umfassen die folgenden Dinge, die in der Regel dazu führen, dass das Netzwerk ausgelastet ist:
  
- Große Nutzlast
    
- Viele Dateien
    
- Großer physikalischer Abstand zum Server
    
Ein Feature, das Sie in SharePoint Online nutzen können, ist das Microsoft CDN (Content Delivery Network). Ein CDN ist im Grunde eine verteilte Sammlung von Servern, die in mehreren Rechenzentren bereitgestellt werden. Bei einem CDN können Inhalte auf Seiten auf einem Server in der Nähe des Clients gehostet werden, auch wenn der Client weit vom ursprünglichen SharePoint Server entfernt ist. Dies wird von Microsoft in Zukunft noch häufiger verwendet, um lokale Instanzen von Seiten zu speichern, die nicht angepasst werden können, beispielsweise die Startseite SharePoint Online Administrators. Weitere Informationen zu CDNs finden Sie unter [Content Delivery Networks](content-delivery-networks.md).
  
Was Sie beachten müssen, aber möglicherweise nicht viel zu tun haben, ist die Verbindungsgeschwindigkeit Ihres ISP. Ein einfaches Test Tool für Geschwindigkeitstests informiert Sie über die Verbindungsgeschwindigkeit.
  
### <a name="browser-connection"></a>Browser Verbindung

Es gibt einige Faktoren, die bei Webbrowsern aus Sicht der Leistung berücksichtigt werden müssen.
  
Der Besuch komplexer Seiten wirkt sich auf die Leistung aus. Die meisten Browser haben nur einen kleinen Cache (um 90MB), während die durchschnittliche Webseite normalerweise etwa 1,6 MB beträgt. Es dauert nicht lange, bis Sie sich verbraucht haben.
  
Bandbreite ist möglicherweise auch ein Problem. Wenn ein Benutzer beispielsweise Videos in einer anderen Sitzung anschaut, wirkt sich dies auf die Leistung der SharePoint-Seite aus. Sie können zwar nicht verhindern, dass Benutzer Medien streamen, aber Sie können steuern, wie eine Seite für die Benutzer laden wird.
  
Lesen Sie die folgenden Artikel für verschiedene Techniken zur SharePoint Online Seitenanpassung und andere bewährte Methoden, um eine optimale Leistung zu erzielen.
  
- [Navigationsoptionen für SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Verwenden des Seiten Diagnosetools für SharePoint Online](page-diagnostics-for-spo.md)
    
- [Bildoptimierung für SharePoint Online](image-optimization-for-sharepoint-online.md)
    
- [Verzögerung beim Laden von Bildern und JavaScript in SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [Minimierung und Bündelung in SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Verwenden des Inhaltssuche-Webparts anstelle des Webpart für Inhaltsabfragen zum Verbessern der Leistung in SharePoint Online](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [Kapazitätsplanung und Auslastungstests für SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [Diagnose von Leistungsproblemen mit SharePoint Online](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [Verwenden des Objektcaches mit SharePoint Online](using-the-object-cache-with-sharepoint-online.md)
    
- [Gewusst wie: Vermeiden von Einschränkungen oder Sperren in SharePoint Online](https://msdn.microsoft.com/library/office/dn889829.aspx)
    


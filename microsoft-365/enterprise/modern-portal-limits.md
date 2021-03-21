---
title: Grenzwerte für moderne SharePoint Online-Portalwebsites
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/9/2019
audience: Admin
ms.topic: interactive-tutorial
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
description: Erfahren Sie mehr über Leistungsempfehlungen für moderne Websites in SharePoint Online, z. B. einschränken von Aufrufen an Sharepoint und externen Endpunkten.
ms.openlocfilehash: 28c32be276f6c27194d164708e268a5cd36ac957
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925320"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>Grenzwerte für moderne SharePoint Online-Portalwebsites

Dieser Artikel enthält Leistungsempfehlungen für moderne Portalwebsites in SharePoint Online. Verwenden Sie die Richtlinien in diesem Artikel, um die Leistung moderner Portalwebsites zu optimieren und häufige Leistungsprobleme zu vermeiden.

## <a name="performance-considerations-for-modern-portal-sites"></a>Leistungsüberlegungen für moderne Portalwebsites

Aus Sicht der Leistungsoptimierung gibt es einige Merkmale, die moderne Portalwebsites einzigartig machen. Der Hauptunterschied zwischen Zusammenarbeit und Portalwebsites in SharePoint Online ist die Skalierung. Es wird allgemein erwartet, dass Portalwebsites einer größeren Anzahl von Benutzern mehr Seitenansichten als Websites für die Zusammenarbeit zur Verfügung stellen und wahrscheinlich mehr statische Inhalte und weniger bearbeitbare Ressourcen enthalten. Darüber hinaus unterscheidet sich die Architektur moderner Websites von klassischen Websites, da der Großteil der Verarbeitung, die beim Rendern von Seiten und beim Ausführen von Code beteiligt ist, auf dem Client statt auf dem Server erfolgt.

Die Leistungsoptimierung für moderne Portalwebsites konzentriert sich in erster Linie auf einige allgemeine Ziele:

- Verringern der Gesamtgröße der Komponenten jeder Websiteseite
- Ausladen des Hostings gängiger statischer Dateien wie Bilder, Stylesheets und Skripts in CDN
- Beschränken von Aufrufen an SharePoint und externe Endpunkte auf das Erforderliche
- Vermeiden doppelter Anforderungen für denselben Inhalt

Viele der Richtlinien in diesem Artikel konzentrieren sich auf die Minimierung und Optimierung von Aufrufen an SharePoint Online. Wiederholte Aufrufe jedes Mal, wenn eine Seite geladen wird, beeinträchtigen die Leistung der Benutzer, da die Informationen jedes Mal vom Dienst abgerufen werden, auch wenn sie sich nicht geändert hat. Daher können Anforderungen an SharePoint entweder als Anrufe kategorisiert werden, die für alle Benutzer üblich sind, oder als Anrufe, die für jeden einzelnen Benutzer erforderlich sind. Die Ergebnisse dieser beiden Anrufkategorien sollten zwischengespeichert werden, um die Benutzeroberfläche zu optimieren.

>[!NOTE]
>Verwenden Sie [das Tool Seitendiagnose für SharePoint](./page-diagnostics-for-spo.md) als Ausgangspunkt, um bestimmte Leistungsmetriken auf SharePoint Online-Websiteseiten zu analysieren.

## <a name="modern-portal-site-limits-and-recommendations"></a>Grenzwerte und Empfehlungen für moderne Portalwebsites

|**Grenze**|**Maximal empfohlener Wert**|**Notizen**|
|:-----|:-----|:-----|:-----|
|Seiten und Nachrichtenelemente  <br/> |5.000 pro Website  <br/> |Es wird empfohlen, die Anzahl der Seiten und Nachrichtenelemente auf einer modernen Portalwebsite auf unter 5.000 zu begrenzen.  <br/> |
|Webparts auf einer Seite  <br/> |20 pro Seite  <br/> |Es wird empfohlen, 20 oder weniger Webparts pro Seite insgesamt zu verwenden, einschließlich der einsatzfertigen Microsoft-Webparts und benutzerdefinierter Webparts. <br/> Weitere Informationen finden Sie unter [Optimieren der Web part-Leistung auf modernen SharePoint Online-Websiteseiten](modern-web-part-optimization.md).  <br/> |
|Dynamische Webparts auf einer Seite  <br/> |4 pro Seite  <br/> |Dynamische Webparts, die eine oder mehrere Abfragen an SharePoint zum Abrufen der neuesten Daten ausführen, sollten auf 4 pro Seite beschränkt sein. Das  News-Webteil ist ein Beispiel für ein dynamisches Webteil. <br/> Weitere Informationen finden Sie unter [Optimieren der Web part-Leistung auf modernen SharePoint Online-Websiteseiten](modern-web-part-optimization.md).    <br/> |
|Sicherheitsgruppen  <br/> |20 pro Website  <br/> |Die Anzahl der Sicherheitsgruppen wirkt sich auf die Skalierung vieler Abfragen auf modernen Portalwebsites aus. Es wird empfohlen, die Anzahl der Sicherheitsgruppen auf einen möglichst kleinen Satz mit nicht mehr als 20 pro Standort zu beschränken.  <br/> |
|Elemente in der Websitenavigation  <br/> |100 pro Website  <br/> |Es wird empfohlen, weniger als 100 Elemente zur Websitenavigation zu hinzufügen und dass Sie die verwendung von out-of-the-box-Navigationssteuerelementen verwenden.  <br/> Weitere Informationen finden Sie unter [Optimieren der Seitengewichtung auf modernen SharePoint Online-Websiteseiten](modern-page-weight-optimization.md). <br/> |
|Maximale Bildgröße  <br/> |300 KB pro Bild  <br/> |Es wird empfohlen, die Größe von Bildern auf 300 KB oder kleiner zu beschränken und ein CDN zum Hosten von Bildern, Stylesheets und Skripts zu verwenden. <br/>Weitere Informationen finden Sie unter Optimieren von Bildern [auf modernen SharePoint](modern-image-optimization.md) Online-Websiteseiten und [Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online](use-microsoft-365-cdn-with-spo.md).  <br/> |
|Benutzer mit Bearbeitungsrechten  <br/> |200 Benutzer pro Website  <br/> |SharePoint-Portalwebsites sind für das Anzeigen und Nutzen von Inhalten optimiert. Bearbeitungsberechtigungen in einem Portal sollten auf eine eingeschränkte Gruppe von Benutzern beschränkt sein, da Bearbeitungsberechtigungen zusätzliche Steuerelemente herunterladen und daher für diese Benutzer langsamer sind. Eine übermäßig große Anzahl von Benutzern mit Bearbeitungsberechtigungen wirkt sich daher auf die Gesamterfahrung aus. <br/> |
|iFrames eines Drittanbieters  <br/> |2 pro Seite  <br/> |iFrames sind unvorhersehbar langsam, da sie eine separate externe Seite mit allen zugeordneten Inhalten wie javascript, CSS und Framework-Elementen laden. Wenn Sie iFrames verwenden müssen, beschränken Sie ihre Anzahl auf 2 oder weniger pro Seite.<br/> Weitere Informationen finden Sie unter [Optimize iFrames in SharePoint Online modern and classic publishing site pages](modern-iframe-optimization.md). <br/> |
|Anrufe an den UPA-Dienst  <br/> |1 pro Benutzer pro Stunde  <br/> |Es wird empfohlen, keine Aufrufe pro _Anforderung_ an den UPA (User Profile Application)-Dienst zu senden. Die [Microsoft Graph-API](/graph/call-api) und [PageContext](/javascript/api/sp-page-context/pagecontext?view=sp-typescript-latest) können zum Abfragen von Benutzerinformationen verwendet werden.  <br/> Wenn ein UPA-Dienstaufruf erforderlich ist, nehmen Sie bei Bedarf einen einzelnen Anruf vor, und speichern Sie die Informationen für die Wiederverwendung in derselben Sitzung zwischen. |
|Aufrufe des Taxonomiediensts  <br/> |5 pro Benutzer pro Stunde  <br/> |Es wird empfohlen, keine Aufrufe pro _Anforderung_ an den Taxonomiedienst zu senden. Wenn Taxonomiedienstaufrufe erforderlich sind, speichern Sie die Informationen für die Wiederverwendung in derselben Sitzung zwischen. <br/> Weitere Informationen finden Sie unter [Optimieren von Seitenaufrufen in modernen und klassischen Veröffentlichungswebsiteseiten von SharePoint Online.](modern-page-call-optimization.md) <br/> |

## <a name="related-topics"></a>Verwandte Themen

[Erstellen eines fehlerfreien SharePoint-Portals](/sharepoint/portal-health)

[Optimieren der Leistung von SharePoint Online](tune-sharepoint-online-performance.md)

[Optimieren der Leistung von Office 365](tune-microsoft-365-performance.md)

[SharePoint Online-Beschränkungen](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Leistung in der modernen SharePoint-Oberfläche](/sharepoint/modern-experience-performance)

[Leitfaden zur Leistung für SharePoint Online-Portale](/sharepoint/dev/solution-guidance/portal-performance)
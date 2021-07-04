---
title: SharePoint Websitebeschränkungen für moderne Onlineportale
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
description: Erfahren Sie mehr über Leistungsempfehlungen für moderne Websites in SharePoint Online, z. B. das Einschränken von Aufrufen an SharePoint und externe Endpunkte.
ms.openlocfilehash: 2429869c5397e0260876ee5a765ea18ae3fc42a1
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288875"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>SharePoint Websitebeschränkungen für moderne Onlineportale

Dieser Artikel enthält Leistungsempfehlungen für moderne Portalwebsites in SharePoint Online. Verwenden Sie die Richtlinien in diesem Artikel, um die Leistung moderner Portalwebsites zu optimieren und häufige Leistungsprobleme zu vermeiden.

## <a name="performance-considerations-for-modern-portal-sites"></a>Überlegungen zur Leistung moderner Portalwebsites

Aus der Sicht der Leistungsoptimierung gibt es einige Merkmale, die moderne Portalwebsites einzigartig machen. Der Hauptunterschied zwischen Zusammenarbeits- und Portalwebsites in SharePoint Online ist die Skalierung. Von Portalwebsites wird in der Regel erwartet, dass sie mehr Seitenaufrufe für eine größere Anzahl von Benutzern bereitstellen als Websites für die Zusammenarbeit, und sie enthalten wahrscheinlich mehr statische Inhalte und weniger bearbeitbare Ressourcen. Darüber hinaus unterscheidet sich die Architektur moderner Websites von klassischen Websites darin, dass der Großteil der Verarbeitung zum Rendern von Seiten und zum Ausführen von Code auf dem Client und nicht auf dem Server stattfindet.

Die Leistungsoptimierung für moderne Portalwebsites konzentriert sich in erster Linie auf einige allgemeine Ziele:

- Verringern der Gesamtgröße der Komponenten jeder Websiteseite
- Auslagern des Hostings gängiger statischer Dateien wie Bilder, Stylesheets und Skripts an CDN
- Beschränken Sie Aufrufe von SharePoint und externen Endpunkten auf die erforderlichen Elemente.
- Vermeiden doppelter Anforderungen für denselben Inhalt

Viele der Richtlinien in diesem Artikel konzentrieren sich auf das Minimieren und Optimieren von Aufrufen von SharePoint Online. Wiederholte Aufrufe bei jedem Laden einer Seite wirken sich auf die Leistung der Benutzer aus, da die Informationen jedes Mal vom Dienst abgerufen werden, auch wenn sie nicht geändert wurden. Daher können Anforderungen an SharePoint entweder als Anrufe kategorisiert werden, die für alle Benutzer üblich sind, oder als Anrufe, die für jeden einzelnen Benutzer erforderlich sind. Die Ergebnisse dieser beiden Anrufkategorien sollten zwischengespeichert werden, um die Benutzererfahrung zu optimieren.

>[!NOTE]
>Verwenden Sie das [Tool "Seitendiagnose für SharePoint"](./page-diagnostics-for-spo.md) als Ausgangspunkt, um bestimmte Leistungsmetriken auf SharePoint Onlinewebsiteseiten zu analysieren.

## <a name="modern-portal-site-limits-and-recommendations"></a>Grenzwerte und Empfehlungen für moderne Portalwebsites

|**Grenze**|**Empfohlener Maximalwert**|**Hinweise**|
|:-----|:-----|:-----|:-----|
|Seiten und Nachrichtenelemente  <br/> |5.000 pro Website  <br/> |Es wird empfohlen, die Anzahl der Seiten und Nachrichtenelemente auf einer modernen Portalwebsite auf unter 5.000 zu beschränken.  <br/> |
|Webparts auf einer Seite  <br/> |20 pro Seite  <br/> |Es wird empfohlen, 20 oder weniger Webparts insgesamt pro Seite zu verwenden, einschließlich sofort einsatzbereiter Microsoft-Webparts und benutzerdefinierter Webparts. <br/> Weitere Informationen finden Sie unter [Optimieren der Webpartleistung in SharePoint modernen Onlinewebsiteseiten.](modern-web-part-optimization.md)  <br/> |
|Dynamische Webparts auf einer Seite  <br/> |4 pro Seite  <br/> |Dynamische Webparts, die eine oder mehrere Abfragen zum SharePoint durchführen, um die neuesten Daten abzurufen, sollten auf 4 pro Seite beschränkt sein. Das  News-Webpart ist ein Beispiel für ein dynamisches Webpart. <br/> Weitere Informationen finden Sie unter [Optimieren der Webpartleistung in SharePoint modernen Onlinewebsiteseiten.](modern-web-part-optimization.md)    <br/> |
|Sicherheitsgruppen  <br/> |20 pro Website  <br/> |Die Anzahl der Sicherheitsgruppen wirkt sich auf das Ausmaß vieler Abfragen auf modernen Portalwebsites aus. Es wird empfohlen, die Anzahl der Sicherheitsgruppen auf so klein wie möglich zu beschränken, mit höchstens 20 pro Standort.  <br/> |
|Elemente in der Websitenavigation  <br/> |100 pro Website  <br/> |Es wird empfohlen, der Websitenavigation weniger als 100 Elemente hinzuzufügen und sofort einsatzbereite Navigationssteuerelemente zu verwenden.  <br/> Weitere Informationen finden Sie unter Optimieren der [Seitenstärke in SharePoint modernen Onlinewebsiteseiten.](modern-page-weight-optimization.md) <br/> |
|Maximale Bildgröße  <br/> |300 Kb pro Bild  <br/> |Es wird empfohlen, die Größe von Bildern auf 300 KB oder kleiner zu beschränken und eine CDN zum Hosten von Bildern, Stylesheets und Skripts zu verwenden. <br/>Weitere Informationen finden Sie unter [Optimieren von Bildern auf SharePoint modernen Online-Websiteseiten](modern-image-optimization.md) und Verwenden des Office 365 Content Delivery Network [(CDN) mit SharePoint Online.](use-microsoft-365-cdn-with-spo.md)  <br/> |
|Benutzer mit Bearbeitungsrechten  <br/> |200 Benutzer pro Website  <br/> |SharePoint Portalwebsites sind für das Anzeigen und Verwenden von Inhalten optimiert. Bearbeitungsberechtigungen für ein Portal sollten auf eine eingeschränkte Gruppe von Benutzern beschränkt sein, da Bearbeitungsberechtigungen zusätzliche Steuerelemente herunterladen und daher für diese Benutzer langsamer ausgeführt werden. Eine übermäßige Anzahl von Benutzern mit Bearbeitungsberechtigungen wirkt sich daher auf die Gesamterfahrung aus. <br/> |
|iFrames von Drittanbietern  <br/> |2 pro Seite  <br/> |iFrames sind unvorhersehbar langsam, da sie eine separate externe Seite laden, einschließlich aller zugehörigen Inhalte wie Javascript, CSS und Framework-Elemente. Wenn Sie iFrames verwenden müssen, beschränken Sie deren Anzahl auf 2 oder weniger pro Seite.<br/> Weitere Informationen finden Sie unter [Optimieren von iFrames in SharePoint modernen und klassischen Online-Veröffentlichungswebsiteseiten.](modern-iframe-optimization.md) <br/> |
|Aufrufe des UPA-Diensts  <br/> |1 pro Benutzer und Stunde  <br/> |Es wird empfohlen, dass Sie keine _Aufrufe pro Anforderung_ an den UPA-Dienst (Benutzerprofilanwendung) senden. Die [Microsoft Graph-API](/graph/call-api) und [PageContext](/javascript/api/sp-page-context/pagecontext) können zum Abfragen von Benutzerinformationen verwendet werden.  <br/> Wenn ein UPA-Dienstaufruf erforderlich ist, führen Sie bei Bedarf einen einzelnen Aufruf durch, und speichern Sie dann die Informationen zwischen, um sie in derselben Sitzung wiederzuverwenden. |
|Aufrufe des Taxonomiediensts  <br/> |5 pro Benutzer und Stunde  <br/> |Es wird empfohlen, dass Sie keine _Aufrufe pro Anforderung_ an den Taxonomiedienst tätigen. Wenn Taxonomiedienstaufrufe erforderlich sind, speichern Sie die Informationen zwischen, um sie in derselben Sitzung wiederzuverwenden. <br/> Weitere Informationen finden Sie unter Optimieren von [Seitenaufrufen in SharePoint modernen und klassischen Online-Veröffentlichungswebsiteseiten.](modern-page-call-optimization.md) <br/> |

## <a name="related-topics"></a>Verwandte Themen

[Erstellen eines fehlerfreien SharePoint Portals](/sharepoint/portal-health)

[Optimieren der Leistung von SharePoint Online](tune-sharepoint-online-performance.md)

[Optimieren der Leistung von Office 365](tune-microsoft-365-performance.md)

[SharePoint Online-Beschränkungen](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Leistung in der modernen SharePoint-Oberfläche](/sharepoint/modern-experience-performance)

[Leitfaden zur Leistung für SharePoint Online-Portale](/sharepoint/dev/solution-guidance/portal-performance)

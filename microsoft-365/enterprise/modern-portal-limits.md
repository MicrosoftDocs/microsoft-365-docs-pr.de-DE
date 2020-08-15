---
title: SharePoint Online Grenzwerte für moderne Portal Standorte
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
description: Hier finden Sie Informationen zu Leistungsempfehlungen für moderne Websites in SharePoint Online, beispielsweise zum Begrenzen von Aufrufen von SharePoint und externen Endpunkten.
ms.openlocfilehash: 2afca20183bef8c8f6dda9bdc35a44e5153ef07c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690738"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>SharePoint Online Grenzwerte für moderne Portal Standorte

Dieser Artikel enthält Leistungsempfehlungen für moderne Portalwebsites in SharePoint Online. Verwenden Sie die Richtlinien in diesem Artikel, um die Leistung moderner Portalwebsites zu optimieren und häufige Leistungsprobleme zu vermeiden.

## <a name="performance-considerations-for-modern-portal-sites"></a>Leistungsüberlegungen für moderne Portalwebsites

Aus Sicht der Leistungsoptimierung gibt es einige Merkmale, die moderne Portalwebsites einzigartig machen. Der Hauptunterschied zwischen der Zusammenarbeit und den Portalwebsites in SharePoint Online ist Maßstab. Portal Websites werden in der Regel erwartet, dass mehr Seitenaufrufe für eine größere Anzahl von Benutzern als Websites für die Zusammenarbeit bereitgestellt werden und wahrscheinlich mehr statische Inhalte und weniger bearbeitbare Ressourcen enthalten. Darüber hinaus unterscheidet sich die Architektur moderner Websites von klassischen Websites dadurch, dass die meisten Verarbeitungsschritte beim Rendern von Seiten und beim Ausführen von Code auf dem Client statt auf dem Server stattfinden.

Die Leistungsoptimierung für moderne Portalwebsites konzentriert sich in erster Linie auf einige allgemeine Ziele:

- Verringern der Gesamtgröße der Komponenten jeder Website Seite
- Abladen des Hostens allgemeiner statischer Dateien wie Bilder, Stylesheets und Skripts auf CDN
- Einschränken von Aufrufen von SharePoint und externen Endpunkten auf nur das, was erforderlich ist
- Vermeiden von doppelten Anforderungen für denselben Inhalt

Viele der Richtlinien in diesem Artikel konzentrieren sich auf die Minimierung und Optimierung von Aufrufen von SharePoint Online. Wenn Sie bei jedem Laden einer Seite wiederholte Anrufe tätigen, wirkt sich dies auf die Leistung der Benutzer aus, da die Informationen immer wieder aus dem Dienst abgerufen werden, auch wenn Sie nicht geändert wurde. Daher können Anforderungen an SharePoint entweder als Anrufe kategorisiert werden, die für alle Benutzer üblich sind, oder für Anrufe, die für jeden einzelnen Benutzer erforderlich sind. Ergebnisse aus diesen beiden Anruf Kategorien sollten zwischengespeichert werden, um die Benutzerfreundlichkeit zu optimieren.

>[!NOTE]
>Verwenden Sie das [Page Diagnostics für SharePoint-Tool](https://aka.ms/perftool) als Ausgangspunkt, um bestimmte Leistungs Metriken auf SharePoint Online Website Seiten zu analysieren.

## <a name="modern-portal-site-limits-and-recommendations"></a>Grenzwerte und Empfehlungen für moderne Portal Standorte

|**Grenze**|**Maximal empfohlener Wert**|**Notizen**|
|:-----|:-----|:-----|:-----|
|Seiten und Newselemente  <br/> |5.000 pro Website  <br/> |Es wird empfohlen, die Anzahl der Seiten und Newselemente auf einer modernen Portalwebsite auf unter 5.000 zu begrenzen.  <br/> |
|Webparts auf einer Seite  <br/> |20 pro Seite  <br/> |Es wird empfohlen, 20 oder weniger Gesamt Webparts pro Seite zu verwenden, einschließlich der vordefinierten Microsoft-Webparts und benutzerdefinierter Webparts. <br/> Weitere Informationen finden Sie unter [Optimieren der Leistung von Webparts in SharePoint Online modernen Website Seiten](modern-web-part-optimization.md).  <br/> |
|Dynamische Webparts auf einer Seite  <br/> |4 pro Seite  <br/> |Dynamische Webparts, die eine oder mehrere Abfragen an SharePoint vornehmen, um die neuesten Daten abzurufen, sollten auf 4 pro Seite limitiert sein. Das Webpart _News_ ist ein Beispiel für ein dynamisches WebPart. <br/> Weitere Informationen finden Sie unter [Optimieren der Leistung von Webparts in SharePoint Online modernen Website Seiten](modern-web-part-optimization.md).    <br/> |
|Sicherheitsgruppen  <br/> |20 pro Website  <br/> |Die Anzahl der Sicherheitsgruppen wirkt sich auf die Skalierung vieler Abfragen auf modernen Portalwebsites aus. Es wird empfohlen, die Anzahl der Sicherheitsgruppen so gering wie möglich zu halten, wobei maximal 20 pro Website zulässig sind.  <br/> |
|Elemente in der Websitenavigation  <br/> |100 pro Website  <br/> |Es wird empfohlen, weniger als 100 Elemente zur Websitenavigation hinzuzufügen und die Standard Navigationssteuerungen zu verwenden.  <br/> Weitere Informationen finden Sie unter [Optimieren der Seitengewichtung in SharePoint Online modernen Website Seiten](modern-page-weight-optimization.md). <br/> |
|Maximale Bildgröße  <br/> |300 KB pro Bild  <br/> |Es wird empfohlen, die Größe von Bildern auf 300KB oder kleiner zu begrenzen und mit einem CDN Bilder, Stylesheets und Skripts zu hosten. <br/>Weitere Informationen finden Sie unter [Optimieren von Bildern auf SharePoint Online modernen Website Seiten](modern-image-optimization.md) und [Verwenden des Office 365 Inhalts Zustellungs Netzwerks (CDN) mit SharePoint Online](use-microsoft-365-cdn-with-spo.md).  <br/> |
|Benutzer mit Bearbeitungsrechten  <br/> |200 Benutzer pro Website  <br/> |SharePoint-Portalwebsites sind für das Anzeigen und Verwenden von Inhalten optimiert. Bearbeitungsberechtigungen für ein Portal sollten auf eine eingeschränkte Benutzergruppe beschränkt sein, da Bearbeitungsberechtigungen zusätzliche Steuerelemente herunterladen und daher für diese Benutzer langsamer ausgeführt werden. Eine übermäßige Anzahl von Benutzern mit Bearbeitungsberechtigungen wirkt sich daher auf die Gesamterfahrung aus. <br/> |
|Iframes von Drittanbietern  <br/> |2 pro Seite  <br/> |iFrames sind unvorhersehbar langsam, da Sie eine separate externe Seite einschließlich aller dazugehörigen Inhalte wie JavaScript, CSS und Framework-Elemente laden. Wenn Sie iFrames verwenden müssen, begrenzen Sie deren Anzahl auf 2 oder weniger pro Seite.<br/> Weitere Informationen finden Sie unter [Optimieren von IFRAMEs auf SharePoint Online modernen und klassischen Veröffentlichungssite Seiten](modern-iframe-optimization.md). <br/> |
|Aufrufe an den UPA-Dienst  <br/> |1 pro Benutzer/Stunde  <br/> |Es wird empfohlen, für den UPA-Dienst (benutzerprofilanwendung) keine _pro Anforderungs_ Aufrufe zu tätigen. Die [Microsoft Graph-API](https://docs.microsoft.com/graph/call-api) und [PageContext](https://docs.microsoft.com/javascript/api/sp-page-context/pagecontext?view=sp-typescript-latest) können zum Abfragen von Benutzerinformationen verwendet werden.  <br/> Wenn ein UPA-Dienstaufruf erforderlich ist, führen Sie bei Bedarf einen einzelnen Aufruf durch, und speichern Sie die Informationen dann zur Wiederverwendung in derselben Sitzung zwischen. |
|Aufrufe des Taxonomie-Diensts  <br/> |5 pro Benutzer pro Stunde  <br/> |Es wird empfohlen, keine _pro Anforderungs_ Aufrufe an den taxonomiedienst vorzunehmen. Wenn taxonomiedienst-Aufrufe erforderlich sind, Zwischenspeichern Sie die Informationen zur Wiederverwendung in derselben Sitzung. <br/> Weitere Informationen finden Sie unter [optimize Page Calls in SharePoint Online modern and Classic Publishing Site Pages](modern-page-call-optimization.md). <br/> |

## <a name="related-topics"></a>Verwandte Themen

[Erstellen eines gesunden SharePoint-Portals](https://docs.microsoft.com/sharepoint/portal-health)

[Optimieren der Leistung von SharePoint Online](tune-sharepoint-online-performance.md)

[Optimieren der Leistung von Office 365](tune-microsoft-365-performance.md)

[SharePoint Online-Beschränkungen](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Leistung in der modernen SharePoint-Oberfläche](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Leitfaden zur Leistung für SharePoint Online-Portale](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-performance)

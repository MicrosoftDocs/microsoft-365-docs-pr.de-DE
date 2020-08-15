---
title: Planen des Rollout Plans für den Portal Start in SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
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
description: In diesem Artikel wird beschrieben, wie Sie den Start Ihres Portals in SharePoint Online planen und welche Schritte Sie für einen erfolgreichen Start ausführen können.
ms.openlocfilehash: e22fa4d9cbfed79841d844f111e3eb91a708512e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690867"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>Planen des Rollout Plans für den Portal Start in SharePoint Online

Bei einem Portal handelt es sich um eine SharePoint-Website in Ihrem Intranet mit einer großen Anzahl von Websitebenutzern, die Inhalte auf der Website nutzen. In großen Organisationen könnten mehrere dieser Portale vorhanden sein, beispielsweise ein Firmenportal und ein Personalportal. In der Regel erstellen und bearbeiten nur relativ wenige Personen die Portalwebsite und deren Inhalte. Die meisten Besucher des Portals können den Inhalt nur lesen und nutzen.

In diesem Artikel wird beschrieben, wie Sie die Bereitstellung und den Rolloutplan für SharePoint Online planen. Es bietet auch Ansätze, die befolgt werden, da herkömmliche Auslastungstests für SharePoint Online nicht zulässig sind. SharePoint Online ist ein clouddienst, und die Ladefunktionen, die Integrität und die Gesamtlastverteilung im Dienst werden von Microsoft verwaltet.

Um bei der Erstellung eines erfolgreichen Portals zu helfen, befolgten Sie die Grundprinzipien, Methoden und Empfehlungen, die im [erstellen, starten und Verwalten eines gesunden Portals](https://go.microsoft.com/fwlink/?linkid=2105838) erläutert werden. 

Der Bereitstellungsansatz ist unten hervorgehoben.

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>Übersicht über die Kapazitätsplanung in SharePoint Online
Um die Kapazität effizient zu nutzen und unerwartetes Wachstum zu bewältigen, gibt es in jeder Farm Automatisierung, die bestimmte Nutzungsszenarien verfolgt. Während das exakte Wachstum für einen beliebigen Mandanten in einer Farm unvorhersehbar ist, ist die aggregierte Summe von Anforderungen im Laufe der Zeit vorhersehbar. Durch die Ermittlung der Wachstumstrends in SharePoint Online können wir die zukünftige Expansion planen. Weitere Informationen zur [Kapazitätsplanung und zu Auslastungstests SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md).

Ein wichtiger Bestandteileines erfolgreichen Starts ist der unten aufgeführte "Wave"-oder "Phased-Rollout"-Ansatz. 

## <a name="can-i-load-test-sharepoint-online"></a>Kann ich Test SharePoint Online Laden?
SharePoint Online ist eine gemeinsam genutzte Umgebung mit mehreren Mandanten, die über mehrere Farmen hinweg ausgeglichen ist und die Skalierung laufend angepasst wird. Auslastungstests einer Umgebung wie SharePoint Online, deren Skalierungsänderungen nicht nur unerwartete Ergebnisse liefern, sondern auch nicht zulässig sind. 

Weitere Informationen:  [Kapazitätsplanung und Auslastungstests SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Optimieren von Seiten mit den empfohlenen Richtlinien
Seiten aus einer lokalen Bereitstellung sollten nicht einfach so verschoben werden, wie Sie auf SharePoint Online sind, ohne Sie anhand der empfohlenen Richtlinien für SharePoint Online zu überprüfen. Der beste Ansatz besteht darin, jede Startseite für jede Website oder jedes Portal in SharePoint immer zu optimieren, da auf diese Weise die meisten Benutzer in Ihrer Organisation als Ausgangspunkt für Ihre Website (en) zugreifen können.

Einige grundlegende Faktoren sollten berücksichtigt werden:
- Lokale Bereitstellungen können herkömmliche serverseitige Caches wie Objektcache, Ausgabecache und BLOB-Cache nutzen. Mit den Unterschieden in der Topologie in der Cloud sind diese Optionen nicht notwendigerweise verfügbar, da Sie durch die schieren Skalierungs Unterschiede weniger tragfähige Ansätze bieten.
- Alle Seiten/Features/Anpassungen, die für die Cloud-Nutzung verwendet werden, sollten für eine höhere Latenz sowie für die verteilte Speicherorte von Benutzern optimiert werden, sodass Benutzer in unterschiedlichen Bereichen oder Regionen eine konsistentere Oberfläche haben. Cloud bietet Optimierungen wie Inhalts Übermittlungs Netzwerke (CDN) zur Optimierung für eine verteilte Benutzerbasis sowie für moderne SharePoint, das letzte bekannte gut (LKG) wird von unseren out-of-the-Box (OOTB)-Webparts verwendet.

### <a name="what-to-do"></a>Was ist zu tun:
 - Verwenden Sie für alle Website Seiten in SharePoint Online das [Page Diagnostics-Tool](https://aka.ms/perftool), bei dem es sich um eine Chromium-Erweiterung handelt, die die Analyse und Bereitstellung von Anleitungen unterstützen wird. Dies kann von Websitebesitzern, Editoren, Administratoren und Entwicklern verwendet werden, da Sie als Ausgangspunkt für Analyse und Optimierung dienen.
 - Entwickler sollten außerdem Entwicklungstools wie F12-Browser Entwicklertool sowie STRG-F12 im Browser auf modernen Seiten verwenden. [Fiddler](https://www.telerik.com/download/fiddler) kann auch verwendet werden, um die Größen Gewichtung (Größe der Seite in Megabytes) der Seite und die Anzahl der Aufrufe und Elemente zu überprüfen, die sich auf die gesamte Seitenlast auswirken. 

Dieser Abschnitt war eine kurze Zusammenfassung für die Optimierung von Seiten.  Weitere Informationen finden Sie unter:  [Creating, Launching and maintain a healthy Portal](https://go.microsoft.com/fwlink/?linkid=2105838).

## <a name="follow-a-wave--phased-roll-out-approach"></a>Durchführen eines Wave/Phasen-Roll-out-Ansatzes
Der herkömmliche Big Bang-Ansatz für Website Starts ermöglicht nicht die Überprüfung, ob Anpassungen, externe Quellen, Dienste oder Prozesse im richtigen Maßstab getestet wurden. Dies bedeutet nicht, dass es Monate dauern wird, bis es gestartet wird, es wird jedoch mindestens einige Tage lang von der Größe Ihrer Organisation empfohlen. Im Anschluss an einen Wave-Rollout-Plan erhalten Sie daher die Möglichkeit, Probleme zu unterbrechen und zu beheben, bevor Sie mit der nächsten Phase fortfahren und somit die potenzielle Anzahl von Benutzern, die von Problemen betroffen sind, reduzieren. SharePoint as a Service skaliert ihre Kapazität basierend auf der Nutzung und der vorhergesagten Nutzung, und wenn Sie uns nicht über Ihren Start informieren müssen, sollten Sie die Richtlinien befolgen, um den Erfolg sicherzustellen.
  
Wie in der folgenden Abbildung gezeigt, ist die Anzahl der eingeladenen Benutzer häufig deutlich höher als die, die die Website tatsächlich verwenden. Dieses Bild zeigt eine Strategie zum Rollout einer Version. Mit dieser Methode können Sie erkennen, wie die SharePoint-Website verbessert werden kann, bevor Sie von den meisten Benutzern angezeigt wird.
  
![Diagramm mit eingeladenen und aktiven Benutzern](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
In der Pilotphase ist es gut, Feedback von Benutzern zu erhalten, denen die Organisation vertraut und weiß, dass Sie aktiviert wird. Auf diese Weise kann gemessen werden, wie das System verwendet wird, und wie es ausgeführt wird.
  
Sammeln Sie während der einzelnen Wellen Benutzer Feedback zu den Features und zur Leistung während jeder Bereitstellungsphase. Dies hat den Vorteil, dass das System langsam eingeführt wird und Verbesserungen vorgenommen werden, da das System mehr verwendet. Dadurch können wir auch auf die erhöhte Auslastung reagieren, da die Website für mehr und mehr Benutzer bereitgestellt wird und die Richtlinien für die Seiten Optimierung kombiniert werden, um den Benutzern eine positive Erfahrung zu ermöglichen.

### <a name="what-to-do"></a>Was ist zu tun:
- Entscheiden Sie sich für den Zeitpunkt der einzelnen Phasen und stellen Sie sicher, dass Sie eine Notfall-/Pausen Möglichkeit haben, falls Sie Anpassungen vornehmen müssen, bevor Sie fortfahren.
- Planen Sie Ihre erste Gruppe von Benutzern, die Sie aktivieren möchten, um sicherzustellen, dass Sie das Feedback erhalten, das Sie benötigen, um sich weiter zu bewegen. Dies bedeutet, dass, wenn möglich, eine aktive Gruppe von Benutzern ausgewählt wird, die zeitnah Feedback zur Verfügung stellt.
- Wenn Sie jede Welle planen, versuchen Sie, mit einer kleinen Benutzerbasis (weniger als 5000 Benutzer) zu beginnen, und erweitern Sie dann die Gruppengröße, während Sie mit jeder Welle fortfahren. Auf diese Weise wird ein gestaffelter Ansatz erstellt, und es können einfachere Pausen Möglichkeiten geboten werden.

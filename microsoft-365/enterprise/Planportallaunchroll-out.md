---
title: Planen des Rolloutplans ihres Portals in SharePoint Online
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
description: In diesem Artikel wird beschrieben, wie Sie den Start Ihres Portals in SharePoint Online planen können und welche Schritte für einen erfolgreichen Start erforderlich sind.
ms.openlocfilehash: 280aa76c41e7ef72d23b22877482a92d981fe29d
ms.sourcegitcommit: 69d28334e01ec757c794cf3f8b8c0d85713f975e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53424022"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>Planen des Rolloutplans ihres Portals in SharePoint Online

Ein Portal ist eine SharePoint Website in Ihrem Intranet mit vielen Websiteviewern, die Inhalte auf der Website nutzen. Große Organisationen könnten mehrere Portale haben. Beispielsweise ein Unternehmensportal und ein Hr-Portal. In der Regel erstellen und bearbeiten nur relativ wenige Personen die Portalwebsite und deren Inhalte. Die meisten Besucher des Portals können den Inhalt nur lesen und nutzen.

In diesem Artikel wird beschrieben, wie Sie Ihren Bereitstellungs- und Rolloutplan für SharePoint Online planen. Es bietet auch Ansätze, die Sie befolgen können, da herkömmliche Auslastungstests auf SharePoint Online nicht zulässig sind. SharePoint Online ist ein Clouddienst, und die Ladefunktionen, der Status und das gesamte Lastenausgleich im Dienst werden von Microsoft verwaltet.

Um bei der Erstellung eines erfolgreichen Portals zu helfen, befolgen Sie die grundlegenden Prinzipien, Methoden und Empfehlungen, die im [Erstellen, Starten und Verwalten eines fehlerfreien Portals](/sharepoint/portal-health) beschrieben sind. 

Der Bereitstellungsansatz wird unten hervorgehoben.

## <a name="portal-launch-scheduler"></a>Portal Launch Scheduler

Verwenden Sie den Portalstartplaner, um Ihr Portal für Benutzer in Ihrer Organisation in geplanten Phasen freizugeben. Weitere Informationen: 

![Kalendersymbol](https://docs.microsoft.com/Office/media/icons/calendar.png "Portalstartplaner")  [Portal Launch Scheduler](https://docs.microsoft.com/microsoft-365/enterprise/portallaunchscheduler)



## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>Übersicht über die Kapazitätsplanung in SharePoint Online
Um die Kapazität effizient zu nutzen und unerwartetes Wachstum zu bewältigen, verfügen wir in jeder Farm über eine Automatisierung, die bestimmte Nutzungsszenarien verfolgt. Während das genaue Wachstum für jeden Mandanten in einer Farm unvorhersehbar ist, ist die aggregierte Summe der Anforderungen im Laufe der Zeit vorhersehbar. Indem wir die Wachstumstrends in SharePoint Online identifizieren, können wir eine zukünftige Erweiterung planen. Weitere Informationen zum [Kapazitätsplanungs- und Auslastungstest SharePoint Online.](capacity-planning-and-load-testing-sharepoint-online.md)

Ein wichtiger Bestandteil eines erfolgreichen Starts ist der "Wave"- oder "phased rollout"-Ansatz, der weiter unten beschrieben wird. 

## <a name="can-i-load-test-sharepoint-online"></a>Kann ich Test SharePoint Online laden?
SharePoint Online ist eine freigegebene mehrinstanzenfähige Umgebung, die über mehrere Farmen hinweg ausgeglichen wird und kontinuierlich angepasst wird. Laden Sie das Testen einer Umgebung wie SharePoint Online, deren Skalierungsänderungen nicht nur unerwartete Ergebnisse liefern, sondern auch nicht zulässig sind. 

Weitere Informationen: [Kapazitätsplanung und Auslastungstests SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Optimieren von Seiten durch Befolgen empfohlener Richtlinien
Seiten aus einer lokalen Bereitstellung sollten nicht einfach in SharePoint Online verschoben werden, ohne sie anhand der empfohlenen Richtlinien für SharePoint Online zu überprüfen. Der beste Ansatz besteht darin, jede Startseite für jede Website oder jedes Portal in SharePoint zu optimieren, da hier die meisten Benutzer in Ihrer Organisation als Ausgangspunkt für Ihre Website(n) zugreifen.

Es sollten einige grundlegende Faktoren berücksichtigt werden:
- Lokale Bereitstellungen können herkömmliche serverseitige Caches wie Objektcache, Ausgabecache und Blobcache verwenden. Mit den Topologieunterschieden in der Cloud sind diese Optionen nicht notwendigerweise verfügbar, da die reinen Skalierungsunterschiede sie zu weniger geeigneten Ansätzen machen.
- Alle Seiten/Features/Anpassungen, die für die Cloudnutzung verwendet werden, sollten für eine höhere Latenz und die verteilten Speicherorte von Benutzern optimiert werden, damit Benutzer in verschiedenen Bereichen oder Regionen eine konsistentere Benutzererfahrung haben. Cloud bietet Optimierungen wie Content Delivery Networks (CDN), um für eine verteilte Benutzerbasis zu optimieren, und für moderne SharePoint wird das letzte bekannte gute (Known Good, LKG) von unseren Out-of-the-Box (OOTB)-Webparts genutzt.

### <a name="what-to-do"></a>Was ist zu tun:
 - Verwenden Sie für alle Websiteseiten in SharePoint Online das [Tool "Seitendiagnose",](./page-diagnostics-for-spo.md)eine Chromium Erweiterung, die bei der Analyse und Bereitstellung von Anleitungen hilft. Dies kann von Websitebesitzern, Editoren, Administratoren und Entwicklern verwendet werden, da es als Ausgangspunkt für Analyse und Optimierung konzipiert ist.
 - Entwickler sollten auch Entwicklungstools wie das F12-Browserentwicklertool und STRG-F12 im Browser auf modernen Seiten verwenden. [Fiddler](https://www.telerik.com/download/fiddler) kann auch verwendet werden, um die Größengewichtung (wie groß die Seite in Megabyte ist) der Seite und die Anzahl der Aufrufe und Elemente zu überprüfen, die sich auf die gesamte Seitenlast auswirken. 

Dieser Abschnitt war eine kurze Zusammenfassung zum Optimieren von Seiten.  Weitere Informationen finden Sie unter: [Erstellen, Starten und Verwalten eines fehlerfreien Portals.](/sharepoint/portal-health)

## <a name="follow-a-wave--phased-roll-out-approach"></a>Folgen eines Wave/Phased-Rollout-Ansatzes
Der herkömmliche Big-Bang-Ansatz für Websitestarts lässt keine Überprüfung zu, ob Anpassungen, externe Quellen, Dienste oder Prozesse im richtigen Umfang getestet wurden. Dieser Ansatz bedeutet nicht, dass es Monate dauert, bis er gestartet wird, aber es wird empfohlen, mindestens mehrere Tage lang zu starten, abhängig von der Größe Ihrer Organisation. Nach einem Wave-Rollout-Plan haben Sie daher die Möglichkeit, Probleme zu unterbrechen und zu beheben, bevor Sie mit der nächsten Phase fortfahren, und verringert daher die potenzielle Anzahl der Benutzer, die von Problemen betroffen sind. SharePoint as a Service Ihre Kapazität basierend auf Nutzung und prognostizierter Nutzung skaliert und wir nicht benötigen, dass Sie uns über Ihren Start benachrichtigen, sollten Sie die Richtlinien befolgen, um den Erfolg sicherzustellen.
  
Wie in der folgenden Abbildung gezeigt, ist die Anzahl der eingeladenen Benutzer häufig wesentlich höher als die der Benutzer, die die Website tatsächlich verwenden. Diese Abbildung zeigt eine Strategie zum Rollout einer Version. Diese Methode hilft bei der Identifizierung von Möglichkeiten, die SharePoint Website zu verbessern, bevor sie den meisten Benutzern angezeigt wird.
  
![Graph mit eingeladenen und aktiven Benutzern](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
In der Pilotphase empfiehlt es sich, Feedback von Benutzern zu erhalten, denen die Organisation vertraut und weiß, dass sie eingebunden werden. Auf diese Weise kann gemessen werden, wie das System verwendet wird und wie es funktioniert.
  
Sammeln Sie während jeder Phase der Bereitstellung Feedback der Benutzer zu den Features und der Leistung. Das Sammeln von Feedback hat den Vorteil, dass das System langsam eingeführt wird und Verbesserungen vorgenommen werden, wenn das System mehr genutzt wird. Dies ermöglicht uns auch, auf die erhöhte Last zu reagieren, wenn die Website für mehr Benutzer bereitgestellt wird, und in Kombination mit den Richtlinien für die Seitenoptimierung wird eine positive Erfahrung für Ihre Benutzer sichergestellt.

### <a name="what-to-do"></a>Was ist zu tun:
- Entscheiden Sie sich für den Zeitpunkt der einzelnen Phasen, und stellen Sie sicher, dass Sie über eine Notfall-/Pausenmöglichkeit verfügen, falls Sie Anpassungen vornehmen müssen, bevor Sie fortfahren
- Planen Sie Ihre erste Gruppe von Benutzern, die Sie aktivieren möchten, um sicherzustellen, dass Sie das Feedback erhalten, das Sie benötigen, um vorwärts zu gehen.  Wählen Sie nach Möglichkeit eine aktive Gruppe von Benutzern aus, die zeitnah Feedback geben wird.
- Versuchen Sie bei der Planung jeder Welle, mit einer kleinen Benutzerbasis (weniger als 5000 Benutzer) zu beginnen. Erhöhen Sie die Gruppengrößen, während Sie mit jeder Welle fortfahren. Durch die Erstellung eines gestaffelten Ansatzes ermöglicht es bei Bedarf einfachere Pausenmöglichkeiten.
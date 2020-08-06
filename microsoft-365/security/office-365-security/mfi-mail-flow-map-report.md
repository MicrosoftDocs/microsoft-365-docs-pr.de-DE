---
title: Nachrichtenfluss Zuordnung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie die e-Mail-Fluss Zuordnung im Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um zu visualisieren und nachzuverfolgen, wie e-Mail-Nachrichten zu und von Ihrer Organisation über Connectors und ohne Connectors verwendet werden.
ms.openlocfilehash: 2996227de3e0141635522ada4e41f2e8e65e9040
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577696"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Nachrichtenfluss Zuordnung im Security & Compliance Center

Die **e-Mail-Fluss Übersicht** im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im Security & Compliance Center gibt Einblicke in die Art und Weise, wie e-Mail-Nachrichten durch Ihre Organisation fließt. Sie können diese Informationen verwenden, um Muster zu erfahren, Anomalien zu identifizieren und Probleme zu beheben, wenn Sie auftreten.

![Nachrichtenfluss-Zuordnungs Widget im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-mail-flow-map-widget.png)

Standardmäßig zeigt das Widget das Nachrichtenfluss Muster aus dem vorherigen Tag in einem Diagramm an, das als *Sankey* -Diagramm bezeichnet wird. Sie können den nach-links-Pfeil nach links ![ ](../../media/scc-left-arrow.png) und nach-rechts-Pfeil verwenden ![ ](../../media/scc-right-arrow.png) , um Informationen aus unterschiedlichen Tagen anzuzeigen. Jede andere Farbe stellt die Nachrichtenübermittlung über einen anderen eingehenden oder ausgehenden Connector (oder ohne Verwendung von Connectors) dar. Wenn Sie mit dem Mauszeiger auf eine bestimmte Farbe zeigen, wird die Anzahl der Nachrichten für diese Art von Connector angezeigt.

## <a name="report-view-for-the-mail-flow-map"></a>Berichtsansicht für die Nachrichtenfluss Zuordnung

Durch Klicken auf das Widget **"Nachrichtenfluss-Zuordnung** " gelangen Sie zum Bericht **"Nachrichtenfluss Karte** ".

Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:

- **Daten anzeigen für: Overview**: Dies ist im Wesentlichen eine größere Ansicht des Widgets. Wenn Sie mit dem Mauszeiger auf eine bestimmte Farbe zeigen, wird die Anzahl der Nachrichten für diese Art von Connector angezeigt.

  ![Übersichtsansicht im Bericht "Nachrichtenfluss Übersicht"](../../media/mfi-mail-flow-map-report-overview.png)

- **Daten anzeigen für: Detail: in**dieser Ansicht werden Details zu den Connectors und Zieldomänen angezeigt. Die obersten Absender-und Empfängerdomänen werden aufgelistet, und die restlichen werden in **andere**eingefügt. Wenn Sie mit dem Mauszeiger auf eine bestimmte Farbe und einen bestimmten Abschnitt zeigen, wird die Anzahl der Nachrichten angezeigt.

  ![Detail Ansicht im Nachrichtenfluss-Zuordnungsbericht](../../media/mfi-mail-flow-map-report-detail.png)

Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.

Klicken Sie auf **Anforderungs Download**, um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere Empfänger zu senden.

Zugehörige Einblicke werden unterhalb der Nachrichtenfluss Zuordnung angezeigt, wenn Sie verfügbar sind (beispielsweise die [Fix possible Mail Loop Insight](mfi-mail-loop-insight.md)).

## <a name="details-table-view-for-the-mail-flow-map"></a>Tabellenansicht "Details" für die Nachrichtenfluss Zuordnung

Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:

- **Date**
- **Kategorie**
- **Connector/Drittanbieter-Dienstanbieter**
- **Absender/Empfängerdomäne**
- **Nachrichtenanzahl**

Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.

Wenn Sie eine Zeile auswählen, werden ähnliche Details in einem Flyout angezeigt:

![Details-Flyout aus der Detailtabelle der Nachrichtenfluss Zuordnung](../../media/mfi-mail-flow-map-view-details-table-details.png)

Klicken Sie auf **Anforderungs Download**, um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere Empfänger zu senden.

Klicken Sie auf **Bericht anzeigen**, um zur Ansicht Berichte zurückzukehren.

## <a name="see-also"></a>Siehe auch

Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).

---
title: Zuordnung der Nachrichtenübermittlung
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren erfahren, wie Sie die Nachrichtenflusszuordnung im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um zu visualisieren und nachzuverfolgen, wie E-Mails über Connectors und ohne Connectors zu und von ihrer Organisation fließen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206961"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Nachrichtenflusszuordnung im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Die **Nachrichtenflusskarte** im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) gibt Einblick in den E-Mail-Fluss in Ihrer Organisation. [](mail-flow-insights-v2.md) Sie können diese Informationen verwenden, um Muster zu erlernen, Anomalien zu identifizieren und Probleme bei deren Auftreten zu beheben.

![Nachrichtenflusszuordnungs-Widget im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-mail-flow-map-widget.png)

Standardmäßig zeigt das Widget das Nachrichtenflussmuster vom Vortag in einem Diagramm an, das als *Sankey-Diagramm bezeichnet* wird. Sie können den Pfeil nach links und nach rechts zum Anzeigen von Informationen aus ![ ](../../media/scc-left-arrow.png) verschiedenen Tagen ![ ](../../media/scc-right-arrow.png) verwenden. Jede unterschiedliche Farbe stellt den Nachrichtenfluss über einen anderen ein- oder ausgehenden Connector (oder ohne Verwendung von Connectors) dar. Wenn Sie den Mauszeiger auf eine bestimmte Farbe zeigen, wird die Anzahl der Nachrichten für diesen Connectortyp angezeigt.

## <a name="report-view-for-the-mail-flow-map"></a>Berichtsansicht für die Nachrichtenflusskarte

Wenn Sie auf das **Widget "Nachrichtenflusszuordnung"** klicken, werden Sie zum **Bericht "Nachrichtenflusszuordnung"** angezeigt.

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Daten anzeigen für: Übersicht**: Dies ist im Wesentlichen eine größere Ansicht des Widgets. Wenn Sie den Mauszeiger auf eine bestimmte Farbe zeigen, wird die Anzahl der Nachrichten für diesen Connectortyp angezeigt.

  ![Übersichtsansicht im Bericht "Nachrichtenflusszuordnung"](../../media/mfi-mail-flow-map-report-overview.png)

- **Daten anzeigen für: Detail**: Diese Ansicht zeigt Details zu den Connectors und Zieldomänen. Die Top-Absender- und Empfängerdomänen werden aufgelistet, und der Rest wird in **Andere angegeben.** Wenn Sie auf eine bestimmte Farbe und einen bestimmten Abschnitt zeigen, wird die Anzahl der Nachrichten angezeigt.

  ![Detailansicht im Bericht "Nachrichtenflusszuordnung"](../../media/mfi-mail-flow-map-report-detail.png)

Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Klicken Sie auf Herunterladen anfordern, um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere **Empfänger zu senden.**

Verwandte Einblicke werden unterhalb der Nachrichtenflusskarte angezeigt, wenn sie verfügbar sind (z. B. die Möglichkeit einer E-Mail-Schleife [beheben).](mfi-mail-loop-insight.md)

## <a name="details-table-view-for-the-mail-flow-map"></a>Detailtabelle für die Nachrichtenflusszuordnung

Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:

- **Date**
- **Kategorie**
- **Connector/Drittanbieter**
- **Absender-Empfänger-Domäne**
- **Anzahl der Nachrichten**

Wenn Sie in einer **Detailtabelle** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Wenn Sie eine Zeile auswählen, werden ähnliche Details in einem Flyout angezeigt:

![Details flyout aus der Detailtabelle in der Nachrichtenflusskarte](../../media/mfi-mail-flow-map-view-details-table-details.png)

Klicken Sie auf Herunterladen anfordern, um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere **Empfänger zu senden.**

Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).

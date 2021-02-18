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
description: Administratoren können erfahren, wie Sie die Nachrichtenflusszuordnung im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um zu visualisieren und nachzuverfolgen, wie E-Mails über Connectors und ohne Connectors zu und von ihrer Organisation fließen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f507f7f01999492d17e168a2a56da906bfcb52d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290585"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Nachrichtenflusszuordnung im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Die **Nachrichtenflusszuordnung** im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) bietet Einblicke in den E-Mail-Fluss in Ihrer Organisation. [](mail-flow-insights-v2.md) Sie können diese Informationen verwenden, um Muster zu erlernen, Anomalien zu identifizieren und Probleme zu beheben, während sie auftreten.

![Widget für die Nachrichtenflusszuordnung im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-mail-flow-map-widget.png)

Standardmäßig zeigt das Widget das Nachrichtenflussmuster vom vorigen Tag in einem Diagramm an, das als *"Sankey"-Diagramm bezeichnet* wird. Sie können den Nach-links-Pfeil und den Pfeil nach rechts verwenden, um Informationen aus ![ ](../../media/scc-left-arrow.png) verschiedenen Tagen ![ ](../../media/scc-right-arrow.png) anzeigen. Jede unterschiedliche Farbe stellt den Nachrichtenfluss über einen anderen eingehenden oder ausgehenden Connector (oder ohne Verwendung von Connectors) dar. Wenn Sie mit der Maus auf eine bestimmte Farbe zeigen, wird die Anzahl der Nachrichten für diesen Connectortyp angezeigt.

## <a name="report-view-for-the-mail-flow-map"></a>Berichtsansicht für die Nachrichtenflusszuordnung

Wenn Sie auf das **Widget für die Nachrichtenflusszuordnung** klicken, werden Sie zum **Bericht "Nachrichtenflusszuordnung" geklickt.**

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Anzeigen von Daten für: Übersicht:** Dies ist im Wesentlichen eine größere Ansicht des Widgets. Wenn Sie mit der Maus auf eine bestimmte Farbe zeigen, wird die Anzahl der Meldungen für diesen Connectortyp angezeigt.

  ![Übersichtsansicht im Bericht "Nachrichtenflusszuordnung"](../../media/mfi-mail-flow-map-report-overview.png)

- **Daten anzeigen für: Detail:** Diese Ansicht zeigt Details zu den Connectors und Zieldomänen. Die am besten verwendeten Absender- und Empfängerdomänen werden aufgelistet, und der Rest wird in **"Andere" angegeben.** Wenn Sie mit der Maus auf eine bestimmte Farbe und einen bestimmten Abschnitt zeigen, wird die Anzahl der Meldungen angezeigt.

  ![Detailansicht im Bericht "Nachrichtenflusszuordnung"](../../media/mfi-mail-flow-map-report-detail.png)

Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Klicken Sie auf "Herunterladen anfordern", um den Bericht für einen bestimmten Datumsbereich per E-Mail an einen oder mehrere Empfänger **zu senden.**

Verwandte Einblicke werden unter der Nachrichtenflusszuordnung angezeigt, wenn sie verfügbar sind (z. B. der Einblick in die mögliche E-Mail-Schleife [korrigieren).](mfi-mail-loop-insight.md)

## <a name="details-table-view-for-the-mail-flow-map"></a>Detailtabelle für die Nachrichtenflusszuordnung

Wenn Sie in einer **Berichtsansicht auf "Details anzeigen"** klicken, werden die folgenden Informationen angezeigt:

- **Date**
- **Kategorie**
- **Connector/Drittanbieter**
- **Absender-/Empfängerdomäne**
- **Anzahl der Nachrichten**

Wenn Sie in einer **Detailtabelle auf Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Wenn Sie eine Zeile auswählen, werden ähnliche Details in einem Flyout angezeigt:

![Detailf flyout aus der Detailtabelle in der Nachrichtenflusszuordnung](../../media/mfi-mail-flow-map-view-details-table-details.png)

Klicken Sie auf "Herunterladen anfordern", um den Bericht für einen bestimmten Datumsbereich per E-Mail an einen oder mehrere Empfänger **zu senden.**

Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)

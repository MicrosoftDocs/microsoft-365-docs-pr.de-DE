---
title: Nicht akzeptierter Domänenbericht im Nachrichtenflussdashboard
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
description: Administratoren erfahren, wie Sie den Nicht akzeptierten Domänenbericht im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um Nachrichten aus Ihrer lokalen Organisation zu überwachen, in der die Domäne des Absenders nicht in Microsoft 365 konfiguriert ist.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fb33feb56bf2b52731c03273ce0c6444c333f348
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206334"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Nicht akzeptierter Domänenbericht im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Der Bericht Nicht akzeptierter [](mail-flow-insights-v2.md) Domänen im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) zeigt Informationen zu Nachrichten aus Ihrer lokalen **E-Mail-Organisation** an, in denen die Domäne des Absenders nicht als akzeptierte Domäne in Ihrer Microsoft 365-Organisation konfiguriert ist.

Microsoft 365 kann diese Nachrichten drosseln, wenn wir Daten zum Nachweis haben, dass die Absicht dieser Nachrichten bösartig ist. Daher ist es wichtig, dass Sie verstehen, was geschieht, und das Problem beheben.

![Nicht akzeptiertes Domänen-Widget im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Berichtsansicht für den Nicht akzeptierten Domänenbericht

Wenn Sie im Widget Nicht **akzeptierte** Domänen auf das Diagramm klicken, werden Sie zum **Bericht Nicht akzeptierter Domänen** angezeigt.

Standardmäßig wird die Aktivität für alle betroffenen Connectors angezeigt. Wenn Sie auf **Daten anzeigen für klicken,** können Sie in der Dropdownliste einen bestimmten Connector auswählen.

Wenn Sie auf einen Datenpunkt (Tag) im Diagramm zeigen, wird die Gesamtanzahl der Nachrichten für den Connector angezeigt.

![Berichtsansicht im Nicht akzeptierten Domänenbericht](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Detailtabelle für den Nicht akzeptierten Domänenbericht

Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:

- **Date**
- **Name des eingehenden Connectors**
- **Absenderdomäne**
- **Anzahl der Nachrichten**
- **Beispielnachrichten:** Die Nachrichten-IDs eines Beispiels betroffener Nachrichten.

Wenn Sie in einer **Detailtabelle** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Klicken Sie auf Herunterladen anfordern, um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere **Empfänger zu senden.**

Wenn Sie eine Zeile in der Tabelle auswählen, wird ein Flyout mit den folgenden Informationen angezeigt:

- **Date**
- **Name des eingehenden Connectors**
- **Absenderdomäne**
- **Anzahl der Nachrichten**
- **Beispielnachrichten:** Sie können auf **Beispielnachrichten anzeigen klicken,** um die Ergebnisse der Nachrichtenverfolgung für ein Beispiel der betroffenen Nachrichten zu sehen. [](message-trace-scc.md)

![Details flyout nach dem Auswählen einer Zeile in der Tabellenansicht Details im Nicht akzeptierten Domänenbericht](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**

## <a name="related-topics"></a>Verwandte Themen

Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).

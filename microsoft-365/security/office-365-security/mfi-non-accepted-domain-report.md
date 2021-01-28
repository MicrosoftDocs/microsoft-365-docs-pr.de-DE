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
description: Administratoren können erfahren, wie Sie den Bericht über nicht akzeptierte Domänen im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um Nachrichten aus Ihrer lokalen Organisation zu überwachen, in denen die Domäne des Absenders nicht in Microsoft 365 konfiguriert ist.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 401d566158ca3f730af94fab60c471484e244a16
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029846"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Nicht akzeptierter Domänenbericht im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Der Bericht "Nicht akzeptierte Domäne" im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) zeigt Informationen zu Nachrichten von Ihrer lokalen E-Mail-Organisation an, in denen die Domäne des Absenders nicht als akzeptierte Domäne in Ihrer Microsoft 365-Organisation konfiguriert ist.  [](mail-flow-insights-v2.md)

Microsoft 365 drosselt diese Nachrichten möglicherweise, wenn wir Daten haben, um nachzuweisen, dass die Absicht dieser Nachrichten böswillig ist. Daher ist es wichtig, dass Sie verstehen, was geschieht, und das Problem zu beheben.

![Nicht akzeptiertes Domänen-Widget im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Berichtsansicht für den Bericht über nicht akzeptierte Domänen

Wenn Sie im Widget "Nicht **akzeptierte** Domäne" auf das Diagramm klicken, werden Sie zum Bericht **"Nicht akzeptierte Domäne" geklickt.**

Standardmäßig wird die Aktivität für alle betroffenen Connectors angezeigt. Wenn Sie auf **"Daten anzeigen" klicken,** können Sie in der Dropdownliste einen bestimmten Connector auswählen.

Wenn Sie mit der Maus auf einen Datenpunkt (Tag) im Diagramm zeigen, wird die Gesamtanzahl der Nachrichten für den Connector angezeigt.

![Berichtsansicht im Bericht "Nicht akzeptierte Domäne"](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Detailtabelle für den Bericht "Nicht akzeptierte Domäne"

Wenn Sie in einer **Berichtsansicht auf "Details anzeigen"** klicken, werden die folgenden Informationen angezeigt:

- **Date**
- **Name des eingehenden Connectors**
- **Absenderdomäne**
- **Anzahl der Nachrichten**
- **Beispielmeldungen:** Die Nachrichten-IDs eines Beispiels betroffener Nachrichten.

Wenn Sie in einer **Detailtabelle auf Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Klicken Sie auf "Herunterladen anfordern", um den Bericht für einen bestimmten Datumsbereich per E-Mail an einen oder mehrere Empfänger **zu senden.**

Wenn Sie eine Zeile in der Tabelle auswählen, wird ein Flyout mit den folgenden Informationen angezeigt:

- **Date**
- **Name des eingehenden Connectors**
- **Absenderdomäne**
- **Anzahl der Nachrichten**
- **Beispielmeldungen:** Sie können auf "Beispielmeldungen **anzeigen"** klicken, um die Ergebnisse der Nachrichtenverfolgung für ein Beispiel der betroffenen Nachrichten zu sehen. [](message-trace-scc.md)

![Details flyout after selecting a row in Details table view in the Non-accepted domain report](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**

## <a name="related-topics"></a>Verwandte Themen

Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)

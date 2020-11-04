---
title: Bericht "nicht akzeptierte Domäne" im Nachrichtenfluss-Dashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie den Bericht nicht akzeptierte Domäne im Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um Nachrichten von Ihrer lokalen Organisation zu überwachen, in denen die Domäne des Absenders in Microsoft 365 nicht konfiguriert ist.
ms.openlocfilehash: 06acacb79c826cb465b3fd28086a7df9d64eabdc
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877717"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Bericht über nicht akzeptierte Domänen im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Der Bericht **nicht akzeptierte Domäne** im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im [Security & Compliance Center](https://protection.office.com) zeigt Informationen zu Nachrichten von Ihrer lokalen e-Mail-Organisation an, in der die Domäne des Absenders nicht als akzeptierte Domäne in Ihrer Microsoft 365-Organisation konfiguriert ist.

Microsoft 365 kann diese Nachrichten Drosseln, wenn wir Daten haben, um zu beweisen, dass die Absicht dieser Nachrichten bösartig ist. Daher ist es wichtig, dass Sie verstehen, was passiert, und das Problem zu beheben.

![Widget "nicht akzeptierte Domäne" im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Berichtsansicht für den Bericht "nicht akzeptierte Domäne"

Durch Klicken auf das Diagramm im Widget " **nicht akzeptierte Domäne** " gelangen Sie zum Bericht " **nicht akzeptierte Domäne** ".

Standardmäßig wird die Aktivität für alle betroffenen Konnektoren angezeigt. Wenn Sie auf **Daten anzeigen für** klicken, können Sie einen bestimmten Konnektor aus der Dropdownliste auswählen.

Wenn Sie mit dem Mauszeiger auf einen Datenpunkt (Tag) im Diagramm zeigen, wird die Gesamtzahl der Nachrichten für den Connector angezeigt.

![Berichtsansicht im Bericht "nicht akzeptierte Domäne"](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Detailtabellen Ansicht für den Bericht "nicht akzeptierte Domäne"

Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:

- **Date**
- **Name des eingehenden Connectors**
- **Absenderdomäne**
- **Nachrichtenanzahl**
- **Beispiel Meldungen** : die Nachrichten-IDs einer Stichprobe betroffener Nachrichten.

Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum** angeben.

Klicken Sie auf **Anforderungs Download** , um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere Empfänger zu senden.

Wenn Sie eine Zeile in der Tabelle auswählen, wird ein Flyout mit den folgenden Informationen angezeigt:

- **Date**
- **Name des eingehenden Connectors**
- **Absenderdomäne**
- **Nachrichtenanzahl**
- **Beispiel Meldungen** : Sie können auf **Beispiel Meldungen anzeigen** klicken, um die Ergebnisse der [Nachrichtenablaufverfolgung](message-trace-scc.md) für ein Beispiel der betroffenen Nachrichten anzuzeigen.

![Detail Flyout nach dem Auswählen einer Zeile in der Detailtabellen Ansicht im Bericht "nicht akzeptierte Domäne"](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Klicken Sie auf **Bericht anzeigen** , um zur Ansicht Berichte zurückzukehren.

## <a name="related-topics"></a>Verwandte Themen

Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).

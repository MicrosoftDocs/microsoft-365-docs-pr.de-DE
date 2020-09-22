---
title: Unzustellbarkeitsbericht im Nachrichtenübermittlungs-Dashboard
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie den Bericht über Unzustellbarkeits Informationen im Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um die am häufigsten auftretenden Fehlercodes in Unzustellbarkeitsberichten (auch als Unzustellbarkeitsberichte oder Unzustellbarkeitsnachrichten bezeichnet) von Absendern in Ihrer Organisation zu überwachen.
ms.openlocfilehash: bc530cce54b3d4fd9f414920a8fb58f4322f6b5c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195964"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Unzustellbarkeitsbericht im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Der **Unzustellbarkeitsbericht** im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im [Security & Compliance Center](https://protection.office.com) zeigt die am häufigsten auftretenden Fehlercodes in Unzustellbarkeitsberichten (auch bekannt als Unzustellbarkeitsberichte oder Bounce-Nachrichten) für Benutzer in Ihrer Organisation. Dieser Bericht zeigt die Details von Unzustellbarkeitsberichten an, damit Sie Probleme mit der e-Mail-Zustellung beheben können.

![Widget "nicht Zustellungsbericht" im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>Berichtsansicht für Unzustellbarkeitsbericht

Wenn Sie auf das Widget **nicht Zustellungsbericht** klicken, gelangen Sie zum **Unzustellbarkeitsbericht**.

Standardmäßig wird die Aktivität für alle Fehlercodes angezeigt. Wenn Sie auf **Daten anzeigen für**klicken, können Sie einen bestimmten Fehlercode aus der Dropdownliste auswählen.

Wenn Sie mit dem Mauszeiger auf eine bestimmte Farbe (Fehlercode) an einem bestimmten Tag im Diagramm zeigen, wird die Gesamtzahl der Nachrichten für den Fehler angezeigt.

![Berichtsansicht im Bericht "nicht akzeptierte Domäne"](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>Detailtabellen Ansicht für den Unzustellbarkeitsbericht

Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:

- **Date**
- **Code für Unzustellbarkeitsberichte**
- **Count**
- **Beispiel Meldungen**: die Nachrichten-IDs einer Stichprobe betroffener Nachrichten.

Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.

Klicken Sie auf **Anforderungs Download**, um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere Empfänger zu senden.

Wenn Sie eine Zeile in der Tabelle auswählen, wird ein Flyout mit den folgenden Informationen angezeigt:

- **Date**
- **Unzustellbarkeitsbericht Code**: Sie können auf den Link klicken, um weitere Informationen zu den Ursachen und Lösungen für den spezifischen Fehlercode zu erhalten.
- **Count**
- **Beispiel Meldungen**: Sie können auf **Beispiel Meldungen anzeigen** klicken, um die Ergebnisse der [Nachrichtenablaufverfolgung](message-trace-scc.md) für ein Beispiel der betroffenen Nachrichten anzuzeigen.

![Detail Flyout nach dem Auswählen einer Zeile in der Detailtabellen Ansicht im Unzustellbarkeitsbericht](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>Verwandte Themen

Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).

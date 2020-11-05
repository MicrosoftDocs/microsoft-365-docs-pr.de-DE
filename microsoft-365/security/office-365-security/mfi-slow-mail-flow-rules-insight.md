---
title: Beheben des Einblicks in langsame Nachrichtenflussregeln
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie in Ihrer Organisation die Informationen zum Fix Slow Mail Flow Rules Insight im Security & Compliance Center verwenden, um ineffiziente oder fehlerhafte Nachrichtenfluss Regeln (auch bekannt als Transportregeln) zu identifizieren und zu beheben.
ms.openlocfilehash: f51c5a577fc6d9c52e35a5217cae4ae94c546c9d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920548"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Beheben langsamer Nachrichtenfluss Regeln Einblicke im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Ineffiziente Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) können zu Verzögerungen bei der Nachrichtenübermittlung für Ihre Organisation führen. Diese Einblicke meldet Nachrichtenfluss Regeln, die sich auf den e-Mail-Fluss Ihrer Organisation auswirken. Beispiele für diese Regeltypen sind:

- Die Bedingungen, die verwendet **werden, sind Mitglied von** für große Gruppen.
- Bedingungen, die einen komplexen Regular Expression (Regex)-Mustervergleich verwenden.
- Bedingungen, die die Inhaltsüberprüfung in Anlagen verwenden.

Die **Fix langsamen Nachrichtenfluss Regeln** Einblicke in den Bereich **Recommended for you** des [Nachrichtenfluss-Dashboards](mail-flow-insights-v2.md) im [Security & Compliance Center](https://protection.office.com) benachrichtigt Sie, wenn eine e-Mail-Fluss Regel zu lange dauert, bis Sie abgeschlossen ist.

Diese Einblicke wird erst nach dem Erkennen der Bedingung angezeigt (wenn Sie keine e-Mail-Schleifen haben, wird die Einblicke nicht angezeigt).

Sie können diese Benachrichtigung verwenden, um e-Mail-Flussregeln zu identifizieren und zu optimieren, um Verzögerungen bei der Nachrichtenübermittlung zu verringern.

![Beheben langsamer Nachrichtenfluss Regeln Einblicke in den Bereich "empfohlen für Sie" des Nachrichtenfluss-Dashboards](../../media/mfi-fix-slow-mail-flow-rules.png)

Wenn Sie auf das Widget **Details anzeigen** klicken, wird ein Flyout mit weiteren Informationen angezeigt:

- **Regel** : Sie können mit dem Mauszeiger auf die Zusammenfassung zeigen, um alle Bedingungen, Ausnahmen und Aktionen der Regel anzuzeigen. Sie können auf die Zusammenfassung klicken, um die Regel im Exchange Admin Center (EAC) zu bearbeiten.
- **Anzahl ausgewerteter Nachrichten** : Sie können auf **Beispiel Meldungen anzeigen** klicken, um die Ergebnisse der [Nachrichtenablaufverfolgung](message-trace-scc.md) für ein Beispiel der Nachrichten anzuzeigen, die von der Regel betroffen waren.
- **Durchschnittliche Zeitaufwand für jede Nachricht**
- **Für eine Nachricht aufgewendete mittlere Zeit** : der mittlere Wert, der die obere Hälfte von der unteren Hälfte der Zeit Daten trennt.

![Details-Flyout, das nach dem Klicken auf Details anzeigen im Fix Slow Mail Flow Rules Insight angezeigt wird](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Weitere Informationen zu Bedingungen und Ausnahmen in Nachrichtenflussregeln finden Sie unter [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

## <a name="see-also"></a>Weitere Informationen

Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).

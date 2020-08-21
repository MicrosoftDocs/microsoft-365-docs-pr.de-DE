---
title: Beheben eines möglichen Einblicks in den E-Mail-Loop
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie den Fix possible Mail Loop Insight im Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um e-Mail-Schleifen in Ihrer Organisation zu identifizieren und zu beheben.
ms.openlocfilehash: 162752ce6981e27d6ae2923aeb0fc33aec42bb0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826953"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Beheben möglicher Einblicke in die e-Mail-Schleife im Security & Compliance Center

Eine e-Mail-Schleife ist schlecht, da Sie Systemressourcen verschwendet, das Kontingent für das e-Mail-Volumen Ihres Unternehmens verwendet und verwirrende Unzustellbarkeitsberichte (auch bekannt als NDR oder Unzustellbarkeitsnachrichten) an die ursprünglichen Absender sendet.

Mit dem **Fix possible Mail Loop** Insight im Bereich **Recommended for you** des [Nachrichtenfluss-Dashboards](mail-flow-insights-v2.md) im Security & Compliance Center werden Sie benachrichtigt, wenn eine e-Mail-Schleife in Ihrer Organisation erkannt wird. Diese Einblicke wird erst nach dem Erkennen der Bedingung angezeigt (wenn Sie keine e-Mail-Schleifen haben, wird die Einblicke nicht angezeigt).

![Beheben langsamer Nachrichtenfluss Regeln Einblicke in den Bereich "empfohlen für Sie" des Nachrichtenfluss-Dashboards](../../media/mfi-fix-possible-mail-loop.png)

Wenn Sie auf das Widget **Details anzeigen** klicken, wird ein Flyout mit weiteren Informationen angezeigt:

- **Domäne**
- **Anzahl von Nachrichten**: Sie können auf **Beispiel Meldungen anzeigen** klicken, um die Ergebnisse der [Nachrichtenablaufverfolgung](message-trace-scc.md) für ein Beispiel der Nachrichten anzuzeigen, die von der Schleife betroffen waren.
- **Domain-Typ**"beispielsweise autorisierend oder nicht autorisierend.
- **MX-Eintrag**: der Host (**e-Mail-Server**) und die **Prioritäts** Werte des MX-Eintrags für die Domäne.
- **Schleifen Grund** und **How to Fix**: Wir werden versuchen, die gängigsten e-Mail-Schleifen Szenarien zu identifizieren und die empfohlenen Aktionen bereitzustellen (falls verfügbar), um die Schleife zu reparieren.

![Details-Flyout, das angezeigt wird, nachdem Sie auf Details anzeigen in der Fix possible Mail Loop Insight](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a>Verwandte Themen

Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).

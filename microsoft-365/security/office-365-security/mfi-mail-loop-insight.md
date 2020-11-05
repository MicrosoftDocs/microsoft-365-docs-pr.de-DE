---
title: Beheben eines möglichen Einblicks in den E-Mail-Loop
f1.keywords:
- NOCSH
ms.author: siosulli
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
ms.openlocfilehash: 1d49fd93b2ea068986e003b36077672215a2dd57
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920565"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Beheben möglicher Einblicke in die e-Mail-Schleife im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


E-Mail-Schleifen sind schlecht, da:

- Sie verschwenden Systemressourcen.
- Sie nutzen das Kontingent für das e-Mail-Volumen Ihres Unternehmens.
- Sie senden verwirrende Unzustellbarkeitsberichte (auch bekannt als NDR oder Unzustellbarkeitsnachrichten) an die ursprünglichen Nachrichtenabsender.

Mit dem **Fix possible Mail Loop** Insight im Bereich **Recommended for you** des [Nachrichtenfluss-Dashboards](mail-flow-insights-v2.md) im [Security & Compliance Center](https://protection.office.com) werden Sie benachrichtigt, wenn eine e-Mail-Schleife in Ihrer Organisation erkannt wird.

Diese Einblicke wird erst nach dem Erkennen der Bedingung angezeigt (wenn Sie keine e-Mail-Schleifen haben, wird die Einblicke nicht angezeigt).

![Beheben langsamer Nachrichtenfluss Regeln Einblicke in den Bereich "empfohlen für Sie" des Nachrichtenfluss-Dashboards](../../media/mfi-fix-possible-mail-loop.png)

Wenn Sie auf das Widget **Details anzeigen** klicken, wird ein Flyout mit weiteren Informationen angezeigt:

- **Domäne**
- **Anzahl von Nachrichten** : Sie können auf **Beispiel Meldungen anzeigen** klicken, um die Ergebnisse der [Nachrichtenablaufverfolgung](message-trace-scc.md) für ein Beispiel der Nachrichten anzuzeigen, die von der Schleife betroffen waren.
- **Domain-Typ** "beispielsweise autorisierend oder nicht autorisierend.
- **MX-Eintrag** : der Host ( **e-Mail-Server** ) und die **Prioritäts** Werte des MX-Eintrags für die Domäne.
- **Grund für Loop** und **How to Fix** : Wir werden die gängigsten e-Mail-Schleifen Szenarien identifizieren und empfohlene Aktionen zum Beheben der Schleife bereitstellen.

![Details-Flyout, das angezeigt wird, nachdem Sie auf Details anzeigen in der Fix possible Mail Loop Insight](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Weitere Informationen

Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).

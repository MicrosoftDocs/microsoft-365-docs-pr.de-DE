---
title: Erweiterte Kontingente und Verwendungsparameter in Microsoft 365 Defender
description: Verstehen verschiedener Kontingente und Verwendungsparameter (Dienstbeschränkungen), die den erweiterten Suchesdienst reaktionsfähig halten
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results, quota, parameters, allocation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245600"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Erweiterte Kontingente und Verwendungsparameter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Um die Leistungsfähigkeit und Reaktionsfähigkeit des Diensts zu halten, legt die erweiterte Suche verschiedene Kontingente und Verwendungsparameter fest (auch als "Dienstbeschränkungen" bezeichnet). Diese Kontingente und Parameter gelten separat für Abfragen, die manuell ausgeführt werden, und für Abfragen, die mit benutzerdefinierten [Erkennungsregeln ausgeführt werden.](custom-detection-rules.md) Kunden, die regelmäßig mehrere Abfragen ausführen, sollten [](advanced-hunting-best-practices.md) diese Grenzwerte beachten und bewährte Optimierungsmethoden anwenden, um Unterbrechungen zu minimieren.

Informationen zu vorhandenen Kontingenten und Verwendungsparametern finden Sie in der folgenden Tabelle.

| Kontingent oder Parameter | Size | Aktualisierungszyklus | Beschreibung |
|--|--|--|--|
| Datenbereich | 30 Tage | Jede Abfrage | Jede Abfrage kann Daten von bis zu den letzten 30 Tagen nachschauen. |
| Ergebnissatz | 10.000 Zeilen | Jede Abfrage | Jede Abfrage kann bis zu 10.000 Datensätze zurückgeben. |
| Timeout | 10 Minuten | Jede Abfrage | Jede Abfrage kann bis zu 10 Minuten ausgeführt werden. Wenn er nicht innerhalb von 10 Minuten abgeschlossen ist, zeigt der Dienst einen Fehler an.
| CPU-Ressourcen | Basierend auf der Mandantengröße | Alle 15 Minuten | Das [Portal zeigt einen Fehler an,](advanced-hunting-errors.md) wenn eine Abfrage ausgeführt wird und der Mandant mehr als 10 % der zugewiesenen Ressourcen verbraucht hat. Abfragen werden blockiert, wenn der Mandant bis nach dem nächsten Zyklus von 15 Minuten 100 % erreicht hat. |

>[!NOTE] 
>Ein separater Satz von Kontingenten und Parametern gilt für erweiterte Suchabfragen, die über die API ausgeführt werden. [Informationen zu erweiterten ApIs für die Suche](./api-advanced-hunting.md)

## <a name="related-topics"></a>Verwandte Themen

- [Bewährte Methoden für die erweiterte Suche](advanced-hunting-best-practices.md)
- [Behandeln von Fehlern bei der erweiterten Suche](advanced-hunting-errors.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Benutzerdefinierte Erkennungen – Übersicht](custom-detections-overview.md)
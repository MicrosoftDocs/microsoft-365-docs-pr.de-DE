---
title: Erweiterte Grenzwerte für die Suche in Microsoft Defender ATP
description: Verstehen verschiedener Dienstbeschränkungen, die den erweiterten Suchesdienst reaktionsfähig halten
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Mdatp, microsoft defender atp, wdatp, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 127ebc8c0eaba433710bc272a2cf602e7c9a9730
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067944"
---
# <a name="advanced-hunting-service-limits"></a>Erweiterte Grenzwerte für den Suchesdienst

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Um die Leistungsfähigkeit und Reaktionsfähigkeit des Diensts zu halten, legt die erweiterte Suche verschiedene Grenzwerte für Abfragen fest, die manuell und nach [benutzerdefinierten Erkennungsregeln ausgeführt werden.](custom-detection-rules.md) Informationen zu diesen Grenzwerten finden Sie in der folgenden Tabelle.

| Grenze | Size | Aktualisierungszyklus | Beschreibung |
|--|--|--|--|
| Datenbereich | 30 Tage | Jede Abfrage | Jede Abfrage kann Daten von bis zu den letzten 30 Tagen nachschauen. |
| Ergebnissatz | 10.000 Zeilen | Jede Abfrage | Jede Abfrage kann bis zu 10.000 Datensätze zurückgeben. |
| Timeout | 10 Minuten | Jede Abfrage | Jede Abfrage kann bis zu 10 Minuten ausgeführt werden. Wenn er nicht innerhalb von 10 Minuten abgeschlossen ist, zeigt der Dienst einen Fehler an.
| CPU-Ressourcen | Basierend auf der Mandantengröße | - Zur Stunde und dann alle 15 Minuten<br>- Täglich um 12:00 Uhr | Der Dienst erzwingt den täglichen und den 15-Minuten-Grenzwert separat. Für jeden Grenzwert zeigt das [Portal](advanced-hunting-errors.md) einen Fehler an, wenn eine Abfrage ausgeführt wird und der Mandant mehr als 10 % der zugewiesenen Ressourcen verbraucht hat. Abfragen werden blockiert, wenn der Mandant bis nach dem nächsten täglichen oder 15-minütigen Zyklus 100 % erreicht hat. |

>[!NOTE] 
>Ein separater Satz von Grenzwerten gilt für erweiterte Suchabfragen, die über die API ausgeführt werden. [Informationen zu erweiterten ApIs für die Suche](run-advanced-query-api.md)

Kunden, die regelmäßig mehrere Abfragen ausführen, sollten den Verbrauch nachverfolgen und bewährte Methoden zur Optimierung anwenden, um Unterbrechungen zu minimieren, die sich aus der Überschreitung dieser Grenzwerte ergeben. [](advanced-hunting-best-practices.md)

## <a name="related-topics"></a>Verwandte Themen

- [Bewährte Methoden für die erweiterte Suche](advanced-hunting-best-practices.md)
- [Behandeln von Fehlern bei der erweiterten Suche](advanced-hunting-errors.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Regeln für benutzerdefinierte Erkennungen](custom-detection-rules.md)

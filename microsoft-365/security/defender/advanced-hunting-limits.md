---
title: Erweiterte Kontingente und Verwendungsparameter in Microsoft 365 Defender
description: Verstehen verschiedener Kontingente und Verwendungsparameter (Dienstbeschränkungen), die den erweiterten Suchesdienst reaktionsfähig halten
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schema, Kusto, CPU-Grenzwert, Abfragebeschränkung, Ressourcen, maximale Ergebnisse, Kontingent, Parameter, Zuordnung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 19606b06ff1a1369614bab533a949bc383c90ad3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064735"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Erweiterte Kontingente und Verwendungsparameter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Um die Leistungsfähigkeit und Reaktionsfähigkeit des Diensts zu halten, legt die erweiterte Suche verschiedene Kontingente und Verwendungsparameter fest (auch als "Dienstbeschränkungen" bezeichnet). Diese Kontingente und Parameter gelten für Abfragen, die manuell und mit benutzerdefinierten [Erkennungsregeln ausgeführt werden.](custom-detection-rules.md) Kunden, die regelmäßig mehrere Abfragen ausführen, sollten den Verbrauch nachverfolgen und bewährte Methoden zur Optimierung [anwenden,](advanced-hunting-best-practices.md) um Unterbrechungen zu minimieren.

Informationen zu vorhandenen Kontingenten und Verwendungsparametern finden Sie in der folgenden Tabelle.

| Kontingent oder Parameter | Size | Aktualisierungszyklus | Beschreibung |
|--|--|--|--|
| Datenbereich | 30 Tage | Jede Abfrage | Jede Abfrage kann Daten von bis zu den letzten 30 Tagen nachschauen. |
| Ergebnissatz | 10.000 Zeilen | Jede Abfrage | Jede Abfrage kann bis zu 10.000 Datensätze zurückgeben. |
| Timeout | 10 Minuten | Jede Abfrage | Jede Abfrage kann bis zu 10 Minuten ausgeführt werden. Wenn er nicht innerhalb von 10 Minuten abgeschlossen ist, zeigt der Dienst einen Fehler an.
| CPU-Ressourcen | Basierend auf der Mandantengröße | - Zur Stunde und dann alle 15 Minuten<br>- Täglich um 12:00 Uhr | Der Dienst erzwingt das tägliche und das 15-Minuten-Kontingent separat. Für jedes Kontingent zeigt das [Portal](advanced-hunting-errors.md) einen Fehler an, wenn eine Abfrage ausgeführt wird und der Mandant mehr als 10 % der zugewiesenen Ressourcen verbraucht hat. Abfragen werden blockiert, wenn der Mandant bis nach dem nächsten täglichen oder 15-minütigen Zyklus 100 % erreicht hat. |

>[!NOTE] 
>Ein separater Satz von Kontingenten und Parametern gilt für erweiterte Suchabfragen, die über die API ausgeführt werden. [Informationen zu erweiterten ApIs für die Suche](./api-advanced-hunting.md)

## <a name="related-topics"></a>Verwandte Themen

- [Bewährte Methoden für die erweiterte Suche](advanced-hunting-best-practices.md)
- [Behandeln von Fehlern bei der erweiterten Suche](advanced-hunting-errors.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Benutzerdefinierte Erkennungen – Übersicht](custom-detections-overview.md)
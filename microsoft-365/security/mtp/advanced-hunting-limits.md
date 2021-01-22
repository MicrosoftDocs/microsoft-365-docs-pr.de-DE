---
title: Erweiterte Kontingente und Verwendungsparameter in Microsoft 365 Defender
description: Verstehen verschiedener Kontingente und Verwendungsparameter (Dienstbeschränkungen), die den dienst für die erweiterte Suche reaktionsfähig halten
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schema, Kusto, CPU-Grenzwert, Abfragegrenzwert, Ressourcen, maximale Ergebnisse, Kontingent, Parameter, Zuordnung
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929790"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Erweiterte Kontingente und Verwendungsparameter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Um die Leistungsfähigkeit und Reaktionsfähigkeit des Diensts zu halten, legt die erweiterte Suche verschiedene Kontingente und Verwendungsparameter (auch als "Dienstbeschränkungen" bezeichnet) fest. Diese Kontingente und Parameter gelten für Abfragen, die manuell und durch benutzerdefinierte [Erkennungsregeln ausgeführt werden.](custom-detection-rules.md) Kunden, die regelmäßig mehrere Abfragen ausführen, sollten den Verbrauch nachverfolgen und bewährte Optimierungsmethoden anwenden, [um](advanced-hunting-best-practices.md) Unterbrechungen zu minimieren.

In der folgenden Tabelle finden Sie Informationen zu vorhandenen Kontingenten und Verwendungsparametern.

| Kontingent oder Parameter | Größe | Aktualisierungszyklus | Beschreibung |
|--|--|--|--|
| Datenbereich | 30 Tage | Jede Abfrage | Jede Abfrage kann Daten von bis zu den letzten 30 Tagen nachschauen. |
| Ergebnissatz | 10.000 Zeilen | Jede Abfrage | Jede Abfrage kann bis zu 10.000 Datensätze zurückgeben. |
| Timeout | 10 Minuten | Jede Abfrage | Jede Abfrage kann bis zu 10 Minuten lang ausgeführt werden. Wenn sie nicht innerhalb von 10 Minuten abgeschlossen wird, zeigt der Dienst einen Fehler an.
| CPU-Ressourcen | Basierend auf der Mandantengröße | - In der Stunde und dann alle 15 Minuten<br>- Täglich um 12 Uhr | Der Dienst erzwingt das tägliche und das 15-Minuten-Kontingent separat. Für jedes Kontingent zeigt das [Portal](advanced-hunting-errors.md) einen Fehler an, wenn eine Abfrage ausgeführt wird und der Mandant mehr als 10 % der zugewiesenen Ressourcen verbraucht hat. Abfragen werden blockiert, wenn der Mandant 100 % erreicht hat, bis nach dem nächsten täglichen oder 15-minütigen Zyklus. |

>[!NOTE] 
>Ein separater Satz von Kontingenten und Parametern gilt für Abfragen der erweiterten Suche, die über die API ausgeführt werden. [Informationen zu APIs für die erweiterte Suche](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>Verwandte Themen

- [Bewährte Methoden für die erweiterte Suche](advanced-hunting-best-practices.md)
- [Behandeln von Fehlern bei der erweiterten Suche](advanced-hunting-errors.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Benutzerdefinierte Erkennungen – Übersicht](custom-detections-overview.md)
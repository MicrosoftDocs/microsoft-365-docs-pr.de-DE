---
title: Erweiterte Jagd Grenzwerte im Microsoft Threat Protection
description: Verstehen verschiedener Diensteinschränkungen, die den erweiterten Jagd Dienst reaktionsfähig halten
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schema, Kusto, CPU-Grenze, Abfrage Grenzwert, Ressourcen, maximale Ergebnisse
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: ab19c86bbdec243dd4abb8b6c9fab9b5ec6f2228
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430455"
---
# <a name="advanced-hunting-service-limits"></a>Grenzwerte für erweiterte Jagd Dienste

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Um den Dienst leistungsfähig und reaktionsfähig zu halten, setzt Advanced Hunting verschiedene Grenzwerte für Abfragen, die manuell und nach [benutzerdefinierten Erkennungsregeln](custom-detection-rules.md)ausgeführt werden. Lesen Sie die folgende Tabelle, um diese Grenzwerte zu verstehen.

| Grenze | Größe | Aktualisierungszyklus | Beschreibung |
|--|--|--|--|
| Datenbereich | 30 Tage | Jede Abfrage | Jede Abfrage kann Daten von bis zu den letzten 30 Tagen nachschlagen. |
| Ergebnismenge | 10.000 Zeilen | Jede Abfrage | Jede Abfrage kann bis zu 10.000 Datensätze zurückgeben. |
| Timeout | 10 Minuten | Jede Abfrage | Jede Abfrage kann bis zu 10 Minuten lang ausgeführt werden. Wenn der Dienst nicht innerhalb von 10 Minuten abgeschlossen ist, wird ein Fehler angezeigt.
| CPU-Ressourcen | Basierend auf der Mandanten Größe | -Auf die Stunde und dann alle 15 Minuten<br>-Täglich um 12 Uhr | Der Dienst erzwingt den täglichen und den 15-minütigen Grenzwert separat. Für jeden Grenzwert zeigt das [Portal einen Fehler](advanced-hunting-errors.md) an, wenn eine Abfrage ausgeführt wird und der Mandant mehr als 10% der zugeordneten Ressourcen verbraucht hat. Abfragen werden blockiert, wenn der Mandant 100% bis nach dem nächsten täglichen oder 15-minütigen Zyklus erreicht hat. |

>[!NOTE] 
>Eine separate Reihe von Grenzwerten gilt für erweiterte Suchabfragen, die über die API ausgeführt werden. [Lesen Sie mehr über erweiterte Jagd-APIs](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

Kunden, die mehrere Abfragen regelmäßig ausführen, sollten den Verbrauch nachverfolgen und [bewährte Methoden für die Optimierung anwenden](advanced-hunting-best-practices.md) , um Unterbrechungen aufgrund der Überschreitung dieser Grenzwerte zu minimieren.

## <a name="related-topics"></a>Verwandte Themen

- [Bewährte Methoden für die erweiterte Suche](advanced-hunting-best-practices.md)
- [Behandeln von erweiterten Jagd Fehlern](advanced-hunting-errors.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Benutzerdefinierte Erkennungen – Übersicht](custom-detections-overview.md)

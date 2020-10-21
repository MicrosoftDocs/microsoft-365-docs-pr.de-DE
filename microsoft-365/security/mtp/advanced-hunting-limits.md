---
title: Erweiterte Jagd Kontingente und Nutzungsparameter in Microsoft Threat Protection
description: Grundlegendes zu verschiedenen Kontingenten und Nutzungsparametern (Service Limits), mit denen der erweiterte Jagd Dienst reaktionsfähig bleibt
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schema, Kusto, CPU-Grenze, Abfrage Grenzwert, Ressourcen, maximale Ergebnisse, Kontingent, Parameter, Zuweisung
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
ms.openlocfilehash: 192fb47aafdd20bd5e1f0774a64ec3215f1203d1
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636905"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Erweiterte Jagd Kontingente und Nutzungsparameter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Um den Dienst leistungsfähig und reaktionsfähig zu halten, setzt Advanced Hunting verschiedene Kontingente und Nutzungsparameter (auch bekannt als "Service Limits"). Diese Kontingente und Parameter gelten für Abfragen, die manuell und durch [benutzerdefinierte Erkennungsregeln](custom-detection-rules.md)ausgeführt werden. Kunden, die regelmäßig mehrere Abfragen ausführen, sollten den Verbrauch nachverfolgen und [bewährte Methoden zur Optimierung anwenden](advanced-hunting-best-practices.md) , um Störungen zu minimieren.

Lesen Sie die folgende Tabelle, um die vorhandenen Kontingente und Nutzungsparameter zu verstehen.

| Quota oder Parameter | Größe | Aktualisierungszyklus | Beschreibung |
|--|--|--|--|
| Datenbereich | 30 Tage | Jede Abfrage | Jede Abfrage kann Daten von bis zu den letzten 30 Tagen nachschlagen. |
| Ergebnismenge | 10.000 Zeilen | Jede Abfrage | Jede Abfrage kann bis zu 10.000 Datensätze zurückgeben. |
| Timeout | 10 Minuten | Jede Abfrage | Jede Abfrage kann bis zu 10 Minuten lang ausgeführt werden. Wenn der Dienst nicht innerhalb von 10 Minuten abgeschlossen ist, wird ein Fehler angezeigt.
| CPU-Ressourcen | Basierend auf der Mandanten Größe | -Auf die Stunde und dann alle 15 Minuten<br>-Täglich um 12 Uhr | Der Dienst erzwingt das tägliche und das 15-minütige Kontingent separat. Für jedes Kontingent wird bei jeder Ausführung einer Abfrage ein [Fehler angezeigt](advanced-hunting-errors.md) , und der Mandant hat mehr als 10% der zugeordneten Ressourcen verbraucht. Abfragen werden blockiert, wenn der Mandant 100% bis nach dem nächsten täglichen oder 15-minütigen Zyklus erreicht hat. |

>[!NOTE] 
>Eine separate Gruppe von Kontingenten und Parametern gilt für erweiterte Jagd Abfragen, die über die API ausgeführt werden. [Lesen Sie mehr über erweiterte Jagd-APIs](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>Verwandte Themen

- [Bewährte Methoden für die erweiterte Suche](advanced-hunting-best-practices.md)
- [Behandeln von erweiterten Jagd Fehlern](advanced-hunting-errors.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Benutzerdefinierte Erkennungen – Übersicht](custom-detections-overview.md)
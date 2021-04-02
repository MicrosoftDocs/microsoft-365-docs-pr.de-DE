---
title: AlertInfo-Tabelle im Schema der erweiterten Suche
description: Informationen zu Benachrichtigungsgenerierungsereignissen in der AlertInfo-Tabelle des schemas für erweiterte Suche
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, severity, category, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS, and Azure ATP
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
ms.openlocfilehash: 1386830a4b3e05009b19a7d0e3a4ea62ce3321f2
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499828"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Warnungen von `AlertInfo` Microsoft Defender for Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `AlertId` | string | Eindeutiger Bezeichner der Warnung |
| `Title` | string | Titel der Warnung |
| `Category` | string | Typ des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität |
| `Severity` | string | Zeigt die potenziellen Auswirkungen (hoch, mittel oder gering) des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität an |
| `ServiceSource` | string | Produkt oder Dienst, das die Warnungsinformationen bereitgestellt hat |
| `DetectionSource` | Zeichenfolge | Erkennungstechnologie oder Sensor, die die wichtige Komponente oder Aktivität identifiziert hat |
| `AttackTechniques` | Zeichenfolge | MITRE ATT&CK-Techniken, die der Aktivität zugeordnet sind, die die Warnung ausgelöst hat |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

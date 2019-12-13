---
title: Tabelle "AlertEvents" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die Warnungserstellungsereignisse in der Tabelle "AlertEvents" des Schema "Erweiterte Suche".
keywords: erweiterte Suche, Suche nach Bedrohungen, Suche nach Cyberbedrohungen, Suche, Anfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, Warnungsereignisse, Warnung, Schweregrad, Kategorie
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4d83b659a98c56cc59e88f9777aa73ca2e25b745
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911127"
---
# <a name="alertevents"></a>AlertEvents

**Gilt für:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

Die Tabelle `AlertEvents` im Schema [Erweiterte Suche](advanced-hunting-overview.md) enthält Informationen zu Microsoft Defender ATP-Warnungen. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `AlertId` | string | Eindeutiger Bezeichner der Warnung |
| `EventTime` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `MachineId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `ComputerName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `Severity` | string | Zeigt die potenziellen Auswirkungen (hoch, mittel oder gering) des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität an |
| `Category` | string | Typ des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität |
| `Title` | string | Titel der Warnung |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `RemoteUrl` | string | URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde |
| `RemoteIP` | string | IP-Adresse, mit der eine Verbindung hergestellt wurde |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Diese Spalte muss in Verbindung mit den Spalten "ComputerName" und "EventTime" verwendet werden, um Ereignisse eindeutig zu identifizieren. |
| `Table` | string | Tabelle, die die Details des Ereignisses enthält |

## <a name="related-topics"></a>Verwandte Themen
- [Vorbeugende Suche nach Bedrohungen](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche nach Bedrohungen auf Geräten und in E-Mails](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

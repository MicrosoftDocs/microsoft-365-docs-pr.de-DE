---
title: DeviceAlertEvents-Tabelle im schema der erweiterten Suche
description: Informationen zu Benachrichtigungsgenerierungsereignissen in der DeviceAlertEvents-Tabelle des schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Mdatp, microsoft defender atp, microsoft defender for endpoint, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, DeviceAlertEvents, alert, severity, category
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: f4f6ecdc57d8602f49fb389c741c5e01dc1b41b5
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939648"
---
# <a name="devicealertevents"></a>DeviceAlertEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)



>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Die `DeviceAlertEvents` Tabelle im Schema der erweiterten [Suche](advanced-hunting-overview.md) enthält Informationen zu Warnungen in Microsoft Defender Security Center. Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.

Weitere Informationen zu anderen Tabellen im Schema für die erweiterte Suche finden Sie in der [Schemareferenz](advanced-hunting-schema-reference.md)für erweiterte Suche .

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `AlertId` | string | Eindeutiger Bezeichner der Warnung |
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutige ID für das Gerät im Dienst |
| `DeviceName` | Zeichenfolge | Vollqualifizierter Domänenname (FQDN) des Geräts |
| `Severity` | string | Zeigt die potenziellen Auswirkungen (hoch, mittel oder gering) des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität an |
| `Category` | string | Typ des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität |
| `Title` | string | Titel der Warnung |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `RemoteUrl` | string | URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde |
| `RemoteIP` | string | IP-Adresse, mit der eine Verbindung hergestellt wurde |
| `AttackTechniques` | Zeichenfolge | MITRE ATT&CK-Techniken, die der Aktivität zugeordnet sind, die die Warnung ausgelöst hat |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten `DeviceName` und verwendet `Timestamp` werden. |
| `Table` | string | Tabelle, die die Details des Ereignisses enthält |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-reference.md)

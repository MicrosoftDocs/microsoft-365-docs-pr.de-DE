---
title: DeviceAlertEvents-Tabelle im schema der erweiterten Suche
description: Informationen zu Benachrichtigungsgenerierungsereignissen in der DeviceAlertEvents-Tabelle des schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Mdatp, Microsoft Defender Atp, wdatp-Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, DeviceAlertEvents, Warnung, Schweregrad, Kategorie
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
ms.openlocfilehash: 66ecdc8fbcde04d78f2deede5f4e296a7f051ef0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499162"
---
# <a name="devicealertevents"></a>DeviceAlertEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)



>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Die `DeviceAlertEvents` Tabelle im Schema der erweiterten [Suche](advanced-hunting-overview.md) enthält Informationen zu Warnungen im Microsoft Defender Security Center. Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.

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

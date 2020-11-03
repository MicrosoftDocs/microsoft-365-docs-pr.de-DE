---
title: DeviceInfo-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über Betriebssystem, Computername und andere Computer Informationen in der deviceInfo-Tabelle des Advanced Hunting-Schemas.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, machineinfo, deviceInfo, Gerät, Computer, OS, Plattform, Benutzer
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
ms.openlocfilehash: 1bb48b4332bc9d60de15bb513f04a503d6a6913b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842714"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Die `DeviceInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Computern in der Organisation, einschließlich Betriebssystemversion, aktive Benutzer und Computername. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `ClientVersion` | string | Version des Endpunkt-Agents oder-Sensors, der auf dem Computer läuft |
| `PublicIP` | string | Öffentliche IP-Adresse, die vom Onboarding-Computer zum Herstellen einer Verbindung mit dem Microsoft Defender für den Endpunkt Dienst verwendet wird. Hierbei kann es sich um die IP-Adresse des Computers selbst, eines NAT-Geräts oder eines Proxys handeln. |
| `OSArchitecture` | string | Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird. |
| `OSPlatform` | string | Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird. Dies weist auf bestimmte Betriebssysteme hin, einschließlich Variationen innerhalb der gleichen Familie wie Windows 10 und Windows 7 |
| `OSBuild` | string | Buildversion des Betriebssystems, das auf dem Computer läuft |
| `IsAzureADJoined` | Boolescher Wert | Boolescher Indikator dafür, ob der Computer mit dem Azure-Active Directory verbunden ist |
| `LoggedOnUsers` | string | Liste aller Benutzer, die zum Zeitpunkt des Ereignisses im JSON-Array Format auf dem Computer angemeldet sind |
| `RegistryDeviceTag` | string | Durch die Registrierung hinzugefügtes Machine-Tag |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte zusammen mit den Gerätename-und timestamp-Spalten verwendet werden. |
| `OSVersion` | string | Die Version des Betriebssystem, das auf dem Computer ausgeführt wird. |
| `MachineGroup` | string | Computergruppe des Computers. Diese Gruppe wird von der rollenbasierten Zugriffssteuerung verwendet, um den Zugriff auf den Computer zu bestimmen. |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suchen auf Geräten, in E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

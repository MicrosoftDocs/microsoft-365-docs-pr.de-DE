---
title: DeviceInfo-Tabelle im Schema für die erweiterte Suche
description: Weitere Informationen zu Betriebssystem, Computername und anderen Computerinformationen finden Sie in der DeviceInfo-Tabelle des schemas für die erweiterte Suche.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machineinfo, DeviceInfo, device, machine, os, platform, users
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
ms.openlocfilehash: f97947c2c9f02720facae4f0c3c29ff702416261
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023129"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender
- Microsoft Defender für Endpunkt



Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Geräten in der Organisation, einschließlich Betriebssystemversion, aktiven Benutzern `DeviceInfo` und Computernamen. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `ClientVersion` | string | Version des Endpunkt-Agents oder -Sensors, der auf dem Computer ausgeführt wird |
| `PublicIP` | Zeichenfolge | Öffentliche IP-Adresse, die vom integrierten Computer zum Herstellen einer Verbindung mit dem Microsoft Defender for Endpoint-Dienst verwendet wird. Dies kann die IP-Adresse des Computers selbst, eines NAT-Geräts oder eines Proxys sein. |
| `OSArchitecture` | string | Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird. |
| `OSPlatform` | string | Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird. Dies gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7 |
| `OSBuild` | Zeichenfolge | Erstellen der Version des Betriebssystems, das auf dem Computer ausgeführt wird |
| `IsAzureADJoined` | boolean | Boolescher Indikator, ob der Computer mit der Azure Active Directory |
| `AadObjectId` | Zeichenfolge | Eindeutige ID für das Gerät in Azure AD |
| `LoggedOnUsers` | Zeichenfolge | Liste aller Benutzer, die zum Zeitpunkt des Ereignisses im JSON-Arrayformat auf dem Computer angemeldet sind |
| `RegistryDeviceTag` | Zeichenfolge | Computertag, das über die Registrierung hinzugefügt wurde |
| `OSVersion` | string | Die Version des Betriebssystem, das auf dem Computer ausgeführt wird. |
| `MachineGroup` | string | Computergruppe des Computers. Diese Gruppe wird von der rollenbasierten Zugriffssteuerung verwendet, um den Zugriff auf den Computer zu bestimmen. |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden. |
|`AdditionalFields` | Zeichenfolge | Zusätzliche Informationen zum Ereignis im JSON-Arrayformat |

Die Tabelle enthält Geräteinformationen basierend auf Takten, bei denen es sich um periodische Berichte oder `DeviceInfo` Signale eines Geräts handelt. Alle 15 Minuten sendet das Gerät einen teilweisen Takt, der häufig geänderte Attribute wie `LoggedOnUsers` enthält. Einmal am Tag wird ein vollständiger Takt mit den Attributen des Geräts gesendet.

Sie können die folgende Beispielabfrage verwenden, um den neuesten Status eines Geräts zu erhalten:

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

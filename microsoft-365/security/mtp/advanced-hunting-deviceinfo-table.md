---
title: Tabelle "DeviceInfo" im Schema "Erweiterte Suche"
description: Informationen zu Betriebssystem, Computername und anderen Computerinformationen in der Tabelle "DeviceInfo" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, MachineInfo, DeviceInfo, Gerät, Computer, BETRIEBSSYSTEM, Plattform, Benutzer
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
ms.openlocfilehash: 6462096a6c1b44ee11299f652a54f261d0355523
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145367"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu Computern in der Organisation, einschließlich Betriebssystemversion, aktiven Benutzern `DeviceInfo` und Computernamen. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `ClientVersion` | string | Version des Endpunkt-Agents oder Sensors, der auf dem Computer ausgeführt wird |
| `PublicIP` | string | Öffentliche IP-Adresse, die vom integrierten Computer zum Herstellen einer Verbindung mit dem Microsoft Defender für Endpunktdienst verwendet wird. Dies kann die IP-Adresse des Computers selbst, ein NAT-Gerät oder ein Proxy sein. |
| `OSArchitecture` | string | Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird. |
| `OSPlatform` | string | Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird. Dies weist auf bestimmte Betriebssysteme hin, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7. |
| `OSBuild` | string | Buildversion des Betriebssystems, das auf dem Computer ausgeführt wird |
| `IsAzureADJoined` | boolean | Boolescher Indikator dafür, ob der Computer mit Azure Active Directory verbunden ist |
| `DeviceObjectId` | string | Eindeutiger Bezeichner für das Gerät in Azure AD |
| `LoggedOnUsers` | string | Liste aller Benutzer, die zum Zeitpunkt des Ereignisses im JSON-Array-Format auf dem Computer angemeldet sind |
| `RegistryDeviceTag` | string | Computertag, das über die Registrierung hinzugefügt wurde |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten "DeviceName" und "Timestamp" verwendet werden. |
|`AdditionalFields` | string | Zusätzliche Informationen zu dem Ereignis im JSON-Array-Format |
| `OSVersion` | string | Die Version des Betriebssystem, das auf dem Computer ausgeführt wird. |
| `MachineGroup` | string | Computergruppe des Computers. Diese Gruppe wird von der rollenbasierten Zugriffssteuerung verwendet, um den Zugriff auf den Computer zu bestimmen. |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

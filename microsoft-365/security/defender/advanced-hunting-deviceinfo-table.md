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
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689109"
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
| `PublicIP` | string | Öffentliche IP-Adresse, die vom integrierten Computer zum Herstellen einer Verbindung mit dem Microsoft Defender for Endpoint-Dienst verwendet wird. Dies kann die IP-Adresse des Computers selbst, eines NAT-Geräts oder eines Proxys sein. |
| `OSArchitecture` | string | Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird. |
| `OSPlatform` | string | Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird. Dies gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7 |
| `OSBuild` | string | Erstellen der Version des Betriebssystems, das auf dem Computer ausgeführt wird |
| `IsAzureADJoined` | boolean | Boolescher Indikator, ob der Computer mit der Azure Active Directory |
| `AadObjectId` | string | Eindeutige ID für das Gerät in Azure AD |
| `LoggedOnUsers` | string | Liste aller Benutzer, die zum Zeitpunkt des Ereignisses im JSON-Arrayformat auf dem Computer angemeldet sind |
| `RegistryDeviceTag` | string | Computertag, das über die Registrierung hinzugefügt wurde |
| `OSVersion` | string | Die Version des Betriebssystem, das auf dem Computer ausgeführt wird. |
| `MachineGroup` | string | Computergruppe des Computers. Diese Gruppe wird von der rollenbasierten Zugriffssteuerung verwendet, um den Zugriff auf den Computer zu bestimmen. |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden. |
| `OnboardingStatus` | string | Gibt an, ob das Gerät derzeit in Microsoft Defender For Endpoint onboarded ist oder ob das Gerät nicht unterstützt wird. |
|`AdditionalFields` | string | Zusätzliche Informationen zum Ereignis im JSON-Arrayformat |
|`DeviceCategory` | string | Umfassendere Klassifizierung, die bestimmte Gerätetypen in den folgenden Kategorien einteilt: Endpunkt, Netzwerkgerät, IoT, Unbekannt |
|`DeviceType` | string | Gerätetyp basierend auf Zweck und Funktionalität, z. B. Netzwerkgerät, Arbeitsstation, Server, Mobil, Spielekonsole oder Drucker |
|`DeviceSubType` | string | Zusätzlicher Modifizierer für bestimmte Gerätetypen, z. B. ein mobiles Gerät kann ein Tablet oder ein Smartphone sein |
|`Model` | string | Modellname oder Nummer des Produkts des Herstellers oder Herstellers |
|`Vendor` | string | Name des Produktanbieters oder Herstellers |
|`OSDistribution` | string | Verteilung der Betriebssystemplattform, z. B. Ubuntu oder RedHat für Linux-Plattformen |
|`OSVersionInfo` | string | Zusätzliche Informationen zur Betriebssystemversion, z. B. der beliebte Name, der Codename oder die Versionsnummer |
|`MergedDeviceIds` | string | Frühere Geräte-IDs, die demselben Gerät zugewiesen wurden |
|`MergedToDeviceId` | string | Die neueste Geräte-ID, die einem Gerät zugewiesen ist |

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

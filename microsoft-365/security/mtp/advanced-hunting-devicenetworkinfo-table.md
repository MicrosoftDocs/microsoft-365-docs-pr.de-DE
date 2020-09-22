---
title: DeviceNetworkInfo-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über die Netzwerkkonfigurationsinformationen in der DeviceNetworkInfo-Tabelle des Advanced Hunting-Schemas.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, machinenetworkinfo, DeviceNetworkInfo, Gerät, Computer, Mac, IP, Adapter, DNS, DHCP, Gateway, Tunnel
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b874ef77dcf6efacd7adeff18553c0c8e6752bda
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197073"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection



Die `DeviceNetworkInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zur Netzwerkkonfiguration von Computern, einschließlich Netzwerkadaptern, IP-und Mac-Adressen und verbundenen Netzwerken oder Domänen. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte zusammen mit den Gerätename-und timestamp-Spalten verwendet werden. |
| `NetworkAdapterName` | Zeichenfolge | Name des Netzwerkadapters |
| `MacAddress` | Zeichenfolge | Mac-Adresse des Netzwerkadapters |
| `NetworkAdapterType` | Zeichenfolge | Typ des Netzwerkadapters. Informationen zu den möglichen Werten finden Sie in [dieser Aufzählung](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | Zeichenfolge | Betriebsstatus des Netzwerkadapters. Informationen zu den möglichen Werten finden Sie in [dieser Aufzählung](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | Zeichenfolge | Tunneling-Protokoll, wenn die Schnittstelle zu diesem Zweck verwendet wird, beispielsweise 6to4, Teredo, ISATAP, PPTP, SSTP und SSH |
| `ConnectedNetworks` | Zeichenfolge | Netzwerke, mit denen der Adapter verbunden ist. Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist. |
| `DnsAddresses` | Zeichenfolge | DNS-Serveradressen im JSON-Array Format |
| `IPv4Dhcp` | Zeichenfolge | IPv4-Adresse des DHCP-Servers |
| `IPv6Dhcp` | Zeichenfolge | IPv6-Adresse des DHCP-Servers |
| `DefaultGateways` | Zeichenfolge | Standardgateway-Adressen im JSON-Array Format |
| `IPAddresses` | Zeichenfolge | JSON-Array, das alle dem Adapter zugewiesenen IP-Adressen zusammen mit dem jeweiligen Subnetz-Präfix und dem IP-Adressraum enthält, beispielsweise Public, private oder Link-Local |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suchen auf Geräten, in E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

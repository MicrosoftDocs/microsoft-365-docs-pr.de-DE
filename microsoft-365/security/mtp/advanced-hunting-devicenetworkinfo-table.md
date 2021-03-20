---
title: DeviceNetworkInfo-Tabelle im schema der erweiterten Suche
description: Informationen zu Netzwerkkonfigurationsinformationen in der DeviceNetworkInfo-Tabelle des Schemas für die erweiterte Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, adapter, dns, dhcp, gateway, tunnel
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
ms.openlocfilehash: 3e3b657d1c33e411f38a8f583adb96139cc85207
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907396"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Die Tabelle im Schema der erweiterten Suche enthält Informationen zur Netzwerkkonfiguration von Computern, einschließlich Netzwerkadaptern, IP- und MAC-Adressen sowie verbundenen `DeviceNetworkInfo` Netzwerken oder Domänen. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden. |
| `NetworkAdapterName` | string | Name des Netzwerkadapters |
| `MacAddress` | string | MAC-Adresse des Netzwerkadapters |
| `NetworkAdapterType` | string | Netzwerkadaptertyp. Mögliche Werte finden Sie in [dieser Enumeration.](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | string | Betriebsstatus des Netzwerkadapters. Mögliche Werte finden Sie in [dieser Enumeration.](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | string | Tunnelingprotokoll, wenn die Schnittstelle zu diesem Zweck verwendet wird, z. B. 6to4, Teredo, ISATAP, PPTP, SSTP und SSH |
| `ConnectedNetworks` | string | Netzwerke, mit der der Adapter verbunden ist. Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist. |
| `DnsAddresses` | string | DNS-Serveradressen im JSON-Arrayformat |
| `IPv4Dhcp` | string | IPv4-Adresse des DHCP-Servers |
| `IPv6Dhcp` | string | IPv6-Adresse des DHCP-Servers |
| `DefaultGateways` | string | Standardgatewayadressen im JSON-Arrayformat |
| `IPAddresses` | string | JSON-Array, das alle dem Adapter zugewiesenen IP-Adressen sowie das entsprechende Subnetzpräfix und den entsprechenden IP-Adressraum enthält, z. B. öffentlich, privat oder link-lokal |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
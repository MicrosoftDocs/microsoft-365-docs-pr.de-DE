---
title: DeviceNetworkInfo-Tabelle im schema der erweiterten Suche
description: Informationen zu Netzwerkkonfigurationsinformationen in der DeviceNetworkInfo-Tabelle des Schemas für die erweiterte Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, devicenetworkinfo, device, device, mac, ip, adapter, dns, dhcp, gateway, tunnel, DeviceNetworkInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4ba3e81163cdbba54bf718dca929e2df3b39a1c3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067055"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Die Tabelle im Schema der erweiterten Suche enthält Informationen zur Netzwerkkonfiguration von Geräten, einschließlich Netzwerkadaptern, IP- und MAC-Adressen sowie verbundenen `DeviceNetworkInfo` Netzwerken oder Domänen. [](advanced-hunting-overview.md) Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.

Weitere Informationen zu anderen Tabellen im Schema für die erweiterte Suche finden Sie in der [Schemareferenz](advanced-hunting-schema-reference.md)für erweiterte Suche .

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutige ID für das Gerät im Dienst |
| `DeviceName` | Zeichenfolge | Vollqualifizierter Domänenname (FQDN) des Geräts |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten `DeviceName` und verwendet `Timestamp` werden. |
| `NetworkAdapterName` | Zeichenfolge | Name des Netzwerkadapters |
| `MacAddress` | Zeichenfolge | MAC-Adresse des Netzwerkadapters |
| `NetworkAdapterType` | Zeichenfolge | Netzwerkadaptertyp. Mögliche Werte finden Sie in [dieser Enumeration.](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true) |
| `NetworkAdapterStatus` | Zeichenfolge | Betriebsstatus des Netzwerkadapters. Mögliche Werte finden Sie in [dieser Enumeration.](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true) |
| `TunnelType` | Zeichenfolge | Tunnelingprotokoll, wenn die Schnittstelle zu diesem Zweck verwendet wird, z. B. 6to4, Teredo, ISATAP, PPTP, SSTP und SSH |
| `ConnectedNetworks` | Zeichenfolge | Netzwerke, mit der der Adapter verbunden ist. Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist. |
| `DnsAddresses` | Zeichenfolge | DNS-Serveradressen im JSON-Arrayformat |
| `IPv4Dhcp` | Zeichenfolge | IPv4-Adresse des DHCP-Servers |
| `IPv6Dhcp` | Zeichenfolge | IPv6-Adresse des DHCP-Servers |
| `DefaultGateways` | Zeichenfolge | Standardgatewayadressen im JSON-Arrayformat |
| `IPAddresses` | Zeichenfolge | JSON-Array, das alle dem Adapter zugewiesenen IP-Adressen sowie das entsprechende Subnetzpräfix und den entsprechenden IP-Adressraum enthält, z. B. öffentlich, privat oder link-lokal |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-reference.md)

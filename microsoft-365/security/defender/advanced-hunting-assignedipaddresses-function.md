---
title: AssignedIPAddresses()-Funktion bei der erweiterten Suche nach Microsoft 365 Defender
description: Erfahren Sie, wie Sie die AssignedIPAddresses()-Funktion verwenden, um die neuesten einem Gerät zugewiesenen IP-Adressen zu erhalten.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, FileProfile, Dateiprofil, Funktion, Bereicherung
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3760ff84e6abfbe05d9e4605d64087d0077300e3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063599"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Verwenden Sie `AssignedIPAddresses()` die Funktion in Ihren [erweiterten](advanced-hunting-overview.md) Suchabfragen, um schnell die neuesten IP-Adressen zu erhalten, die einem Gerät zugewiesen wurden. Wenn Sie ein Zeitstempelargument angeben, ruft diese Funktion die neuesten IP-Adressen zum angegebenen Zeitpunkt ab. 

Diese Funktion gibt eine Tabelle mit den folgenden Spalten zurück:

| Spalte | Datentyp | Beschreibung |
|------------|-------------|-------------|
| `Timestamp` | datetime | Die letzte Zeit, zu der das Gerät mithilfe der IP-Adresse beobachtet wurde |
| `IPAddress` | Zeichenfolge | Vom Gerät verwendete IP-Adresse |
| `IPType` | Zeichenfolge | Gibt an, ob es sich bei der IP-Adresse um eine öffentliche oder eine private Adresse handelt. |
| `NetworkAdapterType` | int | Netzwerkadaptertyp, der vom Gerät verwendet wird, dem die IP-Adresse zugewiesen wurde. Mögliche Werte finden Sie in [dieser Enumeration.](/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | Netzwerke, mit denen der Adapter mit der zugewiesenen IP-Adresse verbunden ist. Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist. |

## <a name="syntax"></a>Syntax

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argumente

- **x**– `DeviceId` oder `DeviceName` Wert, der das Gerät identifiziert
- **y**– (datetime)-Wert, der die Funktion anweisen soll, die neuesten zugewiesenen IP-Adressen aus `Timestamp` einem bestimmten Zeitpunkt zu erhalten. Wenn nicht angegeben, gibt die Funktion die neuesten IP-Adressen zurück.

## <a name="examples"></a>Beispiele

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Liste der vor 24 Stunden von einem Gerät verwendeten IP-Adressen erhalten

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Get IP addresses used by a device and find devices communicating with it
Diese Abfrage verwendet die Funktion, um zugewiesene IP-Adressen für das Gerät ( ) an oder vor einem bestimmten Datum `AssignedIPAddresses()` `example-device-name` ( ) zu `example-date` erhalten. Anschließend werden die IP-Adressen verwendet, um Verbindungen mit dem Gerät zu finden, die von anderen Geräten initiiert wurden. 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
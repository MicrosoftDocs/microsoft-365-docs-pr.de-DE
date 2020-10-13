---
title: AssignedIPAddresses ()-Funktion im Advanced Hunting for Microsoft Threat Protection
description: Erfahren Sie, wie Sie die AssignedIPAddresses ()-Funktion verwenden, um die neuesten IP-Adressen abzurufen, die einem Gerät zugewiesen sind.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Datei Profil, Datei Profil, Funktion, Bereicherung
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
ms.openlocfilehash: 462a4884e2b17f9ae75ea3bdc1531b180dcc5934
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430127"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Verwenden Sie die `AssignedIPAddresses()` -Funktion in Ihren [erweiterten](advanced-hunting-overview.md) Suchabfragen, um schnell die neuesten IP-Adressen zu erhalten, die einem Gerät zugewiesen wurden. Wenn Sie ein Timestamp-Argument angeben, ruft diese Funktion die neuesten IP-Adressen zur angegebenen Zeit ab. 

Diese Funktion gibt eine Tabelle mit den folgenden Spalten zurück:

| Spalte | Datentyp | Beschreibung |
|------------|-------------|-------------|
| `Timestamp` | datetime | Spätester Zeitpunkt, zu dem das Gerät mit der IP-Adresse beobachtet wurde |
| `IPAddress` | string | Vom Gerät verwendete IP-Adresse |
| `IPType` | string | Gibt an, ob es sich bei der IP-Adresse um eine öffentliche oder private Adresse handelt. |
| `NetworkAdapterType` | int | Netzwerkadaptertyp, der von dem Gerät verwendet wird, dem die IP-Adresse zugewiesen wurde. Informationen zu den möglichen Werten finden Sie in [dieser Aufzählung](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | Netzwerke, mit denen der Adapter mit der zugewiesenen IP-Adresse verbunden ist. Jedes JSON-Array enthält den Netzwerknamen, die Kategorie (öffentlich, privat oder Domäne), eine Beschreibung und ein Flag, das angibt, ob es öffentlich mit dem Internet verbunden ist. |

## <a name="syntax"></a>Syntax

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argumente

- **x**– `DeviceId` oder `DeviceName` Wert, der das Gerät identifiziert
- **y**– `Timestamp` (DateTime)-Wert, in dem die Funktion angewiesen wird, die aktuellsten zugewiesenen IP-Adressen von einem bestimmten Zeitpunkt zu erhalten. Wenn nicht angegeben, gibt die Funktion die neuesten IP-Adressen zurück.

## <a name="examples"></a>Beispiele

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Abrufen der Liste der IP-Adressen, die von einem Gerät verwendet werden vor 24 Stunden

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Abrufen von von einem Gerät verwendeten IP-Adressen und Auffinden von Geräten, die mit dieser kommunizieren
Diese Abfrage verwendet die `AssignedIPAddresses()` -Funktion, um zugewiesene IP-Adressen für das Gerät ( `example-device-name` ) an oder vor einem bestimmten Datum ( `example-date` ) abzurufen. Anschließend werden die IP-Adressen verwendet, um Verbindungen mit dem Gerät zu finden, das von anderen Geräten initiiert wurde. 

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

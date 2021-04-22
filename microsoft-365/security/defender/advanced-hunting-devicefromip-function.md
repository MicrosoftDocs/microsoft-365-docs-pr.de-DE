---
title: DeviceFromIP()-Funktion bei der erweiterten Suche nach Microsoft 365 Defender
description: Erfahren Sie, wie Sie die DeviceFromIP()-Funktion verwenden, um die Geräte zu erhalten, denen eine bestimmte IP-Adresse zugewiesen wurde.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, device, devicefromIP, function, enrichment
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
ms.openlocfilehash: 3ea951e35555721a989001b2a5235df5b89a8a55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933181"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Verwenden Sie `DeviceFromIP()` die Funktion in Ihren [erweiterten](advanced-hunting-overview.md) Suchabfragen, um schnell die Liste der Geräte zu erhalten, die zu einem bestimmten Zeitpunkt einer bestimmten IP-Adresse zugewiesen wurden. 

Diese Funktion gibt eine Tabelle mit den folgenden Spalten zurück:

| Spalte | Datentyp | Beschreibung |
|------------|-------------|-------------|
| `IP` | string | IP-Adresse  |
| `DeviceId` | Zeichenfolge | Eindeutige ID für das Gerät im Dienst |


## <a name="syntax"></a>Syntax

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Argumente

Diese Funktion wird als Teil einer Abfrage aufgerufen.

- **x**– Der erste Parameter ist in der Regel bereits eine Spalte in der Abfrage. In diesem Fall ist es die Spalte namens , die IP-Adresse, für die Eine Liste der Geräte angezeigt werden soll, die `IP` ihr zugewiesen wurden. Es sollte eine lokale IP-Adresse sein. Externe IP-Adressen werden nicht unterstützt.
- **y**– Ein zweiter optionaler Parameter ist der , mit dem die Funktion angewiesen wird, die neuesten zugewiesenen Geräte aus einer `Timestamp` bestimmten Zeit zu erhalten. Wenn nicht angegeben, gibt die Funktion die neuesten verfügbaren Datensätze zurück.

## <a name="example"></a>Beispiel


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>Holen Sie sich die neuesten Geräte, denen bestimmte IP-Adressen zugewiesen wurden

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)

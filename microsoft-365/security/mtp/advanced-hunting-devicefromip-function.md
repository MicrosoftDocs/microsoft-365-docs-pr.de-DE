---
title: DeviceFromIP()-Funktion bei der erweiterten Suche nach Microsoft 365 Defender
description: Erfahren Sie, wie Sie die DeviceFromIP()-Funktion verwenden, um die Geräte zu erhalten, denen eine bestimmte IP-Adresse zugewiesen wurde.
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberbedrohungen, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Gerät, DevicefromIP, Funktion, Anreicherung
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 86373c903252fde4ab71c80a81404428a7366da7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931302"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Verwenden Sie die Funktion in Ihren Abfragen für die erweiterte Suche, um schnell die Liste der Geräte zu erhalten, die zu einem bestimmten Zeitpunkt einer bestimmten `DeviceFromIP()` IP-Adresse [](advanced-hunting-overview.md) zugewiesen wurden. 

Diese Funktion gibt eine Tabelle mit den folgenden Spalten zurück:

| Spalte | Datentyp | Beschreibung |
|------------|-------------|-------------|
| `IP` | string | IP-Adresse  |
| `DeviceId` | string | Eindeutige ID für das Gerät im Dienst |


## <a name="syntax"></a>Syntax

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Argumente

Diese Funktion wird als Teil einer Abfrage aufgerufen.

- **x**– Der erste Parameter ist in der Regel bereits eine Spalte in der Abfrage. In diesem Fall handelt es sich um die Spalte namens "IP-Adresse", für die eine Liste der Geräte angezeigt werden soll, die ihr `IP` zugewiesen wurden. Es sollte eine lokale IP-Adresse sein. Externe IP-Adressen werden nicht unterstützt.
- **y**– Ein zweiter optionaler Parameter ist der , der die Funktion anweisen soll, die neuesten zugewiesenen Geräte aus einem `Timestamp` bestimmten Zeitpunkt zu erhalten. Wenn nicht angegeben, gibt die Funktion die neuesten verfügbaren Datensätze zurück.

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

---
title: DeviceFromIP ()-Funktion in Advanced Hunting for Microsoft 365 Defender
description: Erfahren Sie, wie Sie die DeviceFromIP ()-Funktion verwenden, um die Geräte abzurufen, denen eine bestimmte IP-Adresse zugewiesen wurde.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Gerät, devicefromIP, Funktion, Anreicherung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 65409dd93f3703f1af115178c4cd9fa470fb7497
ms.sourcegitcommit: 25ac2736a66bb72c0d574c3fbde7472ac98d5321
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "49741108"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Verwenden Sie die `DeviceFromIP()` -Funktion in Ihren [erweiterten Jagd](advanced-hunting-overview.md) Abfragen, um schnell eine Liste der Geräte zu erhalten, die zu einem bestimmten Zeitpunkt einer bestimmten IP-Adresse zugewiesen wurden. 

Diese Funktion gibt eine Tabelle mit den folgenden Spalten zurück:

| Spalte | Datentyp | Beschreibung |
|------------|-------------|-------------|
| `IP` | string | IP-Adresse  |
| `DeviceId` | Zeichenfolge | Eindeutiger Bezeichner für das Gerät im Dienst |


## <a name="syntax"></a>Syntax

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Argumente

Diese Funktion wird als Teil einer Abfrage aufgerufen.

- **x**– der erste Parameter ist normalerweise bereits eine Spalte in der Abfrage. In diesem Fall ist dies die Spalte mit dem Namen `IP` , die IP-Adresse, für die Sie eine Liste der Geräte anzeigen möchten, die ihr zugewiesen wurden. Es sollte sich um eine lokale IP-Adresse handeln. Externe IP-Adressen werden nicht unterstützt.
- **y**– ein zweiter optionaler Parameter ist der `Timestamp` , der die Funktion anweist, die zuletzt zugewiesenen Geräte aus einem bestimmten Zeitpunkt zu erhalten. Wenn nicht angegeben, gibt die Funktion die neuesten verfügbaren Datensätze zurück.

## <a name="example"></a>Beispiel


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>Abrufen der neuesten Geräte, denen bestimmte IP-Adressen zugewiesen wurden

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

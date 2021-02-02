---
title: Benennungsänderungen im Microsoft 365 Defender Advanced Hunting-Schema
description: Nachverfolgen und Überprüfen von Namensänderungen in Tabellen und Spalten im Schema für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberbedrohungen, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Daten, Benennungsänderungen, Umbenennen, Microsoft Threat Protection
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
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066869"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Schema der erweiterten Suche – Namensänderungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Das [Schema für die erweiterte Suche](advanced-hunting-schema-tables.md) wird regelmäßig aktualisiert, um neue Tabellen und Spalten hinzuzufügen. In einigen Fällen werden vorhandene Spaltennamen umbenannt oder ersetzt, um die Benutzerfreundlichkeit zu verbessern. In diesem Artikel finden Sie Informationen zu Namensänderungen, die sich auf Ihre Abfragen auswirken könnten.

Namensänderungen werden automatisch auf Abfragen angewendet, die im Security Center gespeichert werden, einschließlich Abfragen, die von benutzerdefinierten Erkennungsregeln verwendet werden. Sie müssen diese Abfragen nicht manuell aktualisieren. Sie müssen jedoch die folgenden Abfragen aktualisieren:
- Abfragen, die mit der API ausgeführt werden
- Abfragen, die an anderer Stelle außerhalb des Sicherheitscenters gespeichert werden

## <a name="december-2020"></a>Dezember 2020

| Tabellenname | Ursprünglicher Spaltenname | Neuer Spaltenname | Änderungsgrund
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | Kundenfeedback |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | Kundenfeedback |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | Kundenfeedback |

## <a name="january-2021"></a>Januar 2021

| Spaltenname | Name des ursprünglichen Werts | Name des neuen Werts | Änderungsgrund
|--|--|--|--|
| `DetectionSource` | MCAS |    Microsoft Cloud App-Sicherheit | Rebranding |
| `DetectionSource` | WindowsDefenderAtp|   EDR| Rebranding |
| `DetectionSource` | WindowsDefenderAv | Antivirus | Rebranding |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | Rebranding |
| `DetectionSource` | CustomerTI |  Benutzerdefinierte TI | Rebranding |
| `DetectionSource` | OfficeATP | Microsoft Defender für Office 365 | Rebranding |
| `DetectionSource` | MTP   | Microsoft 365 Defender | Rebranding |
| `DetectionSource` | AzureATP |    Microsoft Defender for Identity | Rebranding |
| `DetectionSource` | CustomDetection   | Benutzerdefinierte Erkennung | Rebranding |
| `DetectionSource` | AutomatedInvestigation |Automatisierte Untersuchung | Rebranding |
| `DetectionSource` | ThreatExperts | Microsoft-Bedrohungsexperten | Rebranding |
| `DetectionSource` | 3rd party TI | Drittanbietersensoren | Rebranding |
| `ServiceSource` | Microsoft Defender ATP| Microsoft Defender für Endpunkt | Rebranding |
|`ServiceSource` |Microsoft Threat Protection   | Microsoft 365 Defender | Rebranding |
| `ServiceSource` | Office 365 ATP  |Microsoft Defender für Office 365 | Rebranding |
| `ServiceSource` |Azure ATP    |Microsoft Defender for Identity | Rebranding |

`DetectionSource` ist in der Tabelle ["AlertInfo"](advanced-hunting-alertinfo-table.md) verfügbar. `ServiceSource` ist in den [Tabellen "AlertEvidence" und](advanced-hunting-alertevidence-table.md) ["AlertInfo"](advanced-hunting-alertinfo-table.md) verfügbar. 
## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
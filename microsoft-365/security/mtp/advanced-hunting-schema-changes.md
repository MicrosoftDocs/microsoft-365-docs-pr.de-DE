---
title: Namensänderungen im Microsoft 365 Defender Advanced Hunting-Schema
description: Nachverfolgen und Überprüfen von Tabellen und Spalten für Namensänderungen im schema der erweiterten Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Daten, Benennungsänderungen, Umbenennen, Microsoft Threat Protection
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
ms.openlocfilehash: cd06286083297d0930270868b99a14f8ddb2f4b2
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461667"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Schema der erweiterten Suche – Benennungsänderungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Das [schema der erweiterten](advanced-hunting-schema-tables.md) Suche wird regelmäßig aktualisiert, um neue Tabellen und Spalten hinzuzufügen. In einigen Fällen werden vorhandene Spaltennamen umbenannt oder ersetzt, um die Benutzerfreundlichkeit zu verbessern. Lesen Sie diesen Artikel, um Namensänderungen zu überprüfen, die sich auf Ihre Abfragen auswirken könnten.

Namensänderungen werden automatisch auf Abfragen angewendet, die im Security Center gespeichert werden, einschließlich Abfragen, die von benutzerdefinierten Erkennungsregeln verwendet werden. Sie müssen diese Abfragen nicht manuell aktualisieren. Sie müssen jedoch die folgenden Abfragen aktualisieren:
- Abfragen, die mithilfe der API ausgeführt werden
- Abfragen, die an anderer Stelle außerhalb des Sicherheitscenters gespeichert werden

## <a name="december-2020"></a>Dezember 2020

| Tabellenname | Ursprünglicher Spaltenname | Neuer Spaltenname | Änderungsgrund
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | Kundenfeedback |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | Kundenfeedback |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | Kundenfeedback |

## <a name="january-2021"></a>Januar 2021

| Spaltenname | Ursprünglicher Wertname | Name des neuen Werts | Änderungsgrund
|--|--|--|--|
| `DetectionSource` | MCAS |    Microsoft Cloud App Security | Rebranding |
| `DetectionSource` | WindowsDefenderAtp|   EDR| Rebranding |
| `DetectionSource` | WindowsDefenderAv | Antivirus | Rebranding |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | Rebranding |
| `DetectionSource` | CustomerTI |  Benutzerdefiniertes TI | Rebranding |
| `DetectionSource` | OfficeATP | Microsoft Defender für Office 365 | Rebranding |
| `DetectionSource` | MTP   | Microsoft 365 Defender | Rebranding |
| `DetectionSource` | AzureATP |    Microsoft Defender for Identity | Rebranding |
| `DetectionSource` | CustomDetection   | Benutzerdefinierte Erkennung | Rebranding |
| `DetectionSource` | AutomatedInvestigation |Automatisierte Untersuchung | Rebranding |
| `DetectionSource` | ThreatExperts | Microsoft-Bedrohungsexperten | Rebranding |
| `DetectionSource` | 3rd Party TI | Sensoren von Drittanbietern | Rebranding |
| `ServiceSource` | Microsoft Defender ATP| Microsoft Defender für Endpunkt | Rebranding |
|`ServiceSource` |Microsoft Threat Protection   | Microsoft 365 Defender | Rebranding |
| `ServiceSource` | Office 365 ATP  |Microsoft Defender für Office 365 | Rebranding |
| `ServiceSource` |Azure ATP    |Microsoft Defender for Identity | Rebranding |

`DetectionSource` ist in der [AlertInfo-Tabelle](advanced-hunting-alertinfo-table.md) verfügbar. `ServiceSource` ist in den [Tabellen AlertEvidence](advanced-hunting-alertevidence-table.md) und [AlertInfo](advanced-hunting-alertinfo-table.md) verfügbar. 

## <a name="february-2021"></a>Februar 2021

1. In den [Tabellen EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) und [EmailEvents](advanced-hunting-emailevents-table.md) haben wir die Spalten und veraltet und durch `MalwareFilterVerdict` die Spalte `PhishFilterVerdict` `ThreatTypes` ersetzt. Außerdem haben wir die Spalten und veraltet und `MalwareDetectionMethod` `PhishDetectionMethod` durch die Spalte `DetectionMethods` ersetzt. Diese Optimierung ermöglicht es uns, weitere Informationen unter den neuen Spalten zur Verfügung zu stellen. Die Zuordnung wird unten bereitgestellt.

| Tabellenname | Ursprünglicher Spaltenname | Neuer Spaltenname | Änderungsgrund
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Fügen Sie weitere Erkennungsmethoden ein |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Weitere Bedrohungstypen enthalten |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Fügen Sie weitere Erkennungsmethoden ein |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Weitere Bedrohungstypen enthalten |


2. In den `EmailAttachmentInfo` Tabellen und haben wir die Spalte hinzugefügt, um weitere Informationen zur E-Mail-Bedrohung `EmailEvents` zu `ThreatNames` erhalten. Diese Spalte enthält Werte wie Spam oder Phish.

3. In der [DeviceInfo-Tabelle](advanced-hunting-deviceinfo-table.md) haben wir die Spalte durch basierend auf `DeviceObjectId` `AadDeviceId` Kundenfeedback ersetzt.

4. In der [DeviceEvents-Tabelle](advanced-hunting-deviceevents-table.md) haben wir mehrere ActionType-Namen aktualisiert, um die Beschreibung der Aktion besser widerspiegeln zu können. Details finden Sie unten.

| Tabellenname | Ursprünglicher ActionType-Name | Neuer ActionType-Name | Änderungsgrund
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | Kundenfeedback |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | Kundenfeedback |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | Kundenfeedback |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | Kundenfeedback |
| `DeviceEvents` | `AntivirusDetection` | `EdrBlock` | Kundenfeedback |





## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
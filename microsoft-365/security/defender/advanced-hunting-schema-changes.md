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
ms.openlocfilehash: ab6bdefb457fb31df98d829ee801b72f4c8ae70a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499690"
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

1. In den [Tabellen EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) und [EmailEvents](advanced-hunting-emailevents-table.md) wurden die `MalwareFilterVerdict` Spalten und durch die Spalte `PhishFilterVerdict` `ThreatTypes` ersetzt. Die `MalwareDetectionMethod` Spalten und wurden auch durch die Spalte `PhishDetectionMethod` `DetectionMethods` ersetzt. Diese Optimierung ermöglicht es uns, weitere Informationen unter den neuen Spalten zur Verfügung zu stellen. Die Zuordnung wird unten bereitgestellt.

| Tabellenname | Ursprünglicher Spaltenname | Neuer Spaltenname | Änderungsgrund
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Fügen Sie weitere Erkennungsmethoden ein |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Weitere Bedrohungstypen enthalten |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Fügen Sie weitere Erkennungsmethoden ein |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Weitere Bedrohungstypen enthalten |


2. In den Tabellen und wurde die Spalte hinzugefügt, um weitere Informationen zur E-Mail-Bedrohung `EmailAttachmentInfo` `EmailEvents` zu `ThreatNames` erhalten. Diese Spalte enthält Werte wie Spam oder Phish.

3. In der [DeviceInfo-Tabelle](advanced-hunting-deviceinfo-table.md) wurde die Spalte basierend auf Kundenfeedback durch `DeviceObjectId` die Spalte `AadDeviceId` ersetzt.

4. In der [DeviceEvents-Tabelle](advanced-hunting-deviceevents-table.md) wurden mehrere ActionType-Namen geändert, um die Beschreibung der Aktion besser widerspiegeln zu können. Details zu den Änderungen finden Sie unten.

| Tabellenname | Ursprünglicher ActionType-Name | Neuer ActionType-Name | Änderungsgrund
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | Kundenfeedback |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | Kundenfeedback |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | Kundenfeedback |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | Kundenfeedback |






## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
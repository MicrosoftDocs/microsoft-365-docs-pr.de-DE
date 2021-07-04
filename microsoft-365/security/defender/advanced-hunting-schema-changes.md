---
title: Namensänderungen im Schema für die erweiterte Suche Microsoft 365 Defender
description: Nachverfolgen und Überprüfen von Namensänderungen in Tabellen und Spalten im Schema für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyber-Bedrohungssuche, Microsoft 365 Defender, Microsoft 365, m365, Suche, Abfrage, Telemetrie, Schemareferenz, kusto, Tabelle, Daten, Namensänderungen, umbenennen
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
ms.openlocfilehash: 9406653a2d16c83f974e2a0ce7597b5c4f833252
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289493"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Schema für erweiterte Suche – Namensänderungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Das Schema für [die erweiterte Suche](advanced-hunting-schema-tables.md) wird regelmäßig aktualisiert, um neue Tabellen und Spalten hinzuzufügen. In einigen Fällen werden vorhandene Spaltennamen umbenannt oder ersetzt, um die Benutzererfahrung zu verbessern. Informationen zu Namensänderungen, die sich auf Ihre Abfragen auswirken könnten, finden Sie in diesem Artikel.

Namensänderungen werden automatisch auf Abfragen angewendet, die im Sicherheitscenter gespeichert werden, einschließlich Abfragen, die von benutzerdefinierten Erkennungsregeln verwendet werden. Sie müssen diese Abfragen nicht manuell aktualisieren. Sie müssen jedoch die folgenden Abfragen aktualisieren:
- Abfragen, die mithilfe der API ausgeführt werden
- Abfragen, die an anderer Stelle außerhalb des Sicherheitscenters gespeichert werden

## <a name="december-2020"></a>Dezember 2020

| Tabellenname | Ursprünglicher Spaltenname | Neuer Spaltenname | Grund für Änderungen
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | Kundenfeedback |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | Kundenfeedback |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | Kundenfeedback |

## <a name="january-2021"></a>Januar 2021

| Spaltenname | Name des ursprünglichen Werts | Neuer Wertname | Grund für Änderungen
|--|--|--|--|
| `DetectionSource` | MCAS | Microsoft Cloud App Security | Rebranding |
| `DetectionSource` | WindowsDefenderAtp| EDR| Rebranding |
| `DetectionSource` | WindowsDefenderAv | Antivirus | Rebranding |
| `DetectionSource` | WindowsDefenderSmartScreen |  Smartscreen | Rebranding |
| `DetectionSource` | CustomerTI | Benutzerdefinierte TI | Rebranding |
| `DetectionSource` | OfficeATP | Microsoft Defender für Office 365 | Rebranding |
| `DetectionSource` | Mtp | Microsoft 365 Defender | Rebranding |
| `DetectionSource` | AzureATP | Microsoft Defender for Identity | Rebranding |
| `DetectionSource` | CustomDetection | Benutzerdefinierte Erkennung | Rebranding |
| `DetectionSource` | AutomatedInvestigation |Automatisierte Untersuchung | Rebranding |
| `DetectionSource` | ThreatExperts | Microsoft-Bedrohungsexperten | Rebranding |
| `DetectionSource` | TI von Drittanbietern | Sensoren von Drittanbietern | Rebranding |
| `ServiceSource` | Microsoft Defender ATP| Microsoft Defender für Endpunkt | Rebranding |
|`ServiceSource` |Microsoft Threat Protection | Microsoft 365 Defender | Rebranding |
| `ServiceSource` | Office 365 ATP |Microsoft Defender für Office 365 | Rebranding |
| `ServiceSource` |Azure ATP |Microsoft Defender for Identity | Rebranding |

`DetectionSource` ist in der [AlertInfo-Tabelle](advanced-hunting-alertinfo-table.md) verfügbar. `ServiceSource` ist in den [Tabellen AlertEvidence ](advanced-hunting-alertevidence-table.md) und [ AlertInfo ](advanced-hunting-alertinfo-table.md) verfügbar. 

## <a name="february-2021"></a>Februar 2021

1. In den Tabellen [ EmailAttachmentInfo ](advanced-hunting-emailattachmentinfo-table.md) und EmailEvents wurden die Spalten durch die Spalte [](advanced-hunting-emailevents-table.md) `MalwareFilterVerdict` `PhishFilterVerdict` `ThreatTypes` ersetzt. Die Spalten und spalten `MalwareDetectionMethod` wurden auch durch die Spalte `PhishDetectionMethod` `DetectionMethods` ersetzt. Diese Bereinigung ermöglicht es uns, weitere Informationen unter den neuen Spalten bereitzustellen. Die Zuordnung wird unten bereitgestellt.

    | Tabellenname | Ursprünglicher Spaltenname | Neuer Spaltenname | Grund für Änderungen
    |--|--|--|--|
    | `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Weitere Erkennungsmethoden einschließen |
    | `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Einschließen weiterer Bedrohungstypen |
    | `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Weitere Erkennungsmethoden einschließen |
    | `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Einschließen weiterer Bedrohungstypen |


2. In den `EmailAttachmentInfo` Tabellen wurde die Spalte `EmailEvents` `ThreatNames` hinzugefügt, um weitere Informationen zur E-Mail-Bedrohung zu erhalten. Diese Spalte enthält Werte wie Spam oder Phishing.

3. In der [DeviceInfo-Tabelle](advanced-hunting-deviceinfo-table.md) wurde die `DeviceObjectId` Spalte basierend auf dem Kundenfeedback durch die Spalte `AadDeviceId` ersetzt.

4. In der [DeviceEvents-Tabelle](advanced-hunting-deviceevents-table.md) wurden mehrere ActionType-Namen geändert, um die Beschreibung der Aktion besser widerzuspiegeln. Details zu den Änderungen finden Sie unten.

    | Tabellenname | Ursprünglicher ActionType-Name | Neuer ActionType-Name | Grund für Änderungen
    |--|--|--|--|
    | `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | Kundenfeedback |
    | `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | Kundenfeedback |
    | `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | Kundenfeedback |
    | `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | Kundenfeedback |

## <a name="march-2021"></a>März 2021

Die `DeviceTvmSoftwareInventoryVulnerabilities` Tabelle ist veraltet. Ersetzen Sie sie durch die `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` Und-Tabellen.

## <a name="may-2021"></a>Mai 2021

Die `AppFileEvents` Tabelle ist veraltet. Die Tabelle enthält Informationen, die früher in der Tabelle enthalten `CloudAppEvents` `AppFileEvents` waren, zusammen mit anderen Aktivitäten in Clouddiensten.

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
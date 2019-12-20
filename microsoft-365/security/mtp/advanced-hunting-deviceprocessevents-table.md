---
title: DeviceProcessEvents-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über das Prozess Laichen oder Erstellen von Ereignissen in der DeviceProcessEventstable des Advanced Hunting-Schemas.
keywords: Erweiterte Jagd, Bedrohungs Jagd, Cyber Threat Hunting, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, processcreationevents, DeviceProcessEvents, Prozess-ID, Befehlszeile, DeviceProcessEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4e7899d06d9107ed5fdbaf67d507ed69a034329b
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809303"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

**Gilt für:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Die `DeviceProcessEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zur Prozesserstellung und zu verwandten Ereignissen. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FolderPath` | string | Ordner mit der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA256` | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde. Dieses Feld wird in der Regel nicht aufgefüllt, wenn es verfügbar ist, verwenden Sie die SHA1-Spalte. |
| `MD5` | string | MD5-Hash der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `ProcessId` | int | Prozess-ID (PID) des neu erstellten Prozesses |
| `ProcessCommandLine` | string | Befehlszeile, die zum Erstellen des neuen Prozesses verwendet wird |
| `ProcessIntegrityLevel` | string | Integritätsstufe des neu erstellten Prozesses. Windows weist Prozessen auf der Grundlage bestimmter Merkmale Integritätsstufen zu, beispielsweise, wenn Sie von einem heruntergeladenen Internet gestartet wurden. Diese Integritätsstufen beeinflussen Berechtigungen für Ressourcen |
| `ProcessTokenElevation` | string | Tokentyp, der angibt, dass die Benutzerzugriffssteuerung (UAC) auf den neu erstellten Prozess angewendet wird oder nicht vorhanden ist |
| `ProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit der Erstellung des Prozesses |
| `AccountDomain` | string | Domäne des Kontos |
| `AccountName` | string | Benutzername des Kontos |
| `AccountSid` | string | Sicherheits-ID (SID) des Kontos |
| `LogonId` | string | Bezeichner für eine Anmeldesitzung. Dieser Bezeichner ist auf demselben Computer nur zwischen Neustarts eindeutig. |
| `InitiatingProcessAccountDomain` | string | Domäne des Kontos, das den für das Ereignis verantwortlichen Prozess ausgeführt hat |
| `InitiatingProcessAccountName` | string | Benutzername des Kontos, das den für das Ereignis verantwortlichen Prozess ausgeführt hat |
| `InitiatingProcessAccountSid` | string | Sicherheits-ID (SID) des Kontos, das den für das Ereignis verantwortlichen Prozess ausgeführt hat |
| `InitiatingProcessLogonId` | string | Bezeichner für eine Anmeldesitzung des Prozesses, der das Ereignis initiiert hat. Dieser Bezeichner ist auf demselben Computer nur zwischen Neustarts eindeutig. |
| `InitiatingProcessIntegrityLevel` | string | Integritätsstufe des Prozesses, der das Ereignis initiiert hat. Windows weist Prozessen auf der Grundlage bestimmter Merkmale Integritätsstufen zu, beispielsweise, wenn Sie von einem Internet Download aus gestartet wurden. Diese Integritätsstufen beeinflussen Berechtigungen für Ressourcen |
| `InitiatingProcessTokenElevation` | string | Tokentyp, der angibt, dass die Rechteerweiterung "Benutzerzugriffssteuerung" (UAC) auf den Prozess angewendet wird, der das Ereignis initiiert hat |
| `InitiatingProcessSHA1` | string | SHA-1 des Prozesses (Image-Datei), der das Ereignis initiiert hat |
| `InitiatingProcessSHA256` | string | SHA-256 des Prozesses (Image-Datei), der das Ereignis initiiert hat. Dieses Feld wird in der Regel nicht aufgefüllt – verwenden Sie die Spalte SHA1, wenn verfügbar. |
| `InitiatingProcessMD5` | string | MD5-Hash des Prozesses (Image-Datei), der das Ereignis initiiert hat |
| `InitiatingProcessFileName` | string | Name des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessId` | int | Prozess-ID (PID) des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCommandLine` | string | Befehlszeile, die zum Ausführen des Prozesses verwendet wird, der das Ereignis initiiert hat |
| `InitiatingProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit des Starts des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessFolderPath` | string | Ordner mit dem Prozess (Image-Datei), der das Ereignis initiiert hat |
| `InitiatingProcessParentId` | int | Prozess-ID (PID) des übergeordneten Prozesses, der den für das Ereignis verantwortlichen Prozess hervorgerufen hat |
| `InitiatingProcessParentFileName` | string | Name des übergeordneten Prozesses, der den für das Ereignis verantwortlichen Prozess hervorgerufen hat |
| `InitiatingProcessParentCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu denen das übergeordnete Element des für das Ereignis Verantwortlichen Prozesses gestartet wurde. |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte zusammen mit den Gerätename-und timestamp-Spalten verwendet werden. |
| `AppGuardContainerId` | string | Bezeichner für den virtualisierten Container, der von Application Guard zum Isolieren von Browseraktivitäten verwendet wird |

## <a name="related-topics"></a>Verwandte Themen
- [Vorbeugende Suche nach Bedrohungen](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche nach Bedrohungen auf Geräten und in E-Mails](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

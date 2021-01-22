---
title: Tabelle "DeviceRegistryEvents" im Schema "Erweiterte Suche"
description: Informationen zu Registrierungsereignissen, die Sie in der Tabelle "DeviceRegistryEvents" des Schemas für die erweiterte Suche abfragen können
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Registryevents, Registrierung, DeviceRegistryEvents, Schlüssel, Unterschlüssel, Wert
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
ms.openlocfilehash: 376e54fb4bf5f07a1c821ff436ddc8ec7dd25812
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931110"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die `DeviceRegistryEvents` Tabelle im Schema für die erweiterte [Suche](advanced-hunting-overview.md) enthält Informationen zum Erstellen und Ändern von Registrierungseinträgen. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den Ereignistypen (Werten), die von einer Tabelle unterstützt werden, finden Sie in der integrierten Schemareferenz, die im `ActionType` Security Center verfügbar ist. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. Weitere Informationen [finden Sie in der In-Portal-Schemareferenz.](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `RegistryKey` | string | Registrierungsschlüssel, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueType` | string | Datentyp, z. B. Binärdatei oder Zeichenfolge, des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueName` | string | Name des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueData` | string | Daten des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `PreviousRegistryValueName` | string | Ursprünglicher Name des Registrierungswerts, bevor er geändert wurde |
| `PreviousRegistryValueData` | string | Ursprüngliche Daten des Registrierungswerts, bevor er geändert wurde |
| `InitiatingProcessAccountDomain` | string | Domäne des Kontos, das den für das Ereignis verantwortlichen Prozess verwendet hat |
| `InitiatingProcessAccountName` | string | Benutzername des Kontos, das den für das Ereignis verantwortlichen Prozess verwendet hat |
| `InitiatingProcessAccountSid` | string | Sicherheits-ID (SID) des Kontos, das den für das Ereignis verantwortlichen Prozess verwendet hat |
| `InitiatingProcessSHA1` | string | SHA-1 des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessSHA256` | string | SHA-256 des Prozesses (Bilddatei), der das Ereignis initiiert hat. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `InitiatingProcessMD5` | string | #A0 des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessFileName` | string | Name des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessId` | int | Prozess-ID (PID) des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCommandLine` | string | Befehlszeile zum Ausführen des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, an dem der Prozess, der das Ereignis initiiert hat, gestartet wurde |
| `InitiatingProcessFolderPath` | string | Ordner, der den Prozess (Bilddatei) enthält, der das Ereignis initiiert hat |
| `InitiatingProcessParentId` | int | Prozess-ID (PID) des übergeordneten Prozesses, der den für das Ereignis verantwortlichen Prozess aussing |
| `InitiatingProcessParentFileName` | string | Name des übergeordneten Prozesses, der den für das Ereignis verantwortlichen Prozess aussing |
| `InitiatingProcessParentCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, an dem das übergeordnete Element des für das Ereignis verantwortlichen Prozesses gestartet wurde |
| `InitiatingProcessIntegrityLevel` | string | Integritätsstufe des Prozesses, der das Ereignis initiiert hat. Windows weist Prozesse Integritätsstufen basierend auf bestimmten Merkmalen zu, z. B. wenn sie über einen Internetdownload gestartet wurden. Diese Integritätsstufen beeinflussen Berechtigungen für Ressourcen |
| `InitiatingProcessTokenElevation` | string | Tokentyp, der angibt, ob die Rechteerweiterung der Benutzerzugriffssteuerung (User Access Control, UAC) auf den Prozess angewendet wurde, der das Ereignis initiiert hat. |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten "DeviceName" und "Timestamp" verwendet werden. |
| `AppGuardContainerId` | string | Bezeichner für den virtualisierten Container, der von Application Guard zum Isolieren der Browseraktivität verwendet wird |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

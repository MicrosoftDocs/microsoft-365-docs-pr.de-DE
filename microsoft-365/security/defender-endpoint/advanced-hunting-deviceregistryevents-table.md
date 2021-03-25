---
title: DeviceRegistryEvents-Tabelle im schema der erweiterten Suche
description: Informationen zu Registrierungsereignissen, die Sie in der DeviceRegistryEvents-Tabelle des erweiterten Suchschemas abfragen können
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, search, query, telemetry, schema reference, kusto, table, column, data type, deviceregistryevents, registry, key, subkey, value, RegistryEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 39ea04e2faa43d230ecdc281967b6a9e8f8c9abe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067015"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Die `DeviceRegistryEvents` Tabelle im Schema der erweiterten [Suche](advanced-hunting-overview.md) enthält Informationen zum Erstellen und Ändern von Registrierungseinträgen. Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.

Weitere Informationen zu anderen Tabellen im Schema für die erweiterte Suche finden Sie in der [Schemareferenz](advanced-hunting-schema-reference.md)für erweiterte Suche .

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutige ID für das Gerät im Dienst |
| `DeviceName` | Zeichenfolge | Vollqualifizierter Domänenname (FQDN) des Geräts |
| `ActionType` | Zeichenfolge | Typ der Aktivität, die das Ereignis ausgelöst hat |
| `RegistryKey` | Zeichenfolge | Registrierungsschlüssel, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueType` | Zeichenfolge | Datentyp, z. B. Binärdatei oder Zeichenfolge, des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueName` | Zeichenfolge | Name des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueData` | Zeichenfolge | Daten des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `PreviousRegistryValueName` | Zeichenfolge | Ursprünglicher Name des Registrierungswerts, bevor er geändert wurde |
| `PreviousRegistryValueData` | Zeichenfolge | Ursprüngliche Daten des Registrierungswerts vor der Änderung |
| `InitiatingProcessAccountDomain` | Zeichenfolge | Domäne des Kontos, mit dem der Prozess für das Ereignis verantwortlich war |
| `InitiatingProcessAccountName` | Zeichenfolge | Benutzername des Kontos, das den prozess für das Ereignis verantwortlich führte |
| `InitiatingProcessAccountSid` | Zeichenfolge | Security Identifier (SID) des Kontos, das den für das Ereignis verantwortlichen Prozess führte |
| `InitiatingProcessSHA1` | Zeichenfolge | SHA-1 des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessMD5` | Zeichenfolge | MD5-Hash des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessFileName` | Zeichenfolge | Name des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessId` | int | Prozess-ID (PID) des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCommandLine` | Zeichenfolge | Befehlszeile zum Ausführen des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu dem der Prozess gestartet wurde, der das Ereignis initiiert hat |
| `InitiatingProcessFolderPath` | Zeichenfolge | Ordner mit dem Prozess (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessParentId` | int | Prozess-ID (PID) des übergeordneten Prozesses, der den prozess, der für das Ereignis verantwortlich war, |
| `InitiatingProcessParentFileName` | Zeichenfolge | Name des übergeordneten Prozesses, der den prozessverantwortlichen Prozess für das Ereignis gezeitet hat |
| `InitiatingProcessParentCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu der das übergeordnete Element des für das Ereignis verantwortlichen Prozesses gestartet wurde |
| `InitiatingProcessIntegrityLevel` | Zeichenfolge | Integritätsebene des Prozesses, der das Ereignis initiiert hat. Windows weist Prozesse Integritätsstufen basierend auf bestimmten Merkmalen zu, z. B. wenn sie über einen Internetdownload gestartet wurden. Diese Integritätsstufen beeinflussen Berechtigungen für Ressourcen |
| `InitiatingProcessTokenElevation` | Zeichenfolge | Tokentyp, der angibt, ob die Berechtigungserweiterung für die Benutzerzugriffssteuerung (User Access Control, UAC) auf den Prozess angewendet wurde, der das Ereignis initiiert hat |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten `DeviceName` und verwendet `Timestamp` werden. |
| `AppGuardContainerId` | Zeichenfolge | Id für den virtualisierten Container, der von Application Guard zum Isolieren von Browseraktivitäten verwendet wird |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-reference.md)

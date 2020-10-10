---
title: DeviceFileEvents-Tabelle im Advanced Hunting-Schema
description: Informationen zu dateibezogenen Ereignissen in der DeviceFileEvents-Tabelle des Advanced Hunting-Schemas
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, filecreationevents, DeviceFileEvents, Dateien, Pfad, Hash, SHA1, SHA256, MD5
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 2d1b8e871a4139a4e025313fe1bda724e87c9b6d
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412214"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Die `DeviceFileEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Datei Erstellungs-, Änderungs-und anderen Dateisystemereignissen. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den `ActionType` von einer Tabelle unterstützten Ereignistypen (Values) finden Sie in der [integrierten Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) , die im Sicherheitscenter verfügbar ist.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. Details finden Sie [in der in-Portal-Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) . |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FolderPath` | string | Ordner mit der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA256` | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `MD5` | string | MD5-Hash der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FileOriginUrl` | string | URL, von der die Datei heruntergeladen wurde |
| `FileOriginReferrerUrl` | string | URL der Webseite, die mit der heruntergeladenen Datei verknüpft ist |
| `FileOriginIP` | string | IP-Adresse, von der die Datei heruntergeladen wurde |
| `InitiatingProcessAccountDomain` | string | Domäne des Kontos, das den für das Ereignis verantwortlichen Prozess ausgeführt hat |
| `InitiatingProcessAccountName` | string | Benutzername des Kontos, das den für das Ereignis verantwortlichen Prozess ausgeführt hat |
| `InitiatingProcessAccountSid` | string | Sicherheits-ID (SID) des Kontos, das den für das Ereignis verantwortlichen Prozess ausgeführt hat |
| `InitiatingProcessMD5` | string | MD5-Hash des Prozesses (Image-Datei), der das Ereignis initiiert hat |
| `InitiatingProcessSHA1` | string | SHA-1 des Prozesses (Image-Datei), der das Ereignis initiiert hat |
| `InitiatingProcessSHA256` | string | SHA-256 des Prozesses (Image-Datei), der das Ereignis initiiert hat. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `InitiatingProcessFolderPath` | string | Ordner mit dem Prozess (Image-Datei), der das Ereignis initiiert hat |
| `InitiatingProcessFileName` | string | Name des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessId` | int | Prozess-ID (PID) des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCommandLine` | string | Befehlszeile, die zum Ausführen des Prozesses verwendet wird, der das Ereignis initiiert hat |
| `InitiatingProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit des Starts des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessIntegrityLevel` | string | Integritätsstufe des Prozesses, der das Ereignis initiiert hat. Windows weist Prozessen auf der Grundlage bestimmter Merkmale Integritätsstufen zu, beispielsweise, wenn Sie von einem Internet Download aus gestartet wurden. Diese Integritätsstufen beeinflussen Berechtigungen für Ressourcen |
| `InitiatingProcessTokenElevation` | string | Tokentyp, der angibt, dass die Rechteerweiterung "Benutzerzugriffssteuerung" (UAC) auf den Prozess angewendet wird, der das Ereignis initiiert hat |
| `InitiatingProcessParentId` | int | Prozess-ID (PID) des übergeordneten Prozesses, der den für das Ereignis verantwortlichen Prozess hervorgerufen hat |
| `InitiatingProcessParentFileName` | string | Name des übergeordneten Prozesses, der den für das Ereignis verantwortlichen Prozess hervorgerufen hat |
| `InitiatingProcessParentCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu denen das übergeordnete Element des für das Ereignis Verantwortlichen Prozesses gestartet wurde. |
| `RequestProtocol` | string | Gegebenenfalls verwendetes Netzwerkprotokoll zum Initiieren der Aktivität: unbekannt, lokal, SMB oder NFS |
| `ShareName` | string | Name des freigegebenen Ordners, der die Datei enthält |
| `RequestSourceIP` | string | IPv4-oder IPv6-Adresse des Remotegeräts, das die Aktivität initiiert hat |
| `RequestSourcePort` | string | Quell Port auf dem Remotegerät, das die Aktivität initiiert hat |
| `RequestAccountName` | string | Benutzername des Kontos, das zum Remote Initiieren der Aktivität verwendet wurde |
| `RequestAccountDomain` | string | Domäne des Kontos, das zum Remote Initiieren der Aktivität verwendet wurde |
| `RequestAccountSid` | string | Sicherheits-ID (SID) des Kontos, das zum Remote Initiieren der Aktivität verwendet wurde |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte zusammen mit den Gerätename-und timestamp-Spalten verwendet werden. |
| `AppGuardContainerId` | string | Bezeichner für den virtualisierten Container, der von Application Guard zum Isolieren von Browseraktivitäten verwendet wird |
| `SensitivityLabel` | string | Bezeichnung, die auf eine e-Mail, Datei oder andere Inhalte angewendet wird, um Sie für den Schutz von Informationen zu klassifizieren |
| `SensitivitySubLabel` | string | Unter Bezeichnung, die auf eine e-Mail, Datei oder andere Inhalte angewendet wird, um Sie für den Schutz von Informationen zu klassifizieren; Sensitivitäts-Sublabel werden unter Sensitivitäts Bezeichnungen gruppiert, jedoch unabhängig voneinander behandelt. |
| `IsAzureInfoProtectionApplied` | Boolescher Wert | Gibt an, ob die Datei durch Azure Information Protection verschlüsselt wird. |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suchen auf Geräten, in E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

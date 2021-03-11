---
title: DeviceEvents-Tabelle im schema der erweiterten Suche
description: Informationen zu Antivirus, Firewall und anderen Ereignistypen finden Sie in der Tabelle verschiedene Geräteereignisse (DeviceEvents) des schemas für die erweiterte Suche.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, security events, antivirus, firewall, exploit guard, DeviceEvents
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
ms.openlocfilehash: 02e0caed602ffa14a756f0cc8e695fc9fb953efc
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712474"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Die verschiedenen Geräteereignisse oder -tabellen im Schema für die erweiterte Suche enthalten Informationen zu verschiedenen Ereignistypen, einschließlich Ereignissen, die durch Sicherheitssteuerelemente ausgelöst werden, z. B. Windows Defender Antivirus- und `DeviceEvents` Exploitschutz. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den von einer Tabelle unterstützten Ereignistypen ( Werte) finden Sie unter Verwendung der integrierten Schemareferenz, die `ActionType` im Security Center verfügbar ist.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).


| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. Weitere Informationen [finden Sie in der In-Portal-Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FolderPath` | string | Ordner, der die Datei enthält, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA256` | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `MD5` | string | MD5-Hash der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `AccountDomain` | string | Domäne des Kontos |
| `AccountName` | string | Benutzername des Kontos |
| `AccountSid` | string | Security Identifier (SID) des Kontos |
| `RemoteUrl` | string | URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde |
| `RemoteDeviceName` | string | Name des Computers, der einen Remotevorgang auf dem betroffenen Computer ausgeführt hat. Je nach gemeldeten Ereignis kann es sich bei diesem Namen um einen vollqualifizierten Domänennamen (FQDN), einen NetBIOS-Namen oder einen Hostnamen ohne Domäneninformationen geben. |
| `ProcessId` | int | Prozess-ID (PID) des neu erstellten Prozesses |
| `ProcessCommandLine` | string | Befehlszeile zum Erstellen des neuen Prozesses |
| `ProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu der der Prozess erstellt wurde |
| `ProcessTokenElevation` | string | Tokentyp, der angibt, ob die Berechtigungserweiterung der Benutzerzugriffssteuerung (User Access Control, UAC) auf den neu erstellten Prozess angewendet wurde oder nicht |
| `LogonId` | string | Bezeichner für eine Anmeldesitzung. Dieser Bezeichner ist auf demselben Computer nur zwischen Neustarts eindeutig |
| `RegistryKey` | string | Registrierungsschlüssel, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueName` | string | Name des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueData` | string | Daten des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `RemoteIP` | string | IP-Adresse, mit der eine Verbindung hergestellt wurde |
| `RemotePort` | int | TCP-Port auf dem Remotegerät, mit dem eine Verbindung hergestellt wurde |
| `LocalIP` | string | IP-Adresse, die dem lokalen Computer zugewiesen ist, der während der Kommunikation verwendet wird |
| `LocalPort` | int | TCP-Port auf dem lokalen Computer, der während der Kommunikation verwendet wird |
| `FileOriginUrl` | string | URL, von der die Datei heruntergeladen wurde |
| `FileOriginIP` | string | IP-Adresse, von der die Datei heruntergeladen wurde |
| `AdditionalFields` | string | Zusätzliche Informationen zum Ereignis im JSON-Arrayformat |
| `InitiatingProcessFileSize` | long | Größe der Datei, die den prozessverantwortlichen Vorgang für das Ereignis führte |
| `FileSize` | long | Größe der Datei in Bytes |
| `InitiatingProcessSHA1` | string | SHA-1 des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessSHA256` | string | SHA-256 des Prozesses (Bilddatei), der das Ereignis initiiert hat. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `InitiatingProcessFileName` | string | Name des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessFolderPath` | string | Ordner mit dem Prozess (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessId` | int | Prozess-ID (PID) des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCommandLine` | string | Befehlszeile zum Ausführen des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu dem der Prozess gestartet wurde, der das Ereignis initiiert hat |
| `InitiatingProcessParentId` | int | Prozess-ID (PID) des übergeordneten Prozesses, der den prozess, der für das Ereignis verantwortlich war, |
| `InitiatingProcessParentFileName` | string | Name des übergeordneten Prozesses, der den prozessverantwortlichen Prozess für das Ereignis gezeitet hat |
| `InitiatingProcessParentCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu der das übergeordnete Element des für das Ereignis verantwortlichen Prozesses gestartet wurde |
| `InitiatingProcessMD5` | string | MD5-Hash des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessAccountDomain` | string | Domäne des Kontos, mit dem der Prozess für das Ereignis verantwortlich war |
| `InitiatingProcessAccountName` | string | Benutzername des Kontos, das den prozess für das Ereignis verantwortlich führte |
| `InitiatingProcessAccountSid` | string | Security Identifier (SID) des Kontos, das den für das Ereignis verantwortlichen Prozess führte |
| `InitiatingProcessAccountUpn` | string | Benutzerprinzipalname (UPN) des Kontos, das den für das Ereignis verantwortlichen Prozess führte |
| `InitiatingProcessAccountObjectId` | string | Azure AD-Objekt-ID des Benutzerkontos, das den für das Ereignis verantwortlichen Prozess ausgeführt hat |
| `InitiatingProcessLogonId` | string | Bezeichner für eine Anmeldesitzung des Prozesses, der das Ereignis initiiert hat. Dieser Bezeichner ist auf demselben Computer nur zwischen Neustarts eindeutig |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden. |
| `AppGuardContainerId` | string | Id für den virtualisierten Container, der von Application Guard zum Isolieren von Browseraktivitäten verwendet wird |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

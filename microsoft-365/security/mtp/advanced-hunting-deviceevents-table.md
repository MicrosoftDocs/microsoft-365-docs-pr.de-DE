---
title: Tabelle "DeviceEvents" im Schema "Erweiterte Suche"
description: Informationen zu Antivirus, Firewall und anderen Ereignistypen finden Sie in der Tabelle für verschiedene Geräteereignisse (DeviceEvents) des Schemas für die erweiterte Suche.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Sicherheitsereignisse, Antivirus, Firewall, Exploit Guard, DeviceEvents
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
ms.openlocfilehash: 1340464fbe71e919a60668cf7d1b2f535eb6d260
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145320"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Die verschiedenen Geräteereignisse oder die Tabelle im Schema für die erweiterte Suche enthalten Informationen zu verschiedenen Ereignistypen, einschließlich Ereignissen, die durch Sicherheitssteuerelemente ausgelöst werden, z. B. Windows Defender Antivirus- und `DeviceEvents` Exploit-Schutz. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den Ereignistypen (Werten), die von einer Tabelle unterstützt werden, finden Sie in der integrierten Schemareferenz, die im `ActionType` Security Center verfügbar ist. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).


| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. Details finden Sie in der [In-Portal-Schemareferenz.](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FolderPath` | string | Ordner mit der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA256` | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `MD5` | string | #A0 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `AccountDomain` | string | Domäne des Kontos |
| `AccountName` | string | Benutzername des Kontos |
| `AccountSid` | string | Sicherheits-ID (SID) des Kontos |
| `RemoteUrl` | string | URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde |
| `RemoteDeviceName` | string | Name des Computers, der einen Remotevorgang auf dem betroffenen Computer ausgeführt hat. Je nach gemeldeten Ereignis kann dieser Name ein vollqualifizierter Domänenname (FQDN), ein NetBIOS-Name oder ein Hostname ohne Domäneninformationen sein. |
| `ProcessId` | int | Prozess-ID (PID) des neu erstellten Prozesses |
| `ProcessCommandLine` | string | Befehlszeile zum Erstellen des neuen Prozesses |
| `ProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit der Prozesserg nung |
| `ProcessTokenElevation` | string | Tokentyp, der angibt, ob die Rechteerweiterung der Benutzerzugriffssteuerung (User Access Control, UAC) auf den neu erstellten Prozess angewendet wurde. |
| `LogonId` | string | Bezeichner für eine Anmeldesitzung. Dieser Bezeichner ist auf demselben Computer nur zwischen Neustarts eindeutig. |
| `RegistryKey` | string | Registrierungsschlüssel, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueName` | string | Name des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueData` | string | Daten des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `RemoteIP` | string | IP-Adresse, mit der eine Verbindung hergestellt wurde |
| `RemotePort` | int | DER PORT auf dem Remotegerät, mit dem eine Verbindung hergestellt wurde |
| `LocalIP` | string | DIE IP-Adresse, die dem lokalen Computer zugewiesen ist, der während der Kommunikation verwendet wird |
| `LocalPort` | int | TCP-Port auf dem lokalen Computer, der während der Kommunikation verwendet wird |
| `FileOriginUrl` | string | URL, von der die Datei heruntergeladen wurde |
| `FileOriginIP` | string | IP-Adresse, von der die Datei heruntergeladen wurde |
| `AdditionalFields` | string | Zusätzliche Informationen zu dem Ereignis im JSON-Array-Format |
| `InitiatingProcessFileSize` | long | Größe der Datei, die den für das Ereignis verantwortlichen Prozess verwendet hat |
| `FileSize` | long | Größe der Datei in Byte |
| `InitiatingProcessSHA1` | string | SHA-1 des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessSHA256` | string | SHA-256 des Prozesses (Bilddatei), der das Ereignis initiiert hat. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `InitiatingProcessFileName` | string | Name des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessFolderPath` | string | Ordner, der den Prozess (Bilddatei) enthält, der das Ereignis initiiert hat |
| `InitiatingProcessId` | int | Prozess-ID (PID) des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCommandLine` | string | Befehlszeile zum Ausführen des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu dem der Prozess, der das Ereignis initiiert hat, gestartet wurde |
| `InitiatingProcessParentId` | int | Prozess-ID (PID) des übergeordneten Prozesses, der den für das Ereignis verantwortlichen Prozess aussing |
| `InitiatingProcessParentFileName` | string | Name des übergeordneten Prozesses, der den für das Ereignis verantwortlichen Prozess aussing |
| `InitiatingProcessParentCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, an dem das übergeordnete Element des für das Ereignis verantwortlichen Prozesses gestartet wurde |
| `InitiatingProcessMD5` | string | #A0 des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessAccountDomain` | string | Domäne des Kontos, das den für das Ereignis verantwortlichen Prozess verwendet hat |
| `InitiatingProcessAccountName` | string | Benutzername des Kontos, das den für das Ereignis verantwortlichen Prozess verwendet hat |
| `InitiatingProcessAccountSid` | string | Sicherheits-ID (SID) des Kontos, das den für das Ereignis verantwortlichen Prozess verwendet hat |
| `InitiatingProcessAccountUpn` | string | Benutzerprinzipalname (UPN) des Kontos, das den für das Ereignis verantwortlichen Prozess verwendet hat |
| `InitiatingProcessAccountObjectId` | string | Azure AD-Objekt-ID des Benutzerkontos, das den für das Ereignis verantwortlichen Prozess ausgeführt hat |
| `InitiatingProcessLogonId` | string | Bezeichner für eine Anmeldesitzung des Prozesses, der das Ereignis initiiert hat. Dieser Bezeichner ist auf demselben Computer nur zwischen Neustarts eindeutig. |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten "DeviceName" und "Timestamp" verwendet werden. |
| `AppGuardContainerId` | string | Bezeichner für den virtualisierten Container, der von Application Guard zum Isolieren der Browseraktivität verwendet wird |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

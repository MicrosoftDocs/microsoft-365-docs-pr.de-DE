---
title: DeviceEvents-Tabelle im schema der erweiterten Suche
description: Informationen zu Antivirus, Firewall und anderen Ereignistypen finden Sie in der Tabelle verschiedene Geräteereignisse (DeviceEvents) des schemas für die erweiterte Suche.
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberbedrohungen, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Sicherheitsereignisse, Antivirus, Firewall, Exploit Guard, MiscEvents
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
ms.openlocfilehash: 49a0b608caa6d759f58889e6f831f84d2b4b90d3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064384"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Die verschiedenen Geräteereignisse oder -tabellen im Schema für die erweiterte Suche enthalten Informationen zu verschiedenen Ereignistypen, einschließlich Ereignissen, die durch Sicherheitssteuerelemente ausgelöst werden, z. B. `DeviceEvents` Microsoft Defender Antivirus und Exploit-Schutz. [](advanced-hunting-overview.md) Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.

Weitere Informationen zu anderen Tabellen im Schema für die erweiterte Suche finden Sie in der [Schemareferenz](advanced-hunting-schema-reference.md)für erweiterte Suche .

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutige ID für das Gerät im Dienst |
| `DeviceName` | Zeichenfolge | Vollqualifizierter Domänenname (FQDN) des Geräts |
| `ActionType` | Zeichenfolge | Typ der Aktivität, die das Ereignis ausgelöst hat |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FolderPath` | string | Ordner, der die Datei enthält, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA256` | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde. Dieses Feld wird in der Regel nicht aufgefüllt– verwenden Sie die SPALTE SHA1, wenn verfügbar |
| `MD5` | Zeichenfolge | MD5-Hash der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `AccountDomain` | Zeichenfolge | Domäne des Kontos |
| `AccountName` |Zeichenfolge | Benutzername des Kontos |
| `AccountSid` | Zeichenfolge | Security Identifier (SID) des Kontos |
| `RemoteUrl` | string | URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde |
| `RemoteDeviceName` | string | Name des Geräts, das einen Remotevorgang auf dem betroffenen Gerät ausgeführt hat. Je nach gemeldeten Ereignis kann es sich bei diesem Namen um einen vollqualifizierten Domänennamen (FQDN), einen NetBIOS-Namen oder einen Hostnamen ohne Domäneninformationen geben. |
| `ProcessId` | int | Prozess-ID (PID) des neu erstellten Prozesses |
| `ProcessCommandLine` | Zeichenfolge | Befehlszeile zum Erstellen des neuen Prozesses |
| `ProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu der der Prozess erstellt wurde |
| `ProcessTokenElevation` | Zeichenfolge | Tokentyp, der angibt, ob die Berechtigungserweiterung der Benutzerzugriffssteuerung (User Access Control, UAC) auf den neu erstellten Prozess angewendet wurde oder nicht |
| `LogonId` | Zeichenfolge | Bezeichner für eine Anmeldesitzung. Dieser Bezeichner ist auf demselben Gerät nur zwischen Neustarts eindeutig. |
| `RegistryKey` | Zeichenfolge | Registrierungsschlüssel, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueName` | Zeichenfolge | Name des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueData` | Zeichenfolge | Daten des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `RemoteIP` | string | IP-Adresse, mit der eine Verbindung hergestellt wurde |
| `RemotePort` | int | TCP-Port auf dem Remotegerät, mit dem eine Verbindung hergestellt wurde |
| `LocalIP` | Zeichenfolge | IP-Adresse, die dem lokalen Gerät zugewiesen ist, das während der Kommunikation verwendet wird |
| `LocalPort` | int | TCP-Port auf dem lokalen Gerät, das während der Kommunikation verwendet wird |
| `FileOriginUrl` | Zeichenfolge | URL, von der die Datei heruntergeladen wurde |
| `FileOriginIP` | Zeichenfolge | IP-Adresse, von der die Datei heruntergeladen wurde |
| `AdditionalFields` | Zeichenfolge | Zusätzliche Informationen zum Ereignis im JSON-Arrayformat |
| `InitiatingProcessSHA1` | Zeichenfolge | SHA-1 des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessSHA256` | Zeichenfolge | SHA-256 des Prozesses (Bilddatei), der das Ereignis initiiert hat. Dieses Feld wird in der Regel nicht aufgefüllt– verwenden Sie die SPALTE SHA1, wenn verfügbar |
| `InitiatingProcessFileName` | Zeichenfolge | Name des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessFolderPath` | Zeichenfolge | Ordner mit dem Prozess (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessId` | int | Prozess-ID (PID) des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCommandLine` | Zeichenfolge | Befehlszeile zum Ausführen des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu dem der Prozess gestartet wurde, der das Ereignis initiiert hat |
| `InitiatingProcessParentId` | int | Prozess-ID (PID) des übergeordneten Prozesses, der den prozess, der für das Ereignis verantwortlich war, |
| `InitiatingProcessParentFileName` | Zeichenfolge | Name des übergeordneten Prozesses, der den prozessverantwortlichen Prozess für das Ereignis gezeitet hat |
| `InitiatingProcessParentCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu der das übergeordnete Element des für das Ereignis verantwortlichen Prozesses gestartet wurde |
| `InitiatingProcessMD5` | Zeichenfolge | MD5-Hash des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessAccountDomain` | Zeichenfolge | Domäne des Kontos, mit dem der Prozess für das Ereignis verantwortlich war |
| `InitiatingProcessAccountName` | Zeichenfolge | Benutzername des Kontos, das den prozess für das Ereignis verantwortlich führte |
| `InitiatingProcessAccountSid` | Zeichenfolge | Security Identifier (SID) des Kontos, das den für das Ereignis verantwortlichen Prozess führte |
| `InitiatingProcessLogonId` | Zeichenfolge | Bezeichner für eine Anmeldesitzung des Prozesses, der das Ereignis initiiert hat. Dieser Bezeichner ist auf demselben Gerät nur zwischen Neustarts eindeutig. |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten `DeviceName` und verwendet `Timestamp` werden. |
| `AppGuardContainerId` | Zeichenfolge | Id für den virtualisierten Container, der von Application Guard zum Isolieren von Browseraktivitäten verwendet wird |


## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-reference.md)

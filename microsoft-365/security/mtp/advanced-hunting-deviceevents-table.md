---
title: DeviceEvents-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über Antivirus, Firewall und andere Ereignistypen in der Tabelle "verschiedene Geräteereignisse" (DeviceEvents) des Advanced Hunting-Schemas.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Sicherheitsereignisse, Antivirus, Firewall, Exploit Guard, DeviceEvents
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: dd49cc0bab2013a0f786266aa87d5575e2b4a2fd
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198235"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection



Die verschiedenen Geräteereignisse oder `DeviceEvents` Tabellen im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthalten Informationen über verschiedene Ereignistypen, einschließlich Ereignissen, die von Sicherheitssteuerelementen ausgelöst wurden, wie Windows Defender Antivirus und Exploit Protection. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

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
| `AccountDomain` | Zeichenfolge | Domäne des Kontos |
| `AccountName` | Zeichenfolge | Benutzername des Kontos |
| `AccountSid` | Zeichenfolge | Sicherheits-ID (SID) des Kontos |
| `RemoteUrl` | string | URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde |
| `RemoteDeviceName` | string | Name des Computers, der auf dem betroffenen Computer einen Remotevorgang ausgeführt hat. Je nachdem, welches Ereignis gemeldet wird, kann dieser Name ein vollqualifizierter Domänenname (FQDN), ein NetBIOS-Name oder ein Hostname ohne Domäneninformationen sein. |
| `ProcessId` | int | Prozess-ID (PID) des neu erstellten Prozesses |
| `ProcessCommandLine` | Zeichenfolge | Befehlszeile, die zum Erstellen des neuen Prozesses verwendet wird |
| `ProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit der Erstellung des Prozesses |
| `ProcessTokenElevation` | Zeichenfolge | Tokentyp, der angibt, dass die Benutzerzugriffssteuerung (UAC) auf den neu erstellten Prozess angewendet wird oder nicht vorhanden ist |
| `LogonId` | Zeichenfolge | Bezeichner für eine Anmeldesitzung. Dieser Bezeichner ist auf demselben Computer nur zwischen Neustarts eindeutig. |
| `RegistryKey` | Zeichenfolge | Registrierungsschlüssel, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueName` | Zeichenfolge | Name des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `RegistryValueData` | Zeichenfolge | Daten des Registrierungswerts, auf den die aufgezeichnete Aktion angewendet wurde |
| `RemoteIP` | string | IP-Adresse, mit der eine Verbindung hergestellt wurde |
| `RemotePort` | int | TCP-Port auf dem Remotegerät, mit dem eine Verbindung hergestellt wurde |
| `LocalIP` | Zeichenfolge | IP-Adresse, die dem lokalen Computer zugewiesen ist, der während der Kommunikation verwendet wird |
| `LocalPort` | int | TCP-Port auf dem lokalen Computer, der während der Kommunikation verwendet wird |
| `FileOriginUrl` | Zeichenfolge | URL, von der die Datei heruntergeladen wurde |
| `FileOriginIP` | Zeichenfolge | IP-Adresse, von der die Datei heruntergeladen wurde |
| `AdditionalFields` | Zeichenfolge | Weitere Informationen zum Ereignis im JSON-Array Format |
| `InitiatingProcessSHA1` | Zeichenfolge | SHA-1 des Prozesses (Image-Datei), der das Ereignis initiiert hat |
| `InitiatingProcessSHA256` | Zeichenfolge | SHA-256 des Prozesses (Image-Datei), der das Ereignis initiiert hat. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `InitiatingProcessFileName` | string | Name des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessFolderPath` | Zeichenfolge | Ordner mit dem Prozess (Image-Datei), der das Ereignis initiiert hat |
| `InitiatingProcessId` | int | Prozess-ID (PID) des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCommandLine` | Zeichenfolge | Befehlszeile, die zum Ausführen des Prozesses verwendet wird, der das Ereignis initiiert hat |
| `InitiatingProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit des Starts des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessParentId` | int | Prozess-ID (PID) des übergeordneten Prozesses, der den für das Ereignis verantwortlichen Prozess hervorgerufen hat |
| `InitiatingProcessParentFileName` | Zeichenfolge | Name des übergeordneten Prozesses, der den für das Ereignis verantwortlichen Prozess hervorgerufen hat |
| `InitiatingProcessParentCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu denen das übergeordnete Element des für das Ereignis Verantwortlichen Prozesses gestartet wurde. |
| `InitiatingProcessMD5` | Zeichenfolge | MD5-Hash des Prozesses (Image-Datei), der das Ereignis initiiert hat |
| `InitiatingProcessAccountDomain` | Zeichenfolge | Domäne des Kontos, das den für das Ereignis verantwortlichen Prozess ausgeführt hat |
| `InitiatingProcessAccountName` | Zeichenfolge | Benutzername des Kontos, das den für das Ereignis verantwortlichen Prozess ausgeführt hat |
| `InitiatingProcessAccountSid` | Zeichenfolge | Sicherheits-ID (SID) des Kontos, das den für das Ereignis verantwortlichen Prozess ausgeführt hat |
| `InitiatingProcessLogonId` | Zeichenfolge | Bezeichner für eine Anmeldesitzung des Prozesses, der das Ereignis initiiert hat. Dieser Bezeichner ist auf demselben Computer nur zwischen Neustarts eindeutig. |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte zusammen mit den Gerätename-und timestamp-Spalten verwendet werden. |
| `AppGuardContainerId` | Zeichenfolge | Bezeichner für den virtualisierten Container, der von Application Guard zum Isolieren von Browseraktivitäten verwendet wird |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suchen auf Geräten, in E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

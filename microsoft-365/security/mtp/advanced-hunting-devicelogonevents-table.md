---
title: DeviceLogonEvents-Tabelle im Advanced Hunting-Schema
description: Informationen zu Authentifizierungs-oder Anmeldeereignissen in der DeviceLogonEvents-Tabelle des Advanced Hunting-Schemas
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, logonevents, DeviceLogonEvents, Authentifizierung, Anmeldung, Anmeldung
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 2ec668ae3aba0a163ebc0c148bf3b35b07a71944
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429959"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection



Die `DeviceLogonEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Benutzeranmeldungen und anderen Authentifizierungsereignissen auf Geräten. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den `ActionType` von einer Tabelle unterstützten Ereignistypen (Values) finden Sie in der [integrierten Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) , die im Sicherheitscenter verfügbar ist.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `ActionType` | string |Typ der Aktivität, die das Ereignis ausgelöst hat. |
| `AccountDomain` | string | Domäne des Kontos |
| `AccountName` | string | Benutzername des Kontos |
| `AccountSid` | string | Sicherheits-ID (SID) des Kontos |
| `LogonType` | string | Typ der Anmeldesitzung, insbesondere:<br><br> - **Interaktiv** – der Benutzer interagiert physisch mit dem Computer mit der lokalen Tastatur und dem Bildschirm.<br><br> - **Remote Interactive (RDP)-Anmeldungen** -Benutzer interagiert mit dem Computer remote mithilfe von Remote Desktop, Terminal Dienste, Remoteunterstützung oder anderen RDP-Clients<br><br> - **Netzwerk** Sitzung, die beim Zugriff auf den Computer mit PsExec initiiert wurde oder bei dem auf freigegebene Ressourcen auf dem Computer (beispielsweise Drucker und freigegebene Ordner) zugegriffen wird<br><br> - Von geplanten Vorgängen initiierte **Batch** Sitzung<br><br> - Von Diensten initiierte **Dienst** Sitzung beim Start<br> |
| `LogonId` | string | Bezeichner für eine Anmeldesitzung. Dieser Bezeichner ist auf demselben Computer nur zwischen Neustarts eindeutig. |
| `RemoteDeviceName` | string | Name des Computers, der auf dem betroffenen Computer einen Remotevorgang ausgeführt hat. Je nachdem, welches Ereignis gemeldet wird, kann dieser Name ein vollqualifizierter Domänenname (FQDN), ein NetBIOS-Name oder ein Hostname ohne Domäneninformationen sein. |
| `RemoteIP` | string | IP-Adresse, mit der eine Verbindung hergestellt wurde |
| `RemoteIPType` | string | Typ der IP-Adresse, beispielsweise Public, private, reservierte, Loopback, Teredo, FourToSixMapping und Broadcast |
| `RemotePort` | int | TCP-Port auf dem Remotegerät, mit dem eine Verbindung hergestellt wurde |
| `AdditionalFields` | string | Weitere Informationen zum Ereignis im JSON-Array Format |
| `InitiatingProcessAccountDomain` | string | Domäne des Kontos, das den für das Ereignis verantwortlichen Prozess ausgeführt hat |
| `InitiatingProcessAccountName` | string | Benutzername des Kontos, das den für das Ereignis verantwortlichen Prozess ausgeführt hat |
| `InitiatingProcessAccountSid` | string | Sicherheits-ID (SID) des Kontos, das den für das Ereignis verantwortlichen Prozess ausgeführt hat |
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
| `IsLocalAdmin` | Boolescher Wert | Boolescher Indikator dafür, ob der Benutzer ein lokaler Administrator auf dem Computer ist |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suchen auf Geräten, in E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

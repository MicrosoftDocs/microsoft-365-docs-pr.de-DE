---
title: Tabelle "DeviceLogonEvents" im Schema "Erweiterte Suche"
description: Informationen zu Authentifizierungs- oder Anmeldeereignissen in der Tabelle "DeviceLogonEvents" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, Anmeldeinformationen, DeviceLogonEvents, Authentifizierung, Anmeldung, Anmelden
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
ms.openlocfilehash: 3a5666cc106365876956c8e313f9cd2f5a996e6f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931230"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Die `DeviceLogonEvents` Tabelle im Schema für die erweiterte [Suche](advanced-hunting-overview.md) enthält Informationen zu Benutzeranmeldungen und anderen Authentifizierungsereignissen auf Geräten. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den Ereignistypen (Werten), die von einer Tabelle unterstützt werden, finden Sie in der integrierten Schemareferenz, die im `ActionType` Security Center verfügbar ist. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `ActionType` | string |Aktivitätstyp, der das Ereignis ausgelöst hat |
| `AccountDomain` | string | Domäne des Kontos |
| `AccountName` | string | Benutzername des Kontos |
| `AccountSid` | string | Sicherheits-ID (SID) des Kontos |
| `LogonType` | string | Typ der Anmeldesitzung, insbesondere:<br><br> - **Interaktiv** – Benutzer interagiert über die lokale Tastatur und den Bildschirm physisch mit dem Computer.<br><br> - **Remote interaktive Anmeldungen (RDP):** Benutzer interagiert remote mit dem Computer mithilfe von Remotedesktop, Terminaldiensten, Remoteunterstützung oder anderen RDP-Clients.<br><br> - **Netzwerk** – Sitzung, die initiiert wird, wenn über PsExec auf den Computer zugegriffen wird oder wenn auf freigegebene Ressourcen auf dem Computer zugegriffen wird, z. B. Drucker und freigegebene Ordner<br><br> - **Batch** – Von geplanten Vorgängen initiierte Sitzung<br><br> - **Dienst** – Von Diensten initiierte Sitzung beim Start<br> |
| `LogonId` | string | Bezeichner für eine Anmeldesitzung. Dieser Bezeichner ist auf demselben Computer nur zwischen Neustarts eindeutig. |
| `RemoteDeviceName` | string | Name des Computers, der einen Remotevorgang auf dem betroffenen Computer ausgeführt hat. Je nach gemeldeten Ereignis kann dieser Name ein vollqualifizierter Domänenname (FQDN), ein NetBIOS-Name oder ein Hostname ohne Domäneninformationen sein. |
| `RemoteIP` | string | IP-Adresse, mit der eine Verbindung hergestellt wurde |
| `RemoteIPType` | string | Typ der IP-Adresse, z. B. Öffentlich, Privat, Reserviert, Loopback, Teredo, FourToSixMapping und Broadcast |
| `RemotePort` | int | DER PORT auf dem Remotegerät, mit dem eine Verbindung hergestellt wurde |
| `AdditionalFields` | string | Zusätzliche Informationen zu dem Ereignis im JSON-Array-Format |
| `InitiatingProcessAccountDomain` | string | Domäne des Kontos, das den für das Ereignis verantwortlichen Prozess verwendet hat |
| `InitiatingProcessAccountName` | string | Benutzername des Kontos, das den für das Ereignis verantwortlichen Prozess verwendet hat |
| `InitiatingProcessAccountSid` | string | Sicherheits-ID (SID) des Kontos, das den für das Ereignis verantwortlichen Prozess verwendet hat |
| `InitiatingProcessIntegrityLevel` | string | Integritätsebene des Prozesses, der das Ereignis initiiert hat. Windows weist Prozesse Integritätsstufen basierend auf bestimmten Merkmalen zu, z. B. wenn sie über einen Internetdownload gestartet wurden. Diese Integritätsstufen beeinflussen Berechtigungen für Ressourcen |
| `InitiatingProcessTokenElevation` | string | Tokentyp, der angibt, ob die Rechteerweiterung der Benutzerzugriffssteuerung (User Access Control, UAC) auf den Prozess angewendet wurde, der das Ereignis initiiert hat. |
| `InitiatingProcessSHA1` | string | SHA-1 des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessSHA256` | string | SHA-256 des Prozesses (Bilddatei), der das Ereignis initiiert hat. Dieses Feld ist in der Regel nicht aufgefüllt. Verwenden Sie die Spalte "SHA1", falls verfügbar. |
| `InitiatingProcessMD5` | string | #A0 des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessFileName` | string | Name des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessId` | int | Prozess-ID (PID) des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCommandLine` | string | Befehlszeile zum Ausführen des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, an dem der Prozess, der das Ereignis initiiert hat, gestartet wurde |
| `InitiatingProcessFolderPath` | string | Ordner, der den Prozess (Bilddatei) enthält, der das Ereignis initiiert hat |
| `InitiatingProcessParentId` | int | Prozess-ID (PID) des übergeordneten Prozesses, der den für das Ereignis verantwortlichen Prozess aussing |
| `InitiatingProcessParentFileName` | string | Name des übergeordneten Prozesses, der den für das Ereignis verantwortlichen Prozess aussing |
| `InitiatingProcessParentCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, an dem das übergeordnete Element des für das Ereignis verantwortlichen Prozesses gestartet wurde |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten "DeviceName" und "Timestamp" verwendet werden. |
| `AppGuardContainerId` | string | Bezeichner für den virtualisierten Container, der von Application Guard zum Isolieren der Browseraktivität verwendet wird |
| `IsLocalAdmin` | Boolescher Wert | Boolescher Indikator dafür, ob der Benutzer ein lokaler Administrator auf dem Computer ist |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

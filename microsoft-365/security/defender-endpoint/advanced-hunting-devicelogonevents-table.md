---
title: DeviceLogonEvents-Tabelle im schema der erweiterten Suche
description: Weitere Informationen zu Authentifizierungs- oder Anmeldeereignissen finden Sie in der DeviceLogonEvents-Tabelle des schemas für die erweiterte Suche.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, devicelogonevents, authentication, logon, sign in, LogonEvents
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
ms.openlocfilehash: 7bc6e655d3a423b45f70210e53fca9713427355a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067063"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Die `DeviceLogonEvents` Tabelle im Schema der erweiterten [Suche](advanced-hunting-overview.md) enthält Informationen zu Benutzeranmeldungen und anderen Authentifizierungsereignissen. Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.

> [!NOTE]
> Die Sammlung von DeviceLogonEvents wird unter Windows 7 oder Windows Server 2008 R2.
> Wir empfehlen ein Upgrade auf Windows 10 oder Windows Server 2019, um eine optimale Sichtbarkeit der Benutzeranmeldungsaktivität zu erhalten.

Weitere Informationen zu anderen Tabellen im Schema für die erweiterte Suche finden Sie in der [Schemareferenz](advanced-hunting-schema-reference.md)für erweiterte Suche .

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutige ID für das Gerät im Dienst |
| `DeviceName` | Zeichenfolge | Vollqualifizierter Domänenname (FQDN) des Geräts |
| `ActionType` | Zeichenfolge |Typ der Aktivität, die das Ereignis ausgelöst hat |
| `AccountDomain` | Zeichenfolge | Domäne des Kontos |
| `AccountName` | Zeichenfolge | Benutzername des Kontos |
| `AccountSid` | Zeichenfolge | Security Identifier (SID) des Kontos |
| `LogonType` | Zeichenfolge | Typ der Anmeldesitzung, insbesondere:<br><br> - **Interaktiv** – Benutzer interagiert physisch mit dem Gerät mithilfe der lokalen Tastatur und des Bildschirms<br><br> - **Remote-interaktive (RDP)-Anmeldungen** – Benutzer interagiert remote mit dem Gerät mithilfe von Remotedesktop, Terminaldiensten, Remoteunterstützung oder anderen RDP-Clients<br><br> - **Netzwerk** – Sitzung, die initiiert wird, wenn über PsExec auf das Gerät zugegriffen wird oder wenn auf freigegebene Ressourcen auf dem Gerät zugegriffen wird( z. B. Drucker und freigegebene Ordner).<br><br> - **Batch** – Sitzung, die von geplanten Vorgängen initiiert wurde<br><br> - **Dienst** – Sitzung, die von Diensten beim Start initiiert wurde<br> |
| `LogonId` | Zeichenfolge | Bezeichner für eine Anmeldesitzung. Dieser Bezeichner ist auf demselben Gerät nur zwischen Neustarts eindeutig. |
| `RemoteDeviceName` | Zeichenfolge | Name des Geräts, das einen Remotevorgang auf dem betroffenen Gerät ausgeführt hat. Je nach gemeldeten Ereignis kann es sich bei diesem Namen um einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN), einen NetBIOS-Namen oder einen Hostnamen ohne Domäneninformationen geben. |
| `RemoteIP` | string | IP-Adresse, mit der eine Verbindung hergestellt wurde |
| `RemoteIPType` | Zeichenfolge | Typ der IP-Adresse, z. B. Public, Private, Reserved, Loopback, Teredo, FourToSixMapping und Broadcast |
| `RemotePort` | int | TCP-Port auf dem Remotegerät, mit dem eine Verbindung hergestellt wurde |
| `AdditionalFields` | Zeichenfolge | Zusätzliche Informationen zum Ereignis im JSON-Arrayformat |
| `InitiatingProcessAccountDomain` | Zeichenfolge | Domäne des Kontos, mit dem der Prozess für das Ereignis verantwortlich war |
| `InitiatingProcessAccountName` | Zeichenfolge | Benutzername des Kontos, das den prozess für das Ereignis verantwortlich führte |
| `InitiatingProcessAccountSid` | Zeichenfolge | Security Identifier (SID) des Kontos, das den für das Ereignis verantwortlichen Prozess führte |
| `InitiatingProcessIntegrityLevel` | Zeichenfolge | Integritätsebene des Prozesses, der das Ereignis initiiert hat. Windows weist Prozesse Integritätsstufen basierend auf bestimmten Merkmalen zu, z. B. wenn sie über einen Internetdownload gestartet wurden. Diese Integritätsstufen beeinflussen Berechtigungen für Ressourcen |
| `InitiatingProcessTokenElevation` | Zeichenfolge | Tokentyp, der angibt, ob die Berechtigungserweiterung für die Benutzerzugriffssteuerung (User Access Control, UAC) auf den Prozess angewendet wurde, der das Ereignis initiiert hat |
| `InitiatingProcessSHA1` | Zeichenfolge | SHA-1 des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessSHA256` | Zeichenfolge | SHA-256 des Prozesses (Bilddatei), der das Ereignis initiiert hat. Dieses Feld wird in der Regel nicht aufgefüllt– verwenden Sie die SPALTE SHA1, wenn verfügbar |
| `InitiatingProcessMD5` | Zeichenfolge | MD5-Hash des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessFileName` | Zeichenfolge | Name des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessId` | int | Prozess-ID (PID) des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCommandLine` | Zeichenfolge | Befehlszeile zum Ausführen des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu dem der Prozess gestartet wurde, der das Ereignis initiiert hat |
| `InitiatingProcessFolderPath` | Zeichenfolge | Ordner mit dem Prozess (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessParentId` | int | Prozess-ID (PID) des übergeordneten Prozesses, der den prozess, der für das Ereignis verantwortlich war, |
| `InitiatingProcessParentFileName` | Zeichenfolge | Name des übergeordneten Prozesses, der den prozessverantwortlichen Prozess für das Ereignis gezeitet hat |
| `InitiatingProcessParentCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu der das übergeordnete Element des für das Ereignis verantwortlichen Prozesses gestartet wurde |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten `DeviceName` und verwendet `Timestamp` werden. |
| `AppGuardContainerId` | Zeichenfolge | Id für den virtualisierten Container, der von Application Guard zum Isolieren von Browseraktivitäten verwendet wird |
| `IsLocalAdmin` | boolean | Boolescher Indikator, ob der Benutzer ein lokaler Administrator auf dem Gerät ist |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-reference.md)

---
title: IdentityLogonEvents-Tabelle im erweiterten Jagdschema
description: Erfahren Sie mehr über Von Active Directory aufgezeichnete Authentifizierungsereignisse in der IdentityLogonEvents-Tabelle des erweiterten Jagdschemas
keywords: Erweiterte Jagd, Bedrohungsjagd, Cyber-Bedrohungsjagd, Microsoft 365 Defender, Microsoft 365, m365, Suche, Abfrage, Telemetrie, Schemareferenz, kusto, Tabelle, Spalte, Datentyp, Beschreibung, IdentityLogonEvents, Azure AD, Active Directory, Microsoft Defender for Identity, Identitäten
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3cd0c0f371c73a515704791e829be7266d400580
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572753"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die `IdentityLogonEvents` Tabelle im erweiterten [Jagdschema](advanced-hunting-overview.md) enthält Informationen zu Authentifizierungsaktivitäten, die über Ihr lokal erstelltes Active Directory erstellt werden, das von Microsoft Defender for Identity erfasst wurde, sowie Authentifizierungsaktivitäten im Zusammenhang mit Microsoft-Onlinediensten, die von Microsoft Cloud App Security erfasst wurden. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Detaillierte Informationen zu den Ereignistypen `ActionType` (Werten), die von einer Tabelle unterstützt werden, finden Sie in der integrierten Schemareferenz, die im Sicherheitscenter verfügbar ist.

>[!NOTE]
>In dieser Tabelle werden Azure Active Directory (Azure AD)-Anmeldeaktivitäten behandelt, die von Cloud App Security nachverfolgt werden, insbesondere interaktive Anmeldungen und Authentifizierungsaktivitäten mit ActiveSync und anderen Älterenprotokollen. Nicht interaktive Anmeldungen, die in dieser Tabelle nicht verfügbar sind, können im Azure AD-Überwachungsprotokoll angezeigt werden. [Weitere Informationen zum Verbinden Cloud App Security mit Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `ActionType` | string | Art der Aktivität, die das Ereignis ausgelöst hat. Weitere Informationen finden Sie in der [In-Portal-Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | Zeichenfolge | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `LogonType` | Zeichenfolge | Typ der Anmeldesitzung, insbesondere:<br><br> - **Interaktiv** - Der Benutzer interagiert physisch mit dem Computer über die lokale Tastatur und den Bildschirm<br><br> - **Interaktive Remote-Anmeldungen (RDP)** – Der Benutzer interagiert über Remotedesktop-, Terminaldienste, Remoteunterstützung oder andere RDP-Clients remote mit dem Computer<br><br> - **Netzwerk** - Sitzung, die initiiert wird, wenn über PsExec auf den Computer zugegriffen wird oder auf das freigegebene Ressourcen auf dem Computer, z. B. Drucker und freigegebene Ordner, zugegriffen wird<br><br> - **Batch** - Sitzung, die durch geplante Aufgaben initiiert wurde<br><br> - **Service** - Sitzung, die von Diensten initiiert wird, wenn sie gestartet werden |
| `Protocol` | Zeichenfolge | Netzwerkprotokoll verwendet |
| `FailureReason` | Zeichenfolge | Informationen, die erklären, warum die aufgezeichnete Aktion fehlgeschlagen ist |
| `AccountName` | Zeichenfolge | Benutzername des Kontos |
| `AccountDomain` | Zeichenfolge | Domain des Kontos |
| `AccountUpn` | Zeichenfolge | Benutzerprinzipalname (UPN) des Kontos |
| `AccountSid` | Zeichenfolge | Security Identifier (SID) des Kontos |
| `AccountObjectId` | Zeichenfolge | Eindeutiger Bezeichner für das Konto in Azure AD |
| `AccountDisplayName` | Zeichenfolge | Name des im Adressbuch angezeigten Kontobenutzers. In der Regel eine Kombination aus einem bestimmten oder Vornamen, einer mittleren Einweihung und einem Nachnamen oder Nachnamen. |
| `DeviceName` | Zeichenfolge | Vollqualifizierter Domänenname (FQDN) des Geräts |
| `DeviceType` | Zeichenfolge | Gerätetyp |
| `OSPlatform` | string | Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. |
| `IPAddress` | string | IP-Adresse, die dem Endpunkt zugewiesen und bei der zugehörigen Netzwerkkommunikation verwendet wird |
| `Port` | Zeichenfolge | TCP-Port, der während der Kommunikation verwendet wird |
| `DestinationDeviceName` | Zeichenfolge | Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `DestinationIPAddress` | Zeichenfolge | IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `DestinationPort` | Zeichenfolge | Zielport der zugehörigen Netzwerkkommunikation |
| `TargetDeviceName` | Zeichenfolge | Vollqualifizierter Domänenname (FQDN) des Geräts, auf das die aufgezeichnete Aktion angewendet wurde |
| `TargetAccountDisplayName` | Zeichenfolge | Anzeigename des Kontos, auf das die aufgezeichnete Aktion angewendet wurde |
| `Location` | Zeichenfolge | Stadt, Land oder anderer geografischer Ort, der mit dem Ereignis verknüpft ist |
| `Isp` | Zeichenfolge | Internetdienstanbieter (Internet Service Provider, ISP), der der Endpunkt-IP-Adresse zugeordnet ist |
| `ReportId` | long | Eindeutiger Bezeichner für das Ereignis |
| `AdditionalFields` | Zeichenfolge | Zusätzliche Informationen zur Entität oder zum Ereignis |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
---
title: Tabelle "IdentityLogonEvents" im Schema "Erweiterte Suche"
description: Informationen zu Authentifizierungsereignissen, die von Active Directory in der Tabelle "IdentityLogonEvents" des Schemas für die erweiterte Suche aufgezeichnet werden
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, Identitäten
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
ms.openlocfilehash: 87ac6194374e8e042cf9d00271b17dd8bb785d64
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145349"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu Authentifizierungsaktivitäten, die über Ihr lokales Active Directory erfolgt, das von Microsoft Defender für Identitäts- und Authentifizierungsaktivitäten im Zusammenhang mit microsoft-Onlinediensten erfasst wird, die von Microsoft Cloud App Security erfasst `IdentityLogonEvents` werden. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den Ereignistypen (Werten), die von einer Tabelle unterstützt werden, finden Sie in der integrierten Schemareferenz, die im `ActionType` Security Center verfügbar ist. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

>[!NOTE]
>Diese Tabelle enthält Azure Active Directory (AD)-Anmeldeaktivitäten, die von Cloud App Security nachverfolgt werden, insbesondere interaktive Anmeldungen und Authentifizierungsaktivitäten mithilfe von ActiveSync und anderen Legacyprotokollen. Nicht interaktive Anmeldungen, die in dieser Tabelle nicht verfügbar sind, können im Azure AD-Überwachungsprotokoll angezeigt werden. [Weitere Informationen zum Verbinden von Cloud App Security mit Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. Details finden Sie in der [In-Portal-Schemareferenz.](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `LogonType` | string | Typ der Anmeldesitzung, insbesondere:<br><br> - **Interaktiv** – Benutzer interagiert über die lokale Tastatur und den Bildschirm physisch mit dem Computer.<br><br> - **Remote interaktive Anmeldungen (RDP):** Benutzer interagiert remote mit dem Computer mithilfe von Remotedesktop, Terminaldiensten, Remoteunterstützung oder anderen RDP-Clients.<br><br> - **Netzwerk** – Sitzung, die initiiert wird, wenn über PsExec auf den Computer zugegriffen wird oder wenn auf freigegebene Ressourcen auf dem Computer zugegriffen wird, z. B. Drucker und freigegebene Ordner<br><br> - **Batch** – Von geplanten Vorgängen initiierte Sitzung<br><br> - **Dienst** – Sitzung, die von Diensten initiiert wird, während sie gestartet werden |
| `Application` | string | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `Protocol` | string | Verwendetes Netzwerkprotokoll |
| `FailureReason` | string | Informationen, die erläutern, warum die aufgezeichnete Aktion fehlgeschlagen ist |
| `AccountName` | string | Benutzername des Kontos |
| `AccountDomain` | string | Domäne des Kontos |
| `AccountUpn` | string | Benutzerprinzipalname (UPN) des Kontos |
| `AccountSid` | string | Sicherheits-ID (SID) des Kontos |
| `AccountObjectId` | string | Eindeutiger Bezeichner für das Konto in Azure AD |
| `AccountDisplayName` | string | Name des Kontobenutzers, der im Adressbuch angezeigt wird. In der Regel eine Kombination aus einem Vor- oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen. |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Geräts |
| `DeviceType` | string | Gerätetyp |
| `OSPlatform` | string | Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. |
| `IPAddress` | string | Dem Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse |
| `Port` | string | Während der Kommunikation verwendeter TCP-Port |
| `DestinationDeviceName` | string | Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `DestinationIPAddress` | string | Die IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `DestinationPort` | string | Zielport der zugehörigen Netzwerkkommunikation |
| `TargetDeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Geräts, auf das die aufgezeichnete Aktion angewendet wurde |
| `TargetAccountDisplayName` | string | Anzeigename des Kontos, auf das die aufgezeichnete Aktion angewendet wurde |
| `Location` | string | Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist |
| `Isp` | string | Internetdienstanbieter (Internet Service Provider, ISP), der der Endpunkt-IP-Adresse zugeordnet ist |
| `ReportId` | long | Eindeutiger Bezeichner für das Ereignis |
| `AdditionalFields` | string | Zusätzliche Informationen über die Entität oder das Ereignis |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

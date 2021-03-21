---
title: IdentityLogonEvents-Tabelle im schema der erweiterten Suche
description: Informationen zu Authentifizierungsereignissen, die von Active Directory in der IdentityLogonEvents-Tabelle des schemas für die erweiterte Suche aufgezeichnet werden
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, identities
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
ms.openlocfilehash: 7426e22fd617e93fbf63748ba38fc705e4c995a9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924410"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Authentifizierungsaktivitäten, die über Ihr lokales Active Directory vorgenommen wurden, das von Microsoft Defender für Identität erfasst wurde, und Authentifizierungsaktivitäten im Zusammenhang mit Microsoft Onlinediensten, die von Microsoft Cloud App Security erfasst `IdentityLogonEvents` wurden. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den von einer Tabelle unterstützten Ereignistypen ( Werte) finden Sie unter Verwendung der integrierten Schemareferenz, die `ActionType` im Security Center verfügbar ist.

>[!NOTE]
>Diese Tabelle enthält Azure Active Directory (AD)-Anmeldeaktivitäten, die von Cloud App Security nachverfolgt werden, insbesondere interaktive Anmeldungen und Authentifizierungsaktivitäten mithilfe von ActiveSync und anderen Legacyprotokollen. Nicht interaktive Anmeldungen, die in dieser Tabelle nicht verfügbar sind, können im Azure AD-Überwachungsprotokoll angezeigt werden. [Weitere Informationen zum Verbinden von Cloud App Security mit Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. Weitere Informationen [finden Sie in der In-Portal-Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `LogonType` | string | Typ der Anmeldesitzung, insbesondere:<br><br> - **Interaktiv** – Benutzer interagiert physisch mit dem Computer mithilfe der lokalen Tastatur und des Bildschirms<br><br> - **Remote-interaktive (RDP)-Anmeldungen** – Benutzer interagiert remote mit dem Computer mithilfe von Remotedesktop, Terminaldiensten, Remoteunterstützung oder anderen RDP-Clients<br><br> - **Netzwerk** – Sitzung, die initiiert wird, wenn über PsExec auf den Computer zugegriffen wird oder wenn auf freigegebene Ressourcen auf dem Computer zugegriffen wird( z. B. Drucker und freigegebene Ordner).<br><br> - **Batch** – Sitzung, die von geplanten Vorgängen initiiert wurde<br><br> - **Dienst** – Sitzung, die von Diensten beim Start initiiert wurde |
| `Application` | string | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `Protocol` | string | Verwendetes Netzwerkprotokoll |
| `FailureReason` | string | Informationen zur Erklärung, warum die aufgezeichnete Aktion fehlgeschlagen ist |
| `AccountName` | string | Benutzername des Kontos |
| `AccountDomain` | string | Domäne des Kontos |
| `AccountUpn` | string | Benutzerprinzipalname (UPN) des Kontos |
| `AccountSid` | string | Security Identifier (SID) des Kontos |
| `AccountObjectId` | string | Eindeutige ID für das Konto in Azure AD |
| `AccountDisplayName` | string | Name des Kontobenutzers, der im Adressbuch angezeigt wird. In der Regel eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen. |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Geräts |
| `DeviceType` | string | Gerätetyp |
| `OSPlatform` | string | Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. |
| `IPAddress` | string | DEM Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse |
| `Port` | string | WÄHREND der Kommunikation verwendeter TCP-Port |
| `DestinationDeviceName` | string | Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `DestinationIPAddress` | string | IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `DestinationPort` | string | Zielport der zugehörigen Netzwerkkommunikation |
| `TargetDeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Geräts, auf das die aufgezeichnete Aktion angewendet wurde |
| `TargetAccountDisplayName` | string | Anzeigename des Kontos, auf das die aufgezeichnete Aktion angewendet wurde |
| `Location` | string | Stadt, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist |
| `Isp` | string | Internetdienstanbieter (Internet Service Provider, ISP), der der Endpunkt-IP-Adresse zugeordnet ist |
| `ReportId` | long | Eindeutiger Bezeichner für das Ereignis |
| `AdditionalFields` | string | Zusätzliche Informationen zur Entität oder zum Ereignis |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
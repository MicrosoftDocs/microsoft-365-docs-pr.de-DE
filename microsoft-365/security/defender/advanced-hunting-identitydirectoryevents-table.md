---
title: IdentityDirectoryEvents-Tabelle im schema der erweiterten Suche
description: Weitere Informationen zu Domänencontroller- und Active Directory-Ereignissen finden Sie in der IdentityDirectoryEvents-Tabelle des schemas für die erweiterte Suche.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityDirectoryEvents, Domänencontroller, Active Directory, Microsoft Defender for Identity, identities
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
ms.openlocfilehash: b42ff09f1e363f115ecc06c361c8386b328b0bcb
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933001"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die Tabelle im Schema der erweiterten Suche enthält Ereignisse, die einen lokalen Domänencontroller mit `IdentityDirectoryEvents` Active Directory [](advanced-hunting-overview.md) (AD) enthalten. Diese Tabelle erfasst verschiedene identitätsbezogene Ereignisse, z. B. Kennwortänderungen, Kennwortablauf und Benutzerprinzipalnamen(UPN) Änderungen. Außerdem werden Systemereignisse auf dem Domänencontroller erfasst, z. B. das Planen von Aufgaben und die PowerShell-Aktivität. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den von einer Tabelle unterstützten Ereignistypen ( Werte) finden Sie unter Verwendung der integrierten Schemareferenz, die `ActionType` im Security Center verfügbar ist.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. Weitere Informationen [finden Sie in der In-Portal-Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | Zeichenfolge | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `TargetAccountUpn` | Zeichenfolge | Benutzerprinzipalname (UPN) des Kontos, auf das die aufgezeichnete Aktion angewendet wurde |
| `TargetAccountDisplayName` | Zeichenfolge | Anzeigename des Kontos, auf das die aufgezeichnete Aktion angewendet wurde |
| `TargetDeviceName` | Zeichenfolge | Vollqualifizierter Domänenname (FQDN) des Geräts, auf das die aufgezeichnete Aktion angewendet wurde |
| `DestinationDeviceName` | Zeichenfolge | Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `DestinationIPAddress` | Zeichenfolge | IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `DestinationPort` | Zeichenfolge | Zielport der Aktivität |
| `Protocol` | Zeichenfolge | Während der Kommunikation verwendetes Protokoll |
| `AccountName` | Zeichenfolge | Benutzername des Kontos |
| `AccountDomain` | Zeichenfolge | Domäne des Kontos |
| `AccountUpn` | Zeichenfolge | Benutzerprinzipalname (UPN) des Kontos |
| `AccountSid` | Zeichenfolge | Security Identifier (SID) des Kontos |
| `AccountObjectId` | Zeichenfolge | Eindeutige ID für das Konto in Azure Active Directory |
| `AccountDisplayName` | Zeichenfolge | Name des Kontobenutzers, der im Adressbuch angezeigt wird. In der Regel eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen. |
| `DeviceName` | Zeichenfolge | Vollqualifizierter Domänenname (FQDN) des Geräts |
| `IPAddress` | Zeichenfolge | Dem Gerät während der Kommunikation zugewiesene IP-Adresse |
| `Port` | Zeichenfolge | WÄHREND der Kommunikation verwendeter TCP-Port |
| `Location` | Zeichenfolge | Stadt, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist |
| `ISP` | Zeichenfolge | Internetdienstanbieter, der der IP-Adresse zugeordnet ist |
| `ReportId` | long | Eindeutiger Bezeichner für das Ereignis |
| `AdditionalFields` | Zeichenfolge | Zusätzliche Informationen zur Entität oder zum Ereignis |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

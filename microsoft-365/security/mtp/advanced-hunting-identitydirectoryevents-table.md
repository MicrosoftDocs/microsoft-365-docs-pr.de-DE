---
title: IdentityDirectoryEvents-Tabelle im Advanced Hunting-Schema
description: Informationen zu Domänencontroller-und Active Directory Ereignissen in der IdentityDirectoryEvents-Tabelle des Advanced Hunting-Schemas
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, IdentityDirectoryEvents, Domänencontroller, Active Directory, Azure ATP, Identitäten
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
ms.openlocfilehash: d93ef3eb3bbf6def0f633aa0f69032e37d10c4c9
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430376"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Die `IdentityDirectoryEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Ereignisse, die einen lokalen Domänencontroller mit Active Directory (AD) umfassen. In dieser Tabelle werden verschiedene identitätsbezogene Ereignisse erfasst, wie Kennwortänderungen, Kennwortablauf und Benutzerprinzipalnamen (User Principal Name, UPN) geändert. Außerdem werden Systemereignisse auf dem Domänencontroller erfasst, wie die Planung von Aufgaben und die PowerShell-Aktivität. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den `ActionType` von einer Tabelle unterstützten Ereignistypen (Values) finden Sie in der [integrierten Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) , die im Sicherheitscenter verfügbar ist.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. Details finden Sie [in der in-Portal-Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) . |
| `Application` | string | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `TargetAccountUpn` | string | Benutzerprinzipalname (User Principal Name, UPN) des Kontos, auf das die aufgezeichnete Aktion angewendet wurde |
| `TargetAccountDisplayName` | string | Anzeigename des Kontos, auf das die aufgezeichnete Aktion angewendet wurde |
| `TargetDeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Geräts, auf das die aufgezeichnete Aktion angewendet wurde |
| `DestinationDeviceName` | string | Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `DestinationIPAddress` | string | IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `DestinationPort` | string | Ziel Port der Aktivität |
| `Protocol` | string | Während der Kommunikation verwendete Protokolle |
| `AccountName` | string | Benutzername des Kontos |
| `AccountDomain` | string | Domäne des Kontos |
| `AccountUpn` | string | Benutzerprinzipalname (UPN) des Kontos |
| `AccountSid` | string | Sicherheits-ID (SID) des Kontos |
| `AccountObjectId` | string | Eindeutiger Bezeichner für das Konto in Azure Active Directory |
| `AccountDisplayName` | string | Name des Kontobenutzers, der im Adressbuch angezeigt wird. Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen. |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Geräts |
| `IPAddress` | string | Dem Gerät während der Kommunikation zugewiesene IP-Adresse |
| `Port` | string | Während der Kommunikation verwendeter TCP-Port |
| `Location` | string | Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist |
| `ISP` | string | Internet Dienstanbieter, der der IP-Adresse zugeordnet ist |
| `ReportId` | long | Eindeutiger Bezeichner für das Ereignis |
| `AdditionalFields` | string | Zusätzliche Informationen zur Entität oder zum Ereignis |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suchen auf Geräten, in E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

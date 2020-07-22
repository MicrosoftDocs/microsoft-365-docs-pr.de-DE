---
title: IdentityQueryEvents-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über Active Directory Abfrage Ereignisse in der IdentityQueryEvents-Tabelle des Advanced Hunting-Schemas.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, Identitäten, LDAP-Abfragen
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
ms.openlocfilehash: 436c4d7306f9f5febd614489090a0a10929ba3c9
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204875"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

**Gilt für:**
- Microsoft Threat Protection

Die `IdentityQueryEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Abfragen, die für Active Directory-Objekte wie Benutzer, Gruppen, Geräte und Domänen ausgeführt werden. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. |
| `Application` | string | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `QueryType` | string | Typ der Abfrage, wie Abfragegruppe, QueryUser oder EnumerateUsers |
| `QueryTarget` | string | Name des Benutzers, der Gruppe, des Geräts, der Domäne oder eines beliebigen anderen Entitätstyps, der abgefragt wird |
| `Query` | string | Zum Ausführen der Abfrage verwendete Zeichenfolge |
| `Protocol` | string | Während der Kommunikation verwendete Protokolle |
| `AccountName` | string | Benutzername des Kontos |
| `AccountDomain` | string | Domäne des Kontos |
| `AccountUpn` | string | Benutzerprinzipalname (UPN) des Kontos |
| `AccountSid` | string | Sicherheits-ID (SID) des Kontos |
| `AccountObjectId` | string | Eindeutiger Bezeichner für das Konto in Azure AD |
| `AccountDisplayName` | string | Name des Kontobenutzers, der im Adressbuch angezeigt wird. Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen. |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Endpunkts |
| `IPAddress` | string | Dem Endpunkt zugewiesene IP-Adresse und wird während der zugehörigen Netzwerkkommunikation verwendet |
| `DestinationDeviceName` | string | Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `DestinationIPAddress` | string | IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `TargetDeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Geräts, auf das die aufgezeichnete Aktion angewendet wurde |
| `TargetAccountUpn` | string | Benutzerprinzipalname (User Principal Name, UPN) des Kontos, auf das die aufgezeichnete Aktion angewendet wurde |
| `TargetAccountDisplayName` | string | Anzeigename des Kontos, auf das die aufgezeichnete Aktion angewendet wurde |
| `Location` | string | Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist |
| `ReportId` | long | Eindeutiger Bezeichner für das Ereignis |
| `AdditionalFields` | string | Zusätzliche Informationen zur Entität oder zum Ereignis |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche nach Bedrohungen auf Geräten und in E-Mails](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

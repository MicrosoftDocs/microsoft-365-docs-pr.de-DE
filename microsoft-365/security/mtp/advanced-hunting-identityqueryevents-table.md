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
ms.openlocfilehash: 3b2459d0d90f6160bcbac7efbb5c0cc0683ae8c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196809"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Die `IdentityQueryEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Abfragen, die für Active Directory-Objekte wie Benutzer, Gruppen, Geräte und Domänen ausgeführt werden. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den `ActionType` von einer Tabelle unterstützten Ereignistypen (Values) finden Sie in der [integrierten Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) , die im Sicherheitscenter verfügbar ist.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. Details finden Sie [in der in-Portal-Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) . |
| `Application` | Zeichenfolge | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `QueryType` | Zeichenfolge | Typ der Abfrage, wie Abfragegruppe, QueryUser oder EnumerateUsers |
| `QueryTarget` | Zeichenfolge | Name des Benutzers, der Gruppe, des Geräts, der Domäne oder eines beliebigen anderen Entitätstyps, der abgefragt wird |
| `Query` | Zeichenfolge | Zum Ausführen der Abfrage verwendete Zeichenfolge |
| `Protocol` | Zeichenfolge | Während der Kommunikation verwendete Protokolle |
| `AccountName` | Zeichenfolge | Benutzername des Kontos |
| `AccountDomain` | Zeichenfolge | Domäne des Kontos |
| `AccountUpn` | Zeichenfolge | Benutzerprinzipalname (UPN) des Kontos |
| `AccountSid` | Zeichenfolge | Sicherheits-ID (SID) des Kontos |
| `AccountObjectId` | Zeichenfolge | Eindeutiger Bezeichner für das Konto in Azure AD |
| `AccountDisplayName` | Zeichenfolge | Name des Kontobenutzers, der im Adressbuch angezeigt wird. Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen. |
| `DeviceName` | Zeichenfolge | Vollqualifizierter Domänenname (FQDN) des Endpunkts |
| `IPAddress` | Zeichenfolge | Dem Endpunkt zugewiesene IP-Adresse und wird während der zugehörigen Netzwerkkommunikation verwendet |
| `DestinationDeviceName` | Zeichenfolge | Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `DestinationIPAddress` | Zeichenfolge | IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat |
| `TargetDeviceName` | Zeichenfolge | Vollqualifizierter Domänenname (FQDN) des Geräts, auf das die aufgezeichnete Aktion angewendet wurde |
| `TargetAccountUpn` | Zeichenfolge | Benutzerprinzipalname (User Principal Name, UPN) des Kontos, auf das die aufgezeichnete Aktion angewendet wurde |
| `TargetAccountDisplayName` | Zeichenfolge | Anzeigename des Kontos, auf das die aufgezeichnete Aktion angewendet wurde |
| `Location` | Zeichenfolge | Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist |
| `ReportId` | long | Eindeutiger Bezeichner für das Ereignis |
| `AdditionalFields` | Zeichenfolge | Zusätzliche Informationen zur Entität oder zum Ereignis |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suchen auf Geräten, in E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

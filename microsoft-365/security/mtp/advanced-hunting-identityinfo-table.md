---
title: Tabelle "IdentityInfo" im Schema "Erweiterte Suche"
description: Informationen zu Benutzerkontoinformationen in der Tabelle "IdentityInfo" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AccountInfo, IdentityInfo, Konto
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
ms.openlocfilehash: 6604e6d48e277e840b87ddc461580bcb69dd1bc7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929910"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu Benutzerkonten, die von verschiedenen `IdentityInfo` Diensten, einschließlich Azure Active Directory, [](advanced-hunting-overview.md) erhalten wurden. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!NOTE]
>Diese Tabelle wurde umbenannt von `AccountInfo` . Während der Umbenennung werden alle im Portal gespeicherten Abfragen automatisch aktualisiert. Überprüfen Sie Abfragen, die Sie an anderer Stelle gespeichert haben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Eindeutiger Bezeichner für das Konto in Azure AD |
| `AccountUpn` | string | Benutzerprinzipalname (UPN) des Kontos |
| `OnPremSid` | string | Lokale Sicherheits-ID (SID) des Kontos |
| `CloudSid` | string | Cloudsicherheits-ID des Kontos |
| `GivenName` | string | Vorname oder Vorname des Kontobenutzers |
| `Surname` | string | Nachname, Familienname oder Nachname des Kontobenutzers |
| `AccountDisplayName` | string | Name des Kontobenutzers, der im Adressbuch angezeigt wird. In der Regel eine Kombination aus einem Vor- oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen. |
| `Department` | string | Name der Abteilung, der der Kontobenutzer angehört |
| `JobTitle` | string | Job title of the account user |
| `AccountName` | string | Benutzername des Kontos |
| `AccountDomain` | string | Domäne des Kontos |
| `EmailAddress` | string | Die SMTP-Adresse des Kontos |
| `SipProxyAddress` | string | Voice over IP (VOIP)-SIP-Adresse (Session Initiation Protocol) des Kontos |
| `City` | string | Ort, in dem sich der Kontobenutzer befindet |
| `Country` | string | Land/Region, in dem sich der Kontobenutzer befindet |
| `IsAccountEnabled` | Boolescher Wert | Gibt an, ob das Konto aktiviert ist oder nicht. |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

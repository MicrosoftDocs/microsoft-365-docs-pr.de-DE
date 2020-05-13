---
title: IdentityInfo-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über Benutzerkontoinformationen in der IdentityInfo-Tabelle des Advanced Hunting-Schemas.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, accountinfo, IdentityInfo, Konto
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
ms.openlocfilehash: 12f8d0995d00daffe8a1ca1c2c8d9dfe25a11581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209775"
---
# <a name="identityinfo"></a>IdentityInfo

**Gilt für:**
- Microsoft Threat Protection

Die `IdentityInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Benutzerkonten, die von verschiedenen Diensten abgerufen wurden, einschließlich Azure Active Directory. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!NOTE]
>Diese Tabelle wurde umbenannt aus `AccountInfo` . Während der Namensänderung werden alle im Portal gespeicherten Abfragen automatisch aktualisiert. Überprüfen Sie Abfragen, die Sie an einer anderen Stelle gespeichert haben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Eindeutiger Bezeichner für das Konto in Azure AD |
| `AccountUpn` | string | Benutzerprinzipalname (UPN) des Kontos |
| `OnPremSid` | string | Lokale Sicherheits-ID (SID) des Kontos |
| `CloudSid` | string | Cloud-Sicherheits-ID des Kontos |
| `GivenName` | string | Vorname oder Vorname des Kontobenutzers |
| `Surname` | string | Nachname, Familienname oder Nachname des Kontobenutzers |
| `AccountDisplayName` | string | Name des Kontobenutzers, der im Adressbuch angezeigt wird. Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen. |
| `Department` | string | Name der Abteilung, zu der der Benutzer des Kontos gehört |
| `JobTitle` | string | Position des Kontobenutzers |
| `AccountName` | string | Benutzername des Kontos |
| `AccountDomain` | string | Domäne des Kontos |
| `EmailAddress` | string | SMTP-Adresse des Kontos |
| `SipProxyAddress` | string | SIP-Adresse (Voice of over IP (VoIP) Session Initiation Protocol) des Kontos |
| `City` | string | Ort, an dem sich der Benutzer des Kontos befindet |
| `Country` | string | Land/Region, in dem sich der Benutzer des Kontos befindet |
| `IsAccountEnabled` | boolean | Gibt an, ob das Konto aktiviert ist oder nicht. |

## <a name="related-topics"></a>Verwandte Themen
- [Vorbeugende Suche nach Bedrohungen](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche nach Bedrohungen auf Geräten und in E-Mails](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

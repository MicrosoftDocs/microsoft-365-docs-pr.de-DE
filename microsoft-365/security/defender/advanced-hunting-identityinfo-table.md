---
title: IdentityInfo-Tabelle im schema der erweiterten Suche
description: Informationen zu Benutzerkonteninformationen in der IdentityInfo-Tabelle des schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AccountInfo, IdentityInfo, Konto
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
ms.openlocfilehash: d7e1ad4d10c3b71a04421d92304dc2bfcb6147da
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498200"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Benutzerkonten, die von verschiedenen `IdentityInfo` Diensten, einschließlich Azure Active Directory, [](advanced-hunting-overview.md) erhalten wurden. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!NOTE]
>Diese Tabelle wurde von `AccountInfo` umbenannt. Während der Umbenennung werden alle im Portal gespeicherten Abfragen automatisch aktualisiert. Überprüfen Sie Abfragen, die Sie an anderer Stelle gespeichert haben.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Eindeutige ID für das Konto in Azure AD |
| `AccountUpn` | Zeichenfolge | Benutzerprinzipalname (UPN) des Kontos |
| `OnPremSid` | Zeichenfolge | Lokale Sicherheits-ID (SID) des Kontos |
| `CloudSid` | Zeichenfolge | Cloudsicherheits-ID des Kontos |
| `GivenName` | Zeichenfolge | Vorname oder Vorname des Kontobenutzers |
| `Surname` | Zeichenfolge | Nachname, Familienname oder Nachname des Kontobenutzers |
| `AccountDisplayName` | Zeichenfolge | Name des Kontobenutzers, der im Adressbuch angezeigt wird. In der Regel eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen. |
| `Department` | Zeichenfolge | Name der Abteilung, zu der der Kontobenutzer gehört |
| `JobTitle` | Zeichenfolge | Auftragstitel des Kontobenutzers |
| `AccountName` | Zeichenfolge | Benutzername des Kontos |
| `AccountDomain` | Zeichenfolge | Domäne des Kontos |
| `EmailAddress` | Zeichenfolge | SMTP-Adresse des Kontos |
| `SipProxyAddress` | Zeichenfolge | Voice over IP (VOIP) Session Initiation Protocol (SIP)-Adresse des Kontos |
| `City` | Zeichenfolge | Ort, in dem sich der Kontobenutzer befindet |
| `Country` | Zeichenfolge | Land/Region, in dem sich der Kontobenutzer befindet |
| `IsAccountEnabled` | boolean | Gibt an, ob das Konto aktiviert ist oder nicht |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)

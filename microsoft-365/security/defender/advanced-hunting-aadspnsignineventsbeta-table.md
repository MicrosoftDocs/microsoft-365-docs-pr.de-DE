---
title: AADSpnSignInEventsBeta-Tabelle im Schema für die erweiterte Suche
description: Erfahren Sie mehr über Informationen im Zusammenhang mit Azure Active Directory Anmeldeereignistabelle für dienstprinzipale und verwaltete Identitäten des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberbedrohungen, Microsoft 365 Defender, Microsoft 365, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AlertInfo, Warnung, Entitäten, Nachweis, Datei, IP-Adresse, Gerät, Computer, Benutzer, Konto, Identität, AAD
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
ms.openlocfilehash: 6aa709fe4534bf049c6f8c097bc4bd85a9d6793b
ms.sourcegitcommit: 93eeaefc0d509c75e4c2210029155298ecca7583
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53347907"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Gilt für:**

- Microsoft 365 Defender

>[!IMPORTANT]
> Die `AADSpnSignInEventsBeta` Tabelle befindet sich derzeit in der Betaversion und wird kurzfristig angeboten, damit Sie Azure Active Directory (AAD)-Dienstprinzipal- und verwaltete Identitätsanmeldungsereignisse durchsuchen können. Wir werden schließlich alle Anmeldeschemainformationen in die `IdentityLogonEvents` Tabelle verschieben.



Die `AADSpnSignInEventsBeta` Tabelle im Schema für die erweiterte Suche enthält Informationen zu Azure Active Directory Dienstprinzipal- und verwalteten Identitätsanmeldungen. Weitere Informationen zu den verschiedenen Arten von Anmeldungen finden Sie in [Azure Active Directory Anmeldeaktivitätsberichten – Vorschau.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Spaltenname | Datentyp | Beschreibung |
|-----|-----|-----|
| `Timestamp` | Datum/Uhrzeit | Datum und Uhrzeit, wann der Datensatz generiert wurde |
| `Application` | string | Anwendung, die die aufgezeichnete Aktion ausgeführt hat |
| `ApplicationId` | string | Eindeutiger Bezeichner für die Anwendung |
| `IsManagedIdentity`    | Boolescher Wert       | Gibt an, ob die Anmeldung durch eine verwaltete Identität initiiert wurde. |
| `ErrorCode`    | Ganzzahl | Enthält den Fehlercode, wenn ein Anmeldefehler auftritt. Eine Beschreibung eines bestimmten Fehlercodes finden Sie unter <https://aka.ms/AADsigninsErrorCodes> . |
| `CorrelationId`        | string        | Eindeutiger Bezeichner des Anmeldeereignisses |
| `ServicePrincipalName` | string        | Name des Dienstprinzipals, der die Anmeldung initiiert hat  |
| `ServicePrincipalId`   | string        | Eindeutiger Bezeichner des Dienstprinzipals, der die Anmeldung initiiert hat  |
| `ResourceDisplayName`  | string        | Anzeigename der Ressource, auf die zugegriffen wird  |
| `ResourceId`           | string        | Eindeutiger Bezeichner der Ressource, auf die zugegriffen wird  |
| `ResourceTenantId`     | string        | Eindeutiger Bezeichner des Mandanten der Ressource, auf die zugegriffen wird |
| `IPAddress`            | string        | Ip-Adresse, die dem Endpunkt zugewiesen und während der zugehörigen Netzwerkkommunikation verwendet wird  |
| `Country`          | string        | Aus zwei Buchstaben bestehender Code, der das Land angibt, in dem die Client-IP-Adresse geolokal ist |
| `State`                | string        | Status, in dem die Anmeldung stattgefunden hat, sofern verfügbar |
| `City`                 | string        | Ort, in dem sich der Kontobenutzer befindet  |
| `Latitude`             | string        | Die Nord-Nach-Süd-Koordinaten des Anmeldestandorts |
| `Longitude`            | string        | Die Ost-Nach-West-Koordinaten des Anmeldestandorts |
| `RequestId`            | string        | Eindeutiger Bezeichner der Anforderung |
|`ReportId` | string | Eindeutiger Bezeichner für das Ereignis |

 

## <a name="related-articles"></a>Verwandte Artikel

-   [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
-   [Übersicht über die erweiterte Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Lernen der Abfragesprache](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Grundlegendes zum Schema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

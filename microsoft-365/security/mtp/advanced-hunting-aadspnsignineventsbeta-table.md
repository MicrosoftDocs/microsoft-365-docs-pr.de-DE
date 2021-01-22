---
title: Tabelle "AADSpnSignInEventsBeta" im Schema "Erweiterte Suche"
description: Informationen zu Informationen zu Azure Active Directory-Dienstprinzipal- und verwalteten Identitäts-Anmeldeereignissen– Tabelle des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, AlertInfo, Warnung, Entitäten, Nachweis, Datei, IP-Adresse, Gerät, Computer, Benutzer, Konto, Identität, AAD
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 172c400df3adea70a2e2d2e37547fa39e0d3b9cf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928618"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Gilt für:**

- Microsoft 365 Defender

>[!IMPORTANT]
> Die Tabelle befindet sich derzeit in der Betaversion und wird kurzfristig angeboten, damit Sie durch Azure Active Directory (AAD)-Dienstprinzipal- und verwaltete Identitäts-Anmeldeereignisse suchen `AADSpnSignInEventsBeta` können. Schließlich werden wir alle Anmeldeschemainformationen in die Tabelle `IdentityLogonEvents` verschieben.<br><br>
> Kunden, die über die integrierte Microsoft Defender for Endpoint-Lösung des Azure Security Center auf Microsoft 365 Defender zugreifen können, aber nicht über Lizenzen für Microsoft Defender für Office, Microsoft Defender for Identity oder Microsoft Cloud App Security verfügen, können dieses Schema nicht anzeigen. 



Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu Azure Active Directory-Dienstprinzipal- und `AADSpnSignInEventsBeta` verwalteten Identitäts-Anmeldungen. Weitere Informationen zu den verschiedenen Arten von Anmeldungen finden Sie in Azure Active Directory-Anmeldeaktivitätsberichten [– Vorschau.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Spaltenname     | Datentyp | Beschreibung   |
| ----- | ----- | ---- |
| `Timestamp` | Datum/Uhrzeit      | Datum und Uhrzeit, wann der Datensatz generiert wurde                                                                                                     |
| `Application`          | string        | Anwendung, die die aufgezeichnete Aktion ausgeführt hat                                                                                                   |
| `ApplicationId`        | string        | Eindeutiger Bezeichner für die Anwendung                                                                                                           |
| `IsManagedIdentity`    | Boolescher Wert       | Gibt an, ob die Anmeldung von einer verwalteten Identität initiiert wurde.                                                                               |
| `ErrorCode`            | int        | Enthält den Fehlercode, wenn ein Anmeldefehler auftritt. Eine Beschreibung eines bestimmten Fehlercodes finden Sie unter <https://aka.ms/AADsigninsErrorCodes> . |
| `CorrelationId`        | string        | Eindeutiger Bezeichner des Anmeldeereigniss                                                                                                          |
| `ServicePrincipalName` | string        | Name des Dienstprinzipal, der die Anmeldung initiiert hat                                                                                        |
| `ServicePrincipalId`   | string        | Eindeutiger Bezeichner des Dienstprinzipal, der die Anmeldung initiiert hat                                                                           |
| `ResourceDisplayName`  | string        | Anzeigename der Ressource, auf die zugegriffen wird                                                                                                           |
| `ResourceId`           | string        | Eindeutiger Bezeichner der Ressource, auf die zugegriffen wird                                                                                                      |
| `ResourceTenantId`     | string        | Eindeutiger Bezeichner des Mandanten der Ressource, auf die zugegriffen wird                                                                                        |
| `IPAddress`            | string        | Dem Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse                                                              |
| `CountryCode`          | string        | Aus zwei Buchstaben bestehter Code, der das Land angibt, in dem die Client-IP-Adresse geolokaliert ist                                                                |
| `State`                | string        | Status, in dem die Anmeldung erfolgt ist( sofern verfügbar)                                                                                                  |
| `City`                 | string        | Ort, in dem sich der Kontobenutzer befindet                                                                                                          |
| `Latitude`             | string        | Die Koordinaten von Nord nach Süd des Anmeldestandorts                                                                                          |
| `Longitude`            | string        | Die Ost-West-Koordinaten des Anmeldestandorts                                                                                            |
| `RequestId`            | string        | Eindeutiger Bezeichner der Anforderung                                                                                                                |
|`ReportId` | string | Eindeutiger Bezeichner für das Ereignis | 

 

## <a name="related-articles"></a>Verwandte Artikel

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [Übersicht über die erweiterte Suche](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Lernen der Abfragesprache](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Grundlegendes zum Schema](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)


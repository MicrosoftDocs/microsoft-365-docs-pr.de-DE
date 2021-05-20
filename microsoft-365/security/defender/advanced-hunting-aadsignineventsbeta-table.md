---
title: AADSignInEventsBeta-Tabelle im schema der erweiterten Suche
description: Informationen zu Informationen, die Azure Active Directory Tabelle mit Anmeldeereignissen des schemas für erweiterte Suche zugeordnet sind
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, file, IP address, device, machine, user, account, identity, AAD
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
ms.openlocfilehash: 704752951c453a3fe872b814e7364ef1699226bf
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582980"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Gilt für:**

- Microsoft 365 Defender

>[!IMPORTANT]
> Die Tabelle befindet sich derzeit in der Betaversion und wird kurzfristig angeboten, damit Sie Azure Active Directory `AADSignInEventsBeta` (AAD)-Anmeldeereignisse nachsuchen können. Wir verschieben schließlich alle Anmeldeschemainformationen in die `IdentityLogonEvents` Tabelle.

 

Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Azure Active Directory interaktiven und `AADSignInEventsBeta` nicht interaktiven Anmeldungen. Erfahren Sie mehr über Anmeldungen in [Azure Active Directory Anmeldeaktivitätsberichte - Vorschau](/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.
Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

 

 

| Spaltenname                 | Datentyp | Beschreibung          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | Datum/Uhrzeit      | Datum und Uhrzeit, wann der Datensatz generiert wurde                                                                                                                                         |
| `Application`                     | string        | Anwendung, die die aufgezeichnete Aktion ausgeführt hat                                                                                                                                       |
| `ApplicationId`                   | Zeichenfolge        | Eindeutige ID für die Anwendung                                                                                                                                               |
| `LogonType`                       | Zeichenfolge        | Typ der Anmeldesitzung, insbesondere interaktiv, remote interaktiv (RDP), Netzwerk, Batch und Dienst                                                                              |
| `ErrorCode`                       | int        | Enthält den Fehlercode, wenn ein Anmeldefehler auftritt. Eine Beschreibung eines bestimmten Fehlercodes finden Sie unter <https://aka.ms/AADsigninsErrorCodes> .                                     |
| `CorrelationId`                   | Zeichenfolge        | Eindeutiger Bezeichner des Anmeldeereigniss                                                                                                                                              |
| `SessionId`                       | Zeichenfolge        | Eindeutige Nummer, die einem Benutzer vom Server einer Website für die Dauer des Besuchs oder der Sitzung zugewiesen wurde                                                                                     |
| `AccountDisplayName`              | Zeichenfolge        | Name des Kontobenutzers, der im Adressbuch angezeigt wird. In der Regel eine Kombination aus einem vor- oder vornamen, einer mittleren Initiale und einem Nachnamen oder Nachnamen.                             |
| `AccountObjectId`                 | Zeichenfolge        | Eindeutige ID für das Konto in Azure AD                                                                                                                                       |
| `AccountUpn`                      | Zeichenfolge        | Benutzerprinzipalname (UPN) des Kontos                                                                                                                                            |
| `IsExternalUser`                  | int        | Gibt an, ob der angemeldete Benutzer extern ist. Mögliche Werte: -1 (nicht festgelegt), 0 (nicht extern), 1 (extern).                                                                   |
| `IsGuestUser`                     | boolean       | Gibt an, ob der angemeldete Benutzer ein Gast im Mandanten ist                                                                                                                  |
| `AlternateSignInName`             | Zeichenfolge        | On-premises user principal name (UPN) of the user signing in to Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | Datum/Uhrzeit        | Datum und Uhrzeit, zu dem der benutzer, der sich zuletzt angemeldet hat, sein Kennwort geändert hat                                                                                                              |
| `ResourceDisplayName`             | Zeichenfolge        | Anzeigename der Ressource, auf die zugegriffen wird                                                                                                                                               |
| `ResourceId`                      | Zeichenfolge        | Eindeutiger Bezeichner der Ressource, auf die zugegriffen wird                                                                                                                                          |
| `ResourceTenantId`                | Zeichenfolge        | Eindeutiger Bezeichner des Mandanten der Ressource, auf die zugegriffen wird                                                                                                                            |
| `DeviceName`                      | string        | Vollqualifizierter Domänenname (FQDN) des Computers                                                                                                                                   |
| `AadDeviceId`                     | string   |      Eindeutige ID für das Gerät in Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | string        | Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.  |
| `DeviceTrustType`                 | string        | Gibt den Vertrauenstyp des angemeldeten Geräts an. Nur für Szenarien mit verwalteten Geräten. Mögliche Werte sind Workplace, AzureAd und ServerAd.                                     |
| `IsManaged`                       | int       | Gibt an, ob das Gerät, das die Anmeldung initiiert hat, ein verwaltetes Gerät (1) oder kein verwaltetes Gerät ist (0)                                                                         |
| `IsCompliant`                     | int       | Gibt an, ob das Gerät, das die Anmeldung initiiert hat, kompatibel (1) oder nicht kompatibel ist (0)                                                                                       |
| `AuthenticationProcessingDetails` | Zeichenfolge        | Details zum Authentifizierungsprozessor                                                                                                                                          |
| `AuthenticationRequirement`       | Zeichenfolge        | Authentifizierungstyp, der für die Anmeldung erforderlich ist. Mögliche Werte: multiFactorAuthentication (MFA war erforderlich) und singleFactorAuthentication (kein MFA erforderlich).                |
| `TokenIssuerType`                 | int        | Gibt an, ob der Tokenherausgeber Azure Active Directory (0) oder Active Directory Federation Services (1) ist.                                                                             |
| `RiskLevelAggregated`                       | int        | Aggregiertes Risikoniveau während der Anmeldung. Mögliche Werte: 0 (aggregierte Risikostufe nicht festgelegt), 1 (keine), 10 (niedrig), 50 (mittel) oder 100 (hoch).                               |
| `RiskDetails`                      | int        | Details zum riskanten Status des angemeldeten Benutzers                                                                                                                            |
| `RiskState`                       | int        | Gibt den riskanten Benutzerstatus an. Mögliche Werte: 0 (keine), 1 (bestätigt sicher), 2 (behoben), 3 (verworfen), 4 (gefährdet) oder 5 (bestätigt gefährdet).                                |
| `UserAgent`                       | Zeichenfolge        | Benutzer-Agent-Informationen aus dem Webbrowser oder einer anderen Clientanwendung                                                                                                             |
| `ClientAppUsed`                   | Zeichenfolge        | Gibt die verwendete Client-App an                                                                                                                                                       |
| `Browser`                         | Zeichenfolge        | Details zur Zur Anmeldung verwendeten Browserversion                                                                                                                            |
| `ConditionalAccessPolicies`       | Zeichenfolge        | Details der Richtlinien für bedingten Zugriff, die auf das Anmeldeereignis angewendet werden                                                                                                             |
| `ConditionalAccessStatus`         | int        | Status der Richtlinien für bedingten Zugriff, die auf die Anmeldung angewendet werden. Mögliche Werte sind 0 (angewendete Richtlinien), 1 (Versuch, Richtlinien anzuwenden fehlgeschlagen) oder 2 (Richtlinien nicht angewendet).      |
| `IPAddress`                       | Zeichenfolge        | DEM Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse                                                                                                  |
| `Country`                     | Zeichenfolge        | Zwei-Buchstaben-Code, der das Land angibt, in dem die Client-IP-Adresse geolokaliert ist                                                                                                    |
| `State`                           | Zeichenfolge        | Status, in dem die Anmeldung erfolgt ist( sofern verfügbar)                                                                                                                                      |
| `City`                            | Zeichenfolge        | Ort, in dem sich der Kontobenutzer befindet                                                                                                                                              |
| `Latitude`                        | Zeichenfolge        | Die Nord-Süd-Koordinaten des Anmeldestandorts                                                                                                                              |
| `Longitude`                       | Zeichenfolge        | Die Ost-West-Koordinaten der Anmeldeposition                                                                                                                                |
| `NetworkLocationDetails`          | Zeichenfolge        | Netzwerkspeicherortdetails des Authentifizierungsprozessors des Anmeldeereigniss                                                                                                       |
| `RequestId`                       | Zeichenfolge        |  Eindeutiger Bezeichner der Anforderung                                                                                                                                                   |
|`ReportId` | Zeichenfolge | Eindeutiger Bezeichner für das Ereignis |

 

 

## <a name="related-articles"></a>Verwandte Artikel

-   [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
-   [Übersicht über die erweiterte Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Lernen der Abfragesprache](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Grundlegendes zum Schema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 
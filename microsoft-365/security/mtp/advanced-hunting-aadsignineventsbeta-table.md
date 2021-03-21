---
title: AADSignInEventsBeta-Tabelle im schema der erweiterten Suche
description: Informationen zu Informationen zur Tabelle mit Azure Active Directory-Anmeldeereignissen des schemas für die erweiterte Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, file, IP address, device, machine, user, account, identity, AAD
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
ms.openlocfilehash: 50f112f6e7198136171d070dc483ad5f84d20d57
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925762"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Gilt für:**

- Microsoft 365 Defender

>[!IMPORTANT]
> Die Tabelle befindet sich derzeit in der Betaversion und wird kurzfristig angeboten, damit Sie Azure `AADSignInEventsBeta` Active Directory (AAD)-Anmeldeereignisse durchsuchen können. Wir verschieben schließlich alle Anmeldeschemainformationen in die `IdentityLogonEvents` Tabelle.<br><br>
> Kunden, die über die integrierte Microsoft Defender for Endpoint-Lösung des Azure Security Centers auf Microsoft 365 Defender zugreifen können, aber keine Lizenzen für Microsoft Defender for Office, Microsoft Defender for Identity oder Microsoft Cloud App Security besitzen, können dieses Schema nicht anzeigen. 

 

Die Tabelle im Schema der erweiterten Suche `AADSignInEventsBeta` enthält Informationen zu interaktiven und nicht interaktiven Azure Active Directory-Anmeldungen. Erfahren Sie mehr über Anmeldungen in [Azure Active Directory-Anmeldeaktivitätsberichten – Vorschau](/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.
Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

 

 

| Spaltenname                 | Datentyp | Beschreibung          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | Datum/Uhrzeit      | Datum und Uhrzeit, wann der Datensatz generiert wurde                                                                                                                                         |
| `Application`                     | string        | Anwendung, die die aufgezeichnete Aktion ausgeführt hat                                                                                                                                       |
| `ApplicationId`                   | string        | Eindeutige ID für die Anwendung                                                                                                                                               |
| `LogonType`                       | string        | Typ der Anmeldesitzung, insbesondere interaktiv, remote interaktiv (RDP), Netzwerk, Batch und Dienst                                                                              |
| `ErrorCode`                       | int        | Enthält den Fehlercode, wenn ein Anmeldefehler auftritt. Eine Beschreibung eines bestimmten Fehlercodes finden Sie unter <https://aka.ms/AADsigninsErrorCodes> .                                     |
| `CorrelationId`                   | string        | Eindeutiger Bezeichner des Anmeldeereigniss                                                                                                                                              |
| `SessionId`                       | string        | Eindeutige Nummer, die einem Benutzer vom Server einer Website für die Dauer des Besuchs oder der Sitzung zugewiesen wurde                                                                                     |
| `AccountDisplayName`              | string        | Name des Kontobenutzers, der im Adressbuch angezeigt wird. In der Regel eine Kombination aus einem vor- oder vornamen, einer mittleren Initiale und einem Nachnamen oder Nachnamen.                             |
| `AccountObjectId`                 | string        | Eindeutige ID für das Konto in Azure AD                                                                                                                                       |
| `AccountUpn`                      | string        | Benutzerprinzipalname (UPN) des Kontos                                                                                                                                            |
| `IsExternalUser`                  | int        | Gibt an, ob der angemeldete Benutzer extern ist. Mögliche Werte: -1 (nicht festgelegt), 0 (nicht extern), 1 (extern).                                                                   |
| `IsGuestUser`                     | boolean       | Gibt an, ob der angemeldete Benutzer ein Gast im Mandanten ist                                                                                                                  |
| `AlternateSignInName`             | string        | On-premises user principal name (UPN) of the user signing in to Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | Datum/Uhrzeit        | Datum und Uhrzeit, zu dem der benutzer, der sich zuletzt angemeldet hat, sein Kennwort geändert hat                                                                                                              |
| `ResourceDisplayName`             | string        | Anzeigename der Ressource, auf die zugegriffen wird                                                                                                                                               |
| `ResourceId`                      | string        | Eindeutiger Bezeichner der Ressource, auf die zugegriffen wird                                                                                                                                          |
| `ResourceTenantId`                | string        | Eindeutiger Bezeichner des Mandanten der Ressource, auf die zugegriffen wird                                                                                                                            |
| `DeviceName`                      | string        | Vollqualifizierter Domänenname (FQDN) des Computers                                                                                                                                   |
| `AadDeviceId`                     | string   |      Eindeutige ID für das Gerät in Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | string        | Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.  |
| `DeviceTrustType`                 | string        | Gibt den Vertrauenstyp des angemeldeten Geräts an. Nur für Szenarien mit verwalteten Geräten. Mögliche Werte sind Workplace, AzureAd und ServerAd.                                     |
| `IsManaged`                       | int       | Gibt an, ob das Gerät, das die Anmeldung initiiert hat, ein verwaltetes Gerät (1) oder kein verwaltetes Gerät ist (0)                                                                         |
| `IsCompliant`                     | int       | Gibt an, ob das Gerät, das die Anmeldung initiiert hat, kompatibel (1) oder nicht kompatibel ist (0)                                                                                       |
| `AuthenticationProcessingDetails` | string        | Details zum Authentifizierungsprozessor                                                                                                                                          |
| `AuthenticationRequirement`       | string        | Authentifizierungstyp, der für die Anmeldung erforderlich ist. Mögliche Werte: multiFactorAuthentication (MFA war erforderlich) und singleFactorAuthentication (kein MFA erforderlich).                |
| `TokenIssuerType`                 | int        | Gibt an, ob der Tokenherausgeber Azure Active Directory (0) oder Active Directory Federation Services (1) ist.                                                                             |
| `RiskLevelAggregated`                       | int        | Aggregiertes Risikoniveau während der Anmeldung. Mögliche Werte: 0 (aggregierte Risikostufe nicht festgelegt), 1 (keine), 10 (niedrig), 50 (mittel) oder 100 (hoch).                               |
| `RiskDetails`                      | int        | Details zum riskanten Status des angemeldeten Benutzers                                                                                                                            |
| `RiskState`                       | int        | Gibt den riskanten Benutzerstatus an. Mögliche Werte: 0 (keine), 1 (bestätigt sicher), 2 (behoben), 3 (verworfen), 4 (gefährdet) oder 5 (bestätigt gefährdet).                                |
| `UserAgent`                       | string        | Benutzer-Agent-Informationen aus dem Webbrowser oder einer anderen Clientanwendung                                                                                                             |
| `ClientAppUsed`                   | string        | Gibt die verwendete Client-App an                                                                                                                                                       |
| `Browser`                         | string        | Details zur Zur Anmeldung verwendeten Browserversion                                                                                                                            |
| `ConditionalAccessPolicies`       | string        | Details der Richtlinien für bedingten Zugriff, die auf das Anmeldeereignis angewendet werden                                                                                                             |
| `ConditionalAccessStatus`         | int        | Status der Richtlinien für bedingten Zugriff, die auf die Anmeldung angewendet werden. Mögliche Werte sind 0 (angewendete Richtlinien), 1 (Versuch, Richtlinien anzuwenden fehlgeschlagen) oder 2 (Richtlinien nicht angewendet).      |
| `IPAddress`                       | string        | DEM Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse                                                                                                  |
| `Country`                     | string        | Zwei-Buchstaben-Code, der das Land angibt, in dem die Client-IP-Adresse geolokaliert ist                                                                                                    |
| `State`                           | string        | Status, in dem die Anmeldung erfolgt ist( sofern verfügbar)                                                                                                                                      |
| `City`                            | string        | Ort, in dem sich der Kontobenutzer befindet                                                                                                                                              |
| `Latitude`                        | string        | Die Nord-Süd-Koordinaten des Anmeldestandorts                                                                                                                              |
| `Longitude`                       | string        | Die Ost-West-Koordinaten der Anmeldeposition                                                                                                                                |
| `NetworkLocationDetails`          | string        | Netzwerkspeicherortdetails des Authentifizierungsprozessors des Anmeldeereigniss                                                                                                       |
| `RequestId`                       | string        |  Eindeutiger Bezeichner der Anforderung                                                                                                                                                   |
|`ReportId` | string | Eindeutiger Bezeichner für das Ereignis |

 

 

## <a name="related-articles"></a>Verwandte Artikel

-   [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
-   [Übersicht über die erweiterte Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Lernen der Abfragesprache](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Grundlegendes zum Schema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 
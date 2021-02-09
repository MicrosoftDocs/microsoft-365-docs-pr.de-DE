---
title: Tabelle "AADSignInEventsBeta" im Schema "Erweiterte Suche"
description: Informationen zu Informationen im Zusammenhang mit der Azure Active Directory-Anmeldeereignisse-Tabelle des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, Datei, IP-Adresse, Gerät, Computer, Benutzer, Konto, Identität, AAD
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
ms.openlocfilehash: 174db150920d2d95c043bb5d6e5a4593ea1ea39d
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145427"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Gilt für:**

- Microsoft 365 Defender

>[!IMPORTANT]
> Die Tabelle befindet sich derzeit in der Betaversion und wird kurzfristig angeboten, damit Sie durch `AADSignInEventsBeta` Azure Active Directory (AAD)-Anmeldeereignisse suchen können. Schließlich werden wir alle Anmeldeschemainformationen in die Tabelle `IdentityLogonEvents` verschieben.<br><br>
> Kunden, die über die integrierte Microsoft Defender for Endpoint-Lösung des Azure Security Center auf Microsoft 365 Defender zugreifen können, aber nicht über Lizenzen für Microsoft Defender für Office, Microsoft Defender for Identity oder Microsoft Cloud App Security verfügen, können dieses Schema nicht anzeigen. 

 

Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu interaktiven und `AADSignInEventsBeta` nicht interaktiven Azure Active Directory-Anmeldungen. Erfahren Sie mehr über Anmeldungen in Azure Active Directory-Anmeldeaktivitätsberichten [– Vorschau.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.
Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

 

 

| Spaltenname                 | Datentyp | Beschreibung          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | Datum/Uhrzeit      | Datum und Uhrzeit, wann der Datensatz generiert wurde                                                                                                                                         |
| `Application`                     | string        | Anwendung, die die aufgezeichnete Aktion ausgeführt hat                                                                                                                                       |
| `ApplicationId`                   | string        | Eindeutiger Bezeichner für die Anwendung                                                                                                                                               |
| `LogonType`                       | string        | Typ der Anmeldesitzung, insbesondere interaktiv, Remote interactive (RDP), Netzwerk, Batch und Dienst                                                                              |
| `ErrorCode`                       | int        | Enthält den Fehlercode, wenn ein Anmeldefehler auftritt. Eine Beschreibung eines bestimmten Fehlercodes finden Sie unter <https://aka.ms/AADsigninsErrorCodes> .                                     |
| `CorrelationId`                   | string        | Eindeutiger Bezeichner des Anmeldeereigniss                                                                                                                                              |
| `SessionId`                       | string        | Eindeutige Nummer, die einem Benutzer vom Server einer Website für die Dauer des Besuchs oder der Sitzung zugewiesen wurde                                                                                     |
| `AccountDisplayName`              | string        | Name des Kontobenutzers, der im Adressbuch angezeigt wird. In der Regel eine Kombination aus einem Vor- oder Vornamen, einem Vornamen und einem Nachnamen oder Nachnamen.                             |
| `AccountObjectId`                 | string        | Eindeutiger Bezeichner für das Konto in Azure AD                                                                                                                                       |
| `AccountUpn`                      | string        | Benutzerprinzipalname (UPN) des Kontos                                                                                                                                            |
| `IsExternalUser`                  | int        | Gibt an, ob der angemeldete Benutzer extern ist. Mögliche Werte: -1 (nicht festgelegt), 0 (nicht extern), 1 (extern).                                                                   |
| `IsGuestUser`                     | boolean       | Gibt an, ob der angemeldete Benutzer ein Gast im Mandanten ist.                                                                                                                  |
| `AlternateSignInName`             | string        | Der lokale Benutzerprinzipalname (UPN) des Benutzers, der sich bei Azure AD an-                                                                                                            |
| `LastPasswordChangeTimestamp`     | Datum/Uhrzeit        | Datum und Uhrzeit der letzten Änderung des Kennworts durch den Angemeldeten                                                                                                              |
| `ResourceDisplayName`             | string        | Anzeigename der Ressource, auf die zugegriffen wird                                                                                                                                               |
| `ResourceId`                      | string        | Eindeutiger Bezeichner der Ressource, auf die zugegriffen wird                                                                                                                                          |
| `ResourceTenantId`                | string        | Eindeutiger Bezeichner des Mandanten der Ressource, auf die zugegriffen wird                                                                                                                            |
| `DeviceName`                      | string        | Vollqualifizierter Domänenname (FQDN) des Computers                                                                                                                                   |
| `AadDeviceId`                     | string   |      Eindeutiger Bezeichner für das Gerät in Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | string        | Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.  |
| `DeviceTrustType`                 | string        | Gibt den Vertrauenstyp des Geräts an, das sich angemeldet hat. Nur für Szenarien mit verwalteten Geräten. Mögliche Werte sind Workplace, AzureAd und ServerAd.                                     |
| `IsManaged`                       | int       | Gibt an, ob das Gerät, das die Anmeldung initiiert hat, ein verwaltetes Gerät (1) oder kein verwaltetes Gerät (0) ist.                                                                         |
| `IsCompliant`                     | int       | Gibt an, ob das Gerät, das die Anmeldung initiiert hat, kompatibel (1) oder nicht kompatibel (0) ist.                                                                                       |
| `AuthenticationProcessingDetails` | string        | Details zum Authentifizierungsprozessor                                                                                                                                          |
| `AuthenticationRequirement`       | string        | Für die Anmeldung erforderlicher Authentifizierungstyp. Mögliche Werte: multiFactorAuthentication (MFA war erforderlich) und singleFactorAuthentication (keine MFA erforderlich).                |
| `TokenIssuerType`                 | int        | Gibt an, ob der Tokenherausgeber Azure Active Directory (0) oder Active Directory Federation Services (1) ist.                                                                             |
| `RiskLevelAggregated`                       | int        | Aggregierte Risikostufe während der Anmeldung. Mögliche Werte: 0 (aggregierte Risikostufe nicht festgelegt), 1 (keine), 10 (niedrig), 50 (mittel) oder 100 (hoch).                               |
| `RiskDetails`                      | int        | Details zum risikoigen Status des angemeldeten Benutzers                                                                                                                            |
| `RiskState`                       | int        | Gibt den riskante Benutzerstatus an. Mögliche Werte: 0 (keine), 1 (bestätigt sicher), 2 (behoben), 3 (verworfen), 4 (gefährdet) oder 5 (als gefährdet bestätigt).                                |
| `UserAgent`                       | string        | Benutzer-Agent-Informationen aus dem Webbrowser oder einer anderen Clientanwendung                                                                                                             |
| `ClientAppUsed`                   | string        | Gibt die verwendete Client-App an.                                                                                                                                                       |
| `Browser`                         | string        | Details zur Version des Browsers, der für die Anmeldung verwendet wird                                                                                                                            |
| `ConditionalAccessPolicies`       | string        | Details zu den Richtlinien für bedingten Zugriff, die auf das Anmeldeereignis angewendet werden                                                                                                             |
| `ConditionalAccessStatus`         | int        | Status der Richtlinien für bedingten Zugriff, die auf die Anmeldung angewendet werden. Mögliche Werte sind 0 (angewendete Richtlinien), 1 (Fehler beim Anwenden von Richtlinien) oder 2 (Richtlinien nicht angewendet).      |
| `IPAddress`                       | string        | Dem Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse                                                                                                  |
| `Country`                     | string        | Aus zwei Buchstaben bestehter Code, der das Land angibt, in dem die Client-IP-Adresse geolokaliert ist                                                                                                    |
| `State`                           | string        | Status, in dem die Anmeldung erfolgt ist( sofern verfügbar)                                                                                                                                      |
| `City`                            | string        | Ort, in dem sich der Kontobenutzer befindet                                                                                                                                              |
| `Latitude`                        | string        | Die Koordinaten von Nord nach Süd des Anmeldestandorts                                                                                                                              |
| `Longitude`                       | string        | Die Ost-West-Koordinaten des Anmeldestandorts                                                                                                                                |
| `NetworkLocationDetails`          | string        | Netzwerkstandortdetails des Authentifizierungsprozessors des Anmeldeereigniss                                                                                                       |
| `RequestId`                       | string        |  Eindeutiger Bezeichner der Anforderung                                                                                                                                                   |
|`ReportId` | string | Eindeutiger Bezeichner für das Ereignis |

 

 

## <a name="related-articles"></a>Verwandte Artikel

-   [AADSpnSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadspnsignineventsbeta-table)
-   [Übersicht über die erweiterte Suche](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Lernen der Abfragesprache](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Grundlegendes zum Schema](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 

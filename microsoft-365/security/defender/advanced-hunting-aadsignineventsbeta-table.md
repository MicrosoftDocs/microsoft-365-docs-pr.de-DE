---
title: AADSignInEventsBeta-Tabelle im Schema für die erweiterte Suche
description: Erfahren Sie mehr über Informationen im Zusammenhang mit Azure Active Directory Anmeldeereignistabelle des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberbedrohungen, Microsoft 365 Defender, Microsoft 365, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, Datei, IP-Adresse, Gerät, Computer, Benutzer, Konto, Identität, AAD
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
ms.openlocfilehash: edc9a1e40275631752ca1252a16071f4b07f07f9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286333"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Die Tabelle befindet sich `AADSignInEventsBeta` derzeit in der Betaversion und wird kurzfristig angeboten, damit Sie Azure Active Directory (AAD)-Anmeldeereignisse durchsuchen können. Wir werden schließlich alle Anmeldeschemainformationen in die `IdentityLogonEvents` Tabelle verschieben.

Die `AADSignInEventsBeta` Tabelle im Schema für die erweiterte Suche enthält Informationen zu Azure Active Directory interaktiven und nicht interaktiven Anmeldungen. Erfahren Sie mehr über Anmeldungen in [Azure Active Directory Anmeldeaktivitätsberichten – Vorschau.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben. Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

<br>

****

|Spaltenname|Datentyp|Beschreibung|
|---|---|---|
|`Timestamp`|Datum/Uhrzeit|Datum und Uhrzeit, wann der Datensatz generiert wurde|
|`Application`|string|Anwendung, die die aufgezeichnete Aktion ausgeführt hat|
|`ApplicationId`|Zeichenfolge|Eindeutiger Bezeichner für die Anwendung|
|`LogonType`|Zeichenfolge|Typ der Anmeldesitzung, insbesondere interaktiv, Remoteinteraktiv (RDP), Netzwerk, Batch und Dienst|
|`ErrorCode`|Ganzzahl|Enthält den Fehlercode, wenn ein Anmeldefehler auftritt. Eine Beschreibung eines bestimmten Fehlercodes finden Sie unter <https://aka.ms/AADsigninsErrorCodes> .|
|`CorrelationId`|Zeichenfolge|Eindeutiger Bezeichner des Anmeldeereignisses|
|`SessionId`|Zeichenfolge|Eindeutige Nummer, die einem Benutzer vom Server einer Website für die Dauer des Besuchs oder der Sitzung zugewiesen wurde|
|`AccountDisplayName`|Zeichenfolge|Name des Kontobenutzers, der im Adressbuch angezeigt wird. In der Regel eine Kombination aus einem bestimmten oder Vornamen, einem Vornamen und einem Nachnamen oder Nachnamen.|
|`AccountObjectId`|Zeichenfolge|Eindeutiger Bezeichner für das Konto in Azure AD|
|`AccountUpn`|Zeichenfolge|Benutzerprinzipalname (UPN) des Kontos|
|`IsExternalUser`|Ganzzahl|Gibt an, ob der angemeldete Benutzer extern ist. Mögliche Werte: -1 (nicht festgelegt), 0 (nicht extern), 1 (extern).|
|`IsGuestUser`|Boolescher Wert|Gibt an, ob der angemeldete Benutzer ein Gast im Mandanten ist.|
|`AlternateSignInName`|Zeichenfolge|Lokaler Benutzerprinzipalname (UPN) des Benutzers, der sich bei Azure AD anmeldet|
|`LastPasswordChangeTimestamp`|Datum/Uhrzeit|Datum und Uhrzeit, zu denen der zuletzt angemeldete Benutzer sein Kennwort geändert hat|
|`ResourceDisplayName`|Zeichenfolge|Anzeigename der Ressource, auf die zugegriffen wird|
|`ResourceId`|Zeichenfolge|Eindeutiger Bezeichner der Ressource, auf die zugegriffen wird|
|`ResourceTenantId`|Zeichenfolge|Eindeutiger Bezeichner des Mandanten der Ressource, auf die zugegriffen wird|
|`DeviceName`|string|Vollqualifizierter Domänenname (FQDN) des Computers|
|`AadDeviceId`|string|Eindeutiger Bezeichner für das Gerät in Azure AD|
|`OSPlatform`|string|Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.|
|`DeviceTrustType`|string|Gibt den Vertrauenstyp des angemeldeten Geräts an. Nur für verwaltete Geräteszenarien. Mögliche Werte sind Workplace, AzureAd und ServerAd.|
|`IsManaged`|Ganzzahl|Gibt an, ob es sich bei dem Gerät, das die Anmeldung initiiert hat, um ein verwaltetes Gerät (1) handelt oder nicht um ein verwaltetes Gerät (0).|
|`IsCompliant`|Ganzzahl|Gibt an, ob das Gerät, das die Anmeldung initiiert hat, konform (1) oder nicht kompatibel (0) ist.|
|`AuthenticationProcessingDetails`|Zeichenfolge|Details zum Authentifizierungsprozessor|
|`AuthenticationRequirement`|Zeichenfolge|Für die Anmeldung erforderlicher Authentifizierungstyp. Mögliche Werte: multiFactorAuthentication (MFA war erforderlich) und singleFactorAuthentication (kein MFA erforderlich).|
|`TokenIssuerType`|Ganzzahl|Gibt an, ob der Tokenaussteller Azure Active Directory (0) oder Active Directory-Verbunddienste (1) ist.|
|`RiskLevelAggregated`|Ganzzahl|Aggregierte Risikostufe während der Anmeldung. Mögliche Werte: 0 (aggregierte Risikostufe nicht festgelegt), 1 (keine), 10 (niedrig), 50 (mittel) oder 100 (hoch).|
|`RiskDetails`|Ganzzahl|Details zum riskanten Status des angemeldeten Benutzers|
|`RiskState`|Ganzzahl|Gibt einen riskanten Benutzerstatus an. Mögliche Werte: 0 (keine), 1 (bestätigt sicher), 2 (behoben), 3 (geschlossen), 4 (gefährdet) oder 5 (bestätigt kompromittiert).|
|`UserAgent`|Zeichenfolge|Benutzer-Agent-Informationen aus dem Webbrowser oder einer anderen Clientanwendung|
|`ClientAppUsed`|Zeichenfolge|Gibt die verwendete Client-App an.|
|`Browser`|Zeichenfolge|Details zur Version des Browsers, der für die Anmeldung verwendet wurde|
|`ConditionalAccessPolicies`|Zeichenfolge|Details zu den Richtlinien für bedingten Zugriff, die auf das Anmeldeereignis angewendet werden|
|`ConditionalAccessStatus`|Ganzzahl|Status der richtlinien für bedingten Zugriff, die auf die Anmeldung angewendet wurden. Mögliche Werte sind 0 (Richtlinien angewendet), 1 (Versuch, Richtlinien anzuwenden, fehlgeschlagen) oder 2 (Richtlinien werden nicht angewendet).|
|`IPAddress`|Zeichenfolge|Ip-Adresse, die dem Endpunkt zugewiesen und während der zugehörigen Netzwerkkommunikation verwendet wird|
|`Country`|Zeichenfolge|Aus zwei Buchstaben bestehender Code, der das Land angibt, in dem die Client-IP-Adresse geolokal ist|
|`State`|Zeichenfolge|Status, in dem die Anmeldung stattgefunden hat, sofern verfügbar|
|`City`|Zeichenfolge|Ort, in dem sich der Kontobenutzer befindet|
|`Latitude`|Zeichenfolge|Die Nord-Nach-Süd-Koordinaten des Anmeldestandorts|
|`Longitude`|Zeichenfolge|Die Ost-Nach-West-Koordinaten des Anmeldestandorts|
|`NetworkLocationDetails`|Zeichenfolge|Netzwerkstandortdetails des Authentifizierungsprozessors des Anmeldeereignisses|
|`RequestId`|Zeichenfolge|Eindeutiger Bezeichner der Anforderung|
|`ReportId`|Zeichenfolge|Eindeutiger Bezeichner für das Ereignis|
|

## <a name="related-articles"></a>Verwandte Artikel

- [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
- [Übersicht über die erweiterte Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Lernen der Abfragesprache](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [Grundlegendes zum Schema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

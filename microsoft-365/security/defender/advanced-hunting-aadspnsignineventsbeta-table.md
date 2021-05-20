---
title: AADSpnSignInEventsBeta-Tabelle im schema der erweiterten Suche
description: Informationen zu Informationen, die Azure Active Directory Dienstprinzipal und der Ereignistabelle für verwaltete Identitätsidentitätsereignisse des erweiterten Schemas für die Suche zugeordnet sind
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account, identity, AAD
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
ms.openlocfilehash: f74972bcd5d0ddaab58d82b72a55991fda44e3b1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583544"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Gilt für:**

- Microsoft 365 Defender

>[!IMPORTANT]
> Die Tabelle befindet sich derzeit in der Betaversion und wird kurzfristig angeboten, um die Suche durch Azure Active Directory (AAD)-Dienstprinzipal- und verwaltete Identitäts-Anmeldeereignisse `AADSpnSignInEventsBeta` zu ermöglichen. Wir verschieben schließlich alle Anmeldeschemainformationen in die `IdentityLogonEvents` Tabelle.



Die Tabelle im Schema der erweiterten Suche enthält Informationen Azure Active Directory `AADSpnSignInEventsBeta` Dienstprinzipal und verwaltete Identitäts-Anmeldungen. Weitere Informationen zu den verschiedenen Arten von Anmeldungen finden Sie in Azure Active Directory [- Vorschau](/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Spaltenname     | Datentyp | Beschreibung   |
| ----- | ----- | ---- |
| `Timestamp` | Datum/Uhrzeit      | Datum und Uhrzeit, wann der Datensatz generiert wurde                                                                                                     |
| `Application`          | string        | Anwendung, die die aufgezeichnete Aktion ausgeführt hat                                                                                                   |
| `ApplicationId`        | Zeichenfolge        | Eindeutige ID für die Anwendung                                                                                                           |
| `IsManagedIdentity`    | boolean       | Gibt an, ob die Anmeldung von einer verwalteten Identität initiiert wurde                                                                               |
| `ErrorCode`            | int        | Enthält den Fehlercode, wenn ein Anmeldefehler auftritt. Eine Beschreibung eines bestimmten Fehlercodes finden Sie unter <https://aka.ms/AADsigninsErrorCodes> . |
| `CorrelationId`        | Zeichenfolge        | Eindeutiger Bezeichner des Anmeldeereigniss                                                                                                          |
| `ServicePrincipalName` | Zeichenfolge        | Name des Dienstprinzipal, der die Anmeldung initiiert hat                                                                                        |
| `ServicePrincipalId`   | Zeichenfolge        | Eindeutiger Bezeichner des Dienstprinzipal, der die Anmeldung initiiert hat                                                                           |
| `ResourceDisplayName`  | Zeichenfolge        | Anzeigename der Ressource, auf die zugegriffen wird                                                                                                           |
| `ResourceId`           | Zeichenfolge        | Eindeutiger Bezeichner der Ressource, auf die zugegriffen wird                                                                                                      |
| `ResourceTenantId`     | Zeichenfolge        | Eindeutiger Bezeichner des Mandanten der Ressource, auf die zugegriffen wird                                                                                        |
| `IPAddress`            | Zeichenfolge        | DEM Endpunkt zugewiesene und während der zugehörigen Netzwerkkommunikation verwendete IP-Adresse                                                              |
| `Country`          | Zeichenfolge        | Zwei-Buchstaben-Code, der das Land angibt, in dem die Client-IP-Adresse geolokaliert ist                                                                |
| `State`                | Zeichenfolge        | Status, in dem die Anmeldung erfolgt ist( sofern verfügbar)                                                                                                  |
| `City`                 | Zeichenfolge        | Ort, in dem sich der Kontobenutzer befindet                                                                                                          |
| `Latitude`             | Zeichenfolge        | Die Nord-Süd-Koordinaten des Anmeldestandorts                                                                                          |
| `Longitude`            | Zeichenfolge        | Die Ost-West-Koordinaten der Anmeldeposition                                                                                            |
| `RequestId`            | Zeichenfolge        | Eindeutiger Bezeichner der Anforderung                                                                                                                |
|`ReportId` | Zeichenfolge | Eindeutiger Bezeichner für das Ereignis | 

 

## <a name="related-articles"></a>Verwandte Artikel

-   [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
-   [Übersicht über die erweiterte Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Lernen der Abfragesprache](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Grundlegendes zum Schema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
---
title: Tabelle "DeviceTvmSecureConfigurationAssessment" im Schema "Erweiterte Suche"
description: Informationen zu Sicherheitsbewertungsereignissen in der Tabelle "DeviceTvmSecureConfigurationAssessment" des Schemas für die erweiterte Suche. Diese Bedrohungs& Sicherheitsrisikoverwaltungsereignisse liefern Geräteinformationen sowie Sicherheitskonfigurationsdetails, Auswirkungen und Complianceinformationen.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, Verwaltung von Sicherheitsrisiken & Bedrohungen, TVM, Geräteverwaltung, Sicherheitskonfiguration, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 6924bbc7a88a4f32d97534c72a180a1f1c4f7db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931098"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Jede Zeile in der Tabelle `DeviceTvmSecureConfigurationAssessment` enthält ein Bewertungsereignis für eine bestimmte Sicherheitskonfiguration der [Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Verwenden Sie diese Referenz, um die neuesten Beurteilungsergebnisse zu überprüfen und zu ermitteln, ob die Geräte kompatibel sind.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `DeviceId` | string | Eindeutige ID für das Gerät im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Geräts |
| `OSPlatform` | string | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.|
| `Timestamp` | Datum/Uhrzeit | Datum und Uhrzeit, wann der Datensatz generiert wurde |
| `ConfigurationId` | string | Eindeutiger Bezeichner für eine bestimmte Konfiguration |
| `ConfigurationCategory` | string | Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen |
| `ConfigurationSubcategory` | string | Unterkategorie oder Untergruppe, zu der die Konfiguration gehört. In vielen Fällen beschreibt dies bestimmte Funktionen oder Features. |
| `ConfigurationImpact` | string | Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10) |
| `IsCompliant` | Boolescher Wert | Gibt an, ob die Konfiguration oder Richtlinie ordnungsgemäß konfiguriert ist |
| `IsApplicable` | Boolescher Wert | Gibt an, ob die Konfiguration oder Richtlinie auf das Gerät angewendet wird. |
| `Context` | string | Zusätzliche kontextbezogene Informationen zur Konfiguration oder Richtlinie |
| `IsExpectedUserImpactCompliant` | Boolescher Wert | Gibt an, ob auswirkungen auf den Benutzer bei Anwendung der Konfiguration oder Richtlinie zu haben sind. |

## <a name="related-topics"></a>Verwandte Themen

- [Vorbeugende Suche nach Bedrohungen](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

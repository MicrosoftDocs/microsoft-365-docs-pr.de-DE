---
title: Tabelle "DeviceTvmSecureConfigurationAssessment" im Schema "Erweiterte Suche"
description: Weitere Informationen zu & Sicherheitsbewertungsereignissen für das Sicherheitsmanagement in der DeviceTvmSecureConfigurationAssessment-Tabelle des Schemas für die erweiterte Suche. Diese Ereignisse enthalten Geräteinformationen sowie Sicherheitskonfigurationsdetails, Auswirkungen und Complianceinformationen.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067008"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)



>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Jede Zeile in der Tabelle `DeviceTvmSecureConfigurationAssessment` enthält ein Bewertungsereignis für eine bestimmte Sicherheitskonfiguration der [Bedrohungs- und Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md). Verwenden Sie diese Referenz, um die neuesten Beurteilungsergebnisse zu überprüfen und zu ermitteln, ob die Geräte kompatibel sind.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `DeviceId` | string | Eindeutige ID für das Gerät im Dienst |
| `DeviceName` | Zeichenfolge | Vollqualifizierter Domänenname (FQDN) des Geräts |
| `OSPlatform` | Zeichenfolge | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.|
| `Timestamp` | Datum/Uhrzeit |Datum und Uhrzeit, wann der Datensatz generiert wurde |
| `ConfigurationId` | string | Eindeutiger Bezeichner für eine bestimmte Konfiguration |
| `ConfigurationCategory` | string | Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen |
| `ConfigurationSubcategory` | string |Unterkategorie oder Untergruppe, zu der die Konfiguration gehört. In vielen Fällen beschreibt dies bestimmte Funktionen oder Features. |
| `ConfigurationImpact` | string | Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10) |
| `IsCompliant` | Boolescher Wert | Gibt an, ob die Konfiguration oder Richtlinie ordnungsgemäß konfiguriert ist |
| `IsApplicable` | boolean | Gibt an, ob die Konfiguration oder Richtlinie auf das Gerät angewendet wird |
| `Context` | Zeichenfolge | Zusätzliche kontextbezogene Informationen zur Konfiguration oder Richtlinie |
| `IsExpectedUserImpactCompliant` | boolean | Gibt an, ob sich Benutzer auswirken, wenn die Konfiguration oder Richtlinie angewendet wird. |

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-reference.md)
- [Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md)
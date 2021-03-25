---
title: Tabelle "DeviceTvmSecureConfigurationAssessmentKB" im Schema "Erweiterte Suche"
description: Erfahren Sie mehr über die verschiedenen sicheren Konfigurationen, die von Threat & Vulnerability Management bewertet werden, in der DeviceTvmSecureConfigurationAssessmentKB-Tabelle des Advanced hunting-Schemas.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, MITRE ATT&CK framework, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 3ba0d90fae872eff209b41b7ba62baeccfe62808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067007"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Die Tabelle `DeviceTvmSecureConfigurationAssessmentKB` des Schemas "Erweiterte Suche" enthält Informationen zu den verschiedenen, von der [Bedrohungs- und Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md) überprüften sicheren Konfigurationen – z. B., ob auf einem Gerät automatische Updates aktiviert sind. Sie enthält außerdem Sicherheitsrisikoinformationen, relevante Branchenbenchmarks sowie anwendbare MITRE ATT&CK-Techniken und -Taktiken. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `ConfigurationId` | string | Eindeutiger Bezeichner für eine bestimmte Konfiguration |
| `ConfigurationImpact` | string | Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10) |
| `ConfigurationName` | string | Anzeigename der Konfiguration |
| `ConfigurationDescription` | string | Beschreibung der Konfiguration |
| `RiskDescription` | string | Beschreibung des zugehörigen Risikos |
| `ConfigurationCategory` | string | Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen|
| `ConfigurationSubcategory` | string |Unterkategorie oder Untergruppe, zu der die Konfiguration gehört. In vielen Fällen beschreibt dies bestimmte Funktionen oder Features. |
| `ConfigurationBenchmarks` | string | Liste der Branchenbenchmarks, die dieselben oder ähnliche Konfigurationen empfehlen |
| `RelatedMitreTechniques` | string | Liste der Mitre ATT&CK-Frameworktechniken im Zusammenhang mit der Konfiguration |
| `RelatedMitreTactics ` | string | Liste der Mitre ATT&CK-Frameworktaktiken im Zusammenhang mit der Konfiguration |

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-reference.md)
- [Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md)

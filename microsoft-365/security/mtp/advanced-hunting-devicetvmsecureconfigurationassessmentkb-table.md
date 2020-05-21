---
title: Tabelle "DeviceTvmSecureConfigurationAssessmentKB" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die verschiedenen sicheren Konfigurationen, die durch die Bedrohungs- und Sicherheitsrisikoverwaltung in der Tabelle "DeviceTvmSecureConfigurationAssessmentKB" des Schemas "Erweiterte Suche" bewertet werden.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, Bedrohungs & Vulnerability Management, TVM, Device Management, Security Configuration, Mitra ATT&ck Framework, Knowledge Base, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a265bb84b0ad59ee56cb0f0670951bab1bcd344a
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327967"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

**Gilt für:**
- Microsoft Threat Protection



Die Tabelle `DeviceTvmSecureConfigurationAssessmentKB` des Schemas "Erweiterte Suche" enthält Informationen zu den verschiedenen, von der [Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) überprüften sicheren Konfigurationen – z. B., ob auf einem Gerät automatische Updates aktiviert sind. Sie enthält außerdem Sicherheitsrisikoinformationen, relevante Branchenbenchmarks sowie anwendbare MITRE ATT&CK-Techniken und -Taktiken. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

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

- [Vorbeugende Suche nach Bedrohungen](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche nach Bedrohungen auf Geräten und in E-Mails](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

---
title: Tabelle "DeviceTvmSoftwareVulnerabilitiesKB" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die Softwaresicherheitsrisiken, die durch die Bedrohungs- und Sicherheitsrisikoverwaltung in der Tabelle "DeviceTvmSoftwareVulnerabilitiesKB" des Schemas "Erweiterte Suche" nachverfolgt werden.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 4b5d11788f0914749edaa58b927ef6d4bcc1a3f4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498939"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender



Die Tabelle `DeviceTvmSoftwareVulnerabilitiesKB` im Schema "Erweiterte Suche" enthält die Liste der Sicherheitsrisiken, nach denen Geräte durch die [Bedrohungs- und Sicherheitsrisikoverwaltung](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) bewertet werden. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.

Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `CveId` | string | Eindeutiger Bezeichner des Sicherheitsrisikos nach CVE (Common Vulnerabilities and Exposures) |
| `CvssScore` | string | Schweregrad des Sicherheitsrisikos nach CVSS (Common Vulnerability Scoring System) |
| `IsExploitAvailable` | Boolescher Wert | Gibt an, ob Exploitcode für das Sicherheitsrisiko öffentlich verfügbar ist |
| `VulnerabilitySeverityLevel` | string | Schweregrad des Sicherheitsrisikos, basierend auf CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden |
| `LastModifiedTime` | datetime | Datum und Uhrzeit der letzten Änderung des Elements oder der zugehörigen Metadaten |
| `PublishedDate` | datetime | Datum der Veröffentlichung des Sicherheitsrisikos für die Allgemeinheit |
| `VulnerabilityDescription` | string | Beschreibung des Sicherheitsrisikos und der damit verbundenen Risiken |
| `AffectedSoftware` | string | Liste aller von dem Sicherheitsrisiko betroffenen Softwareprodukte |

## <a name="related-topics"></a>Verwandte Themen

- [Vorbeugende Suche nach Bedrohungen](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
---
title: Suchen nach offenen Geräten
description: Erfahren Sie Bedrohungs- und Sicherheitsrisikomanagement sie verwendet werden können, um Sicherheitsadministratoren, IT-Administratoren und SecOps bei der Zusammenarbeit zu helfen.
keywords: Microsoft Defender für Endpoint-tvm-Szenarien, Microsoft Defender für Endpunkte, tvm- und tvm-Szenarien, Reduzieren der Bedrohung & Sicherheitsrisikoexposition, Verringern von Bedrohungen und Sicherheitsrisiken, Verbessern der Sicherheitskonfiguration, Erhöhen der Microsoft Secure Score für Geräte, Erhöhen der Bedrohung & Sicherheitsrisiko Microsoft Secure Score for Devices, Microsoft Secure Score for Devices, Exposure Score, Security Controls
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9a8ebcc89c3009cd93fbb42f2a74bbb9ffcc31b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934093"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a>Suche nach verfügbar gemachten Geräten – Bedrohungs- und Sicherheitsrisikomanagement

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohung und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a>Verwenden der erweiterten Suche zum Aufsuchen von Geräten mit Sicherheitsrisiken

Bei der erweiterten Suche handelt es sich um ein abfragebasiertes Tool für die Bedrohungssuche, mit dem Sie Rohdaten von bis zu 30 Tagen erkunden können. Sie können Ereignisse in Ihrem Netzwerk proaktiv überprüfen, um Bedrohungsindikatoren und -entitäten zu finden. Der flexible Zugriff auf Daten ermöglicht die ungesübte Suche nach bekannten und potenziellen Bedrohungen. [Weitere Informationen zur erweiterten Suche](advanced-hunting-overview.md)

### <a name="schema-tables"></a>Schematabellen

- [DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) – Inventar der auf Geräten installierten Software, einschließlich der Versionsinformationen und des Status des Supportendes.

- [DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) – Softwarerisiken, die auf Geräten gefunden werden, und die Liste der verfügbaren Sicherheitsupdates, die die einzelnen Sicherheitsrisiken adressieren.

- [DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) – Wissensdatenbank öffentlich offengelegter Sicherheitsrisiken, einschließlich der Frage, ob Exploitcode öffentlich verfügbar ist.

- [DeviceTvmSecureConfigurationAssessment – Bedrohungs-](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) und Sicherheitsrisikomanagement-Bewertungsereignisse, die den Status verschiedener Sicherheitskonfigurationen auf Geräten angeben.

- [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) – Wissensdatenbank der verschiedenen Sicherheitskonfigurationen, die von Threat & Vulnerability Management zum Bewerten von Geräten verwendet werden; umfasst Zuordnungen zu verschiedenen Standards und Benchmarks

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a>Überprüfen, welche Geräte an Warnungen mit hohem Schweregrad beteiligt sind

1. Wechseln Sie **im** linken Navigationsbereich des Navigationsbereichs zu Erweiterte Microsoft Defender Security Center.

2. Führen Sie einen Bildlauf nach unten zu den erweiterten TVM-Jagdschemas aus, um sich mit den Spaltennamen vertraut zu machen.

3. Geben Sie die folgenden Abfragen ein:

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId
| join kind =inner(DeviceAlertEvents) on DeviceId  
| summarize NumOfVulnerabilities=any(NumOfVulnerabilities),
DeviceName=any(DeviceName) by DeviceId, AlertId
| project DeviceName, NumOfVulnerabilities, AlertId  
| order by NumOfVulnerabilities desc
```

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Bedrohungen Sicherheitsrisikomanagement Bedrohungen](next-gen-threat-and-vuln-mgt.md)
- [Sicherheitsempfehlungen](tvm-security-recommendation.md)
- [APIs](next-gen-threat-and-vuln-mgt.md#apis)
- [Konfigurieren des Datenzugriffs für Bedrohungs- und Sicherheitsrisikomanagement Rollen](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [Übersicht über die erweiterte Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Alle erweiterten Tabellen für die Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)

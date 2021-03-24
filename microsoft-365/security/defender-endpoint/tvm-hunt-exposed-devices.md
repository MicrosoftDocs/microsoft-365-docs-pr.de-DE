---
title: Suche nach verfügbar gemachten Geräten
description: Erfahren Sie, wie das Bedrohungs- und Sicherheitsrisikomanagement verwendet werden kann, um Sicherheitsadministratoren, IT-Administratoren und SecOps bei der Zusammenarbeit zu helfen.
keywords: mdatp-tvm-Szenarien, Mdatp-, TVM-, TVM-Szenarien, Reduzieren der Bedrohung & Sicherheitsrisikoexposition, Verringern von Bedrohungen und Sicherheitsrisiken, Verbessern der Sicherheitskonfiguration, Erhöhen der Microsoft Secure Score für Geräte, Erhöhen der Bedrohung & Sicherheitsrisiko Microsoft Secure Score for Devices, Microsoft Secure Score for Devices, Exposure Score, Sicherheitskontrollen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9af7464d9cae06dc53abb019aa0b189d6e72e749
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060828"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a>Suche nach verfügbar gemachten Geräten – Bedrohungs- und Sicherheitsrisikoverwaltung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohungs- und Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a>Verwenden der erweiterten Suche zum Aufsuchen von Geräten mit Sicherheitsrisiken

Bei der erweiterten Suche handelt es sich um ein abfragebasiertes Tool für die Bedrohungssuche, mit dem Sie Rohdaten von bis zu 30 Tagen erkunden können. Sie können Ereignisse in Ihrem Netzwerk proaktiv überprüfen, um Bedrohungsindikatoren und -entitäten zu finden. Der flexible Zugriff auf Daten ermöglicht die ungesübte Suche nach bekannten und potenziellen Bedrohungen. [Weitere Informationen zur erweiterten Suche](advanced-hunting-overview.md)

### <a name="schema-tables"></a>Schematabellen

- [DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) – Inventar der auf Geräten installierten Software, einschließlich der Versionsinformationen und des Status des Endes des Supportstatus

- [DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) – Softwarerisiken auf Geräten und die Liste der verfügbaren Sicherheitsupdates, die die einzelnen Sicherheitsrisiken adressieren

- [DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) – Wissensdatenbank öffentlich offengelegter Sicherheitsrisiken, einschließlich der Frage, ob Exploitcode öffentlich verfügbar ist

- [DeviceTvmSecureConfigurationAssessment – Bewertungsereignisse](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) zur Bedrohungs- und Sicherheitsrisikoverwaltung, die den Status verschiedener Sicherheitskonfigurationen auf Geräten angeben

- [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) – Wissensdatenbank der verschiedenen Sicherheitskonfigurationen, die von Threat & Vulnerability Management zum Bewerten von Geräten verwendet werden; umfasst Zuordnungen zu verschiedenen Standards und Benchmarks

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a>Überprüfen, welche Geräte an Warnungen mit hohem Schweregrad beteiligt sind

1. Wechseln Sie **im** linken Navigationsbereich des Microsoft Defender Security Center zu Erweiterte Suche.

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

- [Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken](next-gen-threat-and-vuln-mgt.md)
- [Sicherheitsempfehlungen](tvm-security-recommendation.md)
- [APIs](next-gen-threat-and-vuln-mgt.md#apis)
- [Konfigurieren des Datenzugriffs für Bedrohungs- und Sicherheitsrisikoverwaltungsrollen](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [Übersicht über die erweiterte Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Alle erweiterten Tabellen für die Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)

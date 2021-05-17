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
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a><span data-ttu-id="b16ff-104">Suche nach verfügbar gemachten Geräten – Bedrohungs- und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="b16ff-104">Hunt for exposed devices - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b16ff-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b16ff-105">**Applies to:**</span></span>

- [<span data-ttu-id="b16ff-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b16ff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b16ff-107">Bedrohung und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="b16ff-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="b16ff-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b16ff-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b16ff-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b16ff-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b16ff-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b16ff-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a><span data-ttu-id="b16ff-111">Verwenden der erweiterten Suche zum Aufsuchen von Geräten mit Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="b16ff-111">Use advanced hunting to find devices with vulnerabilities</span></span>

<span data-ttu-id="b16ff-112">Bei der erweiterten Suche handelt es sich um ein abfragebasiertes Tool für die Bedrohungssuche, mit dem Sie Rohdaten von bis zu 30 Tagen erkunden können.</span><span class="sxs-lookup"><span data-stu-id="b16ff-112">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="b16ff-113">Sie können Ereignisse in Ihrem Netzwerk proaktiv überprüfen, um Bedrohungsindikatoren und -entitäten zu finden.</span><span class="sxs-lookup"><span data-stu-id="b16ff-113">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="b16ff-114">Der flexible Zugriff auf Daten ermöglicht die ungesübte Suche nach bekannten und potenziellen Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="b16ff-114">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span> [<span data-ttu-id="b16ff-115">Weitere Informationen zur erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="b16ff-115">Learn more about advanced hunting</span></span>](advanced-hunting-overview.md)

### <a name="schema-tables"></a><span data-ttu-id="b16ff-116">Schematabellen</span><span class="sxs-lookup"><span data-stu-id="b16ff-116">Schema tables</span></span>

- <span data-ttu-id="b16ff-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) – Inventar der auf Geräten installierten Software, einschließlich der Versionsinformationen und des Status des Supportendes.</span><span class="sxs-lookup"><span data-stu-id="b16ff-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventory of software installed on devices, including their version information and end-of-support status.</span></span>

- <span data-ttu-id="b16ff-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) – Softwarerisiken, die auf Geräten gefunden werden, und die Liste der verfügbaren Sicherheitsupdates, die die einzelnen Sicherheitsrisiken adressieren.</span><span class="sxs-lookup"><span data-stu-id="b16ff-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Software vulnerabilities found on devices and the list of available security updates that address each vulnerability.</span></span>

- <span data-ttu-id="b16ff-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) – Wissensdatenbank öffentlich offengelegter Sicherheitsrisiken, einschließlich der Frage, ob Exploitcode öffentlich verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b16ff-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available.</span></span>

- <span data-ttu-id="b16ff-120">[DeviceTvmSecureConfigurationAssessment – Bedrohungs-](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) und Sicherheitsrisikomanagement-Bewertungsereignisse, die den Status verschiedener Sicherheitskonfigurationen auf Geräten angeben.</span><span class="sxs-lookup"><span data-stu-id="b16ff-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Threat and vulnerability management assessment events, indicating the status of various security configurations on devices.</span></span>

- <span data-ttu-id="b16ff-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) – Wissensdatenbank der verschiedenen Sicherheitskonfigurationen, die von Threat & Vulnerability Management zum Bewerten von Geräten verwendet werden; umfasst Zuordnungen zu verschiedenen Standards und Benchmarks</span><span class="sxs-lookup"><span data-stu-id="b16ff-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a><span data-ttu-id="b16ff-122">Überprüfen, welche Geräte an Warnungen mit hohem Schweregrad beteiligt sind</span><span class="sxs-lookup"><span data-stu-id="b16ff-122">Check which devices are involved in high severity alerts</span></span>

1. <span data-ttu-id="b16ff-123">Wechseln Sie **im** linken Navigationsbereich des Navigationsbereichs zu Erweiterte Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="b16ff-123">Go to **Advanced hunting** from the left-hand navigation pane of the Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="b16ff-124">Führen Sie einen Bildlauf nach unten zu den erweiterten TVM-Jagdschemas aus, um sich mit den Spaltennamen vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="b16ff-124">Scroll down to the TVM advanced hunting schemas to familiarize yourself with the column names.</span></span>

3. <span data-ttu-id="b16ff-125">Geben Sie die folgenden Abfragen ein:</span><span class="sxs-lookup"><span data-stu-id="b16ff-125">Enter the following queries:</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="b16ff-126">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b16ff-126">Related topics</span></span>

- [<span data-ttu-id="b16ff-127">Übersicht über Bedrohungen Sicherheitsrisikomanagement Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="b16ff-127">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="b16ff-128">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="b16ff-128">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="b16ff-129">APIs</span><span class="sxs-lookup"><span data-stu-id="b16ff-129">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)
- [<span data-ttu-id="b16ff-130">Konfigurieren des Datenzugriffs für Bedrohungs- und Sicherheitsrisikomanagement Rollen</span><span class="sxs-lookup"><span data-stu-id="b16ff-130">Configure data access for threat and vulnerability management roles</span></span>](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [<span data-ttu-id="b16ff-131">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="b16ff-131">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [<span data-ttu-id="b16ff-132">Alle erweiterten Tabellen für die Suche</span><span class="sxs-lookup"><span data-stu-id="b16ff-132">All advanced hunting tables</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)

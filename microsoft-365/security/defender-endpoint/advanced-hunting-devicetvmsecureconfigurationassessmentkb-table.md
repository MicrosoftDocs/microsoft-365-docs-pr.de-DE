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
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="e7246-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="e7246-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e7246-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e7246-105">**Applies to:**</span></span>
- [<span data-ttu-id="e7246-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e7246-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="e7246-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="e7246-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e7246-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e7246-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e7246-109">Die Tabelle `DeviceTvmSecureConfigurationAssessmentKB` des Schemas "Erweiterte Suche" enthält Informationen zu den verschiedenen, von der [Bedrohungs- und Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md) überprüften sicheren Konfigurationen – z. B., ob auf einem Gerät automatische Updates aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e7246-109">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="e7246-110">Sie enthält außerdem Sicherheitsrisikoinformationen, relevante Branchenbenchmarks sowie anwendbare MITRE ATT&CK-Techniken und -Taktiken.</span><span class="sxs-lookup"><span data-stu-id="e7246-110">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="e7246-111">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="e7246-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="e7246-112">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="e7246-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="e7246-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="e7246-113">Column name</span></span> | <span data-ttu-id="e7246-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e7246-114">Data type</span></span> | <span data-ttu-id="e7246-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7246-115">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="e7246-116">string</span><span class="sxs-lookup"><span data-stu-id="e7246-116">string</span></span> | <span data-ttu-id="e7246-117">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e7246-117">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="e7246-118">string</span><span class="sxs-lookup"><span data-stu-id="e7246-118">string</span></span> | <span data-ttu-id="e7246-119">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="e7246-119">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="e7246-120">string</span><span class="sxs-lookup"><span data-stu-id="e7246-120">string</span></span> | <span data-ttu-id="e7246-121">Anzeigename der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e7246-121">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="e7246-122">string</span><span class="sxs-lookup"><span data-stu-id="e7246-122">string</span></span> | <span data-ttu-id="e7246-123">Beschreibung der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e7246-123">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="e7246-124">string</span><span class="sxs-lookup"><span data-stu-id="e7246-124">string</span></span> | <span data-ttu-id="e7246-125">Beschreibung des zugehörigen Risikos</span><span class="sxs-lookup"><span data-stu-id="e7246-125">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="e7246-126">string</span><span class="sxs-lookup"><span data-stu-id="e7246-126">string</span></span> | <span data-ttu-id="e7246-127">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="e7246-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="e7246-128">string</span><span class="sxs-lookup"><span data-stu-id="e7246-128">string</span></span> |<span data-ttu-id="e7246-129">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="e7246-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="e7246-130">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="e7246-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="e7246-131">string</span><span class="sxs-lookup"><span data-stu-id="e7246-131">string</span></span> | <span data-ttu-id="e7246-132">Liste der Branchenbenchmarks, die dieselben oder ähnliche Konfigurationen empfehlen</span><span class="sxs-lookup"><span data-stu-id="e7246-132">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="e7246-133">string</span><span class="sxs-lookup"><span data-stu-id="e7246-133">string</span></span> | <span data-ttu-id="e7246-134">Liste der Mitre ATT&CK-Frameworktechniken im Zusammenhang mit der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e7246-134">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="e7246-135">string</span><span class="sxs-lookup"><span data-stu-id="e7246-135">string</span></span> | <span data-ttu-id="e7246-136">Liste der Mitre ATT&CK-Frameworktaktiken im Zusammenhang mit der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e7246-136">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e7246-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e7246-137">Related topics</span></span>

- [<span data-ttu-id="e7246-138">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="e7246-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e7246-139">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="e7246-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e7246-140">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="e7246-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="e7246-141">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="e7246-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)

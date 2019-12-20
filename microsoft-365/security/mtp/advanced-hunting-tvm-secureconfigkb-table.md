---
title: Tabelle "DeviceTvmSecureConfigurationAssessmentKB" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die verschiedenen sicheren Konfigurationen, die durch die Bedrohungs- und Sicherheitsrisikoverwaltung in der Tabelle "DeviceTvmSecureConfigurationAssessmentKB" des Schemas "Erweiterte Suche" bewertet werden.
keywords: erweiterte Suche, Suche nach Bedrohungen, Suche nach Cyberbedrohungen, Suche, Abfrage, Telemetrie, Schema, Referenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, Bedrohungs- und Sicherheitsrisikoverwaltung, TVM, Geräteverwaltung, Sicherheitskonfiguration, MITRE ATT&CK-Framework, Knowledge Base, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a3ae0a95af4a51d492c577e6a2ac1f2b96bba635
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806934"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="d2395-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="d2395-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="d2395-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d2395-105">**Applies to:**</span></span>
- <span data-ttu-id="d2395-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d2395-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d2395-107">Die Tabelle `DeviceTvmSecureConfigurationAssessmentKB` des Schemas "Erweiterte Suche" enthält Informationen zu den verschiedenen, von der [Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) überprüften sicheren Konfigurationen – z. B., ob auf einem Gerät automatische Updates aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="d2395-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="d2395-108">Sie enthält außerdem Sicherheitsrisikoinformationen, relevante Branchenbenchmarks sowie anwendbare MITRE ATT&CK-Techniken und -Taktiken.</span><span class="sxs-lookup"><span data-stu-id="d2395-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="d2395-109">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="d2395-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="d2395-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="d2395-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d2395-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d2395-111">Column name</span></span> | <span data-ttu-id="d2395-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="d2395-112">Data type</span></span> | <span data-ttu-id="d2395-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2395-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="d2395-114">string</span><span class="sxs-lookup"><span data-stu-id="d2395-114">string</span></span> | <span data-ttu-id="d2395-115">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d2395-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="d2395-116">string</span><span class="sxs-lookup"><span data-stu-id="d2395-116">string</span></span> | <span data-ttu-id="d2395-117">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="d2395-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="d2395-118">string</span><span class="sxs-lookup"><span data-stu-id="d2395-118">string</span></span> | <span data-ttu-id="d2395-119">Anzeigename der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d2395-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="d2395-120">string</span><span class="sxs-lookup"><span data-stu-id="d2395-120">string</span></span> | <span data-ttu-id="d2395-121">Beschreibung der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d2395-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="d2395-122">string</span><span class="sxs-lookup"><span data-stu-id="d2395-122">string</span></span> | <span data-ttu-id="d2395-123">Beschreibung des zugehörigen Risikos</span><span class="sxs-lookup"><span data-stu-id="d2395-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="d2395-124">string</span><span class="sxs-lookup"><span data-stu-id="d2395-124">string</span></span> | <span data-ttu-id="d2395-125">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="d2395-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="d2395-126">string</span><span class="sxs-lookup"><span data-stu-id="d2395-126">string</span></span> |<span data-ttu-id="d2395-127">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="d2395-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="d2395-128">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="d2395-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="d2395-129">string</span><span class="sxs-lookup"><span data-stu-id="d2395-129">string</span></span> | <span data-ttu-id="d2395-130">Liste der Branchenbenchmarks, die dieselben oder ähnliche Konfigurationen empfehlen</span><span class="sxs-lookup"><span data-stu-id="d2395-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="d2395-131">string</span><span class="sxs-lookup"><span data-stu-id="d2395-131">string</span></span> | <span data-ttu-id="d2395-132">Liste der Mitre ATT&CK-Frameworktechniken im Zusammenhang mit der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d2395-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="d2395-133">string</span><span class="sxs-lookup"><span data-stu-id="d2395-133">string</span></span> | <span data-ttu-id="d2395-134">Liste der Mitre ATT&CK-Frameworktaktiken im Zusammenhang mit der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d2395-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d2395-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d2395-135">Related topics</span></span>

- [<span data-ttu-id="d2395-136">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="d2395-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d2395-137">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="d2395-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d2395-138">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="d2395-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d2395-139">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="d2395-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d2395-140">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="d2395-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d2395-141">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="d2395-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="d2395-142">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="d2395-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

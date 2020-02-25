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
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235144"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="7eaf0-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="7eaf0-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="7eaf0-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7eaf0-105">**Applies to:**</span></span>
- <span data-ttu-id="7eaf0-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7eaf0-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="7eaf0-107">Die Tabelle `DeviceTvmSecureConfigurationAssessmentKB` des Schemas "Erweiterte Suche" enthält Informationen zu den verschiedenen, von der [Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) überprüften sicheren Konfigurationen – z. B., ob auf einem Gerät automatische Updates aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7eaf0-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="7eaf0-108">Sie enthält außerdem Sicherheitsrisikoinformationen, relevante Branchenbenchmarks sowie anwendbare MITRE ATT&CK-Techniken und -Taktiken.</span><span class="sxs-lookup"><span data-stu-id="7eaf0-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="7eaf0-109">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7eaf0-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="7eaf0-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7eaf0-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7eaf0-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7eaf0-111">Column name</span></span> | <span data-ttu-id="7eaf0-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="7eaf0-112">Data type</span></span> | <span data-ttu-id="7eaf0-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7eaf0-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="7eaf0-114">string</span><span class="sxs-lookup"><span data-stu-id="7eaf0-114">string</span></span> | <span data-ttu-id="7eaf0-115">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7eaf0-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="7eaf0-116">string</span><span class="sxs-lookup"><span data-stu-id="7eaf0-116">string</span></span> | <span data-ttu-id="7eaf0-117">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="7eaf0-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="7eaf0-118">string</span><span class="sxs-lookup"><span data-stu-id="7eaf0-118">string</span></span> | <span data-ttu-id="7eaf0-119">Anzeigename der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7eaf0-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="7eaf0-120">string</span><span class="sxs-lookup"><span data-stu-id="7eaf0-120">string</span></span> | <span data-ttu-id="7eaf0-121">Beschreibung der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7eaf0-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="7eaf0-122">string</span><span class="sxs-lookup"><span data-stu-id="7eaf0-122">string</span></span> | <span data-ttu-id="7eaf0-123">Beschreibung des zugehörigen Risikos</span><span class="sxs-lookup"><span data-stu-id="7eaf0-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="7eaf0-124">string</span><span class="sxs-lookup"><span data-stu-id="7eaf0-124">string</span></span> | <span data-ttu-id="7eaf0-125">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="7eaf0-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="7eaf0-126">string</span><span class="sxs-lookup"><span data-stu-id="7eaf0-126">string</span></span> |<span data-ttu-id="7eaf0-127">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="7eaf0-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="7eaf0-128">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="7eaf0-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="7eaf0-129">string</span><span class="sxs-lookup"><span data-stu-id="7eaf0-129">string</span></span> | <span data-ttu-id="7eaf0-130">Liste der Branchenbenchmarks, die dieselben oder ähnliche Konfigurationen empfehlen</span><span class="sxs-lookup"><span data-stu-id="7eaf0-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="7eaf0-131">string</span><span class="sxs-lookup"><span data-stu-id="7eaf0-131">string</span></span> | <span data-ttu-id="7eaf0-132">Liste der Mitre ATT&CK-Frameworktechniken im Zusammenhang mit der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7eaf0-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="7eaf0-133">string</span><span class="sxs-lookup"><span data-stu-id="7eaf0-133">string</span></span> | <span data-ttu-id="7eaf0-134">Liste der Mitre ATT&CK-Frameworktaktiken im Zusammenhang mit der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7eaf0-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7eaf0-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7eaf0-135">Related topics</span></span>

- [<span data-ttu-id="7eaf0-136">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="7eaf0-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7eaf0-137">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="7eaf0-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7eaf0-138">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="7eaf0-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7eaf0-139">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="7eaf0-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7eaf0-140">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="7eaf0-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7eaf0-141">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="7eaf0-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="7eaf0-142">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="7eaf0-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

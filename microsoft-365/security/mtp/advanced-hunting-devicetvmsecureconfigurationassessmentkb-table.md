---
title: Tabelle "DeviceTvmSecureConfigurationAssessmentKB" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die verschiedenen sicheren Konfigurationen, die durch die Bedrohungs- und Sicherheitsrisikoverwaltung in der Tabelle "DeviceTvmSecureConfigurationAssessmentKB" des Schemas "Erweiterte Suche" bewertet werden.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, Verwaltung von Sicherheitsrisiken & Bedrohungen, TVM, Geräteverwaltung, Sicherheitskonfiguration, MITRE ATT&CK Framework, Knowledge Base, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 4cd23b8f3ba99b38264b9bf1ba18e8ec2574bab6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931062"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="70bb9-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="70bb9-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="70bb9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="70bb9-105">**Applies to:**</span></span>
- <span data-ttu-id="70bb9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="70bb9-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="70bb9-107">Die Tabelle `DeviceTvmSecureConfigurationAssessmentKB` des Schemas "Erweiterte Suche" enthält Informationen zu den verschiedenen, von der [Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) überprüften sicheren Konfigurationen – z. B., ob auf einem Gerät automatische Updates aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="70bb9-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="70bb9-108">Sie enthält außerdem Sicherheitsrisikoinformationen, relevante Branchenbenchmarks sowie anwendbare MITRE ATT&CK-Techniken und -Taktiken.</span><span class="sxs-lookup"><span data-stu-id="70bb9-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="70bb9-109">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="70bb9-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="70bb9-110">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="70bb9-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="70bb9-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="70bb9-111">Column name</span></span> | <span data-ttu-id="70bb9-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="70bb9-112">Data type</span></span> | <span data-ttu-id="70bb9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70bb9-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="70bb9-114">string</span><span class="sxs-lookup"><span data-stu-id="70bb9-114">string</span></span> | <span data-ttu-id="70bb9-115">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="70bb9-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="70bb9-116">string</span><span class="sxs-lookup"><span data-stu-id="70bb9-116">string</span></span> | <span data-ttu-id="70bb9-117">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="70bb9-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="70bb9-118">string</span><span class="sxs-lookup"><span data-stu-id="70bb9-118">string</span></span> | <span data-ttu-id="70bb9-119">Anzeigename der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="70bb9-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="70bb9-120">string</span><span class="sxs-lookup"><span data-stu-id="70bb9-120">string</span></span> | <span data-ttu-id="70bb9-121">Beschreibung der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="70bb9-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="70bb9-122">string</span><span class="sxs-lookup"><span data-stu-id="70bb9-122">string</span></span> | <span data-ttu-id="70bb9-123">Beschreibung des zugehörigen Risikos</span><span class="sxs-lookup"><span data-stu-id="70bb9-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="70bb9-124">string</span><span class="sxs-lookup"><span data-stu-id="70bb9-124">string</span></span> | <span data-ttu-id="70bb9-125">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="70bb9-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="70bb9-126">string</span><span class="sxs-lookup"><span data-stu-id="70bb9-126">string</span></span> |<span data-ttu-id="70bb9-127">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="70bb9-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="70bb9-128">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="70bb9-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="70bb9-129">string</span><span class="sxs-lookup"><span data-stu-id="70bb9-129">string</span></span> | <span data-ttu-id="70bb9-130">Liste der Branchenbenchmarks, die dieselben oder ähnliche Konfigurationen empfehlen</span><span class="sxs-lookup"><span data-stu-id="70bb9-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="70bb9-131">string</span><span class="sxs-lookup"><span data-stu-id="70bb9-131">string</span></span> | <span data-ttu-id="70bb9-132">Liste der Mitre ATT&CK-Frameworktechniken im Zusammenhang mit der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="70bb9-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="70bb9-133">string</span><span class="sxs-lookup"><span data-stu-id="70bb9-133">string</span></span> | <span data-ttu-id="70bb9-134">Liste der Mitre ATT&CK-Frameworktaktiken im Zusammenhang mit der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="70bb9-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="70bb9-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="70bb9-135">Related topics</span></span>

- [<span data-ttu-id="70bb9-136">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="70bb9-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="70bb9-137">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="70bb9-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="70bb9-138">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="70bb9-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="70bb9-139">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="70bb9-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="70bb9-140">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="70bb9-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="70bb9-141">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="70bb9-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="70bb9-142">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="70bb9-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

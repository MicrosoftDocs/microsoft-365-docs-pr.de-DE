---
title: Tabelle "DeviceTvmSecureConfigurationAssessmentKB" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die verschiedenen sicheren Konfigurationen, die durch die Bedrohungs- und Sicherheitsrisikoverwaltung in der Tabelle "DeviceTvmSecureConfigurationAssessmentKB" des Schemas "Erweiterte Suche" bewertet werden.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & Sicherheitsrisikomanagement, TVM, device management, security configuration, MITRE ATT&CK framework, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 1dfa710b86afdcfd8a5643555564a0f34c7b4702
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024241"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="338c6-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="338c6-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="338c6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="338c6-105">**Applies to:**</span></span>
- <span data-ttu-id="338c6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="338c6-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="338c6-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="338c6-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="338c6-108">Die Tabelle `DeviceTvmSecureConfigurationAssessmentKB` des Schemas "Erweiterte Suche" enthält Informationen zu den verschiedenen, von der [Bedrohungs- und Sicherheitsrisikoverwaltung](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) überprüften sicheren Konfigurationen – z. B., ob auf einem Gerät automatische Updates aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="338c6-108">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="338c6-109">Sie enthält außerdem Sicherheitsrisikoinformationen, relevante Branchenbenchmarks sowie anwendbare MITRE ATT&CK-Techniken und -Taktiken.</span><span class="sxs-lookup"><span data-stu-id="338c6-109">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="338c6-110">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="338c6-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="338c6-111">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="338c6-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="338c6-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="338c6-112">Column name</span></span> | <span data-ttu-id="338c6-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="338c6-113">Data type</span></span> | <span data-ttu-id="338c6-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="338c6-114">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="338c6-115">string</span><span class="sxs-lookup"><span data-stu-id="338c6-115">string</span></span> | <span data-ttu-id="338c6-116">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="338c6-116">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="338c6-117">string</span><span class="sxs-lookup"><span data-stu-id="338c6-117">string</span></span> | <span data-ttu-id="338c6-118">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="338c6-118">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="338c6-119">string</span><span class="sxs-lookup"><span data-stu-id="338c6-119">string</span></span> | <span data-ttu-id="338c6-120">Anzeigename der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="338c6-120">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="338c6-121">string</span><span class="sxs-lookup"><span data-stu-id="338c6-121">string</span></span> | <span data-ttu-id="338c6-122">Beschreibung der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="338c6-122">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="338c6-123">string</span><span class="sxs-lookup"><span data-stu-id="338c6-123">string</span></span> | <span data-ttu-id="338c6-124">Beschreibung des zugehörigen Risikos</span><span class="sxs-lookup"><span data-stu-id="338c6-124">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="338c6-125">string</span><span class="sxs-lookup"><span data-stu-id="338c6-125">string</span></span> | <span data-ttu-id="338c6-126">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="338c6-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="338c6-127">string</span><span class="sxs-lookup"><span data-stu-id="338c6-127">string</span></span> |<span data-ttu-id="338c6-128">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="338c6-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="338c6-129">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="338c6-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="338c6-130">string</span><span class="sxs-lookup"><span data-stu-id="338c6-130">string</span></span> | <span data-ttu-id="338c6-131">Liste der Branchenbenchmarks, die dieselben oder ähnliche Konfigurationen empfehlen</span><span class="sxs-lookup"><span data-stu-id="338c6-131">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="338c6-132">string</span><span class="sxs-lookup"><span data-stu-id="338c6-132">string</span></span> | <span data-ttu-id="338c6-133">Bezeichnungen, die verschiedene Attribute darstellen, die zum Identifizieren oder Kategorisieren einer Sicherheitskonfiguration verwendet werden</span><span class="sxs-lookup"><span data-stu-id="338c6-133">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="338c6-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="338c6-134">string</span></span> | <span data-ttu-id="338c6-135">Empfohlene Maßnahmen zum Reduzieren oder Adressieren zugeordneter Risiken</span><span class="sxs-lookup"><span data-stu-id="338c6-135">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="338c6-136">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="338c6-136">Related topics</span></span>

- [<span data-ttu-id="338c6-137">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="338c6-137">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="338c6-138">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="338c6-138">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="338c6-139">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="338c6-139">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="338c6-140">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="338c6-140">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="338c6-141">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="338c6-141">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="338c6-142">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="338c6-142">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="338c6-143">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="338c6-143">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
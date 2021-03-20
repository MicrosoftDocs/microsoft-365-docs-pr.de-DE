---
title: Tabelle "DeviceTvmSecureConfigurationAssessmentKB" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die verschiedenen sicheren Konfigurationen, die durch die Bedrohungs- und Sicherheitsrisikoverwaltung in der Tabelle "DeviceTvmSecureConfigurationAssessmentKB" des Schemas "Erweiterte Suche" bewertet werden.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, MITRE ATT&CK framework, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 23b109ee5c149ecf9015f8c1622e03b20bdf243c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907336"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="ff396-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="ff396-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ff396-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ff396-105">**Applies to:**</span></span>
- <span data-ttu-id="ff396-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff396-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="ff396-107">Die Tabelle `DeviceTvmSecureConfigurationAssessmentKB` des Schemas "Erweiterte Suche" enthält Informationen zu den verschiedenen, von der [Bedrohungs- und Sicherheitsrisikoverwaltung](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) überprüften sicheren Konfigurationen – z. B., ob auf einem Gerät automatische Updates aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="ff396-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="ff396-108">Sie enthält außerdem Sicherheitsrisikoinformationen, relevante Branchenbenchmarks sowie anwendbare MITRE ATT&CK-Techniken und -Taktiken.</span><span class="sxs-lookup"><span data-stu-id="ff396-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="ff396-109">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ff396-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="ff396-110">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ff396-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ff396-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ff396-111">Column name</span></span> | <span data-ttu-id="ff396-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="ff396-112">Data type</span></span> | <span data-ttu-id="ff396-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff396-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="ff396-114">string</span><span class="sxs-lookup"><span data-stu-id="ff396-114">string</span></span> | <span data-ttu-id="ff396-115">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ff396-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="ff396-116">string</span><span class="sxs-lookup"><span data-stu-id="ff396-116">string</span></span> | <span data-ttu-id="ff396-117">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="ff396-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="ff396-118">string</span><span class="sxs-lookup"><span data-stu-id="ff396-118">string</span></span> | <span data-ttu-id="ff396-119">Anzeigename der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ff396-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="ff396-120">string</span><span class="sxs-lookup"><span data-stu-id="ff396-120">string</span></span> | <span data-ttu-id="ff396-121">Beschreibung der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ff396-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="ff396-122">string</span><span class="sxs-lookup"><span data-stu-id="ff396-122">string</span></span> | <span data-ttu-id="ff396-123">Beschreibung des zugehörigen Risikos</span><span class="sxs-lookup"><span data-stu-id="ff396-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="ff396-124">string</span><span class="sxs-lookup"><span data-stu-id="ff396-124">string</span></span> | <span data-ttu-id="ff396-125">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="ff396-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="ff396-126">string</span><span class="sxs-lookup"><span data-stu-id="ff396-126">string</span></span> |<span data-ttu-id="ff396-127">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="ff396-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="ff396-128">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="ff396-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="ff396-129">string</span><span class="sxs-lookup"><span data-stu-id="ff396-129">string</span></span> | <span data-ttu-id="ff396-130">Liste der Branchenbenchmarks, die dieselben oder ähnliche Konfigurationen empfehlen</span><span class="sxs-lookup"><span data-stu-id="ff396-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="ff396-131">string</span><span class="sxs-lookup"><span data-stu-id="ff396-131">string</span></span> | <span data-ttu-id="ff396-132">Bezeichnungen, die verschiedene Attribute darstellen, die zum Identifizieren oder Kategorisieren einer Sicherheitskonfiguration verwendet werden</span><span class="sxs-lookup"><span data-stu-id="ff396-132">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="ff396-133">string</span><span class="sxs-lookup"><span data-stu-id="ff396-133">string</span></span> | <span data-ttu-id="ff396-134">Empfohlene Maßnahmen zum Reduzieren oder Adressieren zugeordneter Risiken</span><span class="sxs-lookup"><span data-stu-id="ff396-134">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ff396-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ff396-135">Related topics</span></span>

- [<span data-ttu-id="ff396-136">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="ff396-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ff396-137">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="ff396-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ff396-138">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="ff396-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ff396-139">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="ff396-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ff396-140">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="ff396-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ff396-141">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="ff396-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ff396-142">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="ff396-142">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
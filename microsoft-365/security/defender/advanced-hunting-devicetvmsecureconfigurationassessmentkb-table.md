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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e664f0da29e0403b415792c839fd740006791cf0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063456"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="5b34e-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="5b34e-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5b34e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5b34e-105">**Applies to:**</span></span>
- <span data-ttu-id="5b34e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b34e-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="5b34e-107">Die Tabelle `DeviceTvmSecureConfigurationAssessmentKB` des Schemas "Erweiterte Suche" enthält Informationen zu den verschiedenen, von der [Bedrohungs- und Sicherheitsrisikoverwaltung](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) überprüften sicheren Konfigurationen – z. B., ob auf einem Gerät automatische Updates aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="5b34e-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="5b34e-108">Sie enthält außerdem Sicherheitsrisikoinformationen, relevante Branchenbenchmarks sowie anwendbare MITRE ATT&CK-Techniken und -Taktiken.</span><span class="sxs-lookup"><span data-stu-id="5b34e-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="5b34e-109">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="5b34e-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="5b34e-110">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="5b34e-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5b34e-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="5b34e-111">Column name</span></span> | <span data-ttu-id="5b34e-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5b34e-112">Data type</span></span> | <span data-ttu-id="5b34e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b34e-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="5b34e-114">string</span><span class="sxs-lookup"><span data-stu-id="5b34e-114">string</span></span> | <span data-ttu-id="5b34e-115">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5b34e-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="5b34e-116">string</span><span class="sxs-lookup"><span data-stu-id="5b34e-116">string</span></span> | <span data-ttu-id="5b34e-117">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="5b34e-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="5b34e-118">string</span><span class="sxs-lookup"><span data-stu-id="5b34e-118">string</span></span> | <span data-ttu-id="5b34e-119">Anzeigename der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5b34e-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="5b34e-120">string</span><span class="sxs-lookup"><span data-stu-id="5b34e-120">string</span></span> | <span data-ttu-id="5b34e-121">Beschreibung der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5b34e-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="5b34e-122">string</span><span class="sxs-lookup"><span data-stu-id="5b34e-122">string</span></span> | <span data-ttu-id="5b34e-123">Beschreibung des zugehörigen Risikos</span><span class="sxs-lookup"><span data-stu-id="5b34e-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="5b34e-124">string</span><span class="sxs-lookup"><span data-stu-id="5b34e-124">string</span></span> | <span data-ttu-id="5b34e-125">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="5b34e-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="5b34e-126">string</span><span class="sxs-lookup"><span data-stu-id="5b34e-126">string</span></span> |<span data-ttu-id="5b34e-127">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="5b34e-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="5b34e-128">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="5b34e-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="5b34e-129">string</span><span class="sxs-lookup"><span data-stu-id="5b34e-129">string</span></span> | <span data-ttu-id="5b34e-130">Liste der Branchenbenchmarks, die dieselben oder ähnliche Konfigurationen empfehlen</span><span class="sxs-lookup"><span data-stu-id="5b34e-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="5b34e-131">string</span><span class="sxs-lookup"><span data-stu-id="5b34e-131">string</span></span> | <span data-ttu-id="5b34e-132">Bezeichnungen, die verschiedene Attribute darstellen, die zum Identifizieren oder Kategorisieren einer Sicherheitskonfiguration verwendet werden</span><span class="sxs-lookup"><span data-stu-id="5b34e-132">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="5b34e-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b34e-133">string</span></span> | <span data-ttu-id="5b34e-134">Empfohlene Maßnahmen zum Reduzieren oder Adressieren zugeordneter Risiken</span><span class="sxs-lookup"><span data-stu-id="5b34e-134">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5b34e-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="5b34e-135">Related topics</span></span>

- [<span data-ttu-id="5b34e-136">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="5b34e-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5b34e-137">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="5b34e-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5b34e-138">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="5b34e-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5b34e-139">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="5b34e-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5b34e-140">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="5b34e-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5b34e-141">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="5b34e-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="5b34e-142">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="5b34e-142">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
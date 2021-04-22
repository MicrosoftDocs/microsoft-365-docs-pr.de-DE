---
title: Tabelle "DeviceTvmSoftwareVulnerabilitiesKB" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die Softwaresicherheitsrisiken, die durch die Bedrohungs- und Sicherheitsrisikoverwaltung in der Tabelle "DeviceTvmSoftwareVulnerabilitiesKB" des Schemas "Erweiterte Suche" nachverfolgt werden.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema, reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 0c9a29a75b2dc6ea2ae88f84e21ee2ab6455b2b0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933013"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="e6a59-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="e6a59-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e6a59-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e6a59-105">**Applies to:**</span></span>
- <span data-ttu-id="e6a59-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6a59-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="e6a59-107">Die Tabelle `DeviceTvmSoftwareVulnerabilitiesKB` im Schema "Erweiterte Suche" enthält die Liste der Sicherheitsrisiken, nach denen Geräte durch die [Bedrohungs- und Sicherheitsrisikoverwaltung](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) bewertet werden.</span><span class="sxs-lookup"><span data-stu-id="e6a59-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="e6a59-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="e6a59-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="e6a59-109">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="e6a59-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e6a59-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="e6a59-110">Column name</span></span> | <span data-ttu-id="e6a59-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e6a59-111">Data type</span></span> | <span data-ttu-id="e6a59-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6a59-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="e6a59-113">string</span><span class="sxs-lookup"><span data-stu-id="e6a59-113">string</span></span> | <span data-ttu-id="e6a59-114">Eindeutiger Bezeichner des Sicherheitsrisikos nach CVE (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="e6a59-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="e6a59-115">string</span><span class="sxs-lookup"><span data-stu-id="e6a59-115">string</span></span> | <span data-ttu-id="e6a59-116">Schweregrad des Sicherheitsrisikos nach CVSS (Common Vulnerability Scoring System)</span><span class="sxs-lookup"><span data-stu-id="e6a59-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="e6a59-117">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="e6a59-117">boolean</span></span> | <span data-ttu-id="e6a59-118">Gibt an, ob Exploitcode für das Sicherheitsrisiko öffentlich verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="e6a59-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="e6a59-119">string</span><span class="sxs-lookup"><span data-stu-id="e6a59-119">string</span></span> | <span data-ttu-id="e6a59-120">Schweregrad des Sicherheitsrisikos, basierend auf CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden</span><span class="sxs-lookup"><span data-stu-id="e6a59-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="e6a59-121">datetime</span><span class="sxs-lookup"><span data-stu-id="e6a59-121">datetime</span></span> | <span data-ttu-id="e6a59-122">Datum und Uhrzeit der letzten Änderung des Elements oder der zugehörigen Metadaten</span><span class="sxs-lookup"><span data-stu-id="e6a59-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="e6a59-123">datetime</span><span class="sxs-lookup"><span data-stu-id="e6a59-123">datetime</span></span> | <span data-ttu-id="e6a59-124">Datum der Veröffentlichung des Sicherheitsrisikos für die Allgemeinheit</span><span class="sxs-lookup"><span data-stu-id="e6a59-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="e6a59-125">string</span><span class="sxs-lookup"><span data-stu-id="e6a59-125">string</span></span> | <span data-ttu-id="e6a59-126">Beschreibung des Sicherheitsrisikos und der damit verbundenen Risiken</span><span class="sxs-lookup"><span data-stu-id="e6a59-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="e6a59-127">string</span><span class="sxs-lookup"><span data-stu-id="e6a59-127">string</span></span> | <span data-ttu-id="e6a59-128">Liste aller von dem Sicherheitsrisiko betroffenen Softwareprodukte</span><span class="sxs-lookup"><span data-stu-id="e6a59-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e6a59-129">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e6a59-129">Related topics</span></span>

- [<span data-ttu-id="e6a59-130">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="e6a59-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e6a59-131">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="e6a59-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e6a59-132">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="e6a59-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e6a59-133">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="e6a59-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e6a59-134">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="e6a59-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e6a59-135">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="e6a59-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e6a59-136">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="e6a59-136">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
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
ms.openlocfilehash: afcd6bcd81e1a8635be9ced766c533ea4195334f
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023797"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="17685-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="17685-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="17685-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="17685-105">**Applies to:**</span></span>
- <span data-ttu-id="17685-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17685-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="17685-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="17685-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="17685-108">Die Tabelle `DeviceTvmSoftwareVulnerabilitiesKB` im Schema "Erweiterte Suche" enthält die Liste der Sicherheitsrisiken, nach denen Geräte durch die [Bedrohungs- und Sicherheitsrisikoverwaltung](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) bewertet werden.</span><span class="sxs-lookup"><span data-stu-id="17685-108">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="17685-109">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="17685-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="17685-110">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="17685-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="17685-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="17685-111">Column name</span></span> | <span data-ttu-id="17685-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="17685-112">Data type</span></span> | <span data-ttu-id="17685-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17685-113">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="17685-114">string</span><span class="sxs-lookup"><span data-stu-id="17685-114">string</span></span> | <span data-ttu-id="17685-115">Eindeutiger Bezeichner des Sicherheitsrisikos nach CVE (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="17685-115">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="17685-116">string</span><span class="sxs-lookup"><span data-stu-id="17685-116">string</span></span> | <span data-ttu-id="17685-117">Schweregrad des Sicherheitsrisikos nach CVSS (Common Vulnerability Scoring System)</span><span class="sxs-lookup"><span data-stu-id="17685-117">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="17685-118">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="17685-118">boolean</span></span> | <span data-ttu-id="17685-119">Gibt an, ob Exploitcode für das Sicherheitsrisiko öffentlich verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="17685-119">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="17685-120">string</span><span class="sxs-lookup"><span data-stu-id="17685-120">string</span></span> | <span data-ttu-id="17685-121">Schweregrad des Sicherheitsrisikos, basierend auf CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden</span><span class="sxs-lookup"><span data-stu-id="17685-121">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="17685-122">datetime</span><span class="sxs-lookup"><span data-stu-id="17685-122">datetime</span></span> | <span data-ttu-id="17685-123">Datum und Uhrzeit der letzten Änderung des Elements oder der zugehörigen Metadaten</span><span class="sxs-lookup"><span data-stu-id="17685-123">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="17685-124">datetime</span><span class="sxs-lookup"><span data-stu-id="17685-124">datetime</span></span> | <span data-ttu-id="17685-125">Datum der Veröffentlichung des Sicherheitsrisikos für die Allgemeinheit</span><span class="sxs-lookup"><span data-stu-id="17685-125">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="17685-126">string</span><span class="sxs-lookup"><span data-stu-id="17685-126">string</span></span> | <span data-ttu-id="17685-127">Beschreibung des Sicherheitsrisikos und der damit verbundenen Risiken</span><span class="sxs-lookup"><span data-stu-id="17685-127">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="17685-128">string</span><span class="sxs-lookup"><span data-stu-id="17685-128">string</span></span> | <span data-ttu-id="17685-129">Liste aller von dem Sicherheitsrisiko betroffenen Softwareprodukte</span><span class="sxs-lookup"><span data-stu-id="17685-129">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="17685-130">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="17685-130">Related topics</span></span>

- [<span data-ttu-id="17685-131">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="17685-131">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="17685-132">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="17685-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="17685-133">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="17685-133">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="17685-134">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="17685-134">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="17685-135">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="17685-135">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="17685-136">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="17685-136">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="17685-137">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="17685-137">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
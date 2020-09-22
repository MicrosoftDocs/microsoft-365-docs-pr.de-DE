---
title: Tabelle "DeviceTvmSoftwareVulnerabilitiesKB" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die Softwaresicherheitsrisiken, die durch die Bedrohungs- und Sicherheitsrisikoverwaltung in der Tabelle "DeviceTvmSoftwareVulnerabilitiesKB" des Schemas "Erweiterte Suche" nachverfolgt werden.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schema, Referenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, Bedrohung & Vulnerability Management, TVM, Geräteverwaltung, Software, Inventar, Sicherheitsanfälligkeiten, CVE-ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: f486a4187ed904f460d5c2677663a5a6b5513ff5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198133"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="b8afc-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="b8afc-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b8afc-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b8afc-105">**Applies to:**</span></span>
- <span data-ttu-id="b8afc-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8afc-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="b8afc-107">Die Tabelle `DeviceTvmSoftwareVulnerabilitiesKB` im Schema "Erweiterte Suche" enthält die Liste der Sicherheitsrisiken, nach denen Geräte durch die [Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) bewertet werden.</span><span class="sxs-lookup"><span data-stu-id="b8afc-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="b8afc-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b8afc-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="b8afc-109">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b8afc-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b8afc-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="b8afc-110">Column name</span></span> | <span data-ttu-id="b8afc-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b8afc-111">Data type</span></span> | <span data-ttu-id="b8afc-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8afc-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="b8afc-113">string</span><span class="sxs-lookup"><span data-stu-id="b8afc-113">string</span></span> | <span data-ttu-id="b8afc-114">Eindeutiger Bezeichner des Sicherheitsrisikos nach CVE (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="b8afc-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="b8afc-115">string</span><span class="sxs-lookup"><span data-stu-id="b8afc-115">string</span></span> | <span data-ttu-id="b8afc-116">Schweregrad des Sicherheitsrisikos nach CVSS (Common Vulnerability Scoring System)</span><span class="sxs-lookup"><span data-stu-id="b8afc-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="b8afc-117">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="b8afc-117">boolean</span></span> | <span data-ttu-id="b8afc-118">Gibt an, ob Exploitcode für das Sicherheitsrisiko öffentlich verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="b8afc-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="b8afc-119">string</span><span class="sxs-lookup"><span data-stu-id="b8afc-119">string</span></span> | <span data-ttu-id="b8afc-120">Schweregrad des Sicherheitsrisikos, basierend auf CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden</span><span class="sxs-lookup"><span data-stu-id="b8afc-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="b8afc-121">datetime</span><span class="sxs-lookup"><span data-stu-id="b8afc-121">datetime</span></span> | <span data-ttu-id="b8afc-122">Datum und Uhrzeit der letzten Änderung des Elements oder der zugehörigen Metadaten</span><span class="sxs-lookup"><span data-stu-id="b8afc-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="b8afc-123">datetime</span><span class="sxs-lookup"><span data-stu-id="b8afc-123">datetime</span></span> | <span data-ttu-id="b8afc-124">Datum der Veröffentlichung des Sicherheitsrisikos für die Allgemeinheit</span><span class="sxs-lookup"><span data-stu-id="b8afc-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="b8afc-125">string</span><span class="sxs-lookup"><span data-stu-id="b8afc-125">string</span></span> | <span data-ttu-id="b8afc-126">Beschreibung des Sicherheitsrisikos und der damit verbundenen Risiken</span><span class="sxs-lookup"><span data-stu-id="b8afc-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="b8afc-127">string</span><span class="sxs-lookup"><span data-stu-id="b8afc-127">string</span></span> | <span data-ttu-id="b8afc-128">Liste aller von dem Sicherheitsrisiko betroffenen Softwareprodukte</span><span class="sxs-lookup"><span data-stu-id="b8afc-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b8afc-129">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b8afc-129">Related topics</span></span>

- [<span data-ttu-id="b8afc-130">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="b8afc-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b8afc-131">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="b8afc-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b8afc-132">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="b8afc-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b8afc-133">Suchen auf Geräten, in E-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="b8afc-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b8afc-134">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="b8afc-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b8afc-135">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="b8afc-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b8afc-136">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="b8afc-136">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

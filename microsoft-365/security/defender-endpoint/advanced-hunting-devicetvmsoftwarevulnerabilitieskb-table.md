---
title: Tabelle "DeviceTvmSoftwareVulnerabilitiesKB" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die Softwaresicherheitsrisiken, die durch die Bedrohungs- und Sicherheitsrisikoverwaltung in der Tabelle "DeviceTvmSoftwareVulnerabilitiesKB" des Schemas "Erweiterte Suche" nachverfolgt werden.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 772a287097f0b204eb329d066cdd81c4eef7a755
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062887"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="f7104-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="f7104-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f7104-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f7104-105">**Applies to:**</span></span>
- [<span data-ttu-id="f7104-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f7104-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="f7104-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f7104-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f7104-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f7104-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f7104-109">Die Tabelle `DeviceTvmSoftwareVulnerabilitiesKB` im Schema "Erweiterte Suche" enthält die Liste der Sicherheitsrisiken, nach denen Geräte durch die [Bedrohungs- und Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md) bewertet werden.</span><span class="sxs-lookup"><span data-stu-id="f7104-109">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) assesses devices for.</span></span> <span data-ttu-id="f7104-110">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f7104-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="f7104-111">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="f7104-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="f7104-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f7104-112">Column name</span></span> | <span data-ttu-id="f7104-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f7104-113">Data type</span></span> | <span data-ttu-id="f7104-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7104-114">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="f7104-115">string</span><span class="sxs-lookup"><span data-stu-id="f7104-115">string</span></span> | <span data-ttu-id="f7104-116">Eindeutiger Bezeichner des Sicherheitsrisikos nach CVE (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="f7104-116">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="f7104-117">string</span><span class="sxs-lookup"><span data-stu-id="f7104-117">string</span></span> | <span data-ttu-id="f7104-118">Schweregrad des Sicherheitsrisikos nach CVSS (Common Vulnerability Scoring System)</span><span class="sxs-lookup"><span data-stu-id="f7104-118">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="f7104-119">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="f7104-119">boolean</span></span> | <span data-ttu-id="f7104-120">Gibt an, ob Exploitcode für das Sicherheitsrisiko öffentlich verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="f7104-120">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="f7104-121">string</span><span class="sxs-lookup"><span data-stu-id="f7104-121">string</span></span> | <span data-ttu-id="f7104-122">Schweregrad des Sicherheitsrisikos, basierend auf CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden</span><span class="sxs-lookup"><span data-stu-id="f7104-122">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="f7104-123">datetime</span><span class="sxs-lookup"><span data-stu-id="f7104-123">datetime</span></span> | <span data-ttu-id="f7104-124">Datum und Uhrzeit der letzten Änderung des Elements oder der zugehörigen Metadaten</span><span class="sxs-lookup"><span data-stu-id="f7104-124">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="f7104-125">datetime</span><span class="sxs-lookup"><span data-stu-id="f7104-125">datetime</span></span> | <span data-ttu-id="f7104-126">Datum der Veröffentlichung des Sicherheitsrisikos für die Allgemeinheit</span><span class="sxs-lookup"><span data-stu-id="f7104-126">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="f7104-127">string</span><span class="sxs-lookup"><span data-stu-id="f7104-127">string</span></span> | <span data-ttu-id="f7104-128">Beschreibung des Sicherheitsrisikos und der damit verbundenen Risiken</span><span class="sxs-lookup"><span data-stu-id="f7104-128">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="f7104-129">string</span><span class="sxs-lookup"><span data-stu-id="f7104-129">string</span></span> | <span data-ttu-id="f7104-130">Liste aller von dem Sicherheitsrisiko betroffenen Softwareprodukte</span><span class="sxs-lookup"><span data-stu-id="f7104-130">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f7104-131">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f7104-131">Related topics</span></span>

- [<span data-ttu-id="f7104-132">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="f7104-132">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f7104-133">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="f7104-133">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f7104-134">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="f7104-134">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="f7104-135">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="f7104-135">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)

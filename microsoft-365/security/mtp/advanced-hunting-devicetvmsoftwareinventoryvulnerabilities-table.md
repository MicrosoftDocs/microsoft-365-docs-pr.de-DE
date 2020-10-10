---
title: Tabelle „DeviceTvmSoftwareInventoryVulnerabilities“ im Schema „Erweiterte Suche“
description: Erfahren Sie mehr über den Softwarebestand auf Ihren Geräten und deren Sicherheitsrisiken in der DeviceTvmSoftwareInventoryVulnerabilities-Tabelle des Schemas „Erweiterte Suche“.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, Bedrohung & Vulnerability Management, TVM, Geräteverwaltung, Software, Inventar, Sicherheitsanfälligkeiten, CVE-ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: d8858fe9acd8183ad0d8644a9d5e4d70d32990a6
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413222"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="98aed-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="98aed-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="98aed-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="98aed-105">**Applies to:**</span></span>
- <span data-ttu-id="98aed-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="98aed-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="98aed-107">Die `DeviceTvmSoftwareInventoryVulnerabilities` Tabelle im Schema „Erweiterte Suche“ enthält den Softwarebestand für die [Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) auf Ihren Geräten sowie alle bekannten Sicherheitsrisiken in diesen Softwareprodukten.</span><span class="sxs-lookup"><span data-stu-id="98aed-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="98aed-108">Diese Tabelle enthält außerdem Betriebssysteminformationen, CVE-IDs und Informationen zum Schweregrad des Sicherheitsrisikos.</span><span class="sxs-lookup"><span data-stu-id="98aed-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="98aed-109">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="98aed-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="98aed-110">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="98aed-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="98aed-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="98aed-111">Column name</span></span> | <span data-ttu-id="98aed-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="98aed-112">Data type</span></span> | <span data-ttu-id="98aed-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98aed-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="98aed-114">string</span><span class="sxs-lookup"><span data-stu-id="98aed-114">string</span></span> | <span data-ttu-id="98aed-115">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="98aed-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="98aed-116">string</span><span class="sxs-lookup"><span data-stu-id="98aed-116">string</span></span> | <span data-ttu-id="98aed-117">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="98aed-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="98aed-118">string</span><span class="sxs-lookup"><span data-stu-id="98aed-118">string</span></span> | <span data-ttu-id="98aed-119">Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="98aed-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="98aed-120">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="98aed-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="98aed-121">string</span><span class="sxs-lookup"><span data-stu-id="98aed-121">string</span></span> | <span data-ttu-id="98aed-122">Die Version des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="98aed-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="98aed-123">string</span><span class="sxs-lookup"><span data-stu-id="98aed-123">string</span></span> | <span data-ttu-id="98aed-124">Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="98aed-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="98aed-125">string</span><span class="sxs-lookup"><span data-stu-id="98aed-125">string</span></span> | <span data-ttu-id="98aed-126">Name des Softwareanbieters</span><span class="sxs-lookup"><span data-stu-id="98aed-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="98aed-127">string</span><span class="sxs-lookup"><span data-stu-id="98aed-127">string</span></span> | <span data-ttu-id="98aed-128">Name des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="98aed-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="98aed-129">string</span><span class="sxs-lookup"><span data-stu-id="98aed-129">string</span></span> | <span data-ttu-id="98aed-130">Versionsnummer des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="98aed-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="98aed-131">string</span><span class="sxs-lookup"><span data-stu-id="98aed-131">string</span></span> | <span data-ttu-id="98aed-132">Eindeutiger Bezeichner des Sicherheitsrisikos nach CVE (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="98aed-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="98aed-133">string</span><span class="sxs-lookup"><span data-stu-id="98aed-133">string</span></span> | <span data-ttu-id="98aed-134">Schweregrad des Sicherheitsrisikos, basierend auf CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden</span><span class="sxs-lookup"><span data-stu-id="98aed-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="98aed-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="98aed-135">Related topics</span></span>

- [<span data-ttu-id="98aed-136">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="98aed-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="98aed-137">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="98aed-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="98aed-138">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="98aed-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="98aed-139">Suchen auf Geräten, in E-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="98aed-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="98aed-140">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="98aed-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="98aed-141">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="98aed-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="98aed-142">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="98aed-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

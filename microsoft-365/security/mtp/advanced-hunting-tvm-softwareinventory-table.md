---
title: Tabelle „DeviceTvmSoftwareInventoryVulnerabilities“ im Schema „Erweiterte Suche“
description: Erfahren Sie mehr über den Softwarebestand auf Ihren Geräten und deren Sicherheitsrisiken in der DeviceTvmSoftwareInventoryVulnerabilities-Tabelle des Schemas „Erweiterte Suche“.
keywords: 'Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, Bedrohung #a0 Vulnerability Management, TVM, Geräteverwaltung, Software, Inventar, Sicherheitsanfälligkeiten, CVE-ID, OS DeviceTvmSoftwareInventoryVulnerabilities'
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: d3b85bcbc2cb65cc434c7af0ba078bd835d8203f
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210497"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="a5cf4-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="a5cf4-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

<span data-ttu-id="a5cf4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a5cf4-105">**Applies to:**</span></span>
- <span data-ttu-id="a5cf4-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a5cf4-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a5cf4-107">Die `DeviceTvmSoftwareInventoryVulnerabilities` Tabelle im Schema „Erweiterte Suche“ enthält den Softwarebestand für die [Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) auf Ihren Geräten sowie alle bekannten Sicherheitsrisiken in diesen Softwareprodukten.</span><span class="sxs-lookup"><span data-stu-id="a5cf4-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="a5cf4-108">Diese Tabelle enthält außerdem Betriebssysteminformationen, CVE-IDs und Informationen zum Schweregrad des Sicherheitsrisikos.</span><span class="sxs-lookup"><span data-stu-id="a5cf4-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="a5cf4-109">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a5cf4-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="a5cf4-110">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a5cf4-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a5cf4-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="a5cf4-111">Column name</span></span> | <span data-ttu-id="a5cf4-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a5cf4-112">Data type</span></span> | <span data-ttu-id="a5cf4-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5cf4-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="a5cf4-114">string</span><span class="sxs-lookup"><span data-stu-id="a5cf4-114">string</span></span> | <span data-ttu-id="a5cf4-115">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="a5cf4-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a5cf4-116">string</span><span class="sxs-lookup"><span data-stu-id="a5cf4-116">string</span></span> | <span data-ttu-id="a5cf4-117">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="a5cf4-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="a5cf4-118">string</span><span class="sxs-lookup"><span data-stu-id="a5cf4-118">string</span></span> | <span data-ttu-id="a5cf4-119">Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a5cf4-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="a5cf4-120">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="a5cf4-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="a5cf4-121">string</span><span class="sxs-lookup"><span data-stu-id="a5cf4-121">string</span></span> | <span data-ttu-id="a5cf4-122">Die Version des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a5cf4-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="a5cf4-123">string</span><span class="sxs-lookup"><span data-stu-id="a5cf4-123">string</span></span> | <span data-ttu-id="a5cf4-124">Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a5cf4-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="a5cf4-125">string</span><span class="sxs-lookup"><span data-stu-id="a5cf4-125">string</span></span> | <span data-ttu-id="a5cf4-126">Schweregrad des Sicherheitsrisikos, basierend auf CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden</span><span class="sxs-lookup"><span data-stu-id="a5cf4-126">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `SoftwareName` | <span data-ttu-id="a5cf4-127">string</span><span class="sxs-lookup"><span data-stu-id="a5cf4-127">string</span></span> | <span data-ttu-id="a5cf4-128">Name des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="a5cf4-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="a5cf4-129">string</span><span class="sxs-lookup"><span data-stu-id="a5cf4-129">string</span></span> | <span data-ttu-id="a5cf4-130">Versionsnummer des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="a5cf4-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="a5cf4-131">string</span><span class="sxs-lookup"><span data-stu-id="a5cf4-131">string</span></span> | <span data-ttu-id="a5cf4-132">Eindeutiger Bezeichner des Sicherheitsrisikos nach CVE (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="a5cf4-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="a5cf4-133">string</span><span class="sxs-lookup"><span data-stu-id="a5cf4-133">string</span></span> | <span data-ttu-id="a5cf4-134">Schweregrad des Sicherheitsrisikos, basierend auf CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden</span><span class="sxs-lookup"><span data-stu-id="a5cf4-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="a5cf4-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a5cf4-135">Related topics</span></span>

- [<span data-ttu-id="a5cf4-136">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="a5cf4-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a5cf4-137">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="a5cf4-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a5cf4-138">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="a5cf4-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a5cf4-139">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="a5cf4-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a5cf4-140">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="a5cf4-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a5cf4-141">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="a5cf4-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="a5cf4-142">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="a5cf4-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

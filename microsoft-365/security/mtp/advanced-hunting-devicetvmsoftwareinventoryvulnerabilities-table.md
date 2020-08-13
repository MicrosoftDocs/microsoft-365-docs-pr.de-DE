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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 70b687a185538b11cf0a8975eebf2a5d8b53ec11
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648953"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="7bd69-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="7bd69-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

<span data-ttu-id="7bd69-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7bd69-105">**Applies to:**</span></span>
- <span data-ttu-id="7bd69-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7bd69-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="7bd69-107">Die `DeviceTvmSoftwareInventoryVulnerabilities` Tabelle im Schema „Erweiterte Suche“ enthält den Softwarebestand für die [Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) auf Ihren Geräten sowie alle bekannten Sicherheitsrisiken in diesen Softwareprodukten.</span><span class="sxs-lookup"><span data-stu-id="7bd69-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="7bd69-108">Diese Tabelle enthält außerdem Betriebssysteminformationen, CVE-IDs und Informationen zum Schweregrad des Sicherheitsrisikos.</span><span class="sxs-lookup"><span data-stu-id="7bd69-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="7bd69-109">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7bd69-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="7bd69-110">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7bd69-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7bd69-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7bd69-111">Column name</span></span> | <span data-ttu-id="7bd69-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="7bd69-112">Data type</span></span> | <span data-ttu-id="7bd69-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7bd69-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="7bd69-114">string</span><span class="sxs-lookup"><span data-stu-id="7bd69-114">string</span></span> | <span data-ttu-id="7bd69-115">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="7bd69-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="7bd69-116">string</span><span class="sxs-lookup"><span data-stu-id="7bd69-116">string</span></span> | <span data-ttu-id="7bd69-117">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="7bd69-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="7bd69-118">string</span><span class="sxs-lookup"><span data-stu-id="7bd69-118">string</span></span> | <span data-ttu-id="7bd69-119">Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7bd69-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="7bd69-120">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="7bd69-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="7bd69-121">string</span><span class="sxs-lookup"><span data-stu-id="7bd69-121">string</span></span> | <span data-ttu-id="7bd69-122">Die Version des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7bd69-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="7bd69-123">string</span><span class="sxs-lookup"><span data-stu-id="7bd69-123">string</span></span> | <span data-ttu-id="7bd69-124">Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7bd69-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="7bd69-125">string</span><span class="sxs-lookup"><span data-stu-id="7bd69-125">string</span></span> | <span data-ttu-id="7bd69-126">Name des Softwareanbieters</span><span class="sxs-lookup"><span data-stu-id="7bd69-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="7bd69-127">string</span><span class="sxs-lookup"><span data-stu-id="7bd69-127">string</span></span> | <span data-ttu-id="7bd69-128">Name des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="7bd69-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="7bd69-129">string</span><span class="sxs-lookup"><span data-stu-id="7bd69-129">string</span></span> | <span data-ttu-id="7bd69-130">Versionsnummer des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="7bd69-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="7bd69-131">string</span><span class="sxs-lookup"><span data-stu-id="7bd69-131">string</span></span> | <span data-ttu-id="7bd69-132">Eindeutiger Bezeichner des Sicherheitsrisikos nach CVE (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="7bd69-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="7bd69-133">string</span><span class="sxs-lookup"><span data-stu-id="7bd69-133">string</span></span> | <span data-ttu-id="7bd69-134">Schweregrad des Sicherheitsrisikos, basierend auf CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden</span><span class="sxs-lookup"><span data-stu-id="7bd69-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="7bd69-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7bd69-135">Related topics</span></span>

- [<span data-ttu-id="7bd69-136">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="7bd69-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7bd69-137">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="7bd69-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7bd69-138">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="7bd69-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7bd69-139">Jagd auf Geräte, e-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="7bd69-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7bd69-140">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="7bd69-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7bd69-141">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="7bd69-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="7bd69-142">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="7bd69-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

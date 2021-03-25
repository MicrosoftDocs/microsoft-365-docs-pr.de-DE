---
title: Tabelle „DeviceTvmSoftwareInventoryVulnerabilities“ im Schema „Erweiterte Suche“
description: Erfahren Sie mehr über den Softwarebestand auf Ihren Geräten und deren Sicherheitsrisiken in der DeviceTvmSoftwareInventoryVulnerabilities-Tabelle des Schemas „Erweiterte Suche“.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: bbb535aa3f106c8569edb3c64ba95bba9bf36186
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163459"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="f4400-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="f4400-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f4400-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f4400-105">**Applies to:**</span></span>

- [<span data-ttu-id="f4400-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f4400-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="f4400-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f4400-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f4400-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f4400-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f4400-109">Die `DeviceTvmSoftwareInventoryVulnerabilities` Tabelle im Schema „Erweiterte Suche“ enthält den Softwarebestand für die [Bedrohungs- und Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md) auf Ihren Geräten sowie alle bekannten Sicherheitsrisiken in diesen Softwareprodukten.</span><span class="sxs-lookup"><span data-stu-id="f4400-109">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="f4400-110">Diese Tabelle enthält außerdem Betriebssysteminformationen, CVE-IDs und Informationen zum Schweregrad des Sicherheitsrisikos.</span><span class="sxs-lookup"><span data-stu-id="f4400-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="f4400-111">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f4400-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="f4400-112">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="f4400-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="f4400-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f4400-113">Column name</span></span> | <span data-ttu-id="f4400-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f4400-114">Data type</span></span> | <span data-ttu-id="f4400-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4400-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="f4400-116">string</span><span class="sxs-lookup"><span data-stu-id="f4400-116">string</span></span> | <span data-ttu-id="f4400-117">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="f4400-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f4400-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4400-118">string</span></span> | <span data-ttu-id="f4400-119">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="f4400-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="f4400-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4400-120">string</span></span> | <span data-ttu-id="f4400-121">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f4400-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f4400-122">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="f4400-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="f4400-123">string</span><span class="sxs-lookup"><span data-stu-id="f4400-123">string</span></span> | <span data-ttu-id="f4400-124">Version des Betriebssystems, das auf dem Gerät ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="f4400-124">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="f4400-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4400-125">string</span></span> | <span data-ttu-id="f4400-126">Architektur des Betriebssystems, das auf dem Gerät ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="f4400-126">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="f4400-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4400-127">string</span></span> | <span data-ttu-id="f4400-128">Name des Softwareanbieters</span><span class="sxs-lookup"><span data-stu-id="f4400-128">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="f4400-129">string</span><span class="sxs-lookup"><span data-stu-id="f4400-129">string</span></span> | <span data-ttu-id="f4400-130">Name des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="f4400-130">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="f4400-131">string</span><span class="sxs-lookup"><span data-stu-id="f4400-131">string</span></span> | <span data-ttu-id="f4400-132">Versionsnummer des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="f4400-132">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="f4400-133">string</span><span class="sxs-lookup"><span data-stu-id="f4400-133">string</span></span> | <span data-ttu-id="f4400-134">Eindeutiger Bezeichner des Sicherheitsrisikos nach CVE (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="f4400-134">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="f4400-135">string</span><span class="sxs-lookup"><span data-stu-id="f4400-135">string</span></span> | <span data-ttu-id="f4400-136">Schweregrad des Sicherheitsrisikos, basierend auf CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden</span><span class="sxs-lookup"><span data-stu-id="f4400-136">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="f4400-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f4400-137">Related topics</span></span>

- [<span data-ttu-id="f4400-138">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="f4400-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f4400-139">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="f4400-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f4400-140">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="f4400-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="f4400-141">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="f4400-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)

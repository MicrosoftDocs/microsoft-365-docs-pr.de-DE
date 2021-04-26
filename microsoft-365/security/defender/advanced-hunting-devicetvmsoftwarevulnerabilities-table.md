---
title: DeviceTvmSoftwareVulnerabilities-Tabelle im schema der erweiterten Suche
description: Erfahren Sie mehr über die Softwarerisiken auf Geräten und die Liste der verfügbaren Sicherheitsupdates, die die einzelnen Sicherheitsrisiken in der DeviceTvmSoftwareVulnerabilities-Tabelle des Schemas für die erweiterte Suche adressieren.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 17faffc45cfd1f472dec3f423681aaa3f64944a3
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023809"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="991e7-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="991e7-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="991e7-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="991e7-105">**Applies to:**</span></span>
- <span data-ttu-id="991e7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="991e7-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="991e7-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="991e7-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="991e7-108">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="991e7-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="991e7-109">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="991e7-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="991e7-110">Die Tabelle im Schema der erweiterten Suche enthält die & Liste der Sicherheitsrisiken `DeviceTvmSoftwareVulnerabilities` in installierten [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Softwareprodukten.</span><span class="sxs-lookup"><span data-stu-id="991e7-110">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="991e7-111">Diese Tabelle enthält außerdem Betriebssysteminformationen, CVE-IDs und Informationen zum Schweregrad des Sicherheitsrisikos.</span><span class="sxs-lookup"><span data-stu-id="991e7-111">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="991e7-112">In dieser Tabelle können Sie beispielsweise nach Ereignissen mit Geräten mit schwerwiegenden Sicherheitsrisiken in ihrer Software fahnen.</span><span class="sxs-lookup"><span data-stu-id="991e7-112">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="991e7-113">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="991e7-113">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="991e7-114">The `DeviceTvmSoftwareInventory` and tables have replaced the `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` table.</span><span class="sxs-lookup"><span data-stu-id="991e7-114">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="991e7-115">Zusammen enthalten die ersten beiden Tabellen weitere Spalten, die Sie verwenden können, um Ihre Aktivitäten zur Verwaltung von Vulnerablität zu informieren oder nach anfälligen Geräten zu fahnen.</span><span class="sxs-lookup"><span data-stu-id="991e7-115">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="991e7-116">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="991e7-116">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="991e7-117">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="991e7-117">Column name</span></span> | <span data-ttu-id="991e7-118">Datentyp</span><span class="sxs-lookup"><span data-stu-id="991e7-118">Data type</span></span> | <span data-ttu-id="991e7-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="991e7-119">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="991e7-120">string</span><span class="sxs-lookup"><span data-stu-id="991e7-120">string</span></span> | <span data-ttu-id="991e7-121">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="991e7-121">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="991e7-122">string</span><span class="sxs-lookup"><span data-stu-id="991e7-122">string</span></span> | <span data-ttu-id="991e7-123">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="991e7-123">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="991e7-124">string</span><span class="sxs-lookup"><span data-stu-id="991e7-124">string</span></span> | <span data-ttu-id="991e7-125">Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="991e7-125">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="991e7-126">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="991e7-126">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="991e7-127">string</span><span class="sxs-lookup"><span data-stu-id="991e7-127">string</span></span> | <span data-ttu-id="991e7-128">Die Version des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="991e7-128">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="991e7-129">string</span><span class="sxs-lookup"><span data-stu-id="991e7-129">string</span></span> | <span data-ttu-id="991e7-130">Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="991e7-130">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="991e7-131">string</span><span class="sxs-lookup"><span data-stu-id="991e7-131">string</span></span> | <span data-ttu-id="991e7-132">Name des Softwareanbieters</span><span class="sxs-lookup"><span data-stu-id="991e7-132">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="991e7-133">string</span><span class="sxs-lookup"><span data-stu-id="991e7-133">string</span></span> | <span data-ttu-id="991e7-134">Name des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="991e7-134">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="991e7-135">string</span><span class="sxs-lookup"><span data-stu-id="991e7-135">string</span></span> | <span data-ttu-id="991e7-136">Versionsnummer des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="991e7-136">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="991e7-137">string</span><span class="sxs-lookup"><span data-stu-id="991e7-137">string</span></span> | <span data-ttu-id="991e7-138">Eindeutiger Bezeichner des Sicherheitsrisikos nach CVE (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="991e7-138">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="991e7-139">string</span><span class="sxs-lookup"><span data-stu-id="991e7-139">string</span></span> | <span data-ttu-id="991e7-140">Schweregrad des Sicherheitsrisikos, basierend auf CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden</span><span class="sxs-lookup"><span data-stu-id="991e7-140">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="991e7-141">string</span><span class="sxs-lookup"><span data-stu-id="991e7-141">string</span></span> | <span data-ttu-id="991e7-142">Name oder Beschreibung des vom Softwarehersteller bereitgestellten Sicherheitsupdates zur Beanwortung der Sicherheitslücke</span><span class="sxs-lookup"><span data-stu-id="991e7-142">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="991e7-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="991e7-143">string</span></span> | <span data-ttu-id="991e7-144">Bezeichner der anwendbaren Sicherheitsupdates oder bezeichner für die entsprechenden Anleitungen oder Knowledge Base (KB)-Artikel</span><span class="sxs-lookup"><span data-stu-id="991e7-144">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="991e7-145">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="991e7-145">Related topics</span></span>

- [<span data-ttu-id="991e7-146">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="991e7-146">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="991e7-147">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="991e7-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="991e7-148">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="991e7-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="991e7-149">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="991e7-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="991e7-150">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="991e7-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="991e7-151">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="991e7-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="991e7-152">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="991e7-152">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
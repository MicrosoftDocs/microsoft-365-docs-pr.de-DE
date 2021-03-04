---
title: DeviceTvmSoftwareVulnerabilities-Tabelle im schema der erweiterten Suche
description: Erfahren Sie mehr über die Softwarerisiken auf Geräten und die Liste der verfügbaren Sicherheitsupdates, die die einzelnen Sicherheitsrisiken in der DeviceTvmSoftwareVulnerabilities-Tabelle des Schemas für die erweiterte Suche adressieren.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c5a143d835120339ade006dfd2dc394ec7c542d3
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423873"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="12485-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="12485-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="12485-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="12485-105">**Applies to:**</span></span>
- <span data-ttu-id="12485-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12485-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="12485-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="12485-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="12485-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="12485-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="12485-109">Die Tabelle im Schema der erweiterten Suche enthält die & Liste der Sicherheitsrisiken `DeviceTvmSoftwareVulnerabilities` in installierten [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Softwareprodukten.</span><span class="sxs-lookup"><span data-stu-id="12485-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="12485-110">Diese Tabelle enthält außerdem Betriebssysteminformationen, CVE-IDs und Informationen zum Schweregrad des Sicherheitsrisikos.</span><span class="sxs-lookup"><span data-stu-id="12485-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="12485-111">In dieser Tabelle können Sie beispielsweise nach Ereignissen mit Geräten mit schwerwiegenden Sicherheitsrisiken in ihrer Software fahnen.</span><span class="sxs-lookup"><span data-stu-id="12485-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="12485-112">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="12485-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="12485-113">The `DeviceTvmSoftwareInventory` and tables have replaced the `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` table.</span><span class="sxs-lookup"><span data-stu-id="12485-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="12485-114">Zusammen enthalten die ersten beiden Tabellen weitere Spalten, die Sie verwenden können, um Ihre Aktivitäten zur Verwaltung von Vulnerablität zu informieren oder nach anfälligen Geräten zu fahnen.</span><span class="sxs-lookup"><span data-stu-id="12485-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="12485-115">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="12485-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="12485-116">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="12485-116">Column name</span></span> | <span data-ttu-id="12485-117">Datentyp</span><span class="sxs-lookup"><span data-stu-id="12485-117">Data type</span></span> | <span data-ttu-id="12485-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12485-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="12485-119">string</span><span class="sxs-lookup"><span data-stu-id="12485-119">string</span></span> | <span data-ttu-id="12485-120">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="12485-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="12485-121">string</span><span class="sxs-lookup"><span data-stu-id="12485-121">string</span></span> | <span data-ttu-id="12485-122">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="12485-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="12485-123">string</span><span class="sxs-lookup"><span data-stu-id="12485-123">string</span></span> | <span data-ttu-id="12485-124">Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="12485-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="12485-125">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="12485-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="12485-126">string</span><span class="sxs-lookup"><span data-stu-id="12485-126">string</span></span> | <span data-ttu-id="12485-127">Die Version des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="12485-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="12485-128">string</span><span class="sxs-lookup"><span data-stu-id="12485-128">string</span></span> | <span data-ttu-id="12485-129">Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="12485-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="12485-130">string</span><span class="sxs-lookup"><span data-stu-id="12485-130">string</span></span> | <span data-ttu-id="12485-131">Name des Softwareanbieters</span><span class="sxs-lookup"><span data-stu-id="12485-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="12485-132">string</span><span class="sxs-lookup"><span data-stu-id="12485-132">string</span></span> | <span data-ttu-id="12485-133">Name des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="12485-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="12485-134">string</span><span class="sxs-lookup"><span data-stu-id="12485-134">string</span></span> | <span data-ttu-id="12485-135">Versionsnummer des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="12485-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="12485-136">string</span><span class="sxs-lookup"><span data-stu-id="12485-136">string</span></span> | <span data-ttu-id="12485-137">Eindeutiger Bezeichner des Sicherheitsrisikos nach CVE (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="12485-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="12485-138">string</span><span class="sxs-lookup"><span data-stu-id="12485-138">string</span></span> | <span data-ttu-id="12485-139">Schweregrad des Sicherheitsrisikos, basierend auf CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden</span><span class="sxs-lookup"><span data-stu-id="12485-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="12485-140">string</span><span class="sxs-lookup"><span data-stu-id="12485-140">string</span></span> | <span data-ttu-id="12485-141">Name oder Beschreibung des vom Softwarehersteller bereitgestellten Sicherheitsupdates zur Beanwortung der Sicherheitslücke</span><span class="sxs-lookup"><span data-stu-id="12485-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="12485-142">string</span><span class="sxs-lookup"><span data-stu-id="12485-142">string</span></span> | <span data-ttu-id="12485-143">Bezeichner der anwendbaren Sicherheitsupdates oder bezeichner für die entsprechenden Anleitungen oder Knowledge Base (KB)-Artikel</span><span class="sxs-lookup"><span data-stu-id="12485-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="12485-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="12485-144">Related topics</span></span>

- [<span data-ttu-id="12485-145">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="12485-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="12485-146">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="12485-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="12485-147">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="12485-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="12485-148">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="12485-148">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="12485-149">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="12485-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="12485-150">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="12485-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="12485-151">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="12485-151">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

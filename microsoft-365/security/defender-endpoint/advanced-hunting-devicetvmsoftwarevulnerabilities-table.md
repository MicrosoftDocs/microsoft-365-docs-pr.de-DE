---
title: DeviceTvmSoftwareVulnerabilities-Tabelle im schema der erweiterten Suche
description: Erfahren Sie mehr über Softwarerisiken auf Geräten und die Liste der verfügbaren Sicherheitsupdates, die die einzelnen Sicherheitsrisiken in der Tabelle DeviceTvmSoftwareVulnerabilities des Schemas für die erweiterte Suche adressieren.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b38297cd0fa2e931619ff9c0557d2ae868c7aa4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067999"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="fc71a-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="fc71a-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fc71a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fc71a-105">**Applies to:**</span></span>
- [<span data-ttu-id="fc71a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="fc71a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="fc71a-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="fc71a-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fc71a-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="fc71a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="fc71a-109">Die Tabelle im Schema der erweiterten Suche enthält die & Liste der Sicherheitsrisiken `DeviceTvmSoftwareVulnerabilities` in installierten [](next-gen-threat-and-vuln-mgt.md) Softwareprodukten.</span><span class="sxs-lookup"><span data-stu-id="fc71a-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="fc71a-110">Diese Tabelle enthält außerdem Betriebssysteminformationen, CVE-IDs und Informationen zum Schweregrad des Sicherheitsrisikos.</span><span class="sxs-lookup"><span data-stu-id="fc71a-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="fc71a-111">In dieser Tabelle können Sie beispielsweise nach Ereignissen mit Geräten mit schwerwiegenden Sicherheitsrisiken in ihrer Software fahnen.</span><span class="sxs-lookup"><span data-stu-id="fc71a-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="fc71a-112">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="fc71a-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="fc71a-113">The `DeviceTvmSoftwareInventory` and tables have replaced the `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` table.</span><span class="sxs-lookup"><span data-stu-id="fc71a-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="fc71a-114">Zusammen enthalten die ersten beiden Tabellen weitere Spalten, die Sie verwenden können, um Ihre Aktivitäten zur Verwaltung von Sicherheitslücken zu informieren.</span><span class="sxs-lookup"><span data-stu-id="fc71a-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="fc71a-115">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="fc71a-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="fc71a-116">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="fc71a-116">Column name</span></span> | <span data-ttu-id="fc71a-117">Datentyp</span><span class="sxs-lookup"><span data-stu-id="fc71a-117">Data type</span></span> | <span data-ttu-id="fc71a-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc71a-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="fc71a-119">string</span><span class="sxs-lookup"><span data-stu-id="fc71a-119">string</span></span> | <span data-ttu-id="fc71a-120">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="fc71a-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="fc71a-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fc71a-121">string</span></span> | <span data-ttu-id="fc71a-122">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="fc71a-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="fc71a-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fc71a-123">string</span></span> | <span data-ttu-id="fc71a-124">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fc71a-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="fc71a-125">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="fc71a-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="fc71a-126">string</span><span class="sxs-lookup"><span data-stu-id="fc71a-126">string</span></span> | <span data-ttu-id="fc71a-127">Version des Betriebssystems, das auf dem Gerät ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="fc71a-127">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="fc71a-128">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fc71a-128">string</span></span> | <span data-ttu-id="fc71a-129">Architektur des Betriebssystems, das auf dem Gerät ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="fc71a-129">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="fc71a-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fc71a-130">string</span></span> | <span data-ttu-id="fc71a-131">Name des Softwareanbieters</span><span class="sxs-lookup"><span data-stu-id="fc71a-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="fc71a-132">string</span><span class="sxs-lookup"><span data-stu-id="fc71a-132">string</span></span> | <span data-ttu-id="fc71a-133">Name des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="fc71a-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="fc71a-134">string</span><span class="sxs-lookup"><span data-stu-id="fc71a-134">string</span></span> | <span data-ttu-id="fc71a-135">Versionsnummer des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="fc71a-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="fc71a-136">string</span><span class="sxs-lookup"><span data-stu-id="fc71a-136">string</span></span> | <span data-ttu-id="fc71a-137">Eindeutiger Bezeichner des Sicherheitsrisikos nach CVE (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="fc71a-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="fc71a-138">string</span><span class="sxs-lookup"><span data-stu-id="fc71a-138">string</span></span> | <span data-ttu-id="fc71a-139">Schweregrad des Sicherheitsrisikos, basierend auf CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden</span><span class="sxs-lookup"><span data-stu-id="fc71a-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="fc71a-140">string</span><span class="sxs-lookup"><span data-stu-id="fc71a-140">string</span></span> | <span data-ttu-id="fc71a-141">Name oder Beschreibung des vom Softwarehersteller bereitgestellten Sicherheitsupdates zur Beanwortung der Sicherheitslücke</span><span class="sxs-lookup"><span data-stu-id="fc71a-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="fc71a-142">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fc71a-142">string</span></span> | <span data-ttu-id="fc71a-143">Bezeichner der anwendbaren Sicherheitsupdates oder bezeichner für die entsprechenden Anleitungen oder Knowledge Base (KB)-Artikel</span><span class="sxs-lookup"><span data-stu-id="fc71a-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="fc71a-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="fc71a-144">Related topics</span></span>

- [<span data-ttu-id="fc71a-145">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="fc71a-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fc71a-146">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="fc71a-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fc71a-147">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="fc71a-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="fc71a-148">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="fc71a-148">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)

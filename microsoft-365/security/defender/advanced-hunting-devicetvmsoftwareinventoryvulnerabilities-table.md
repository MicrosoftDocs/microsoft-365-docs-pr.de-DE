---
title: DeviceTvmSoftwareInventory-Tabelle im schema der erweiterten Suche
description: Informationen zum Inventar der Software auf Ihren Geräten finden Sie in der DeviceTvmSoftwareInventory-Tabelle des schemas für die erweiterte Suche.
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 4d3aa317e3013e6fe8452bfbfd759bc1f003cd6f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065928"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="658c7-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="658c7-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="658c7-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="658c7-105">**Applies to:**</span></span>
- <span data-ttu-id="658c7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="658c7-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="658c7-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="658c7-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="658c7-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="658c7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="658c7-109">Die Tabelle im Schema für die erweiterte Suche enthält das Inventar & Threat & Vulnerability Management der software, die derzeit auf Geräten in Ihrem Netzwerk installiert ist, einschließlich Der Ende `DeviceTvmSoftwareInventory` der Supportinformationen. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="658c7-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="658c7-110">Sie können z. B. nach Ereignissen suchen, die Geräte enthalten, die mit einer derzeit anfälligen Softwareversion installiert sind.</span><span class="sxs-lookup"><span data-stu-id="658c7-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="658c7-111">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="658c7-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="658c7-112">The `DeviceTvmSoftwareInventory` and tables have replaced the `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` table.</span><span class="sxs-lookup"><span data-stu-id="658c7-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="658c7-113">Zusammen enthalten die ersten beiden Tabellen weitere Spalten, die Sie verwenden können, um Ihre Aktivitäten zur Verwaltung von Vulnerablität zu informieren oder nach anfälligen Geräten zu fahnen.</span><span class="sxs-lookup"><span data-stu-id="658c7-113">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="658c7-114">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="658c7-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="658c7-115">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="658c7-115">Column name</span></span> | <span data-ttu-id="658c7-116">Datentyp</span><span class="sxs-lookup"><span data-stu-id="658c7-116">Data type</span></span> | <span data-ttu-id="658c7-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="658c7-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="658c7-118">string</span><span class="sxs-lookup"><span data-stu-id="658c7-118">string</span></span> | <span data-ttu-id="658c7-119">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="658c7-119">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="658c7-120">string</span><span class="sxs-lookup"><span data-stu-id="658c7-120">string</span></span> | <span data-ttu-id="658c7-121">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="658c7-121">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="658c7-122">string</span><span class="sxs-lookup"><span data-stu-id="658c7-122">string</span></span> | <span data-ttu-id="658c7-123">Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="658c7-123">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="658c7-124">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="658c7-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="658c7-125">string</span><span class="sxs-lookup"><span data-stu-id="658c7-125">string</span></span> | <span data-ttu-id="658c7-126">Die Version des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="658c7-126">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="658c7-127">string</span><span class="sxs-lookup"><span data-stu-id="658c7-127">string</span></span> | <span data-ttu-id="658c7-128">Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="658c7-128">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="658c7-129">string</span><span class="sxs-lookup"><span data-stu-id="658c7-129">string</span></span> | <span data-ttu-id="658c7-130">Name des Softwareanbieters</span><span class="sxs-lookup"><span data-stu-id="658c7-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="658c7-131">string</span><span class="sxs-lookup"><span data-stu-id="658c7-131">string</span></span> | <span data-ttu-id="658c7-132">Name des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="658c7-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="658c7-133">string</span><span class="sxs-lookup"><span data-stu-id="658c7-133">string</span></span> | <span data-ttu-id="658c7-134">Versionsnummer des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="658c7-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="658c7-135">string</span><span class="sxs-lookup"><span data-stu-id="658c7-135">string</span></span> | <span data-ttu-id="658c7-136">Gibt die Lebenszyklusphase des Softwareprodukts relativ zum angegebenen End-of-Support (EOS) oder End-of-Life (EOL)-Datum an.</span><span class="sxs-lookup"><span data-stu-id="658c7-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="658c7-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="658c7-137">string</span></span> | <span data-ttu-id="658c7-138">End-of-Support (EOS) oder End-of-Life (EOL) des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="658c7-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="658c7-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="658c7-139">Related topics</span></span>

- [<span data-ttu-id="658c7-140">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="658c7-140">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="658c7-141">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="658c7-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="658c7-142">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="658c7-142">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="658c7-143">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="658c7-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="658c7-144">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="658c7-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="658c7-145">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="658c7-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="658c7-146">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="658c7-146">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
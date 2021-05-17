---
title: DeviceTvmSoftwareInventory-Tabelle im schema der erweiterten Suche
description: Informationen zum Inventar der Software auf Ihren Geräten finden Sie in der DeviceTvmSoftwareInventory-Tabelle des schemas für die erweiterte Suche.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & Sicherheitsrisikomanagement, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 5f82684ebb10b72ff83a6789c010f5ec9fa099e7
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024229"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="1ed42-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="1ed42-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1ed42-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1ed42-105">**Applies to:**</span></span>
- <span data-ttu-id="1ed42-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ed42-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="1ed42-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1ed42-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="1ed42-108">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="1ed42-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1ed42-109">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="1ed42-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="1ed42-110">Die Tabelle im Schema für die erweiterte Suche enthält das Inventar & Threat & Vulnerability Management der software, die derzeit auf Geräten in Ihrem Netzwerk installiert ist, einschließlich Der Ende `DeviceTvmSoftwareInventory` der Supportinformationen. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="1ed42-110">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="1ed42-111">Sie können z. B. nach Ereignissen suchen, die Geräte enthalten, die mit einer derzeit anfälligen Softwareversion installiert sind.</span><span class="sxs-lookup"><span data-stu-id="1ed42-111">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="1ed42-112">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1ed42-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="1ed42-113">The `DeviceTvmSoftwareInventory` and tables have replaced the `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` table.</span><span class="sxs-lookup"><span data-stu-id="1ed42-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="1ed42-114">Zusammen enthalten die ersten beiden Tabellen weitere Spalten, die Sie verwenden können, um Ihre Aktivitäten zur Verwaltung von Vulnerablität zu informieren oder nach anfälligen Geräten zu fahnen.</span><span class="sxs-lookup"><span data-stu-id="1ed42-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="1ed42-115">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="1ed42-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="1ed42-116">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1ed42-116">Column name</span></span> | <span data-ttu-id="1ed42-117">Datentyp</span><span class="sxs-lookup"><span data-stu-id="1ed42-117">Data type</span></span> | <span data-ttu-id="1ed42-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ed42-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="1ed42-119">string</span><span class="sxs-lookup"><span data-stu-id="1ed42-119">string</span></span> | <span data-ttu-id="1ed42-120">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="1ed42-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="1ed42-121">string</span><span class="sxs-lookup"><span data-stu-id="1ed42-121">string</span></span> | <span data-ttu-id="1ed42-122">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="1ed42-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="1ed42-123">string</span><span class="sxs-lookup"><span data-stu-id="1ed42-123">string</span></span> | <span data-ttu-id="1ed42-124">Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1ed42-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="1ed42-125">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="1ed42-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="1ed42-126">string</span><span class="sxs-lookup"><span data-stu-id="1ed42-126">string</span></span> | <span data-ttu-id="1ed42-127">Die Version des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1ed42-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="1ed42-128">string</span><span class="sxs-lookup"><span data-stu-id="1ed42-128">string</span></span> | <span data-ttu-id="1ed42-129">Die Architektur des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1ed42-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="1ed42-130">string</span><span class="sxs-lookup"><span data-stu-id="1ed42-130">string</span></span> | <span data-ttu-id="1ed42-131">Name des Softwareanbieters</span><span class="sxs-lookup"><span data-stu-id="1ed42-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="1ed42-132">string</span><span class="sxs-lookup"><span data-stu-id="1ed42-132">string</span></span> | <span data-ttu-id="1ed42-133">Name des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="1ed42-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="1ed42-134">string</span><span class="sxs-lookup"><span data-stu-id="1ed42-134">string</span></span> | <span data-ttu-id="1ed42-135">Versionsnummer des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="1ed42-135">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="1ed42-136">string</span><span class="sxs-lookup"><span data-stu-id="1ed42-136">string</span></span> | <span data-ttu-id="1ed42-137">Gibt die Lebenszyklusphase des Softwareprodukts relativ zum angegebenen End-of-Support (EOS) oder End-of-Life (EOL)-Datum an.</span><span class="sxs-lookup"><span data-stu-id="1ed42-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="1ed42-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1ed42-138">string</span></span> | <span data-ttu-id="1ed42-139">End-of-Support (EOS) oder End-of-Life (EOL) des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="1ed42-139">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="1ed42-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1ed42-140">Related topics</span></span>

- [<span data-ttu-id="1ed42-141">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="1ed42-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1ed42-142">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="1ed42-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1ed42-143">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="1ed42-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1ed42-144">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="1ed42-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="1ed42-145">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="1ed42-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1ed42-146">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="1ed42-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="1ed42-147">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="1ed42-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
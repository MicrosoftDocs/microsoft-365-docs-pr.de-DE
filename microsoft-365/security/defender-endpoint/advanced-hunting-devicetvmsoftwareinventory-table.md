---
title: DeviceTvmSoftwareInventory-Tabelle im schema der erweiterten Suche
description: Informationen zum Inventar der Software auf Ihren Geräten finden Sie in der DeviceTvmSoftwareInventory-Tabelle des schemas für die erweiterte Suche.
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
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067504"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="6444b-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="6444b-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6444b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6444b-105">**Applies to:**</span></span>
- [<span data-ttu-id="6444b-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6444b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="6444b-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="6444b-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6444b-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="6444b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6444b-109">Die Tabelle im Schema für die erweiterte Suche enthält das Inventar & Threat & Vulnerability Management der software, die derzeit auf Geräten in Ihrem Netzwerk installiert ist, einschließlich Der Ende `DeviceTvmSoftwareInventory` der Supportinformationen. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="6444b-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="6444b-110">Sie können z. B. nach Ereignissen suchen, die Geräte enthalten, die mit einer derzeit anfälligen Softwareversion installiert sind.</span><span class="sxs-lookup"><span data-stu-id="6444b-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="6444b-111">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="6444b-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="6444b-112">The `DeviceTvmSoftwareInventory` and tables have replaced the `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` table.</span><span class="sxs-lookup"><span data-stu-id="6444b-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="6444b-113">Zusammen enthalten die ersten beiden Tabellen weitere Spalten, die Sie verwenden können, um Ihre Aktivitäten zur Verwaltung von Sicherheitslücken zu informieren.</span><span class="sxs-lookup"><span data-stu-id="6444b-113">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="6444b-114">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="6444b-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="6444b-115">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="6444b-115">Column name</span></span> | <span data-ttu-id="6444b-116">Datentyp</span><span class="sxs-lookup"><span data-stu-id="6444b-116">Data type</span></span> | <span data-ttu-id="6444b-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6444b-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="6444b-118">string</span><span class="sxs-lookup"><span data-stu-id="6444b-118">string</span></span> | <span data-ttu-id="6444b-119">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="6444b-119">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6444b-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6444b-120">string</span></span> | <span data-ttu-id="6444b-121">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="6444b-121">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="6444b-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6444b-122">string</span></span> | <span data-ttu-id="6444b-123">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6444b-123">Platform of the operating system running on the device.</span></span> <span data-ttu-id="6444b-124">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="6444b-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="6444b-125">string</span><span class="sxs-lookup"><span data-stu-id="6444b-125">string</span></span> | <span data-ttu-id="6444b-126">Version des Betriebssystems, das auf dem Gerät ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="6444b-126">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="6444b-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6444b-127">string</span></span> | <span data-ttu-id="6444b-128">Architektur des Betriebssystems, das auf dem Gerät ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="6444b-128">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="6444b-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6444b-129">string</span></span> | <span data-ttu-id="6444b-130">Name des Softwareanbieters</span><span class="sxs-lookup"><span data-stu-id="6444b-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="6444b-131">string</span><span class="sxs-lookup"><span data-stu-id="6444b-131">string</span></span> | <span data-ttu-id="6444b-132">Name des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="6444b-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="6444b-133">string</span><span class="sxs-lookup"><span data-stu-id="6444b-133">string</span></span> | <span data-ttu-id="6444b-134">Versionsnummer des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="6444b-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="6444b-135">string</span><span class="sxs-lookup"><span data-stu-id="6444b-135">string</span></span> | <span data-ttu-id="6444b-136">Gibt die Lebenszyklusphase des Softwareprodukts relativ zum angegebenen End-of-Support (EOS) oder End-of-Life (EOL)-Datum an.</span><span class="sxs-lookup"><span data-stu-id="6444b-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="6444b-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6444b-137">string</span></span> | <span data-ttu-id="6444b-138">End-of-Support (EOS) oder End-of-Life (EOL) des Softwareprodukts</span><span class="sxs-lookup"><span data-stu-id="6444b-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="6444b-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6444b-139">Related topics</span></span>

- [<span data-ttu-id="6444b-140">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="6444b-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6444b-141">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="6444b-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6444b-142">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="6444b-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="6444b-143">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="6444b-143">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)


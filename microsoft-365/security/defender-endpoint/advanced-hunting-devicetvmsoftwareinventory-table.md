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
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408623"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="f0355-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="f0355-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f0355-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f0355-105">**Applies to:**</span></span>
- [<span data-ttu-id="f0355-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f0355-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="f0355-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f0355-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f0355-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f0355-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f0355-109">Die Tabelle im Schema der erweiterten Suche enthält das Bedrohungs- und Sicherheitsrisikoverwaltungsinventar der Software, die derzeit auf Geräten in Ihrem Netzwerk installiert ist, einschließlich der `DeviceTvmSoftwareInventory` Supportinformationen zum [](next-gen-threat-and-vuln-mgt.md) Ende.</span><span class="sxs-lookup"><span data-stu-id="f0355-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="f0355-110">Sie können z. B. nach Ereignissen suchen, die Geräte enthalten, die mit einer derzeit anfälligen Softwareversion installiert sind.</span><span class="sxs-lookup"><span data-stu-id="f0355-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="f0355-111">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f0355-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="f0355-112">DeviceTVMSoftwareInventory enthält alle Software, die das Bedrohungs- und Sicherheitsrisikomanagement mit einer Common Platform Enumeration (CPE) übereinstimmen konnte – unabhängig davon, ob es anfällig ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="f0355-112">DeviceTVMSoftwareInventory contains all the software which threat and vulnerability management was able to match to a Common Platform Enumeration (CPE) – whether it is vulnerable or not.</span></span>

>[!NOTE]
><span data-ttu-id="f0355-113">The `DeviceTvmSoftwareInventory` and tables have replaced the `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` table.</span><span class="sxs-lookup"><span data-stu-id="f0355-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="f0355-114">Zusammen enthalten die ersten beiden Tabellen weitere Spalten, die Sie verwenden können, um Ihre Aktivitäten zur Verwaltung von Sicherheitslücken zu informieren.</span><span class="sxs-lookup"><span data-stu-id="f0355-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="f0355-115">Informationen zu anderen Tabellen im Schema „Erweiterte Suche“ finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="f0355-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="f0355-116">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f0355-116">Column name</span></span> | <span data-ttu-id="f0355-117">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f0355-117">Data type</span></span> | <span data-ttu-id="f0355-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0355-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="f0355-119">string</span><span class="sxs-lookup"><span data-stu-id="f0355-119">string</span></span> | <span data-ttu-id="f0355-120">Eindeutige ID für das Gerät im Dienst.</span><span class="sxs-lookup"><span data-stu-id="f0355-120">Unique identifier for the device in the service.</span></span> |
| `DeviceName` | <span data-ttu-id="f0355-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f0355-121">string</span></span> | <span data-ttu-id="f0355-122">Vollqualifizierter Domänenname (FQDN) des Geräts.</span><span class="sxs-lookup"><span data-stu-id="f0355-122">Fully qualified domain name (FQDN) of the device.</span></span> |
| `OSPlatform` | <span data-ttu-id="f0355-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f0355-123">string</span></span> | <span data-ttu-id="f0355-124">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f0355-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f0355-125">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="f0355-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="f0355-126">string</span><span class="sxs-lookup"><span data-stu-id="f0355-126">string</span></span> | <span data-ttu-id="f0355-127">Version des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f0355-127">Version of the operating system running on the device.</span></span> |
| `OSArchitecture` | <span data-ttu-id="f0355-128">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f0355-128">string</span></span> | <span data-ttu-id="f0355-129">Architektur des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f0355-129">Architecture of the operating system running on the device.</span></span> |
| `SoftwareVendor` | <span data-ttu-id="f0355-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f0355-130">string</span></span> | <span data-ttu-id="f0355-131">Name des Softwareanbieters.</span><span class="sxs-lookup"><span data-stu-id="f0355-131">Name of the software vendor.</span></span> |
| `SoftwareName` | <span data-ttu-id="f0355-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f0355-132">string</span></span> | <span data-ttu-id="f0355-133">Name des Softwareprodukts.</span><span class="sxs-lookup"><span data-stu-id="f0355-133">Name of the software product.</span></span> |
| `SoftwareVersion` | <span data-ttu-id="f0355-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f0355-134">string</span></span> | <span data-ttu-id="f0355-135">Versionsnummer des Softwareprodukts.</span><span class="sxs-lookup"><span data-stu-id="f0355-135">Version number of the software product.</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="f0355-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f0355-136">string</span></span> | <span data-ttu-id="f0355-137">Gibt die Lebenszyklusphase des Softwareprodukts relativ zum angegebenen End-of-Support (EOS) oder End-of-Life (EOL)-Datum an.</span><span class="sxs-lookup"><span data-stu-id="f0355-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date.</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="f0355-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f0355-138">string</span></span> | <span data-ttu-id="f0355-139">End-of-Support (EOS) oder End-of-Life (EOL)-Datum des Softwareprodukts.</span><span class="sxs-lookup"><span data-stu-id="f0355-139">End-of-support (EOS) or end-of-life (EOL) date of the software product.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f0355-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f0355-140">Related topics</span></span>

- [<span data-ttu-id="f0355-141">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="f0355-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f0355-142">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="f0355-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f0355-143">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="f0355-143">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="f0355-144">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="f0355-144">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)

---
title: Tabelle "DeviceTvmSecureConfigurationAssessment" im Schema "Erweiterte Suche"
description: Weitere Informationen zu & Sicherheitsbewertungsereignissen für das Sicherheitsmanagement in der DeviceTvmSecureConfigurationAssessment-Tabelle des Schemas für die erweiterte Suche. Diese Ereignisse enthalten Geräteinformationen sowie Sicherheitskonfigurationsdetails, Auswirkungen und Complianceinformationen.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067008"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="d78a6-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="d78a6-105">DeviceTvmSecureConfigurationAssessment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d78a6-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d78a6-106">**Applies to:**</span></span>
- [<span data-ttu-id="d78a6-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d78a6-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="d78a6-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="d78a6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d78a6-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d78a6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="d78a6-110">Jede Zeile in der Tabelle `DeviceTvmSecureConfigurationAssessment` enthält ein Bewertungsereignis für eine bestimmte Sicherheitskonfiguration der [Bedrohungs- und Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md).</span><span class="sxs-lookup"><span data-stu-id="d78a6-110">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="d78a6-111">Verwenden Sie diese Referenz, um die neuesten Beurteilungsergebnisse zu überprüfen und zu ermitteln, ob die Geräte kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="d78a6-111">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="d78a6-112">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="d78a6-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="d78a6-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d78a6-113">Column name</span></span> | <span data-ttu-id="d78a6-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="d78a6-114">Data type</span></span> | <span data-ttu-id="d78a6-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d78a6-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="d78a6-116">string</span><span class="sxs-lookup"><span data-stu-id="d78a6-116">string</span></span> | <span data-ttu-id="d78a6-117">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="d78a6-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d78a6-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d78a6-118">string</span></span> | <span data-ttu-id="d78a6-119">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="d78a6-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="d78a6-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d78a6-120">string</span></span> | <span data-ttu-id="d78a6-121">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d78a6-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="d78a6-122">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d78a6-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="d78a6-123">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d78a6-123">datetime</span></span> |<span data-ttu-id="d78a6-124">Datum und Uhrzeit, wann der Datensatz generiert wurde</span><span class="sxs-lookup"><span data-stu-id="d78a6-124">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="d78a6-125">string</span><span class="sxs-lookup"><span data-stu-id="d78a6-125">string</span></span> | <span data-ttu-id="d78a6-126">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d78a6-126">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="d78a6-127">string</span><span class="sxs-lookup"><span data-stu-id="d78a6-127">string</span></span> | <span data-ttu-id="d78a6-128">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="d78a6-128">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="d78a6-129">string</span><span class="sxs-lookup"><span data-stu-id="d78a6-129">string</span></span> |<span data-ttu-id="d78a6-130">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="d78a6-130">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="d78a6-131">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="d78a6-131">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="d78a6-132">string</span><span class="sxs-lookup"><span data-stu-id="d78a6-132">string</span></span> | <span data-ttu-id="d78a6-133">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="d78a6-133">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="d78a6-134">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="d78a6-134">boolean</span></span> | <span data-ttu-id="d78a6-135">Gibt an, ob die Konfiguration oder Richtlinie ordnungsgemäß konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="d78a6-135">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="d78a6-136">boolean</span><span class="sxs-lookup"><span data-stu-id="d78a6-136">boolean</span></span> | <span data-ttu-id="d78a6-137">Gibt an, ob die Konfiguration oder Richtlinie auf das Gerät angewendet wird</span><span class="sxs-lookup"><span data-stu-id="d78a6-137">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="d78a6-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d78a6-138">string</span></span> | <span data-ttu-id="d78a6-139">Zusätzliche kontextbezogene Informationen zur Konfiguration oder Richtlinie</span><span class="sxs-lookup"><span data-stu-id="d78a6-139">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="d78a6-140">boolean</span><span class="sxs-lookup"><span data-stu-id="d78a6-140">boolean</span></span> | <span data-ttu-id="d78a6-141">Gibt an, ob sich Benutzer auswirken, wenn die Konfiguration oder Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d78a6-141">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d78a6-142">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d78a6-142">Related topics</span></span>

- [<span data-ttu-id="d78a6-143">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="d78a6-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d78a6-144">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="d78a6-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d78a6-145">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="d78a6-145">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="d78a6-146">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="d78a6-146">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
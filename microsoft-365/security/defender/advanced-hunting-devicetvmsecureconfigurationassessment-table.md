---
title: Tabelle "DeviceTvmSecureConfigurationAssessment" im Schema "Erweiterte Suche"
description: Informationen zu Sicherheitsbewertungsereignissen finden Sie in der DeviceTvmSecureConfigurationAssessment-Tabelle des erweiterten Nachschlageschemas. Diese & Sicherheitsrisikomanagement bieten Geräteinformationen sowie Sicherheitskonfigurationsdetails, Auswirkungen und Complianceinformationen.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & Sicherheitsrisikomanagement, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 2e3e649911cb2ce63c2a49be0ebc93e35e8055d6
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024217"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="2f097-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="2f097-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2f097-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2f097-106">**Applies to:**</span></span>
- <span data-ttu-id="2f097-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f097-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="2f097-108">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2f097-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="2f097-109">Jede Zeile in der Tabelle `DeviceTvmSecureConfigurationAssessment` enthält ein Bewertungsereignis für eine bestimmte Sicherheitskonfiguration der [Bedrohungs- und Sicherheitsrisikoverwaltung](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="2f097-109">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="2f097-110">Verwenden Sie diese Referenz, um die neuesten Beurteilungsergebnisse zu überprüfen und zu ermitteln, ob die Geräte kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="2f097-110">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="2f097-111">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2f097-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2f097-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2f097-112">Column name</span></span> | <span data-ttu-id="2f097-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2f097-113">Data type</span></span> | <span data-ttu-id="2f097-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f097-114">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="2f097-115">string</span><span class="sxs-lookup"><span data-stu-id="2f097-115">string</span></span> | <span data-ttu-id="2f097-116">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="2f097-116">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2f097-117">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f097-117">string</span></span> | <span data-ttu-id="2f097-118">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="2f097-118">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="2f097-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f097-119">string</span></span> | <span data-ttu-id="2f097-120">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2f097-120">Platform of the operating system running on the device.</span></span> <span data-ttu-id="2f097-121">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2f097-121">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="2f097-122">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="2f097-122">datetime</span></span> | <span data-ttu-id="2f097-123">Datum und Uhrzeit, wann der Datensatz generiert wurde</span><span class="sxs-lookup"><span data-stu-id="2f097-123">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="2f097-124">string</span><span class="sxs-lookup"><span data-stu-id="2f097-124">string</span></span> | <span data-ttu-id="2f097-125">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="2f097-125">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="2f097-126">string</span><span class="sxs-lookup"><span data-stu-id="2f097-126">string</span></span> | <span data-ttu-id="2f097-127">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="2f097-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="2f097-128">string</span><span class="sxs-lookup"><span data-stu-id="2f097-128">string</span></span> | <span data-ttu-id="2f097-129">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="2f097-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="2f097-130">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="2f097-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="2f097-131">string</span><span class="sxs-lookup"><span data-stu-id="2f097-131">string</span></span> | <span data-ttu-id="2f097-132">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="2f097-132">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="2f097-133">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="2f097-133">boolean</span></span> | <span data-ttu-id="2f097-134">Gibt an, ob die Konfiguration oder Richtlinie ordnungsgemäß konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="2f097-134">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="2f097-135">boolean</span><span class="sxs-lookup"><span data-stu-id="2f097-135">boolean</span></span> | <span data-ttu-id="2f097-136">Gibt an, ob die Konfiguration oder Richtlinie auf das Gerät angewendet wird</span><span class="sxs-lookup"><span data-stu-id="2f097-136">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="2f097-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2f097-137">string</span></span> | <span data-ttu-id="2f097-138">Zusätzliche kontextbezogene Informationen zur Konfiguration oder Richtlinie</span><span class="sxs-lookup"><span data-stu-id="2f097-138">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpact` | <span data-ttu-id="2f097-139">boolean</span><span class="sxs-lookup"><span data-stu-id="2f097-139">boolean</span></span> | <span data-ttu-id="2f097-140">Gibt an, ob sich Benutzer auswirken, wenn die Konfiguration oder Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2f097-140">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2f097-141">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2f097-141">Related topics</span></span>

- [<span data-ttu-id="2f097-142">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="2f097-142">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2f097-143">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="2f097-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2f097-144">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="2f097-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2f097-145">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="2f097-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2f097-146">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="2f097-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2f097-147">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="2f097-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="2f097-148">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="2f097-148">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
---
title: Tabelle "DeviceTvmSecureConfigurationAssessment" im Schema "Erweiterte Suche"
description: Informationen zu Sicherheitsbewertungsereignissen finden Sie in der DeviceTvmSecureConfigurationAssessment-Tabelle des erweiterten Nachschlageschemas. Diese Ereignisse & Sicherheitsrisikoverwaltung bieten Geräteinformationen sowie Sicherheitskonfigurationsdetails, Auswirkungen und Complianceinformationen.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3d991bc5e78fc7b33e20df1f86471a0969b7345f
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382595"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="548a0-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="548a0-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="548a0-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="548a0-106">**Applies to:**</span></span>
- <span data-ttu-id="548a0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="548a0-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="548a0-108">Jede Zeile in der Tabelle `DeviceTvmSecureConfigurationAssessment` enthält ein Bewertungsereignis für eine bestimmte Sicherheitskonfiguration der [Bedrohungs- und Sicherheitsrisikoverwaltung](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="548a0-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="548a0-109">Verwenden Sie diese Referenz, um die neuesten Beurteilungsergebnisse zu überprüfen und zu ermitteln, ob die Geräte kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="548a0-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="548a0-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="548a0-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="548a0-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="548a0-111">Column name</span></span> | <span data-ttu-id="548a0-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="548a0-112">Data type</span></span> | <span data-ttu-id="548a0-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="548a0-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="548a0-114">string</span><span class="sxs-lookup"><span data-stu-id="548a0-114">string</span></span> | <span data-ttu-id="548a0-115">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="548a0-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="548a0-116">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="548a0-116">string</span></span> | <span data-ttu-id="548a0-117">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="548a0-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="548a0-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="548a0-118">string</span></span> | <span data-ttu-id="548a0-119">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="548a0-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="548a0-120">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="548a0-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="548a0-121">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="548a0-121">datetime</span></span> | <span data-ttu-id="548a0-122">Datum und Uhrzeit, wann der Datensatz generiert wurde</span><span class="sxs-lookup"><span data-stu-id="548a0-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="548a0-123">string</span><span class="sxs-lookup"><span data-stu-id="548a0-123">string</span></span> | <span data-ttu-id="548a0-124">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="548a0-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="548a0-125">string</span><span class="sxs-lookup"><span data-stu-id="548a0-125">string</span></span> | <span data-ttu-id="548a0-126">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="548a0-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="548a0-127">string</span><span class="sxs-lookup"><span data-stu-id="548a0-127">string</span></span> | <span data-ttu-id="548a0-128">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="548a0-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="548a0-129">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="548a0-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="548a0-130">string</span><span class="sxs-lookup"><span data-stu-id="548a0-130">string</span></span> | <span data-ttu-id="548a0-131">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="548a0-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="548a0-132">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="548a0-132">boolean</span></span> | <span data-ttu-id="548a0-133">Gibt an, ob die Konfiguration oder Richtlinie ordnungsgemäß konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="548a0-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="548a0-134">boolean</span><span class="sxs-lookup"><span data-stu-id="548a0-134">boolean</span></span> | <span data-ttu-id="548a0-135">Gibt an, ob die Konfiguration oder Richtlinie auf das Gerät angewendet wird</span><span class="sxs-lookup"><span data-stu-id="548a0-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="548a0-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="548a0-136">string</span></span> | <span data-ttu-id="548a0-137">Zusätzliche kontextbezogene Informationen zur Konfiguration oder Richtlinie</span><span class="sxs-lookup"><span data-stu-id="548a0-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpact` | <span data-ttu-id="548a0-138">boolean</span><span class="sxs-lookup"><span data-stu-id="548a0-138">boolean</span></span> | <span data-ttu-id="548a0-139">Gibt an, ob sich Benutzer auswirken, wenn die Konfiguration oder Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="548a0-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="548a0-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="548a0-140">Related topics</span></span>

- [<span data-ttu-id="548a0-141">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="548a0-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="548a0-142">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="548a0-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="548a0-143">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="548a0-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="548a0-144">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="548a0-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="548a0-145">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="548a0-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="548a0-146">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="548a0-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="548a0-147">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="548a0-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
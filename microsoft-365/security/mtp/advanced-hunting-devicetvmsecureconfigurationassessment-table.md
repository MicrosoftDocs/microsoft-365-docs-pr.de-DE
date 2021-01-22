---
title: Tabelle "DeviceTvmSecureConfigurationAssessment" im Schema "Erweiterte Suche"
description: Informationen zu Sicherheitsbewertungsereignissen in der Tabelle "DeviceTvmSecureConfigurationAssessment" des Schemas für die erweiterte Suche. Diese Bedrohungs& Sicherheitsrisikoverwaltungsereignisse liefern Geräteinformationen sowie Sicherheitskonfigurationsdetails, Auswirkungen und Complianceinformationen.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, Verwaltung von Sicherheitsrisiken & Bedrohungen, TVM, Geräteverwaltung, Sicherheitskonfiguration, DeviceTvmSecureConfigurationAssessment
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6924bbc7a88a4f32d97534c72a180a1f1c4f7db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931098"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="01e4f-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="01e4f-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="01e4f-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="01e4f-106">**Applies to:**</span></span>
- <span data-ttu-id="01e4f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01e4f-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="01e4f-108">Jede Zeile in der Tabelle `DeviceTvmSecureConfigurationAssessment` enthält ein Bewertungsereignis für eine bestimmte Sicherheitskonfiguration der [Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="01e4f-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="01e4f-109">Verwenden Sie diese Referenz, um die neuesten Beurteilungsergebnisse zu überprüfen und zu ermitteln, ob die Geräte kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="01e4f-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="01e4f-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="01e4f-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="01e4f-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="01e4f-111">Column name</span></span> | <span data-ttu-id="01e4f-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="01e4f-112">Data type</span></span> | <span data-ttu-id="01e4f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01e4f-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="01e4f-114">string</span><span class="sxs-lookup"><span data-stu-id="01e4f-114">string</span></span> | <span data-ttu-id="01e4f-115">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="01e4f-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="01e4f-116">string</span><span class="sxs-lookup"><span data-stu-id="01e4f-116">string</span></span> | <span data-ttu-id="01e4f-117">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="01e4f-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="01e4f-118">string</span><span class="sxs-lookup"><span data-stu-id="01e4f-118">string</span></span> | <span data-ttu-id="01e4f-119">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="01e4f-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="01e4f-120">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="01e4f-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="01e4f-121">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="01e4f-121">datetime</span></span> | <span data-ttu-id="01e4f-122">Datum und Uhrzeit, wann der Datensatz generiert wurde</span><span class="sxs-lookup"><span data-stu-id="01e4f-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="01e4f-123">string</span><span class="sxs-lookup"><span data-stu-id="01e4f-123">string</span></span> | <span data-ttu-id="01e4f-124">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="01e4f-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="01e4f-125">string</span><span class="sxs-lookup"><span data-stu-id="01e4f-125">string</span></span> | <span data-ttu-id="01e4f-126">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="01e4f-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="01e4f-127">string</span><span class="sxs-lookup"><span data-stu-id="01e4f-127">string</span></span> | <span data-ttu-id="01e4f-128">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="01e4f-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="01e4f-129">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="01e4f-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="01e4f-130">string</span><span class="sxs-lookup"><span data-stu-id="01e4f-130">string</span></span> | <span data-ttu-id="01e4f-131">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="01e4f-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="01e4f-132">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="01e4f-132">boolean</span></span> | <span data-ttu-id="01e4f-133">Gibt an, ob die Konfiguration oder Richtlinie ordnungsgemäß konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="01e4f-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="01e4f-134">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="01e4f-134">boolean</span></span> | <span data-ttu-id="01e4f-135">Gibt an, ob die Konfiguration oder Richtlinie auf das Gerät angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="01e4f-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="01e4f-136">string</span><span class="sxs-lookup"><span data-stu-id="01e4f-136">string</span></span> | <span data-ttu-id="01e4f-137">Zusätzliche kontextbezogene Informationen zur Konfiguration oder Richtlinie</span><span class="sxs-lookup"><span data-stu-id="01e4f-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="01e4f-138">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="01e4f-138">boolean</span></span> | <span data-ttu-id="01e4f-139">Gibt an, ob auswirkungen auf den Benutzer bei Anwendung der Konfiguration oder Richtlinie zu haben sind.</span><span class="sxs-lookup"><span data-stu-id="01e4f-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="01e4f-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="01e4f-140">Related topics</span></span>

- [<span data-ttu-id="01e4f-141">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="01e4f-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="01e4f-142">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="01e4f-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="01e4f-143">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="01e4f-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="01e4f-144">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="01e4f-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="01e4f-145">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="01e4f-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="01e4f-146">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="01e4f-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="01e4f-147">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="01e4f-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

---
title: Tabelle "DeviceTvmSecureConfigurationAssessment" im Schema "Erweiterte Suche"
description: Erfahren Sie mehr über Sicherheits Bewertungs Ereignisse in der DeviceTvmSecureConfigurationAssessment-Tabelle des Advanced Hunting-Schemas. Diese Bedrohungs & Ereignisse zur Risikoverwaltung bieten Geräteinformationen sowie Details zur Sicherheitskonfiguration, Auswirkungen und Kompatibilitätsinformationen.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, Bedrohungs & Vulnerability Management, TVM, Device Management, Security Configuration, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: bfe63397d194567a7d71de703363083d2fd4fe75
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847608"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="61e0e-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="61e0e-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="61e0e-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="61e0e-106">**Applies to:**</span></span>
- <span data-ttu-id="61e0e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61e0e-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="61e0e-108">Jede Zeile in der Tabelle `DeviceTvmSecureConfigurationAssessment` enthält ein Bewertungsereignis für eine bestimmte Sicherheitskonfiguration der [Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="61e0e-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="61e0e-109">Verwenden Sie diese Referenz, um die neuesten Beurteilungsergebnisse zu überprüfen und zu ermitteln, ob die Geräte kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="61e0e-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="61e0e-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="61e0e-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="61e0e-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="61e0e-111">Column name</span></span> | <span data-ttu-id="61e0e-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="61e0e-112">Data type</span></span> | <span data-ttu-id="61e0e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61e0e-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="61e0e-114">string</span><span class="sxs-lookup"><span data-stu-id="61e0e-114">string</span></span> | <span data-ttu-id="61e0e-115">Eindeutiger Bezeichner für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="61e0e-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="61e0e-116">string</span><span class="sxs-lookup"><span data-stu-id="61e0e-116">string</span></span> | <span data-ttu-id="61e0e-117">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="61e0e-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="61e0e-118">string</span><span class="sxs-lookup"><span data-stu-id="61e0e-118">string</span></span> | <span data-ttu-id="61e0e-119">Plattform des auf dem Gerät ausgeführten Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="61e0e-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="61e0e-120">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="61e0e-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="61e0e-121">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="61e0e-121">datetime</span></span> | <span data-ttu-id="61e0e-122">Datum und Uhrzeit, wann der Datensatz generiert wurde</span><span class="sxs-lookup"><span data-stu-id="61e0e-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="61e0e-123">string</span><span class="sxs-lookup"><span data-stu-id="61e0e-123">string</span></span> | <span data-ttu-id="61e0e-124">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="61e0e-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="61e0e-125">string</span><span class="sxs-lookup"><span data-stu-id="61e0e-125">string</span></span> | <span data-ttu-id="61e0e-126">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="61e0e-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="61e0e-127">string</span><span class="sxs-lookup"><span data-stu-id="61e0e-127">string</span></span> | <span data-ttu-id="61e0e-128">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="61e0e-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="61e0e-129">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="61e0e-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="61e0e-130">string</span><span class="sxs-lookup"><span data-stu-id="61e0e-130">string</span></span> | <span data-ttu-id="61e0e-131">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="61e0e-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="61e0e-132">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="61e0e-132">boolean</span></span> | <span data-ttu-id="61e0e-133">Gibt an, ob die Konfiguration oder Richtlinie ordnungsgemäß konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="61e0e-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="61e0e-134">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="61e0e-134">boolean</span></span> | <span data-ttu-id="61e0e-135">Gibt an, ob die Konfiguration oder Richtlinie auf das Gerät angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="61e0e-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="61e0e-136">string</span><span class="sxs-lookup"><span data-stu-id="61e0e-136">string</span></span> | <span data-ttu-id="61e0e-137">Zusätzliche Kontextinformationen zur Konfiguration oder Richtlinie</span><span class="sxs-lookup"><span data-stu-id="61e0e-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="61e0e-138">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="61e0e-138">boolean</span></span> | <span data-ttu-id="61e0e-139">Gibt an, ob Benutzer Auswirkungen haben, wenn die Konfiguration oder Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="61e0e-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="61e0e-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="61e0e-140">Related topics</span></span>

- [<span data-ttu-id="61e0e-141">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="61e0e-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="61e0e-142">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="61e0e-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="61e0e-143">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="61e0e-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="61e0e-144">Suchen auf Geräten, in E-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="61e0e-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="61e0e-145">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="61e0e-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="61e0e-146">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="61e0e-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="61e0e-147">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="61e0e-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

---
title: Tabelle "DeviceTvmSecureConfigurationAssessment" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die Sicherheitsbewertungsereignisse der Bedrohungs- und Sicherheitsrisikoverwaltung in der Tabelle "DeviceTvmSecureConfigurationAssessment" des Schemas "Erweiterte Suche". Diese Ereignisse stellen Computerinformationen sowie Details zur Sicherheitskonfiguration, Auswirkungen und Konformitätsinformationen bereit.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: ade218a440f8e7db223460e95363eae2cb659622
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235174"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="1ca9f-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="1ca9f-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="1ca9f-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1ca9f-106">**Applies to:**</span></span>
- <span data-ttu-id="1ca9f-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1ca9f-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="1ca9f-108">Jede Zeile in der Tabelle `DeviceTvmSecureConfigurationAssessment` enthält ein Bewertungsereignis für eine bestimmte Sicherheitskonfiguration der [Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="1ca9f-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="1ca9f-109">Verwenden Sie diese Referenz, um die neuesten Beurteilungsergebnisse zu überprüfen und zu ermitteln, ob die Geräte kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="1ca9f-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="1ca9f-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="1ca9f-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="1ca9f-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1ca9f-111">Column name</span></span> | <span data-ttu-id="1ca9f-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="1ca9f-112">Data type</span></span> | <span data-ttu-id="1ca9f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ca9f-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="1ca9f-114">string</span><span class="sxs-lookup"><span data-stu-id="1ca9f-114">string</span></span> | <span data-ttu-id="1ca9f-115">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="1ca9f-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="1ca9f-116">string</span><span class="sxs-lookup"><span data-stu-id="1ca9f-116">string</span></span> | <span data-ttu-id="1ca9f-117">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="1ca9f-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="1ca9f-118">string</span><span class="sxs-lookup"><span data-stu-id="1ca9f-118">string</span></span> | <span data-ttu-id="1ca9f-119">Die Plattform des Betriebssystem, das auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1ca9f-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="1ca9f-120">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="1ca9f-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="1ca9f-121">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="1ca9f-121">datetime</span></span> | <span data-ttu-id="1ca9f-122">Datum und Uhrzeit, wann der Datensatz generiert wurde</span><span class="sxs-lookup"><span data-stu-id="1ca9f-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="1ca9f-123">string</span><span class="sxs-lookup"><span data-stu-id="1ca9f-123">string</span></span> | <span data-ttu-id="1ca9f-124">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="1ca9f-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="1ca9f-125">string</span><span class="sxs-lookup"><span data-stu-id="1ca9f-125">string</span></span> | <span data-ttu-id="1ca9f-126">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="1ca9f-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="1ca9f-127">string</span><span class="sxs-lookup"><span data-stu-id="1ca9f-127">string</span></span> | <span data-ttu-id="1ca9f-128">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="1ca9f-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="1ca9f-129">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="1ca9f-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="1ca9f-130">string</span><span class="sxs-lookup"><span data-stu-id="1ca9f-130">string</span></span> | <span data-ttu-id="1ca9f-131">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="1ca9f-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="1ca9f-132">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="1ca9f-132">boolean</span></span> | <span data-ttu-id="1ca9f-133">Gibt an, ob die Konfiguration oder Richtlinie ordnungsgemäß konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="1ca9f-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1ca9f-134">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1ca9f-134">Related topics</span></span>

- [<span data-ttu-id="1ca9f-135">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="1ca9f-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1ca9f-136">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="1ca9f-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1ca9f-137">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="1ca9f-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1ca9f-138">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="1ca9f-138">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="1ca9f-139">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="1ca9f-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1ca9f-140">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="1ca9f-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="1ca9f-141">Übersicht über die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="1ca9f-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

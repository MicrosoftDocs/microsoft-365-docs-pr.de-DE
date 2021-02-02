---
title: Benennungsänderungen im Microsoft 365 Defender Advanced Hunting-Schema
description: Nachverfolgen und Überprüfen von Namensänderungen in Tabellen und Spalten im Schema für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberbedrohungen, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Daten, Benennungsänderungen, Umbenennen, Microsoft Threat Protection
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
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066869"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="42a7b-104">Schema der erweiterten Suche – Namensänderungen</span><span class="sxs-lookup"><span data-stu-id="42a7b-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="42a7b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="42a7b-105">**Applies to:**</span></span>
- <span data-ttu-id="42a7b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42a7b-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="42a7b-107">Das [Schema für die erweiterte Suche](advanced-hunting-schema-tables.md) wird regelmäßig aktualisiert, um neue Tabellen und Spalten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="42a7b-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="42a7b-108">In einigen Fällen werden vorhandene Spaltennamen umbenannt oder ersetzt, um die Benutzerfreundlichkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="42a7b-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="42a7b-109">In diesem Artikel finden Sie Informationen zu Namensänderungen, die sich auf Ihre Abfragen auswirken könnten.</span><span class="sxs-lookup"><span data-stu-id="42a7b-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="42a7b-110">Namensänderungen werden automatisch auf Abfragen angewendet, die im Security Center gespeichert werden, einschließlich Abfragen, die von benutzerdefinierten Erkennungsregeln verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="42a7b-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="42a7b-111">Sie müssen diese Abfragen nicht manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="42a7b-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="42a7b-112">Sie müssen jedoch die folgenden Abfragen aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="42a7b-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="42a7b-113">Abfragen, die mit der API ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="42a7b-113">Queries that are run using the API</span></span>
- <span data-ttu-id="42a7b-114">Abfragen, die an anderer Stelle außerhalb des Sicherheitscenters gespeichert werden</span><span class="sxs-lookup"><span data-stu-id="42a7b-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="42a7b-115">Dezember 2020</span><span class="sxs-lookup"><span data-stu-id="42a7b-115">December 2020</span></span>

| <span data-ttu-id="42a7b-116">Tabellenname</span><span class="sxs-lookup"><span data-stu-id="42a7b-116">Table name</span></span> | <span data-ttu-id="42a7b-117">Ursprünglicher Spaltenname</span><span class="sxs-lookup"><span data-stu-id="42a7b-117">Original column name</span></span> | <span data-ttu-id="42a7b-118">Neuer Spaltenname</span><span class="sxs-lookup"><span data-stu-id="42a7b-118">New column name</span></span> | <span data-ttu-id="42a7b-119">Änderungsgrund</span><span class="sxs-lookup"><span data-stu-id="42a7b-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="42a7b-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="42a7b-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="42a7b-121">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="42a7b-121">Customer feedback</span></span> |
| [<span data-ttu-id="42a7b-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="42a7b-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="42a7b-123">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="42a7b-123">Customer feedback</span></span> |
| [<span data-ttu-id="42a7b-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="42a7b-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="42a7b-125">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="42a7b-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="42a7b-126">Januar 2021</span><span class="sxs-lookup"><span data-stu-id="42a7b-126">January 2021</span></span>

| <span data-ttu-id="42a7b-127">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="42a7b-127">Column name</span></span> | <span data-ttu-id="42a7b-128">Name des ursprünglichen Werts</span><span class="sxs-lookup"><span data-stu-id="42a7b-128">Original value name</span></span> | <span data-ttu-id="42a7b-129">Name des neuen Werts</span><span class="sxs-lookup"><span data-stu-id="42a7b-129">New value name</span></span> | <span data-ttu-id="42a7b-130">Änderungsgrund</span><span class="sxs-lookup"><span data-stu-id="42a7b-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="42a7b-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="42a7b-131">MCAS</span></span> |    <span data-ttu-id="42a7b-132">Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="42a7b-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="42a7b-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="42a7b-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="42a7b-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="42a7b-135">EDR</span><span class="sxs-lookup"><span data-stu-id="42a7b-135">EDR</span></span>| <span data-ttu-id="42a7b-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="42a7b-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="42a7b-137">WindowsDefenderAv</span></span> | <span data-ttu-id="42a7b-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="42a7b-138">Antivirus</span></span> | <span data-ttu-id="42a7b-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="42a7b-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="42a7b-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="42a7b-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="42a7b-141">SmartScreen</span></span> | <span data-ttu-id="42a7b-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="42a7b-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="42a7b-143">CustomerTI</span></span> |  <span data-ttu-id="42a7b-144">Benutzerdefinierte TI</span><span class="sxs-lookup"><span data-stu-id="42a7b-144">Custom TI</span></span> | <span data-ttu-id="42a7b-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="42a7b-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="42a7b-146">OfficeATP</span></span> | <span data-ttu-id="42a7b-147">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="42a7b-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="42a7b-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="42a7b-149">MTP</span><span class="sxs-lookup"><span data-stu-id="42a7b-149">MTP</span></span>   | <span data-ttu-id="42a7b-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42a7b-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="42a7b-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="42a7b-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="42a7b-152">AzureATP</span></span> |    <span data-ttu-id="42a7b-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="42a7b-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="42a7b-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="42a7b-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="42a7b-155">CustomDetection</span></span>   | <span data-ttu-id="42a7b-156">Benutzerdefinierte Erkennung</span><span class="sxs-lookup"><span data-stu-id="42a7b-156">Custom detection</span></span> | <span data-ttu-id="42a7b-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="42a7b-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="42a7b-158">AutomatedInvestigation</span></span> |<span data-ttu-id="42a7b-159">Automatisierte Untersuchung</span><span class="sxs-lookup"><span data-stu-id="42a7b-159">Automated investigation</span></span> | <span data-ttu-id="42a7b-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="42a7b-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="42a7b-161">ThreatExperts</span></span> | <span data-ttu-id="42a7b-162">Microsoft-Bedrohungsexperten</span><span class="sxs-lookup"><span data-stu-id="42a7b-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="42a7b-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="42a7b-164">3rd party TI</span><span class="sxs-lookup"><span data-stu-id="42a7b-164">3rd party TI</span></span> | <span data-ttu-id="42a7b-165">Drittanbietersensoren</span><span class="sxs-lookup"><span data-stu-id="42a7b-165">3rd Party sensors</span></span> | <span data-ttu-id="42a7b-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="42a7b-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="42a7b-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="42a7b-168">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="42a7b-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="42a7b-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="42a7b-170">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="42a7b-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="42a7b-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42a7b-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="42a7b-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="42a7b-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="42a7b-173">Office 365 ATP</span></span>  |<span data-ttu-id="42a7b-174">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="42a7b-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="42a7b-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="42a7b-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="42a7b-176">Azure ATP</span></span>    |<span data-ttu-id="42a7b-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="42a7b-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="42a7b-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="42a7b-178">Rebranding</span></span> |

<span data-ttu-id="42a7b-179">`DetectionSource` ist in der Tabelle ["AlertInfo"](advanced-hunting-alertinfo-table.md) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="42a7b-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="42a7b-180">`ServiceSource` ist in den [Tabellen "AlertEvidence" und](advanced-hunting-alertevidence-table.md) ["AlertInfo"](advanced-hunting-alertinfo-table.md) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="42a7b-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 
## <a name="related-topics"></a><span data-ttu-id="42a7b-181">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="42a7b-181">Related topics</span></span>
- [<span data-ttu-id="42a7b-182">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="42a7b-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="42a7b-183">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="42a7b-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
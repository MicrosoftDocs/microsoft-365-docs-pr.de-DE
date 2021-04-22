---
title: Namensänderungen im Microsoft 365 Defender Advanced Hunting-Schema
description: Nachverfolgen und Überprüfen von Tabellen und Spalten für Namensänderungen im schema der erweiterten Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft 365 Defender, microsoft 365, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Daten, Benennungsänderungen, Umbenennen
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
ms.openlocfilehash: 22d26dac6b7ee502d6934349d22b1d40532f575f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935773"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="fee9c-104">Schema der erweiterten Suche – Benennungsänderungen</span><span class="sxs-lookup"><span data-stu-id="fee9c-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fee9c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fee9c-105">**Applies to:**</span></span>
- <span data-ttu-id="fee9c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fee9c-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="fee9c-107">Das [schema der erweiterten](advanced-hunting-schema-tables.md) Suche wird regelmäßig aktualisiert, um neue Tabellen und Spalten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fee9c-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="fee9c-108">In einigen Fällen werden vorhandene Spaltennamen umbenannt oder ersetzt, um die Benutzerfreundlichkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="fee9c-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="fee9c-109">Lesen Sie diesen Artikel, um Namensänderungen zu überprüfen, die sich auf Ihre Abfragen auswirken könnten.</span><span class="sxs-lookup"><span data-stu-id="fee9c-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="fee9c-110">Namensänderungen werden automatisch auf Abfragen angewendet, die im Security Center gespeichert werden, einschließlich Abfragen, die von benutzerdefinierten Erkennungsregeln verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fee9c-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="fee9c-111">Sie müssen diese Abfragen nicht manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="fee9c-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="fee9c-112">Sie müssen jedoch die folgenden Abfragen aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="fee9c-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="fee9c-113">Abfragen, die mithilfe der API ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="fee9c-113">Queries that are run using the API</span></span>
- <span data-ttu-id="fee9c-114">Abfragen, die an anderer Stelle außerhalb des Sicherheitscenters gespeichert werden</span><span class="sxs-lookup"><span data-stu-id="fee9c-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="fee9c-115">Dezember 2020</span><span class="sxs-lookup"><span data-stu-id="fee9c-115">December 2020</span></span>

| <span data-ttu-id="fee9c-116">Tabellenname</span><span class="sxs-lookup"><span data-stu-id="fee9c-116">Table name</span></span> | <span data-ttu-id="fee9c-117">Ursprünglicher Spaltenname</span><span class="sxs-lookup"><span data-stu-id="fee9c-117">Original column name</span></span> | <span data-ttu-id="fee9c-118">Neuer Spaltenname</span><span class="sxs-lookup"><span data-stu-id="fee9c-118">New column name</span></span> | <span data-ttu-id="fee9c-119">Änderungsgrund</span><span class="sxs-lookup"><span data-stu-id="fee9c-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="fee9c-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="fee9c-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="fee9c-121">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="fee9c-121">Customer feedback</span></span> |
| [<span data-ttu-id="fee9c-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="fee9c-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="fee9c-123">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="fee9c-123">Customer feedback</span></span> |
| [<span data-ttu-id="fee9c-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="fee9c-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="fee9c-125">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="fee9c-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="fee9c-126">Januar 2021</span><span class="sxs-lookup"><span data-stu-id="fee9c-126">January 2021</span></span>

| <span data-ttu-id="fee9c-127">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="fee9c-127">Column name</span></span> | <span data-ttu-id="fee9c-128">Ursprünglicher Wertname</span><span class="sxs-lookup"><span data-stu-id="fee9c-128">Original value name</span></span> | <span data-ttu-id="fee9c-129">Name des neuen Werts</span><span class="sxs-lookup"><span data-stu-id="fee9c-129">New value name</span></span> | <span data-ttu-id="fee9c-130">Änderungsgrund</span><span class="sxs-lookup"><span data-stu-id="fee9c-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="fee9c-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="fee9c-131">MCAS</span></span> |    <span data-ttu-id="fee9c-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fee9c-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="fee9c-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="fee9c-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="fee9c-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="fee9c-135">EDR</span><span class="sxs-lookup"><span data-stu-id="fee9c-135">EDR</span></span>| <span data-ttu-id="fee9c-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="fee9c-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="fee9c-137">WindowsDefenderAv</span></span> | <span data-ttu-id="fee9c-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="fee9c-138">Antivirus</span></span> | <span data-ttu-id="fee9c-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="fee9c-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="fee9c-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="fee9c-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="fee9c-141">SmartScreen</span></span> | <span data-ttu-id="fee9c-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="fee9c-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="fee9c-143">CustomerTI</span></span> |  <span data-ttu-id="fee9c-144">Benutzerdefiniertes TI</span><span class="sxs-lookup"><span data-stu-id="fee9c-144">Custom TI</span></span> | <span data-ttu-id="fee9c-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="fee9c-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="fee9c-146">OfficeATP</span></span> | <span data-ttu-id="fee9c-147">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="fee9c-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="fee9c-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="fee9c-149">MTP</span><span class="sxs-lookup"><span data-stu-id="fee9c-149">MTP</span></span>   | <span data-ttu-id="fee9c-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fee9c-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="fee9c-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="fee9c-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="fee9c-152">AzureATP</span></span> |    <span data-ttu-id="fee9c-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="fee9c-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="fee9c-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="fee9c-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="fee9c-155">CustomDetection</span></span>   | <span data-ttu-id="fee9c-156">Benutzerdefinierte Erkennung</span><span class="sxs-lookup"><span data-stu-id="fee9c-156">Custom detection</span></span> | <span data-ttu-id="fee9c-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="fee9c-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="fee9c-158">AutomatedInvestigation</span></span> |<span data-ttu-id="fee9c-159">Automatisierte Untersuchung</span><span class="sxs-lookup"><span data-stu-id="fee9c-159">Automated investigation</span></span> | <span data-ttu-id="fee9c-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="fee9c-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="fee9c-161">ThreatExperts</span></span> | <span data-ttu-id="fee9c-162">Microsoft-Bedrohungsexperten</span><span class="sxs-lookup"><span data-stu-id="fee9c-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="fee9c-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="fee9c-164">3rd Party TI</span><span class="sxs-lookup"><span data-stu-id="fee9c-164">3rd party TI</span></span> | <span data-ttu-id="fee9c-165">Sensoren von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="fee9c-165">3rd Party sensors</span></span> | <span data-ttu-id="fee9c-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="fee9c-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="fee9c-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="fee9c-168">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="fee9c-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="fee9c-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="fee9c-170">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fee9c-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="fee9c-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fee9c-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="fee9c-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="fee9c-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="fee9c-173">Office 365 ATP</span></span>  |<span data-ttu-id="fee9c-174">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="fee9c-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="fee9c-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="fee9c-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="fee9c-176">Azure ATP</span></span>    |<span data-ttu-id="fee9c-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="fee9c-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="fee9c-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="fee9c-178">Rebranding</span></span> |

<span data-ttu-id="fee9c-179">`DetectionSource` ist in der [AlertInfo-Tabelle](advanced-hunting-alertinfo-table.md) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fee9c-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="fee9c-180">`ServiceSource` ist in den [Tabellen AlertEvidence](advanced-hunting-alertevidence-table.md) und [AlertInfo](advanced-hunting-alertinfo-table.md) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fee9c-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="fee9c-181">Februar 2021</span><span class="sxs-lookup"><span data-stu-id="fee9c-181">February 2021</span></span>

1. <span data-ttu-id="fee9c-182">In den [Tabellen EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) und [EmailEvents](advanced-hunting-emailevents-table.md) wurden die `MalwareFilterVerdict` Spalten und durch die Spalte `PhishFilterVerdict` `ThreatTypes` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="fee9c-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="fee9c-183">Die `MalwareDetectionMethod` Spalten und wurden auch durch die Spalte `PhishDetectionMethod` `DetectionMethods` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="fee9c-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="fee9c-184">Diese Optimierung ermöglicht es uns, weitere Informationen unter den neuen Spalten zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="fee9c-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="fee9c-185">Die Zuordnung wird unten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fee9c-185">The mapping is provided below.</span></span>

| <span data-ttu-id="fee9c-186">Tabellenname</span><span class="sxs-lookup"><span data-stu-id="fee9c-186">Table name</span></span> | <span data-ttu-id="fee9c-187">Ursprünglicher Spaltenname</span><span class="sxs-lookup"><span data-stu-id="fee9c-187">Original column name</span></span> | <span data-ttu-id="fee9c-188">Neuer Spaltenname</span><span class="sxs-lookup"><span data-stu-id="fee9c-188">New column name</span></span> | <span data-ttu-id="fee9c-189">Änderungsgrund</span><span class="sxs-lookup"><span data-stu-id="fee9c-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="fee9c-190">Fügen Sie weitere Erkennungsmethoden ein</span><span class="sxs-lookup"><span data-stu-id="fee9c-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="fee9c-191">Weitere Bedrohungstypen enthalten</span><span class="sxs-lookup"><span data-stu-id="fee9c-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="fee9c-192">Fügen Sie weitere Erkennungsmethoden ein</span><span class="sxs-lookup"><span data-stu-id="fee9c-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="fee9c-193">Weitere Bedrohungstypen enthalten</span><span class="sxs-lookup"><span data-stu-id="fee9c-193">Include more threat types</span></span> |


2. <span data-ttu-id="fee9c-194">In den Tabellen und wurde die Spalte hinzugefügt, um weitere Informationen zur E-Mail-Bedrohung `EmailAttachmentInfo` `EmailEvents` zu `ThreatNames` erhalten.</span><span class="sxs-lookup"><span data-stu-id="fee9c-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="fee9c-195">Diese Spalte enthält Werte wie Spam oder Phish.</span><span class="sxs-lookup"><span data-stu-id="fee9c-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="fee9c-196">In der [DeviceInfo-Tabelle](advanced-hunting-deviceinfo-table.md) wurde die Spalte basierend auf Kundenfeedback durch `DeviceObjectId` die Spalte `AadDeviceId` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="fee9c-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="fee9c-197">In der [DeviceEvents-Tabelle](advanced-hunting-deviceevents-table.md) wurden mehrere ActionType-Namen geändert, um die Beschreibung der Aktion besser widerspiegeln zu können.</span><span class="sxs-lookup"><span data-stu-id="fee9c-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="fee9c-198">Details zu den Änderungen finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="fee9c-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="fee9c-199">Tabellenname</span><span class="sxs-lookup"><span data-stu-id="fee9c-199">Table name</span></span> | <span data-ttu-id="fee9c-200">Ursprünglicher ActionType-Name</span><span class="sxs-lookup"><span data-stu-id="fee9c-200">Original ActionType name</span></span> | <span data-ttu-id="fee9c-201">Neuer ActionType-Name</span><span class="sxs-lookup"><span data-stu-id="fee9c-201">New ActionType name</span></span> | <span data-ttu-id="fee9c-202">Änderungsgrund</span><span class="sxs-lookup"><span data-stu-id="fee9c-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="fee9c-203">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="fee9c-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="fee9c-204">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="fee9c-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="fee9c-205">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="fee9c-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="fee9c-206">Kundenfeedback</span><span class="sxs-lookup"><span data-stu-id="fee9c-206">Customer feedback</span></span> |






## <a name="related-topics"></a><span data-ttu-id="fee9c-207">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="fee9c-207">Related topics</span></span>
- [<span data-ttu-id="fee9c-208">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="fee9c-208">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fee9c-209">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="fee9c-209">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
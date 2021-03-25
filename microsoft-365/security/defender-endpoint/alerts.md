---
title: Abrufen der Benachrichtigungs-API
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Ressourcentyps Warnung in Microsoft Defender for Endpoint.
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4997d7118b139d993ed94ed917137ca107940e46
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199621"
---
# <a name="alert-resource-type"></a><span data-ttu-id="9ddf5-104">Ressourcentyp "Warnung"</span><span class="sxs-lookup"><span data-stu-id="9ddf5-104">Alert resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9ddf5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9ddf5-105">**Applies to:**</span></span>
- [<span data-ttu-id="9ddf5-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9ddf5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="9ddf5-107">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9ddf5-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9ddf5-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a><span data-ttu-id="9ddf5-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="9ddf5-109">Methods</span></span>

<span data-ttu-id="9ddf5-110">Methode</span><span class="sxs-lookup"><span data-stu-id="9ddf5-110">Method</span></span> |<span data-ttu-id="9ddf5-111">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="9ddf5-111">Return Type</span></span> |<span data-ttu-id="9ddf5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ddf5-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="9ddf5-113">Warnung erhalten</span><span class="sxs-lookup"><span data-stu-id="9ddf5-113">Get alert</span></span>](get-alert-info-by-id.md) | [<span data-ttu-id="9ddf5-114">Warnung</span><span class="sxs-lookup"><span data-stu-id="9ddf5-114">Alert</span></span>](alerts.md) | <span data-ttu-id="9ddf5-115">Ein einzelnes [Warnungsobjekt](alerts.md) erhalten.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-115">Get a single [alert](alerts.md) object.</span></span>
[<span data-ttu-id="9ddf5-116">Warnungen auflisten</span><span class="sxs-lookup"><span data-stu-id="9ddf5-116">List alerts</span></span>](get-alerts.md) | <span data-ttu-id="9ddf5-117">[Warnungssammlung](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="9ddf5-117">[Alert](alerts.md) collection</span></span> | <span data-ttu-id="9ddf5-118">Auflisten [der Warnungssammlung.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="9ddf5-118">List [alert](alerts.md) collection.</span></span>
[<span data-ttu-id="9ddf5-119">Warnung aktualisieren</span><span class="sxs-lookup"><span data-stu-id="9ddf5-119">Update alert</span></span>](update-alert.md) | [<span data-ttu-id="9ddf5-120">Warnung</span><span class="sxs-lookup"><span data-stu-id="9ddf5-120">Alert</span></span>](alerts.md) | <span data-ttu-id="9ddf5-121">Aktualisieren einer [bestimmten Warnung](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="9ddf5-121">Update specific [alert](alerts.md).</span></span>
[<span data-ttu-id="9ddf5-122">Batchupdatewarnungen</span><span class="sxs-lookup"><span data-stu-id="9ddf5-122">Batch update alerts</span></span>](batch-update-alerts.md) | | <span data-ttu-id="9ddf5-123">Aktualisieren eines Batches von [Warnungen](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="9ddf5-123">Update a batch of [alerts](alerts.md).</span></span>
[<span data-ttu-id="9ddf5-124">Erstellen einer Warnung</span><span class="sxs-lookup"><span data-stu-id="9ddf5-124">Create alert</span></span>](create-alert-by-reference.md)|[<span data-ttu-id="9ddf5-125">Warnung</span><span class="sxs-lookup"><span data-stu-id="9ddf5-125">Alert</span></span>](alerts.md)|<span data-ttu-id="9ddf5-126">Erstellen Sie eine Warnung basierend auf Ereignisdaten, die von [Advanced Hunting erhalten wurden.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="9ddf5-126">Create an alert based on event data obtained from [Advanced Hunting](run-advanced-query-api.md).</span></span>
[<span data-ttu-id="9ddf5-127">Auflisten verwandter Domänen</span><span class="sxs-lookup"><span data-stu-id="9ddf5-127">List related domains</span></span>](get-alert-related-domain-info.md)|<span data-ttu-id="9ddf5-128">Domänensammlung</span><span class="sxs-lookup"><span data-stu-id="9ddf5-128">Domain collection</span></span>| <span data-ttu-id="9ddf5-129">Listet URLs auf, die der Warnung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-129">List URLs associated with the alert.</span></span>
[<span data-ttu-id="9ddf5-130">Auflisten verwandter Dateien</span><span class="sxs-lookup"><span data-stu-id="9ddf5-130">List related files</span></span>](get-alert-related-files-info.md) | <span data-ttu-id="9ddf5-131">[Dateisammlung](files.md)</span><span class="sxs-lookup"><span data-stu-id="9ddf5-131">[File](files.md) collection</span></span> |  <span data-ttu-id="9ddf5-132">Listet [die](files.md) Dateientitäten auf, die der Warnung [zugeordnet sind.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="9ddf5-132">List the [file](files.md) entities that are associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="9ddf5-133">Auflisten verwandter IPs</span><span class="sxs-lookup"><span data-stu-id="9ddf5-133">List related IPs</span></span>](get-alert-related-ip-info.md) | <span data-ttu-id="9ddf5-134">IP-Auflistung</span><span class="sxs-lookup"><span data-stu-id="9ddf5-134">IP collection</span></span> | <span data-ttu-id="9ddf5-135">Listet IPs auf, die der Warnung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-135">List IPs that are associated with the alert.</span></span>
[<span data-ttu-id="9ddf5-136">Verwandte Computer erhalten</span><span class="sxs-lookup"><span data-stu-id="9ddf5-136">Get related machines</span></span>](get-alert-related-machine-info.md) | [<span data-ttu-id="9ddf5-137">Maschine</span><span class="sxs-lookup"><span data-stu-id="9ddf5-137">Machine</span></span>](machine.md) | <span data-ttu-id="9ddf5-138">Der [Computer,](machine.md) der der Warnung [zugeordnet ist.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="9ddf5-138">The [machine](machine.md) that is associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="9ddf5-139">Verwandte Benutzer erhalten</span><span class="sxs-lookup"><span data-stu-id="9ddf5-139">Get related users</span></span>](get-alert-related-user-info.md) | [<span data-ttu-id="9ddf5-140">Benutzer</span><span class="sxs-lookup"><span data-stu-id="9ddf5-140">User</span></span>](user.md) | <span data-ttu-id="9ddf5-141">Der [Benutzer,](user.md) der der Warnung [zugeordnet ist.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="9ddf5-141">The [user](user.md) that is associated with the [alert](alerts.md).</span></span>


## <a name="properties"></a><span data-ttu-id="9ddf5-142">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9ddf5-142">Properties</span></span>

<span data-ttu-id="9ddf5-143">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9ddf5-143">Property</span></span> |    <span data-ttu-id="9ddf5-144">Typ</span><span class="sxs-lookup"><span data-stu-id="9ddf5-144">Type</span></span>    |    <span data-ttu-id="9ddf5-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ddf5-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="9ddf5-146">id</span><span class="sxs-lookup"><span data-stu-id="9ddf5-146">id</span></span> | <span data-ttu-id="9ddf5-147">String</span><span class="sxs-lookup"><span data-stu-id="9ddf5-147">String</span></span> | <span data-ttu-id="9ddf5-148">Warnungs-ID.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-148">Alert ID.</span></span>
<span data-ttu-id="9ddf5-149">title</span><span class="sxs-lookup"><span data-stu-id="9ddf5-149">title</span></span> | <span data-ttu-id="9ddf5-150">String</span><span class="sxs-lookup"><span data-stu-id="9ddf5-150">String</span></span> | <span data-ttu-id="9ddf5-151">Warnungstitel.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-151">Alert title.</span></span>
<span data-ttu-id="9ddf5-152">description</span><span class="sxs-lookup"><span data-stu-id="9ddf5-152">description</span></span> | <span data-ttu-id="9ddf5-153">String</span><span class="sxs-lookup"><span data-stu-id="9ddf5-153">String</span></span> | <span data-ttu-id="9ddf5-154">Warnungsbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-154">Alert description.</span></span>
<span data-ttu-id="9ddf5-155">alertCreationTime</span><span class="sxs-lookup"><span data-stu-id="9ddf5-155">alertCreationTime</span></span> | <span data-ttu-id="9ddf5-156">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="9ddf5-156">Nullable DateTimeOffset</span></span> | <span data-ttu-id="9ddf5-157">Das Datum und die Uhrzeit (in UTC), zu der die Warnung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-157">The date and time (in UTC) the alert was created.</span></span>
<span data-ttu-id="9ddf5-158">lastEventTime</span><span class="sxs-lookup"><span data-stu-id="9ddf5-158">lastEventTime</span></span> | <span data-ttu-id="9ddf5-159">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="9ddf5-159">Nullable DateTimeOffset</span></span> | <span data-ttu-id="9ddf5-160">Das letzte Vorkommen des Ereignisses, das die Warnung auf demselben Gerät ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-160">The last occurrence of the event that triggered the alert on the same device.</span></span>
<span data-ttu-id="9ddf5-161">firstEventTime</span><span class="sxs-lookup"><span data-stu-id="9ddf5-161">firstEventTime</span></span> | <span data-ttu-id="9ddf5-162">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="9ddf5-162">Nullable DateTimeOffset</span></span> | <span data-ttu-id="9ddf5-163">Das erste Vorkommen des Ereignisses, das die Warnung auf diesem Gerät ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-163">The first occurrence of the event that triggered the alert on that device.</span></span>
<span data-ttu-id="9ddf5-164">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="9ddf5-164">lastUpdateTime</span></span> | <span data-ttu-id="9ddf5-165">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="9ddf5-165">Nullable DateTimeOffset</span></span> | <span data-ttu-id="9ddf5-166">Datum und Uhrzeit (in UTC), zu der die Warnung zuletzt aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-166">The date and time (in UTC) the alert was last updated.</span></span>
<span data-ttu-id="9ddf5-167">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="9ddf5-167">resolvedTime</span></span> | <span data-ttu-id="9ddf5-168">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="9ddf5-168">Nullable DateTimeOffset</span></span> | <span data-ttu-id="9ddf5-169">Datum und Uhrzeit, in dem der Status der Warnung in "Aufgelöst" geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-169">The date and time in which the status of the alert was changed to 'Resolved'.</span></span>
<span data-ttu-id="9ddf5-170">incidentId</span><span class="sxs-lookup"><span data-stu-id="9ddf5-170">incidentId</span></span> | <span data-ttu-id="9ddf5-171">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="9ddf5-171">Nullable Long</span></span> | <span data-ttu-id="9ddf5-172">Die [Vorfall-ID](view-incidents-queue.md) der Warnung.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-172">The [Incident](view-incidents-queue.md) ID of the Alert.</span></span>
<span data-ttu-id="9ddf5-173">investigationId</span><span class="sxs-lookup"><span data-stu-id="9ddf5-173">investigationId</span></span> | <span data-ttu-id="9ddf5-174">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="9ddf5-174">Nullable Long</span></span> | <span data-ttu-id="9ddf5-175">Die [Untersuchungs-ID](automated-investigations.md) im Zusammenhang mit der Warnung.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-175">The [Investigation](automated-investigations.md) ID related to the Alert.</span></span>
<span data-ttu-id="9ddf5-176">investigationState</span><span class="sxs-lookup"><span data-stu-id="9ddf5-176">investigationState</span></span> | <span data-ttu-id="9ddf5-177">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="9ddf5-177">Nullable Enum</span></span> | <span data-ttu-id="9ddf5-178">Der aktuelle Status der [Untersuchung](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="9ddf5-178">The current state of the [Investigation](automated-investigations.md).</span></span> <span data-ttu-id="9ddf5-179">Mögliche Werte sind: "Unknown", "Terminated", "SuccessfullyRemediated", "Benign", "Failed", "PartiallyRemediated", "Running", "PendingApproval", "PendingResource", "PartiallyInvestigated", "TerminatedByUser", "TerminatedBySystem", "Queued", "InnerFailure", "PreexistingAlert", "UnsupportedOs", "UnsupportedAlertType", "SuppressedAlert".</span><span class="sxs-lookup"><span data-stu-id="9ddf5-179">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="9ddf5-180">assignedTo</span><span class="sxs-lookup"><span data-stu-id="9ddf5-180">assignedTo</span></span> | <span data-ttu-id="9ddf5-181">String</span><span class="sxs-lookup"><span data-stu-id="9ddf5-181">String</span></span> | <span data-ttu-id="9ddf5-182">Besitzer der Warnung.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-182">Owner of the alert.</span></span>
<span data-ttu-id="9ddf5-183">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="9ddf5-183">severity</span></span> | <span data-ttu-id="9ddf5-184">Enum</span><span class="sxs-lookup"><span data-stu-id="9ddf5-184">Enum</span></span> | <span data-ttu-id="9ddf5-185">Der Schweregrad der Warnung.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-185">Severity of the alert.</span></span> <span data-ttu-id="9ddf5-186">Mögliche Werte sind: "UnSpecified", "Informational", "Low", "Medium" und "High".</span><span class="sxs-lookup"><span data-stu-id="9ddf5-186">Possible values are: 'UnSpecified', 'Informational', 'Low', 'Medium' and 'High'.</span></span>
<span data-ttu-id="9ddf5-187">status</span><span class="sxs-lookup"><span data-stu-id="9ddf5-187">status</span></span> | <span data-ttu-id="9ddf5-188">Enum</span><span class="sxs-lookup"><span data-stu-id="9ddf5-188">Enum</span></span> | <span data-ttu-id="9ddf5-189">Gibt den aktuellen Status der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-189">Specifies the current status of the alert.</span></span> <span data-ttu-id="9ddf5-190">Mögliche Werte sind: "Unbekannt", "Neu", "InProgress" und "Aufgelöst".</span><span class="sxs-lookup"><span data-stu-id="9ddf5-190">Possible values are: 'Unknown', 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="9ddf5-191">classification</span><span class="sxs-lookup"><span data-stu-id="9ddf5-191">classification</span></span> | <span data-ttu-id="9ddf5-192">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="9ddf5-192">Nullable Enum</span></span> | <span data-ttu-id="9ddf5-193">Spezifikation der Warnung.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-193">Specification of the alert.</span></span> <span data-ttu-id="9ddf5-194">Mögliche Werte sind: "Unbekannt", "FalsePositive", "TruePositive".</span><span class="sxs-lookup"><span data-stu-id="9ddf5-194">Possible values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span>
<span data-ttu-id="9ddf5-195">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="9ddf5-195">determination</span></span> | <span data-ttu-id="9ddf5-196">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="9ddf5-196">Nullable Enum</span></span> | <span data-ttu-id="9ddf5-197">Gibt die Bestimmung der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-197">Specifies the determination of the alert.</span></span> <span data-ttu-id="9ddf5-198">Mögliche Werte sind: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other".</span><span class="sxs-lookup"><span data-stu-id="9ddf5-198">Possible values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span></span>
<span data-ttu-id="9ddf5-199">category</span><span class="sxs-lookup"><span data-stu-id="9ddf5-199">category</span></span>| <span data-ttu-id="9ddf5-200">String</span><span class="sxs-lookup"><span data-stu-id="9ddf5-200">String</span></span> | <span data-ttu-id="9ddf5-201">Die Kategorie der Warnung.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-201">Category of the alert.</span></span>
<span data-ttu-id="9ddf5-202">detectionSource</span><span class="sxs-lookup"><span data-stu-id="9ddf5-202">detectionSource</span></span> | <span data-ttu-id="9ddf5-203">String</span><span class="sxs-lookup"><span data-stu-id="9ddf5-203">String</span></span> | <span data-ttu-id="9ddf5-204">Erkennungsquelle.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-204">Detection source.</span></span>
<span data-ttu-id="9ddf5-205">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="9ddf5-205">threatFamilyName</span></span> | <span data-ttu-id="9ddf5-206">String</span><span class="sxs-lookup"><span data-stu-id="9ddf5-206">String</span></span> | <span data-ttu-id="9ddf5-207">Bedrohungsfamilie.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-207">Threat family.</span></span>
<span data-ttu-id="9ddf5-208">threatName</span><span class="sxs-lookup"><span data-stu-id="9ddf5-208">threatName</span></span> | <span data-ttu-id="9ddf5-209">String</span><span class="sxs-lookup"><span data-stu-id="9ddf5-209">String</span></span> | <span data-ttu-id="9ddf5-210">Bedrohungsname.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-210">Threat name.</span></span>
<span data-ttu-id="9ddf5-211">machineId</span><span class="sxs-lookup"><span data-stu-id="9ddf5-211">machineId</span></span> | <span data-ttu-id="9ddf5-212">String</span><span class="sxs-lookup"><span data-stu-id="9ddf5-212">String</span></span> | <span data-ttu-id="9ddf5-213">ID einer [Computerentität,](machine.md) die der Warnung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-213">ID of a [machine](machine.md) entity that is associated with the alert.</span></span>
<span data-ttu-id="9ddf5-214">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="9ddf5-214">computerDnsName</span></span> | <span data-ttu-id="9ddf5-215">String</span><span class="sxs-lookup"><span data-stu-id="9ddf5-215">String</span></span> | <span data-ttu-id="9ddf5-216">[vollqualifizierten](machine.md) Namen des Computers.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-216">[machine](machine.md) fully qualified name.</span></span>
<span data-ttu-id="9ddf5-217">aadTenantId</span><span class="sxs-lookup"><span data-stu-id="9ddf5-217">aadTenantId</span></span> | <span data-ttu-id="9ddf5-218">String</span><span class="sxs-lookup"><span data-stu-id="9ddf5-218">String</span></span> | <span data-ttu-id="9ddf5-219">Die Azure Active Directory-ID.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-219">The Azure Active Directory ID.</span></span>
<span data-ttu-id="9ddf5-220">detectorId</span><span class="sxs-lookup"><span data-stu-id="9ddf5-220">detectorId</span></span> | <span data-ttu-id="9ddf5-221">String</span><span class="sxs-lookup"><span data-stu-id="9ddf5-221">String</span></span> | <span data-ttu-id="9ddf5-222">Die ID des Melders, der die Warnung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-222">The ID of the detector that triggered the alert.</span></span>
<span data-ttu-id="9ddf5-223">Kommentare</span><span class="sxs-lookup"><span data-stu-id="9ddf5-223">comments</span></span> | <span data-ttu-id="9ddf5-224">Liste der Warnungskommentare</span><span class="sxs-lookup"><span data-stu-id="9ddf5-224">List of Alert comments</span></span> | <span data-ttu-id="9ddf5-225">Alert Comment-Objekt enthält: Kommentarzeichenfolge, createdBy-Zeichenfolge und createTime-Datumszeit.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-225">Alert Comment object contains: comment string, createdBy string and createTime date time.</span></span>
<span data-ttu-id="9ddf5-226">Beweis</span><span class="sxs-lookup"><span data-stu-id="9ddf5-226">Evidence</span></span> | <span data-ttu-id="9ddf5-227">Liste der Warnungsbeweis</span><span class="sxs-lookup"><span data-stu-id="9ddf5-227">List of Alert evidence</span></span> | <span data-ttu-id="9ddf5-228">Nachweise im Zusammenhang mit der Warnung.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-228">Evidence related to the alert.</span></span> <span data-ttu-id="9ddf5-229">Siehe Beispiel unten.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-229">See example below.</span></span>

### <a name="response-example-for-getting-single-alert"></a><span data-ttu-id="9ddf5-230">Antwortbeispiel zum Abrufen einer einzelnen Warnung:</span><span class="sxs-lookup"><span data-stu-id="9ddf5-230">Response example for getting single alert:</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
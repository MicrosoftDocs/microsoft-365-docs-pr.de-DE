---
title: Liste der Vorfällen-API in Microsoft 365 Defender
description: Erfahren Sie, wie Sie die Vorfall-API in Microsoft 365 Defender auflisten
keywords: Liste, Vorfall, Vorfälle, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572153"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="e2470-104">Liste der Vorfällen-API in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2470-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e2470-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e2470-105">**Applies to:**</span></span>

- <span data-ttu-id="e2470-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2470-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2470-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="e2470-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e2470-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="e2470-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="e2470-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2470-109">API description</span></span>

<span data-ttu-id="e2470-110">Die Api für Listenvorfälle ermöglicht es Ihnen, Vorfälle zu sortieren, um eine informierte Cybersicherheitsreaktion zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2470-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="e2470-111">Es macht eine Sammlung von Vorfällen verfügbar, die in Ihrem Netzwerk innerhalb des in der Umgebungsbindungsrichtlinie angegebenen Zeitraums gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="e2470-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="e2470-112">Die neuesten Vorfälle werden oben in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e2470-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="e2470-113">Jeder Vorfall enthält ein Array verwandter Warnungen und der zugehörigen Entitäten.</span><span class="sxs-lookup"><span data-stu-id="e2470-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="e2470-114">Die API unterstützt  die folgenden OData-Operatoren:</span><span class="sxs-lookup"><span data-stu-id="e2470-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="e2470-115">`$filter` auf den `lastUpdateTime` , `createdTime` , und `status` `assignedTo` Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e2470-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="e2470-116">`$top`, mit einem Maximalwert von **100**</span><span class="sxs-lookup"><span data-stu-id="e2470-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="e2470-117">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e2470-117">Limitations</span></span>

1. <span data-ttu-id="e2470-118">Die maximale Seitengröße beträgt **100 Vorfälle**.</span><span class="sxs-lookup"><span data-stu-id="e2470-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="e2470-119">Die maximale Rate der Anfragen beträgt **50 Anrufe pro Minute** und **1500 Anrufe pro Stunde**.</span><span class="sxs-lookup"><span data-stu-id="e2470-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="e2470-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e2470-120">Permissions</span></span>

<span data-ttu-id="e2470-121">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e2470-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e2470-122">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access Microsoft 365 Defender-APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="e2470-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="e2470-123">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="e2470-123">Permission type</span></span> | <span data-ttu-id="e2470-124">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e2470-124">Permission</span></span> | <span data-ttu-id="e2470-125">Name der Berechtigungsanzeige</span><span class="sxs-lookup"><span data-stu-id="e2470-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="e2470-126">Anwendung</span><span class="sxs-lookup"><span data-stu-id="e2470-126">Application</span></span> | <span data-ttu-id="e2470-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="e2470-127">Incident.Read.All</span></span> | <span data-ttu-id="e2470-128">Lesen Sie alle Vorfälle</span><span class="sxs-lookup"><span data-stu-id="e2470-128">Read all incidents</span></span>
<span data-ttu-id="e2470-129">Anwendung</span><span class="sxs-lookup"><span data-stu-id="e2470-129">Application</span></span> | <span data-ttu-id="e2470-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e2470-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="e2470-131">Lesen und Schreiben aller Vorfälle</span><span class="sxs-lookup"><span data-stu-id="e2470-131">Read and write all incidents</span></span>
<span data-ttu-id="e2470-132">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="e2470-132">Delegated (work or school account)</span></span> | <span data-ttu-id="e2470-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="e2470-133">Incident.Read</span></span> | <span data-ttu-id="e2470-134">Vorfälle lesen</span><span class="sxs-lookup"><span data-stu-id="e2470-134">Read incidents</span></span>
<span data-ttu-id="e2470-135">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="e2470-135">Delegated (work or school account)</span></span> | <span data-ttu-id="e2470-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e2470-136">Incident.ReadWrite</span></span> | <span data-ttu-id="e2470-137">Vorkommnisse lesen und schreiben</span><span class="sxs-lookup"><span data-stu-id="e2470-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="e2470-138">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="e2470-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="e2470-139">Der Benutzer muss über die Ansichtsberechtigung für Vorfälle im Portal verfügen.</span><span class="sxs-lookup"><span data-stu-id="e2470-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="e2470-140">Die Antwort enthält nur Vorfälle, denen der Benutzer ausgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="e2470-141">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="e2470-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="e2470-142">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="e2470-142">Request headers</span></span>

<span data-ttu-id="e2470-143">Name</span><span class="sxs-lookup"><span data-stu-id="e2470-143">Name</span></span> | <span data-ttu-id="e2470-144">Typ</span><span class="sxs-lookup"><span data-stu-id="e2470-144">Type</span></span> | <span data-ttu-id="e2470-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2470-145">Description</span></span>
-|-|-
<span data-ttu-id="e2470-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="e2470-146">Authorization</span></span> | <span data-ttu-id="e2470-147">String</span><span class="sxs-lookup"><span data-stu-id="e2470-147">String</span></span> | <span data-ttu-id="e2470-148">Träger 'Token'.</span><span class="sxs-lookup"><span data-stu-id="e2470-148">Bearer {token}.</span></span> <span data-ttu-id="e2470-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="e2470-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="e2470-150">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="e2470-150">Request body</span></span>

<span data-ttu-id="e2470-151">Keine</span><span class="sxs-lookup"><span data-stu-id="e2470-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="e2470-152">Antwort</span><span class="sxs-lookup"><span data-stu-id="e2470-152">Response</span></span>

<span data-ttu-id="e2470-153">Bei Erfolg gibt diese Methode `200 OK` zurück , und eine Liste der [Vorfälle](api-incident.md) im Antworttext.</span><span class="sxs-lookup"><span data-stu-id="e2470-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="e2470-154">Schemazuordnung</span><span class="sxs-lookup"><span data-stu-id="e2470-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="e2470-155">Vorfallmetadaten</span><span class="sxs-lookup"><span data-stu-id="e2470-155">Incident metadata</span></span>

<span data-ttu-id="e2470-156">Feldname</span><span class="sxs-lookup"><span data-stu-id="e2470-156">Field name</span></span> | <span data-ttu-id="e2470-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2470-157">Description</span></span> | <span data-ttu-id="e2470-158">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="e2470-158">Example value</span></span>
-|-|-
<span data-ttu-id="e2470-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="e2470-159">incidentId</span></span> | <span data-ttu-id="e2470-160">Eindeutiger Bezeichner zur Darstellung des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="e2470-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="e2470-161">924565</span><span class="sxs-lookup"><span data-stu-id="e2470-161">924565</span></span>
<span data-ttu-id="e2470-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="e2470-162">redirectIncidentId</span></span> | <span data-ttu-id="e2470-163">Nur für den Fall, dass ein Vorfall zusammen mit einem anderen Vorfall als Teil der Ereignisverarbeitungslogik gruppiert wird.</span><span class="sxs-lookup"><span data-stu-id="e2470-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="e2470-164">924569</span><span class="sxs-lookup"><span data-stu-id="e2470-164">924569</span></span>
<span data-ttu-id="e2470-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="e2470-165">incidentName</span></span> | <span data-ttu-id="e2470-166">Zeichenfolgenwert für jeden Vorfall verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e2470-166">String value available for every incident.</span></span> | <span data-ttu-id="e2470-167">Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="e2470-167">Ransomware activity</span></span>
<span data-ttu-id="e2470-168">createdZeit</span><span class="sxs-lookup"><span data-stu-id="e2470-168">createdTime</span></span> | <span data-ttu-id="e2470-169">Zeitpunkt, zu dem der Vorfall zum ersten Mal erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e2470-169">Time when incident was first created.</span></span> | <span data-ttu-id="e2470-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="e2470-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="e2470-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="e2470-171">lastUpdateTime</span></span> | <span data-ttu-id="e2470-172">Uhrzeit, zu der der Vorfall zuletzt auf dem Backend aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e2470-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="e2470-173">Dieses Feld kann verwendet werden, wenn Sie den Anforderungsparameter für den Zeitbereich festlegen, in dem Vorfälle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e2470-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="e2470-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="e2470-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="e2470-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="e2470-175">assignedTo</span></span> | <span data-ttu-id="e2470-176">Besitzer des Vorfalls oder *null,* wenn kein Besitzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="e2470-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2470-177">secop2@contoso.com</span></span>
<span data-ttu-id="e2470-178">classification</span><span class="sxs-lookup"><span data-stu-id="e2470-178">classification</span></span> | <span data-ttu-id="e2470-179">Die Spezifikation für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="e2470-179">The specification for the incident.</span></span> <span data-ttu-id="e2470-180">Die Eigenschaftswerte sind: *Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="e2470-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="e2470-181">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="e2470-181">Unknown</span></span>
<span data-ttu-id="e2470-182">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="e2470-182">determination</span></span> | <span data-ttu-id="e2470-183">Gibt die Bestimmung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="e2470-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="e2470-184">Die Eigenschaftswerte sind: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Andere*</span><span class="sxs-lookup"><span data-stu-id="e2470-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="e2470-185">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="e2470-185">NotAvailable</span></span>
<span data-ttu-id="e2470-186">status</span><span class="sxs-lookup"><span data-stu-id="e2470-186">status</span></span> | <span data-ttu-id="e2470-187">Kategorisieren von Vorfällen (als *Aktiv* oder *Aufgelöst*).</span><span class="sxs-lookup"><span data-stu-id="e2470-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="e2470-188">Es kann Ihnen helfen, Ihre Reaktion auf Vorfälle zu organisieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e2470-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="e2470-189">Aktiv</span><span class="sxs-lookup"><span data-stu-id="e2470-189">Active</span></span>
<span data-ttu-id="e2470-190">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="e2470-190">severity</span></span> | <span data-ttu-id="e2470-191">Gibt die möglichen Auswirkungen auf Anlagen an.</span><span class="sxs-lookup"><span data-stu-id="e2470-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="e2470-192">Je höher der Schweregrad, desto größer die Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="e2470-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="e2470-193">In der Regel erfordern Elemente mit höherem Schweregrad die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="e2470-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="e2470-194">Einer der folgenden Werte: *Informational*, *Low*, \*Medium und *High*.</span><span class="sxs-lookup"><span data-stu-id="e2470-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="e2470-195">Mittel</span><span class="sxs-lookup"><span data-stu-id="e2470-195">Medium</span></span>
<span data-ttu-id="e2470-196">tags</span><span class="sxs-lookup"><span data-stu-id="e2470-196">tags</span></span> | <span data-ttu-id="e2470-197">Array von benutzerdefinierten Tags, die einem Vorfall zugeordnet sind, z. B. zum Kennzeichnen einer Gruppe von Vorfällen mit einem gemeinsamen Merkmal.</span><span class="sxs-lookup"><span data-stu-id="e2470-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="e2470-198">Kommentare</span><span class="sxs-lookup"><span data-stu-id="e2470-198">comments</span></span> | <span data-ttu-id="e2470-199">Array von Kommentaren, die von Secops bei der Verwaltung des Vorfalls erstellt wurden, z. B. zusätzliche Informationen zur Klassifizierungsauswahl.</span><span class="sxs-lookup"><span data-stu-id="e2470-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="e2470-200">Warnungen</span><span class="sxs-lookup"><span data-stu-id="e2470-200">alerts</span></span> | <span data-ttu-id="e2470-201">Array, das alle Warnungen im Zusammenhang mit dem Vorfall enthält, sowie andere Informationen, z. B. Schweregrad, Entitäten, die an der Warnung beteiligt waren, und die Quelle der Warnungen.</span><span class="sxs-lookup"><span data-stu-id="e2470-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="e2470-202">\[\] (siehe Details zu den Warnungsfeldern unten)</span><span class="sxs-lookup"><span data-stu-id="e2470-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="e2470-203">Warnungsmetadaten</span><span class="sxs-lookup"><span data-stu-id="e2470-203">Alerts metadata</span></span>

<span data-ttu-id="e2470-204">Feldname</span><span class="sxs-lookup"><span data-stu-id="e2470-204">Field name</span></span> | <span data-ttu-id="e2470-205">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2470-205">Description</span></span> | <span data-ttu-id="e2470-206">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="e2470-206">Example value</span></span>
-|-|-
<span data-ttu-id="e2470-207">alertId</span><span class="sxs-lookup"><span data-stu-id="e2470-207">alertId</span></span> | <span data-ttu-id="e2470-208">Eindeutiger Bezeichner zur Darstellung der Warnung</span><span class="sxs-lookup"><span data-stu-id="e2470-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="e2470-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="e2470-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="e2470-210">incidentId</span><span class="sxs-lookup"><span data-stu-id="e2470-210">incidentId</span></span> | <span data-ttu-id="e2470-211">Eindeutiger Bezeichner zur Darstellung des Vorfalls, dem diese Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="e2470-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="e2470-212">924565</span><span class="sxs-lookup"><span data-stu-id="e2470-212">924565</span></span>
<span data-ttu-id="e2470-213">serviceSource</span><span class="sxs-lookup"><span data-stu-id="e2470-213">serviceSource</span></span> | <span data-ttu-id="e2470-214">Der Dienst, von dem die Warnung stammt, z. B. Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity oder Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2470-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="e2470-215">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="e2470-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="e2470-216">Creationtime</span><span class="sxs-lookup"><span data-stu-id="e2470-216">creationTime</span></span> | <span data-ttu-id="e2470-217">Uhrzeit, zu dem die Warnung zum ersten Mal erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e2470-217">Time when alert was first created.</span></span> | <span data-ttu-id="e2470-218">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="e2470-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="e2470-219">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="e2470-219">lastUpdatedTime</span></span> | <span data-ttu-id="e2470-220">Uhrzeit, zu der die Warnung zuletzt am Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e2470-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="e2470-221">2020-09-06T14:46:57.243333Z</span><span class="sxs-lookup"><span data-stu-id="e2470-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="e2470-222">resolvedZeit</span><span class="sxs-lookup"><span data-stu-id="e2470-222">resolvedTime</span></span> | <span data-ttu-id="e2470-223">Uhrzeit, zu der die Warnung aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="e2470-223">Time when alert was resolved.</span></span> | <span data-ttu-id="e2470-224">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="e2470-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="e2470-225">firstAktivität</span><span class="sxs-lookup"><span data-stu-id="e2470-225">firstActivity</span></span> | <span data-ttu-id="e2470-226">Zeitpunkt, zu dem die Warnung zum ersten Mal gemeldet hat, dass die Aktivität am Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e2470-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="e2470-227">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="e2470-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="e2470-228">title</span><span class="sxs-lookup"><span data-stu-id="e2470-228">title</span></span> | <span data-ttu-id="e2470-229">Kurzes Identifizieren des Zeichenfolgenwerts, der für jede Warnung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="e2470-230">Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="e2470-230">Ransomware activity</span></span>
<span data-ttu-id="e2470-231">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2470-231">description</span></span> | <span data-ttu-id="e2470-232">Zeichenfolgenwert, der jede Warnung beschreibt.</span><span class="sxs-lookup"><span data-stu-id="e2470-232">String value describing each alert.</span></span> | <span data-ttu-id="e2470-233">Der User Test User2 (testUser2@contoso.com) hat 99 Dateien mit mehreren Erweiterungen manipuliert, die mit der ungewöhnlichen *Erweiterung* enden.</span><span class="sxs-lookup"><span data-stu-id="e2470-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="e2470-234">Dies ist eine ungewöhnliche Anzahl von Dateimanipulationen und ist ein Hinweis auf einen möglichen Ransomware-Angriff.</span><span class="sxs-lookup"><span data-stu-id="e2470-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="e2470-235">category</span><span class="sxs-lookup"><span data-stu-id="e2470-235">category</span></span> | <span data-ttu-id="e2470-236">Visuelle und numerische Ansicht, wie weit der Angriff entlang der Kill-Kette fortgeschritten ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="e2470-237">Ausgerichtet an das [MITRE ATT&CK™ Framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="e2470-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="e2470-238">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="e2470-238">Impact</span></span>
<span data-ttu-id="e2470-239">status</span><span class="sxs-lookup"><span data-stu-id="e2470-239">status</span></span> | <span data-ttu-id="e2470-240">Kategorisieren von Warnungen (als *Neu*, *Aktiv* oder *Aufgelöst*).</span><span class="sxs-lookup"><span data-stu-id="e2470-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="e2470-241">Es kann Ihnen helfen, Ihre Reaktion auf Warnungen zu organisieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e2470-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="e2470-242">Neu</span><span class="sxs-lookup"><span data-stu-id="e2470-242">New</span></span>
<span data-ttu-id="e2470-243">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="e2470-243">severity</span></span> | <span data-ttu-id="e2470-244">Gibt die möglichen Auswirkungen auf Anlagen an.</span><span class="sxs-lookup"><span data-stu-id="e2470-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="e2470-245">Je höher der Schweregrad, desto größer die Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="e2470-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="e2470-246">In der Regel erfordern Elemente mit höherem Schweregrad die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="e2470-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="e2470-247">Einer der folgenden Werte: *Informational*, *Low*, \*Medium und *High*.</span><span class="sxs-lookup"><span data-stu-id="e2470-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="e2470-248">Mittel</span><span class="sxs-lookup"><span data-stu-id="e2470-248">Medium</span></span>
<span data-ttu-id="e2470-249">investigationId</span><span class="sxs-lookup"><span data-stu-id="e2470-249">investigationId</span></span> | <span data-ttu-id="e2470-250">Die automatisierte Untersuchungs-ID, die durch diese Warnung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e2470-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="e2470-251">1234</span><span class="sxs-lookup"><span data-stu-id="e2470-251">1234</span></span>
<span data-ttu-id="e2470-252">UntersuchungStaat</span><span class="sxs-lookup"><span data-stu-id="e2470-252">investigationState</span></span> | <span data-ttu-id="e2470-253">Informationen über den aktuellen Stand der Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="e2470-253">Information on the investigation's current status.</span></span> <span data-ttu-id="e2470-254">Einer der folgenden Werte: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="e2470-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="e2470-255">Nicht unterstütztAlertType</span><span class="sxs-lookup"><span data-stu-id="e2470-255">UnsupportedAlertType</span></span>
<span data-ttu-id="e2470-256">classification</span><span class="sxs-lookup"><span data-stu-id="e2470-256">classification</span></span> | <span data-ttu-id="e2470-257">Die Spezifikation für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="e2470-257">The specification for the incident.</span></span> <span data-ttu-id="e2470-258">Die Eigenschaftswerte lauten: *Unknown*, *FalsePositive*, *TruePositive* oder *null*</span><span class="sxs-lookup"><span data-stu-id="e2470-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="e2470-259">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="e2470-259">Unknown</span></span>
<span data-ttu-id="e2470-260">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="e2470-260">determination</span></span> | <span data-ttu-id="e2470-261">Gibt die Bestimmung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="e2470-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="e2470-262">Die Eigenschaftswerte lauten: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* oder  *NULL*</span><span class="sxs-lookup"><span data-stu-id="e2470-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="e2470-263">Apt</span><span class="sxs-lookup"><span data-stu-id="e2470-263">Apt</span></span>
<span data-ttu-id="e2470-264">assignedTo</span><span class="sxs-lookup"><span data-stu-id="e2470-264">assignedTo</span></span> | <span data-ttu-id="e2470-265">Besitzer des Vorfalls oder *null,* wenn kein Besitzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="e2470-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2470-266">secop2@contoso.com</span></span>
<span data-ttu-id="e2470-267">actorName</span><span class="sxs-lookup"><span data-stu-id="e2470-267">actorName</span></span> | <span data-ttu-id="e2470-268">Die Aktivitätsgruppe, falls vorhanden, die dieser Warnung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="e2470-269">Bor</span><span class="sxs-lookup"><span data-stu-id="e2470-269">BORON</span></span>
<span data-ttu-id="e2470-270">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="e2470-270">threatFamilyName</span></span> | <span data-ttu-id="e2470-271">Bedrohungsfamilie, die mit dieser Warnung verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="e2470-272">null</span><span class="sxs-lookup"><span data-stu-id="e2470-272">null</span></span>
<span data-ttu-id="e2470-273">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="e2470-273">mitreTechniques</span></span> | <span data-ttu-id="e2470-274">Die Angriffstechniken, die auf das [MITRE ATT&CK](https://attack.mitre.org/)™ Framework ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="e2470-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="e2470-275">Geräte</span><span class="sxs-lookup"><span data-stu-id="e2470-275">devices</span></span> | <span data-ttu-id="e2470-276">Alle Geräte, auf denen Warnungen im Zusammenhang mit dem Vorfall gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="e2470-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="e2470-277">\[\] (siehe Details zu Entitätsfeldern unten)</span><span class="sxs-lookup"><span data-stu-id="e2470-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="e2470-278">Geräteformat</span><span class="sxs-lookup"><span data-stu-id="e2470-278">Device format</span></span>

<span data-ttu-id="e2470-279">Feldname</span><span class="sxs-lookup"><span data-stu-id="e2470-279">Field name</span></span> | <span data-ttu-id="e2470-280">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2470-280">Description</span></span> | <span data-ttu-id="e2470-281">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="e2470-281">Example value</span></span>
-|-|-
<span data-ttu-id="e2470-282">Deviceid</span><span class="sxs-lookup"><span data-stu-id="e2470-282">DeviceId</span></span> | <span data-ttu-id="e2470-283">Die Geräte-ID, wie in Microsoft Defender für Endpoint festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e2470-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="e2470-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="e2470-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="e2470-285">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="e2470-285">aadDeviceId</span></span> |  <span data-ttu-id="e2470-286">Die Geräte-ID, wie in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis)angegeben.</span><span class="sxs-lookup"><span data-stu-id="e2470-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="e2470-287">Nur für Domänengeräte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e2470-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="e2470-288">null</span><span class="sxs-lookup"><span data-stu-id="e2470-288">null</span></span>
<span data-ttu-id="e2470-289">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="e2470-289">deviceDnsName</span></span> | <span data-ttu-id="e2470-290">Der vollqualifizierte Domänenname für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="e2470-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="e2470-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2470-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="e2470-292">osPlatform</span><span class="sxs-lookup"><span data-stu-id="e2470-292">osPlatform</span></span> | <span data-ttu-id="e2470-293">Die Betriebssystemplattform, auf der das Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e2470-293">The OS platform the device is running.</span></span>| <span data-ttu-id="e2470-294">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="e2470-294">WindowsServer2016</span></span>
<span data-ttu-id="e2470-295">osBuild</span><span class="sxs-lookup"><span data-stu-id="e2470-295">osBuild</span></span> | <span data-ttu-id="e2470-296">Die Buildversion für das Betriebssystem, auf dem das Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e2470-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="e2470-297">14393</span><span class="sxs-lookup"><span data-stu-id="e2470-297">14393</span></span>
<span data-ttu-id="e2470-298">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="e2470-298">rbacGroupName</span></span> | <span data-ttu-id="e2470-299">Die dem Gerät zugeordnete [rollenbasierte Zugriffssteuerungsgruppe](/azure/role-based-access-control/overview) (RBAC).</span><span class="sxs-lookup"><span data-stu-id="e2470-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="e2470-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="e2470-300">WDATP-Ring0</span></span>
<span data-ttu-id="e2470-301">firstSeen</span><span class="sxs-lookup"><span data-stu-id="e2470-301">firstSeen</span></span> | <span data-ttu-id="e2470-302">Uhrzeit, zu der das Gerät zum ersten Mal gesehen wurde.</span><span class="sxs-lookup"><span data-stu-id="e2470-302">Time when device was first seen.</span></span> | <span data-ttu-id="e2470-303">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="e2470-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="e2470-304">healthStatus</span><span class="sxs-lookup"><span data-stu-id="e2470-304">healthStatus</span></span> | <span data-ttu-id="e2470-305">Der Integritätszustand des Geräts.</span><span class="sxs-lookup"><span data-stu-id="e2470-305">The health state of the device.</span></span> | <span data-ttu-id="e2470-306">Aktiv</span><span class="sxs-lookup"><span data-stu-id="e2470-306">Active</span></span>
<span data-ttu-id="e2470-307">riskScore</span><span class="sxs-lookup"><span data-stu-id="e2470-307">riskScore</span></span> | <span data-ttu-id="e2470-308">Der Risiko-Score für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="e2470-308">The risk score for the  device.</span></span> | <span data-ttu-id="e2470-309">Hoch</span><span class="sxs-lookup"><span data-stu-id="e2470-309">High</span></span>
<span data-ttu-id="e2470-310">Entitäten</span><span class="sxs-lookup"><span data-stu-id="e2470-310">entities</span></span> | <span data-ttu-id="e2470-311">Alle Entitäten, die als Teil einer bestimmten Warnung identifiziert wurden oder mit ihr verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="e2470-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="e2470-312">\[\] (siehe Details zu Entitätsfeldern unten)</span><span class="sxs-lookup"><span data-stu-id="e2470-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="e2470-313">Entitätsformat</span><span class="sxs-lookup"><span data-stu-id="e2470-313">Entity Format</span></span>

<span data-ttu-id="e2470-314">Feldname</span><span class="sxs-lookup"><span data-stu-id="e2470-314">Field name</span></span> | <span data-ttu-id="e2470-315">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2470-315">Description</span></span> | <span data-ttu-id="e2470-316">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="e2470-316">Example value</span></span>
-|-|-
<span data-ttu-id="e2470-317">Entitytype</span><span class="sxs-lookup"><span data-stu-id="e2470-317">entityType</span></span> | <span data-ttu-id="e2470-318">Entitäten, die als Teil einer bestimmten Warnung identifiziert wurden oder mit ihr verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="e2470-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="e2470-319">Die Eigenschaftenwerte sind: *Benutzer*, *Ip*, *Url*, *Datei*, *Prozess*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span><span class="sxs-lookup"><span data-stu-id="e2470-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="e2470-320">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e2470-320">User</span></span>
<span data-ttu-id="e2470-321">sha1</span><span class="sxs-lookup"><span data-stu-id="e2470-321">sha1</span></span> | <span data-ttu-id="e2470-322">Verfügbar, wenn entityType *Datei* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="e2470-323">Der Dateihash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e2470-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="e2470-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="e2470-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="e2470-325">sha256</span><span class="sxs-lookup"><span data-stu-id="e2470-325">sha256</span></span> | <span data-ttu-id="e2470-326">Verfügbar, wenn entityType *Datei* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="e2470-327">Der Dateihash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e2470-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="e2470-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="e2470-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="e2470-329">fileName</span><span class="sxs-lookup"><span data-stu-id="e2470-329">fileName</span></span> | <span data-ttu-id="e2470-330">Verfügbar, wenn entityType *Datei* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="e2470-331">Der Dateiname für Warnungen, die einer Datei oder einem Prozess zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="e2470-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="e2470-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="e2470-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="e2470-333">Filepath</span><span class="sxs-lookup"><span data-stu-id="e2470-333">filePath</span></span> | <span data-ttu-id="e2470-334">Verfügbar, wenn entityType *Datei* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="e2470-335">Der Dateipfad für Warnungen, die einer Datei oder einem Prozess zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="e2470-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="e2470-336">C: \\ agent_work_temp-Bereitstellungssystem, 2020-09-06 12_14_54, Out</span><span class="sxs-lookup"><span data-stu-id="e2470-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="e2470-337">Processid</span><span class="sxs-lookup"><span data-stu-id="e2470-337">processId</span></span> | <span data-ttu-id="e2470-338">Verfügbar, wenn entityType *Prozess* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="e2470-339">24348</span><span class="sxs-lookup"><span data-stu-id="e2470-339">24348</span></span>
<span data-ttu-id="e2470-340">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="e2470-340">processCommandLine</span></span> | <span data-ttu-id="e2470-341">Verfügbar, wenn entityType *Prozess* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="e2470-342">"Ihre Datei ist bereit, \_1911150169.exe herunterzuladen"</span><span class="sxs-lookup"><span data-stu-id="e2470-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="e2470-343">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="e2470-343">processCreationTime</span></span> | <span data-ttu-id="e2470-344">Verfügbar, wenn entityType *Prozess* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="e2470-345">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="e2470-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="e2470-346">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="e2470-346">parentProcessId</span></span> | <span data-ttu-id="e2470-347">Verfügbar, wenn entityType *Prozess* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="e2470-348">16840</span><span class="sxs-lookup"><span data-stu-id="e2470-348">16840</span></span>
<span data-ttu-id="e2470-349">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="e2470-349">parentProcessCreationTime</span></span> | <span data-ttu-id="e2470-350">Verfügbar, wenn entityType *Prozess* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="e2470-351">18.07.2010 02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="e2470-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="e2470-352">ipAddress</span><span class="sxs-lookup"><span data-stu-id="e2470-352">ipAddress</span></span> | <span data-ttu-id="e2470-353">Verfügbar, wenn entityType *Ip* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="e2470-354">IP-Adresse für Warnungen im Zusammenhang mit Netzwerkereignissen, z. B. *Kommunikation mit einem böswilligen Netzwerkziel*.</span><span class="sxs-lookup"><span data-stu-id="e2470-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="e2470-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="e2470-355">62.216.203.204</span></span>
<span data-ttu-id="e2470-356">url</span><span class="sxs-lookup"><span data-stu-id="e2470-356">url</span></span> | <span data-ttu-id="e2470-357">Verfügbar, wenn entityType *Url* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="e2470-358">URL für Warnungen im Zusammenhang mit Netzwerkereignissen, z. B. *Kommunikation mit einem böswilligen Netzwerkziel*.</span><span class="sxs-lookup"><span data-stu-id="e2470-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="e2470-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="e2470-359">down.esales360.cn</span></span>
<span data-ttu-id="e2470-360">accountName</span><span class="sxs-lookup"><span data-stu-id="e2470-360">accountName</span></span> | <span data-ttu-id="e2470-361">Verfügbar, wenn entityType *Benutzer* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="e2470-362">testUser2</span><span class="sxs-lookup"><span data-stu-id="e2470-362">testUser2</span></span>
<span data-ttu-id="e2470-363">Domänname</span><span class="sxs-lookup"><span data-stu-id="e2470-363">domainName</span></span> | <span data-ttu-id="e2470-364">Verfügbar, wenn entityType *Benutzer* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="e2470-365">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="e2470-365">europe.corp.contoso</span></span>
<span data-ttu-id="e2470-366">userSid</span><span class="sxs-lookup"><span data-stu-id="e2470-366">userSid</span></span> | <span data-ttu-id="e2470-367">Verfügbar, wenn entityType *Benutzer* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="e2470-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="e2470-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="e2470-369">aadUserId</span><span class="sxs-lookup"><span data-stu-id="e2470-369">aadUserId</span></span> | <span data-ttu-id="e2470-370">Verfügbar, wenn entityType *Benutzer* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="e2470-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="e2470-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="e2470-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="e2470-372">userPrincipalName</span></span> | <span data-ttu-id="e2470-373">Verfügbar, wenn entityType *Benutzer* / *MailBox* / *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="e2470-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2470-374">testUser2@contoso.com</span></span>
<span data-ttu-id="e2470-375">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="e2470-375">mailboxDisplayName</span></span> | <span data-ttu-id="e2470-376">Verfügbar, wenn entityType *MailBox* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="e2470-377">Test Benutzer2</span><span class="sxs-lookup"><span data-stu-id="e2470-377">test User2</span></span>
<span data-ttu-id="e2470-378">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="e2470-378">mailboxAddress</span></span> | <span data-ttu-id="e2470-379">Verfügbar, wenn entityType *Benutzer* / *MailBox* / *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="e2470-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2470-380">testUser2@contoso.com</span></span>
<span data-ttu-id="e2470-381">clusterBy</span><span class="sxs-lookup"><span data-stu-id="e2470-381">clusterBy</span></span> | <span data-ttu-id="e2470-382">Verfügbar, wenn entityType  *MailCluster* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="e2470-383">Thema; P2SenderDomain; Contenttype</span><span class="sxs-lookup"><span data-stu-id="e2470-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="e2470-384">sender</span><span class="sxs-lookup"><span data-stu-id="e2470-384">sender</span></span> | <span data-ttu-id="e2470-385">Verfügbar, wenn entityType *Benutzer* / *MailBox* / *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="e2470-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="e2470-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="e2470-387">recipient</span><span class="sxs-lookup"><span data-stu-id="e2470-387">recipient</span></span> | <span data-ttu-id="e2470-388">Verfügbar, wenn entityType *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="e2470-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2470-389">testUser2@contoso.com</span></span>
<span data-ttu-id="e2470-390">subject</span><span class="sxs-lookup"><span data-stu-id="e2470-390">subject</span></span> | <span data-ttu-id="e2470-391">Verfügbar, wenn entityType *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="e2470-392">\[EXTERNAL \] Aufmerksamkeit</span><span class="sxs-lookup"><span data-stu-id="e2470-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="e2470-393">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="e2470-393">deliveryAction</span></span> | <span data-ttu-id="e2470-394">Verfügbar, wenn entityType *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="e2470-395">Geliefert</span><span class="sxs-lookup"><span data-stu-id="e2470-395">Delivered</span></span>
<span data-ttu-id="e2470-396">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="e2470-396">securityGroupId</span></span> | <span data-ttu-id="e2470-397">Verfügbar, wenn entityType  *SecurityGroup* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="e2470-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="e2470-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="e2470-399">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="e2470-399">securityGroupName</span></span> | <span data-ttu-id="e2470-400">Verfügbar, wenn entityType  *SecurityGroup* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="e2470-401">Netzwerkkonfigurationsoperatoren</span><span class="sxs-lookup"><span data-stu-id="e2470-401">Network Configuration Operators</span></span>
<span data-ttu-id="e2470-402">registryHive</span><span class="sxs-lookup"><span data-stu-id="e2470-402">registryHive</span></span> | <span data-ttu-id="e2470-403">Verfügbar, wenn entityType  *Registrierung* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="e2470-404">HKEY \_ LOCAL \_ MASCHINE</span><span class="sxs-lookup"><span data-stu-id="e2470-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="e2470-405">Registrykey</span><span class="sxs-lookup"><span data-stu-id="e2470-405">registryKey</span></span> | <span data-ttu-id="e2470-406">Verfügbar, wenn entityType  *Registrierung* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="e2470-407">SOFTWARE-Windows NT-Version-Winlogon-Windows-NT-Version-Winlogon</span><span class="sxs-lookup"><span data-stu-id="e2470-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="e2470-408">registryValueType</span><span class="sxs-lookup"><span data-stu-id="e2470-408">registryValueType</span></span> | <span data-ttu-id="e2470-409">Verfügbar, wenn entityType  *Registrierung* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="e2470-410">String</span><span class="sxs-lookup"><span data-stu-id="e2470-410">String</span></span>
<span data-ttu-id="e2470-411">RegistryValue</span><span class="sxs-lookup"><span data-stu-id="e2470-411">registryValue</span></span> | <span data-ttu-id="e2470-412">Verfügbar, wenn entityType  *Registrierung* ist.</span><span class="sxs-lookup"><span data-stu-id="e2470-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="e2470-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="e2470-413">31-00-00-00</span></span>
<span data-ttu-id="e2470-414">deviceId</span><span class="sxs-lookup"><span data-stu-id="e2470-414">deviceId</span></span> | <span data-ttu-id="e2470-415">Die ID(en) des Geräts, das sich auf die Entität bezieht.</span><span class="sxs-lookup"><span data-stu-id="e2470-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="e2470-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="e2470-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="e2470-417">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2470-417">Example</span></span>

<span data-ttu-id="e2470-418">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="e2470-418">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="e2470-419">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="e2470-419">**Response**</span></span>

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="e2470-420">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="e2470-420">Related articles</span></span>

- [<span data-ttu-id="e2470-421">Zugriff auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="e2470-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="e2470-422">Informationen zu API-Limits und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="e2470-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="e2470-423">Verstehen von Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="e2470-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="e2470-424">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="e2470-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e2470-425">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="e2470-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="e2470-426">Aktualisieren der Vorfall-API</span><span class="sxs-lookup"><span data-stu-id="e2470-426">Update incident API</span></span>](api-update-incidents.md)

---
title: Auflisten der Incidents-API in Microsoft 365 Defender
description: Informationen zum Auflisten der Incidents-API in Microsoft 365 Defender
keywords: list, incident, incidents, api
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
ms.openlocfilehash: 833bc1d8284829323cc2f0c391e42f4e563a6948
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730882"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="0244a-104">Auflisten der Incidents-API in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0244a-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0244a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0244a-105">**Applies to:**</span></span>

- [<span data-ttu-id="0244a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0244a-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="0244a-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="0244a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0244a-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="0244a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="0244a-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0244a-109">API description</span></span>

<span data-ttu-id="0244a-110">Mit der API für Listenvorfälle können Sie Vorfälle sortieren, um eine informierte Cybersicherheitsantwort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0244a-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="0244a-111">Es wird eine Sammlung von Vorfällen verfügbar gemacht, die in Ihrem Netzwerk innerhalb des von Ihnen in Ihrer Umgebungsaufbewahrungsrichtlinie angegebenen Zeitbereichs gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="0244a-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="0244a-112">Die neuesten Vorfälle werden am Anfang der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0244a-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="0244a-113">Jeder Vorfall enthält ein Array verwandter Warnungen und deren zugehörige Entitäten.</span><span class="sxs-lookup"><span data-stu-id="0244a-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="0244a-114">Die API unterstützt die folgenden **OData-Operatoren:**</span><span class="sxs-lookup"><span data-stu-id="0244a-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="0244a-115">`$filter`auf `lastUpdateTime` den `createdTime` Eigenschaften , , `status` und `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="0244a-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="0244a-116">`$top`, mit einem maximalen Wert von **100**</span><span class="sxs-lookup"><span data-stu-id="0244a-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="0244a-117">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="0244a-117">Limitations</span></span>

1. <span data-ttu-id="0244a-118">Die maximale Seitengröße beträgt **100 Vorfälle.**</span><span class="sxs-lookup"><span data-stu-id="0244a-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="0244a-119">Die maximale Anzahl von Anforderungen beträgt **50 Anrufe pro Minute und** **1500 Anrufe pro Stunde.**</span><span class="sxs-lookup"><span data-stu-id="0244a-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="0244a-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0244a-120">Permissions</span></span>

<span data-ttu-id="0244a-121">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0244a-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0244a-122">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access Microsoft 365 Defender APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="0244a-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="0244a-123">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="0244a-123">Permission type</span></span> | <span data-ttu-id="0244a-124">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0244a-124">Permission</span></span> | <span data-ttu-id="0244a-125">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0244a-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="0244a-126">Application</span><span class="sxs-lookup"><span data-stu-id="0244a-126">Application</span></span> | <span data-ttu-id="0244a-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="0244a-127">Incident.Read.All</span></span> | <span data-ttu-id="0244a-128">Alle Vorfälle lesen</span><span class="sxs-lookup"><span data-stu-id="0244a-128">Read all incidents</span></span>
<span data-ttu-id="0244a-129">Application</span><span class="sxs-lookup"><span data-stu-id="0244a-129">Application</span></span> | <span data-ttu-id="0244a-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="0244a-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="0244a-131">Lesen und Schreiben aller Vorfälle</span><span class="sxs-lookup"><span data-stu-id="0244a-131">Read and write all incidents</span></span>
<span data-ttu-id="0244a-132">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="0244a-132">Delegated (work or school account)</span></span> | <span data-ttu-id="0244a-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="0244a-133">Incident.Read</span></span> | <span data-ttu-id="0244a-134">Lesen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="0244a-134">Read incidents</span></span>
<span data-ttu-id="0244a-135">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="0244a-135">Delegated (work or school account)</span></span> | <span data-ttu-id="0244a-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0244a-136">Incident.ReadWrite</span></span> | <span data-ttu-id="0244a-137">Lese- und Schreibvorfälle</span><span class="sxs-lookup"><span data-stu-id="0244a-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="0244a-138">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="0244a-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="0244a-139">Der Benutzer muss über die Berechtigung zum Anzeigen von Vorfällen im Portal verfügen.</span><span class="sxs-lookup"><span data-stu-id="0244a-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="0244a-140">Die Antwort umfasst nur Vorfälle, für die der Benutzer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0244a-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="0244a-141">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="0244a-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="0244a-142">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="0244a-142">Request headers</span></span>

<span data-ttu-id="0244a-143">Name</span><span class="sxs-lookup"><span data-stu-id="0244a-143">Name</span></span> | <span data-ttu-id="0244a-144">Typ</span><span class="sxs-lookup"><span data-stu-id="0244a-144">Type</span></span> | <span data-ttu-id="0244a-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0244a-145">Description</span></span>
-|-|-
<span data-ttu-id="0244a-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="0244a-146">Authorization</span></span> | <span data-ttu-id="0244a-147">String</span><span class="sxs-lookup"><span data-stu-id="0244a-147">String</span></span> | <span data-ttu-id="0244a-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="0244a-148">Bearer {token}.</span></span> <span data-ttu-id="0244a-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="0244a-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="0244a-150">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="0244a-150">Request body</span></span>

<span data-ttu-id="0244a-151">Keine</span><span class="sxs-lookup"><span data-stu-id="0244a-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="0244a-152">Antwort</span><span class="sxs-lookup"><span data-stu-id="0244a-152">Response</span></span>

<span data-ttu-id="0244a-153">Wenn die Methode erfolgreich ist, wird eine Liste der `200 OK` [Vorfälle im](api-incident.md) Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0244a-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="0244a-154">Schemazuordnung</span><span class="sxs-lookup"><span data-stu-id="0244a-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="0244a-155">Metadaten zu Vorfällen</span><span class="sxs-lookup"><span data-stu-id="0244a-155">Incident metadata</span></span>

<span data-ttu-id="0244a-156">Feldname</span><span class="sxs-lookup"><span data-stu-id="0244a-156">Field name</span></span> | <span data-ttu-id="0244a-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0244a-157">Description</span></span> | <span data-ttu-id="0244a-158">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="0244a-158">Example value</span></span>
-|-|-
<span data-ttu-id="0244a-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="0244a-159">incidentId</span></span> | <span data-ttu-id="0244a-160">Eindeutige ID zur Darstellung des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="0244a-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="0244a-161">924565</span><span class="sxs-lookup"><span data-stu-id="0244a-161">924565</span></span>
<span data-ttu-id="0244a-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="0244a-162">redirectIncidentId</span></span> | <span data-ttu-id="0244a-163">Nur aufgefüllt, wenn ein Vorfall zusammen mit einem anderen Vorfall im Rahmen der Vorfallverarbeitungslogik gruppieren wird.</span><span class="sxs-lookup"><span data-stu-id="0244a-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="0244a-164">924569</span><span class="sxs-lookup"><span data-stu-id="0244a-164">924569</span></span>
<span data-ttu-id="0244a-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="0244a-165">incidentName</span></span> | <span data-ttu-id="0244a-166">Zeichenfolgenwert, der für jeden Vorfall verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0244a-166">String value available for every incident.</span></span> | <span data-ttu-id="0244a-167">Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="0244a-167">Ransomware activity</span></span>
<span data-ttu-id="0244a-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="0244a-168">createdTime</span></span> | <span data-ttu-id="0244a-169">Zeitpunkt, zu dem der Vorfall zum ersten Mal erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="0244a-169">Time when incident was first created.</span></span> | <span data-ttu-id="0244a-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="0244a-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="0244a-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="0244a-171">lastUpdateTime</span></span> | <span data-ttu-id="0244a-172">Zeitpunkt, zu dem der Vorfall zuletzt im Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0244a-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="0244a-173">Dieses Feld kann verwendet werden, wenn Sie den Anforderungsparameter für den Zeitraum festlegen, in dem Vorfälle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0244a-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="0244a-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="0244a-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="0244a-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="0244a-175">assignedTo</span></span> | <span data-ttu-id="0244a-176">Besitzer des Vorfalls oder *null,* wenn kein Besitzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0244a-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="0244a-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0244a-177">secop2@contoso.com</span></span>
<span data-ttu-id="0244a-178">classification</span><span class="sxs-lookup"><span data-stu-id="0244a-178">classification</span></span> | <span data-ttu-id="0244a-179">Die Spezifikation für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="0244a-179">The specification for the incident.</span></span> <span data-ttu-id="0244a-180">Die Eigenschaftswerte sind: *Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="0244a-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="0244a-181">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="0244a-181">Unknown</span></span>
<span data-ttu-id="0244a-182">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="0244a-182">determination</span></span> | <span data-ttu-id="0244a-183">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="0244a-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="0244a-184">Die Eigenschaftswerte sind: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span><span class="sxs-lookup"><span data-stu-id="0244a-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="0244a-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="0244a-185">NotAvailable</span></span>
<span data-ttu-id="0244a-186">status</span><span class="sxs-lookup"><span data-stu-id="0244a-186">status</span></span> | <span data-ttu-id="0244a-187">Kategorisieren von *Vorfällen (als Aktiv* oder *Aufgelöst*).</span><span class="sxs-lookup"><span data-stu-id="0244a-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="0244a-188">Es kann Ihnen helfen, Ihre Reaktion auf Vorfälle zu organisieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="0244a-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="0244a-189">Aktiv</span><span class="sxs-lookup"><span data-stu-id="0244a-189">Active</span></span>
<span data-ttu-id="0244a-190">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="0244a-190">severity</span></span> | <span data-ttu-id="0244a-191">Gibt die möglichen Auswirkungen auf Ressourcen an.</span><span class="sxs-lookup"><span data-stu-id="0244a-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="0244a-192">Je höher der Schweregrad, desto größer sind die Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="0244a-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="0244a-193">In der Regel erfordern Elemente mit höherem Schweregrad die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="0244a-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="0244a-194">Einer der folgenden Werte: *Informational*, *Low*, \*Medium und *High*.</span><span class="sxs-lookup"><span data-stu-id="0244a-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="0244a-195">Mittel</span><span class="sxs-lookup"><span data-stu-id="0244a-195">Medium</span></span>
<span data-ttu-id="0244a-196">tags</span><span class="sxs-lookup"><span data-stu-id="0244a-196">tags</span></span> | <span data-ttu-id="0244a-197">Array von benutzerdefinierten Tags, die einem Vorfall zugeordnet sind, z. B. zum Kennzeichnen einer Gruppe von Vorfällen mit einem gemeinsamen Merkmal.</span><span class="sxs-lookup"><span data-stu-id="0244a-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="0244a-198">Kommentare</span><span class="sxs-lookup"><span data-stu-id="0244a-198">comments</span></span> | <span data-ttu-id="0244a-199">Array von Kommentaren, die von Secops bei der Verwaltung des Vorfalls erstellt werden, z. B. zusätzliche Informationen zur Klassifizierungsauswahl.</span><span class="sxs-lookup"><span data-stu-id="0244a-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="0244a-200">Warnungen</span><span class="sxs-lookup"><span data-stu-id="0244a-200">alerts</span></span> | <span data-ttu-id="0244a-201">Array, das alle Warnungen im Zusammenhang mit dem Vorfall sowie weitere Informationen enthält, z. B. schweregrad, Entitäten, die an der Warnung beteiligt waren, und die Quelle der Warnungen.</span><span class="sxs-lookup"><span data-stu-id="0244a-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="0244a-202">\[\] (Weitere Informationen zu Warnungsfeldern finden Sie weiter unten)</span><span class="sxs-lookup"><span data-stu-id="0244a-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="0244a-203">Benachrichtigungsmetadaten</span><span class="sxs-lookup"><span data-stu-id="0244a-203">Alerts metadata</span></span>

<span data-ttu-id="0244a-204">Feldname</span><span class="sxs-lookup"><span data-stu-id="0244a-204">Field name</span></span> | <span data-ttu-id="0244a-205">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0244a-205">Description</span></span> | <span data-ttu-id="0244a-206">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="0244a-206">Example value</span></span>
-|-|-
<span data-ttu-id="0244a-207">alertId</span><span class="sxs-lookup"><span data-stu-id="0244a-207">alertId</span></span> | <span data-ttu-id="0244a-208">Eindeutiger Bezeichner zur Darstellung der Warnung</span><span class="sxs-lookup"><span data-stu-id="0244a-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="0244a-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="0244a-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="0244a-210">incidentId</span><span class="sxs-lookup"><span data-stu-id="0244a-210">incidentId</span></span> | <span data-ttu-id="0244a-211">Eindeutiger Bezeichner zum Darstellen des Vorfalls, dem diese Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="0244a-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="0244a-212">924565</span><span class="sxs-lookup"><span data-stu-id="0244a-212">924565</span></span>
<span data-ttu-id="0244a-213">serviceSource</span><span class="sxs-lookup"><span data-stu-id="0244a-213">serviceSource</span></span> | <span data-ttu-id="0244a-214">Dienst, von dem die Warnung stammt, z. B. Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity oder Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="0244a-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="0244a-215">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="0244a-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="0244a-216">creationTime</span><span class="sxs-lookup"><span data-stu-id="0244a-216">creationTime</span></span> | <span data-ttu-id="0244a-217">Zeitpunkt, zu dem die Warnung zum ersten Mal erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="0244a-217">Time when alert was first created.</span></span> | <span data-ttu-id="0244a-218">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="0244a-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="0244a-219">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="0244a-219">lastUpdatedTime</span></span> | <span data-ttu-id="0244a-220">Zeitpunkt, zu dem die Warnung zuletzt im Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0244a-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="0244a-221">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="0244a-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="0244a-222">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="0244a-222">resolvedTime</span></span> | <span data-ttu-id="0244a-223">Zeitpunkt, zu dem die Warnung aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="0244a-223">Time when alert was resolved.</span></span> | <span data-ttu-id="0244a-224">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="0244a-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="0244a-225">firstActivity</span><span class="sxs-lookup"><span data-stu-id="0244a-225">firstActivity</span></span> | <span data-ttu-id="0244a-226">Zeitpunkt, zu dem die Benachrichtigung zum ersten Mal gemeldet hat, dass die Aktivität im Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0244a-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="0244a-227">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="0244a-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="0244a-228">title</span><span class="sxs-lookup"><span data-stu-id="0244a-228">title</span></span> | <span data-ttu-id="0244a-229">Kurzes Identifizieren des Zeichenfolgenwerts, der für jede Warnung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0244a-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="0244a-230">Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="0244a-230">Ransomware activity</span></span>
<span data-ttu-id="0244a-231">description</span><span class="sxs-lookup"><span data-stu-id="0244a-231">description</span></span> | <span data-ttu-id="0244a-232">Zeichenfolgenwert, der jede Warnung beschreibt.</span><span class="sxs-lookup"><span data-stu-id="0244a-232">String value describing each alert.</span></span> | <span data-ttu-id="0244a-233">Der Benutzer Test User2 (testUser2@contoso.com) bearbeitete 99 Dateien mit mehreren Erweiterungen, die mit der ungewöhnlichen Erweiterung *herunterladen endeten.*</span><span class="sxs-lookup"><span data-stu-id="0244a-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="0244a-234">Dies ist eine ungewöhnliche Anzahl von Dateimanipulationen und deutet auf einen potenziellen Ransomware-Angriff hin.</span><span class="sxs-lookup"><span data-stu-id="0244a-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="0244a-235">category</span><span class="sxs-lookup"><span data-stu-id="0244a-235">category</span></span> | <span data-ttu-id="0244a-236">Visuelle und numerische Ansicht, wie weit der Angriff entlang der Kill Chain schreitet.</span><span class="sxs-lookup"><span data-stu-id="0244a-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="0244a-237">Ausgerichtet am [MITRE ATT&CK™ Framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="0244a-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="0244a-238">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="0244a-238">Impact</span></span>
<span data-ttu-id="0244a-239">status</span><span class="sxs-lookup"><span data-stu-id="0244a-239">status</span></span> | <span data-ttu-id="0244a-240">Kategorisieren von Warnungen *(als Neu,* *Aktiv* oder *Aufgelöst*).</span><span class="sxs-lookup"><span data-stu-id="0244a-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="0244a-241">Es kann Ihnen helfen, Ihre Antwort auf Warnungen zu organisieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="0244a-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="0244a-242">Neu</span><span class="sxs-lookup"><span data-stu-id="0244a-242">New</span></span>
<span data-ttu-id="0244a-243">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="0244a-243">severity</span></span> | <span data-ttu-id="0244a-244">Gibt die möglichen Auswirkungen auf Ressourcen an.</span><span class="sxs-lookup"><span data-stu-id="0244a-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="0244a-245">Je höher der Schweregrad, desto größer sind die Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="0244a-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="0244a-246">In der Regel erfordern Elemente mit höherem Schweregrad die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="0244a-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="0244a-247">Einer der folgenden Werte: *Informational*, *Low*, \*Medium und *High*.</span><span class="sxs-lookup"><span data-stu-id="0244a-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="0244a-248">Mittel</span><span class="sxs-lookup"><span data-stu-id="0244a-248">Medium</span></span>
<span data-ttu-id="0244a-249">investigationId</span><span class="sxs-lookup"><span data-stu-id="0244a-249">investigationId</span></span> | <span data-ttu-id="0244a-250">Die durch diese Warnung ausgelöste automatische Untersuchungs-ID.</span><span class="sxs-lookup"><span data-stu-id="0244a-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="0244a-251">1234</span><span class="sxs-lookup"><span data-stu-id="0244a-251">1234</span></span>
<span data-ttu-id="0244a-252">investigationState</span><span class="sxs-lookup"><span data-stu-id="0244a-252">investigationState</span></span> | <span data-ttu-id="0244a-253">Informationen zum aktuellen Status der Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="0244a-253">Information on the investigation's current status.</span></span> <span data-ttu-id="0244a-254">Einer der folgenden Werte: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="0244a-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="0244a-255">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="0244a-255">UnsupportedAlertType</span></span>
<span data-ttu-id="0244a-256">classification</span><span class="sxs-lookup"><span data-stu-id="0244a-256">classification</span></span> | <span data-ttu-id="0244a-257">Die Spezifikation für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="0244a-257">The specification for the incident.</span></span> <span data-ttu-id="0244a-258">Die Eigenschaftswerte sind: *Unknown*, *FalsePositive*, *TruePositive* oder *Null*</span><span class="sxs-lookup"><span data-stu-id="0244a-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="0244a-259">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="0244a-259">Unknown</span></span>
<span data-ttu-id="0244a-260">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="0244a-260">determination</span></span> | <span data-ttu-id="0244a-261">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="0244a-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="0244a-262">Die Eigenschaftswerte sind: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* oder  *Null*</span><span class="sxs-lookup"><span data-stu-id="0244a-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="0244a-263">Apt</span><span class="sxs-lookup"><span data-stu-id="0244a-263">Apt</span></span>
<span data-ttu-id="0244a-264">assignedTo</span><span class="sxs-lookup"><span data-stu-id="0244a-264">assignedTo</span></span> | <span data-ttu-id="0244a-265">Besitzer des Vorfalls oder *null,* wenn kein Besitzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0244a-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="0244a-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0244a-266">secop2@contoso.com</span></span>
<span data-ttu-id="0244a-267">actorName</span><span class="sxs-lookup"><span data-stu-id="0244a-267">actorName</span></span> | <span data-ttu-id="0244a-268">Die Aktivitätsgruppe, falls die dieser Warnung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0244a-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="0244a-269">BORON</span><span class="sxs-lookup"><span data-stu-id="0244a-269">BORON</span></span>
<span data-ttu-id="0244a-270">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="0244a-270">threatFamilyName</span></span> | <span data-ttu-id="0244a-271">Dieser Warnung zugeordnete Bedrohungsfamilie.</span><span class="sxs-lookup"><span data-stu-id="0244a-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="0244a-272">null</span><span class="sxs-lookup"><span data-stu-id="0244a-272">null</span></span>
<span data-ttu-id="0244a-273">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="0244a-273">mitreTechniques</span></span> | <span data-ttu-id="0244a-274">Die Angriffstechniken, die mit [dem MITRE ATT-&CK](https://attack.mitre.org/)™ werden.</span><span class="sxs-lookup"><span data-stu-id="0244a-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="0244a-275">Geräte</span><span class="sxs-lookup"><span data-stu-id="0244a-275">devices</span></span> | <span data-ttu-id="0244a-276">Alle Geräte, auf denen Warnungen im Zusammenhang mit dem Vorfall gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="0244a-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="0244a-277">\[\] (Weitere Informationen zu Entitätsfeldern finden Sie weiter unten)</span><span class="sxs-lookup"><span data-stu-id="0244a-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="0244a-278">Geräteformat</span><span class="sxs-lookup"><span data-stu-id="0244a-278">Device format</span></span>

<span data-ttu-id="0244a-279">Feldname</span><span class="sxs-lookup"><span data-stu-id="0244a-279">Field name</span></span> | <span data-ttu-id="0244a-280">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0244a-280">Description</span></span> | <span data-ttu-id="0244a-281">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="0244a-281">Example value</span></span>
-|-|-
<span data-ttu-id="0244a-282">DeviceId</span><span class="sxs-lookup"><span data-stu-id="0244a-282">DeviceId</span></span> | <span data-ttu-id="0244a-283">Die Geräte-ID, die in Microsoft Defender for Endpoint festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0244a-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="0244a-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="0244a-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="0244a-285">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="0244a-285">aadDeviceId</span></span> |  <span data-ttu-id="0244a-286">Die Geräte-ID, wie in [Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="0244a-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="0244a-287">Nur für Geräte verfügbar, die der Domäne beigetreten sind.</span><span class="sxs-lookup"><span data-stu-id="0244a-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="0244a-288">null</span><span class="sxs-lookup"><span data-stu-id="0244a-288">null</span></span>
<span data-ttu-id="0244a-289">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="0244a-289">deviceDnsName</span></span> | <span data-ttu-id="0244a-290">Der vollqualifizierte Domänenname für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="0244a-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="0244a-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0244a-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="0244a-292">osPlatform</span><span class="sxs-lookup"><span data-stu-id="0244a-292">osPlatform</span></span> | <span data-ttu-id="0244a-293">Die Betriebssystemplattform, auf der das Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0244a-293">The OS platform the device is running.</span></span>| <span data-ttu-id="0244a-294">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="0244a-294">WindowsServer2016</span></span>
<span data-ttu-id="0244a-295">osBuild</span><span class="sxs-lookup"><span data-stu-id="0244a-295">osBuild</span></span> | <span data-ttu-id="0244a-296">Die Buildversion für das Betriebssystem, auf dem das Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0244a-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="0244a-297">14393</span><span class="sxs-lookup"><span data-stu-id="0244a-297">14393</span></span>
<span data-ttu-id="0244a-298">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="0244a-298">rbacGroupName</span></span> | <span data-ttu-id="0244a-299">Die [dem Gerät](/azure/role-based-access-control/overview) zugeordnete rollenbasierte Zugriffssteuerungsgruppe (RBAC).</span><span class="sxs-lookup"><span data-stu-id="0244a-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="0244a-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="0244a-300">WDATP-Ring0</span></span>
<span data-ttu-id="0244a-301">firstSeen</span><span class="sxs-lookup"><span data-stu-id="0244a-301">firstSeen</span></span> | <span data-ttu-id="0244a-302">Zeitpunkt, zu dem das Gerät zum ersten Mal angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="0244a-302">Time when device was first seen.</span></span> | <span data-ttu-id="0244a-303">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="0244a-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="0244a-304">healthStatus</span><span class="sxs-lookup"><span data-stu-id="0244a-304">healthStatus</span></span> | <span data-ttu-id="0244a-305">Der Integritätsstatus des Geräts.</span><span class="sxs-lookup"><span data-stu-id="0244a-305">The health state of the device.</span></span> | <span data-ttu-id="0244a-306">Aktiv</span><span class="sxs-lookup"><span data-stu-id="0244a-306">Active</span></span>
<span data-ttu-id="0244a-307">riskScore</span><span class="sxs-lookup"><span data-stu-id="0244a-307">riskScore</span></span> | <span data-ttu-id="0244a-308">Die Risikosentwertung für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="0244a-308">The risk score for the  device.</span></span> | <span data-ttu-id="0244a-309">Hoch</span><span class="sxs-lookup"><span data-stu-id="0244a-309">High</span></span>
<span data-ttu-id="0244a-310">Entitäten</span><span class="sxs-lookup"><span data-stu-id="0244a-310">entities</span></span> | <span data-ttu-id="0244a-311">Alle Entitäten, die als Teil oder verwandt mit einer bestimmten Warnung identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="0244a-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="0244a-312">\[\] (Weitere Informationen zu Entitätsfeldern finden Sie weiter unten)</span><span class="sxs-lookup"><span data-stu-id="0244a-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="0244a-313">Entitätsformat</span><span class="sxs-lookup"><span data-stu-id="0244a-313">Entity Format</span></span>

<span data-ttu-id="0244a-314">Feldname</span><span class="sxs-lookup"><span data-stu-id="0244a-314">Field name</span></span> | <span data-ttu-id="0244a-315">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0244a-315">Description</span></span> | <span data-ttu-id="0244a-316">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="0244a-316">Example value</span></span>
-|-|-
<span data-ttu-id="0244a-317">entityType</span><span class="sxs-lookup"><span data-stu-id="0244a-317">entityType</span></span> | <span data-ttu-id="0244a-318">Entitäten, die als Teil oder verwandt mit einer bestimmten Warnung identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="0244a-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="0244a-319">Die Eigenschaftenwerte sind: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span><span class="sxs-lookup"><span data-stu-id="0244a-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="0244a-320">Benutzer</span><span class="sxs-lookup"><span data-stu-id="0244a-320">User</span></span>
<span data-ttu-id="0244a-321">sha1</span><span class="sxs-lookup"><span data-stu-id="0244a-321">sha1</span></span> | <span data-ttu-id="0244a-322">Verfügbar, wenn entityType File *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="0244a-323">Der Dateihash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0244a-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="0244a-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="0244a-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="0244a-325">sha256</span><span class="sxs-lookup"><span data-stu-id="0244a-325">sha256</span></span> | <span data-ttu-id="0244a-326">Verfügbar, wenn entityType File *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="0244a-327">Der Dateihash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0244a-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="0244a-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="0244a-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="0244a-329">fileName</span><span class="sxs-lookup"><span data-stu-id="0244a-329">fileName</span></span> | <span data-ttu-id="0244a-330">Verfügbar, wenn entityType File *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="0244a-331">Der Dateiname für Warnungen, die einer Datei oder einem Prozess zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="0244a-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="0244a-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="0244a-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="0244a-333">filePath</span><span class="sxs-lookup"><span data-stu-id="0244a-333">filePath</span></span> | <span data-ttu-id="0244a-334">Verfügbar, wenn entityType File *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="0244a-335">Der Dateipfad für Warnungen, die einer Datei oder einem Prozess zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="0244a-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="0244a-336">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="0244a-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="0244a-337">processId</span><span class="sxs-lookup"><span data-stu-id="0244a-337">processId</span></span> | <span data-ttu-id="0244a-338">Verfügbar, wenn entityType Process *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="0244a-339">24348</span><span class="sxs-lookup"><span data-stu-id="0244a-339">24348</span></span>
<span data-ttu-id="0244a-340">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="0244a-340">processCommandLine</span></span> | <span data-ttu-id="0244a-341">Verfügbar, wenn entityType Process *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="0244a-342">"Ihre Datei kann heruntergeladen \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="0244a-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="0244a-343">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="0244a-343">processCreationTime</span></span> | <span data-ttu-id="0244a-344">Verfügbar, wenn entityType Process *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="0244a-345">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="0244a-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="0244a-346">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="0244a-346">parentProcessId</span></span> | <span data-ttu-id="0244a-347">Verfügbar, wenn entityType Process *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="0244a-348">16840</span><span class="sxs-lookup"><span data-stu-id="0244a-348">16840</span></span>
<span data-ttu-id="0244a-349">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="0244a-349">parentProcessCreationTime</span></span> | <span data-ttu-id="0244a-350">Verfügbar, wenn entityType Process *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="0244a-351">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="0244a-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="0244a-352">ipAddress</span><span class="sxs-lookup"><span data-stu-id="0244a-352">ipAddress</span></span> | <span data-ttu-id="0244a-353">Verfügbar, wenn entityType ip *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="0244a-354">IP-Adresse für Warnungen im Zusammenhang mit Netzwerkereignissen, z. *B. Kommunikation mit einem schädlichen Netzwerkziel.*</span><span class="sxs-lookup"><span data-stu-id="0244a-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="0244a-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="0244a-355">62.216.203.204</span></span>
<span data-ttu-id="0244a-356">url</span><span class="sxs-lookup"><span data-stu-id="0244a-356">url</span></span> | <span data-ttu-id="0244a-357">Verfügbar, wenn entityType url *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="0244a-358">URL für Warnungen im Zusammenhang mit Netzwerkereignissen, z. *B. Kommunikation mit einem zielschädlichen Netzwerk.*</span><span class="sxs-lookup"><span data-stu-id="0244a-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="0244a-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="0244a-359">down.esales360.cn</span></span>
<span data-ttu-id="0244a-360">accountName</span><span class="sxs-lookup"><span data-stu-id="0244a-360">accountName</span></span> | <span data-ttu-id="0244a-361">Verfügbar, wenn entityType User *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="0244a-362">testUser2</span><span class="sxs-lookup"><span data-stu-id="0244a-362">testUser2</span></span>
<span data-ttu-id="0244a-363">Domänname</span><span class="sxs-lookup"><span data-stu-id="0244a-363">domainName</span></span> | <span data-ttu-id="0244a-364">Verfügbar, wenn entityType User *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="0244a-365">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="0244a-365">europe.corp.contoso</span></span>
<span data-ttu-id="0244a-366">userSid</span><span class="sxs-lookup"><span data-stu-id="0244a-366">userSid</span></span> | <span data-ttu-id="0244a-367">Verfügbar, wenn entityType User *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="0244a-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="0244a-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="0244a-369">aadUserId</span><span class="sxs-lookup"><span data-stu-id="0244a-369">aadUserId</span></span> | <span data-ttu-id="0244a-370">Verfügbar, wenn entityType User *ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="0244a-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="0244a-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="0244a-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="0244a-372">userPrincipalName</span></span> | <span data-ttu-id="0244a-373">Verfügbar, wenn entityType *User* / *MailBox* / *MailMessage ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="0244a-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0244a-374">testUser2@contoso.com</span></span>
<span data-ttu-id="0244a-375">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="0244a-375">mailboxDisplayName</span></span> | <span data-ttu-id="0244a-376">Verfügbar, wenn entityType *MailBox ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="0244a-377">Testen von User2</span><span class="sxs-lookup"><span data-stu-id="0244a-377">test User2</span></span>
<span data-ttu-id="0244a-378">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="0244a-378">mailboxAddress</span></span> | <span data-ttu-id="0244a-379">Verfügbar, wenn entityType *User* / *MailBox* / *MailMessage ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="0244a-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0244a-380">testUser2@contoso.com</span></span>
<span data-ttu-id="0244a-381">clusterBy</span><span class="sxs-lookup"><span data-stu-id="0244a-381">clusterBy</span></span> | <span data-ttu-id="0244a-382">Verfügbar, wenn entityType *MailCluster ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="0244a-383">Betreff; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="0244a-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="0244a-384">sender</span><span class="sxs-lookup"><span data-stu-id="0244a-384">sender</span></span> | <span data-ttu-id="0244a-385">Verfügbar, wenn entityType *User* / *MailBox* / *MailMessage ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="0244a-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="0244a-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="0244a-387">recipient</span><span class="sxs-lookup"><span data-stu-id="0244a-387">recipient</span></span> | <span data-ttu-id="0244a-388">Verfügbar, wenn entityType *MailMessage ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="0244a-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0244a-389">testUser2@contoso.com</span></span>
<span data-ttu-id="0244a-390">subject</span><span class="sxs-lookup"><span data-stu-id="0244a-390">subject</span></span> | <span data-ttu-id="0244a-391">Verfügbar, wenn entityType *MailMessage ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="0244a-392">\[EXTERNE \] Aufmerksamkeit</span><span class="sxs-lookup"><span data-stu-id="0244a-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="0244a-393">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="0244a-393">deliveryAction</span></span> | <span data-ttu-id="0244a-394">Verfügbar, wenn entityType *MailMessage ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="0244a-395">Zugestellt</span><span class="sxs-lookup"><span data-stu-id="0244a-395">Delivered</span></span>
<span data-ttu-id="0244a-396">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="0244a-396">securityGroupId</span></span> | <span data-ttu-id="0244a-397">Verfügbar, wenn entityType *SecurityGroup ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="0244a-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="0244a-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="0244a-399">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="0244a-399">securityGroupName</span></span> | <span data-ttu-id="0244a-400">Verfügbar, wenn entityType *SecurityGroup ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="0244a-401">Netzwerkkonfigurationsoperatoren</span><span class="sxs-lookup"><span data-stu-id="0244a-401">Network Configuration Operators</span></span>
<span data-ttu-id="0244a-402">registryHive</span><span class="sxs-lookup"><span data-stu-id="0244a-402">registryHive</span></span> | <span data-ttu-id="0244a-403">Verfügbar, wenn entityType die *Registrierung ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="0244a-404">LOKALER \_ \_ HKEY-COMPUTER</span><span class="sxs-lookup"><span data-stu-id="0244a-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="0244a-405">registryKey</span><span class="sxs-lookup"><span data-stu-id="0244a-405">registryKey</span></span> | <span data-ttu-id="0244a-406">Verfügbar, wenn entityType die *Registrierung ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="0244a-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="0244a-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="0244a-408">registryValueType</span><span class="sxs-lookup"><span data-stu-id="0244a-408">registryValueType</span></span> | <span data-ttu-id="0244a-409">Verfügbar, wenn entityType die *Registrierung ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="0244a-410">String</span><span class="sxs-lookup"><span data-stu-id="0244a-410">String</span></span>
<span data-ttu-id="0244a-411">registryValue</span><span class="sxs-lookup"><span data-stu-id="0244a-411">registryValue</span></span> | <span data-ttu-id="0244a-412">Verfügbar, wenn entityType die *Registrierung ist.*</span><span class="sxs-lookup"><span data-stu-id="0244a-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="0244a-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="0244a-413">31-00-00-00</span></span>
<span data-ttu-id="0244a-414">deviceId</span><span class="sxs-lookup"><span data-stu-id="0244a-414">deviceId</span></span> | <span data-ttu-id="0244a-415">Die ID des Geräts, das sich auf die Entität bezogen hat.</span><span class="sxs-lookup"><span data-stu-id="0244a-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="0244a-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="0244a-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="0244a-417">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0244a-417">Example</span></span>

<span data-ttu-id="0244a-418">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="0244a-418">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="0244a-419">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="0244a-419">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="0244a-420">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="0244a-420">Related articles</span></span>

- [<span data-ttu-id="0244a-421">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="0244a-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="0244a-422">Informationen zu API-Beschränkungen und -Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="0244a-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="0244a-423">Verstehen von Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="0244a-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="0244a-424">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="0244a-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="0244a-425">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="0244a-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="0244a-426">Aktualisieren der Vorfall-API</span><span class="sxs-lookup"><span data-stu-id="0244a-426">Update incident API</span></span>](api-update-incidents.md)

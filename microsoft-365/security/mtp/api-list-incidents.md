---
title: Api zum Auflisten von Vorfällen in Microsoft 365 Defender
description: Erfahren Sie, wie Sie Vorfälle in Microsoft 365 Defender auflisten
keywords: Liste, Vorfall, Vorfälle, API
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 39a170a1845ab33f67d77b2de3d5f298f67fdc99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932070"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="c435a-104">Api zum Auflisten von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c435a-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c435a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c435a-105">**Applies to:**</span></span>

- <span data-ttu-id="c435a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c435a-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c435a-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="c435a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c435a-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="c435a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="c435a-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c435a-109">API description</span></span>

<span data-ttu-id="c435a-110">Mit der API für Listenvorfälle können Sie Vorfälle sortieren, um eine informierte Reaktion auf die Cybersicherheit zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c435a-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="c435a-111">Es macht eine Sammlung von Vorfällen verfügbar, die in Ihrem Netzwerk innerhalb des von Ihnen in ihrer Umgebungsaufbewahrungsrichtlinie angegebenen Zeitbereichs gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="c435a-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="c435a-112">Die neuesten Vorfälle werden am Anfang der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c435a-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="c435a-113">Jeder Vorfall enthält ein Array verwandter Warnungen und deren zugehörige Entitäten.</span><span class="sxs-lookup"><span data-stu-id="c435a-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="c435a-114">Die API unterstützt die folgenden **OData-Operatoren:**</span><span class="sxs-lookup"><span data-stu-id="c435a-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="c435a-115">`$filter`für `lastUpdateTime` die `createdTime` Eigenschaften , , `status` und `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="c435a-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="c435a-116">`$top`, mit einem Maximalwert von **100**</span><span class="sxs-lookup"><span data-stu-id="c435a-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="c435a-117">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c435a-117">Limitations</span></span>

1. <span data-ttu-id="c435a-118">Die maximale Seitengröße beträgt **100 Vorfälle.**</span><span class="sxs-lookup"><span data-stu-id="c435a-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="c435a-119">Die maximale Rate von Anforderungen beträgt **50 Anrufe pro Minute** und **1.500 Anrufe pro Stunde.**</span><span class="sxs-lookup"><span data-stu-id="c435a-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="c435a-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c435a-120">Permissions</span></span>

<span data-ttu-id="c435a-121">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c435a-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c435a-122">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access Microsoft 365 Defender APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="c435a-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="c435a-123">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="c435a-123">Permission type</span></span> | <span data-ttu-id="c435a-124">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c435a-124">Permission</span></span> | <span data-ttu-id="c435a-125">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c435a-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="c435a-126">Anwendung</span><span class="sxs-lookup"><span data-stu-id="c435a-126">Application</span></span> | <span data-ttu-id="c435a-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="c435a-127">Incident.Read.All</span></span> | <span data-ttu-id="c435a-128">Alle Vorfälle lesen</span><span class="sxs-lookup"><span data-stu-id="c435a-128">Read all incidents</span></span>
<span data-ttu-id="c435a-129">Anwendung</span><span class="sxs-lookup"><span data-stu-id="c435a-129">Application</span></span> | <span data-ttu-id="c435a-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c435a-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="c435a-131">Lesen und Schreiben aller Vorfälle</span><span class="sxs-lookup"><span data-stu-id="c435a-131">Read and write all incidents</span></span>
<span data-ttu-id="c435a-132">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="c435a-132">Delegated (work or school account)</span></span> | <span data-ttu-id="c435a-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="c435a-133">Incident.Read</span></span> | <span data-ttu-id="c435a-134">Lesen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="c435a-134">Read incidents</span></span>
<span data-ttu-id="c435a-135">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="c435a-135">Delegated (work or school account)</span></span> | <span data-ttu-id="c435a-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c435a-136">Incident.ReadWrite</span></span> | <span data-ttu-id="c435a-137">Lese- und Schreibzugriff auf Vorfälle</span><span class="sxs-lookup"><span data-stu-id="c435a-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="c435a-138">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="c435a-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="c435a-139">Der Benutzer muss über die Berechtigung zum Anzeigen von Vorfällen im Portal verfügen.</span><span class="sxs-lookup"><span data-stu-id="c435a-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="c435a-140">Die Antwort enthält nur Vorfälle, für die der Benutzer offengelegt wird.</span><span class="sxs-lookup"><span data-stu-id="c435a-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="c435a-141">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="c435a-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="c435a-142">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="c435a-142">Request headers</span></span>

<span data-ttu-id="c435a-143">Name</span><span class="sxs-lookup"><span data-stu-id="c435a-143">Name</span></span> | <span data-ttu-id="c435a-144">Typ</span><span class="sxs-lookup"><span data-stu-id="c435a-144">Type</span></span> | <span data-ttu-id="c435a-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c435a-145">Description</span></span>
-|-|-
<span data-ttu-id="c435a-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="c435a-146">Authorization</span></span> | <span data-ttu-id="c435a-147">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c435a-147">String</span></span> | <span data-ttu-id="c435a-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c435a-148">Bearer {token}.</span></span> <span data-ttu-id="c435a-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="c435a-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="c435a-150">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="c435a-150">Request body</span></span>

<span data-ttu-id="c435a-151">Keine</span><span class="sxs-lookup"><span data-stu-id="c435a-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="c435a-152">Antwort</span><span class="sxs-lookup"><span data-stu-id="c435a-152">Response</span></span>

<span data-ttu-id="c435a-153">Wenn die Methode erfolgreich ist, werden eine Liste der Vorfälle `200 OK` [im](api-incident.md) Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c435a-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="c435a-154">Schemazuordnung</span><span class="sxs-lookup"><span data-stu-id="c435a-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="c435a-155">Metadaten für Vorfälle</span><span class="sxs-lookup"><span data-stu-id="c435a-155">Incident metadata</span></span>

<span data-ttu-id="c435a-156">Feldname</span><span class="sxs-lookup"><span data-stu-id="c435a-156">Field name</span></span> | <span data-ttu-id="c435a-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c435a-157">Description</span></span> | <span data-ttu-id="c435a-158">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="c435a-158">Example value</span></span>
-|-|-
<span data-ttu-id="c435a-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="c435a-159">incidentId</span></span> | <span data-ttu-id="c435a-160">Eindeutiger Bezeichner für den Vorfall</span><span class="sxs-lookup"><span data-stu-id="c435a-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="c435a-161">924565</span><span class="sxs-lookup"><span data-stu-id="c435a-161">924565</span></span>
<span data-ttu-id="c435a-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="c435a-162">redirectIncidentId</span></span> | <span data-ttu-id="c435a-163">Nur ausgefüllt, wenn ein Vorfall im Rahmen der Vorfallverarbeitungslogik mit einem anderen Vorfall zusammenged?nert wird.</span><span class="sxs-lookup"><span data-stu-id="c435a-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="c435a-164">924569</span><span class="sxs-lookup"><span data-stu-id="c435a-164">924569</span></span>
<span data-ttu-id="c435a-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="c435a-165">incidentName</span></span> | <span data-ttu-id="c435a-166">Zeichenfolgenwert, der für jeden Vorfall verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c435a-166">String value available for every incident.</span></span> | <span data-ttu-id="c435a-167">Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="c435a-167">Ransomware activity</span></span>
<span data-ttu-id="c435a-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="c435a-168">createdTime</span></span> | <span data-ttu-id="c435a-169">Zeitpunkt, zu dem der Vorfall zum ersten Mal erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c435a-169">Time when incident was first created.</span></span> | <span data-ttu-id="c435a-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="c435a-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="c435a-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="c435a-171">lastUpdateTime</span></span> | <span data-ttu-id="c435a-172">Zeitpunkt, zu dem der Vorfall zuletzt im Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c435a-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="c435a-173">Dieses Feld kann verwendet werden, wenn Sie den Anforderungsparameter für den Zeitraum festlegen, für den Vorfälle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c435a-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="c435a-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="c435a-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="c435a-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="c435a-175">assignedTo</span></span> | <span data-ttu-id="c435a-176">Besitzer des Vorfalls oder *NULL,* wenn kein Besitzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c435a-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="c435a-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c435a-177">secop2@contoso.com</span></span>
<span data-ttu-id="c435a-178">classification</span><span class="sxs-lookup"><span data-stu-id="c435a-178">classification</span></span> | <span data-ttu-id="c435a-179">Die Spezifikation für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="c435a-179">The specification for the incident.</span></span> <span data-ttu-id="c435a-180">Die Eigenschaftswerte sind: *Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="c435a-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="c435a-181">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="c435a-181">Unknown</span></span>
<span data-ttu-id="c435a-182">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="c435a-182">determination</span></span> | <span data-ttu-id="c435a-183">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="c435a-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="c435a-184">Die Eigenschaftswerte sind: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span><span class="sxs-lookup"><span data-stu-id="c435a-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="c435a-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="c435a-185">NotAvailable</span></span>
<span data-ttu-id="c435a-186">status</span><span class="sxs-lookup"><span data-stu-id="c435a-186">status</span></span> | <span data-ttu-id="c435a-187">Kategorisieren von Vorfällen *(als "Aktiv"* oder *"Gelöst").*</span><span class="sxs-lookup"><span data-stu-id="c435a-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="c435a-188">Es kann Ihnen helfen, Ihre Reaktion auf Vorfälle zu organisieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c435a-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="c435a-189">Aktiv</span><span class="sxs-lookup"><span data-stu-id="c435a-189">Active</span></span>
<span data-ttu-id="c435a-190">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="c435a-190">severity</span></span> | <span data-ttu-id="c435a-191">Gibt die möglichen Auswirkungen auf Ressourcen an.</span><span class="sxs-lookup"><span data-stu-id="c435a-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="c435a-192">Je höher der Schweregrad, desto größer sind die Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="c435a-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="c435a-193">Elemente mit einem höheren Schweregrad erfordern in der Regel die direkteste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="c435a-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="c435a-194">Einer der folgenden Werte: *Informational*, *Low*, \*Medium und *High*.</span><span class="sxs-lookup"><span data-stu-id="c435a-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="c435a-195">Mittel</span><span class="sxs-lookup"><span data-stu-id="c435a-195">Medium</span></span>
<span data-ttu-id="c435a-196">tags</span><span class="sxs-lookup"><span data-stu-id="c435a-196">tags</span></span> | <span data-ttu-id="c435a-197">Array von benutzerdefinierten Tags, die einem Vorfall zugeordnet sind, z. B. um eine Gruppe von Vorfällen mit einem gemeinsamen Merkmal zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="c435a-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="c435a-198">Warnungen</span><span class="sxs-lookup"><span data-stu-id="c435a-198">alerts</span></span> | <span data-ttu-id="c435a-199">Array, das alle Warnungen im Zusammenhang mit dem Vorfall sowie weitere Informationen enthält, z. B. Schweregrad, Entitäten, die an der Warnung beteiligt waren, und die Quelle der Warnungen.</span><span class="sxs-lookup"><span data-stu-id="c435a-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="c435a-200">\[\] (Details zu Warnungsfeldern finden Sie weiter unten))</span><span class="sxs-lookup"><span data-stu-id="c435a-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="c435a-201">Warnungsmetadaten</span><span class="sxs-lookup"><span data-stu-id="c435a-201">Alerts metadata</span></span>

<span data-ttu-id="c435a-202">Feldname</span><span class="sxs-lookup"><span data-stu-id="c435a-202">Field name</span></span> | <span data-ttu-id="c435a-203">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c435a-203">Description</span></span> | <span data-ttu-id="c435a-204">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="c435a-204">Example value</span></span>
-|-|-
<span data-ttu-id="c435a-205">alertId</span><span class="sxs-lookup"><span data-stu-id="c435a-205">alertId</span></span> | <span data-ttu-id="c435a-206">Eindeutiger Bezeichner zur Darstellung der Warnung</span><span class="sxs-lookup"><span data-stu-id="c435a-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="c435a-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="c435a-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="c435a-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="c435a-208">incidentId</span></span> | <span data-ttu-id="c435a-209">Eindeutige ID zur Darstellung des Vorfalls, dem diese Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="c435a-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="c435a-210">924565</span><span class="sxs-lookup"><span data-stu-id="c435a-210">924565</span></span>
<span data-ttu-id="c435a-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="c435a-211">serviceSource</span></span> | <span data-ttu-id="c435a-212">Dienst, von dem die Warnung stammt, z. B. Microsoft Defender für Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity oder Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="c435a-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="c435a-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="c435a-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="c435a-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="c435a-214">creationTime</span></span> | <span data-ttu-id="c435a-215">Zeitpunkt, zu dem die Warnung zum ersten Mal erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c435a-215">Time when alert was first created.</span></span> | <span data-ttu-id="c435a-216">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="c435a-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="c435a-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="c435a-217">lastUpdatedTime</span></span> | <span data-ttu-id="c435a-218">Zeitpunkt, zu dem die Warnung zuletzt im Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c435a-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="c435a-219">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="c435a-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="c435a-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="c435a-220">resolvedTime</span></span> | <span data-ttu-id="c435a-221">Zeitpunkt, zu dem die Warnung aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="c435a-221">Time when alert was resolved.</span></span> | <span data-ttu-id="c435a-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="c435a-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="c435a-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="c435a-223">firstActivity</span></span> | <span data-ttu-id="c435a-224">Zeitpunkt, zu dem die Warnung erstmals gemeldet hat, dass die Aktivität im Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c435a-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="c435a-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="c435a-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="c435a-226">title</span><span class="sxs-lookup"><span data-stu-id="c435a-226">title</span></span> | <span data-ttu-id="c435a-227">Kurzes Identifizieren des Zeichenfolgenwerts, der für jede Warnung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c435a-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="c435a-228">Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="c435a-228">Ransomware activity</span></span>
<span data-ttu-id="c435a-229">description</span><span class="sxs-lookup"><span data-stu-id="c435a-229">description</span></span> | <span data-ttu-id="c435a-230">Zeichenfolgenwert, der jede Warnung beschreibt.</span><span class="sxs-lookup"><span data-stu-id="c435a-230">String value describing each alert.</span></span> | <span data-ttu-id="c435a-231">Der Benutzer Test User2 (testUser2@contoso.com) hat 99 Dateien mit mehreren Erweiterungen bearbeitet, die mit der ungewöhnlichen Erweiterung *"herunterladen" enden.*</span><span class="sxs-lookup"><span data-stu-id="c435a-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="c435a-232">Dies ist eine ungewöhnliche Anzahl von Dateimanipulationen und ein Hinweis auf einen potenziellen Ransomware-Angriff.</span><span class="sxs-lookup"><span data-stu-id="c435a-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="c435a-233">category</span><span class="sxs-lookup"><span data-stu-id="c435a-233">category</span></span> | <span data-ttu-id="c435a-234">Visuelle und numerische Ansicht, wie weit der Angriff entlang der Kill Chain schreitet.</span><span class="sxs-lookup"><span data-stu-id="c435a-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="c435a-235">Ausgerichtet am [MITRE ATT&CK™ Framework.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="c435a-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="c435a-236">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="c435a-236">Impact</span></span>
<span data-ttu-id="c435a-237">status</span><span class="sxs-lookup"><span data-stu-id="c435a-237">status</span></span> | <span data-ttu-id="c435a-238">Kategorisieren von Warnungen *(als "Neu",* *"Aktiv"* oder *"Gelöst").*</span><span class="sxs-lookup"><span data-stu-id="c435a-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="c435a-239">Es kann Ihnen helfen, Ihre Antwort auf Warnungen zu organisieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c435a-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="c435a-240">Neu</span><span class="sxs-lookup"><span data-stu-id="c435a-240">New</span></span>
<span data-ttu-id="c435a-241">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="c435a-241">severity</span></span> | <span data-ttu-id="c435a-242">Gibt die möglichen Auswirkungen auf Ressourcen an.</span><span class="sxs-lookup"><span data-stu-id="c435a-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="c435a-243">Je höher der Schweregrad, desto größer sind die Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="c435a-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="c435a-244">Elemente mit einem höheren Schweregrad erfordern in der Regel die direkteste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="c435a-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="c435a-245">Einer der folgenden Werte: *Informational*, *Low*, \*Medium und *High*.</span><span class="sxs-lookup"><span data-stu-id="c435a-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="c435a-246">Mittel</span><span class="sxs-lookup"><span data-stu-id="c435a-246">Medium</span></span>
<span data-ttu-id="c435a-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="c435a-247">investigationId</span></span> | <span data-ttu-id="c435a-248">Die durch diese Warnung ausgelöste automatisierte Untersuchungs-ID.</span><span class="sxs-lookup"><span data-stu-id="c435a-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="c435a-249">1234</span><span class="sxs-lookup"><span data-stu-id="c435a-249">1234</span></span>
<span data-ttu-id="c435a-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="c435a-250">investigationState</span></span> | <span data-ttu-id="c435a-251">Informationen zum aktuellen Status der Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="c435a-251">Information on the investigation's current status.</span></span> <span data-ttu-id="c435a-252">Einer der folgenden Werte: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="c435a-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="c435a-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="c435a-253">UnsupportedAlertType</span></span>
<span data-ttu-id="c435a-254">classification</span><span class="sxs-lookup"><span data-stu-id="c435a-254">classification</span></span> | <span data-ttu-id="c435a-255">Die Spezifikation für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="c435a-255">The specification for the incident.</span></span> <span data-ttu-id="c435a-256">Die Eigenschaftswerte sind: *Unknown*, *FalsePositive*, *TruePositive* oder *NULL*</span><span class="sxs-lookup"><span data-stu-id="c435a-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="c435a-257">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="c435a-257">Unknown</span></span>
<span data-ttu-id="c435a-258">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="c435a-258">determination</span></span> | <span data-ttu-id="c435a-259">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="c435a-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="c435a-260">Die Eigenschaftswerte sind: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* oder  *NULL*</span><span class="sxs-lookup"><span data-stu-id="c435a-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="c435a-261">Apt</span><span class="sxs-lookup"><span data-stu-id="c435a-261">Apt</span></span>
<span data-ttu-id="c435a-262">assignedTo</span><span class="sxs-lookup"><span data-stu-id="c435a-262">assignedTo</span></span> | <span data-ttu-id="c435a-263">Besitzer des Vorfalls oder *NULL,* wenn kein Besitzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c435a-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="c435a-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c435a-264">secop2@contoso.com</span></span>
<span data-ttu-id="c435a-265">actorName</span><span class="sxs-lookup"><span data-stu-id="c435a-265">actorName</span></span> | <span data-ttu-id="c435a-266">Die Aktivitätsgruppe, falls dies der Fall ist, die dieser Warnung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c435a-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="c435a-267">BORON</span><span class="sxs-lookup"><span data-stu-id="c435a-267">BORON</span></span>
<span data-ttu-id="c435a-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="c435a-268">threatFamilyName</span></span> | <span data-ttu-id="c435a-269">Dieser Warnung zugeordnete Bedrohungsfamilie.</span><span class="sxs-lookup"><span data-stu-id="c435a-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="c435a-270">null</span><span class="sxs-lookup"><span data-stu-id="c435a-270">null</span></span>
<span data-ttu-id="c435a-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="c435a-271">mitreTechniques</span></span> | <span data-ttu-id="c435a-272">Die Angriffstechniken, wie in der [MitRE ATT-&CK-™](https://attack.mitre.org/)sind.</span><span class="sxs-lookup"><span data-stu-id="c435a-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="c435a-273">Geräte</span><span class="sxs-lookup"><span data-stu-id="c435a-273">devices</span></span> | <span data-ttu-id="c435a-274">Alle Geräte, auf denen Warnungen im Zusammenhang mit dem Vorfall gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="c435a-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="c435a-275">\[\] (Details zu Entitätsfeldern finden Sie weiter unten)</span><span class="sxs-lookup"><span data-stu-id="c435a-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="c435a-276">Geräteformat</span><span class="sxs-lookup"><span data-stu-id="c435a-276">Device format</span></span>

<span data-ttu-id="c435a-277">Feldname</span><span class="sxs-lookup"><span data-stu-id="c435a-277">Field name</span></span> | <span data-ttu-id="c435a-278">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c435a-278">Description</span></span> | <span data-ttu-id="c435a-279">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="c435a-279">Example value</span></span>
-|-|-
<span data-ttu-id="c435a-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="c435a-280">DeviceId</span></span> | <span data-ttu-id="c435a-281">Die In Microsoft Defender ATP festgelegte Geräte-ID.</span><span class="sxs-lookup"><span data-stu-id="c435a-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="c435a-282">24c222b0b60fe148eece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="c435a-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="c435a-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="c435a-283">aadDeviceId</span></span> |  <span data-ttu-id="c435a-284">Die In Azure Active Directory festgelegte [Geräte-ID.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="c435a-284">The device ID as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="c435a-285">Nur für Geräte verfügbar, die einer Domäne beigetreten sind.</span><span class="sxs-lookup"><span data-stu-id="c435a-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="c435a-286">null</span><span class="sxs-lookup"><span data-stu-id="c435a-286">null</span></span>
<span data-ttu-id="c435a-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="c435a-287">deviceDnsName</span></span> | <span data-ttu-id="c435a-288">Der vollqualifizierte Domänenname für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="c435a-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="c435a-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c435a-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="c435a-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="c435a-290">osPlatform</span></span> | <span data-ttu-id="c435a-291">Die Betriebssystemplattform, auf der das Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c435a-291">The OS platform the device is running.</span></span>| <span data-ttu-id="c435a-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="c435a-292">WindowsServer2016</span></span>
<span data-ttu-id="c435a-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="c435a-293">osBuild</span></span> | <span data-ttu-id="c435a-294">Die Buildversion für das Betriebssystem, auf dem das Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c435a-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="c435a-295">14393</span><span class="sxs-lookup"><span data-stu-id="c435a-295">14393</span></span>
<span data-ttu-id="c435a-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="c435a-296">rbacGroupName</span></span> | <span data-ttu-id="c435a-297">Die dem Gerät [zugeordnete](https://docs.microsoft.com/azure/role-based-access-control/overview) rollenbasierte Zugriffssteuerungsgruppe (RBAC).</span><span class="sxs-lookup"><span data-stu-id="c435a-297">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="c435a-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="c435a-298">WDATP-Ring0</span></span>
<span data-ttu-id="c435a-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="c435a-299">firstSeen</span></span> | <span data-ttu-id="c435a-300">Zeitpunkt, zu dem das Gerät zum ersten Mal gesehen wurde.</span><span class="sxs-lookup"><span data-stu-id="c435a-300">Time when device was first seen.</span></span> | <span data-ttu-id="c435a-301">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="c435a-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="c435a-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="c435a-302">healthStatus</span></span> | <span data-ttu-id="c435a-303">Der Integritätsstatus des Geräts.</span><span class="sxs-lookup"><span data-stu-id="c435a-303">The health state of the device.</span></span> | <span data-ttu-id="c435a-304">Aktiv</span><span class="sxs-lookup"><span data-stu-id="c435a-304">Active</span></span>
<span data-ttu-id="c435a-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="c435a-305">riskScore</span></span> | <span data-ttu-id="c435a-306">Die Risikobewertung für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="c435a-306">The risk score for the  device.</span></span> | <span data-ttu-id="c435a-307">Hoch</span><span class="sxs-lookup"><span data-stu-id="c435a-307">High</span></span>
<span data-ttu-id="c435a-308">Entitäten</span><span class="sxs-lookup"><span data-stu-id="c435a-308">entities</span></span> | <span data-ttu-id="c435a-309">Alle Entitäten, die identifiziert wurden, dass sie Teil einer bestimmten Warnung sind oder damit verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="c435a-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="c435a-310">\[\] (Details zu Entitätsfeldern finden Sie weiter unten))</span><span class="sxs-lookup"><span data-stu-id="c435a-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="c435a-311">Entitätsformat</span><span class="sxs-lookup"><span data-stu-id="c435a-311">Entity Format</span></span>

<span data-ttu-id="c435a-312">Feldname</span><span class="sxs-lookup"><span data-stu-id="c435a-312">Field name</span></span> | <span data-ttu-id="c435a-313">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c435a-313">Description</span></span> | <span data-ttu-id="c435a-314">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="c435a-314">Example value</span></span>
-|-|-
<span data-ttu-id="c435a-315">entityType</span><span class="sxs-lookup"><span data-stu-id="c435a-315">entityType</span></span> | <span data-ttu-id="c435a-316">Entitäten, die identifiziert wurden, dass sie Teil einer bestimmten Warnung sind oder damit verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="c435a-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="c435a-317">Die Eigenschaftenwerte sind: *User*, *Ip*, *URL*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span><span class="sxs-lookup"><span data-stu-id="c435a-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="c435a-318">Benutzer</span><span class="sxs-lookup"><span data-stu-id="c435a-318">User</span></span>
<span data-ttu-id="c435a-319">sha1</span><span class="sxs-lookup"><span data-stu-id="c435a-319">sha1</span></span> | <span data-ttu-id="c435a-320">Verfügbar, wenn entityType Datei *ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="c435a-321">Der Dateihash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c435a-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="c435a-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="c435a-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="c435a-323">sha256</span><span class="sxs-lookup"><span data-stu-id="c435a-323">sha256</span></span> | <span data-ttu-id="c435a-324">Verfügbar, wenn entityType Datei *ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="c435a-325">Der Dateihash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c435a-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="c435a-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="c435a-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="c435a-327">fileName</span><span class="sxs-lookup"><span data-stu-id="c435a-327">fileName</span></span> | <span data-ttu-id="c435a-328">Verfügbar, wenn entityType Datei *ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="c435a-329">Der Dateiname für Warnungen, die einer Datei oder einem Prozess zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="c435a-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="c435a-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="c435a-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="c435a-331">filePath</span><span class="sxs-lookup"><span data-stu-id="c435a-331">filePath</span></span> | <span data-ttu-id="c435a-332">Verfügbar, wenn entityType Datei *ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="c435a-333">Der Dateipfad für Warnungen, die einer Datei oder einem Prozess zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="c435a-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="c435a-334">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="c435a-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="c435a-335">processId</span><span class="sxs-lookup"><span data-stu-id="c435a-335">processId</span></span> | <span data-ttu-id="c435a-336">Verfügbar, wenn entityType *Process ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="c435a-337">24348</span><span class="sxs-lookup"><span data-stu-id="c435a-337">24348</span></span>
<span data-ttu-id="c435a-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="c435a-338">processCommandLine</span></span> | <span data-ttu-id="c435a-339">Verfügbar, wenn entityType *Process ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="c435a-340">"Ihre Datei ist bereit zum Herunterladen \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="c435a-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="c435a-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="c435a-341">processCreationTime</span></span> | <span data-ttu-id="c435a-342">Verfügbar, wenn entityType *Process ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="c435a-343">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="c435a-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="c435a-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="c435a-344">parentProcessId</span></span> | <span data-ttu-id="c435a-345">Verfügbar, wenn entityType *Process ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="c435a-346">16840</span><span class="sxs-lookup"><span data-stu-id="c435a-346">16840</span></span>
<span data-ttu-id="c435a-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="c435a-347">parentProcessCreationTime</span></span> | <span data-ttu-id="c435a-348">Verfügbar, wenn entityType *Process ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="c435a-349">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="c435a-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="c435a-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="c435a-350">ipAddress</span></span> | <span data-ttu-id="c435a-351">Verfügbar, wenn entityType ip *ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="c435a-352">IP-Adresse für Warnungen im Zusammenhang mit Netzwerkereignissen, z. B. Kommunikation *mit einem schädlichen Netzwerkziel.*</span><span class="sxs-lookup"><span data-stu-id="c435a-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="c435a-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="c435a-353">62.216.203.204</span></span>
<span data-ttu-id="c435a-354">url</span><span class="sxs-lookup"><span data-stu-id="c435a-354">url</span></span> | <span data-ttu-id="c435a-355">Verfügbar, wenn entityType url *ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="c435a-356">URL für Warnungen im Zusammenhang mit Netzwerkereignissen, z. B. Kommunikation *mit einem schädlichen Netzwerkziel.*</span><span class="sxs-lookup"><span data-stu-id="c435a-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="c435a-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="c435a-357">down.esales360.cn</span></span>
<span data-ttu-id="c435a-358">accountName</span><span class="sxs-lookup"><span data-stu-id="c435a-358">accountName</span></span> | <span data-ttu-id="c435a-359">Verfügbar, wenn entityType Benutzer *ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="c435a-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="c435a-360">testUser2</span></span>
<span data-ttu-id="c435a-361">Domänname</span><span class="sxs-lookup"><span data-stu-id="c435a-361">domainName</span></span> | <span data-ttu-id="c435a-362">Verfügbar, wenn entityType Benutzer *ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="c435a-363">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="c435a-363">europe.corp.contoso</span></span>
<span data-ttu-id="c435a-364">userSid</span><span class="sxs-lookup"><span data-stu-id="c435a-364">userSid</span></span> | <span data-ttu-id="c435a-365">Verfügbar, wenn entityType Benutzer *ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="c435a-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="c435a-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="c435a-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="c435a-367">aadUserId</span></span> | <span data-ttu-id="c435a-368">Verfügbar, wenn entityType Benutzer *ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="c435a-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="c435a-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="c435a-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="c435a-370">userPrincipalName</span></span> | <span data-ttu-id="c435a-371">Verfügbar, wenn entityType *User* / *MailBox* / *MailMessage ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="c435a-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c435a-372">testUser2@contoso.com</span></span>
<span data-ttu-id="c435a-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="c435a-373">mailboxDisplayName</span></span> | <span data-ttu-id="c435a-374">Verfügbar, wenn entityType *MailBox ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="c435a-375">Testbenutzer2</span><span class="sxs-lookup"><span data-stu-id="c435a-375">test User2</span></span>
<span data-ttu-id="c435a-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="c435a-376">mailboxAddress</span></span> | <span data-ttu-id="c435a-377">Verfügbar, wenn entityType *User* / *MailBox* / *MailMessage ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="c435a-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c435a-378">testUser2@contoso.com</span></span>
<span data-ttu-id="c435a-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="c435a-379">clusterBy</span></span> | <span data-ttu-id="c435a-380">Verfügbar, wenn entityType *MailCluster ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="c435a-381">Betreff; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="c435a-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="c435a-382">sender</span><span class="sxs-lookup"><span data-stu-id="c435a-382">sender</span></span> | <span data-ttu-id="c435a-383">Verfügbar, wenn entityType *User* / *MailBox* / *MailMessage ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="c435a-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="c435a-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="c435a-385">recipient</span><span class="sxs-lookup"><span data-stu-id="c435a-385">recipient</span></span> | <span data-ttu-id="c435a-386">Verfügbar, wenn entityType *MailMessage ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="c435a-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c435a-387">testUser2@contoso.com</span></span>
<span data-ttu-id="c435a-388">subject</span><span class="sxs-lookup"><span data-stu-id="c435a-388">subject</span></span> | <span data-ttu-id="c435a-389">Verfügbar, wenn entityType *MailMessage ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="c435a-390">\[EXTERNE \] Aufmerksamkeit</span><span class="sxs-lookup"><span data-stu-id="c435a-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="c435a-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="c435a-391">deliveryAction</span></span> | <span data-ttu-id="c435a-392">Verfügbar, wenn entityType *MailMessage ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="c435a-393">Zugestellt</span><span class="sxs-lookup"><span data-stu-id="c435a-393">Delivered</span></span>
<span data-ttu-id="c435a-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="c435a-394">securityGroupId</span></span> | <span data-ttu-id="c435a-395">Verfügbar, wenn entityType *SecurityGroup ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="c435a-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="c435a-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="c435a-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="c435a-397">securityGroupName</span></span> | <span data-ttu-id="c435a-398">Verfügbar, wenn entityType *SecurityGroup ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="c435a-399">Netzwerkkonfigurationsoperatoren</span><span class="sxs-lookup"><span data-stu-id="c435a-399">Network Configuration Operators</span></span>
<span data-ttu-id="c435a-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="c435a-400">registryHive</span></span> | <span data-ttu-id="c435a-401">Verfügbar, wenn entityType Registrierung *ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="c435a-402">LOKALER \_ \_ HKEY-COMPUTER</span><span class="sxs-lookup"><span data-stu-id="c435a-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="c435a-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="c435a-403">registryKey</span></span> | <span data-ttu-id="c435a-404">Verfügbar, wenn entityType Registrierung *ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="c435a-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="c435a-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="c435a-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="c435a-406">registryValueType</span></span> | <span data-ttu-id="c435a-407">Verfügbar, wenn entityType Registrierung *ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="c435a-408">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c435a-408">String</span></span>
<span data-ttu-id="c435a-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="c435a-409">registryValue</span></span> | <span data-ttu-id="c435a-410">Verfügbar, wenn entityType Registrierung *ist.*</span><span class="sxs-lookup"><span data-stu-id="c435a-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="c435a-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="c435a-411">31-00-00-00</span></span>
<span data-ttu-id="c435a-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="c435a-412">deviceId</span></span> | <span data-ttu-id="c435a-413">Die ID des Geräts, das sich auf die Entität bezogen hat( sofern eine id).</span><span class="sxs-lookup"><span data-stu-id="c435a-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="c435a-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="c435a-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="c435a-415">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c435a-415">Example</span></span>

<span data-ttu-id="c435a-416">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="c435a-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="c435a-417">**Response**</span><span class="sxs-lookup"><span data-stu-id="c435a-417">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="c435a-418">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="c435a-418">Related articles</span></span>

- [<span data-ttu-id="c435a-419">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="c435a-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="c435a-420">Informationen zu API-Beschränkungen und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="c435a-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="c435a-421">Fehlercodes verstehen</span><span class="sxs-lookup"><span data-stu-id="c435a-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="c435a-422">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="c435a-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c435a-423">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="c435a-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="c435a-424">Vorfall-API aktualisieren</span><span class="sxs-lookup"><span data-stu-id="c435a-424">Update incident API</span></span>](api-update-incidents.md)

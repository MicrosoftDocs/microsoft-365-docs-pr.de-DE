---
title: Listen Vorfälle-API in Microsoft 365 Defender
description: Informationen zum Auflisten von Vorfälle-API in Microsoft 365 Defender
keywords: Liste, Vorfall, Vorfälle, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 13508d3ad9d61797517ccb55a27152883947843a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719428"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="b9eee-104">Listen Vorfälle-API in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9eee-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b9eee-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b9eee-105">**Applies to:**</span></span>

- <span data-ttu-id="b9eee-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9eee-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9eee-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="b9eee-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b9eee-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="b9eee-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="b9eee-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9eee-109">API description</span></span>

<span data-ttu-id="b9eee-110">Mit der List Incidents-API können Sie Vorfälle sortieren, um eine informierte Cyber-Antwort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9eee-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="b9eee-111">Es macht eine Sammlung von Vorfällen verfügbar, die in Ihrem Netzwerk markiert wurden, innerhalb des Zeitbereichs, den Sie in der Aufbewahrungsrichtlinie für die Umgebung angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="b9eee-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="b9eee-112">Die jüngsten Vorfälle werden oben in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9eee-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="b9eee-113">Jeder Vorfall enthält ein Array zusammengehöriger Warnungen und zugehöriger Entitäten.</span><span class="sxs-lookup"><span data-stu-id="b9eee-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="b9eee-114">Die API unterstützt die folgenden **OData** -Operatoren:</span><span class="sxs-lookup"><span data-stu-id="b9eee-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="b9eee-115">`$filter`in den `lastUpdateTime` `createdTime` Eigenschaften,, `status` und und `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="b9eee-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="b9eee-116">`$top`mit einem Höchstwert von **100**</span><span class="sxs-lookup"><span data-stu-id="b9eee-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="b9eee-117">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b9eee-117">Limitations</span></span>

1. <span data-ttu-id="b9eee-118">Die maximale Seitengröße beträgt **100 Vorfälle**.</span><span class="sxs-lookup"><span data-stu-id="b9eee-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="b9eee-119">Die maximale Anzahl von Anforderungen beträgt **50 Anrufe pro Minute** und **1500 Anrufe pro Stunde**.</span><span class="sxs-lookup"><span data-stu-id="b9eee-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="b9eee-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b9eee-120">Permissions</span></span>

<span data-ttu-id="b9eee-121">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b9eee-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b9eee-122">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access Microsoft 365 Defender APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="b9eee-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="b9eee-123">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="b9eee-123">Permission type</span></span> | <span data-ttu-id="b9eee-124">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b9eee-124">Permission</span></span> | <span data-ttu-id="b9eee-125">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b9eee-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="b9eee-126">Anwendung</span><span class="sxs-lookup"><span data-stu-id="b9eee-126">Application</span></span> | <span data-ttu-id="b9eee-127">Vorfall. Read. all</span><span class="sxs-lookup"><span data-stu-id="b9eee-127">Incident.Read.All</span></span> | <span data-ttu-id="b9eee-128">Alle Vorfälle lesen</span><span class="sxs-lookup"><span data-stu-id="b9eee-128">Read all incidents</span></span>
<span data-ttu-id="b9eee-129">Anwendung</span><span class="sxs-lookup"><span data-stu-id="b9eee-129">Application</span></span> | <span data-ttu-id="b9eee-130">Incident. ReadWrite. all</span><span class="sxs-lookup"><span data-stu-id="b9eee-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="b9eee-131">Lesen und Schreiben aller Vorfälle</span><span class="sxs-lookup"><span data-stu-id="b9eee-131">Read and write all incidents</span></span>
<span data-ttu-id="b9eee-132">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="b9eee-132">Delegated (work or school account)</span></span> | <span data-ttu-id="b9eee-133">Vorfall. Read</span><span class="sxs-lookup"><span data-stu-id="b9eee-133">Incident.Read</span></span> | <span data-ttu-id="b9eee-134">Vorfälle lesen</span><span class="sxs-lookup"><span data-stu-id="b9eee-134">Read incidents</span></span>
<span data-ttu-id="b9eee-135">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="b9eee-135">Delegated (work or school account)</span></span> | <span data-ttu-id="b9eee-136">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b9eee-136">Incident.ReadWrite</span></span> | <span data-ttu-id="b9eee-137">Lese-und Schreib Vorfälle</span><span class="sxs-lookup"><span data-stu-id="b9eee-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="b9eee-138">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="b9eee-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="b9eee-139">Der Benutzer muss über die Berechtigung "anzeigen" für Vorfälle im Portal verfügen.</span><span class="sxs-lookup"><span data-stu-id="b9eee-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="b9eee-140">Die Antwort umfasst nur Vorfälle, denen der Benutzer ausgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="b9eee-141">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="b9eee-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="b9eee-142">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="b9eee-142">Request headers</span></span>

<span data-ttu-id="b9eee-143">Name</span><span class="sxs-lookup"><span data-stu-id="b9eee-143">Name</span></span> | <span data-ttu-id="b9eee-144">Typ</span><span class="sxs-lookup"><span data-stu-id="b9eee-144">Type</span></span> | <span data-ttu-id="b9eee-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9eee-145">Description</span></span>
-|-|-
<span data-ttu-id="b9eee-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="b9eee-146">Authorization</span></span> | <span data-ttu-id="b9eee-147">String</span><span class="sxs-lookup"><span data-stu-id="b9eee-147">String</span></span> | <span data-ttu-id="b9eee-148">Bearer {Token}.</span><span class="sxs-lookup"><span data-stu-id="b9eee-148">Bearer {token}.</span></span> <span data-ttu-id="b9eee-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="b9eee-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="b9eee-150">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="b9eee-150">Request body</span></span>

<span data-ttu-id="b9eee-151">Keine</span><span class="sxs-lookup"><span data-stu-id="b9eee-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="b9eee-152">Antwort</span><span class="sxs-lookup"><span data-stu-id="b9eee-152">Response</span></span>

<span data-ttu-id="b9eee-153">Wenn die Methode erfolgreich verläuft, `200 OK` wird eine Liste von [Vorfällen](api-incident.md) im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b9eee-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="b9eee-154">Schema Zuordnung</span><span class="sxs-lookup"><span data-stu-id="b9eee-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="b9eee-155">Vorfall Metadaten</span><span class="sxs-lookup"><span data-stu-id="b9eee-155">Incident metadata</span></span>

<span data-ttu-id="b9eee-156">Feldname</span><span class="sxs-lookup"><span data-stu-id="b9eee-156">Field name</span></span> | <span data-ttu-id="b9eee-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9eee-157">Description</span></span> | <span data-ttu-id="b9eee-158">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="b9eee-158">Example value</span></span>
-|-|-
<span data-ttu-id="b9eee-159">Vorfall-Nr</span><span class="sxs-lookup"><span data-stu-id="b9eee-159">incidentId</span></span> | <span data-ttu-id="b9eee-160">Eindeutiger Bezeichner zur Darstellung des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="b9eee-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="b9eee-161">924565</span><span class="sxs-lookup"><span data-stu-id="b9eee-161">924565</span></span>
<span data-ttu-id="b9eee-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="b9eee-162">redirectIncidentId</span></span> | <span data-ttu-id="b9eee-163">Nur aufgefüllt, wenn ein Vorfall als Teil der Vorfall Verarbeitungslogik mit einem anderen Vorfall zusammengefasst wird.</span><span class="sxs-lookup"><span data-stu-id="b9eee-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="b9eee-164">924569</span><span class="sxs-lookup"><span data-stu-id="b9eee-164">924569</span></span>
<span data-ttu-id="b9eee-165">Vorfallname</span><span class="sxs-lookup"><span data-stu-id="b9eee-165">incidentName</span></span> | <span data-ttu-id="b9eee-166">Zeichenfolgenwert, der für jeden Vorfall verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-166">String value available for every incident.</span></span> | <span data-ttu-id="b9eee-167">Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="b9eee-167">Ransomware activity</span></span>
<span data-ttu-id="b9eee-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="b9eee-168">createdTime</span></span> | <span data-ttu-id="b9eee-169">Zeitpunkt, zu dem der Vorfall erstmals erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b9eee-169">Time when incident was first created.</span></span> | <span data-ttu-id="b9eee-170">2020-09-06T14:46:57.0733333 z</span><span class="sxs-lookup"><span data-stu-id="b9eee-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="b9eee-171">Last Update time</span><span class="sxs-lookup"><span data-stu-id="b9eee-171">lastUpdateTime</span></span> | <span data-ttu-id="b9eee-172">Zeitpunkt, zu dem der Vorfall zuletzt auf dem Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b9eee-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="b9eee-173">Dieses Feld kann verwendet werden, wenn Sie den Parameter Request für den Zeitraum festlegen, in dem Vorfälle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b9eee-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="b9eee-174">2020-09-06T14:46:57.29 z</span><span class="sxs-lookup"><span data-stu-id="b9eee-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="b9eee-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="b9eee-175">assignedTo</span></span> | <span data-ttu-id="b9eee-176">Der Besitzer des Vorfalls oder *null* , wenn kein Besitzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="b9eee-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9eee-177">secop2@contoso.com</span></span>
<span data-ttu-id="b9eee-178">classification</span><span class="sxs-lookup"><span data-stu-id="b9eee-178">classification</span></span> | <span data-ttu-id="b9eee-179">Die Spezifikation für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="b9eee-179">The specification for the incident.</span></span> <span data-ttu-id="b9eee-180">Die Eigenschaftswerte lauten: *unbekannt*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="b9eee-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="b9eee-181">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="b9eee-181">Unknown</span></span>
<span data-ttu-id="b9eee-182">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="b9eee-182">determination</span></span> | <span data-ttu-id="b9eee-183">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="b9eee-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="b9eee-184">Die Eigenschaftswerte lauten: *nichtin*, *apt*, *Schadsoftware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other*</span><span class="sxs-lookup"><span data-stu-id="b9eee-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="b9eee-185">Nichtin</span><span class="sxs-lookup"><span data-stu-id="b9eee-185">NotAvailable</span></span>
<span data-ttu-id="b9eee-186">status</span><span class="sxs-lookup"><span data-stu-id="b9eee-186">status</span></span> | <span data-ttu-id="b9eee-187">Vorfälle kategorisieren (als *aktiv* oder *aufgelöst*).</span><span class="sxs-lookup"><span data-stu-id="b9eee-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="b9eee-188">Es kann Ihnen helfen, Ihre Antwort auf Vorfälle zu organisieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b9eee-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="b9eee-189">Aktiv</span><span class="sxs-lookup"><span data-stu-id="b9eee-189">Active</span></span>
<span data-ttu-id="b9eee-190">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="b9eee-190">severity</span></span> | <span data-ttu-id="b9eee-191">Gibt die möglichen Auswirkungen auf Objekte an.</span><span class="sxs-lookup"><span data-stu-id="b9eee-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="b9eee-192">Je höher der Schweregrad, desto größer die Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="b9eee-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="b9eee-193">Normalerweise erfordern höhere Severity-Elemente die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="b9eee-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="b9eee-194">Einer der folgenden Werte: *Informational*, *Low*, \* Mittel und *High*.</span><span class="sxs-lookup"><span data-stu-id="b9eee-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="b9eee-195">Mittel</span><span class="sxs-lookup"><span data-stu-id="b9eee-195">Medium</span></span>
<span data-ttu-id="b9eee-196">tags</span><span class="sxs-lookup"><span data-stu-id="b9eee-196">tags</span></span> | <span data-ttu-id="b9eee-197">Array von benutzerdefinierten Tags, die einem Vorfall zugeordnet sind, beispielsweise zum Kennzeichnen einer Gruppe von Vorfällen mit einem gemeinsamen Merkmal.</span><span class="sxs-lookup"><span data-stu-id="b9eee-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="b9eee-198">Warnungen</span><span class="sxs-lookup"><span data-stu-id="b9eee-198">alerts</span></span> | <span data-ttu-id="b9eee-199">Array mit allen Warnungen im Zusammenhang mit dem Vorfall sowie weiteren Informationen wie Schweregrad, Entitäten, die an der Warnung beteiligt waren, und die Quelle der Warnungen.</span><span class="sxs-lookup"><span data-stu-id="b9eee-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="b9eee-200">\[\] (Weitere Informationen zu den folgenden Warnfeldern finden Sie unter)</span><span class="sxs-lookup"><span data-stu-id="b9eee-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="b9eee-201">Warnungs Metadaten</span><span class="sxs-lookup"><span data-stu-id="b9eee-201">Alerts metadata</span></span>

<span data-ttu-id="b9eee-202">Feldname</span><span class="sxs-lookup"><span data-stu-id="b9eee-202">Field name</span></span> | <span data-ttu-id="b9eee-203">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9eee-203">Description</span></span> | <span data-ttu-id="b9eee-204">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="b9eee-204">Example value</span></span>
-|-|-
<span data-ttu-id="b9eee-205">Warnungs-Nr</span><span class="sxs-lookup"><span data-stu-id="b9eee-205">alertId</span></span> | <span data-ttu-id="b9eee-206">Eindeutiger Bezeichner zur Darstellung der Warnung</span><span class="sxs-lookup"><span data-stu-id="b9eee-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="b9eee-207">caD70CFEE2-1F54-32dB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="b9eee-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="b9eee-208">Vorfall-Nr</span><span class="sxs-lookup"><span data-stu-id="b9eee-208">incidentId</span></span> | <span data-ttu-id="b9eee-209">Eindeutige ID, die den Vorfall darstellt, dem diese Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="b9eee-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="b9eee-210">924565</span><span class="sxs-lookup"><span data-stu-id="b9eee-210">924565</span></span>
<span data-ttu-id="b9eee-211">Metadata</span><span class="sxs-lookup"><span data-stu-id="b9eee-211">serviceSource</span></span> | <span data-ttu-id="b9eee-212">Dienst, von dem die Warnung stammt, beispielsweise Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity oder Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9eee-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="b9eee-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="b9eee-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="b9eee-214">CreationTime</span><span class="sxs-lookup"><span data-stu-id="b9eee-214">creationTime</span></span> | <span data-ttu-id="b9eee-215">Zeitpunkt, zu dem die Warnung erstmalig erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b9eee-215">Time when alert was first created.</span></span> | <span data-ttu-id="b9eee-216">2020-09-06T14:46:55.7182276 z</span><span class="sxs-lookup"><span data-stu-id="b9eee-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="b9eee-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="b9eee-217">lastUpdatedTime</span></span> | <span data-ttu-id="b9eee-218">Zeitpunkt, zu dem die Benachrichtigung zuletzt im Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b9eee-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="b9eee-219">2020-09-06T14:46:57.2433333 z</span><span class="sxs-lookup"><span data-stu-id="b9eee-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="b9eee-220">aufgelöst</span><span class="sxs-lookup"><span data-stu-id="b9eee-220">resolvedTime</span></span> | <span data-ttu-id="b9eee-221">Zeitpunkt, zu dem die Warnung aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="b9eee-221">Time when alert was resolved.</span></span> | <span data-ttu-id="b9eee-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="b9eee-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="b9eee-223">First-Angleichung</span><span class="sxs-lookup"><span data-stu-id="b9eee-223">firstActivity</span></span> | <span data-ttu-id="b9eee-224">Zeitpunkt, zu dem von der Warnung zuerst berichtet wurde, dass die Aktivität im Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b9eee-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="b9eee-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="b9eee-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="b9eee-226">title</span><span class="sxs-lookup"><span data-stu-id="b9eee-226">title</span></span> | <span data-ttu-id="b9eee-227">Der kurze identifizierende Zeichenfolgenwert, der für jede Warnung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="b9eee-228">Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="b9eee-228">Ransomware activity</span></span>
<span data-ttu-id="b9eee-229">description</span><span class="sxs-lookup"><span data-stu-id="b9eee-229">description</span></span> | <span data-ttu-id="b9eee-230">Zeichenfolgenwert, der jede Warnung beschreibt.</span><span class="sxs-lookup"><span data-stu-id="b9eee-230">String value describing each alert.</span></span> | <span data-ttu-id="b9eee-231">Der Benutzer testet Benutzer2 (testUser2@contoso.com) manipulierte 99-Dateien mit mehreren Endungen, die mit der ungewöhnlich *herunterladen*-Erweiterung enden.</span><span class="sxs-lookup"><span data-stu-id="b9eee-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="b9eee-232">Dies ist eine ungewöhnliche Anzahl von Datei Manipulationen und deutet auf einen potenziellen Ransomware-Angriff hin.</span><span class="sxs-lookup"><span data-stu-id="b9eee-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="b9eee-233">category</span><span class="sxs-lookup"><span data-stu-id="b9eee-233">category</span></span> | <span data-ttu-id="b9eee-234">Visuelle und numerische Ansicht, wie weit der Angriff in der killkette fortgeschritten ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="b9eee-235">Am [Mitra ATT&ck™ Framework](https://attack.mitre.org/)ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="b9eee-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="b9eee-236">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="b9eee-236">Impact</span></span>
<span data-ttu-id="b9eee-237">status</span><span class="sxs-lookup"><span data-stu-id="b9eee-237">status</span></span> | <span data-ttu-id="b9eee-238">Benachrichtigungen kategorisieren (als *neu*, *aktiv* oder *aufgelöst*).</span><span class="sxs-lookup"><span data-stu-id="b9eee-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="b9eee-239">Es kann Ihnen helfen, Ihre Antwort auf Warnungen zu organisieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b9eee-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="b9eee-240">Neu</span><span class="sxs-lookup"><span data-stu-id="b9eee-240">New</span></span>
<span data-ttu-id="b9eee-241">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="b9eee-241">severity</span></span> | <span data-ttu-id="b9eee-242">Gibt die möglichen Auswirkungen auf Objekte an.</span><span class="sxs-lookup"><span data-stu-id="b9eee-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="b9eee-243">Je höher der Schweregrad, desto größer die Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="b9eee-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="b9eee-244">Normalerweise erfordern höhere Severity-Elemente die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="b9eee-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="b9eee-245">Einer der folgenden Werte: *Informational*, *Low*, \* Mittel und *High*.</span><span class="sxs-lookup"><span data-stu-id="b9eee-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="b9eee-246">Mittel</span><span class="sxs-lookup"><span data-stu-id="b9eee-246">Medium</span></span>
<span data-ttu-id="b9eee-247">Ermittlungs-Nr</span><span class="sxs-lookup"><span data-stu-id="b9eee-247">investigationId</span></span> | <span data-ttu-id="b9eee-248">Die von dieser Warnung ausgelöste automatische Ermittlungs-ID.</span><span class="sxs-lookup"><span data-stu-id="b9eee-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="b9eee-249">1234</span><span class="sxs-lookup"><span data-stu-id="b9eee-249">1234</span></span>
<span data-ttu-id="b9eee-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="b9eee-250">investigationState</span></span> | <span data-ttu-id="b9eee-251">Informationen zum aktuellen Status der Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="b9eee-251">Information on the investigation's current status.</span></span> <span data-ttu-id="b9eee-252">Einer der folgenden Werte: *Unknown*, *terminated*, *SuccessfullyRemediated*, *benigne*, *failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *unsupporteds*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="b9eee-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="b9eee-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="b9eee-253">UnsupportedAlertType</span></span>
<span data-ttu-id="b9eee-254">classification</span><span class="sxs-lookup"><span data-stu-id="b9eee-254">classification</span></span> | <span data-ttu-id="b9eee-255">Die Spezifikation für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="b9eee-255">The specification for the incident.</span></span> <span data-ttu-id="b9eee-256">Die Eigenschaftswerte sind: *Unknown*, *FalsePositive*, *TruePositive* oder *null*</span><span class="sxs-lookup"><span data-stu-id="b9eee-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="b9eee-257">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="b9eee-257">Unknown</span></span>
<span data-ttu-id="b9eee-258">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="b9eee-258">determination</span></span> | <span data-ttu-id="b9eee-259">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="b9eee-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="b9eee-260">Die Eigenschaftswerte sind: *nichtin*, *apt*, *Schadsoftware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other* oder  *null*</span><span class="sxs-lookup"><span data-stu-id="b9eee-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="b9eee-261">Apt</span><span class="sxs-lookup"><span data-stu-id="b9eee-261">Apt</span></span>
<span data-ttu-id="b9eee-262">assignedTo</span><span class="sxs-lookup"><span data-stu-id="b9eee-262">assignedTo</span></span> | <span data-ttu-id="b9eee-263">Der Besitzer des Vorfalls oder *null* , wenn kein Besitzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="b9eee-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9eee-264">secop2@contoso.com</span></span>
<span data-ttu-id="b9eee-265">darstellername</span><span class="sxs-lookup"><span data-stu-id="b9eee-265">actorName</span></span> | <span data-ttu-id="b9eee-266">Die Aktivitätsgruppe (sofern vorhanden), die dieser Warnung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="b9eee-267">Bor</span><span class="sxs-lookup"><span data-stu-id="b9eee-267">BORON</span></span>
<span data-ttu-id="b9eee-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="b9eee-268">threatFamilyName</span></span> | <span data-ttu-id="b9eee-269">Bedrohungs Familie, die dieser Warnung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="b9eee-270">null</span><span class="sxs-lookup"><span data-stu-id="b9eee-270">null</span></span>
<span data-ttu-id="b9eee-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="b9eee-271">mitreTechniques</span></span> | <span data-ttu-id="b9eee-272">Die Angriffstechniken, die mit dem [Gehrungs&ck](https://attack.mitre.org/)™ Framework ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="b9eee-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="b9eee-273">Geräte</span><span class="sxs-lookup"><span data-stu-id="b9eee-273">devices</span></span> | <span data-ttu-id="b9eee-274">Alle Geräte, auf denen Benachrichtigungen im Zusammenhang mit dem Vorfall gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="b9eee-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="b9eee-275">\[\] (siehe Details zu Entitätsfeldern unten)</span><span class="sxs-lookup"><span data-stu-id="b9eee-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="b9eee-276">Geräteformat</span><span class="sxs-lookup"><span data-stu-id="b9eee-276">Device format</span></span>

<span data-ttu-id="b9eee-277">Feldname</span><span class="sxs-lookup"><span data-stu-id="b9eee-277">Field name</span></span> | <span data-ttu-id="b9eee-278">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9eee-278">Description</span></span> | <span data-ttu-id="b9eee-279">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="b9eee-279">Example value</span></span>
-|-|-
<span data-ttu-id="b9eee-280">DeviceID</span><span class="sxs-lookup"><span data-stu-id="b9eee-280">DeviceId</span></span> | <span data-ttu-id="b9eee-281">Die Geräte-ID, wie in Microsoft Defender ATP angegeben.</span><span class="sxs-lookup"><span data-stu-id="b9eee-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="b9eee-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="b9eee-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="b9eee-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="b9eee-283">aadDeviceId</span></span> |  <span data-ttu-id="b9eee-284">Die in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)bezeichnete Geräte-ID.</span><span class="sxs-lookup"><span data-stu-id="b9eee-284">The device ID as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="b9eee-285">Nur für Domänen verbundene Geräte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b9eee-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="b9eee-286">null</span><span class="sxs-lookup"><span data-stu-id="b9eee-286">null</span></span>
<span data-ttu-id="b9eee-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="b9eee-287">deviceDnsName</span></span> | <span data-ttu-id="b9eee-288">Der vollqualifizierte Domänenname für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="b9eee-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="b9eee-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9eee-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="b9eee-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="b9eee-290">osPlatform</span></span> | <span data-ttu-id="b9eee-291">Die Betriebssystemplattform, die das Gerät ausführt.</span><span class="sxs-lookup"><span data-stu-id="b9eee-291">The OS platform the device is running.</span></span>| <span data-ttu-id="b9eee-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="b9eee-292">WindowsServer2016</span></span>
<span data-ttu-id="b9eee-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="b9eee-293">osBuild</span></span> | <span data-ttu-id="b9eee-294">Die Buildversion für das Betriebssystem, auf dem das Gerät läuft.</span><span class="sxs-lookup"><span data-stu-id="b9eee-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="b9eee-295">14393</span><span class="sxs-lookup"><span data-stu-id="b9eee-295">14393</span></span>
<span data-ttu-id="b9eee-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="b9eee-296">rbacGroupName</span></span> | <span data-ttu-id="b9eee-297">Die dem Gerät zugeordnete [rollenbasierte Zugriffs Steuerungsgruppe (Role-Based Access Control](https://docs.microsoft.com/azure/role-based-access-control/overview) , RBAC).</span><span class="sxs-lookup"><span data-stu-id="b9eee-297">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="b9eee-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="b9eee-298">WDATP-Ring0</span></span>
<span data-ttu-id="b9eee-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="b9eee-299">firstSeen</span></span> | <span data-ttu-id="b9eee-300">Zeitpunkt, zu dem das Gerät zum ersten Mal angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="b9eee-300">Time when device was first seen.</span></span> | <span data-ttu-id="b9eee-301">2020-02-06T14:16:01.9330135 z</span><span class="sxs-lookup"><span data-stu-id="b9eee-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="b9eee-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="b9eee-302">healthStatus</span></span> | <span data-ttu-id="b9eee-303">Der Integritätsstatus des Geräts.</span><span class="sxs-lookup"><span data-stu-id="b9eee-303">The health state of the device.</span></span> | <span data-ttu-id="b9eee-304">Aktiv</span><span class="sxs-lookup"><span data-stu-id="b9eee-304">Active</span></span>
<span data-ttu-id="b9eee-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="b9eee-305">riskScore</span></span> | <span data-ttu-id="b9eee-306">Die Risikobewertung für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="b9eee-306">The risk score for the  device.</span></span> | <span data-ttu-id="b9eee-307">Hoch</span><span class="sxs-lookup"><span data-stu-id="b9eee-307">High</span></span>
<span data-ttu-id="b9eee-308">Entitäten</span><span class="sxs-lookup"><span data-stu-id="b9eee-308">entities</span></span> | <span data-ttu-id="b9eee-309">Alle Entitäten, die als Teil einer bestimmten Warnung oder mit dieser in Verbindung mit dieser identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="b9eee-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="b9eee-310">\[\] (siehe Details zu Entitätsfeldern unten)</span><span class="sxs-lookup"><span data-stu-id="b9eee-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="b9eee-311">Entitäts Format</span><span class="sxs-lookup"><span data-stu-id="b9eee-311">Entity Format</span></span>

<span data-ttu-id="b9eee-312">Feldname</span><span class="sxs-lookup"><span data-stu-id="b9eee-312">Field name</span></span> | <span data-ttu-id="b9eee-313">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9eee-313">Description</span></span> | <span data-ttu-id="b9eee-314">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="b9eee-314">Example value</span></span>
-|-|-
<span data-ttu-id="b9eee-315">EntityType</span><span class="sxs-lookup"><span data-stu-id="b9eee-315">entityType</span></span> | <span data-ttu-id="b9eee-316">Entitäten, die als Teil oder mit einer bestimmten Warnung in Verbindung mit identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="b9eee-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="b9eee-317">Die Eigenschaftenwerte lauten: *User*, *IP*, *URL*, *File*, *Process*, *Mailbox*, *MailMessage*, *mailcluster*, *Registry*</span><span class="sxs-lookup"><span data-stu-id="b9eee-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="b9eee-318">Benutzer</span><span class="sxs-lookup"><span data-stu-id="b9eee-318">User</span></span>
<span data-ttu-id="b9eee-319">SHA1</span><span class="sxs-lookup"><span data-stu-id="b9eee-319">sha1</span></span> | <span data-ttu-id="b9eee-320">Verfügbar, wenn EntityType *Datei* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="b9eee-321">Der Datei Hash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b9eee-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="b9eee-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="b9eee-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="b9eee-323">SHA256</span><span class="sxs-lookup"><span data-stu-id="b9eee-323">sha256</span></span> | <span data-ttu-id="b9eee-324">Verfügbar, wenn EntityType *Datei* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="b9eee-325">Der Datei Hash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b9eee-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="b9eee-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="b9eee-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="b9eee-327">fileName</span><span class="sxs-lookup"><span data-stu-id="b9eee-327">fileName</span></span> | <span data-ttu-id="b9eee-328">Verfügbar, wenn EntityType *Datei* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="b9eee-329">Den Dateinamen für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b9eee-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="b9eee-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="b9eee-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="b9eee-331">FilePath</span><span class="sxs-lookup"><span data-stu-id="b9eee-331">filePath</span></span> | <span data-ttu-id="b9eee-332">Verfügbar, wenn EntityType *Datei* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="b9eee-333">Der Dateipfad für Warnungen, die einer Datei oder einem Prozess zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="b9eee-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="b9eee-334">C: \\ \ agent_work_temp \deploy\system\2020-09-06 12_14_54 \ out</span><span class="sxs-lookup"><span data-stu-id="b9eee-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="b9eee-335">ProcessID</span><span class="sxs-lookup"><span data-stu-id="b9eee-335">processId</span></span> | <span data-ttu-id="b9eee-336">Verfügbar, wenn EntityType *Prozess* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="b9eee-337">24348</span><span class="sxs-lookup"><span data-stu-id="b9eee-337">24348</span></span>
<span data-ttu-id="b9eee-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="b9eee-338">processCommandLine</span></span> | <span data-ttu-id="b9eee-339">Verfügbar, wenn EntityType *Prozess* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="b9eee-340">"Ihre Datei kann1911150169.exe heruntergeladen werden \_ "</span><span class="sxs-lookup"><span data-stu-id="b9eee-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="b9eee-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="b9eee-341">processCreationTime</span></span> | <span data-ttu-id="b9eee-342">Verfügbar, wenn EntityType *Prozess* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="b9eee-343">2020-07-18T03:25:38.5269993 z</span><span class="sxs-lookup"><span data-stu-id="b9eee-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="b9eee-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="b9eee-344">parentProcessId</span></span> | <span data-ttu-id="b9eee-345">Verfügbar, wenn EntityType *Prozess* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="b9eee-346">16840</span><span class="sxs-lookup"><span data-stu-id="b9eee-346">16840</span></span>
<span data-ttu-id="b9eee-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="b9eee-347">parentProcessCreationTime</span></span> | <span data-ttu-id="b9eee-348">Verfügbar, wenn EntityType *Prozess* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="b9eee-349">2020-07-18T02:12:32.8616797 z</span><span class="sxs-lookup"><span data-stu-id="b9eee-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="b9eee-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="b9eee-350">ipAddress</span></span> | <span data-ttu-id="b9eee-351">Verfügbar, wenn EntityType *IP* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="b9eee-352">IP-Adresse für Warnungen, die Netzwerkereignissen zugeordnet sind, beispielsweise *die Kommunikation mit einem böswilligen Netzwerkziel*.</span><span class="sxs-lookup"><span data-stu-id="b9eee-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="b9eee-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="b9eee-353">62.216.203.204</span></span>
<span data-ttu-id="b9eee-354">url</span><span class="sxs-lookup"><span data-stu-id="b9eee-354">url</span></span> | <span data-ttu-id="b9eee-355">Verfügbar, wenn EntityType *URL* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="b9eee-356">URL für Warnungen, die Netzwerkereignissen zugeordnet sind, beispielsweise *die Kommunikation mit einem böswilligen Netzwerkziel*.</span><span class="sxs-lookup"><span data-stu-id="b9eee-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="b9eee-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="b9eee-357">down.esales360.cn</span></span>
<span data-ttu-id="b9eee-358">accountName</span><span class="sxs-lookup"><span data-stu-id="b9eee-358">accountName</span></span> | <span data-ttu-id="b9eee-359">Verfügbar, wenn EntityType *Benutzer* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="b9eee-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="b9eee-360">testUser2</span></span>
<span data-ttu-id="b9eee-361">Domänname</span><span class="sxs-lookup"><span data-stu-id="b9eee-361">domainName</span></span> | <span data-ttu-id="b9eee-362">Verfügbar, wenn EntityType *Benutzer* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="b9eee-363">Europe. Corp. contoso</span><span class="sxs-lookup"><span data-stu-id="b9eee-363">europe.corp.contoso</span></span>
<span data-ttu-id="b9eee-364">userSid</span><span class="sxs-lookup"><span data-stu-id="b9eee-364">userSid</span></span> | <span data-ttu-id="b9eee-365">Verfügbar, wenn EntityType *Benutzer* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="b9eee-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="b9eee-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="b9eee-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="b9eee-367">aadUserId</span></span> | <span data-ttu-id="b9eee-368">Verfügbar, wenn EntityType *Benutzer* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="b9eee-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="b9eee-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="b9eee-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="b9eee-370">userPrincipalName</span></span> | <span data-ttu-id="b9eee-371">Verfügbar, wenn EntityType *Benutzer* / *Postfach* / -e-*Mail* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="b9eee-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9eee-372">testUser2@contoso.com</span></span>
<span data-ttu-id="b9eee-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="b9eee-373">mailboxDisplayName</span></span> | <span data-ttu-id="b9eee-374">Verfügbar, wenn EntityType *Postfach* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="b9eee-375">Benutzer2 testen</span><span class="sxs-lookup"><span data-stu-id="b9eee-375">test User2</span></span>
<span data-ttu-id="b9eee-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="b9eee-376">mailboxAddress</span></span> | <span data-ttu-id="b9eee-377">Verfügbar, wenn EntityType *Benutzer* / *Postfach* / -e-*Mail* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="b9eee-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9eee-378">testUser2@contoso.com</span></span>
<span data-ttu-id="b9eee-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="b9eee-379">clusterBy</span></span> | <span data-ttu-id="b9eee-380">Verfügbar, wenn EntityType  *mailcluster* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="b9eee-381">Thema P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="b9eee-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="b9eee-382">sender</span><span class="sxs-lookup"><span data-stu-id="b9eee-382">sender</span></span> | <span data-ttu-id="b9eee-383">Verfügbar, wenn EntityType *Benutzer* / *Postfach* / -e-*Mail* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="b9eee-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="b9eee-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="b9eee-385">recipient</span><span class="sxs-lookup"><span data-stu-id="b9eee-385">recipient</span></span> | <span data-ttu-id="b9eee-386">Verfügbar, wenn EntityType *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="b9eee-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9eee-387">testUser2@contoso.com</span></span>
<span data-ttu-id="b9eee-388">subject</span><span class="sxs-lookup"><span data-stu-id="b9eee-388">subject</span></span> | <span data-ttu-id="b9eee-389">Verfügbar, wenn EntityType *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="b9eee-390">\[Externe \] Aufmerksamkeit</span><span class="sxs-lookup"><span data-stu-id="b9eee-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="b9eee-391">Zustellungs-Dienst</span><span class="sxs-lookup"><span data-stu-id="b9eee-391">deliveryAction</span></span> | <span data-ttu-id="b9eee-392">Verfügbar, wenn EntityType *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="b9eee-393">Geliefert</span><span class="sxs-lookup"><span data-stu-id="b9eee-393">Delivered</span></span>
<span data-ttu-id="b9eee-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="b9eee-394">securityGroupId</span></span> | <span data-ttu-id="b9eee-395">Verfügbar, wenn EntityType  *SecurityGroup* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="b9eee-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="b9eee-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="b9eee-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="b9eee-397">securityGroupName</span></span> | <span data-ttu-id="b9eee-398">Verfügbar, wenn EntityType  *SecurityGroup* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="b9eee-399">Netzwerk Konfigurations Operatoren</span><span class="sxs-lookup"><span data-stu-id="b9eee-399">Network Configuration Operators</span></span>
<span data-ttu-id="b9eee-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="b9eee-400">registryHive</span></span> | <span data-ttu-id="b9eee-401">Verfügbar, wenn EntityType in der  *Registrierung* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="b9eee-402">HKEY \_ lokaler \_ Computer</span><span class="sxs-lookup"><span data-stu-id="b9eee-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="b9eee-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="b9eee-403">registryKey</span></span> | <span data-ttu-id="b9eee-404">Verfügbar, wenn EntityType in der  *Registrierung* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="b9eee-405">Software\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="b9eee-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="b9eee-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="b9eee-406">registryValueType</span></span> | <span data-ttu-id="b9eee-407">Verfügbar, wenn EntityType in der  *Registrierung* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="b9eee-408">String</span><span class="sxs-lookup"><span data-stu-id="b9eee-408">String</span></span>
<span data-ttu-id="b9eee-409">REGISTRYVALUE</span><span class="sxs-lookup"><span data-stu-id="b9eee-409">registryValue</span></span> | <span data-ttu-id="b9eee-410">Verfügbar, wenn EntityType in der  *Registrierung* ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="b9eee-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="b9eee-411">31-00-00-00</span></span>
<span data-ttu-id="b9eee-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="b9eee-412">deviceId</span></span> | <span data-ttu-id="b9eee-413">Die ID (falls vorhanden) des Geräts, das mit der Entität verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="b9eee-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="b9eee-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="b9eee-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="b9eee-415">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9eee-415">Example</span></span>

<span data-ttu-id="b9eee-416">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="b9eee-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="b9eee-417">**Response**</span><span class="sxs-lookup"><span data-stu-id="b9eee-417">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="b9eee-418">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="b9eee-418">Related articles</span></span>

- [<span data-ttu-id="b9eee-419">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="b9eee-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="b9eee-420">Informationen zu API-Grenzwerten und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="b9eee-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="b9eee-421">Grundlegendes zu Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="b9eee-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="b9eee-422">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="b9eee-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b9eee-423">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="b9eee-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="b9eee-424">Update Incident API</span><span class="sxs-lookup"><span data-stu-id="b9eee-424">Update incident API</span></span>](api-update-incidents.md)

---
title: Api zum Auflisten von Vorfällen in Microsoft 365 Defender
description: Erfahren Sie, wie Sie die Vorfall-API in Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 038879e77dfa26d82add20d043a32de117f95b19
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287831"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="1dec2-104">Api zum Auflisten von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1dec2-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1dec2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1dec2-105">**Applies to:**</span></span>

- [<span data-ttu-id="1dec2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1dec2-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="1dec2-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="1dec2-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1dec2-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="1dec2-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="1dec2-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dec2-109">API description</span></span>

<span data-ttu-id="1dec2-110">Die API für Listenvorfälle ermöglicht es Ihnen, Vorfälle zu sortieren, um eine informierte Reaktion auf die Internetsicherheit zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1dec2-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="1dec2-111">Es macht eine Sammlung von Vorfällen verfügbar, die in Ihrem Netzwerk innerhalb des Zeitraums gekennzeichnet wurden, den Sie in Ihrer Aufbewahrungsrichtlinie für die Umgebung angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="1dec2-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="1dec2-112">Die neuesten Vorfälle werden oben in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1dec2-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="1dec2-113">Jeder Vorfall enthält ein Array verwandter Warnungen und zugehöriger Entitäten.</span><span class="sxs-lookup"><span data-stu-id="1dec2-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="1dec2-114">Die API unterstützt die folgenden **OData-Operatoren:**</span><span class="sxs-lookup"><span data-stu-id="1dec2-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="1dec2-115">`$filter`für die `lastUpdateTime` Eigenschaften `createdTime` , , `status` und `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="1dec2-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="1dec2-116">`$top`, mit einem Höchstwert von **100**</span><span class="sxs-lookup"><span data-stu-id="1dec2-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="1dec2-117">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1dec2-117">Limitations</span></span>

1. <span data-ttu-id="1dec2-118">Die maximale Seitengröße beträgt **100 Vorfälle.**</span><span class="sxs-lookup"><span data-stu-id="1dec2-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="1dec2-119">Die maximale Anzahl von Anforderungen beträgt **50 Anrufe pro Minute** und **1500 Anrufe pro Stunde.**</span><span class="sxs-lookup"><span data-stu-id="1dec2-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="1dec2-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1dec2-120">Permissions</span></span>

<span data-ttu-id="1dec2-121">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="1dec2-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1dec2-122">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access Microsoft 365 Defender-APIs.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="1dec2-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="1dec2-123">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="1dec2-123">Permission type</span></span> | <span data-ttu-id="1dec2-124">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1dec2-124">Permission</span></span> | <span data-ttu-id="1dec2-125">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1dec2-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="1dec2-126">Anwendung</span><span class="sxs-lookup"><span data-stu-id="1dec2-126">Application</span></span> | <span data-ttu-id="1dec2-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="1dec2-127">Incident.Read.All</span></span> | <span data-ttu-id="1dec2-128">Alle Vorfälle lesen</span><span class="sxs-lookup"><span data-stu-id="1dec2-128">Read all incidents</span></span>
<span data-ttu-id="1dec2-129">Anwendung</span><span class="sxs-lookup"><span data-stu-id="1dec2-129">Application</span></span> | <span data-ttu-id="1dec2-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="1dec2-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="1dec2-131">Lesen und Schreiben aller Vorfälle</span><span class="sxs-lookup"><span data-stu-id="1dec2-131">Read and write all incidents</span></span>
<span data-ttu-id="1dec2-132">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="1dec2-132">Delegated (work or school account)</span></span> | <span data-ttu-id="1dec2-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="1dec2-133">Incident.Read</span></span> | <span data-ttu-id="1dec2-134">Lesen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="1dec2-134">Read incidents</span></span>
<span data-ttu-id="1dec2-135">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="1dec2-135">Delegated (work or school account)</span></span> | <span data-ttu-id="1dec2-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1dec2-136">Incident.ReadWrite</span></span> | <span data-ttu-id="1dec2-137">Lesen und Schreiben von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="1dec2-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="1dec2-138">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="1dec2-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="1dec2-139">Der Benutzer muss über die Anzeigeberechtigung für Vorfälle im Portal verfügen.</span><span class="sxs-lookup"><span data-stu-id="1dec2-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="1dec2-140">Die Antwort enthält nur Vorfälle, denen der Benutzer ausgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="1dec2-141">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="1dec2-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="1dec2-142">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="1dec2-142">Request headers</span></span>

<span data-ttu-id="1dec2-143">Name</span><span class="sxs-lookup"><span data-stu-id="1dec2-143">Name</span></span> | <span data-ttu-id="1dec2-144">Typ</span><span class="sxs-lookup"><span data-stu-id="1dec2-144">Type</span></span> | <span data-ttu-id="1dec2-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dec2-145">Description</span></span>
-|-|-
<span data-ttu-id="1dec2-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="1dec2-146">Authorization</span></span> | <span data-ttu-id="1dec2-147">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1dec2-147">String</span></span> | <span data-ttu-id="1dec2-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1dec2-148">Bearer {token}.</span></span> <span data-ttu-id="1dec2-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="1dec2-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="1dec2-150">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="1dec2-150">Request body</span></span>

<span data-ttu-id="1dec2-151">Keine</span><span class="sxs-lookup"><span data-stu-id="1dec2-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="1dec2-152">Antwort</span><span class="sxs-lookup"><span data-stu-id="1dec2-152">Response</span></span>

<span data-ttu-id="1dec2-153">Bei erfolgreicher Ausführung gibt die Methode `200 OK` eine Liste der [Vorfälle](api-incident.md) im Antworttext zurück.</span><span class="sxs-lookup"><span data-stu-id="1dec2-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="1dec2-154">Schemazuordnung</span><span class="sxs-lookup"><span data-stu-id="1dec2-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="1dec2-155">Vorfallmetadaten</span><span class="sxs-lookup"><span data-stu-id="1dec2-155">Incident metadata</span></span>

<span data-ttu-id="1dec2-156">Feldname</span><span class="sxs-lookup"><span data-stu-id="1dec2-156">Field name</span></span> | <span data-ttu-id="1dec2-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dec2-157">Description</span></span> | <span data-ttu-id="1dec2-158">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="1dec2-158">Example value</span></span>
-|-|-
<span data-ttu-id="1dec2-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="1dec2-159">incidentId</span></span> | <span data-ttu-id="1dec2-160">Eindeutiger Bezeichner zur Darstellung des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="1dec2-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="1dec2-161">924565</span><span class="sxs-lookup"><span data-stu-id="1dec2-161">924565</span></span>
<span data-ttu-id="1dec2-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="1dec2-162">redirectIncidentId</span></span> | <span data-ttu-id="1dec2-163">Nur für den Fall, dass ein Vorfall mit einem anderen Vorfall gruppiert wird, als Teil der Logik für die Verarbeitung von Sicherheitsvorfällen.</span><span class="sxs-lookup"><span data-stu-id="1dec2-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="1dec2-164">924569</span><span class="sxs-lookup"><span data-stu-id="1dec2-164">924569</span></span>
<span data-ttu-id="1dec2-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="1dec2-165">incidentName</span></span> | <span data-ttu-id="1dec2-166">Für jeden Vorfall verfügbarer Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="1dec2-166">String value available for every incident.</span></span> | <span data-ttu-id="1dec2-167">Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="1dec2-167">Ransomware activity</span></span>
<span data-ttu-id="1dec2-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="1dec2-168">createdTime</span></span> | <span data-ttu-id="1dec2-169">Zeitpunkt, zu dem der Vorfall zum ersten Mal erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="1dec2-169">Time when incident was first created.</span></span> | <span data-ttu-id="1dec2-170">2020-09-06T14:46:57.073333Z</span><span class="sxs-lookup"><span data-stu-id="1dec2-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="1dec2-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="1dec2-171">lastUpdateTime</span></span> | <span data-ttu-id="1dec2-172">Zeitpunkt, zu dem der Vorfall zuletzt im Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1dec2-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="1dec2-173">Dieses Feld kann verwendet werden, wenn Sie den Anforderungsparameter für den Zeitraum festlegen, für den Vorfälle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1dec2-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="1dec2-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="1dec2-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="1dec2-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="1dec2-175">assignedTo</span></span> | <span data-ttu-id="1dec2-176">Besitzer des Vorfalls oder *NULL,* wenn kein Besitzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="1dec2-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1dec2-177">secop2@contoso.com</span></span>
<span data-ttu-id="1dec2-178">classification</span><span class="sxs-lookup"><span data-stu-id="1dec2-178">classification</span></span> | <span data-ttu-id="1dec2-179">Die Spezifikation für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="1dec2-179">The specification for the incident.</span></span> <span data-ttu-id="1dec2-180">Die Eigenschaftswerte sind: *Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="1dec2-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="1dec2-181">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="1dec2-181">Unknown</span></span>
<span data-ttu-id="1dec2-182">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="1dec2-182">determination</span></span> | <span data-ttu-id="1dec2-183">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="1dec2-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="1dec2-184">Die Eigenschaftswerte sind: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span><span class="sxs-lookup"><span data-stu-id="1dec2-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="1dec2-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="1dec2-185">NotAvailable</span></span>
<span data-ttu-id="1dec2-186">status</span><span class="sxs-lookup"><span data-stu-id="1dec2-186">status</span></span> | <span data-ttu-id="1dec2-187">Kategorisieren von Vorfällen (als *aktiv* oder *behoben).*</span><span class="sxs-lookup"><span data-stu-id="1dec2-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="1dec2-188">Es kann Ihnen helfen, Ihre Reaktion auf Vorfälle zu organisieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="1dec2-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="1dec2-189">Aktiv</span><span class="sxs-lookup"><span data-stu-id="1dec2-189">Active</span></span>
<span data-ttu-id="1dec2-190">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="1dec2-190">severity</span></span> | <span data-ttu-id="1dec2-191">Gibt die möglichen Auswirkungen auf Ressourcen an.</span><span class="sxs-lookup"><span data-stu-id="1dec2-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="1dec2-192">Je höher der Schweregrad, desto größer die Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="1dec2-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="1dec2-193">In der Regel erfordern Elemente mit höherem Schweregrad die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="1dec2-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="1dec2-194">Einer der folgenden Werte: *Informational*, *Low*, \*Medium und *High*.</span><span class="sxs-lookup"><span data-stu-id="1dec2-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="1dec2-195">Mittel</span><span class="sxs-lookup"><span data-stu-id="1dec2-195">Medium</span></span>
<span data-ttu-id="1dec2-196">tags</span><span class="sxs-lookup"><span data-stu-id="1dec2-196">tags</span></span> | <span data-ttu-id="1dec2-197">Array von benutzerdefinierten Tags, die einem Vorfall zugeordnet sind, z. B. zum Kennzeichnen einer Gruppe von Vorfällen mit einem gemeinsamen Merkmal.</span><span class="sxs-lookup"><span data-stu-id="1dec2-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="1dec2-198">Kommentare</span><span class="sxs-lookup"><span data-stu-id="1dec2-198">comments</span></span> | <span data-ttu-id="1dec2-199">Array von Kommentaren, die von Denkpunkten bei der Verwaltung des Vorfalls erstellt werden, z. B. zusätzliche Informationen zur Klassifizierungsauswahl.</span><span class="sxs-lookup"><span data-stu-id="1dec2-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="1dec2-200">Warnungen</span><span class="sxs-lookup"><span data-stu-id="1dec2-200">alerts</span></span> | <span data-ttu-id="1dec2-201">Array, das alle Warnungen im Zusammenhang mit dem Vorfall sowie andere Informationen enthält, z. B. Schweregrad, Entitäten, die an der Warnung beteiligt waren, und die Quelle der Warnungen.</span><span class="sxs-lookup"><span data-stu-id="1dec2-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="1dec2-202">\[\] (Details zu Warnungsfeldern finden Sie weiter unten)</span><span class="sxs-lookup"><span data-stu-id="1dec2-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="1dec2-203">Warnungsmetadaten</span><span class="sxs-lookup"><span data-stu-id="1dec2-203">Alerts metadata</span></span>

<span data-ttu-id="1dec2-204">Feldname</span><span class="sxs-lookup"><span data-stu-id="1dec2-204">Field name</span></span> | <span data-ttu-id="1dec2-205">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dec2-205">Description</span></span> | <span data-ttu-id="1dec2-206">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="1dec2-206">Example value</span></span>
-|-|-
<span data-ttu-id="1dec2-207">alertId</span><span class="sxs-lookup"><span data-stu-id="1dec2-207">alertId</span></span> | <span data-ttu-id="1dec2-208">Eindeutiger Bezeichner zur Darstellung der Warnung</span><span class="sxs-lookup"><span data-stu-id="1dec2-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="1dec2-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="1dec2-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="1dec2-210">incidentId</span><span class="sxs-lookup"><span data-stu-id="1dec2-210">incidentId</span></span> | <span data-ttu-id="1dec2-211">Eindeutiger Bezeichner zur Darstellung des Vorfalls, dem diese Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="1dec2-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="1dec2-212">924565</span><span class="sxs-lookup"><span data-stu-id="1dec2-212">924565</span></span>
<span data-ttu-id="1dec2-213">serviceSource</span><span class="sxs-lookup"><span data-stu-id="1dec2-213">serviceSource</span></span> | <span data-ttu-id="1dec2-214">Dienst, von dem die Warnung stammt, z. B. Microsoft Defender für Endpunkt, Microsoft Cloud App Security, Microsoft Defender for Identity oder Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="1dec2-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="1dec2-215">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="1dec2-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="1dec2-216">Creationtime</span><span class="sxs-lookup"><span data-stu-id="1dec2-216">creationTime</span></span> | <span data-ttu-id="1dec2-217">Zeitpunkt, zu dem die Warnung zum ersten Mal erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="1dec2-217">Time when alert was first created.</span></span> | <span data-ttu-id="1dec2-218">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="1dec2-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="1dec2-219">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="1dec2-219">lastUpdatedTime</span></span> | <span data-ttu-id="1dec2-220">Zeitpunkt, zu dem die Warnung zuletzt im Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1dec2-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="1dec2-221">2020-09-06T14:46:57.243333Z</span><span class="sxs-lookup"><span data-stu-id="1dec2-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="1dec2-222">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="1dec2-222">resolvedTime</span></span> | <span data-ttu-id="1dec2-223">Zeitpunkt, zu dem die Warnung aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="1dec2-223">Time when alert was resolved.</span></span> | <span data-ttu-id="1dec2-224">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="1dec2-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="1dec2-225">firstActivity</span><span class="sxs-lookup"><span data-stu-id="1dec2-225">firstActivity</span></span> | <span data-ttu-id="1dec2-226">Zeitpunkt, zu dem die Warnung zuerst gemeldet hat, dass die Aktivität im Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1dec2-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="1dec2-227">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="1dec2-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="1dec2-228">title</span><span class="sxs-lookup"><span data-stu-id="1dec2-228">title</span></span> | <span data-ttu-id="1dec2-229">Kurzes Identifizieren des Zeichenfolgenwerts, der für jede Warnung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="1dec2-230">Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="1dec2-230">Ransomware activity</span></span>
<span data-ttu-id="1dec2-231">description</span><span class="sxs-lookup"><span data-stu-id="1dec2-231">description</span></span> | <span data-ttu-id="1dec2-232">Zeichenfolgenwert, der die einzelnen Warnungen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="1dec2-232">String value describing each alert.</span></span> | <span data-ttu-id="1dec2-233">Der Benutzer Test User2 (testUser2@contoso.com) hat 99 Dateien mit mehreren Erweiterungen bearbeitet, die mit der ungewöhnlichen Erweiterung *herunterladen* enden.</span><span class="sxs-lookup"><span data-stu-id="1dec2-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="1dec2-234">Dies ist eine ungewöhnliche Anzahl von Dateimanipulationen und ein Hinweis auf einen potenziellen Ransomware-Angriff.</span><span class="sxs-lookup"><span data-stu-id="1dec2-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="1dec2-235">category</span><span class="sxs-lookup"><span data-stu-id="1dec2-235">category</span></span> | <span data-ttu-id="1dec2-236">Visuelle und numerische Ansicht, wie weit der Angriff entlang der Kill Chain fortgeschritten ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="1dec2-237">Ausgerichtet am [MITRE ATT&CK™ Framework.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="1dec2-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="1dec2-238">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="1dec2-238">Impact</span></span>
<span data-ttu-id="1dec2-239">status</span><span class="sxs-lookup"><span data-stu-id="1dec2-239">status</span></span> | <span data-ttu-id="1dec2-240">Kategorisieren Sie Warnungen (als *neu,* *aktiv* oder *aufgelöst).*</span><span class="sxs-lookup"><span data-stu-id="1dec2-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="1dec2-241">Es kann Ihnen helfen, Ihre Reaktion auf Warnungen zu organisieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="1dec2-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="1dec2-242">Neu</span><span class="sxs-lookup"><span data-stu-id="1dec2-242">New</span></span>
<span data-ttu-id="1dec2-243">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="1dec2-243">severity</span></span> | <span data-ttu-id="1dec2-244">Gibt die möglichen Auswirkungen auf Ressourcen an.</span><span class="sxs-lookup"><span data-stu-id="1dec2-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="1dec2-245">Je höher der Schweregrad, desto größer die Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="1dec2-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="1dec2-246">In der Regel erfordern Elemente mit höherem Schweregrad die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="1dec2-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="1dec2-247">Einer der folgenden Werte: *Informational*, *Low*, \*Medium und *High*.</span><span class="sxs-lookup"><span data-stu-id="1dec2-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="1dec2-248">Mittel</span><span class="sxs-lookup"><span data-stu-id="1dec2-248">Medium</span></span>
<span data-ttu-id="1dec2-249">investigationId</span><span class="sxs-lookup"><span data-stu-id="1dec2-249">investigationId</span></span> | <span data-ttu-id="1dec2-250">Die durch diese Warnung ausgelöste automatisierte Untersuchungs-ID.</span><span class="sxs-lookup"><span data-stu-id="1dec2-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="1dec2-251">1234</span><span class="sxs-lookup"><span data-stu-id="1dec2-251">1234</span></span>
<span data-ttu-id="1dec2-252">investigationState</span><span class="sxs-lookup"><span data-stu-id="1dec2-252">investigationState</span></span> | <span data-ttu-id="1dec2-253">Informationen zum aktuellen Status der Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="1dec2-253">Information on the investigation's current status.</span></span> <span data-ttu-id="1dec2-254">Einer der folgenden Werte: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="1dec2-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="1dec2-255">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="1dec2-255">UnsupportedAlertType</span></span>
<span data-ttu-id="1dec2-256">classification</span><span class="sxs-lookup"><span data-stu-id="1dec2-256">classification</span></span> | <span data-ttu-id="1dec2-257">Die Spezifikation für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="1dec2-257">The specification for the incident.</span></span> <span data-ttu-id="1dec2-258">Die Eigenschaftswerte sind: *Unknown*, *FalsePositive*, *TruePositive* oder *null*</span><span class="sxs-lookup"><span data-stu-id="1dec2-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="1dec2-259">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="1dec2-259">Unknown</span></span>
<span data-ttu-id="1dec2-260">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="1dec2-260">determination</span></span> | <span data-ttu-id="1dec2-261">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="1dec2-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="1dec2-262">Die Eigenschaftswerte sind: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* oder  *null*</span><span class="sxs-lookup"><span data-stu-id="1dec2-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="1dec2-263">Apt</span><span class="sxs-lookup"><span data-stu-id="1dec2-263">Apt</span></span>
<span data-ttu-id="1dec2-264">assignedTo</span><span class="sxs-lookup"><span data-stu-id="1dec2-264">assignedTo</span></span> | <span data-ttu-id="1dec2-265">Besitzer des Vorfalls oder *NULL,* wenn kein Besitzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="1dec2-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1dec2-266">secop2@contoso.com</span></span>
<span data-ttu-id="1dec2-267">actorName</span><span class="sxs-lookup"><span data-stu-id="1dec2-267">actorName</span></span> | <span data-ttu-id="1dec2-268">Die Aktivitätsgruppe, falls vorhanden, die dieser Warnung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="1dec2-269">Bor</span><span class="sxs-lookup"><span data-stu-id="1dec2-269">BORON</span></span>
<span data-ttu-id="1dec2-270">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="1dec2-270">threatFamilyName</span></span> | <span data-ttu-id="1dec2-271">Dieser Warnung zugeordnete Bedrohungsfamilie.</span><span class="sxs-lookup"><span data-stu-id="1dec2-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="1dec2-272">null</span><span class="sxs-lookup"><span data-stu-id="1dec2-272">null</span></span>
<span data-ttu-id="1dec2-273">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="1dec2-273">mitreTechniques</span></span> | <span data-ttu-id="1dec2-274">Die Angriffstechniken, wie sie dem [MITRE ATT&CK](https://attack.mitre.org/)™ Framework entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1dec2-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="1dec2-275">Geräte</span><span class="sxs-lookup"><span data-stu-id="1dec2-275">devices</span></span> | <span data-ttu-id="1dec2-276">Alle Geräte, auf denen Warnungen im Zusammenhang mit dem Vorfall gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="1dec2-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="1dec2-277">\[\] (Details zu Entitätsfeldern finden Sie weiter unten)</span><span class="sxs-lookup"><span data-stu-id="1dec2-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="1dec2-278">Geräteformat</span><span class="sxs-lookup"><span data-stu-id="1dec2-278">Device format</span></span>

<span data-ttu-id="1dec2-279">Feldname</span><span class="sxs-lookup"><span data-stu-id="1dec2-279">Field name</span></span> | <span data-ttu-id="1dec2-280">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dec2-280">Description</span></span> | <span data-ttu-id="1dec2-281">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="1dec2-281">Example value</span></span>
-|-|-
<span data-ttu-id="1dec2-282">Deviceid</span><span class="sxs-lookup"><span data-stu-id="1dec2-282">DeviceId</span></span> | <span data-ttu-id="1dec2-283">Die Geräte-ID wie in Microsoft Defender für Endpunkt angegeben.</span><span class="sxs-lookup"><span data-stu-id="1dec2-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="1dec2-284">24c222b0b60fe148eece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="1dec2-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="1dec2-285">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="1dec2-285">aadDeviceId</span></span> |  <span data-ttu-id="1dec2-286">Die In [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis)angegebene Geräte-ID.</span><span class="sxs-lookup"><span data-stu-id="1dec2-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="1dec2-287">Nur für Geräte verfügbar, die in die Domäne eingebunden sind.</span><span class="sxs-lookup"><span data-stu-id="1dec2-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="1dec2-288">null</span><span class="sxs-lookup"><span data-stu-id="1dec2-288">null</span></span>
<span data-ttu-id="1dec2-289">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="1dec2-289">deviceDnsName</span></span> | <span data-ttu-id="1dec2-290">Der vollqualifizierte Domänenname für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="1dec2-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="1dec2-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1dec2-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="1dec2-292">osPlatform</span><span class="sxs-lookup"><span data-stu-id="1dec2-292">osPlatform</span></span> | <span data-ttu-id="1dec2-293">Die Betriebssystemplattform, auf der das Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1dec2-293">The OS platform the device is running.</span></span>| <span data-ttu-id="1dec2-294">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="1dec2-294">WindowsServer2016</span></span>
<span data-ttu-id="1dec2-295">osBuild</span><span class="sxs-lookup"><span data-stu-id="1dec2-295">osBuild</span></span> | <span data-ttu-id="1dec2-296">Die Buildversion für das Betriebssystem, auf dem das Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1dec2-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="1dec2-297">14393</span><span class="sxs-lookup"><span data-stu-id="1dec2-297">14393</span></span>
<span data-ttu-id="1dec2-298">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="1dec2-298">rbacGroupName</span></span> | <span data-ttu-id="1dec2-299">Die [rollenbasierte Zugriffssteuerungsgruppe](/azure/role-based-access-control/overview) (RBAC), die dem Gerät zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="1dec2-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="1dec2-300">WDATP-Ring0</span></span>
<span data-ttu-id="1dec2-301">firstSeen</span><span class="sxs-lookup"><span data-stu-id="1dec2-301">firstSeen</span></span> | <span data-ttu-id="1dec2-302">Zeitpunkt, zu dem das Gerät zum ersten Mal angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="1dec2-302">Time when device was first seen.</span></span> | <span data-ttu-id="1dec2-303">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="1dec2-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="1dec2-304">healthStatus</span><span class="sxs-lookup"><span data-stu-id="1dec2-304">healthStatus</span></span> | <span data-ttu-id="1dec2-305">Der Integritätsstatus des Geräts.</span><span class="sxs-lookup"><span data-stu-id="1dec2-305">The health state of the device.</span></span> | <span data-ttu-id="1dec2-306">Aktiv</span><span class="sxs-lookup"><span data-stu-id="1dec2-306">Active</span></span>
<span data-ttu-id="1dec2-307">riskScore</span><span class="sxs-lookup"><span data-stu-id="1dec2-307">riskScore</span></span> | <span data-ttu-id="1dec2-308">Die Risikobewertung für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="1dec2-308">The risk score for the  device.</span></span> | <span data-ttu-id="1dec2-309">Hoch</span><span class="sxs-lookup"><span data-stu-id="1dec2-309">High</span></span>
<span data-ttu-id="1dec2-310">Entitäten</span><span class="sxs-lookup"><span data-stu-id="1dec2-310">entities</span></span> | <span data-ttu-id="1dec2-311">Alle Entitäten, die als Teil einer bestimmten Warnung identifiziert wurden oder mit dieser verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="1dec2-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="1dec2-312">\[\] (Details zu Entitätsfeldern finden Sie weiter unten)</span><span class="sxs-lookup"><span data-stu-id="1dec2-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="1dec2-313">Entitätsformat</span><span class="sxs-lookup"><span data-stu-id="1dec2-313">Entity Format</span></span>

<span data-ttu-id="1dec2-314">Feldname</span><span class="sxs-lookup"><span data-stu-id="1dec2-314">Field name</span></span> | <span data-ttu-id="1dec2-315">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dec2-315">Description</span></span> | <span data-ttu-id="1dec2-316">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="1dec2-316">Example value</span></span>
-|-|-
<span data-ttu-id="1dec2-317">Entitytype</span><span class="sxs-lookup"><span data-stu-id="1dec2-317">entityType</span></span> | <span data-ttu-id="1dec2-318">Entitäten, die als Teil einer bestimmten Warnung identifiziert wurden oder mit dieser verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="1dec2-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="1dec2-319">Die Eigenschaftenwerte sind: *User*, *Ip*, *URL*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span><span class="sxs-lookup"><span data-stu-id="1dec2-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="1dec2-320">Benutzer</span><span class="sxs-lookup"><span data-stu-id="1dec2-320">User</span></span>
<span data-ttu-id="1dec2-321">sha1</span><span class="sxs-lookup"><span data-stu-id="1dec2-321">sha1</span></span> | <span data-ttu-id="1dec2-322">Verfügbar, wenn entityType *File* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="1dec2-323">Der Dateihash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1dec2-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="1dec2-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="1dec2-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="1dec2-325">sha256</span><span class="sxs-lookup"><span data-stu-id="1dec2-325">sha256</span></span> | <span data-ttu-id="1dec2-326">Verfügbar, wenn entityType *File* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="1dec2-327">Der Dateihash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1dec2-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="1dec2-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="1dec2-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="1dec2-329">fileName</span><span class="sxs-lookup"><span data-stu-id="1dec2-329">fileName</span></span> | <span data-ttu-id="1dec2-330">Verfügbar, wenn entityType *File* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="1dec2-331">Der Dateiname für Warnungen, die einer Datei oder einem Prozess zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="1dec2-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="1dec2-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="1dec2-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="1dec2-333">Filepath</span><span class="sxs-lookup"><span data-stu-id="1dec2-333">filePath</span></span> | <span data-ttu-id="1dec2-334">Verfügbar, wenn entityType *File* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="1dec2-335">Der Dateipfad für Warnungen, die einer Datei oder einem Prozess zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="1dec2-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="1dec2-336">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="1dec2-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="1dec2-337">Processid</span><span class="sxs-lookup"><span data-stu-id="1dec2-337">processId</span></span> | <span data-ttu-id="1dec2-338">Verfügbar, wenn entityType *Process* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="1dec2-339">24348</span><span class="sxs-lookup"><span data-stu-id="1dec2-339">24348</span></span>
<span data-ttu-id="1dec2-340">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="1dec2-340">processCommandLine</span></span> | <span data-ttu-id="1dec2-341">Verfügbar, wenn entityType *Process* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="1dec2-342">"Ihre Datei kann1911150169.exe heruntergeladen \_ werden"</span><span class="sxs-lookup"><span data-stu-id="1dec2-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="1dec2-343">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="1dec2-343">processCreationTime</span></span> | <span data-ttu-id="1dec2-344">Verfügbar, wenn entityType *Process* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="1dec2-345">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="1dec2-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="1dec2-346">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="1dec2-346">parentProcessId</span></span> | <span data-ttu-id="1dec2-347">Verfügbar, wenn entityType *Process* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="1dec2-348">16840</span><span class="sxs-lookup"><span data-stu-id="1dec2-348">16840</span></span>
<span data-ttu-id="1dec2-349">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="1dec2-349">parentProcessCreationTime</span></span> | <span data-ttu-id="1dec2-350">Verfügbar, wenn entityType *Process* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="1dec2-351">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="1dec2-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="1dec2-352">ipAddress</span><span class="sxs-lookup"><span data-stu-id="1dec2-352">ipAddress</span></span> | <span data-ttu-id="1dec2-353">Verfügbar, wenn entityType *ip* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="1dec2-354">IP-Adresse für Warnungen im Zusammenhang mit Netzwerkereignissen, *z. B. Kommunikation mit einem schädlichen Netzwerkziel.*</span><span class="sxs-lookup"><span data-stu-id="1dec2-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="1dec2-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="1dec2-355">62.216.203.204</span></span>
<span data-ttu-id="1dec2-356">url</span><span class="sxs-lookup"><span data-stu-id="1dec2-356">url</span></span> | <span data-ttu-id="1dec2-357">Verfügbar, wenn entityType *url* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="1dec2-358">Url für Warnungen, die Netzwerkereignissen zugeordnet sind, z. *B. Kommunikation mit einem schädlichen Netzwerkziel.*</span><span class="sxs-lookup"><span data-stu-id="1dec2-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="1dec2-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="1dec2-359">down.esales360.cn</span></span>
<span data-ttu-id="1dec2-360">Accountname</span><span class="sxs-lookup"><span data-stu-id="1dec2-360">accountName</span></span> | <span data-ttu-id="1dec2-361">Verfügbar, wenn entityType *User* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="1dec2-362">testUser2</span><span class="sxs-lookup"><span data-stu-id="1dec2-362">testUser2</span></span>
<span data-ttu-id="1dec2-363">Domänname</span><span class="sxs-lookup"><span data-stu-id="1dec2-363">domainName</span></span> | <span data-ttu-id="1dec2-364">Verfügbar, wenn entityType *User* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="1dec2-365">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="1dec2-365">europe.corp.contoso</span></span>
<span data-ttu-id="1dec2-366">userSid</span><span class="sxs-lookup"><span data-stu-id="1dec2-366">userSid</span></span> | <span data-ttu-id="1dec2-367">Verfügbar, wenn entityType *User* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="1dec2-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="1dec2-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="1dec2-369">aadUserId</span><span class="sxs-lookup"><span data-stu-id="1dec2-369">aadUserId</span></span> | <span data-ttu-id="1dec2-370">Verfügbar, wenn entityType *User* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="1dec2-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="1dec2-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="1dec2-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="1dec2-372">userPrincipalName</span></span> | <span data-ttu-id="1dec2-373">Verfügbar, wenn entityType *User* / *MailBox* / *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="1dec2-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1dec2-374">testUser2@contoso.com</span></span>
<span data-ttu-id="1dec2-375">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="1dec2-375">mailboxDisplayName</span></span> | <span data-ttu-id="1dec2-376">Verfügbar, wenn entityType *MailBox* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="1dec2-377">Testbenutzer2</span><span class="sxs-lookup"><span data-stu-id="1dec2-377">test User2</span></span>
<span data-ttu-id="1dec2-378">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="1dec2-378">mailboxAddress</span></span> | <span data-ttu-id="1dec2-379">Verfügbar, wenn entityType *User* / *MailBox* / *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="1dec2-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1dec2-380">testUser2@contoso.com</span></span>
<span data-ttu-id="1dec2-381">clusterBy</span><span class="sxs-lookup"><span data-stu-id="1dec2-381">clusterBy</span></span> | <span data-ttu-id="1dec2-382">Verfügbar, wenn entityType  *MailCluster* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="1dec2-383">Betreff; P2SenderDomain; Contenttype</span><span class="sxs-lookup"><span data-stu-id="1dec2-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="1dec2-384">sender</span><span class="sxs-lookup"><span data-stu-id="1dec2-384">sender</span></span> | <span data-ttu-id="1dec2-385">Verfügbar, wenn entityType *User* / *MailBox* / *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="1dec2-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="1dec2-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="1dec2-387">recipient</span><span class="sxs-lookup"><span data-stu-id="1dec2-387">recipient</span></span> | <span data-ttu-id="1dec2-388">Verfügbar, wenn entityType *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="1dec2-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1dec2-389">testUser2@contoso.com</span></span>
<span data-ttu-id="1dec2-390">subject</span><span class="sxs-lookup"><span data-stu-id="1dec2-390">subject</span></span> | <span data-ttu-id="1dec2-391">Verfügbar, wenn entityType *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="1dec2-392">\[Externe \] Aufmerksamkeit</span><span class="sxs-lookup"><span data-stu-id="1dec2-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="1dec2-393">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="1dec2-393">deliveryAction</span></span> | <span data-ttu-id="1dec2-394">Verfügbar, wenn entityType *MailMessage* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="1dec2-395">Geliefert</span><span class="sxs-lookup"><span data-stu-id="1dec2-395">Delivered</span></span>
<span data-ttu-id="1dec2-396">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="1dec2-396">securityGroupId</span></span> | <span data-ttu-id="1dec2-397">Verfügbar, wenn entityType  *SecurityGroup* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="1dec2-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="1dec2-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="1dec2-399">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="1dec2-399">securityGroupName</span></span> | <span data-ttu-id="1dec2-400">Verfügbar, wenn entityType  *SecurityGroup* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="1dec2-401">Netzwerkkonfigurationsoperatoren</span><span class="sxs-lookup"><span data-stu-id="1dec2-401">Network Configuration Operators</span></span>
<span data-ttu-id="1dec2-402">registryHive</span><span class="sxs-lookup"><span data-stu-id="1dec2-402">registryHive</span></span> | <span data-ttu-id="1dec2-403">Verfügbar, wenn entityType  *registry* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="1dec2-404">HKEY \_ LOCAL \_ MACHINE</span><span class="sxs-lookup"><span data-stu-id="1dec2-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="1dec2-405">Registrykey</span><span class="sxs-lookup"><span data-stu-id="1dec2-405">registryKey</span></span> | <span data-ttu-id="1dec2-406">Verfügbar, wenn entityType  *registry* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="1dec2-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="1dec2-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="1dec2-408">registryValueType</span><span class="sxs-lookup"><span data-stu-id="1dec2-408">registryValueType</span></span> | <span data-ttu-id="1dec2-409">Verfügbar, wenn entityType  *registry* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="1dec2-410">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1dec2-410">String</span></span>
<span data-ttu-id="1dec2-411">registryValue</span><span class="sxs-lookup"><span data-stu-id="1dec2-411">registryValue</span></span> | <span data-ttu-id="1dec2-412">Verfügbar, wenn entityType  *registry* ist.</span><span class="sxs-lookup"><span data-stu-id="1dec2-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="1dec2-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="1dec2-413">31-00-00-00</span></span>
<span data-ttu-id="1dec2-414">deviceId</span><span class="sxs-lookup"><span data-stu-id="1dec2-414">deviceId</span></span> | <span data-ttu-id="1dec2-415">Die ID (sofern vorhanden) des Geräts, das sich auf die Entität bezieht.</span><span class="sxs-lookup"><span data-stu-id="1dec2-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="1dec2-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="1dec2-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="1dec2-417">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1dec2-417">Example</span></span>

### <a name="request"></a><span data-ttu-id="1dec2-418">Anforderung</span><span class="sxs-lookup"><span data-stu-id="1dec2-418">Request</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

### <a name="response"></a><span data-ttu-id="1dec2-419">Antwort</span><span class="sxs-lookup"><span data-stu-id="1dec2-419">Response</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="1dec2-420">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="1dec2-420">Related articles</span></span>

- [<span data-ttu-id="1dec2-421">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="1dec2-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="1dec2-422">Informationen zu API-Beschränkungen und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="1dec2-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="1dec2-423">Grundlegendes zu Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="1dec2-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="1dec2-424">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="1dec2-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1dec2-425">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="1dec2-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="1dec2-426">Api zum Aktualisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="1dec2-426">Update incident API</span></span>](api-update-incidents.md)

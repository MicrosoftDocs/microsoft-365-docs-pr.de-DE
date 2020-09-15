---
title: Listen Vorfälle-API in Microsoft Threat Protection
description: Informationen zum Auflisten von Vorfälle-API in Microsoft Threat Protection
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
ms.openlocfilehash: 54f5ba640ecc175e78c7087df8016e9b715f17f7
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775111"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a><span data-ttu-id="15e2a-104">Listen Vorfälle-API in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="15e2a-104">List incidents API in Microsoft Threat Protection</span></span>

<span data-ttu-id="15e2a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="15e2a-105">**Applies to:**</span></span>

- <span data-ttu-id="15e2a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="15e2a-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15e2a-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="15e2a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="15e2a-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="15e2a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="15e2a-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15e2a-109">API description</span></span>

<span data-ttu-id="15e2a-110">Die Vorfall-API ermöglicht das Sortieren von Vorfällen, um Prioritäten zu setzen und eine informierte Cyber-Antwort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="15e2a-110">The Incident API allows you to sort through incidents to prioritize and create an informed cybersecurity response.</span></span> <span data-ttu-id="15e2a-111">Es macht eine Sammlung von Vorfällen verfügbar, die von Geräten, e-Mail-Konten und Benutzern in Ihrem Netzwerk gekennzeichnet wurden, innerhalb des Zeitbereichs, den Sie in der Aufbewahrungsrichtlinie für die Umgebung angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="15e2a-111">It exposes a collection of incidents that were flagged from devices, email accounts, and users in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="15e2a-112">Die jüngsten Vorfälle werden oben in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15e2a-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="15e2a-113">Jeder Vorfall enthält ein Array zusammengehöriger Warnungen und zugehöriger Entitäten.</span><span class="sxs-lookup"><span data-stu-id="15e2a-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<br><span data-ttu-id="15e2a-114">Die API unterstützt die folgenden **OData** -Operatoren:</span><span class="sxs-lookup"><span data-stu-id="15e2a-114">The API supports the following **OData** operators:</span></span>
<br><span data-ttu-id="15e2a-115">```$filter``` on: ```lastUpdateTime``` , ```createdTime``` ```status``` und ```assignedTo``` Properties.</span><span class="sxs-lookup"><span data-stu-id="15e2a-115">```$filter``` on: ```lastUpdateTime```, ```createdTime```, ```status``` and ```assignedTo``` properties.</span></span>
<br><span data-ttu-id="15e2a-116">```$top``` mit dem Höchstwert von **100**</span><span class="sxs-lookup"><span data-stu-id="15e2a-116">```$top``` with max value of **100**</span></span>
<br>```$skip```

## <a name="limitations"></a><span data-ttu-id="15e2a-117">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="15e2a-117">Limitations</span></span>

1. <span data-ttu-id="15e2a-118">Die maximale Seitengröße beträgt **100 Vorfälle**.</span><span class="sxs-lookup"><span data-stu-id="15e2a-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="15e2a-119">Die maximale Anzahl von Anforderungen beträgt **50 Anrufe pro Minute** und **1500 Anrufe pro Stunde**.</span><span class="sxs-lookup"><span data-stu-id="15e2a-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="15e2a-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="15e2a-120">Permissions</span></span>

<span data-ttu-id="15e2a-121">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="15e2a-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="15e2a-122">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access Microsoft Threat Protection APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="15e2a-122">To learn more, including how to choose permissions, see [Access Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="15e2a-123">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="15e2a-123">Permission type</span></span> |   <span data-ttu-id="15e2a-124">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="15e2a-124">Permission</span></span>  |   <span data-ttu-id="15e2a-125">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="15e2a-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="15e2a-126">Anwendung</span><span class="sxs-lookup"><span data-stu-id="15e2a-126">Application</span></span> |   <span data-ttu-id="15e2a-127">Vorfall. Read. all</span><span class="sxs-lookup"><span data-stu-id="15e2a-127">Incident.Read.All</span></span> | <span data-ttu-id="15e2a-128">"Alle Vorfälle lesen"</span><span class="sxs-lookup"><span data-stu-id="15e2a-128">'Read all incidents'</span></span>
<span data-ttu-id="15e2a-129">Anwendung</span><span class="sxs-lookup"><span data-stu-id="15e2a-129">Application</span></span> |   <span data-ttu-id="15e2a-130">Incident. ReadWrite. all</span><span class="sxs-lookup"><span data-stu-id="15e2a-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="15e2a-131">"Alle Vorfälle lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="15e2a-131">'Read and write all incidents'</span></span>
<span data-ttu-id="15e2a-132">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="15e2a-132">Delegated (work or school account)</span></span> | <span data-ttu-id="15e2a-133">Vorfall. Read</span><span class="sxs-lookup"><span data-stu-id="15e2a-133">Incident.Read</span></span> | <span data-ttu-id="15e2a-134">"Vorfälle lesen"</span><span class="sxs-lookup"><span data-stu-id="15e2a-134">'Read incidents'</span></span>
<span data-ttu-id="15e2a-135">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="15e2a-135">Delegated (work or school account)</span></span> | <span data-ttu-id="15e2a-136">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="15e2a-136">Incident.ReadWrite</span></span> | <span data-ttu-id="15e2a-137">' Lesen und Schreiben von Vorfällen '</span><span class="sxs-lookup"><span data-stu-id="15e2a-137">'Read and write incidents'</span></span>

> [!Note]
> <span data-ttu-id="15e2a-138">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="15e2a-138">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="15e2a-139">Der Benutzer muss über die Berechtigung "anzeigen" für Vorfälle im Portal verfügen.</span><span class="sxs-lookup"><span data-stu-id="15e2a-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="15e2a-140">Die Antwort umfasst nur Vorfälle, denen der Benutzer ausgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="15e2a-141">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="15e2a-141">HTTP request</span></span>

```
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="15e2a-142">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="15e2a-142">Request headers</span></span>

<span data-ttu-id="15e2a-143">Name</span><span class="sxs-lookup"><span data-stu-id="15e2a-143">Name</span></span> | <span data-ttu-id="15e2a-144">Typ</span><span class="sxs-lookup"><span data-stu-id="15e2a-144">Type</span></span> | <span data-ttu-id="15e2a-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15e2a-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="15e2a-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="15e2a-146">Authorization</span></span> | <span data-ttu-id="15e2a-147">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="15e2a-147">String</span></span> | <span data-ttu-id="15e2a-148">Bearer {Token}.</span><span class="sxs-lookup"><span data-stu-id="15e2a-148">Bearer {token}.</span></span> <span data-ttu-id="15e2a-149">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="15e2a-149">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="15e2a-150">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="15e2a-150">Request body</span></span>
<span data-ttu-id="15e2a-151">Keine</span><span class="sxs-lookup"><span data-stu-id="15e2a-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="15e2a-152">Antwort</span><span class="sxs-lookup"><span data-stu-id="15e2a-152">Response</span></span>
<span data-ttu-id="15e2a-153">Wenn die Methode erfolgreich verläuft, werden 200 OK und eine Liste von [Vorfällen](api-incident.md) im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="15e2a-153">If successful, this method returns 200 OK, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="15e2a-154">Schema Zuordnung</span><span class="sxs-lookup"><span data-stu-id="15e2a-154">Schema mapping</span></span>

| <span data-ttu-id="15e2a-155">Feldname</span><span class="sxs-lookup"><span data-stu-id="15e2a-155">Field name</span></span>                                | <span data-ttu-id="15e2a-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15e2a-156">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="15e2a-157">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="15e2a-157">Example value</span></span>                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="15e2a-158">**Vorfall Metadaten**</span><span class="sxs-lookup"><span data-stu-id="15e2a-158">**Incident metadata**</span></span>                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="15e2a-159">Vorfall-Nr</span><span class="sxs-lookup"><span data-stu-id="15e2a-159">incidentId</span></span>                                | <span data-ttu-id="15e2a-160">Eindeutiger Bezeichner, der den Vorfall darstellt.</span><span class="sxs-lookup"><span data-stu-id="15e2a-160">Unique identifier to represent the incident.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="15e2a-161">924565</span><span class="sxs-lookup"><span data-stu-id="15e2a-161">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="15e2a-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="15e2a-162">redirectIncidentId</span></span>                        | <span data-ttu-id="15e2a-163">Nur aufgefüllt, wenn ein Vorfall als Teil der Vorfall Verarbeitungslogik mit einem anderen Vorfall zusammengefasst wird.</span><span class="sxs-lookup"><span data-stu-id="15e2a-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span>                                                                                                                                                                                                                                                           | <span data-ttu-id="15e2a-164">924569</span><span class="sxs-lookup"><span data-stu-id="15e2a-164">924569</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="15e2a-165">Vorfallname</span><span class="sxs-lookup"><span data-stu-id="15e2a-165">incidentName</span></span>                              | <span data-ttu-id="15e2a-166">Zeichenfolgenwert, der für jeden Vorfall verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-166">String value available for every incident.</span></span>                                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="15e2a-167">Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="15e2a-167">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="15e2a-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="15e2a-168">createdTime</span></span>                               | <span data-ttu-id="15e2a-169">Zeitpunkt, zu dem der Vorfall erstmals erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="15e2a-169">Time when incident was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                      | <span data-ttu-id="15e2a-170">2020-09-06T14:46:57.0733333 z</span><span class="sxs-lookup"><span data-stu-id="15e2a-170">2020-09-06T14:46:57.0733333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="15e2a-171">Last Update time</span><span class="sxs-lookup"><span data-stu-id="15e2a-171">lastUpdateTime</span></span>                            | <span data-ttu-id="15e2a-172">Zeitpunkt der letzten Aktualisierung des Vorfalls im Back-End.</span><span class="sxs-lookup"><span data-stu-id="15e2a-172">Time when incident was last updated at the backend.</span></span><br> <span data-ttu-id="15e2a-173">Dieses Feld kann verwendet werden, wenn der Anforderungsparameter für den Zeitraum festgelegt wird, in dem Vorfälle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="15e2a-173">This field can be used when setting the request parameter for the range of time that incidents are retrieved.</span></span>                                                                                                                                                                                                                      | <span data-ttu-id="15e2a-174">2020-09-06T14:46:57.29 z</span><span class="sxs-lookup"><span data-stu-id="15e2a-174">2020-09-06T14:46:57.29Z</span></span>                                                                                                                                                                                                                           |
| <span data-ttu-id="15e2a-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="15e2a-175">assignedTo</span></span>                                | <span data-ttu-id="15e2a-176">Der Besitzer des Vorfalls oder *null* , wenn kein Besitzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-176">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="15e2a-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="15e2a-177">secop2@contoso.com</span></span>                                                                                                                                                                                                |
| <span data-ttu-id="15e2a-178">classification</span><span class="sxs-lookup"><span data-stu-id="15e2a-178">classification</span></span>                            | <span data-ttu-id="15e2a-179">Die Spezifikation für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="15e2a-179">The specification for the incident.</span></span> <span data-ttu-id="15e2a-180">Die Eigenschaftswerte lauten: *unbekannt*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="15e2a-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span>                                                                                                                                                                                                                                                                           | <span data-ttu-id="15e2a-181">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="15e2a-181">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="15e2a-182">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="15e2a-182">determination</span></span>                             | <span data-ttu-id="15e2a-183">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="15e2a-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="15e2a-184">Die Eigenschaftswerte lauten: *nichtin*, *apt*, *Schadsoftware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other*</span><span class="sxs-lookup"><span data-stu-id="15e2a-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span>                                                                                                                                                                                                                | <span data-ttu-id="15e2a-185">Nichtin</span><span class="sxs-lookup"><span data-stu-id="15e2a-185">NotAvailable</span></span>                                                                                                                                                                                                                                      |
| <span data-ttu-id="15e2a-186">status</span><span class="sxs-lookup"><span data-stu-id="15e2a-186">status</span></span>                                    | <span data-ttu-id="15e2a-187">Vorfälle kategorisieren (als *aktiv*oder *aufgelöst*).</span><span class="sxs-lookup"><span data-stu-id="15e2a-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="15e2a-188">Auf diese Weise können Sie Ihre Antwort auf Vorfälle organisieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="15e2a-188">This helps you organize and manage your response to incidents.</span></span>                                                                                                                                                                                                                                                                  | <span data-ttu-id="15e2a-189">Aktiv</span><span class="sxs-lookup"><span data-stu-id="15e2a-189">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="15e2a-190">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="15e2a-190">severity</span></span>                                  | <span data-ttu-id="15e2a-191">Gibt die möglichen Auswirkungen auf Objekte an.</span><span class="sxs-lookup"><span data-stu-id="15e2a-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="15e2a-192">Je höher der Schweregrad, desto größer die Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="15e2a-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="15e2a-193">Normalerweise erfordern höhere Severity-Elemente die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="15e2a-193">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="15e2a-194">Einer der folgenden Werte: *Informational*, *Low*, \* Mittel und *High*.</span><span class="sxs-lookup"><span data-stu-id="15e2a-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                | <span data-ttu-id="15e2a-195">Mittel</span><span class="sxs-lookup"><span data-stu-id="15e2a-195">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="15e2a-196">tags</span><span class="sxs-lookup"><span data-stu-id="15e2a-196">tags</span></span>                                      | <span data-ttu-id="15e2a-197">Array von benutzerdefinierten Tags, die einem Vorfall zugeordnet sind, beispielsweise zum Kennzeichnen einer Gruppe von Vorfällen mit einem gemeinsamen Merkmal.</span><span class="sxs-lookup"><span data-stu-id="15e2a-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span>                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="15e2a-198">Warnungen</span><span class="sxs-lookup"><span data-stu-id="15e2a-198">alerts</span></span>                                    | <span data-ttu-id="15e2a-199">Array aller Warnungen im Zusammenhang mit dem Vorfall und anderen Informationen, wie Schweregrad, Entitäten, die an der Warnung beteiligt waren, die Quelle der Warnungen.</span><span class="sxs-lookup"><span data-stu-id="15e2a-199">Array of all the alerts related to the incident and other information, such as severity, entities that were involved in the alert, the source of the alerts.</span></span>                                                                                                                                                                                                                     | <span data-ttu-id="15e2a-200">\[\] (Weitere Informationen zu den folgenden Warnfeldern finden Sie unter)</span><span class="sxs-lookup"><span data-stu-id="15e2a-200">\[\] (see details on alert fields below)</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="15e2a-201">**Warnungs Metadaten**</span><span class="sxs-lookup"><span data-stu-id="15e2a-201">**Alerts metadata**</span></span>                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="15e2a-202">Warnungs-Nr</span><span class="sxs-lookup"><span data-stu-id="15e2a-202">alertId</span></span>                                   | <span data-ttu-id="15e2a-203">Eindeutiger Bezeichner zur Darstellung der Warnung</span><span class="sxs-lookup"><span data-stu-id="15e2a-203">Unique identifier to represent the alert</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="15e2a-204">caD70CFEE2-1F54-32dB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="15e2a-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>                                                                                                                                                                                                            |
| <span data-ttu-id="15e2a-205">Vorfall-Nr</span><span class="sxs-lookup"><span data-stu-id="15e2a-205">incidentId</span></span>                                | <span data-ttu-id="15e2a-206">Eindeutige ID, die den Vorfall darstellt, dem diese Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="15e2a-206">Unique identifier to represent the incident this alert is associated with</span></span>                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="15e2a-207">924565</span><span class="sxs-lookup"><span data-stu-id="15e2a-207">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="15e2a-208">Metadata</span><span class="sxs-lookup"><span data-stu-id="15e2a-208">serviceSource</span></span>                             | <span data-ttu-id="15e2a-209">Dienst, von dem die Warnung stammt, beispielsweise Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP oder Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="15e2a-209">Service that the alert originates from, such as Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, or Office 365 ATP.</span></span>                                                                                                                                                                                                                                                                     | <span data-ttu-id="15e2a-210">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="15e2a-210">MicrosoftCloudAppSecurity</span></span>                                                                                                                                                                                                                         |
| <span data-ttu-id="15e2a-211">CreationTime</span><span class="sxs-lookup"><span data-stu-id="15e2a-211">creationTime</span></span>                              | <span data-ttu-id="15e2a-212">Zeitpunkt, zu dem die Warnung erstmalig erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="15e2a-212">Time when alert was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="15e2a-213">2020-09-06T14:46:55.7182276 z</span><span class="sxs-lookup"><span data-stu-id="15e2a-213">2020-09-06T14:46:55.7182276Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="15e2a-214">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="15e2a-214">lastUpdatedTime</span></span>                           | <span data-ttu-id="15e2a-215">Zeitpunkt, zu dem die Benachrichtigung zuletzt im Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="15e2a-215">Time when alert was last updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="15e2a-216">2020-09-06T14:46:57.2433333 z</span><span class="sxs-lookup"><span data-stu-id="15e2a-216">2020-09-06T14:46:57.2433333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="15e2a-217">aufgelöst</span><span class="sxs-lookup"><span data-stu-id="15e2a-217">resolvedTime</span></span>                              | <span data-ttu-id="15e2a-218">Zeitpunkt, zu dem die Warnung aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="15e2a-218">Time when alert was resolved.</span></span>                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="15e2a-219">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="15e2a-219">2020-09-10T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="15e2a-220">First-Angleichung</span><span class="sxs-lookup"><span data-stu-id="15e2a-220">firstActivity</span></span>                             | <span data-ttu-id="15e2a-221">Zeitpunkt, zu dem von der Warnung zuerst berichtet wurde, dass die Aktivität im Back-End aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="15e2a-221">Time when alert first reported that activity was updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="15e2a-222">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="15e2a-222">2020-09-04T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="15e2a-223">title</span><span class="sxs-lookup"><span data-stu-id="15e2a-223">title</span></span>                                     | <span data-ttu-id="15e2a-224">Der kurze identifizierende Zeichenfolgenwert, der für jede Warnung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-224">Brief identifying string value available for each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="15e2a-225">Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="15e2a-225">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="15e2a-226">description</span><span class="sxs-lookup"><span data-stu-id="15e2a-226">description</span></span>                               | <span data-ttu-id="15e2a-227">Zeichenfolgenwert, der jede Warnung beschreibt.</span><span class="sxs-lookup"><span data-stu-id="15e2a-227">String value describing each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="15e2a-228">Der Benutzer testet Benutzer2 (testUser2@contoso.com) manipulierte 99-Dateien mit mehreren Endungen, die mit der ungewöhnlich *herunterladen*-Erweiterung enden.</span><span class="sxs-lookup"><span data-stu-id="15e2a-228">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="15e2a-229">Dies ist eine ungewöhnliche Anzahl von Datei Manipulationen und deutet auf einen potenziellen Ransomware-Angriff hin.</span><span class="sxs-lookup"><span data-stu-id="15e2a-229">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span> |
| <span data-ttu-id="15e2a-230">category</span><span class="sxs-lookup"><span data-stu-id="15e2a-230">category</span></span>                                  | <span data-ttu-id="15e2a-231">Visuelle und numerische Ansicht, wie weit der Angriff in der killkette fortgeschritten ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-231">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="15e2a-232">Am [Mitra ATT&ck™ Framework](https://attack.mitre.org/)ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="15e2a-232">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span>                                                                                                                                                                                                                           | <span data-ttu-id="15e2a-233">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="15e2a-233">Impact</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="15e2a-234">status</span><span class="sxs-lookup"><span data-stu-id="15e2a-234">status</span></span>                                    | <span data-ttu-id="15e2a-235">Benachrichtigungen kategorisieren (als *neu*, *aktiv*oder *aufgelöst*).</span><span class="sxs-lookup"><span data-stu-id="15e2a-235">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="15e2a-236">Auf diese Weise können Sie Ihre Antwort auf Warnungen organisieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="15e2a-236">This helps you organize and manage your response to alerts.</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="15e2a-237">Neu</span><span class="sxs-lookup"><span data-stu-id="15e2a-237">New</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="15e2a-238">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="15e2a-238">severity</span></span>                                  | <span data-ttu-id="15e2a-239">Gibt die möglichen Auswirkungen auf Objekte an.</span><span class="sxs-lookup"><span data-stu-id="15e2a-239">Indicates the possible impact on assets.</span></span> <span data-ttu-id="15e2a-240">Je höher der Schweregrad, desto größer die Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="15e2a-240">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="15e2a-241">Normalerweise erfordern höhere Severity-Elemente die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="15e2a-241">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="15e2a-242">Einer der folgenden Werte: *Informational*, *Low*, \* Mittel und *High*.</span><span class="sxs-lookup"><span data-stu-id="15e2a-242">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                   | <span data-ttu-id="15e2a-243">Mittel</span><span class="sxs-lookup"><span data-stu-id="15e2a-243">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="15e2a-244">Ermittlungs-Nr</span><span class="sxs-lookup"><span data-stu-id="15e2a-244">investigationId</span></span>                           | <span data-ttu-id="15e2a-245">Die von dieser Warnung ausgelöste automatische Ermittlungs-ID.</span><span class="sxs-lookup"><span data-stu-id="15e2a-245">The automated investigation id triggered by this alert.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="15e2a-246">1234</span><span class="sxs-lookup"><span data-stu-id="15e2a-246">1234</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="15e2a-247">investigationState</span><span class="sxs-lookup"><span data-stu-id="15e2a-247">investigationState</span></span>                        | <span data-ttu-id="15e2a-248">Informationen zum aktuellen Status der Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="15e2a-248">Information on the investigation's current status.</span></span> <span data-ttu-id="15e2a-249">Einer der folgenden: *Unknown*, *terminated*, *SuccessfullyRemediated*, *benigne*, *failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *unsupporteds*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="15e2a-249">One of the following: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="15e2a-250">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="15e2a-250">UnsupportedAlertType</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="15e2a-251">classification</span><span class="sxs-lookup"><span data-stu-id="15e2a-251">classification</span></span>                            | <span data-ttu-id="15e2a-252">Die Spezifikation für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="15e2a-252">The specification for the incident.</span></span> <span data-ttu-id="15e2a-253">Die Eigenschaftswerte sind: *Unknown*, *FalsePositive*, *TruePositive* oder *null*</span><span class="sxs-lookup"><span data-stu-id="15e2a-253">The property values are: *Unknown*, *FalsePositive*, *TruePositive* or *null*</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="15e2a-254">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="15e2a-254">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="15e2a-255">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="15e2a-255">determination</span></span>                             | <span data-ttu-id="15e2a-256">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="15e2a-256">Specifies the determination of the incident.</span></span> <span data-ttu-id="15e2a-257">Die Eigenschaftswerte sind: *nichtin*, *apt*, *Schadsoftware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other* oder  *null*</span><span class="sxs-lookup"><span data-stu-id="15e2a-257">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="15e2a-258">Apt</span><span class="sxs-lookup"><span data-stu-id="15e2a-258">Apt</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="15e2a-259">assignedTo</span><span class="sxs-lookup"><span data-stu-id="15e2a-259">assignedTo</span></span>                                | <span data-ttu-id="15e2a-260">Der Besitzer des Vorfalls oder *null* , wenn kein Besitzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-260">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                            | <span data-ttu-id="15e2a-261">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="15e2a-261">secop2@contoso.com</span></span>                                                                                                                                                                                                 |
| <span data-ttu-id="15e2a-262">darstellername</span><span class="sxs-lookup"><span data-stu-id="15e2a-262">actorName</span></span>                                 | <span data-ttu-id="15e2a-263">Die Aktivitätsgruppe (sofern vorhanden), die dieser Warnung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-263">The activity group, if any, the  associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="15e2a-264">Bor</span><span class="sxs-lookup"><span data-stu-id="15e2a-264">BORON</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="15e2a-265">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="15e2a-265">threatFamilyName</span></span>                          | <span data-ttu-id="15e2a-266">Bedrohungs Familie, die dieser Warnung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-266">Threat family associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="15e2a-267">null</span><span class="sxs-lookup"><span data-stu-id="15e2a-267">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="15e2a-268">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="15e2a-268">mitreTechniques</span></span>                           | <span data-ttu-id="15e2a-269">Die Angriffstechniken, die mit dem [Gehrungs&ck](https://attack.mitre.org/)™ Framework ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="15e2a-269">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span>                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="15e2a-270">Geräte</span><span class="sxs-lookup"><span data-stu-id="15e2a-270">devices</span></span>                                   | <span data-ttu-id="15e2a-271">Alle Geräte, auf denen Benachrichtigungen im Zusammenhang mit dem Vorfall gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="15e2a-271">All devices where alerts related to the incident were sent.</span></span>                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="15e2a-272">\[\] (siehe Details zu Entitätsfeldern unten)</span><span class="sxs-lookup"><span data-stu-id="15e2a-272">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="15e2a-273">**Geräteformat**</span><span class="sxs-lookup"><span data-stu-id="15e2a-273">**Device format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="15e2a-274">DeviceID</span><span class="sxs-lookup"><span data-stu-id="15e2a-274">DeviceId</span></span>                                  | <span data-ttu-id="15e2a-275">Die Geräte-ID, wie in Microsoft Defender ATP angegeben.</span><span class="sxs-lookup"><span data-stu-id="15e2a-275">The device ID as designated in Microsoft Defender ATP.</span></span>                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="15e2a-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="15e2a-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="15e2a-277">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="15e2a-277">aadDeviceId</span></span>                               |  <span data-ttu-id="15e2a-278">Die in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD) festgelegte Geräte-ID.</span><span class="sxs-lookup"><span data-stu-id="15e2a-278">The device Id as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span></span> <span data-ttu-id="15e2a-279">Nur für Domänen verbundene Geräte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="15e2a-279">Only available for domain-joined devices.</span></span>                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="15e2a-280">null</span><span class="sxs-lookup"><span data-stu-id="15e2a-280">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="15e2a-281">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="15e2a-281">deviceDnsName</span></span>                             | <span data-ttu-id="15e2a-282">Der vollqualifizierte Domänenname für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="15e2a-282">The fully qualified domain name for the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="15e2a-283">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15e2a-283">user5cx.middleeast.corp.contoso.com</span></span>                                                                                                                                                                                                    |
| <span data-ttu-id="15e2a-284">osPlatform</span><span class="sxs-lookup"><span data-stu-id="15e2a-284">osPlatform</span></span>                                | <span data-ttu-id="15e2a-285">Die Betriebssystemplattform, die das Gerät ausführt.</span><span class="sxs-lookup"><span data-stu-id="15e2a-285">The OS platform the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="15e2a-286">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="15e2a-286">WindowsServer2016</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="15e2a-287">osBuild</span><span class="sxs-lookup"><span data-stu-id="15e2a-287">osBuild</span></span>                                   | <span data-ttu-id="15e2a-288">Die Buildversion für das Betriebssystem, auf dem das Gerät läuft.</span><span class="sxs-lookup"><span data-stu-id="15e2a-288">The build version for the OS the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="15e2a-289">14393</span><span class="sxs-lookup"><span data-stu-id="15e2a-289">14393</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="15e2a-290">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="15e2a-290">rbacGroupName</span></span>                             | <span data-ttu-id="15e2a-291">Die dem Gerät zugeordnete [rollenbasierte Zugriffs Steuerungsgruppe (Role-Based Access Control](https://docs.microsoft.com/azure/role-based-access-control/overview) , RBAC).</span><span class="sxs-lookup"><span data-stu-id="15e2a-291">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="15e2a-292">WDATP-ring0</span><span class="sxs-lookup"><span data-stu-id="15e2a-292">WDATP-Ring0</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="15e2a-293">firstSeen</span><span class="sxs-lookup"><span data-stu-id="15e2a-293">firstSeen</span></span>                                 | <span data-ttu-id="15e2a-294">Zeitpunkt, zu dem das Gerät zum ersten Mal angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="15e2a-294">Time when device was first seen.</span></span>                                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="15e2a-295">2020-02-06T14:16:01.9330135 z</span><span class="sxs-lookup"><span data-stu-id="15e2a-295">2020-02-06T14:16:01.9330135Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="15e2a-296">healthStatus</span><span class="sxs-lookup"><span data-stu-id="15e2a-296">healthStatus</span></span>                              | <span data-ttu-id="15e2a-297">Der Integritätsstatus des Geräts.</span><span class="sxs-lookup"><span data-stu-id="15e2a-297">The health state of the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="15e2a-298">Aktiv</span><span class="sxs-lookup"><span data-stu-id="15e2a-298">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="15e2a-299">riskScore</span><span class="sxs-lookup"><span data-stu-id="15e2a-299">riskScore</span></span>                                 | <span data-ttu-id="15e2a-300">Die Risikobewertung für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="15e2a-300">The risk score for the  device.</span></span>                                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="15e2a-301">Hoch</span><span class="sxs-lookup"><span data-stu-id="15e2a-301">High</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="15e2a-302">Entitäten</span><span class="sxs-lookup"><span data-stu-id="15e2a-302">entities</span></span>                                  | <span data-ttu-id="15e2a-303">Alle Entitäten, die als Teil einer bestimmten Warnung oder mit dieser in Verbindung mit dieser identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="15e2a-303">All entities that have been identified to be part of, or related to, a given alert.</span></span>                                                                                                                                                                                                                                                                                | <span data-ttu-id="15e2a-304">\[\] (siehe Details zu Entitätsfeldern unten)</span><span class="sxs-lookup"><span data-stu-id="15e2a-304">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="15e2a-305">**Entitäts Format**</span><span class="sxs-lookup"><span data-stu-id="15e2a-305">**Entity Format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="15e2a-306">EntityType</span><span class="sxs-lookup"><span data-stu-id="15e2a-306">entityType</span></span>                                | <span data-ttu-id="15e2a-307">Entitäten, die als Teil oder mit einer bestimmten Warnung in Verbindung mit identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="15e2a-307">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="15e2a-308">Die Eigenschaftenwerte lauten: *User*, *IP*, *URL*, *File*, *Process*, *Mailbox*, *MailMessage*, *mailcluster*, *Registry*</span><span class="sxs-lookup"><span data-stu-id="15e2a-308">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="15e2a-309">User</span><span class="sxs-lookup"><span data-stu-id="15e2a-309">User</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="15e2a-310">SHA1</span><span class="sxs-lookup"><span data-stu-id="15e2a-310">sha1</span></span>                                      | <span data-ttu-id="15e2a-311">Verfügbar, wenn EntityType *Datei*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-311">Available if entityType is *File*.</span></span><br><span data-ttu-id="15e2a-312">Der Datei Hash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="15e2a-312">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="15e2a-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="15e2a-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="15e2a-314">SHA256</span><span class="sxs-lookup"><span data-stu-id="15e2a-314">sha256</span></span>                                    | <span data-ttu-id="15e2a-315">Verfügbar, wenn EntityType *Datei*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-315">Available if entityType is *File*.</span></span><br><span data-ttu-id="15e2a-316">Der Datei Hash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="15e2a-316">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="15e2a-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="15e2a-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="15e2a-318">fileName</span><span class="sxs-lookup"><span data-stu-id="15e2a-318">fileName</span></span>                                  | <span data-ttu-id="15e2a-319">Verfügbar, wenn EntityType *Datei*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-319">Available if entityType is *File*.</span></span><br><span data-ttu-id="15e2a-320">Den Dateinamen für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="15e2a-320">The file name for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="15e2a-321">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="15e2a-321">Detector.UnitTests.dll</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="15e2a-322">FilePath</span><span class="sxs-lookup"><span data-stu-id="15e2a-322">filePath</span></span>                                  | <span data-ttu-id="15e2a-323">Verfügbar, wenn EntityType *Datei*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-323">Available if entityType is *File*.</span></span><br><span data-ttu-id="15e2a-324">Der Dateipfad für Warnungen, die einer Datei oder einem Prozess zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="15e2a-324">The file path for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="15e2a-325">C: \\ \\ Agent \\ \\ \_ work \\ \\ \_ Temp \\ \\ Deploy \_ System 2020-09-06 12 \_ 14 \_ 54 \\ \\ out</span><span class="sxs-lookup"><span data-stu-id="15e2a-325">C:\\\\Agent\\\\\_work\\\\\_temp\\\\Deploy\_SYSTEM 2020-09-06 12\_14\_54\\\\Out</span></span>                                                                                                                                                                    |
| <span data-ttu-id="15e2a-326">ProcessID</span><span class="sxs-lookup"><span data-stu-id="15e2a-326">processId</span></span>                                 | <span data-ttu-id="15e2a-327">Verfügbar, wenn EntityType *Prozess*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-327">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="15e2a-328">24348</span><span class="sxs-lookup"><span data-stu-id="15e2a-328">24348</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="15e2a-329">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="15e2a-329">processCommandLine</span></span>                        | <span data-ttu-id="15e2a-330">Verfügbar, wenn EntityType *Prozess*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-330">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="15e2a-331">" \\ " Ihre Datei kann \_1911150169.exe\\ "" heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="15e2a-331">"\\"Your File Is Ready To Download\_1911150169.exe\\" "</span></span>                                                                                                                                                                                           |
| <span data-ttu-id="15e2a-332">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="15e2a-332">processCreationTime</span></span>                       | <span data-ttu-id="15e2a-333">Verfügbar, wenn EntityType *Prozess*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-333">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="15e2a-334">2020-07-18T03:25:38.5269993 z</span><span class="sxs-lookup"><span data-stu-id="15e2a-334">2020-07-18T03:25:38.5269993Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="15e2a-335">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="15e2a-335">parentProcessId</span></span>                           | <span data-ttu-id="15e2a-336">Verfügbar, wenn EntityType *Prozess*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-336">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="15e2a-337">16840</span><span class="sxs-lookup"><span data-stu-id="15e2a-337">16840</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="15e2a-338">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="15e2a-338">parentProcessCreationTime</span></span>                 | <span data-ttu-id="15e2a-339">Verfügbar, wenn EntityType *Prozess*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-339">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="15e2a-340">2020-07-18T02:12:32.8616797 z</span><span class="sxs-lookup"><span data-stu-id="15e2a-340">2020-07-18T02:12:32.8616797Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="15e2a-341">ipAddress</span><span class="sxs-lookup"><span data-stu-id="15e2a-341">ipAddress</span></span>                                 | <span data-ttu-id="15e2a-342">Verfügbar, wenn EntityType *IP*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-342">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="15e2a-343">IP-Adresse für Warnungen, die Netzwerkereignissen zugeordnet sind, beispielsweise *die Kommunikation mit einem böswilligen Netzwerkziel*.</span><span class="sxs-lookup"><span data-stu-id="15e2a-343">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                   | <span data-ttu-id="15e2a-344">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="15e2a-344">62.216.203.204</span></span>                                                                                                                                                                                                                                    |
| <span data-ttu-id="15e2a-345">url</span><span class="sxs-lookup"><span data-stu-id="15e2a-345">url</span></span>                                       | <span data-ttu-id="15e2a-346">Verfügbar, wenn EntityType *URL*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-346">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="15e2a-347">URL für Warnungen, die Netzwerkereignissen zugeordnet sind, beispielsweise *die Kommunikation mit einem böswilligen Netzwerkziel*.</span><span class="sxs-lookup"><span data-stu-id="15e2a-347">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                  | <span data-ttu-id="15e2a-348">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="15e2a-348">down.esales360.cn</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="15e2a-349">accountName</span><span class="sxs-lookup"><span data-stu-id="15e2a-349">accountName</span></span>                               | <span data-ttu-id="15e2a-350">Verfügbar, wenn EntityType *Benutzer*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-350">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="15e2a-351">testUser2</span><span class="sxs-lookup"><span data-stu-id="15e2a-351">testUser2</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="15e2a-352">Domänname</span><span class="sxs-lookup"><span data-stu-id="15e2a-352">domainName</span></span>                                | <span data-ttu-id="15e2a-353">Verfügbar, wenn EntityType *Benutzer*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-353">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="15e2a-354">Europe. Corp. contoso</span><span class="sxs-lookup"><span data-stu-id="15e2a-354">europe.corp.contoso</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="15e2a-355">userSid</span><span class="sxs-lookup"><span data-stu-id="15e2a-355">userSid</span></span>                                   | <span data-ttu-id="15e2a-356">Verfügbar, wenn EntityType *Benutzer*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-356">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="15e2a-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="15e2a-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="15e2a-358">aadUserId</span><span class="sxs-lookup"><span data-stu-id="15e2a-358">aadUserId</span></span>                                 | <span data-ttu-id="15e2a-359">Verfügbar, wenn EntityType *Benutzer*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-359">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="15e2a-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="15e2a-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="15e2a-361">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="15e2a-361">userPrincipalName</span></span>                         | <span data-ttu-id="15e2a-362">Verfügbar, wenn EntityType *Benutzer* / *Postfach* / -e-*Mail*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-362">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="15e2a-363">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="15e2a-363">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="15e2a-364">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="15e2a-364">mailboxDisplayName</span></span>                        | <span data-ttu-id="15e2a-365">Verfügbar, wenn EntityType *Postfach*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-365">Available if entityType is *MailBox*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="15e2a-366">Benutzer2 testen</span><span class="sxs-lookup"><span data-stu-id="15e2a-366">test User2</span></span>                                                                                                                                                                                                                                        |
| <span data-ttu-id="15e2a-367">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="15e2a-367">mailboxAddress</span></span>                            | <span data-ttu-id="15e2a-368">Verfügbar, wenn EntityType *Benutzer* / *Postfach* / -e-*Mail*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-368">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="15e2a-369">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="15e2a-369">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="15e2a-370">clusterBy</span><span class="sxs-lookup"><span data-stu-id="15e2a-370">clusterBy</span></span>                                 | <span data-ttu-id="15e2a-371">Verfügbar, wenn EntityType  *mailcluster*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-371">Available if entityType is  *MailCluster*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="15e2a-372">Thema P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="15e2a-372">Subject;P2SenderDomain;ContentType</span></span>                                                                                                                                                                                                                |
| <span data-ttu-id="15e2a-373">sender</span><span class="sxs-lookup"><span data-stu-id="15e2a-373">sender</span></span>                                    | <span data-ttu-id="15e2a-374">Verfügbar, wenn EntityType *Benutzer* / *Postfach* / -e-*Mail*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-374">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="15e2a-375">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="15e2a-375">user.abc@mail.contoso.co.in</span></span>                                                                                                                                                                 |
| <span data-ttu-id="15e2a-376">recipient</span><span class="sxs-lookup"><span data-stu-id="15e2a-376">recipient</span></span>                                 | <span data-ttu-id="15e2a-377">Verfügbar, wenn EntityType *MailMessage*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-377">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="15e2a-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="15e2a-378">testUser2@contoso.com</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="15e2a-379">subject</span><span class="sxs-lookup"><span data-stu-id="15e2a-379">subject</span></span>                                   | <span data-ttu-id="15e2a-380">Verfügbar, wenn EntityType *MailMessage*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-380">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="15e2a-381">\[Externe \] Aufmerksamkeit</span><span class="sxs-lookup"><span data-stu-id="15e2a-381">\[EXTERNAL\] Attention</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="15e2a-382">Zustellungs-Dienst</span><span class="sxs-lookup"><span data-stu-id="15e2a-382">deliveryAction</span></span>                            | <span data-ttu-id="15e2a-383">Verfügbar, wenn EntityType *MailMessage*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-383">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="15e2a-384">Geliefert</span><span class="sxs-lookup"><span data-stu-id="15e2a-384">Delivered</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="15e2a-385">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="15e2a-385">securityGroupId</span></span>                           | <span data-ttu-id="15e2a-386">Verfügbar, wenn EntityType  *SecurityGroup*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-386">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="15e2a-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="15e2a-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="15e2a-388">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="15e2a-388">securityGroupName</span></span>                         | <span data-ttu-id="15e2a-389">Verfügbar, wenn EntityType  *SecurityGroup*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-389">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="15e2a-390">Netzwerk Konfigurations Operatoren</span><span class="sxs-lookup"><span data-stu-id="15e2a-390">Network Configuration Operators</span></span>                                                                                                                                                                                                                   |
| <span data-ttu-id="15e2a-391">registryHive</span><span class="sxs-lookup"><span data-stu-id="15e2a-391">registryHive</span></span>                              | <span data-ttu-id="15e2a-392">Verfügbar, wenn EntityType in der  *Registrierung*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-392">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="15e2a-393">HKEY \_ lokaler \_ Computer</span><span class="sxs-lookup"><span data-stu-id="15e2a-393">HKEY\_LOCAL\_MACHINE</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="15e2a-394">registryKey</span><span class="sxs-lookup"><span data-stu-id="15e2a-394">registryKey</span></span>                               | <span data-ttu-id="15e2a-395">Verfügbar, wenn EntityType in der  *Registrierung*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-395">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="15e2a-396">Software \\ \\ Microsoft \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon</span><span class="sxs-lookup"><span data-stu-id="15e2a-396">SOFTWARE\\\\Microsoft\\\\Windows NT\\\\CurrentVersion\\\\Winlogon</span></span>                                                                                                                                                                                 |
| <span data-ttu-id="15e2a-397">registryValueType</span><span class="sxs-lookup"><span data-stu-id="15e2a-397">registryValueType</span></span>                         | <span data-ttu-id="15e2a-398">Verfügbar, wenn EntityType in der  *Registrierung*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-398">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="15e2a-399">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="15e2a-399">String</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="15e2a-400">REGISTRYVALUE</span><span class="sxs-lookup"><span data-stu-id="15e2a-400">registryValue</span></span>                             | <span data-ttu-id="15e2a-401">Verfügbar, wenn EntityType in der  *Registrierung*ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-401">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="15e2a-402">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="15e2a-402">31-00-00-00</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="15e2a-403">deviceId</span><span class="sxs-lookup"><span data-stu-id="15e2a-403">deviceId</span></span>                                  | <span data-ttu-id="15e2a-404">Die ID (falls vorhanden) des Geräts, das mit der Entität verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="15e2a-404">The ID, if any, of the device related to the entity.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="15e2a-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="15e2a-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>                                                                                                                                                                                                          |



## <a name="example"></a><span data-ttu-id="15e2a-406">Beispiel</span><span class="sxs-lookup"><span data-stu-id="15e2a-406">Example</span></span>

<span data-ttu-id="15e2a-407">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="15e2a-407">**Request**</span></span>

```
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="15e2a-408">**Response**</span><span class="sxs-lookup"><span data-stu-id="15e2a-408">**Response**</span></span>
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

## <a name="related-topic"></a><span data-ttu-id="15e2a-409">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="15e2a-409">Related topic</span></span>
- [<span data-ttu-id="15e2a-410">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="15e2a-410">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="15e2a-411">Vorfall aktualisieren</span><span class="sxs-lookup"><span data-stu-id="15e2a-411">Update incident</span></span>](api-update-incidents.md)

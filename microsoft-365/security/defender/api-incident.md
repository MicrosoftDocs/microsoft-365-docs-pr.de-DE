---
title: Microsoft 365 ApIs für Defender-Vorfälle und den Ressourcentyp "Vorfälle"
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Ressourcentyps Incidents in Microsoft 365 Defender
keywords: Vorfall, Vorfälle, API
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
ms.openlocfilehash: 587d6107b0c09b2178311d8da6606968e7fda083
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730930"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="9c506-104">Microsoft 365 Defender Incidents API und der Ressourcentyp "Incidents"</span><span class="sxs-lookup"><span data-stu-id="9c506-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9c506-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9c506-105">**Applies to:**</span></span>

- [<span data-ttu-id="9c506-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c506-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="9c506-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="9c506-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9c506-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="9c506-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="9c506-109">Bei [einem Vorfall](incidents-overview.md) handelt es sich um eine Sammlung verwandter Warnungen, die bei der Beschreibung eines Angriffs helfen.</span><span class="sxs-lookup"><span data-stu-id="9c506-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="9c506-110">Ereignisse aus verschiedenen Entitäten in Ihrer Organisation werden automatisch von defender Microsoft 365 aggregiert.</span><span class="sxs-lookup"><span data-stu-id="9c506-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="9c506-111">Sie können die Incidents-API verwenden, um programmgesteuert auf die Vorfälle und zugehörigen Warnungen Ihrer Organisation zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9c506-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="9c506-112">Kontingente und Ressourcenzuordnung</span><span class="sxs-lookup"><span data-stu-id="9c506-112">Quotas and resource allocation</span></span>

<span data-ttu-id="9c506-113">Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde anfordern.</span><span class="sxs-lookup"><span data-stu-id="9c506-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="9c506-114">Jede Methode verfügt auch über eigene Kontingente.</span><span class="sxs-lookup"><span data-stu-id="9c506-114">Each method also has its own quotas.</span></span> <span data-ttu-id="9c506-115">Weitere Informationen zu methodenspezifischen Kontingenten finden Sie im entsprechenden Artikel für die zu verwendende Methode.</span><span class="sxs-lookup"><span data-stu-id="9c506-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="9c506-116">Ein HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder nach der Anzahl der gesendeten Anforderungen oder nach der zugewiesenen `429` Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="9c506-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="9c506-117">Der Antworttext enthält die Zeit bis zum Zurücksetzen des erreichten Kontingents.</span><span class="sxs-lookup"><span data-stu-id="9c506-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="9c506-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9c506-118">Permissions</span></span>

<span data-ttu-id="9c506-119">Die Incidents-API erfordert unterschiedliche Arten von Berechtigungen für jede ihrer Methoden.</span><span class="sxs-lookup"><span data-stu-id="9c506-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="9c506-120">Weitere Informationen zu den erforderlichen Berechtigungen finden Sie im Artikel der jeweiligen Methode.</span><span class="sxs-lookup"><span data-stu-id="9c506-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="9c506-121">Methoden</span><span class="sxs-lookup"><span data-stu-id="9c506-121">Methods</span></span>

<span data-ttu-id="9c506-122">Methode</span><span class="sxs-lookup"><span data-stu-id="9c506-122">Method</span></span> | <span data-ttu-id="9c506-123">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="9c506-123">Return Type</span></span> | <span data-ttu-id="9c506-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c506-124">Description</span></span>
-|-|-
[<span data-ttu-id="9c506-125">Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="9c506-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="9c506-126">[Liste der Vorfälle](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="9c506-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="9c506-127">Hier erhalten Sie eine Liste der Vorfälle.</span><span class="sxs-lookup"><span data-stu-id="9c506-127">Get a list of incidents.</span></span>
[<span data-ttu-id="9c506-128">Aktualisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="9c506-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="9c506-129">Vorfall</span><span class="sxs-lookup"><span data-stu-id="9c506-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="9c506-130">Aktualisieren eines bestimmten Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="9c506-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="9c506-131">Anforderungstext, Antwort und Beispiele</span><span class="sxs-lookup"><span data-stu-id="9c506-131">Request body, response, and examples</span></span>

<span data-ttu-id="9c506-132">Weitere Informationen zum Erstellen einer Anforderung oder analysieren einer Antwort sowie praktische Beispiele finden Sie in den jeweiligen Methodenartikeln.</span><span class="sxs-lookup"><span data-stu-id="9c506-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="9c506-133">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9c506-133">Common properties</span></span>

<span data-ttu-id="9c506-134">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9c506-134">Property</span></span> | <span data-ttu-id="9c506-135">Typ</span><span class="sxs-lookup"><span data-stu-id="9c506-135">Type</span></span> | <span data-ttu-id="9c506-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c506-136">Description</span></span>
-|-|-
<span data-ttu-id="9c506-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="9c506-137">incidentId</span></span> | <span data-ttu-id="9c506-138">long</span><span class="sxs-lookup"><span data-stu-id="9c506-138">long</span></span> | <span data-ttu-id="9c506-139">Eindeutige ID des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="9c506-139">Incident unique ID.</span></span>
<span data-ttu-id="9c506-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="9c506-140">redirectIncidentId</span></span> | <span data-ttu-id="9c506-141">Nullable long</span><span class="sxs-lookup"><span data-stu-id="9c506-141">nullable long</span></span> | <span data-ttu-id="9c506-142">Die Vorfall-ID, mit der der aktuelle Vorfall zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="9c506-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="9c506-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="9c506-143">incidentName</span></span> | <span data-ttu-id="9c506-144">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9c506-144">string</span></span> | <span data-ttu-id="9c506-145">Der Name des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="9c506-145">The name of the Incident.</span></span>
<span data-ttu-id="9c506-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="9c506-146">createdTime</span></span> | <span data-ttu-id="9c506-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="9c506-147">DateTimeOffset</span></span> | <span data-ttu-id="9c506-148">Das Datum und die Uhrzeit (in UTC), zu der der Vorfall erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9c506-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="9c506-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="9c506-149">lastUpdateTime</span></span> | <span data-ttu-id="9c506-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="9c506-150">DateTimeOffset</span></span> | <span data-ttu-id="9c506-151">Datum und Uhrzeit (in UTC) der Vorfall wurde zuletzt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="9c506-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="9c506-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="9c506-152">assignedTo</span></span> | <span data-ttu-id="9c506-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9c506-153">string</span></span> | <span data-ttu-id="9c506-154">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="9c506-154">Owner of the Incident.</span></span>
<span data-ttu-id="9c506-155">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="9c506-155">severity</span></span> | <span data-ttu-id="9c506-156">Enum</span><span class="sxs-lookup"><span data-stu-id="9c506-156">Enum</span></span> | <span data-ttu-id="9c506-157">Schweregrad des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="9c506-157">Severity of the Incident.</span></span> <span data-ttu-id="9c506-158">Mögliche Werte sind: ```UnSpecified``` , , , , und ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="9c506-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="9c506-159">status</span><span class="sxs-lookup"><span data-stu-id="9c506-159">status</span></span> | <span data-ttu-id="9c506-160">Enum</span><span class="sxs-lookup"><span data-stu-id="9c506-160">Enum</span></span> | <span data-ttu-id="9c506-161">Gibt den aktuellen Status des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="9c506-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="9c506-162">Mögliche Werte sind: ```Active``` ```Resolved``` , , und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="9c506-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="9c506-163">classification</span><span class="sxs-lookup"><span data-stu-id="9c506-163">classification</span></span> | <span data-ttu-id="9c506-164">Enum</span><span class="sxs-lookup"><span data-stu-id="9c506-164">Enum</span></span> | <span data-ttu-id="9c506-165">Spezifikation des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="9c506-165">Specification of the incident.</span></span> <span data-ttu-id="9c506-166">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="9c506-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="9c506-167">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="9c506-167">determination</span></span> | <span data-ttu-id="9c506-168">Enum</span><span class="sxs-lookup"><span data-stu-id="9c506-168">Enum</span></span> | <span data-ttu-id="9c506-169">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="9c506-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="9c506-170">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="9c506-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="9c506-171">tags</span><span class="sxs-lookup"><span data-stu-id="9c506-171">tags</span></span> | <span data-ttu-id="9c506-172">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="9c506-172">string List</span></span> | <span data-ttu-id="9c506-173">Liste der Incident-Tags.</span><span class="sxs-lookup"><span data-stu-id="9c506-173">List of Incident tags.</span></span>
<span data-ttu-id="9c506-174">Kommentare</span><span class="sxs-lookup"><span data-stu-id="9c506-174">comments</span></span> | <span data-ttu-id="9c506-175">Liste der Vorfallkommentare</span><span class="sxs-lookup"><span data-stu-id="9c506-175">List of incident comments</span></span> | <span data-ttu-id="9c506-176">Das Incident Comment-Objekt enthält: Kommentarzeichenfolge, createdBy-Zeichenfolge und createTime-Datumszeit.</span><span class="sxs-lookup"><span data-stu-id="9c506-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="9c506-177">Warnungen</span><span class="sxs-lookup"><span data-stu-id="9c506-177">alerts</span></span> | <span data-ttu-id="9c506-178">Warnungsliste</span><span class="sxs-lookup"><span data-stu-id="9c506-178">Alert List</span></span> | <span data-ttu-id="9c506-179">Liste der zugehörigen Warnungen.</span><span class="sxs-lookup"><span data-stu-id="9c506-179">List of related alerts.</span></span> <span data-ttu-id="9c506-180">Beispiele finden Sie unter [List incidents](api-list-incidents.md) API documentation.</span><span class="sxs-lookup"><span data-stu-id="9c506-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9c506-181">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="9c506-181">Related articles</span></span>

- [<span data-ttu-id="9c506-182">Microsoft 365 Übersicht über Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="9c506-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="9c506-183">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="9c506-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="9c506-184">Auflisten der Incidents-API</span><span class="sxs-lookup"><span data-stu-id="9c506-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="9c506-185">Aktualisieren der Vorfall-API</span><span class="sxs-lookup"><span data-stu-id="9c506-185">Update incident API</span></span>](api-update-incidents.md)

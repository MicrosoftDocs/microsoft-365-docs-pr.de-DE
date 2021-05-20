---
title: Microsoft 365 Defender-Vorfällen-APIs und der Vorfallressourcentyp
description: Weitere Informationen zu den Methoden und Eigenschaften des Ressourcentyps "Vorfall" in Microsoft 365 Defender
keywords: Vorfall, Vorfälle, api
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
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572585"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="74a7e-104">Microsoft 365 Defender-Vorfällen-API und der Ressourcentyp des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="74a7e-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="74a7e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="74a7e-105">**Applies to:**</span></span>

- <span data-ttu-id="74a7e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74a7e-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74a7e-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="74a7e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="74a7e-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="74a7e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="74a7e-109">Ein [Vorfall](incidents-overview.md) ist eine Sammlung verwandter Warnungen, die einen Angriff beschreiben.</span><span class="sxs-lookup"><span data-stu-id="74a7e-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="74a7e-110">Ereignisse aus verschiedenen Entitäten in Ihrer Organisation werden automatisch von Microsoft 365 Defender aggregiert.</span><span class="sxs-lookup"><span data-stu-id="74a7e-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="74a7e-111">Sie können die Vorfall-API verwenden, um programmgesteuert auf Vorfälle und zugehörige Warnungen Ihrer Organisation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="74a7e-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="74a7e-112">Kontingente und Ressourcenallokation</span><span class="sxs-lookup"><span data-stu-id="74a7e-112">Quotas and resource allocation</span></span>

<span data-ttu-id="74a7e-113">Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde anfordern.</span><span class="sxs-lookup"><span data-stu-id="74a7e-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="74a7e-114">Jede Methode hat auch ihre eigenen Quoten.</span><span class="sxs-lookup"><span data-stu-id="74a7e-114">Each method also has its own quotas.</span></span> <span data-ttu-id="74a7e-115">Weitere Informationen zu methodenspezifischen Kontingenten finden Sie im entsprechenden Artikel für die Methode, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="74a7e-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="74a7e-116">Ein `429` HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder nach Anzahl der gesendeten Anforderungen oder nach zugeteilter Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="74a7e-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="74a7e-117">Der Antworttext enthält die Zeit, bis das erreichte Kontingent zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="74a7e-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="74a7e-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="74a7e-118">Permissions</span></span>

<span data-ttu-id="74a7e-119">Die Vorkommniss-API erfordert für jede ihrer Methoden unterschiedliche Arten von Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="74a7e-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="74a7e-120">Weitere Informationen zu den erforderlichen Berechtigungen finden Sie im Artikel der jeweiligen Methode.</span><span class="sxs-lookup"><span data-stu-id="74a7e-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="74a7e-121">Methoden</span><span class="sxs-lookup"><span data-stu-id="74a7e-121">Methods</span></span>

<span data-ttu-id="74a7e-122">Methode</span><span class="sxs-lookup"><span data-stu-id="74a7e-122">Method</span></span> | <span data-ttu-id="74a7e-123">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="74a7e-123">Return Type</span></span> | <span data-ttu-id="74a7e-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74a7e-124">Description</span></span>
-|-|-
[<span data-ttu-id="74a7e-125">Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="74a7e-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="74a7e-126">[Vorfallliste](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="74a7e-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="74a7e-127">Hier erhalten Sie eine Liste der Vorfälle.</span><span class="sxs-lookup"><span data-stu-id="74a7e-127">Get a list of incidents.</span></span>
[<span data-ttu-id="74a7e-128">Aktualisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="74a7e-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="74a7e-129">Vorfall</span><span class="sxs-lookup"><span data-stu-id="74a7e-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="74a7e-130">Aktualisieren Sie einen bestimmten Vorfall.</span><span class="sxs-lookup"><span data-stu-id="74a7e-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="74a7e-131">Anforderungstext, Antwort und Beispiele</span><span class="sxs-lookup"><span data-stu-id="74a7e-131">Request body, response, and examples</span></span>

<span data-ttu-id="74a7e-132">Weitere Informationen zum Erstellen einer Anforderung oder zum Analysieren einer Antwort sowie praktische Beispiele finden Sie in den entsprechenden Methodenartikeln.</span><span class="sxs-lookup"><span data-stu-id="74a7e-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="74a7e-133">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="74a7e-133">Common properties</span></span>

<span data-ttu-id="74a7e-134">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="74a7e-134">Property</span></span> | <span data-ttu-id="74a7e-135">Typ</span><span class="sxs-lookup"><span data-stu-id="74a7e-135">Type</span></span> | <span data-ttu-id="74a7e-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74a7e-136">Description</span></span>
-|-|-
<span data-ttu-id="74a7e-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="74a7e-137">incidentId</span></span> | <span data-ttu-id="74a7e-138">long</span><span class="sxs-lookup"><span data-stu-id="74a7e-138">long</span></span> | <span data-ttu-id="74a7e-139">Eindeutige ID des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="74a7e-139">Incident unique ID.</span></span>
<span data-ttu-id="74a7e-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="74a7e-140">redirectIncidentId</span></span> | <span data-ttu-id="74a7e-141">nullable lange</span><span class="sxs-lookup"><span data-stu-id="74a7e-141">nullable long</span></span> | <span data-ttu-id="74a7e-142">Die Vorfall-ID, mit der der aktuelle Vorfall zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="74a7e-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="74a7e-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="74a7e-143">incidentName</span></span> | <span data-ttu-id="74a7e-144">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="74a7e-144">string</span></span> | <span data-ttu-id="74a7e-145">Der Name des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="74a7e-145">The name of the Incident.</span></span>
<span data-ttu-id="74a7e-146">createdZeit</span><span class="sxs-lookup"><span data-stu-id="74a7e-146">createdTime</span></span> | <span data-ttu-id="74a7e-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="74a7e-147">DateTimeOffset</span></span> | <span data-ttu-id="74a7e-148">Das Datum und die Uhrzeit (in UTC), die der Vorfall erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="74a7e-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="74a7e-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="74a7e-149">lastUpdateTime</span></span> | <span data-ttu-id="74a7e-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="74a7e-150">DateTimeOffset</span></span> | <span data-ttu-id="74a7e-151">Das Datum und die Uhrzeit (in UTC) der Vorfall wurde zuletzt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="74a7e-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="74a7e-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="74a7e-152">assignedTo</span></span> | <span data-ttu-id="74a7e-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="74a7e-153">string</span></span> | <span data-ttu-id="74a7e-154">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="74a7e-154">Owner of the Incident.</span></span>
<span data-ttu-id="74a7e-155">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="74a7e-155">severity</span></span> | <span data-ttu-id="74a7e-156">Enum</span><span class="sxs-lookup"><span data-stu-id="74a7e-156">Enum</span></span> | <span data-ttu-id="74a7e-157">Schweregrad des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="74a7e-157">Severity of the Incident.</span></span> <span data-ttu-id="74a7e-158">Mögliche Werte sind: ```UnSpecified``` , , , , und ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="74a7e-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="74a7e-159">status</span><span class="sxs-lookup"><span data-stu-id="74a7e-159">status</span></span> | <span data-ttu-id="74a7e-160">Enum</span><span class="sxs-lookup"><span data-stu-id="74a7e-160">Enum</span></span> | <span data-ttu-id="74a7e-161">Gibt den aktuellen Status des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="74a7e-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="74a7e-162">Mögliche Werte sind: ```Active``` , ```Resolved``` , und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="74a7e-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="74a7e-163">classification</span><span class="sxs-lookup"><span data-stu-id="74a7e-163">classification</span></span> | <span data-ttu-id="74a7e-164">Enum</span><span class="sxs-lookup"><span data-stu-id="74a7e-164">Enum</span></span> | <span data-ttu-id="74a7e-165">Spezifikation des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="74a7e-165">Specification of the incident.</span></span> <span data-ttu-id="74a7e-166">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="74a7e-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="74a7e-167">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="74a7e-167">determination</span></span> | <span data-ttu-id="74a7e-168">Enum</span><span class="sxs-lookup"><span data-stu-id="74a7e-168">Enum</span></span> | <span data-ttu-id="74a7e-169">Gibt die Bestimmung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="74a7e-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="74a7e-170">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="74a7e-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="74a7e-171">tags</span><span class="sxs-lookup"><span data-stu-id="74a7e-171">tags</span></span> | <span data-ttu-id="74a7e-172">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="74a7e-172">string List</span></span> | <span data-ttu-id="74a7e-173">Liste der Incident-Tags.</span><span class="sxs-lookup"><span data-stu-id="74a7e-173">List of Incident tags.</span></span>
<span data-ttu-id="74a7e-174">Kommentare</span><span class="sxs-lookup"><span data-stu-id="74a7e-174">comments</span></span> | <span data-ttu-id="74a7e-175">Liste der Kommentare zu Vorfällen</span><span class="sxs-lookup"><span data-stu-id="74a7e-175">List of incident comments</span></span> | <span data-ttu-id="74a7e-176">Incident Comment-Objekt enthält: Kommentarzeichenfolge, createdBy-Zeichenfolge und createTime-Datumszeit.</span><span class="sxs-lookup"><span data-stu-id="74a7e-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="74a7e-177">Warnungen</span><span class="sxs-lookup"><span data-stu-id="74a7e-177">alerts</span></span> | <span data-ttu-id="74a7e-178">Warnungsliste</span><span class="sxs-lookup"><span data-stu-id="74a7e-178">Alert List</span></span> | <span data-ttu-id="74a7e-179">Liste der zugehörigen Warnungen.</span><span class="sxs-lookup"><span data-stu-id="74a7e-179">List of related alerts.</span></span> <span data-ttu-id="74a7e-180">Weitere Beispiele finden Sie in der API-Dokumentation Liste von [Vorfällen.](api-list-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="74a7e-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="74a7e-181">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="74a7e-181">Related articles</span></span>

- [<span data-ttu-id="74a7e-182">Microsoft 365 Übersicht über Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="74a7e-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="74a7e-183">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="74a7e-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="74a7e-184">Liste der Vorfällen API</span><span class="sxs-lookup"><span data-stu-id="74a7e-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="74a7e-185">Aktualisieren der Vorfall-API</span><span class="sxs-lookup"><span data-stu-id="74a7e-185">Update incident API</span></span>](api-update-incidents.md)

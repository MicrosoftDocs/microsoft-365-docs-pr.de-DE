---
title: Microsoft 365 Defender Incidents-APIs und der Vorfall-Ressourcentyp
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Incident-Ressourcentyps in Microsoft 365 Defender
keywords: Vorfall, Vorfälle, API
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
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719334"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="df7b6-104">Microsoft 365 Defender Incidents-API und der Vorfall-Ressourcentyp</span><span class="sxs-lookup"><span data-stu-id="df7b6-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="df7b6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="df7b6-105">**Applies to:**</span></span>

- <span data-ttu-id="df7b6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df7b6-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df7b6-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="df7b6-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="df7b6-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="df7b6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="df7b6-109">Bei einem [Vorfall](incidents-overview.md) handelt es sich um eine Sammlung zusammengehöriger Warnungen, die einen Angriff beschreiben.</span><span class="sxs-lookup"><span data-stu-id="df7b6-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="df7b6-110">Ereignisse aus unterschiedlichen Entitäten in Ihrer Organisation werden automatisch von Microsoft 365 Defender aggregiert.</span><span class="sxs-lookup"><span data-stu-id="df7b6-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="df7b6-111">Sie können die Vorfälle-API verwenden, um Programmgesteuertes auf Vorfälle und Verwandte Warnungen Ihrer Organisation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="df7b6-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="df7b6-112">Kontingente und Ressourcenzuteilung</span><span class="sxs-lookup"><span data-stu-id="df7b6-112">Quotas and resource allocation</span></span>

<span data-ttu-id="df7b6-113">Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde anfordern.</span><span class="sxs-lookup"><span data-stu-id="df7b6-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="df7b6-114">Jede Methode verfügt auch über eigene Kontingente.</span><span class="sxs-lookup"><span data-stu-id="df7b6-114">Each method also has its own quotas.</span></span> <span data-ttu-id="df7b6-115">Weitere Informationen zu Methoden spezifischen Kontingenten finden Sie im jeweiligen Artikel für die Methode, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="df7b6-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="df7b6-116">Ein `429` HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder nach der Anzahl der gesendeten Anforderungen oder nach der zugewiesenen Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="df7b6-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="df7b6-117">Der Antworttext enthält die Zeit, bis das von Ihnen erreichte Kontingent zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="df7b6-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="df7b6-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="df7b6-118">Permissions</span></span>

<span data-ttu-id="df7b6-119">Für die Vorfälle-API sind unterschiedliche Arten von Berechtigungen für jede ihrer Methoden erforderlich.</span><span class="sxs-lookup"><span data-stu-id="df7b6-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="df7b6-120">Weitere Informationen zu den erforderlichen Berechtigungen finden Sie im Artikel zur jeweiligen Methode.</span><span class="sxs-lookup"><span data-stu-id="df7b6-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="df7b6-121">Methoden</span><span class="sxs-lookup"><span data-stu-id="df7b6-121">Methods</span></span>

<span data-ttu-id="df7b6-122">Methode</span><span class="sxs-lookup"><span data-stu-id="df7b6-122">Method</span></span> | <span data-ttu-id="df7b6-123">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="df7b6-123">Return Type</span></span> | <span data-ttu-id="df7b6-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df7b6-124">Description</span></span>
-|-|-
[<span data-ttu-id="df7b6-125">Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="df7b6-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="df7b6-126">[Vorfall](api-incident.md) Liste</span><span class="sxs-lookup"><span data-stu-id="df7b6-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="df7b6-127">Abrufen einer Liste von Vorfällen.</span><span class="sxs-lookup"><span data-stu-id="df7b6-127">Get a list of incidents.</span></span>
[<span data-ttu-id="df7b6-128">Aktualisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="df7b6-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="df7b6-129">Vorfall</span><span class="sxs-lookup"><span data-stu-id="df7b6-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="df7b6-130">Einen bestimmten Vorfall aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="df7b6-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="df7b6-131">Anforderungstext, Antwort und Beispiele</span><span class="sxs-lookup"><span data-stu-id="df7b6-131">Request body, response, and examples</span></span>

<span data-ttu-id="df7b6-132">Weitere Informationen zum Erstellen einer Anforderung oder zum Analysieren einer Antwort sowie zu praktischen Beispielen finden Sie in den jeweiligen Methoden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="df7b6-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="df7b6-133">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="df7b6-133">Common properties</span></span>

<span data-ttu-id="df7b6-134">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="df7b6-134">Property</span></span> | <span data-ttu-id="df7b6-135">Typ</span><span class="sxs-lookup"><span data-stu-id="df7b6-135">Type</span></span> | <span data-ttu-id="df7b6-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df7b6-136">Description</span></span>
-|-|-
<span data-ttu-id="df7b6-137">Vorfall-Nr</span><span class="sxs-lookup"><span data-stu-id="df7b6-137">incidentId</span></span> | <span data-ttu-id="df7b6-138">long</span><span class="sxs-lookup"><span data-stu-id="df7b6-138">long</span></span> | <span data-ttu-id="df7b6-139">Vorfall eindeutige ID.</span><span class="sxs-lookup"><span data-stu-id="df7b6-139">Incident unique ID.</span></span>
<span data-ttu-id="df7b6-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="df7b6-140">redirectIncidentId</span></span> | <span data-ttu-id="df7b6-141">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="df7b6-141">nullable long</span></span> | <span data-ttu-id="df7b6-142">Die Vorfall-ID, mit der der aktuelle Vorfall zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="df7b6-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="df7b6-143">Vorfallname</span><span class="sxs-lookup"><span data-stu-id="df7b6-143">incidentName</span></span> | <span data-ttu-id="df7b6-144">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="df7b6-144">string</span></span> | <span data-ttu-id="df7b6-145">Der Name des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="df7b6-145">The name of the Incident.</span></span>
<span data-ttu-id="df7b6-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="df7b6-146">createdTime</span></span> | <span data-ttu-id="df7b6-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="df7b6-147">DateTimeOffset</span></span> | <span data-ttu-id="df7b6-148">Das Datum und die Uhrzeit (in UTC), an denen der Vorfall erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="df7b6-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="df7b6-149">Last Update time</span><span class="sxs-lookup"><span data-stu-id="df7b6-149">lastUpdateTime</span></span> | <span data-ttu-id="df7b6-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="df7b6-150">DateTimeOffset</span></span> | <span data-ttu-id="df7b6-151">Datum und Uhrzeit (in UTC) der Vorfall wurde zuletzt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="df7b6-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="df7b6-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="df7b6-152">assignedTo</span></span> | <span data-ttu-id="df7b6-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="df7b6-153">string</span></span> | <span data-ttu-id="df7b6-154">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="df7b6-154">Owner of the Incident.</span></span>
<span data-ttu-id="df7b6-155">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="df7b6-155">severity</span></span> | <span data-ttu-id="df7b6-156">Enum</span><span class="sxs-lookup"><span data-stu-id="df7b6-156">Enum</span></span> | <span data-ttu-id="df7b6-157">Schweregrad des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="df7b6-157">Severity of the Incident.</span></span> <span data-ttu-id="df7b6-158">Mögliche Werte sind: ```UnSpecified``` , ```Informational``` , ```Low``` , ```Medium``` , und ```High``` .</span><span class="sxs-lookup"><span data-stu-id="df7b6-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="df7b6-159">status</span><span class="sxs-lookup"><span data-stu-id="df7b6-159">status</span></span> | <span data-ttu-id="df7b6-160">Enum</span><span class="sxs-lookup"><span data-stu-id="df7b6-160">Enum</span></span> | <span data-ttu-id="df7b6-161">Gibt den aktuellen Status des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="df7b6-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="df7b6-162">Mögliche Werte sind: ```Active``` , ```Resolved``` und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="df7b6-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="df7b6-163">classification</span><span class="sxs-lookup"><span data-stu-id="df7b6-163">classification</span></span> | <span data-ttu-id="df7b6-164">Enum</span><span class="sxs-lookup"><span data-stu-id="df7b6-164">Enum</span></span> | <span data-ttu-id="df7b6-165">Spezifikation des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="df7b6-165">Specification of the incident.</span></span> <span data-ttu-id="df7b6-166">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="df7b6-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="df7b6-167">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="df7b6-167">determination</span></span> | <span data-ttu-id="df7b6-168">Enum</span><span class="sxs-lookup"><span data-stu-id="df7b6-168">Enum</span></span> | <span data-ttu-id="df7b6-169">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="df7b6-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="df7b6-170">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="df7b6-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="df7b6-171">tags</span><span class="sxs-lookup"><span data-stu-id="df7b6-171">tags</span></span> | <span data-ttu-id="df7b6-172">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="df7b6-172">string List</span></span> | <span data-ttu-id="df7b6-173">Liste der Vorfall Tags.</span><span class="sxs-lookup"><span data-stu-id="df7b6-173">List of Incident tags.</span></span>
<span data-ttu-id="df7b6-174">Warnungen</span><span class="sxs-lookup"><span data-stu-id="df7b6-174">alerts</span></span> | <span data-ttu-id="df7b6-175">Warnungsliste</span><span class="sxs-lookup"><span data-stu-id="df7b6-175">Alert List</span></span> | <span data-ttu-id="df7b6-176">Liste der zugehörigen Warnungen.</span><span class="sxs-lookup"><span data-stu-id="df7b6-176">List of related alerts.</span></span> <span data-ttu-id="df7b6-177">Siehe Beispiele unter Documentation [List Incidents](api-list-incidents.md) API.</span><span class="sxs-lookup"><span data-stu-id="df7b6-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="df7b6-178">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="df7b6-178">Related articles</span></span>

- [<span data-ttu-id="df7b6-179">Microsoft 365 Defender-APIs (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="df7b6-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="df7b6-180">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="df7b6-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="df7b6-181">Listen Vorfälle-API</span><span class="sxs-lookup"><span data-stu-id="df7b6-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="df7b6-182">Update Incident API</span><span class="sxs-lookup"><span data-stu-id="df7b6-182">Update incident API</span></span>](api-update-incidents.md)

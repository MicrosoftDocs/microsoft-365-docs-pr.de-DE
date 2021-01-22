---
title: Microsoft 365 Defender-Vorfall-APIs und der Ressourcentyp für Vorfälle
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Vorfallressourcentyps in Microsoft 365 Defender
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928354"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="ca882-104">Microsoft 365 Defender Incidents API und der Ressourcentyp für Vorfälle</span><span class="sxs-lookup"><span data-stu-id="ca882-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ca882-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ca882-105">**Applies to:**</span></span>

- <span data-ttu-id="ca882-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca882-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca882-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="ca882-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ca882-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="ca882-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="ca882-109">Ein [Vorfall](incidents-overview.md) ist eine Sammlung verwandter Warnungen, die einen Angriff beschreiben.</span><span class="sxs-lookup"><span data-stu-id="ca882-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="ca882-110">Ereignisse von verschiedenen Entitäten in Ihrer Organisation werden automatisch von Microsoft 365 Defender aggregiert.</span><span class="sxs-lookup"><span data-stu-id="ca882-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="ca882-111">Sie können die Vorfall-API verwenden, um programmgesteuert auf die Vorfälle und zugehörigen Warnungen Ihrer Organisation zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ca882-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="ca882-112">Kontingente und Ressourcenzuordnung</span><span class="sxs-lookup"><span data-stu-id="ca882-112">Quotas and resource allocation</span></span>

<span data-ttu-id="ca882-113">Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde anfordern.</span><span class="sxs-lookup"><span data-stu-id="ca882-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="ca882-114">Jede Methode verfügt auch über eigene Kontingente.</span><span class="sxs-lookup"><span data-stu-id="ca882-114">Each method also has its own quotas.</span></span> <span data-ttu-id="ca882-115">Weitere Informationen zu methodenspezifischen Kontingenten finden Sie im entsprechenden Artikel zu der Methode, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ca882-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="ca882-116">Ein HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder durch die Anzahl der gesendeten Anforderungen oder durch die `429` zugewiesene Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="ca882-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="ca882-117">Der Antworttext enthält die Zeit bis zum Zurücksetzen des erreichten Kontingents.</span><span class="sxs-lookup"><span data-stu-id="ca882-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="ca882-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ca882-118">Permissions</span></span>

<span data-ttu-id="ca882-119">Die Vorfall-API erfordert unterschiedliche Arten von Berechtigungen für jede ihrer Methoden.</span><span class="sxs-lookup"><span data-stu-id="ca882-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="ca882-120">Weitere Informationen zu den erforderlichen Berechtigungen finden Sie im Artikel der jeweiligen Methode.</span><span class="sxs-lookup"><span data-stu-id="ca882-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="ca882-121">Methoden</span><span class="sxs-lookup"><span data-stu-id="ca882-121">Methods</span></span>

<span data-ttu-id="ca882-122">Methode</span><span class="sxs-lookup"><span data-stu-id="ca882-122">Method</span></span> | <span data-ttu-id="ca882-123">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="ca882-123">Return Type</span></span> | <span data-ttu-id="ca882-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca882-124">Description</span></span>
-|-|-
[<span data-ttu-id="ca882-125">Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="ca882-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="ca882-126">[Vorfallliste](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="ca882-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="ca882-127">Eine Liste der Vorfälle erhalten.</span><span class="sxs-lookup"><span data-stu-id="ca882-127">Get a list of incidents.</span></span>
[<span data-ttu-id="ca882-128">Aktualisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="ca882-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="ca882-129">Vorfall</span><span class="sxs-lookup"><span data-stu-id="ca882-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="ca882-130">Aktualisieren eines bestimmten Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="ca882-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="ca882-131">Anforderungstext, Antwort und Beispiele</span><span class="sxs-lookup"><span data-stu-id="ca882-131">Request body, response, and examples</span></span>

<span data-ttu-id="ca882-132">Weitere Informationen zum Erstellen einer Anforderung oder Analysieren einer Antwort sowie praktische Beispiele finden Sie in den jeweiligen Methodenartikeln.</span><span class="sxs-lookup"><span data-stu-id="ca882-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="ca882-133">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ca882-133">Common properties</span></span>

<span data-ttu-id="ca882-134">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ca882-134">Property</span></span> | <span data-ttu-id="ca882-135">Typ</span><span class="sxs-lookup"><span data-stu-id="ca882-135">Type</span></span> | <span data-ttu-id="ca882-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca882-136">Description</span></span>
-|-|-
<span data-ttu-id="ca882-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="ca882-137">incidentId</span></span> | <span data-ttu-id="ca882-138">long</span><span class="sxs-lookup"><span data-stu-id="ca882-138">long</span></span> | <span data-ttu-id="ca882-139">Eindeutige VORfall-ID.</span><span class="sxs-lookup"><span data-stu-id="ca882-139">Incident unique ID.</span></span>
<span data-ttu-id="ca882-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="ca882-140">redirectIncidentId</span></span> | <span data-ttu-id="ca882-141">Nullwerte zulassend lang</span><span class="sxs-lookup"><span data-stu-id="ca882-141">nullable long</span></span> | <span data-ttu-id="ca882-142">Die Vorfall-ID, mit der der aktuelle Vorfall zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ca882-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="ca882-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="ca882-143">incidentName</span></span> | <span data-ttu-id="ca882-144">string</span><span class="sxs-lookup"><span data-stu-id="ca882-144">string</span></span> | <span data-ttu-id="ca882-145">Der Name des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="ca882-145">The name of the Incident.</span></span>
<span data-ttu-id="ca882-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="ca882-146">createdTime</span></span> | <span data-ttu-id="ca882-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="ca882-147">DateTimeOffset</span></span> | <span data-ttu-id="ca882-148">Das Datum und die Uhrzeit (in UTC), zu der der Vorfall erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ca882-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="ca882-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="ca882-149">lastUpdateTime</span></span> | <span data-ttu-id="ca882-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="ca882-150">DateTimeOffset</span></span> | <span data-ttu-id="ca882-151">Datum und Uhrzeit (in UTC), zu der der Vorfall zuletzt aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ca882-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="ca882-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="ca882-152">assignedTo</span></span> | <span data-ttu-id="ca882-153">string</span><span class="sxs-lookup"><span data-stu-id="ca882-153">string</span></span> | <span data-ttu-id="ca882-154">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="ca882-154">Owner of the Incident.</span></span>
<span data-ttu-id="ca882-155">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="ca882-155">severity</span></span> | <span data-ttu-id="ca882-156">Enum</span><span class="sxs-lookup"><span data-stu-id="ca882-156">Enum</span></span> | <span data-ttu-id="ca882-157">Schweregrad des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="ca882-157">Severity of the Incident.</span></span> <span data-ttu-id="ca882-158">Mögliche Werte sind: ```UnSpecified``` , , , und ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="ca882-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="ca882-159">status</span><span class="sxs-lookup"><span data-stu-id="ca882-159">status</span></span> | <span data-ttu-id="ca882-160">Enum</span><span class="sxs-lookup"><span data-stu-id="ca882-160">Enum</span></span> | <span data-ttu-id="ca882-161">Gibt den aktuellen Status des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="ca882-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="ca882-162">Mögliche Werte sind: ```Active``` , ```Resolved``` und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="ca882-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="ca882-163">classification</span><span class="sxs-lookup"><span data-stu-id="ca882-163">classification</span></span> | <span data-ttu-id="ca882-164">Enum</span><span class="sxs-lookup"><span data-stu-id="ca882-164">Enum</span></span> | <span data-ttu-id="ca882-165">Spezifikation des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="ca882-165">Specification of the incident.</span></span> <span data-ttu-id="ca882-166">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="ca882-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="ca882-167">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="ca882-167">determination</span></span> | <span data-ttu-id="ca882-168">Enum</span><span class="sxs-lookup"><span data-stu-id="ca882-168">Enum</span></span> | <span data-ttu-id="ca882-169">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="ca882-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="ca882-170">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="ca882-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="ca882-171">tags</span><span class="sxs-lookup"><span data-stu-id="ca882-171">tags</span></span> | <span data-ttu-id="ca882-172">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="ca882-172">string List</span></span> | <span data-ttu-id="ca882-173">Liste der Vorfalltags.</span><span class="sxs-lookup"><span data-stu-id="ca882-173">List of Incident tags.</span></span>
<span data-ttu-id="ca882-174">Warnungen</span><span class="sxs-lookup"><span data-stu-id="ca882-174">alerts</span></span> | <span data-ttu-id="ca882-175">Warnungsliste</span><span class="sxs-lookup"><span data-stu-id="ca882-175">Alert List</span></span> | <span data-ttu-id="ca882-176">Liste verwandter Warnungen.</span><span class="sxs-lookup"><span data-stu-id="ca882-176">List of related alerts.</span></span> <span data-ttu-id="ca882-177">Beispiele finden Sie in [der Dokumentation zur API für Listenvorfälle.](api-list-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="ca882-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ca882-178">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="ca882-178">Related articles</span></span>

- [<span data-ttu-id="ca882-179">Übersicht über Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="ca882-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="ca882-180">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="ca882-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="ca882-181">Api zum Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="ca882-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="ca882-182">Vorfall-API aktualisieren</span><span class="sxs-lookup"><span data-stu-id="ca882-182">Update incident API</span></span>](api-update-incidents.md)

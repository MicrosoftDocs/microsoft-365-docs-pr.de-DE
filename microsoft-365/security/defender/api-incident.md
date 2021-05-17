---
title: Microsoft 365 APIs für Defender-Vorfälle und der Ressourcentyp für Vorfälle
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Ressourcentyps Incident in Microsoft 365 Defender
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
ms.openlocfilehash: 0a9022c0448ae0ddc16dc996ca93075abf6b2857
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060819"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="56000-104">Microsoft 365 Defender Incidents-API und der Ressourcentyp für Vorfälle</span><span class="sxs-lookup"><span data-stu-id="56000-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="56000-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="56000-105">**Applies to:**</span></span>

- <span data-ttu-id="56000-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56000-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56000-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="56000-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="56000-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="56000-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="56000-109">Bei [einem Vorfall](incidents-overview.md) handelt es sich um eine Sammlung verwandter Warnungen, die bei der Beschreibung eines Angriffs helfen.</span><span class="sxs-lookup"><span data-stu-id="56000-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="56000-110">Ereignisse aus verschiedenen Entitäten in Ihrer Organisation werden automatisch von defender Microsoft 365 aggregiert.</span><span class="sxs-lookup"><span data-stu-id="56000-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="56000-111">Sie können die Incidents-API verwenden, um programmgesteuert auf die Vorfälle und zugehörigen Warnungen Ihrer Organisation zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="56000-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="56000-112">Kontingente und Ressourcenzuordnung</span><span class="sxs-lookup"><span data-stu-id="56000-112">Quotas and resource allocation</span></span>

<span data-ttu-id="56000-113">Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde anfordern.</span><span class="sxs-lookup"><span data-stu-id="56000-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="56000-114">Jede Methode verfügt auch über eigene Kontingente.</span><span class="sxs-lookup"><span data-stu-id="56000-114">Each method also has its own quotas.</span></span> <span data-ttu-id="56000-115">Weitere Informationen zu methodenspezifischen Kontingenten finden Sie im entsprechenden Artikel für die zu verwendende Methode.</span><span class="sxs-lookup"><span data-stu-id="56000-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="56000-116">Ein HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder nach der Anzahl der gesendeten Anforderungen oder nach der zugewiesenen `429` Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="56000-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="56000-117">Der Antworttext enthält die Zeit bis zum Zurücksetzen des erreichten Kontingents.</span><span class="sxs-lookup"><span data-stu-id="56000-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="56000-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="56000-118">Permissions</span></span>

<span data-ttu-id="56000-119">Die Incidents-API erfordert unterschiedliche Arten von Berechtigungen für jede ihrer Methoden.</span><span class="sxs-lookup"><span data-stu-id="56000-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="56000-120">Weitere Informationen zu den erforderlichen Berechtigungen finden Sie im Artikel der jeweiligen Methode.</span><span class="sxs-lookup"><span data-stu-id="56000-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="56000-121">Methoden</span><span class="sxs-lookup"><span data-stu-id="56000-121">Methods</span></span>

<span data-ttu-id="56000-122">Methode</span><span class="sxs-lookup"><span data-stu-id="56000-122">Method</span></span> | <span data-ttu-id="56000-123">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="56000-123">Return Type</span></span> | <span data-ttu-id="56000-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56000-124">Description</span></span>
-|-|-
[<span data-ttu-id="56000-125">Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="56000-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="56000-126">[Liste der Vorfälle](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="56000-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="56000-127">Hier erhalten Sie eine Liste der Vorfälle.</span><span class="sxs-lookup"><span data-stu-id="56000-127">Get a list of incidents.</span></span>
[<span data-ttu-id="56000-128">Aktualisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="56000-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="56000-129">Vorfall</span><span class="sxs-lookup"><span data-stu-id="56000-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="56000-130">Aktualisieren eines bestimmten Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="56000-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="56000-131">Anforderungstext, Antwort und Beispiele</span><span class="sxs-lookup"><span data-stu-id="56000-131">Request body, response, and examples</span></span>

<span data-ttu-id="56000-132">Weitere Informationen zum Erstellen einer Anforderung oder analysieren einer Antwort sowie praktische Beispiele finden Sie in den jeweiligen Methodenartikeln.</span><span class="sxs-lookup"><span data-stu-id="56000-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="56000-133">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="56000-133">Common properties</span></span>

<span data-ttu-id="56000-134">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="56000-134">Property</span></span> | <span data-ttu-id="56000-135">Typ</span><span class="sxs-lookup"><span data-stu-id="56000-135">Type</span></span> | <span data-ttu-id="56000-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56000-136">Description</span></span>
-|-|-
<span data-ttu-id="56000-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="56000-137">incidentId</span></span> | <span data-ttu-id="56000-138">long</span><span class="sxs-lookup"><span data-stu-id="56000-138">long</span></span> | <span data-ttu-id="56000-139">Eindeutige ID des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="56000-139">Incident unique ID.</span></span>
<span data-ttu-id="56000-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="56000-140">redirectIncidentId</span></span> | <span data-ttu-id="56000-141">Nullable long</span><span class="sxs-lookup"><span data-stu-id="56000-141">nullable long</span></span> | <span data-ttu-id="56000-142">Die Vorfall-ID, mit der der aktuelle Vorfall zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="56000-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="56000-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="56000-143">incidentName</span></span> | <span data-ttu-id="56000-144">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="56000-144">string</span></span> | <span data-ttu-id="56000-145">Der Name des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="56000-145">The name of the Incident.</span></span>
<span data-ttu-id="56000-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="56000-146">createdTime</span></span> | <span data-ttu-id="56000-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="56000-147">DateTimeOffset</span></span> | <span data-ttu-id="56000-148">Das Datum und die Uhrzeit (in UTC), zu der der Vorfall erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="56000-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="56000-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="56000-149">lastUpdateTime</span></span> | <span data-ttu-id="56000-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="56000-150">DateTimeOffset</span></span> | <span data-ttu-id="56000-151">Datum und Uhrzeit (in UTC) der Vorfall wurde zuletzt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="56000-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="56000-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="56000-152">assignedTo</span></span> | <span data-ttu-id="56000-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="56000-153">string</span></span> | <span data-ttu-id="56000-154">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="56000-154">Owner of the Incident.</span></span>
<span data-ttu-id="56000-155">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="56000-155">severity</span></span> | <span data-ttu-id="56000-156">Enum</span><span class="sxs-lookup"><span data-stu-id="56000-156">Enum</span></span> | <span data-ttu-id="56000-157">Schweregrad des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="56000-157">Severity of the Incident.</span></span> <span data-ttu-id="56000-158">Mögliche Werte sind: ```UnSpecified``` , , , , und ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="56000-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="56000-159">status</span><span class="sxs-lookup"><span data-stu-id="56000-159">status</span></span> | <span data-ttu-id="56000-160">Enum</span><span class="sxs-lookup"><span data-stu-id="56000-160">Enum</span></span> | <span data-ttu-id="56000-161">Gibt den aktuellen Status des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="56000-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="56000-162">Mögliche Werte sind: ```Active``` ```Resolved``` , , und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="56000-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="56000-163">classification</span><span class="sxs-lookup"><span data-stu-id="56000-163">classification</span></span> | <span data-ttu-id="56000-164">Enum</span><span class="sxs-lookup"><span data-stu-id="56000-164">Enum</span></span> | <span data-ttu-id="56000-165">Spezifikation des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="56000-165">Specification of the incident.</span></span> <span data-ttu-id="56000-166">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="56000-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="56000-167">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="56000-167">determination</span></span> | <span data-ttu-id="56000-168">Enum</span><span class="sxs-lookup"><span data-stu-id="56000-168">Enum</span></span> | <span data-ttu-id="56000-169">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="56000-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="56000-170">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="56000-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="56000-171">tags</span><span class="sxs-lookup"><span data-stu-id="56000-171">tags</span></span> | <span data-ttu-id="56000-172">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="56000-172">string List</span></span> | <span data-ttu-id="56000-173">Liste der Incident-Tags.</span><span class="sxs-lookup"><span data-stu-id="56000-173">List of Incident tags.</span></span>
<span data-ttu-id="56000-174">Warnungen</span><span class="sxs-lookup"><span data-stu-id="56000-174">alerts</span></span> | <span data-ttu-id="56000-175">Warnungsliste</span><span class="sxs-lookup"><span data-stu-id="56000-175">Alert List</span></span> | <span data-ttu-id="56000-176">Liste der zugehörigen Warnungen.</span><span class="sxs-lookup"><span data-stu-id="56000-176">List of related alerts.</span></span> <span data-ttu-id="56000-177">Beispiele finden Sie unter [List incidents](api-list-incidents.md) API documentation.</span><span class="sxs-lookup"><span data-stu-id="56000-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="56000-178">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="56000-178">Related articles</span></span>

- [<span data-ttu-id="56000-179">Microsoft 365 Übersicht über Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="56000-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="56000-180">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="56000-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="56000-181">Auflisten der Incidents-API</span><span class="sxs-lookup"><span data-stu-id="56000-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="56000-182">Aktualisieren der Vorfall-API</span><span class="sxs-lookup"><span data-stu-id="56000-182">Update incident API</span></span>](api-update-incidents.md)

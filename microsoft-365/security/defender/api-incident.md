---
title: Microsoft 365 Defender Incidents-APIs und der Ressourcentyp "Vorfälle"
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Incidents-Ressourcentyps in Microsoft 365 Defender
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
ms.openlocfilehash: 0c0c2e280f63076687a0854e25c47577b050a8f7
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888433"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="fbdae-104">Microsoft 365 Api für Defender-Vorfälle und der Ressourcentyp "Vorfälle"</span><span class="sxs-lookup"><span data-stu-id="fbdae-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="fbdae-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fbdae-105">**Applies to:**</span></span>

- [<span data-ttu-id="fbdae-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbdae-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="fbdae-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="fbdae-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="fbdae-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="fbdae-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="fbdae-109">Ein [Vorfall](incidents-overview.md) ist eine Sammlung verwandter Warnungen, die einen Angriff beschreiben.</span><span class="sxs-lookup"><span data-stu-id="fbdae-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="fbdae-110">Ereignisse aus verschiedenen Entitäten in Ihrer Organisation werden automatisch von Microsoft 365 Defender aggregiert.</span><span class="sxs-lookup"><span data-stu-id="fbdae-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="fbdae-111">Sie können die Vorfall-API verwenden, um programmgesteuert auf Vorfälle und zugehörige Warnungen Ihrer Organisation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="fbdae-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="fbdae-112">Kontingente und Ressourcenzuweisung</span><span class="sxs-lookup"><span data-stu-id="fbdae-112">Quotas and resource allocation</span></span>

<span data-ttu-id="fbdae-113">Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde anfordern.</span><span class="sxs-lookup"><span data-stu-id="fbdae-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="fbdae-114">Jede Methode verfügt auch über eigene Kontingente.</span><span class="sxs-lookup"><span data-stu-id="fbdae-114">Each method also has its own quotas.</span></span> <span data-ttu-id="fbdae-115">Weitere Informationen zu methodenspezifischen Kontingenten finden Sie im entsprechenden Artikel für die Methode, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="fbdae-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="fbdae-116">Ein `429` HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder nach anzahl der gesendeten Anforderungen oder nach zugewiesener Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="fbdae-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="fbdae-117">Der Antworttext enthält die Zeit bis zum Zurücksetzen des erreichten Kontingents.</span><span class="sxs-lookup"><span data-stu-id="fbdae-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="fbdae-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="fbdae-118">Permissions</span></span>

<span data-ttu-id="fbdae-119">Die Vorfall-API erfordert unterschiedliche Arten von Berechtigungen für jede ihrer Methoden.</span><span class="sxs-lookup"><span data-stu-id="fbdae-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="fbdae-120">Weitere Informationen zu den erforderlichen Berechtigungen finden Sie im Artikel der entsprechenden Methode.</span><span class="sxs-lookup"><span data-stu-id="fbdae-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="fbdae-121">Methoden</span><span class="sxs-lookup"><span data-stu-id="fbdae-121">Methods</span></span>

<span data-ttu-id="fbdae-122">Methode</span><span class="sxs-lookup"><span data-stu-id="fbdae-122">Method</span></span> | <span data-ttu-id="fbdae-123">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="fbdae-123">Return Type</span></span> | <span data-ttu-id="fbdae-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbdae-124">Description</span></span>
-|-|-
[<span data-ttu-id="fbdae-125">Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="fbdae-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="fbdae-126">[Vorfallliste](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="fbdae-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="fbdae-127">Abrufen einer Liste von Vorfällen.</span><span class="sxs-lookup"><span data-stu-id="fbdae-127">Get a list of incidents.</span></span>
[<span data-ttu-id="fbdae-128">Aktualisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="fbdae-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="fbdae-129">Vorfall</span><span class="sxs-lookup"><span data-stu-id="fbdae-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="fbdae-130">Aktualisieren eines bestimmten Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="fbdae-130">Update a specific incident.</span></span>
[<span data-ttu-id="fbdae-131">Vorfall abrufen</span><span class="sxs-lookup"><span data-stu-id="fbdae-131">Get incident</span></span>](api-get-incident.md) | [<span data-ttu-id="fbdae-132">Vorfall</span><span class="sxs-lookup"><span data-stu-id="fbdae-132">Incident</span></span>](api-incident.md) | <span data-ttu-id="fbdae-133">Rufen Sie einen einzelnen Vorfall ab.</span><span class="sxs-lookup"><span data-stu-id="fbdae-133">Get a single incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="fbdae-134">Anforderungstext, Antwort und Beispiele</span><span class="sxs-lookup"><span data-stu-id="fbdae-134">Request body, response, and examples</span></span>

<span data-ttu-id="fbdae-135">Weitere Informationen zum Erstellen einer Anforderung oder Analysieren einer Antwort sowie praktische Beispiele finden Sie in den entsprechenden Methodenartikeln.</span><span class="sxs-lookup"><span data-stu-id="fbdae-135">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="fbdae-136">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fbdae-136">Common properties</span></span>

<span data-ttu-id="fbdae-137">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="fbdae-137">Property</span></span> | <span data-ttu-id="fbdae-138">Typ</span><span class="sxs-lookup"><span data-stu-id="fbdae-138">Type</span></span> | <span data-ttu-id="fbdae-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbdae-139">Description</span></span>
-|-|-
<span data-ttu-id="fbdae-140">incidentId</span><span class="sxs-lookup"><span data-stu-id="fbdae-140">incidentId</span></span> | <span data-ttu-id="fbdae-141">long</span><span class="sxs-lookup"><span data-stu-id="fbdae-141">long</span></span> | <span data-ttu-id="fbdae-142">Eindeutige ID des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="fbdae-142">Incident unique ID.</span></span>
<span data-ttu-id="fbdae-143">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="fbdae-143">redirectIncidentId</span></span> | <span data-ttu-id="fbdae-144">Nullable long</span><span class="sxs-lookup"><span data-stu-id="fbdae-144">nullable long</span></span> | <span data-ttu-id="fbdae-145">Die Vorfall-ID, mit der der aktuelle Vorfall zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="fbdae-145">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="fbdae-146">incidentName</span><span class="sxs-lookup"><span data-stu-id="fbdae-146">incidentName</span></span> | <span data-ttu-id="fbdae-147">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fbdae-147">string</span></span> | <span data-ttu-id="fbdae-148">Der Name des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="fbdae-148">The name of the Incident.</span></span>
<span data-ttu-id="fbdae-149">createdTime</span><span class="sxs-lookup"><span data-stu-id="fbdae-149">createdTime</span></span> | <span data-ttu-id="fbdae-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="fbdae-150">DateTimeOffset</span></span> | <span data-ttu-id="fbdae-151">Das Datum und die Uhrzeit (in UTC), zu der der Vorfall erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fbdae-151">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="fbdae-152">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="fbdae-152">lastUpdateTime</span></span> | <span data-ttu-id="fbdae-153">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="fbdae-153">DateTimeOffset</span></span> | <span data-ttu-id="fbdae-154">Datum und Uhrzeit (in UTC), zu der der Vorfall zuletzt aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fbdae-154">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="fbdae-155">assignedTo</span><span class="sxs-lookup"><span data-stu-id="fbdae-155">assignedTo</span></span> | <span data-ttu-id="fbdae-156">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fbdae-156">string</span></span> | <span data-ttu-id="fbdae-157">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="fbdae-157">Owner of the Incident.</span></span>
<span data-ttu-id="fbdae-158">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="fbdae-158">severity</span></span> | <span data-ttu-id="fbdae-159">Enum</span><span class="sxs-lookup"><span data-stu-id="fbdae-159">Enum</span></span> | <span data-ttu-id="fbdae-160">Schweregrad des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="fbdae-160">Severity of the Incident.</span></span> <span data-ttu-id="fbdae-161">Mögliche Werte sind: ```UnSpecified``` , , , und ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="fbdae-161">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="fbdae-162">status</span><span class="sxs-lookup"><span data-stu-id="fbdae-162">status</span></span> | <span data-ttu-id="fbdae-163">Enum</span><span class="sxs-lookup"><span data-stu-id="fbdae-163">Enum</span></span> | <span data-ttu-id="fbdae-164">Gibt den aktuellen Status des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="fbdae-164">Specifies the current status of the incident.</span></span> <span data-ttu-id="fbdae-165">Mögliche Werte sind: ```Active``` ```Resolved``` , und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="fbdae-165">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="fbdae-166">classification</span><span class="sxs-lookup"><span data-stu-id="fbdae-166">classification</span></span> | <span data-ttu-id="fbdae-167">Enum</span><span class="sxs-lookup"><span data-stu-id="fbdae-167">Enum</span></span> | <span data-ttu-id="fbdae-168">Spezifikation des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="fbdae-168">Specification of the incident.</span></span> <span data-ttu-id="fbdae-169">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="fbdae-169">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="fbdae-170">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="fbdae-170">determination</span></span> | <span data-ttu-id="fbdae-171">Enum</span><span class="sxs-lookup"><span data-stu-id="fbdae-171">Enum</span></span> | <span data-ttu-id="fbdae-172">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="fbdae-172">Specifies the determination of the incident.</span></span> <span data-ttu-id="fbdae-173">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="fbdae-173">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="fbdae-174">tags</span><span class="sxs-lookup"><span data-stu-id="fbdae-174">tags</span></span> | <span data-ttu-id="fbdae-175">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="fbdae-175">string List</span></span> | <span data-ttu-id="fbdae-176">Liste der Vorfalltags.</span><span class="sxs-lookup"><span data-stu-id="fbdae-176">List of Incident tags.</span></span>
<span data-ttu-id="fbdae-177">Kommentare</span><span class="sxs-lookup"><span data-stu-id="fbdae-177">comments</span></span> | <span data-ttu-id="fbdae-178">Liste der Vorfallkommentare</span><span class="sxs-lookup"><span data-stu-id="fbdae-178">List of incident comments</span></span> | <span data-ttu-id="fbdae-179">Incident Comment-Objekt enthält: Kommentarzeichenfolge, createdBy-Zeichenfolge und createTime-Datumszeit.</span><span class="sxs-lookup"><span data-stu-id="fbdae-179">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="fbdae-180">Warnungen</span><span class="sxs-lookup"><span data-stu-id="fbdae-180">alerts</span></span> | <span data-ttu-id="fbdae-181">Warnungsliste</span><span class="sxs-lookup"><span data-stu-id="fbdae-181">Alert List</span></span> | <span data-ttu-id="fbdae-182">Liste verwandter Warnungen.</span><span class="sxs-lookup"><span data-stu-id="fbdae-182">List of related alerts.</span></span> <span data-ttu-id="fbdae-183">Beispiele finden Sie in der API-Dokumentation [für Listenvorfälle.](api-list-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="fbdae-183">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fbdae-184">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="fbdae-184">Related articles</span></span>

- [<span data-ttu-id="fbdae-185">Microsoft 365 Übersicht über Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="fbdae-185">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="fbdae-186">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="fbdae-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="fbdae-187">API zum Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="fbdae-187">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="fbdae-188">Api zum Aktualisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="fbdae-188">Update incident API</span></span>](api-update-incidents.md)

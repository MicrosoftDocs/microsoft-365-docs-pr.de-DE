---
title: Vorfall-Ressourcentyp in der Microsoft Threat Protection-API
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Incident-Ressourcentyps in Microsoft Threat Protection.
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
ms.openlocfilehash: 310e3105c973223ea79373d770eb10f7753b917e
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650330"
---
# <a name="incident-resource-type"></a><span data-ttu-id="26e20-104">Vorfall-Ressourcentyp</span><span class="sxs-lookup"><span data-stu-id="26e20-104">Incident resource type</span></span>

<span data-ttu-id="26e20-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="26e20-105">**Applies to:**</span></span>
- <span data-ttu-id="26e20-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="26e20-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="26e20-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="26e20-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="26e20-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="26e20-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="26e20-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="26e20-109">Methods</span></span>

<span data-ttu-id="26e20-110">Methode</span><span class="sxs-lookup"><span data-stu-id="26e20-110">Method</span></span> |<span data-ttu-id="26e20-111">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="26e20-111">Return Type</span></span> |<span data-ttu-id="26e20-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26e20-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="26e20-113">Vorfälle auflisten</span><span class="sxs-lookup"><span data-stu-id="26e20-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="26e20-114">[Vorfall](api-incident.md) Liste</span><span class="sxs-lookup"><span data-stu-id="26e20-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="26e20-115">Abrufen einer Liste von Vorfällen.</span><span class="sxs-lookup"><span data-stu-id="26e20-115">Get a list of incidents.</span></span>
[<span data-ttu-id="26e20-116">Vorfall aktualisieren</span><span class="sxs-lookup"><span data-stu-id="26e20-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="26e20-117">Vorfall</span><span class="sxs-lookup"><span data-stu-id="26e20-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="26e20-118">Aktualisieren eines bestimmten Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="26e20-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="26e20-119">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="26e20-119">Properties</span></span>

<span data-ttu-id="26e20-120">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="26e20-120">Property</span></span> |    <span data-ttu-id="26e20-121">Typ</span><span class="sxs-lookup"><span data-stu-id="26e20-121">Type</span></span>    |    <span data-ttu-id="26e20-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26e20-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="26e20-123">Vorfall-Nr</span><span class="sxs-lookup"><span data-stu-id="26e20-123">incidentId</span></span> | <span data-ttu-id="26e20-124">long</span><span class="sxs-lookup"><span data-stu-id="26e20-124">long</span></span> | <span data-ttu-id="26e20-125">Vorfall eindeutige ID.</span><span class="sxs-lookup"><span data-stu-id="26e20-125">Incident unique ID.</span></span>
<span data-ttu-id="26e20-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="26e20-126">redirectIncidentId</span></span> | <span data-ttu-id="26e20-127">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="26e20-127">nullable long</span></span> | <span data-ttu-id="26e20-128">Die Vorfall-ID, mit der der aktuelle Vorfall zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="26e20-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="26e20-129">Vorfallname</span><span class="sxs-lookup"><span data-stu-id="26e20-129">incidentName</span></span> | <span data-ttu-id="26e20-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="26e20-130">string</span></span> | <span data-ttu-id="26e20-131">Der Name des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="26e20-131">The name of the Incident.</span></span>
<span data-ttu-id="26e20-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="26e20-132">createdTime</span></span> | <span data-ttu-id="26e20-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="26e20-133">DateTimeOffset</span></span> | <span data-ttu-id="26e20-134">Das Datum und die Uhrzeit (in UTC), an denen der Vorfall erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="26e20-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="26e20-135">Last Update time</span><span class="sxs-lookup"><span data-stu-id="26e20-135">lastUpdateTime</span></span> | <span data-ttu-id="26e20-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="26e20-136">DateTimeOffset</span></span> | <span data-ttu-id="26e20-137">Datum und Uhrzeit (in UTC) der Vorfall wurde zuletzt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="26e20-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="26e20-138">assignedTo</span><span class="sxs-lookup"><span data-stu-id="26e20-138">assignedTo</span></span> | <span data-ttu-id="26e20-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="26e20-139">string</span></span> | <span data-ttu-id="26e20-140">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="26e20-140">Owner of the Incident.</span></span>
<span data-ttu-id="26e20-141">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="26e20-141">severity</span></span> | <span data-ttu-id="26e20-142">Enum</span><span class="sxs-lookup"><span data-stu-id="26e20-142">Enum</span></span> | <span data-ttu-id="26e20-143">Schweregrad des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="26e20-143">Severity of the Incident.</span></span> <span data-ttu-id="26e20-144">Mögliche Werte sind: ```UnSpecified``` , ```Informational``` , ```Low``` ```Medium``` und ```High``` .</span><span class="sxs-lookup"><span data-stu-id="26e20-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="26e20-145">status</span><span class="sxs-lookup"><span data-stu-id="26e20-145">status</span></span> | <span data-ttu-id="26e20-146">Enum</span><span class="sxs-lookup"><span data-stu-id="26e20-146">Enum</span></span> | <span data-ttu-id="26e20-147">Gibt den aktuellen Status des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="26e20-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="26e20-148">Mögliche Werte sind: ```Active``` ```Resolved``` und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="26e20-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="26e20-149">classification</span><span class="sxs-lookup"><span data-stu-id="26e20-149">classification</span></span> | <span data-ttu-id="26e20-150">Enum</span><span class="sxs-lookup"><span data-stu-id="26e20-150">Enum</span></span> | <span data-ttu-id="26e20-151">Spezifikation des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="26e20-151">Specification of the incident.</span></span> <span data-ttu-id="26e20-152">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="26e20-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="26e20-153">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="26e20-153">determination</span></span> | <span data-ttu-id="26e20-154">Enum</span><span class="sxs-lookup"><span data-stu-id="26e20-154">Enum</span></span> | <span data-ttu-id="26e20-155">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="26e20-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="26e20-156">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="26e20-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="26e20-157">tags</span><span class="sxs-lookup"><span data-stu-id="26e20-157">tags</span></span> | <span data-ttu-id="26e20-158">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="26e20-158">string List</span></span> | <span data-ttu-id="26e20-159">Liste der Vorfall Tags.</span><span class="sxs-lookup"><span data-stu-id="26e20-159">List of Incident tags.</span></span>
<span data-ttu-id="26e20-160">Warnungen</span><span class="sxs-lookup"><span data-stu-id="26e20-160">alerts</span></span> | <span data-ttu-id="26e20-161">Warnungsliste</span><span class="sxs-lookup"><span data-stu-id="26e20-161">Alert List</span></span> | <span data-ttu-id="26e20-162">Liste der zugehörigen Warnungen.</span><span class="sxs-lookup"><span data-stu-id="26e20-162">List of related alerts.</span></span> <span data-ttu-id="26e20-163">Siehe Beispiele unter Documentation [List Incidents](api-list-incidents.md) API.</span><span class="sxs-lookup"><span data-stu-id="26e20-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>
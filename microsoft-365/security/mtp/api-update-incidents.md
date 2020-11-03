---
title: Update Incidents-API
description: Informationen zum Aktualisieren von Vorfällen mit der Microsoft 365 Defender-API
keywords: Update, API, Vorfall
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
ms.openlocfilehash: 3f77980863b0c232166d736a6b557444df98c8ac
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844836"
---
# <a name="update-incidents-api"></a><span data-ttu-id="35328-104">Update Incidents-API</span><span class="sxs-lookup"><span data-stu-id="35328-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="35328-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="35328-105">**Applies to:**</span></span>
- <span data-ttu-id="35328-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35328-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="35328-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="35328-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="35328-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="35328-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="35328-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35328-109">API description</span></span>
<span data-ttu-id="35328-110">Aktualisiert die Eigenschaften des vorhandenen Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="35328-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="35328-111">Aktualisierbare Eigenschaften sind: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` und ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="35328-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="35328-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="35328-112">Limitations</span></span>
1. <span data-ttu-id="35328-113">Die Raten Beschränkungen für diese API lauten 50 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="35328-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="35328-114">Sie können den ```determination``` Wert nur festlegen, wenn die Klassifizierung auf TruePositive festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="35328-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="35328-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="35328-115">Permissions</span></span>
<span data-ttu-id="35328-116">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="35328-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="35328-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender APIs](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="35328-117">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="35328-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="35328-118">Permission type</span></span> |   <span data-ttu-id="35328-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="35328-119">Permission</span></span>  |   <span data-ttu-id="35328-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="35328-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="35328-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="35328-121">Application</span></span> |   <span data-ttu-id="35328-122">Incident. ReadWrite. all</span><span class="sxs-lookup"><span data-stu-id="35328-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="35328-123">"Alle Vorfälle lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="35328-123">'Read and write all incidents'</span></span>
<span data-ttu-id="35328-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="35328-124">Delegated (work or school account)</span></span> | <span data-ttu-id="35328-125">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="35328-125">Incident.ReadWrite</span></span> | <span data-ttu-id="35328-126">' Lesen und Schreiben von Vorfällen '</span><span class="sxs-lookup"><span data-stu-id="35328-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="35328-127">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="35328-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="35328-128">Der Benutzer muss über die Berechtigung verfügen, den Vorfall im Portal zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="35328-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="35328-129">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="35328-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="35328-130">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="35328-130">Request headers</span></span>

<span data-ttu-id="35328-131">Name</span><span class="sxs-lookup"><span data-stu-id="35328-131">Name</span></span> | <span data-ttu-id="35328-132">Typ</span><span class="sxs-lookup"><span data-stu-id="35328-132">Type</span></span> | <span data-ttu-id="35328-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35328-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="35328-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="35328-134">Authorization</span></span> | <span data-ttu-id="35328-135">String</span><span class="sxs-lookup"><span data-stu-id="35328-135">String</span></span> | <span data-ttu-id="35328-136">Bearer {Token}.</span><span class="sxs-lookup"><span data-stu-id="35328-136">Bearer {token}.</span></span> <span data-ttu-id="35328-137">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="35328-137">**Required**.</span></span>
<span data-ttu-id="35328-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="35328-138">Content-Type</span></span> | <span data-ttu-id="35328-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="35328-139">String</span></span> | <span data-ttu-id="35328-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="35328-140">application/json.</span></span> <span data-ttu-id="35328-141">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="35328-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="35328-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="35328-142">Request body</span></span>
<span data-ttu-id="35328-143">Geben Sie im Anforderungstext die Werte für die relevanten Felder an, die aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="35328-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="35328-144">Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre vorherigen Werte oder werden basierend auf Änderungen an anderen Eigenschaftswerten neu berechnet.</span><span class="sxs-lookup"><span data-stu-id="35328-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="35328-145">Für eine optimale Leistung sollten Sie keine vorhandenen Werte einbeziehen, die sich nicht geändert haben.</span><span class="sxs-lookup"><span data-stu-id="35328-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="35328-146">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="35328-146">Property</span></span> | <span data-ttu-id="35328-147">Typ</span><span class="sxs-lookup"><span data-stu-id="35328-147">Type</span></span> | <span data-ttu-id="35328-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35328-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="35328-149">status</span><span class="sxs-lookup"><span data-stu-id="35328-149">status</span></span> | <span data-ttu-id="35328-150">Enum</span><span class="sxs-lookup"><span data-stu-id="35328-150">Enum</span></span> | <span data-ttu-id="35328-151">Gibt den aktuellen Status der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="35328-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="35328-152">Mögliche Werte sind: ```Active``` ```Resolved``` und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="35328-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="35328-153">assignedTo</span><span class="sxs-lookup"><span data-stu-id="35328-153">assignedTo</span></span> | <span data-ttu-id="35328-154">string</span><span class="sxs-lookup"><span data-stu-id="35328-154">string</span></span> | <span data-ttu-id="35328-155">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="35328-155">Owner of the incident.</span></span>
<span data-ttu-id="35328-156">classification</span><span class="sxs-lookup"><span data-stu-id="35328-156">classification</span></span> | <span data-ttu-id="35328-157">Enum</span><span class="sxs-lookup"><span data-stu-id="35328-157">Enum</span></span> | <span data-ttu-id="35328-158">Spezifikation der Warnung.</span><span class="sxs-lookup"><span data-stu-id="35328-158">Specification of the alert.</span></span> <span data-ttu-id="35328-159">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="35328-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="35328-160">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="35328-160">determination</span></span> | <span data-ttu-id="35328-161">Enum</span><span class="sxs-lookup"><span data-stu-id="35328-161">Enum</span></span> | <span data-ttu-id="35328-162">Gibt die Bestimmung der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="35328-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="35328-163">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="35328-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="35328-164">tags</span><span class="sxs-lookup"><span data-stu-id="35328-164">tags</span></span> | <span data-ttu-id="35328-165">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="35328-165">string List</span></span> | <span data-ttu-id="35328-166">Liste der Vorfall Tags.</span><span class="sxs-lookup"><span data-stu-id="35328-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="35328-167">Antwort</span><span class="sxs-lookup"><span data-stu-id="35328-167">Response</span></span>
<span data-ttu-id="35328-168">Wenn die Methode erfolgreich verläuft, werden 200 OK und die Vorfall Entität im Antworttext mit den aktualisierten Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="35328-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="35328-169">Wenn Incident mit der angegebenen ID nicht gefunden wurde-404 nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="35328-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="35328-170">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35328-170">Example</span></span>

<span data-ttu-id="35328-171">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="35328-171">**Request**</span></span>

<span data-ttu-id="35328-172">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="35328-172">Here is an example of the request.</span></span>

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a><span data-ttu-id="35328-173">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="35328-173">Related topic</span></span>
- [<span data-ttu-id="35328-174">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="35328-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="35328-175">Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="35328-175">List incidents</span></span>](api-list-incidents.md)

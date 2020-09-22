---
title: Update Incidents-API
description: Informationen zum Aktualisieren von Vorfällen mit der Microsoft Threat Protection-API
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
ms.openlocfilehash: 8ad47453c7163bfac99c17f42986b818cdca603f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203629"
---
# <a name="update-incidents-api"></a><span data-ttu-id="dfdf8-104">Update Incidents-API</span><span class="sxs-lookup"><span data-stu-id="dfdf8-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dfdf8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="dfdf8-105">**Applies to:**</span></span>
- <span data-ttu-id="dfdf8-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="dfdf8-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="dfdf8-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="dfdf8-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="dfdf8-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dfdf8-109">API description</span></span>
<span data-ttu-id="dfdf8-110">Aktualisiert die Eigenschaften des vorhandenen Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="dfdf8-111">Aktualisierbare Eigenschaften sind: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` und ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="dfdf8-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="dfdf8-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="dfdf8-112">Limitations</span></span>
1. <span data-ttu-id="dfdf8-113">Die Raten Beschränkungen für diese API lauten 50 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="dfdf8-114">Sie können den ```determination``` Wert nur festlegen, wenn die Klassifizierung auf TruePositive festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="dfdf8-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="dfdf8-115">Permissions</span></span>
<span data-ttu-id="dfdf8-116">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="dfdf8-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [zugreifen auf die Microsoft Threat Protection-APIs](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="dfdf8-117">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md).</span></span>

<span data-ttu-id="dfdf8-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="dfdf8-118">Permission type</span></span> |   <span data-ttu-id="dfdf8-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="dfdf8-119">Permission</span></span>  |   <span data-ttu-id="dfdf8-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="dfdf8-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="dfdf8-121">Application</span><span class="sxs-lookup"><span data-stu-id="dfdf8-121">Application</span></span> |   <span data-ttu-id="dfdf8-122">Incident. ReadWrite. all</span><span class="sxs-lookup"><span data-stu-id="dfdf8-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="dfdf8-123">"Alle Vorfälle lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="dfdf8-123">'Read and write all incidents'</span></span>
<span data-ttu-id="dfdf8-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="dfdf8-124">Delegated (work or school account)</span></span> | <span data-ttu-id="dfdf8-125">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="dfdf8-125">Incident.ReadWrite</span></span> | <span data-ttu-id="dfdf8-126">' Lesen und Schreiben von Vorfällen '</span><span class="sxs-lookup"><span data-stu-id="dfdf8-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="dfdf8-127">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="dfdf8-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="dfdf8-128">Der Benutzer muss über die Berechtigung verfügen, den Vorfall im Portal zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="dfdf8-129">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="dfdf8-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="dfdf8-130">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="dfdf8-130">Request headers</span></span>

<span data-ttu-id="dfdf8-131">Name</span><span class="sxs-lookup"><span data-stu-id="dfdf8-131">Name</span></span> | <span data-ttu-id="dfdf8-132">Typ</span><span class="sxs-lookup"><span data-stu-id="dfdf8-132">Type</span></span> | <span data-ttu-id="dfdf8-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dfdf8-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="dfdf8-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="dfdf8-134">Authorization</span></span> | <span data-ttu-id="dfdf8-135">String</span><span class="sxs-lookup"><span data-stu-id="dfdf8-135">String</span></span> | <span data-ttu-id="dfdf8-136">Bearer {Token}.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-136">Bearer {token}.</span></span> <span data-ttu-id="dfdf8-137">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-137">**Required**.</span></span>
<span data-ttu-id="dfdf8-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="dfdf8-138">Content-Type</span></span> | <span data-ttu-id="dfdf8-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="dfdf8-139">String</span></span> | <span data-ttu-id="dfdf8-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-140">application/json.</span></span> <span data-ttu-id="dfdf8-141">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="dfdf8-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="dfdf8-142">Request body</span></span>
<span data-ttu-id="dfdf8-143">Geben Sie im Anforderungstext die Werte für die relevanten Felder an, die aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="dfdf8-144">Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre vorherigen Werte oder werden basierend auf Änderungen an anderen Eigenschaftswerten neu berechnet.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="dfdf8-145">Für eine optimale Leistung sollten Sie keine vorhandenen Werte einbeziehen, die sich nicht geändert haben.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="dfdf8-146">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dfdf8-146">Property</span></span> | <span data-ttu-id="dfdf8-147">Typ</span><span class="sxs-lookup"><span data-stu-id="dfdf8-147">Type</span></span> | <span data-ttu-id="dfdf8-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dfdf8-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="dfdf8-149">status</span><span class="sxs-lookup"><span data-stu-id="dfdf8-149">status</span></span> | <span data-ttu-id="dfdf8-150">Enum</span><span class="sxs-lookup"><span data-stu-id="dfdf8-150">Enum</span></span> | <span data-ttu-id="dfdf8-151">Gibt den aktuellen Status der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="dfdf8-152">Mögliche Werte sind: ```Active``` ```Resolved``` und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="dfdf8-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="dfdf8-153">assignedTo</span><span class="sxs-lookup"><span data-stu-id="dfdf8-153">assignedTo</span></span> | <span data-ttu-id="dfdf8-154">string</span><span class="sxs-lookup"><span data-stu-id="dfdf8-154">string</span></span> | <span data-ttu-id="dfdf8-155">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-155">Owner of the incident.</span></span>
<span data-ttu-id="dfdf8-156">classification</span><span class="sxs-lookup"><span data-stu-id="dfdf8-156">classification</span></span> | <span data-ttu-id="dfdf8-157">Enum</span><span class="sxs-lookup"><span data-stu-id="dfdf8-157">Enum</span></span> | <span data-ttu-id="dfdf8-158">Spezifikation der Warnung.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-158">Specification of the alert.</span></span> <span data-ttu-id="dfdf8-159">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="dfdf8-160">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="dfdf8-160">determination</span></span> | <span data-ttu-id="dfdf8-161">Enum</span><span class="sxs-lookup"><span data-stu-id="dfdf8-161">Enum</span></span> | <span data-ttu-id="dfdf8-162">Gibt die Bestimmung der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="dfdf8-163">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="dfdf8-164">tags</span><span class="sxs-lookup"><span data-stu-id="dfdf8-164">tags</span></span> | <span data-ttu-id="dfdf8-165">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="dfdf8-165">string List</span></span> | <span data-ttu-id="dfdf8-166">Liste der Vorfall Tags.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="dfdf8-167">Antwort</span><span class="sxs-lookup"><span data-stu-id="dfdf8-167">Response</span></span>
<span data-ttu-id="dfdf8-168">Wenn die Methode erfolgreich verläuft, werden 200 OK und die Vorfall Entität im Antworttext mit den aktualisierten Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="dfdf8-169">Wenn Incident mit der angegebenen ID nicht gefunden wurde-404 nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="dfdf8-170">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dfdf8-170">Example</span></span>

<span data-ttu-id="dfdf8-171">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="dfdf8-171">**Request**</span></span>

<span data-ttu-id="dfdf8-172">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="dfdf8-172">Here is an example of the request.</span></span>

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


## <a name="related-topic"></a><span data-ttu-id="dfdf8-173">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="dfdf8-173">Related topic</span></span>
- [<span data-ttu-id="dfdf8-174">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="dfdf8-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="dfdf8-175">Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="dfdf8-175">List incidents</span></span>](api-list-incidents.md)

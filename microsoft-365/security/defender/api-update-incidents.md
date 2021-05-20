---
title: Aktualisieren der Vorfall-API
description: Erfahren Sie, wie Sie Vorfälle mithilfe der Microsoft 365 Defender-API aktualisieren
keywords: Update, api, Vorfall
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
ms.openlocfilehash: e3f3919d067078ef1fd1e116dc52e8a73c0726d9
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571781"
---
# <a name="update-incident-api"></a><span data-ttu-id="bdc12-104">Aktualisieren der Vorfall-API</span><span class="sxs-lookup"><span data-stu-id="bdc12-104">Update incident API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bdc12-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bdc12-105">**Applies to:**</span></span>

- <span data-ttu-id="bdc12-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bdc12-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bdc12-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="bdc12-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="bdc12-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="bdc12-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="bdc12-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bdc12-109">API description</span></span>

<span data-ttu-id="bdc12-110">Aktualisiert die Eigenschaften vorhandener Vorfälle.</span><span class="sxs-lookup"><span data-stu-id="bdc12-110">Updates properties of existing incident.</span></span> <span data-ttu-id="bdc12-111">Updatable Eigenschaften sind: ```status``` , , , , und ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .</span><span class="sxs-lookup"><span data-stu-id="bdc12-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="bdc12-112">Kontingente, Ressourcenzuweisung und andere Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="bdc12-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="bdc12-113">Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde tätigen, bevor Sie die Drosselschwelle erreichen.</span><span class="sxs-lookup"><span data-stu-id="bdc12-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="bdc12-114">Sie können die `determination` Eigenschaft nur festlegen, wenn `classification` auf TruePositive festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bdc12-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="bdc12-115">Wenn Ihre Anforderung gedrosselt wird, wird ein `429` Antwortcode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bdc12-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="bdc12-116">Der Antworttext gibt den Zeitpunkt an, zu dem Sie mit neuen Anrufen beginnen können.</span><span class="sxs-lookup"><span data-stu-id="bdc12-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="bdc12-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bdc12-117">Permissions</span></span>

<span data-ttu-id="bdc12-118">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="bdc12-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bdc12-119">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Zugriff auf die Microsoft 365 Defender-APIs](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="bdc12-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="bdc12-120">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="bdc12-120">Permission type</span></span> | <span data-ttu-id="bdc12-121">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="bdc12-121">Permission</span></span> | <span data-ttu-id="bdc12-122">Name der Berechtigungsanzeige</span><span class="sxs-lookup"><span data-stu-id="bdc12-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="bdc12-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="bdc12-123">Application</span></span> | <span data-ttu-id="bdc12-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="bdc12-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="bdc12-125">Lesen und Schreiben aller Vorfälle</span><span class="sxs-lookup"><span data-stu-id="bdc12-125">Read and write all incidents</span></span>
<span data-ttu-id="bdc12-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="bdc12-126">Delegated (work or school account)</span></span> | <span data-ttu-id="bdc12-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="bdc12-127">Incident.ReadWrite</span></span> | <span data-ttu-id="bdc12-128">Vorkommnisse lesen und schreiben</span><span class="sxs-lookup"><span data-stu-id="bdc12-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="bdc12-129">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen muss der Benutzer über die Berechtigung zum Aktualisieren des Vorfalls im Portal verfügen.</span><span class="sxs-lookup"><span data-stu-id="bdc12-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="bdc12-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="bdc12-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="bdc12-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="bdc12-131">Request headers</span></span>

<span data-ttu-id="bdc12-132">Name</span><span class="sxs-lookup"><span data-stu-id="bdc12-132">Name</span></span> | <span data-ttu-id="bdc12-133">Typ</span><span class="sxs-lookup"><span data-stu-id="bdc12-133">Type</span></span> | <span data-ttu-id="bdc12-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bdc12-134">Description</span></span>
-|-|-
<span data-ttu-id="bdc12-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="bdc12-135">Authorization</span></span> | <span data-ttu-id="bdc12-136">String</span><span class="sxs-lookup"><span data-stu-id="bdc12-136">String</span></span> | <span data-ttu-id="bdc12-137">Träger 'Token'.</span><span class="sxs-lookup"><span data-stu-id="bdc12-137">Bearer {token}.</span></span> <span data-ttu-id="bdc12-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="bdc12-138">**Required**.</span></span>
<span data-ttu-id="bdc12-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="bdc12-139">Content-Type</span></span> | <span data-ttu-id="bdc12-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="bdc12-140">String</span></span> | <span data-ttu-id="bdc12-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="bdc12-141">application/json.</span></span> <span data-ttu-id="bdc12-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="bdc12-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="bdc12-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="bdc12-143">Request body</span></span>

<span data-ttu-id="bdc12-144">Geben Sie im Anforderungstext die Werte für die Felder ein, die aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bdc12-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="bdc12-145">Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre Werte bei, es sei denn, sie müssen aufgrund von Änderungen an verwandten Werten neu berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="bdc12-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="bdc12-146">Um eine optimale Leistung zu erzielen, sollten Sie vorhandene Werte weglassen, die sich nicht geändert haben.</span><span class="sxs-lookup"><span data-stu-id="bdc12-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="bdc12-147">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bdc12-147">Property</span></span> | <span data-ttu-id="bdc12-148">Typ</span><span class="sxs-lookup"><span data-stu-id="bdc12-148">Type</span></span> | <span data-ttu-id="bdc12-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bdc12-149">Description</span></span>
-|-|-
<span data-ttu-id="bdc12-150">status</span><span class="sxs-lookup"><span data-stu-id="bdc12-150">status</span></span> | <span data-ttu-id="bdc12-151">Enum</span><span class="sxs-lookup"><span data-stu-id="bdc12-151">Enum</span></span> | <span data-ttu-id="bdc12-152">Gibt den aktuellen Status des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="bdc12-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="bdc12-153">Mögliche Werte sind: ```Active``` , ```Resolved``` , und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="bdc12-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="bdc12-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="bdc12-154">assignedTo</span></span> | <span data-ttu-id="bdc12-155">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="bdc12-155">string</span></span> | <span data-ttu-id="bdc12-156">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="bdc12-156">Owner of the incident.</span></span>
<span data-ttu-id="bdc12-157">classification</span><span class="sxs-lookup"><span data-stu-id="bdc12-157">classification</span></span> | <span data-ttu-id="bdc12-158">Enum</span><span class="sxs-lookup"><span data-stu-id="bdc12-158">Enum</span></span> | <span data-ttu-id="bdc12-159">Spezifikation des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="bdc12-159">Specification of the incident.</span></span> <span data-ttu-id="bdc12-160">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="bdc12-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="bdc12-161">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="bdc12-161">determination</span></span> | <span data-ttu-id="bdc12-162">Enum</span><span class="sxs-lookup"><span data-stu-id="bdc12-162">Enum</span></span> | <span data-ttu-id="bdc12-163">Gibt die Bestimmung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="bdc12-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="bdc12-164">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="bdc12-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="bdc12-165">tags</span><span class="sxs-lookup"><span data-stu-id="bdc12-165">tags</span></span> | <span data-ttu-id="bdc12-166">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="bdc12-166">string List</span></span> | <span data-ttu-id="bdc12-167">Liste der Incident-Tags.</span><span class="sxs-lookup"><span data-stu-id="bdc12-167">List of Incident tags.</span></span>
<span data-ttu-id="bdc12-168">Kommentar</span><span class="sxs-lookup"><span data-stu-id="bdc12-168">comment</span></span> | <span data-ttu-id="bdc12-169">string</span><span class="sxs-lookup"><span data-stu-id="bdc12-169">string</span></span> | <span data-ttu-id="bdc12-170">Kommentar, der dem Vorfall hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bdc12-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="bdc12-171">Antwort</span><span class="sxs-lookup"><span data-stu-id="bdc12-171">Response</span></span>

<span data-ttu-id="bdc12-172">Bei Erfolg gibt diese Methode `200 OK` zurück.</span><span class="sxs-lookup"><span data-stu-id="bdc12-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="bdc12-173">Der Antworttext enthält die Ereignisentität mit aktualisierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="bdc12-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="bdc12-174">Wenn kein Vorfall mit der angegebenen ID gefunden wurde, gibt die Methode `404 Not Found` zurück.</span><span class="sxs-lookup"><span data-stu-id="bdc12-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="bdc12-175">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bdc12-175">Example</span></span>

<span data-ttu-id="bdc12-176">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="bdc12-176">**Request**</span></span>

<span data-ttu-id="bdc12-177">Hier ist ein Beispiel für die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="bdc12-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="bdc12-178">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="bdc12-178">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a><span data-ttu-id="bdc12-179">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="bdc12-179">Related articles</span></span>

- [<span data-ttu-id="bdc12-180">Zugriff auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="bdc12-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="bdc12-181">Informationen zu API-Limits und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="bdc12-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="bdc12-182">Verstehen von Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="bdc12-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="bdc12-183">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="bdc12-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="bdc12-184">Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="bdc12-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="bdc12-185">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="bdc12-185">Incidents overview</span></span>](incidents-overview.md)

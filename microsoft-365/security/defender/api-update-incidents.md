---
title: Aktualisieren der Vorfall-API
description: Informationen zum Aktualisieren von Vorfällen mithilfe Microsoft 365 Defender-API
keywords: update, api, incident
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
# <a name="update-incident-api"></a><span data-ttu-id="8fe81-104">Aktualisieren der Vorfall-API</span><span class="sxs-lookup"><span data-stu-id="8fe81-104">Update incident API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8fe81-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8fe81-105">**Applies to:**</span></span>

- <span data-ttu-id="8fe81-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8fe81-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fe81-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="8fe81-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8fe81-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="8fe81-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="8fe81-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fe81-109">API description</span></span>

<span data-ttu-id="8fe81-110">Aktualisiert die Eigenschaften vorhandener Vorfälle.</span><span class="sxs-lookup"><span data-stu-id="8fe81-110">Updates properties of existing incident.</span></span> <span data-ttu-id="8fe81-111">Updatable Eigenschaften sind: ```status``` , , , , , und ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .</span><span class="sxs-lookup"><span data-stu-id="8fe81-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="8fe81-112">Kontingente, Ressourcenzuordnung und andere Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8fe81-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="8fe81-113">Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde machen, bevor Sie den Drosselungsschwellenwert erreichen.</span><span class="sxs-lookup"><span data-stu-id="8fe81-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="8fe81-114">Sie können die Eigenschaft `determination` nur festlegen, `classification` wenn truePositive festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8fe81-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="8fe81-115">Wenn Ihre Anforderung gedrosselt wird, gibt sie einen `429` Antwortcode zurück.</span><span class="sxs-lookup"><span data-stu-id="8fe81-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="8fe81-116">Der Antworttext gibt den Zeitpunkt an, zu dem Sie mit dem Starten neuer Anrufe beginnen können.</span><span class="sxs-lookup"><span data-stu-id="8fe81-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="8fe81-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8fe81-117">Permissions</span></span>

<span data-ttu-id="8fe81-118">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8fe81-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8fe81-119">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender APIs](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="8fe81-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="8fe81-120">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="8fe81-120">Permission type</span></span> | <span data-ttu-id="8fe81-121">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8fe81-121">Permission</span></span> | <span data-ttu-id="8fe81-122">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8fe81-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="8fe81-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="8fe81-123">Application</span></span> | <span data-ttu-id="8fe81-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8fe81-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="8fe81-125">Lesen und Schreiben aller Vorfälle</span><span class="sxs-lookup"><span data-stu-id="8fe81-125">Read and write all incidents</span></span>
<span data-ttu-id="8fe81-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="8fe81-126">Delegated (work or school account)</span></span> | <span data-ttu-id="8fe81-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8fe81-127">Incident.ReadWrite</span></span> | <span data-ttu-id="8fe81-128">Lese- und Schreibvorfälle</span><span class="sxs-lookup"><span data-stu-id="8fe81-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="8fe81-129">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen benötigt der Benutzer die Berechtigung, den Vorfall im Portal zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8fe81-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="8fe81-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="8fe81-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="8fe81-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="8fe81-131">Request headers</span></span>

<span data-ttu-id="8fe81-132">Name</span><span class="sxs-lookup"><span data-stu-id="8fe81-132">Name</span></span> | <span data-ttu-id="8fe81-133">Typ</span><span class="sxs-lookup"><span data-stu-id="8fe81-133">Type</span></span> | <span data-ttu-id="8fe81-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fe81-134">Description</span></span>
-|-|-
<span data-ttu-id="8fe81-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="8fe81-135">Authorization</span></span> | <span data-ttu-id="8fe81-136">String</span><span class="sxs-lookup"><span data-stu-id="8fe81-136">String</span></span> | <span data-ttu-id="8fe81-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8fe81-137">Bearer {token}.</span></span> <span data-ttu-id="8fe81-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8fe81-138">**Required**.</span></span>
<span data-ttu-id="8fe81-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8fe81-139">Content-Type</span></span> | <span data-ttu-id="8fe81-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8fe81-140">String</span></span> | <span data-ttu-id="8fe81-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="8fe81-141">application/json.</span></span> <span data-ttu-id="8fe81-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8fe81-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8fe81-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="8fe81-143">Request body</span></span>

<span data-ttu-id="8fe81-144">Stellen Sie im Anforderungstext die Werte für die Felder zur Verfügung, die aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8fe81-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="8fe81-145">Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre Werte bei, es sei denn, sie müssen aufgrund von Änderungen an verwandten Werten neu berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="8fe81-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="8fe81-146">Um eine optimale Leistung zu erzielen, sollten Sie vorhandene Werte auslassen, die sich nicht geändert haben.</span><span class="sxs-lookup"><span data-stu-id="8fe81-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="8fe81-147">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8fe81-147">Property</span></span> | <span data-ttu-id="8fe81-148">Typ</span><span class="sxs-lookup"><span data-stu-id="8fe81-148">Type</span></span> | <span data-ttu-id="8fe81-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fe81-149">Description</span></span>
-|-|-
<span data-ttu-id="8fe81-150">status</span><span class="sxs-lookup"><span data-stu-id="8fe81-150">status</span></span> | <span data-ttu-id="8fe81-151">Enum</span><span class="sxs-lookup"><span data-stu-id="8fe81-151">Enum</span></span> | <span data-ttu-id="8fe81-152">Gibt den aktuellen Status des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="8fe81-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="8fe81-153">Mögliche Werte sind: ```Active``` ```Resolved``` , , und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="8fe81-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="8fe81-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="8fe81-154">assignedTo</span></span> | <span data-ttu-id="8fe81-155">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8fe81-155">string</span></span> | <span data-ttu-id="8fe81-156">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="8fe81-156">Owner of the incident.</span></span>
<span data-ttu-id="8fe81-157">classification</span><span class="sxs-lookup"><span data-stu-id="8fe81-157">classification</span></span> | <span data-ttu-id="8fe81-158">Enum</span><span class="sxs-lookup"><span data-stu-id="8fe81-158">Enum</span></span> | <span data-ttu-id="8fe81-159">Spezifikation des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="8fe81-159">Specification of the incident.</span></span> <span data-ttu-id="8fe81-160">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="8fe81-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="8fe81-161">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="8fe81-161">determination</span></span> | <span data-ttu-id="8fe81-162">Enum</span><span class="sxs-lookup"><span data-stu-id="8fe81-162">Enum</span></span> | <span data-ttu-id="8fe81-163">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="8fe81-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="8fe81-164">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="8fe81-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="8fe81-165">tags</span><span class="sxs-lookup"><span data-stu-id="8fe81-165">tags</span></span> | <span data-ttu-id="8fe81-166">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="8fe81-166">string List</span></span> | <span data-ttu-id="8fe81-167">Liste der Incident-Tags.</span><span class="sxs-lookup"><span data-stu-id="8fe81-167">List of Incident tags.</span></span>
<span data-ttu-id="8fe81-168">Kommentar</span><span class="sxs-lookup"><span data-stu-id="8fe81-168">comment</span></span> | <span data-ttu-id="8fe81-169">string</span><span class="sxs-lookup"><span data-stu-id="8fe81-169">string</span></span> | <span data-ttu-id="8fe81-170">Kommentar, der dem Vorfall hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8fe81-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="8fe81-171">Antwort</span><span class="sxs-lookup"><span data-stu-id="8fe81-171">Response</span></span>

<span data-ttu-id="8fe81-172">Wenn die Methode erfolgreich ist, gibt sie `200 OK` zurück.</span><span class="sxs-lookup"><span data-stu-id="8fe81-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="8fe81-173">Der Antworttext enthält die Vorfallentität mit aktualisierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="8fe81-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="8fe81-174">Wenn ein Vorfall mit der angegebenen ID nicht gefunden wurde, gibt die Methode `404 Not Found` zurück.</span><span class="sxs-lookup"><span data-stu-id="8fe81-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="8fe81-175">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8fe81-175">Example</span></span>

<span data-ttu-id="8fe81-176">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="8fe81-176">**Request**</span></span>

<span data-ttu-id="8fe81-177">Hier sehen Sie ein Beispiel für die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="8fe81-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="8fe81-178">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="8fe81-178">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="8fe81-179">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="8fe81-179">Related articles</span></span>

- [<span data-ttu-id="8fe81-180">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="8fe81-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="8fe81-181">Informationen zu API-Beschränkungen und -Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="8fe81-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="8fe81-182">Verstehen von Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="8fe81-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="8fe81-183">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="8fe81-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="8fe81-184">Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="8fe81-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="8fe81-185">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="8fe81-185">Incidents overview</span></span>](incidents-overview.md)

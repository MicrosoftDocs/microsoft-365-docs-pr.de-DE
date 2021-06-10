---
title: Api zum Aktualisieren von Vorfällen
description: Erfahren Sie, wie Sie Vorfälle mithilfe Microsoft 365 Defender-API aktualisieren.
keywords: Update, API, Vorfall
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
ms.openlocfilehash: b50fe4672dd4cd721464c7414297efcc4a4921b7
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861503"
---
# <a name="update-incidents-api"></a><span data-ttu-id="c4919-104">API zum Aktualisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="c4919-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c4919-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c4919-105">**Applies to:**</span></span>

- [<span data-ttu-id="c4919-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4919-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="c4919-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="c4919-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c4919-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="c4919-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="c4919-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4919-109">API description</span></span>

<span data-ttu-id="c4919-110">Aktualisiert die Eigenschaften eines vorhandenen Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="c4919-110">Updates properties of existing incident.</span></span> <span data-ttu-id="c4919-111">Aktualisierbare Eigenschaften sind: ```status``` , , , , und ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .</span><span class="sxs-lookup"><span data-stu-id="c4919-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="c4919-112">Kontingente, Ressourcenzuweisung und andere Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c4919-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="c4919-113">Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde tätigen, bevor Sie den Einschränkungsschwellenwert erreichen.</span><span class="sxs-lookup"><span data-stu-id="c4919-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="c4919-114">Sie können die `determination` Eigenschaft nur festlegen, wenn `classification` sie auf "TruePositive" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c4919-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="c4919-115">Wenn Ihre Anforderung gedrosselt wird, wird ein `429` Antwortcode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c4919-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="c4919-116">Der Antworttext gibt den Zeitpunkt an, zu dem Sie mit neuen Aufrufen beginnen können.</span><span class="sxs-lookup"><span data-stu-id="c4919-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="c4919-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c4919-117">Permissions</span></span>

<span data-ttu-id="c4919-118">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c4919-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c4919-119">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender APIs.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="c4919-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="c4919-120">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="c4919-120">Permission type</span></span> | <span data-ttu-id="c4919-121">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c4919-121">Permission</span></span> | <span data-ttu-id="c4919-122">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c4919-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="c4919-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="c4919-123">Application</span></span> | <span data-ttu-id="c4919-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c4919-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="c4919-125">Lesen und Schreiben aller Vorfälle</span><span class="sxs-lookup"><span data-stu-id="c4919-125">Read and write all incidents</span></span>
<span data-ttu-id="c4919-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="c4919-126">Delegated (work or school account)</span></span> | <span data-ttu-id="c4919-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c4919-127">Incident.ReadWrite</span></span> | <span data-ttu-id="c4919-128">Lesen und Schreiben von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="c4919-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="c4919-129">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen muss der Benutzer über die Berechtigung zum Aktualisieren des Vorfalls im Portal verfügen.</span><span class="sxs-lookup"><span data-stu-id="c4919-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="c4919-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="c4919-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="c4919-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="c4919-131">Request headers</span></span>

<span data-ttu-id="c4919-132">Name</span><span class="sxs-lookup"><span data-stu-id="c4919-132">Name</span></span> | <span data-ttu-id="c4919-133">Typ</span><span class="sxs-lookup"><span data-stu-id="c4919-133">Type</span></span> | <span data-ttu-id="c4919-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4919-134">Description</span></span>
-|-|-
<span data-ttu-id="c4919-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="c4919-135">Authorization</span></span> | <span data-ttu-id="c4919-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c4919-136">String</span></span> | <span data-ttu-id="c4919-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c4919-137">Bearer {token}.</span></span> <span data-ttu-id="c4919-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="c4919-138">**Required**.</span></span>
<span data-ttu-id="c4919-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c4919-139">Content-Type</span></span> | <span data-ttu-id="c4919-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c4919-140">String</span></span> | <span data-ttu-id="c4919-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="c4919-141">application/json.</span></span> <span data-ttu-id="c4919-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="c4919-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c4919-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="c4919-143">Request body</span></span>

<span data-ttu-id="c4919-144">Geben Sie im Anforderungstext die Werte für die Felder an, die aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c4919-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="c4919-145">Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre Werte bei, es sei denn, sie müssen aufgrund von Änderungen an verwandten Werten neu berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="c4919-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="c4919-146">Um eine optimale Leistung zu erzielen, sollten Sie vorhandene Werte auslassen, die sich nicht geändert haben.</span><span class="sxs-lookup"><span data-stu-id="c4919-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="c4919-147">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c4919-147">Property</span></span> | <span data-ttu-id="c4919-148">Typ</span><span class="sxs-lookup"><span data-stu-id="c4919-148">Type</span></span> | <span data-ttu-id="c4919-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4919-149">Description</span></span>
-|-|-
<span data-ttu-id="c4919-150">status</span><span class="sxs-lookup"><span data-stu-id="c4919-150">status</span></span> | <span data-ttu-id="c4919-151">Enum</span><span class="sxs-lookup"><span data-stu-id="c4919-151">Enum</span></span> | <span data-ttu-id="c4919-152">Gibt den aktuellen Status des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="c4919-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="c4919-153">Mögliche Werte sind: ```Active``` ```Resolved``` , und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="c4919-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="c4919-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="c4919-154">assignedTo</span></span> | <span data-ttu-id="c4919-155">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c4919-155">string</span></span> | <span data-ttu-id="c4919-156">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="c4919-156">Owner of the incident.</span></span>
<span data-ttu-id="c4919-157">classification</span><span class="sxs-lookup"><span data-stu-id="c4919-157">classification</span></span> | <span data-ttu-id="c4919-158">Enum</span><span class="sxs-lookup"><span data-stu-id="c4919-158">Enum</span></span> | <span data-ttu-id="c4919-159">Spezifikation des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="c4919-159">Specification of the incident.</span></span> <span data-ttu-id="c4919-160">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="c4919-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="c4919-161">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="c4919-161">determination</span></span> | <span data-ttu-id="c4919-162">Enum</span><span class="sxs-lookup"><span data-stu-id="c4919-162">Enum</span></span> | <span data-ttu-id="c4919-163">Gibt die Ermittlung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="c4919-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="c4919-164">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="c4919-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="c4919-165">tags</span><span class="sxs-lookup"><span data-stu-id="c4919-165">tags</span></span> | <span data-ttu-id="c4919-166">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="c4919-166">string List</span></span> | <span data-ttu-id="c4919-167">Liste der Vorfalltags.</span><span class="sxs-lookup"><span data-stu-id="c4919-167">List of Incident tags.</span></span>
<span data-ttu-id="c4919-168">Kommentar</span><span class="sxs-lookup"><span data-stu-id="c4919-168">comment</span></span> | <span data-ttu-id="c4919-169">string</span><span class="sxs-lookup"><span data-stu-id="c4919-169">string</span></span> | <span data-ttu-id="c4919-170">Kommentar, der dem Vorfall hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c4919-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="c4919-171">Antwort</span><span class="sxs-lookup"><span data-stu-id="c4919-171">Response</span></span>

<span data-ttu-id="c4919-172">Wenn die Methode erfolgreich ist, wird `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="c4919-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="c4919-173">Der Antworttext enthält die Vorfallentität mit aktualisierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c4919-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="c4919-174">Wenn ein Vorfall mit der angegebenen ID nicht gefunden wurde, gibt die Methode `404 Not Found` zurück.</span><span class="sxs-lookup"><span data-stu-id="c4919-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="c4919-175">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c4919-175">Example</span></span>

<span data-ttu-id="c4919-176">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="c4919-176">**Request**</span></span>

<span data-ttu-id="c4919-177">Hier ist ein Beispiel für die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="c4919-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="c4919-178">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="c4919-178">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="c4919-179">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="c4919-179">Related articles</span></span>

- [<span data-ttu-id="c4919-180">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="c4919-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="c4919-181">Informationen zu API-Grenzwerten und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="c4919-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="c4919-182">Grundlegendes zu Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="c4919-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="c4919-183">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="c4919-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="c4919-184">Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="c4919-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="c4919-185">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="c4919-185">Incidents overview</span></span>](incidents-overview.md)

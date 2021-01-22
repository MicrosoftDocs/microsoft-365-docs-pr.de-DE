---
title: Api zum Aktualisieren von Vorfällen
description: Erfahren Sie, wie Sie Vorfälle mithilfe der Microsoft 365 Defender-API aktualisieren.
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929070"
---
# <a name="update-incidents-api"></a><span data-ttu-id="994a9-104">Api zum Aktualisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="994a9-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="994a9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="994a9-105">**Applies to:**</span></span>

- <span data-ttu-id="994a9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="994a9-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="994a9-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="994a9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="994a9-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="994a9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="994a9-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="994a9-109">API description</span></span>

<span data-ttu-id="994a9-110">Aktualisiert die Eigenschaften vorhandener Vorfälle.</span><span class="sxs-lookup"><span data-stu-id="994a9-110">Updates properties of existing incident.</span></span> <span data-ttu-id="994a9-111">Updatable eigenschaften are: ```status``` , , , , and ```determination``` ```classification``` ```assignedTo``` ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="994a9-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="994a9-112">Kontingente, Ressourcenzuordnung und andere Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="994a9-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="994a9-113">Sie können bis zu 50 Anrufe pro Minute oder 1.500 Anrufe pro Stunde machen, bevor Sie den Einschränkungsschwellenwert erreichen.</span><span class="sxs-lookup"><span data-stu-id="994a9-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="994a9-114">Sie können die Eigenschaft `determination` nur festlegen, wenn `classification` sie auf "TruePositive" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="994a9-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="994a9-115">Wenn Ihre Anforderung gedrosselt ist, gibt sie einen `429` Antwortcode zurück.</span><span class="sxs-lookup"><span data-stu-id="994a9-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="994a9-116">Der Antworttext gibt den Zeitpunkt an, zu dem Sie mit dem Starten neuer Anrufe beginnen können.</span><span class="sxs-lookup"><span data-stu-id="994a9-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="994a9-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="994a9-117">Permissions</span></span>

<span data-ttu-id="994a9-118">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="994a9-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="994a9-119">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender APIs](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="994a9-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="994a9-120">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="994a9-120">Permission type</span></span> | <span data-ttu-id="994a9-121">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="994a9-121">Permission</span></span> | <span data-ttu-id="994a9-122">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="994a9-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="994a9-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="994a9-123">Application</span></span> | <span data-ttu-id="994a9-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="994a9-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="994a9-125">Lesen und Schreiben aller Vorfälle</span><span class="sxs-lookup"><span data-stu-id="994a9-125">Read and write all incidents</span></span>
<span data-ttu-id="994a9-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="994a9-126">Delegated (work or school account)</span></span> | <span data-ttu-id="994a9-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="994a9-127">Incident.ReadWrite</span></span> | <span data-ttu-id="994a9-128">Lesen und Schreiben von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="994a9-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="994a9-129">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen benötigt der Benutzer die Berechtigung, den Vorfall im Portal zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="994a9-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="994a9-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="994a9-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="994a9-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="994a9-131">Request headers</span></span>

<span data-ttu-id="994a9-132">Name</span><span class="sxs-lookup"><span data-stu-id="994a9-132">Name</span></span> | <span data-ttu-id="994a9-133">Typ</span><span class="sxs-lookup"><span data-stu-id="994a9-133">Type</span></span> | <span data-ttu-id="994a9-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="994a9-134">Description</span></span>
-|-|-
<span data-ttu-id="994a9-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="994a9-135">Authorization</span></span> | <span data-ttu-id="994a9-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="994a9-136">String</span></span> | <span data-ttu-id="994a9-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="994a9-137">Bearer {token}.</span></span> <span data-ttu-id="994a9-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="994a9-138">**Required**.</span></span>
<span data-ttu-id="994a9-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="994a9-139">Content-Type</span></span> | <span data-ttu-id="994a9-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="994a9-140">String</span></span> | <span data-ttu-id="994a9-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="994a9-141">application/json.</span></span> <span data-ttu-id="994a9-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="994a9-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="994a9-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="994a9-143">Request body</span></span>

<span data-ttu-id="994a9-144">Stellen Sie im Anforderungstext die Werte für die Felder fest, die aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="994a9-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="994a9-145">Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre Werte bei, es sei denn, sie müssen aufgrund von Änderungen an verwandten Werten neu berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="994a9-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="994a9-146">Um eine optimale Leistung zu erzielen, sollten Sie vorhandene Werte auslassen, die sich nicht geändert haben.</span><span class="sxs-lookup"><span data-stu-id="994a9-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="994a9-147">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="994a9-147">Property</span></span> | <span data-ttu-id="994a9-148">Typ</span><span class="sxs-lookup"><span data-stu-id="994a9-148">Type</span></span> | <span data-ttu-id="994a9-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="994a9-149">Description</span></span>
-|-|-
<span data-ttu-id="994a9-150">status</span><span class="sxs-lookup"><span data-stu-id="994a9-150">status</span></span> | <span data-ttu-id="994a9-151">Enum</span><span class="sxs-lookup"><span data-stu-id="994a9-151">Enum</span></span> | <span data-ttu-id="994a9-152">Gibt den aktuellen Status der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="994a9-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="994a9-153">Mögliche Werte sind: ```Active``` ```Resolved``` , und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="994a9-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="994a9-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="994a9-154">assignedTo</span></span> | <span data-ttu-id="994a9-155">string</span><span class="sxs-lookup"><span data-stu-id="994a9-155">string</span></span> | <span data-ttu-id="994a9-156">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="994a9-156">Owner of the incident.</span></span>
<span data-ttu-id="994a9-157">classification</span><span class="sxs-lookup"><span data-stu-id="994a9-157">classification</span></span> | <span data-ttu-id="994a9-158">Enum</span><span class="sxs-lookup"><span data-stu-id="994a9-158">Enum</span></span> | <span data-ttu-id="994a9-159">Spezifikation der Warnung.</span><span class="sxs-lookup"><span data-stu-id="994a9-159">Specification of the alert.</span></span> <span data-ttu-id="994a9-160">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="994a9-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="994a9-161">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="994a9-161">determination</span></span> | <span data-ttu-id="994a9-162">Enum</span><span class="sxs-lookup"><span data-stu-id="994a9-162">Enum</span></span> | <span data-ttu-id="994a9-163">Gibt die Bestimmung der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="994a9-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="994a9-164">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="994a9-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="994a9-165">tags</span><span class="sxs-lookup"><span data-stu-id="994a9-165">tags</span></span> | <span data-ttu-id="994a9-166">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="994a9-166">string List</span></span> | <span data-ttu-id="994a9-167">Liste der Vorfalltags.</span><span class="sxs-lookup"><span data-stu-id="994a9-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="994a9-168">Antwort</span><span class="sxs-lookup"><span data-stu-id="994a9-168">Response</span></span>

<span data-ttu-id="994a9-169">Wenn die Methode erfolgreich ist, wird sie `200 OK` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="994a9-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="994a9-170">Der Antworttext enthält die Vorfallentität mit aktualisierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="994a9-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="994a9-171">Wenn ein Vorfall mit der angegebenen ID nicht gefunden wurde, gibt die Methode `404 Not Found` zurück.</span><span class="sxs-lookup"><span data-stu-id="994a9-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="994a9-172">Beispiel</span><span class="sxs-lookup"><span data-stu-id="994a9-172">Example</span></span>

<span data-ttu-id="994a9-173">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="994a9-173">**Request**</span></span>

<span data-ttu-id="994a9-174">Hier ist ein Beispiel für die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="994a9-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="994a9-175">**Response**</span><span class="sxs-lookup"><span data-stu-id="994a9-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="994a9-176">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="994a9-176">Related articles</span></span>

- [<span data-ttu-id="994a9-177">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="994a9-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="994a9-178">Informationen zu API-Beschränkungen und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="994a9-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="994a9-179">Fehlercodes verstehen</span><span class="sxs-lookup"><span data-stu-id="994a9-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="994a9-180">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="994a9-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="994a9-181">Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="994a9-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="994a9-182">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="994a9-182">Incidents overview</span></span>](incidents-overview.md)

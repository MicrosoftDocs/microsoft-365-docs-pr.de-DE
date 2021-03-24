---
title: Update incidents API
description: Informationen zum Aktualisieren von Vorfällen mithilfe der Microsoft 365 Defender-API
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
ms.openlocfilehash: 549f9bf2b9dc2ea5d1c734a809ad10a168c8123e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060803"
---
# <a name="update-incidents-api"></a><span data-ttu-id="5d899-104">Update incidents API</span><span class="sxs-lookup"><span data-stu-id="5d899-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5d899-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5d899-105">**Applies to:**</span></span>

- <span data-ttu-id="5d899-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d899-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d899-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="5d899-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5d899-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="5d899-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="5d899-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d899-109">API description</span></span>

<span data-ttu-id="5d899-110">Aktualisiert die Eigenschaften vorhandener Vorfälle.</span><span class="sxs-lookup"><span data-stu-id="5d899-110">Updates properties of existing incident.</span></span> <span data-ttu-id="5d899-111">Updatable Eigenschaften sind: ```status``` , , , , und ```determination``` ```classification``` ```assignedTo``` ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="5d899-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="5d899-112">Kontingente, Ressourcenzuordnung und andere Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5d899-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="5d899-113">Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde machen, bevor Sie den Drosselungsschwellenwert erreichen.</span><span class="sxs-lookup"><span data-stu-id="5d899-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="5d899-114">Sie können die Eigenschaft `determination` nur festlegen, `classification` wenn truePositive festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5d899-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="5d899-115">Wenn Ihre Anforderung gedrosselt wird, gibt sie einen `429` Antwortcode zurück.</span><span class="sxs-lookup"><span data-stu-id="5d899-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="5d899-116">Der Antworttext gibt den Zeitpunkt an, zu dem Sie mit dem Starten neuer Anrufe beginnen können.</span><span class="sxs-lookup"><span data-stu-id="5d899-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="5d899-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5d899-117">Permissions</span></span>

<span data-ttu-id="5d899-118">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5d899-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5d899-119">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender APIs](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="5d899-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="5d899-120">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="5d899-120">Permission type</span></span> | <span data-ttu-id="5d899-121">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="5d899-121">Permission</span></span> | <span data-ttu-id="5d899-122">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="5d899-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="5d899-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="5d899-123">Application</span></span> | <span data-ttu-id="5d899-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="5d899-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="5d899-125">Lesen und Schreiben aller Vorfälle</span><span class="sxs-lookup"><span data-stu-id="5d899-125">Read and write all incidents</span></span>
<span data-ttu-id="5d899-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="5d899-126">Delegated (work or school account)</span></span> | <span data-ttu-id="5d899-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5d899-127">Incident.ReadWrite</span></span> | <span data-ttu-id="5d899-128">Lese- und Schreibvorfälle</span><span class="sxs-lookup"><span data-stu-id="5d899-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="5d899-129">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen benötigt der Benutzer die Berechtigung, den Vorfall im Portal zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5d899-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="5d899-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="5d899-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="5d899-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="5d899-131">Request headers</span></span>

<span data-ttu-id="5d899-132">Name</span><span class="sxs-lookup"><span data-stu-id="5d899-132">Name</span></span> | <span data-ttu-id="5d899-133">Typ</span><span class="sxs-lookup"><span data-stu-id="5d899-133">Type</span></span> | <span data-ttu-id="5d899-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d899-134">Description</span></span>
-|-|-
<span data-ttu-id="5d899-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="5d899-135">Authorization</span></span> | <span data-ttu-id="5d899-136">String</span><span class="sxs-lookup"><span data-stu-id="5d899-136">String</span></span> | <span data-ttu-id="5d899-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5d899-137">Bearer {token}.</span></span> <span data-ttu-id="5d899-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="5d899-138">**Required**.</span></span>
<span data-ttu-id="5d899-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="5d899-139">Content-Type</span></span> | <span data-ttu-id="5d899-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5d899-140">String</span></span> | <span data-ttu-id="5d899-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="5d899-141">application/json.</span></span> <span data-ttu-id="5d899-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="5d899-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="5d899-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="5d899-143">Request body</span></span>

<span data-ttu-id="5d899-144">Stellen Sie im Anforderungstext die Werte für die Felder zur Verfügung, die aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5d899-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="5d899-145">Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre Werte bei, es sei denn, sie müssen aufgrund von Änderungen an verwandten Werten neu berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="5d899-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="5d899-146">Um eine optimale Leistung zu erzielen, sollten Sie vorhandene Werte auslassen, die sich nicht geändert haben.</span><span class="sxs-lookup"><span data-stu-id="5d899-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="5d899-147">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5d899-147">Property</span></span> | <span data-ttu-id="5d899-148">Typ</span><span class="sxs-lookup"><span data-stu-id="5d899-148">Type</span></span> | <span data-ttu-id="5d899-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d899-149">Description</span></span>
-|-|-
<span data-ttu-id="5d899-150">status</span><span class="sxs-lookup"><span data-stu-id="5d899-150">status</span></span> | <span data-ttu-id="5d899-151">Enum</span><span class="sxs-lookup"><span data-stu-id="5d899-151">Enum</span></span> | <span data-ttu-id="5d899-152">Gibt den aktuellen Status der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="5d899-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="5d899-153">Mögliche Werte sind: ```Active``` ```Resolved``` , , und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="5d899-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="5d899-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="5d899-154">assignedTo</span></span> | <span data-ttu-id="5d899-155">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5d899-155">string</span></span> | <span data-ttu-id="5d899-156">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="5d899-156">Owner of the incident.</span></span>
<span data-ttu-id="5d899-157">classification</span><span class="sxs-lookup"><span data-stu-id="5d899-157">classification</span></span> | <span data-ttu-id="5d899-158">Enum</span><span class="sxs-lookup"><span data-stu-id="5d899-158">Enum</span></span> | <span data-ttu-id="5d899-159">Spezifikation der Warnung.</span><span class="sxs-lookup"><span data-stu-id="5d899-159">Specification of the alert.</span></span> <span data-ttu-id="5d899-160">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="5d899-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="5d899-161">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="5d899-161">determination</span></span> | <span data-ttu-id="5d899-162">Enum</span><span class="sxs-lookup"><span data-stu-id="5d899-162">Enum</span></span> | <span data-ttu-id="5d899-163">Gibt die Bestimmung der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="5d899-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="5d899-164">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="5d899-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="5d899-165">tags</span><span class="sxs-lookup"><span data-stu-id="5d899-165">tags</span></span> | <span data-ttu-id="5d899-166">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="5d899-166">string List</span></span> | <span data-ttu-id="5d899-167">Liste der Incident-Tags.</span><span class="sxs-lookup"><span data-stu-id="5d899-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="5d899-168">Antwort</span><span class="sxs-lookup"><span data-stu-id="5d899-168">Response</span></span>

<span data-ttu-id="5d899-169">Wenn die Methode erfolgreich ist, gibt sie `200 OK` zurück.</span><span class="sxs-lookup"><span data-stu-id="5d899-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="5d899-170">Der Antworttext enthält die Vorfallentität mit aktualisierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="5d899-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="5d899-171">Wenn ein Vorfall mit der angegebenen ID nicht gefunden wurde, gibt die Methode `404 Not Found` zurück.</span><span class="sxs-lookup"><span data-stu-id="5d899-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="5d899-172">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d899-172">Example</span></span>

<span data-ttu-id="5d899-173">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="5d899-173">**Request**</span></span>

<span data-ttu-id="5d899-174">Hier sehen Sie ein Beispiel für die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="5d899-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="5d899-175">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="5d899-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="5d899-176">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="5d899-176">Related articles</span></span>

- [<span data-ttu-id="5d899-177">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="5d899-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="5d899-178">Informationen zu API-Beschränkungen und -Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="5d899-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="5d899-179">Verstehen von Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="5d899-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="5d899-180">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="5d899-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="5d899-181">Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="5d899-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="5d899-182">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="5d899-182">Incidents overview</span></span>](incidents-overview.md)

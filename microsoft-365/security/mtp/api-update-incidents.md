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
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719404"
---
# <a name="update-incidents-api"></a><span data-ttu-id="0a063-104">Update Incidents-API</span><span class="sxs-lookup"><span data-stu-id="0a063-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0a063-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0a063-105">**Applies to:**</span></span>

- <span data-ttu-id="0a063-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a063-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a063-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="0a063-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0a063-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="0a063-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="0a063-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a063-109">API description</span></span>

<span data-ttu-id="0a063-110">Aktualisiert die Eigenschaften des vorhandenen Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="0a063-110">Updates properties of existing incident.</span></span> <span data-ttu-id="0a063-111">Aktualisierbare Eigenschaften sind: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` , und ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="0a063-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="0a063-112">Kontingente, Ressourcenzuweisungen und andere Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="0a063-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="0a063-113">Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde vornehmen, bevor Sie den Schwellenwert für die Drosselung erreichen.</span><span class="sxs-lookup"><span data-stu-id="0a063-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="0a063-114">Sie können die `determination` -Eigenschaft nur festlegen `classification` , wenn auf TruePositive festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0a063-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="0a063-115">Wenn Ihre Anforderung gedrosselt wird, gibt Sie einen `429` Antwortcode zurück.</span><span class="sxs-lookup"><span data-stu-id="0a063-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="0a063-116">Der Antworttext gibt die Zeit an, zu der Sie mit der Erstellung neuer Anrufe beginnen können.</span><span class="sxs-lookup"><span data-stu-id="0a063-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="0a063-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0a063-117">Permissions</span></span>

<span data-ttu-id="0a063-118">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0a063-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0a063-119">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender APIs](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="0a063-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="0a063-120">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="0a063-120">Permission type</span></span> | <span data-ttu-id="0a063-121">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0a063-121">Permission</span></span> | <span data-ttu-id="0a063-122">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0a063-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="0a063-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="0a063-123">Application</span></span> | <span data-ttu-id="0a063-124">Incident. ReadWrite. all</span><span class="sxs-lookup"><span data-stu-id="0a063-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="0a063-125">Lesen und Schreiben aller Vorfälle</span><span class="sxs-lookup"><span data-stu-id="0a063-125">Read and write all incidents</span></span>
<span data-ttu-id="0a063-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="0a063-126">Delegated (work or school account)</span></span> | <span data-ttu-id="0a063-127">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0a063-127">Incident.ReadWrite</span></span> | <span data-ttu-id="0a063-128">Lese-und Schreib Vorfälle</span><span class="sxs-lookup"><span data-stu-id="0a063-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="0a063-129">Wenn ein Token mithilfe von Benutzeranmeldeinformationen abgerufen wird, muss der Benutzer über die Berechtigung verfügen, den Vorfall im Portal zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="0a063-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="0a063-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="0a063-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="0a063-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="0a063-131">Request headers</span></span>

<span data-ttu-id="0a063-132">Name</span><span class="sxs-lookup"><span data-stu-id="0a063-132">Name</span></span> | <span data-ttu-id="0a063-133">Typ</span><span class="sxs-lookup"><span data-stu-id="0a063-133">Type</span></span> | <span data-ttu-id="0a063-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a063-134">Description</span></span>
-|-|-
<span data-ttu-id="0a063-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="0a063-135">Authorization</span></span> | <span data-ttu-id="0a063-136">String</span><span class="sxs-lookup"><span data-stu-id="0a063-136">String</span></span> | <span data-ttu-id="0a063-137">Bearer {Token}.</span><span class="sxs-lookup"><span data-stu-id="0a063-137">Bearer {token}.</span></span> <span data-ttu-id="0a063-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0a063-138">**Required**.</span></span>
<span data-ttu-id="0a063-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="0a063-139">Content-Type</span></span> | <span data-ttu-id="0a063-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0a063-140">String</span></span> | <span data-ttu-id="0a063-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="0a063-141">application/json.</span></span> <span data-ttu-id="0a063-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0a063-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="0a063-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="0a063-143">Request body</span></span>

<span data-ttu-id="0a063-144">Geben Sie im Anforderungstext die Werte für die Felder an, die aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0a063-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="0a063-145">Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre Werte bei, es sei denn, Sie müssen aufgrund von Änderungen an verwandten Werten neu berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="0a063-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="0a063-146">Um eine optimale Leistung zu erzielen, sollten Sie vorhandene Werte weglassen, die sich nicht geändert haben.</span><span class="sxs-lookup"><span data-stu-id="0a063-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="0a063-147">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0a063-147">Property</span></span> | <span data-ttu-id="0a063-148">Typ</span><span class="sxs-lookup"><span data-stu-id="0a063-148">Type</span></span> | <span data-ttu-id="0a063-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a063-149">Description</span></span>
-|-|-
<span data-ttu-id="0a063-150">status</span><span class="sxs-lookup"><span data-stu-id="0a063-150">status</span></span> | <span data-ttu-id="0a063-151">Enum</span><span class="sxs-lookup"><span data-stu-id="0a063-151">Enum</span></span> | <span data-ttu-id="0a063-152">Gibt den aktuellen Status der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="0a063-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="0a063-153">Mögliche Werte sind: ```Active``` , ```Resolved``` und ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="0a063-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="0a063-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="0a063-154">assignedTo</span></span> | <span data-ttu-id="0a063-155">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0a063-155">string</span></span> | <span data-ttu-id="0a063-156">Besitzer des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="0a063-156">Owner of the incident.</span></span>
<span data-ttu-id="0a063-157">classification</span><span class="sxs-lookup"><span data-stu-id="0a063-157">classification</span></span> | <span data-ttu-id="0a063-158">Enum</span><span class="sxs-lookup"><span data-stu-id="0a063-158">Enum</span></span> | <span data-ttu-id="0a063-159">Spezifikation der Warnung.</span><span class="sxs-lookup"><span data-stu-id="0a063-159">Specification of the alert.</span></span> <span data-ttu-id="0a063-160">Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="0a063-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="0a063-161">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="0a063-161">determination</span></span> | <span data-ttu-id="0a063-162">Enum</span><span class="sxs-lookup"><span data-stu-id="0a063-162">Enum</span></span> | <span data-ttu-id="0a063-163">Gibt die Bestimmung der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="0a063-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="0a063-164">Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="0a063-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="0a063-165">tags</span><span class="sxs-lookup"><span data-stu-id="0a063-165">tags</span></span> | <span data-ttu-id="0a063-166">Zeichenfolgenliste</span><span class="sxs-lookup"><span data-stu-id="0a063-166">string List</span></span> | <span data-ttu-id="0a063-167">Liste der Vorfall Tags.</span><span class="sxs-lookup"><span data-stu-id="0a063-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="0a063-168">Antwort</span><span class="sxs-lookup"><span data-stu-id="0a063-168">Response</span></span>

<span data-ttu-id="0a063-169">Wenn die Methode erfolgreich verläuft, wird diese zurückgegeben `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="0a063-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="0a063-170">Der Antworttext enthält die Vorfall Entität mit aktualisierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0a063-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="0a063-171">Wenn ein Vorfall mit der angegebenen ID nicht gefunden wurde, gibt die Methode zurück `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="0a063-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="0a063-172">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a063-172">Example</span></span>

<span data-ttu-id="0a063-173">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="0a063-173">**Request**</span></span>

<span data-ttu-id="0a063-174">Hier ist ein Beispiel für die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="0a063-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="0a063-175">**Response**</span><span class="sxs-lookup"><span data-stu-id="0a063-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="0a063-176">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="0a063-176">Related articles</span></span>

- [<span data-ttu-id="0a063-177">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="0a063-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="0a063-178">Informationen zu API-Grenzwerten und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="0a063-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="0a063-179">Grundlegendes zu Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="0a063-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="0a063-180">Vorfall-APIs</span><span class="sxs-lookup"><span data-stu-id="0a063-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="0a063-181">Auflisten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="0a063-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="0a063-182">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="0a063-182">Incidents overview</span></span>](incidents-overview.md)

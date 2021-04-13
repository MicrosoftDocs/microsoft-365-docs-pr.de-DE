---
title: Aktualisieren der Benachrichtigungsentitäts-API
description: Erfahren Sie, wie Sie eine Microsoft Defender for Endpoint-Warnung mithilfe dieser API aktualisieren. Sie können die Eigenschaften status, determination, classification und assignedTo aktualisieren.
keywords: apis, graph api, supported apis, get, alert, information, id
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 94be185bd30cd36f456a66d5ae30a4361abc0c48
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688249"
---
# <a name="update-alert"></a><span data-ttu-id="82c7d-105">Warnung aktualisieren</span><span class="sxs-lookup"><span data-stu-id="82c7d-105">Update alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="82c7d-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="82c7d-106">**Applies to:**</span></span>
- [<span data-ttu-id="82c7d-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="82c7d-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="82c7d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82c7d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="82c7d-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="82c7d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="82c7d-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="82c7d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="82c7d-111">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82c7d-111">API description</span></span>
<span data-ttu-id="82c7d-112">Aktualisiert die Eigenschaften der vorhandenen [Warnung](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="82c7d-112">Updates properties of existing [Alert](alerts.md).</span></span>
<br><span data-ttu-id="82c7d-113">Die Übermittlung **von Kommentaren** ist mit oder ohne Aktualisierung von Eigenschaften verfügbar.</span><span class="sxs-lookup"><span data-stu-id="82c7d-113">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="82c7d-114">Die updatablen Eigenschaften sind: ```status``` ```determination``` , und ```classification``` ```assignedTo``` .</span><span class="sxs-lookup"><span data-stu-id="82c7d-114">Updatable properties are: ```status```, ```determination```, ```classification``` and ```assignedTo```.</span></span>


## <a name="limitations"></a><span data-ttu-id="82c7d-115">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="82c7d-115">Limitations</span></span>
1. <span data-ttu-id="82c7d-116">Sie können Warnungen aktualisieren, die in der API verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="82c7d-116">You can update alerts that available in the API.</span></span> <span data-ttu-id="82c7d-117">Weitere Informationen finden Sie unter [Warnungen](get-alerts.md) auflisten.</span><span class="sxs-lookup"><span data-stu-id="82c7d-117">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="82c7d-118">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="82c7d-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="82c7d-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="82c7d-119">Permissions</span></span>
<span data-ttu-id="82c7d-120">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="82c7d-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="82c7d-121">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="82c7d-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="82c7d-122">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="82c7d-122">Permission type</span></span> |   <span data-ttu-id="82c7d-123">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="82c7d-123">Permission</span></span>  |   <span data-ttu-id="82c7d-124">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="82c7d-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="82c7d-125">Anwendung</span><span class="sxs-lookup"><span data-stu-id="82c7d-125">Application</span></span> |   <span data-ttu-id="82c7d-126">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="82c7d-126">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="82c7d-127">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="82c7d-127">'Read and write all alerts'</span></span>
<span data-ttu-id="82c7d-128">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="82c7d-128">Delegated (work or school account)</span></span> | <span data-ttu-id="82c7d-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="82c7d-129">Alert.ReadWrite</span></span> | <span data-ttu-id="82c7d-130">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="82c7d-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="82c7d-131">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="82c7d-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="82c7d-132">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Warnungsuntersuchung" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="82c7d-132">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="82c7d-133">Der Benutzer muss auf das Gerät zugreifen können, das der Warnung zugeordnet ist, basierend auf den Gerätegruppeneinstellungen (Weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen)</span><span class="sxs-lookup"><span data-stu-id="82c7d-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="82c7d-134">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="82c7d-134">HTTP request</span></span>
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="82c7d-135">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="82c7d-135">Request headers</span></span>

<span data-ttu-id="82c7d-136">Name</span><span class="sxs-lookup"><span data-stu-id="82c7d-136">Name</span></span> | <span data-ttu-id="82c7d-137">Typ</span><span class="sxs-lookup"><span data-stu-id="82c7d-137">Type</span></span> | <span data-ttu-id="82c7d-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82c7d-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="82c7d-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="82c7d-139">Authorization</span></span> | <span data-ttu-id="82c7d-140">String</span><span class="sxs-lookup"><span data-stu-id="82c7d-140">String</span></span> | <span data-ttu-id="82c7d-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="82c7d-141">Bearer {token}.</span></span> <span data-ttu-id="82c7d-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="82c7d-142">**Required**.</span></span>
<span data-ttu-id="82c7d-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="82c7d-143">Content-Type</span></span> | <span data-ttu-id="82c7d-144">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="82c7d-144">String</span></span> | <span data-ttu-id="82c7d-145">application/json.</span><span class="sxs-lookup"><span data-stu-id="82c7d-145">application/json.</span></span> <span data-ttu-id="82c7d-146">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="82c7d-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="82c7d-147">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="82c7d-147">Request body</span></span>
<span data-ttu-id="82c7d-148">Stellen Sie im Anforderungstext die Werte für die relevanten Felder zur Verfügung, die aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="82c7d-148">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="82c7d-149">Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre vorherigen Werte oder werden basierend auf Änderungen an anderen Eigenschaftswerten neu berechnet.</span><span class="sxs-lookup"><span data-stu-id="82c7d-149">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="82c7d-150">Um eine optimale Leistung zu erzielen, sollten Sie keine vorhandenen Werte enthalten, die sich nicht geändert haben.</span><span class="sxs-lookup"><span data-stu-id="82c7d-150">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="82c7d-151">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="82c7d-151">Property</span></span> | <span data-ttu-id="82c7d-152">Typ</span><span class="sxs-lookup"><span data-stu-id="82c7d-152">Type</span></span> | <span data-ttu-id="82c7d-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82c7d-153">Description</span></span>
:---|:---|:---
<span data-ttu-id="82c7d-154">status</span><span class="sxs-lookup"><span data-stu-id="82c7d-154">status</span></span> | <span data-ttu-id="82c7d-155">String</span><span class="sxs-lookup"><span data-stu-id="82c7d-155">String</span></span> | <span data-ttu-id="82c7d-156">Gibt den aktuellen Status der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="82c7d-156">Specifies the current status of the alert.</span></span> <span data-ttu-id="82c7d-157">Die Eigenschaftswerte sind: 'New', 'InProgress' und 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="82c7d-157">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="82c7d-158">assignedTo</span><span class="sxs-lookup"><span data-stu-id="82c7d-158">assignedTo</span></span> | <span data-ttu-id="82c7d-159">String</span><span class="sxs-lookup"><span data-stu-id="82c7d-159">String</span></span> | <span data-ttu-id="82c7d-160">Besitzer der Warnung</span><span class="sxs-lookup"><span data-stu-id="82c7d-160">Owner of the alert</span></span>
<span data-ttu-id="82c7d-161">classification</span><span class="sxs-lookup"><span data-stu-id="82c7d-161">classification</span></span> | <span data-ttu-id="82c7d-162">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="82c7d-162">String</span></span> | <span data-ttu-id="82c7d-163">Gibt die Spezifikation der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="82c7d-163">Specifies the specification of the alert.</span></span> <span data-ttu-id="82c7d-164">Die Eigenschaftswerte sind: "Unbekannt", "FalsePositive", "TruePositive".</span><span class="sxs-lookup"><span data-stu-id="82c7d-164">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="82c7d-165">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="82c7d-165">determination</span></span> | <span data-ttu-id="82c7d-166">String</span><span class="sxs-lookup"><span data-stu-id="82c7d-166">String</span></span> | <span data-ttu-id="82c7d-167">Gibt die Bestimmung der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="82c7d-167">Specifies the determination of the alert.</span></span> <span data-ttu-id="82c7d-168">Die Eigenschaftswerte sind: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other"</span><span class="sxs-lookup"><span data-stu-id="82c7d-168">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="82c7d-169">comment</span><span class="sxs-lookup"><span data-stu-id="82c7d-169">comment</span></span> | <span data-ttu-id="82c7d-170">String</span><span class="sxs-lookup"><span data-stu-id="82c7d-170">String</span></span> | <span data-ttu-id="82c7d-171">Kommentar, der der Warnung hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="82c7d-171">Comment to be added to the alert.</span></span>

## <a name="response"></a><span data-ttu-id="82c7d-172">Antwort</span><span class="sxs-lookup"><span data-stu-id="82c7d-172">Response</span></span>
<span data-ttu-id="82c7d-173">Wenn die Methode erfolgreich ist, werden 200 OK und die Warnungsentität im Antworttext mit den aktualisierten Eigenschaften zurückgegeben. [](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="82c7d-173">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="82c7d-174">Wenn eine Warnung mit der angegebenen ID nicht gefunden wurde - 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="82c7d-174">If alert with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="82c7d-175">Beispiel</span><span class="sxs-lookup"><span data-stu-id="82c7d-175">Example</span></span>

<span data-ttu-id="82c7d-176">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="82c7d-176">**Request**</span></span>

<span data-ttu-id="82c7d-177">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="82c7d-177">Here is an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```

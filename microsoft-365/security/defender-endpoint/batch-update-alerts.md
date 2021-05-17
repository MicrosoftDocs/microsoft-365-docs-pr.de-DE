---
title: Batch Update alert entities API
description: Erfahren Sie, wie Sie Microsoft Defender for Endpoint-Warnungen in einem Batch mithilfe dieser API aktualisieren. Sie können die Eigenschaften status, determination, classification und assignedTo aktualisieren.
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
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166681"
---
# <a name="batch-update-alerts"></a><span data-ttu-id="6a751-105">Batchupdatewarnungen</span><span class="sxs-lookup"><span data-stu-id="6a751-105">Batch update alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6a751-106">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6a751-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="6a751-107">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="6a751-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6a751-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="6a751-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="6a751-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a751-109">API description</span></span>
<span data-ttu-id="6a751-110">Aktualisiert die Eigenschaften eines Batches vorhandener [Alerts .](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="6a751-110">Updates properties of a batch of existing [Alerts](alerts.md).</span></span>
<br><span data-ttu-id="6a751-111">Die Übermittlung **von Kommentaren** ist mit oder ohne Aktualisierung von Eigenschaften verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6a751-111">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="6a751-112">Die updatablen Eigenschaften sind: `status` `determination` , und `classification` `assignedTo` .</span><span class="sxs-lookup"><span data-stu-id="6a751-112">Updatable properties are: `status`, `determination`, `classification` and `assignedTo`.</span></span>


## <a name="limitations"></a><span data-ttu-id="6a751-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6a751-113">Limitations</span></span>
1. <span data-ttu-id="6a751-114">Sie können Warnungen aktualisieren, die in der API verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6a751-114">You can update alerts that are available in the API.</span></span> <span data-ttu-id="6a751-115">Weitere Informationen finden Sie unter [Warnungen](get-alerts.md) auflisten.</span><span class="sxs-lookup"><span data-stu-id="6a751-115">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="6a751-116">Die Tarifeinschränkungen für diese API sind 10 Anrufe pro Minute und 500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="6a751-116">Rate limitations for this API are 10 calls per minute and 500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="6a751-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6a751-117">Permissions</span></span>
<span data-ttu-id="6a751-118">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6a751-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6a751-119">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6a751-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="6a751-120">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="6a751-120">Permission type</span></span> |   <span data-ttu-id="6a751-121">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="6a751-121">Permission</span></span>  |   <span data-ttu-id="6a751-122">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="6a751-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6a751-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="6a751-123">Application</span></span> |   <span data-ttu-id="6a751-124">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="6a751-124">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="6a751-125">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="6a751-125">'Read and write all alerts'</span></span>
<span data-ttu-id="6a751-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="6a751-126">Delegated (work or school account)</span></span> | <span data-ttu-id="6a751-127">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6a751-127">Alert.ReadWrite</span></span> | <span data-ttu-id="6a751-128">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="6a751-128">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="6a751-129">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="6a751-129">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="6a751-130">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Warnungsuntersuchung" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="6a751-130">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="6a751-131">Der Benutzer muss auf das Gerät zugreifen können, das der Warnung zugeordnet ist, basierend auf den Gerätegruppeneinstellungen (Weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen)</span><span class="sxs-lookup"><span data-stu-id="6a751-131">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="6a751-132">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="6a751-132">HTTP request</span></span>
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a><span data-ttu-id="6a751-133">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="6a751-133">Request headers</span></span>

<span data-ttu-id="6a751-134">Name</span><span class="sxs-lookup"><span data-stu-id="6a751-134">Name</span></span> | <span data-ttu-id="6a751-135">Typ</span><span class="sxs-lookup"><span data-stu-id="6a751-135">Type</span></span> | <span data-ttu-id="6a751-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a751-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="6a751-137">Authorization</span><span class="sxs-lookup"><span data-stu-id="6a751-137">Authorization</span></span> | <span data-ttu-id="6a751-138">String</span><span class="sxs-lookup"><span data-stu-id="6a751-138">String</span></span> | <span data-ttu-id="6a751-139">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6a751-139">Bearer {token}.</span></span> <span data-ttu-id="6a751-140">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="6a751-140">**Required**.</span></span>
<span data-ttu-id="6a751-141">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6a751-141">Content-Type</span></span> | <span data-ttu-id="6a751-142">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6a751-142">String</span></span> | <span data-ttu-id="6a751-143">application/json.</span><span class="sxs-lookup"><span data-stu-id="6a751-143">application/json.</span></span> <span data-ttu-id="6a751-144">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="6a751-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6a751-145">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="6a751-145">Request body</span></span>
<span data-ttu-id="6a751-146">Stellen Sie im Anforderungstext die IDs der zu aktualisierenden Warnungen und die Werte der relevanten Felder zur Verfügung, die Sie für diese Warnungen aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6a751-146">In the request body, supply the IDs of the alerts to be updated and the values of the relevant fields that you wish to update for these alerts.</span></span>
<br><span data-ttu-id="6a751-147">Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre vorherigen Werte oder werden basierend auf Änderungen an anderen Eigenschaftswerten neu berechnet.</span><span class="sxs-lookup"><span data-stu-id="6a751-147">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="6a751-148">Aus Gründen der Leistung sollten Sie vorhandene Werte, die nicht geändert wurden, nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="6a751-148">For best performance you shouldn't include existing values that haven't changed.</span></span>

<span data-ttu-id="6a751-149">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6a751-149">Property</span></span> | <span data-ttu-id="6a751-150">Typ</span><span class="sxs-lookup"><span data-stu-id="6a751-150">Type</span></span> | <span data-ttu-id="6a751-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a751-151">Description</span></span>
:---|:---|:---
<span data-ttu-id="6a751-152">alertIds</span><span class="sxs-lookup"><span data-stu-id="6a751-152">alertIds</span></span> | <span data-ttu-id="6a751-153">&lt;Listenzeichenfolge&gt;</span><span class="sxs-lookup"><span data-stu-id="6a751-153">List&lt;String&gt;</span></span>| <span data-ttu-id="6a751-154">Eine Liste der IDs der zu aktualisierenden Warnungen.</span><span class="sxs-lookup"><span data-stu-id="6a751-154">A list of the IDs of the alerts to be updated.</span></span> <span data-ttu-id="6a751-155">**Required**</span><span class="sxs-lookup"><span data-stu-id="6a751-155">**Required**</span></span>
<span data-ttu-id="6a751-156">status</span><span class="sxs-lookup"><span data-stu-id="6a751-156">status</span></span> | <span data-ttu-id="6a751-157">String</span><span class="sxs-lookup"><span data-stu-id="6a751-157">String</span></span> | <span data-ttu-id="6a751-158">Gibt den aktualisierten Status der angegebenen Warnungen an.</span><span class="sxs-lookup"><span data-stu-id="6a751-158">Specifies the updated status of the specified alerts.</span></span> <span data-ttu-id="6a751-159">Die Eigenschaftswerte sind: 'New', 'InProgress' und 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="6a751-159">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="6a751-160">assignedTo</span><span class="sxs-lookup"><span data-stu-id="6a751-160">assignedTo</span></span> | <span data-ttu-id="6a751-161">String</span><span class="sxs-lookup"><span data-stu-id="6a751-161">String</span></span> | <span data-ttu-id="6a751-162">Besitzer der angegebenen Warnungen</span><span class="sxs-lookup"><span data-stu-id="6a751-162">Owner of the specified alerts</span></span>
<span data-ttu-id="6a751-163">classification</span><span class="sxs-lookup"><span data-stu-id="6a751-163">classification</span></span> | <span data-ttu-id="6a751-164">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6a751-164">String</span></span> | <span data-ttu-id="6a751-165">Gibt die Spezifikation der angegebenen Warnungen an.</span><span class="sxs-lookup"><span data-stu-id="6a751-165">Specifies the specification of the specified alerts.</span></span> <span data-ttu-id="6a751-166">Die Eigenschaftswerte sind: "Unbekannt", "FalsePositive", "TruePositive".</span><span class="sxs-lookup"><span data-stu-id="6a751-166">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="6a751-167">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="6a751-167">determination</span></span> | <span data-ttu-id="6a751-168">String</span><span class="sxs-lookup"><span data-stu-id="6a751-168">String</span></span> | <span data-ttu-id="6a751-169">Gibt die Bestimmung der angegebenen Warnungen an.</span><span class="sxs-lookup"><span data-stu-id="6a751-169">Specifies the determination of the specified alerts.</span></span> <span data-ttu-id="6a751-170">Die Eigenschaftswerte sind: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other"</span><span class="sxs-lookup"><span data-stu-id="6a751-170">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="6a751-171">comment</span><span class="sxs-lookup"><span data-stu-id="6a751-171">comment</span></span> | <span data-ttu-id="6a751-172">String</span><span class="sxs-lookup"><span data-stu-id="6a751-172">String</span></span> | <span data-ttu-id="6a751-173">Kommentar, der den angegebenen Warnungen hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6a751-173">Comment to be added to the specified alerts.</span></span>

## <a name="response"></a><span data-ttu-id="6a751-174">Antwort</span><span class="sxs-lookup"><span data-stu-id="6a751-174">Response</span></span>
<span data-ttu-id="6a751-175">Wenn die Methode erfolgreich ist, gibt sie 200 OK mit einem leeren Antworttext zurück.</span><span class="sxs-lookup"><span data-stu-id="6a751-175">If successful, this method returns 200 OK, with an empty response body.</span></span>


## <a name="example"></a><span data-ttu-id="6a751-176">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6a751-176">Example</span></span>

<span data-ttu-id="6a751-177">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="6a751-177">**Request**</span></span>

<span data-ttu-id="6a751-178">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="6a751-178">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```

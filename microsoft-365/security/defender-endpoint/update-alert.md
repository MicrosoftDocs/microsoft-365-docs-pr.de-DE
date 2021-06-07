---
title: Aktualisieren der Warnungsentitäts-API
description: Erfahren Sie, wie Sie eine Microsoft Defender für Endpunkt-Warnung mithilfe dieser API aktualisieren. Sie können die Eigenschaften Status, Bestimmung, Klassifizierung und assignedTo aktualisieren.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnung, Informationen, ID
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 043d423e1016d77cad4a175aa41718329f464252
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768925"
---
# <a name="update-alert"></a><span data-ttu-id="bad5b-105">Warnung aktualisieren</span><span class="sxs-lookup"><span data-stu-id="bad5b-105">Update alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bad5b-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bad5b-106">**Applies to:**</span></span>
- [<span data-ttu-id="bad5b-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bad5b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="bad5b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bad5b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bad5b-109">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="bad5b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bad5b-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bad5b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="bad5b-111">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bad5b-111">API description</span></span>
<span data-ttu-id="bad5b-112">Aktualisiert die Eigenschaften vorhandener [Warnungen.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="bad5b-112">Updates properties of existing [Alert](alerts.md).</span></span>
<br><span data-ttu-id="bad5b-113">Die Übermittlung eines **Kommentars** ist mit oder ohne Aktualisierung der Eigenschaften verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bad5b-113">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="bad5b-114">Aktualisierbare Eigenschaften sind: ```status``` , ```determination``` und ```classification``` ```assignedTo``` .</span><span class="sxs-lookup"><span data-stu-id="bad5b-114">Updatable properties are: ```status```, ```determination```, ```classification``` and ```assignedTo```.</span></span>


## <a name="limitations"></a><span data-ttu-id="bad5b-115">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="bad5b-115">Limitations</span></span>
1. <span data-ttu-id="bad5b-116">Sie können Warnungen aktualisieren, die in der API verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="bad5b-116">You can update alerts that available in the API.</span></span> <span data-ttu-id="bad5b-117">Weitere Informationen finden Sie unter ["Warnungen auflisten".](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="bad5b-117">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="bad5b-118">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="bad5b-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="bad5b-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bad5b-119">Permissions</span></span>
<span data-ttu-id="bad5b-120">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="bad5b-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bad5b-121">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bad5b-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="bad5b-122">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="bad5b-122">Permission type</span></span> |   <span data-ttu-id="bad5b-123">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="bad5b-123">Permission</span></span>  |   <span data-ttu-id="bad5b-124">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="bad5b-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bad5b-125">Anwendung</span><span class="sxs-lookup"><span data-stu-id="bad5b-125">Application</span></span> |   <span data-ttu-id="bad5b-126">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="bad5b-126">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="bad5b-127">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="bad5b-127">'Read and write all alerts'</span></span>
<span data-ttu-id="bad5b-128">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="bad5b-128">Delegated (work or school account)</span></span> | <span data-ttu-id="bad5b-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="bad5b-129">Alert.ReadWrite</span></span> | <span data-ttu-id="bad5b-130">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="bad5b-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="bad5b-131">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="bad5b-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="bad5b-132">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Warnungsuntersuchung" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="bad5b-132">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="bad5b-133">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben, das der Warnung zugeordnet ist (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="bad5b-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="bad5b-134">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="bad5b-134">HTTP request</span></span>
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="bad5b-135">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="bad5b-135">Request headers</span></span>

<span data-ttu-id="bad5b-136">Name</span><span class="sxs-lookup"><span data-stu-id="bad5b-136">Name</span></span> | <span data-ttu-id="bad5b-137">Typ</span><span class="sxs-lookup"><span data-stu-id="bad5b-137">Type</span></span> | <span data-ttu-id="bad5b-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bad5b-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="bad5b-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="bad5b-139">Authorization</span></span> | <span data-ttu-id="bad5b-140">String</span><span class="sxs-lookup"><span data-stu-id="bad5b-140">String</span></span> | <span data-ttu-id="bad5b-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="bad5b-141">Bearer {token}.</span></span> <span data-ttu-id="bad5b-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="bad5b-142">**Required**.</span></span>
<span data-ttu-id="bad5b-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="bad5b-143">Content-Type</span></span> | <span data-ttu-id="bad5b-144">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="bad5b-144">String</span></span> | <span data-ttu-id="bad5b-145">application/json.</span><span class="sxs-lookup"><span data-stu-id="bad5b-145">application/json.</span></span> <span data-ttu-id="bad5b-146">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="bad5b-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="bad5b-147">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="bad5b-147">Request body</span></span>
<span data-ttu-id="bad5b-148">Geben Sie im Anforderungstext die Werte für die relevanten Felder an, die aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bad5b-148">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="bad5b-149">Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre vorherigen Werte oder werden basierend auf Änderungen an anderen Eigenschaftswerten neu berechnet.</span><span class="sxs-lookup"><span data-stu-id="bad5b-149">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="bad5b-150">Um eine optimale Leistung zu erzielen, sollten Sie vorhandene Werte, die sich nicht geändert haben, nicht einschließen.</span><span class="sxs-lookup"><span data-stu-id="bad5b-150">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="bad5b-151">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bad5b-151">Property</span></span> | <span data-ttu-id="bad5b-152">Typ</span><span class="sxs-lookup"><span data-stu-id="bad5b-152">Type</span></span> | <span data-ttu-id="bad5b-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bad5b-153">Description</span></span>
:---|:---|:---
<span data-ttu-id="bad5b-154">status</span><span class="sxs-lookup"><span data-stu-id="bad5b-154">status</span></span> | <span data-ttu-id="bad5b-155">String</span><span class="sxs-lookup"><span data-stu-id="bad5b-155">String</span></span> | <span data-ttu-id="bad5b-156">Gibt den aktuellen Status der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="bad5b-156">Specifies the current status of the alert.</span></span> <span data-ttu-id="bad5b-157">Die Eigenschaftswerte sind: 'New', 'InProgress' und 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="bad5b-157">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="bad5b-158">assignedTo</span><span class="sxs-lookup"><span data-stu-id="bad5b-158">assignedTo</span></span> | <span data-ttu-id="bad5b-159">String</span><span class="sxs-lookup"><span data-stu-id="bad5b-159">String</span></span> | <span data-ttu-id="bad5b-160">Besitzer der Warnung</span><span class="sxs-lookup"><span data-stu-id="bad5b-160">Owner of the alert</span></span>
<span data-ttu-id="bad5b-161">classification</span><span class="sxs-lookup"><span data-stu-id="bad5b-161">classification</span></span> | <span data-ttu-id="bad5b-162">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="bad5b-162">String</span></span> | <span data-ttu-id="bad5b-163">Gibt die Spezifikation der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="bad5b-163">Specifies the specification of the alert.</span></span> <span data-ttu-id="bad5b-164">Die Eigenschaftswerte sind: 'Unknown', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="bad5b-164">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="bad5b-165">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="bad5b-165">determination</span></span> | <span data-ttu-id="bad5b-166">String</span><span class="sxs-lookup"><span data-stu-id="bad5b-166">String</span></span> | <span data-ttu-id="bad5b-167">Gibt die Bestimmung der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="bad5b-167">Specifies the determination of the alert.</span></span> <span data-ttu-id="bad5b-168">Die Eigenschaftswerte sind: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="bad5b-168">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="bad5b-169">comment</span><span class="sxs-lookup"><span data-stu-id="bad5b-169">comment</span></span> | <span data-ttu-id="bad5b-170">String</span><span class="sxs-lookup"><span data-stu-id="bad5b-170">String</span></span> | <span data-ttu-id="bad5b-171">Kommentar, der der Warnung hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bad5b-171">Comment to be added to the alert.</span></span>

## <a name="response"></a><span data-ttu-id="bad5b-172">Antwort</span><span class="sxs-lookup"><span data-stu-id="bad5b-172">Response</span></span>
<span data-ttu-id="bad5b-173">Wenn die Methode erfolgreich ist, werden 200 OK und die [Warnungsentität](alerts.md) im Antworttext mit den aktualisierten Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bad5b-173">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="bad5b-174">Wenn warnung mit der angegebenen ID nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="bad5b-174">If alert with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="bad5b-175">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bad5b-175">Example</span></span>

<span data-ttu-id="bad5b-176">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="bad5b-176">**Request**</span></span>

<span data-ttu-id="bad5b-177">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="bad5b-177">Here is an example of the request.</span></span>

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

---
title: Api für Batchaktualisierungs-Warnungsentitäten
description: Erfahren Sie, wie Sie Microsoft Defender für Endpunkt-Warnungen mithilfe dieser API in einem Batch aktualisieren. Sie können die Eigenschaften Status, Bestimmung, Klassifizierung und assignedTo aktualisieren.
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
ms.technology: mde
ms.openlocfilehash: 80f88b31c1e07d1f40f3f58a1bd21b4a5c58c60b
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290207"
---
# <a name="batch-update-alerts"></a><span data-ttu-id="97c33-105">Warnungen bei Batchaktualisierungen</span><span class="sxs-lookup"><span data-stu-id="97c33-105">Batch update alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="97c33-106">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="97c33-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="97c33-107">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="97c33-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="97c33-108">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="97c33-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="97c33-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97c33-109">API description</span></span>

<span data-ttu-id="97c33-110">Aktualisiert die Eigenschaften eines Batches vorhandener [Warnungen.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="97c33-110">Updates properties of a batch of existing [Alerts](alerts.md).</span></span>

<span data-ttu-id="97c33-111">Die Übermittlung eines **Kommentars** ist mit oder ohne Aktualisierung der Eigenschaften verfügbar.</span><span class="sxs-lookup"><span data-stu-id="97c33-111">Submission of **comment** is available with or without updating properties.</span></span>

<span data-ttu-id="97c33-112">Aktualisierbare Eigenschaften sind: `status` , `determination` und `classification` `assignedTo` .</span><span class="sxs-lookup"><span data-stu-id="97c33-112">Updatable properties are: `status`, `determination`, `classification` and `assignedTo`.</span></span>

## <a name="limitations"></a><span data-ttu-id="97c33-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="97c33-113">Limitations</span></span>

1. <span data-ttu-id="97c33-114">Sie können Warnungen aktualisieren, die in der API verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="97c33-114">You can update alerts that are available in the API.</span></span> <span data-ttu-id="97c33-115">Weitere Informationen finden Sie unter ["Warnungen auflisten".](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="97c33-115">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="97c33-116">Die Rateneinschränkungen für diese API sind 10 Anrufe pro Minute und 500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="97c33-116">Rate limitations for this API are 10 calls per minute and 500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="97c33-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="97c33-117">Permissions</span></span>

<span data-ttu-id="97c33-118">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="97c33-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="97c33-119">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="97c33-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="97c33-120">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="97c33-120">Permission type</span></span> | <span data-ttu-id="97c33-121">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="97c33-121">Permission</span></span> | <span data-ttu-id="97c33-122">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="97c33-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="97c33-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="97c33-123">Application</span></span> | <span data-ttu-id="97c33-124">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="97c33-124">Alerts.ReadWrite.All</span></span> | <span data-ttu-id="97c33-125">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="97c33-125">'Read and write all alerts'</span></span>
<span data-ttu-id="97c33-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="97c33-126">Delegated (work or school account)</span></span> | <span data-ttu-id="97c33-127">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="97c33-127">Alert.ReadWrite</span></span> | <span data-ttu-id="97c33-128">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="97c33-128">'Read and write alerts'</span></span>

> [!NOTE]
> <span data-ttu-id="97c33-129">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="97c33-129">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="97c33-130">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Warnungsuntersuchung" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="97c33-130">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="97c33-131">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben, das der Warnung zugeordnet ist (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="97c33-131">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="97c33-132">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="97c33-132">HTTP request</span></span>

```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a><span data-ttu-id="97c33-133">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="97c33-133">Request headers</span></span>

<span data-ttu-id="97c33-134">Name</span><span class="sxs-lookup"><span data-stu-id="97c33-134">Name</span></span> | <span data-ttu-id="97c33-135">Typ</span><span class="sxs-lookup"><span data-stu-id="97c33-135">Type</span></span> | <span data-ttu-id="97c33-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97c33-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="97c33-137">Authorization</span><span class="sxs-lookup"><span data-stu-id="97c33-137">Authorization</span></span> | <span data-ttu-id="97c33-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="97c33-138">String</span></span> | <span data-ttu-id="97c33-139">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="97c33-139">Bearer {token}.</span></span> <span data-ttu-id="97c33-140">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="97c33-140">**Required**.</span></span>
<span data-ttu-id="97c33-141">Content-Type</span><span class="sxs-lookup"><span data-stu-id="97c33-141">Content-Type</span></span> | <span data-ttu-id="97c33-142">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="97c33-142">String</span></span> | <span data-ttu-id="97c33-143">application/json.</span><span class="sxs-lookup"><span data-stu-id="97c33-143">application/json.</span></span> <span data-ttu-id="97c33-144">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="97c33-144">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="97c33-145">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="97c33-145">Request body</span></span>

<span data-ttu-id="97c33-146">Geben Sie im Anforderungstext die IDs der zu aktualisierenden Warnungen und die Werte der relevanten Felder an, die Sie für diese Warnungen aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="97c33-146">In the request body, supply the IDs of the alerts to be updated and the values of the relevant fields that you wish to update for these alerts.</span></span>

<span data-ttu-id="97c33-147">Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre vorherigen Werte oder werden basierend auf Änderungen an anderen Eigenschaftswerten neu berechnet.</span><span class="sxs-lookup"><span data-stu-id="97c33-147">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span>

<span data-ttu-id="97c33-148">Aus Gründen der Leistung sollten Sie vorhandene Werte, die nicht geändert wurden, nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="97c33-148">For best performance you shouldn't include existing values that haven't changed.</span></span>

<span data-ttu-id="97c33-149">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="97c33-149">Property</span></span> | <span data-ttu-id="97c33-150">Typ</span><span class="sxs-lookup"><span data-stu-id="97c33-150">Type</span></span> | <span data-ttu-id="97c33-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97c33-151">Description</span></span>
:---|:---|:---
<span data-ttu-id="97c33-152">alertIds</span><span class="sxs-lookup"><span data-stu-id="97c33-152">alertIds</span></span> | <span data-ttu-id="97c33-153">&lt;Listenzeichenfolge&gt;</span><span class="sxs-lookup"><span data-stu-id="97c33-153">List&lt;String&gt;</span></span>| <span data-ttu-id="97c33-154">Eine Liste der IDs der zu aktualisierenden Warnungen.</span><span class="sxs-lookup"><span data-stu-id="97c33-154">A list of the IDs of the alerts to be updated.</span></span> <span data-ttu-id="97c33-155">**Required**</span><span class="sxs-lookup"><span data-stu-id="97c33-155">**Required**</span></span>
<span data-ttu-id="97c33-156">status</span><span class="sxs-lookup"><span data-stu-id="97c33-156">status</span></span> | <span data-ttu-id="97c33-157">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="97c33-157">String</span></span> | <span data-ttu-id="97c33-158">Gibt den aktualisierten Status der angegebenen Warnungen an.</span><span class="sxs-lookup"><span data-stu-id="97c33-158">Specifies the updated status of the specified alerts.</span></span> <span data-ttu-id="97c33-159">Die Eigenschaftswerte sind: 'New', 'InProgress' und 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="97c33-159">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="97c33-160">assignedTo</span><span class="sxs-lookup"><span data-stu-id="97c33-160">assignedTo</span></span> | <span data-ttu-id="97c33-161">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="97c33-161">String</span></span> | <span data-ttu-id="97c33-162">Besitzer der angegebenen Warnungen</span><span class="sxs-lookup"><span data-stu-id="97c33-162">Owner of the specified alerts</span></span>
<span data-ttu-id="97c33-163">classification</span><span class="sxs-lookup"><span data-stu-id="97c33-163">classification</span></span> | <span data-ttu-id="97c33-164">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="97c33-164">String</span></span> | <span data-ttu-id="97c33-165">Gibt die Spezifikation der angegebenen Warnungen an.</span><span class="sxs-lookup"><span data-stu-id="97c33-165">Specifies the specification of the specified alerts.</span></span> <span data-ttu-id="97c33-166">Die Eigenschaftswerte sind: 'Unknown', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="97c33-166">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="97c33-167">Bestimmung</span><span class="sxs-lookup"><span data-stu-id="97c33-167">determination</span></span> | <span data-ttu-id="97c33-168">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="97c33-168">String</span></span> | <span data-ttu-id="97c33-169">Gibt die Bestimmung der angegebenen Warnungen an.</span><span class="sxs-lookup"><span data-stu-id="97c33-169">Specifies the determination of the specified alerts.</span></span> <span data-ttu-id="97c33-170">Die Eigenschaftswerte sind: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="97c33-170">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="97c33-171">comment</span><span class="sxs-lookup"><span data-stu-id="97c33-171">comment</span></span> | <span data-ttu-id="97c33-172">String</span><span class="sxs-lookup"><span data-stu-id="97c33-172">String</span></span> | <span data-ttu-id="97c33-173">Kommentar, der den angegebenen Warnungen hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="97c33-173">Comment to be added to the specified alerts.</span></span>

## <a name="response"></a><span data-ttu-id="97c33-174">Antwort</span><span class="sxs-lookup"><span data-stu-id="97c33-174">Response</span></span>

<span data-ttu-id="97c33-175">Wenn die Methode erfolgreich ist, wird 200 OK mit einem leeren Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="97c33-175">If successful, this method returns 200 OK, with an empty response body.</span></span>

## <a name="example"></a><span data-ttu-id="97c33-176">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97c33-176">Example</span></span>

### <a name="request"></a><span data-ttu-id="97c33-177">Anforderung</span><span class="sxs-lookup"><span data-stu-id="97c33-177">Request</span></span>

<span data-ttu-id="97c33-178">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="97c33-178">Here is an example of the request.</span></span>

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

---
title: Aktualisieren der Computerentitäts-API
description: Erfahren Sie, wie Sie Computertags mithilfe dieser API aktualisieren. Sie können die Tags und Gerätewerteigenschaften aktualisieren.
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985747"
---
# <a name="update-machine"></a><span data-ttu-id="570f5-105">Aktualisieren des Computers</span><span class="sxs-lookup"><span data-stu-id="570f5-105">Update machine</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="570f5-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="570f5-106">**Applies to:**</span></span>
- [<span data-ttu-id="570f5-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="570f5-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="570f5-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="570f5-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="570f5-109">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="570f5-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="570f5-110">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="570f5-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="570f5-111">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="570f5-111">API description</span></span>
<span data-ttu-id="570f5-112">Aktualisiert die Eigenschaften des vorhandenen [Computers.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="570f5-112">Updates properties of existing [Machine](machine.md).</span></span>
<br><span data-ttu-id="570f5-113">Aktualisierbare Eigenschaften sind: ```machineTags``` und ```deviceValue``` .</span><span class="sxs-lookup"><span data-stu-id="570f5-113">Updatable properties are: ```machineTags``` and ```deviceValue```.</span></span>


## <a name="limitations"></a><span data-ttu-id="570f5-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="570f5-114">Limitations</span></span>
1. <span data-ttu-id="570f5-115">Sie können Computer aktualisieren, die in der API verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="570f5-115">You can update machines that are available in the API.</span></span> 
2. <span data-ttu-id="570f5-116">Der Updatecomputer fügt nur Tags an die Tagsammlung an.</span><span class="sxs-lookup"><span data-stu-id="570f5-116">Update machine only appends tags to the tag collection.</span></span> <span data-ttu-id="570f5-117">Wenn Tags vorhanden sind, müssen sie in die Tagssammlung im Textkörper eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="570f5-117">If tags exist, they must be included in the tags collection in the body.</span></span>
3. <span data-ttu-id="570f5-118">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="570f5-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="570f5-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="570f5-119">Permissions</span></span>
<span data-ttu-id="570f5-120">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="570f5-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="570f5-121">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="570f5-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="570f5-122">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="570f5-122">Permission type</span></span> |   <span data-ttu-id="570f5-123">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="570f5-123">Permission</span></span>  |   <span data-ttu-id="570f5-124">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="570f5-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="570f5-125">Application</span><span class="sxs-lookup"><span data-stu-id="570f5-125">Application</span></span> |   <span data-ttu-id="570f5-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="570f5-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="570f5-127">"Lesen und Schreiben von Computerinformationen für alle Computer"</span><span class="sxs-lookup"><span data-stu-id="570f5-127">'Read and write machine information for all machines'</span></span>
<span data-ttu-id="570f5-128">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="570f5-128">Delegated (work or school account)</span></span> | <span data-ttu-id="570f5-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="570f5-129">Machine.ReadWrite</span></span> | <span data-ttu-id="570f5-130">"Lesen und Schreiben von Computerinformationen"</span><span class="sxs-lookup"><span data-stu-id="570f5-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="570f5-131">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="570f5-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="570f5-132">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Warnungsuntersuchung".</span><span class="sxs-lookup"><span data-stu-id="570f5-132">The user needs to have at least the following role permission: 'Alerts investigation'.</span></span> <span data-ttu-id="570f5-133">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="570f5-133">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="570f5-134">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben, das der Warnung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="570f5-134">The user needs to have access to the device associated with the alert, based on device group settings.</span></span> <span data-ttu-id="570f5-135">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="570f5-135">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="570f5-136">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="570f5-136">HTTP request</span></span>
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a><span data-ttu-id="570f5-137">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="570f5-137">Request headers</span></span>

<span data-ttu-id="570f5-138">Name</span><span class="sxs-lookup"><span data-stu-id="570f5-138">Name</span></span> | <span data-ttu-id="570f5-139">Typ</span><span class="sxs-lookup"><span data-stu-id="570f5-139">Type</span></span> | <span data-ttu-id="570f5-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="570f5-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="570f5-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="570f5-141">Authorization</span></span> | <span data-ttu-id="570f5-142">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="570f5-142">String</span></span> | <span data-ttu-id="570f5-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="570f5-143">Bearer {token}.</span></span> <span data-ttu-id="570f5-144">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="570f5-144">**Required**.</span></span>
<span data-ttu-id="570f5-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="570f5-145">Content-Type</span></span> | <span data-ttu-id="570f5-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="570f5-146">String</span></span> | <span data-ttu-id="570f5-147">application/json.</span><span class="sxs-lookup"><span data-stu-id="570f5-147">application/json.</span></span> <span data-ttu-id="570f5-148">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="570f5-148">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="570f5-149">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="570f5-149">Request body</span></span>
<span data-ttu-id="570f5-150">Geben Sie im Anforderungstext die Werte für die relevanten Felder an, die aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="570f5-150">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="570f5-151">Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre vorherigen Werte oder werden basierend auf Änderungen an anderen Eigenschaftswerten neu berechnet.</span><span class="sxs-lookup"><span data-stu-id="570f5-151">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="570f5-152">Um eine optimale Leistung zu erzielen, sollten Sie vorhandene Werte, die sich nicht geändert haben, nicht einschließen.</span><span class="sxs-lookup"><span data-stu-id="570f5-152">For best performance, you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="570f5-153">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="570f5-153">Property</span></span> | <span data-ttu-id="570f5-154">Typ</span><span class="sxs-lookup"><span data-stu-id="570f5-154">Type</span></span> | <span data-ttu-id="570f5-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="570f5-155">Description</span></span>
:---|:---|:---
<span data-ttu-id="570f5-156">machineTags</span><span class="sxs-lookup"><span data-stu-id="570f5-156">machineTags</span></span> | <span data-ttu-id="570f5-157">String-Sammlung</span><span class="sxs-lookup"><span data-stu-id="570f5-157">String collection</span></span> | <span data-ttu-id="570f5-158">Satz [](machine.md) von Computertags.</span><span class="sxs-lookup"><span data-stu-id="570f5-158">Set of [machine](machine.md) tags.</span></span>
<span data-ttu-id="570f5-159">deviceValue</span><span class="sxs-lookup"><span data-stu-id="570f5-159">deviceValue</span></span> | <span data-ttu-id="570f5-160">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="570f5-160">Nullable Enum</span></span> | <span data-ttu-id="570f5-161">Der [Wert des Geräts.](tvm-assign-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="570f5-161">The [value of the device](tvm-assign-device-value.md).</span></span> <span data-ttu-id="570f5-162">Mögliche Werte sind: 'Normal', 'Low' und 'High'.</span><span class="sxs-lookup"><span data-stu-id="570f5-162">Possible values are: 'Normal', 'Low' and 'High'.</span></span>

## <a name="response"></a><span data-ttu-id="570f5-163">Antwort</span><span class="sxs-lookup"><span data-stu-id="570f5-163">Response</span></span>
<span data-ttu-id="570f5-164">Wenn die Methode erfolgreich ist, werden 200 OK und die [Computerentität](machine.md) im Antworttext mit den aktualisierten Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="570f5-164">If successful, this method returns 200 OK, and the [machine](machine.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="570f5-165">Wenn die Sammlung von Computertags im Textkörper keine vorhandenen Computertags enthält– 400 Ungültige Eingabe und eine Meldung, die über die fehlenden Tags informiert.</span><span class="sxs-lookup"><span data-stu-id="570f5-165">If machine tags collection in body doesn't contain existing machine tags - 400 Invalid Input and a message informing of the missing tag/s.</span></span>
<span data-ttu-id="570f5-166">Wenn der Computer mit der angegebenen ID nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="570f5-166">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="570f5-167">Beispiel</span><span class="sxs-lookup"><span data-stu-id="570f5-167">Example</span></span>

<span data-ttu-id="570f5-168">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="570f5-168">**Request**</span></span>

<span data-ttu-id="570f5-169">Hier ist ein Beispiel für die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="570f5-169">Here's an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```

---
title: Häufige Fehlercodes für Microsoft 365 Defender-Rest-API
description: Informationen zu den allgemeinen Fehlercodes von Microsoft 365 Defender-Rest-API
keywords: API, Fehler, Codes, häufige Fehler, MTP, API-Fehlercodes
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
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719214"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="65ec3-104">Häufige Fehlercodes für Microsoft 365 Defender-Rest-API</span><span class="sxs-lookup"><span data-stu-id="65ec3-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="65ec3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="65ec3-105">**Applies to:**</span></span>

- <span data-ttu-id="65ec3-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="65ec3-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65ec3-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="65ec3-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="65ec3-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="65ec3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="65ec3-109">Fehlercodes werden möglicherweise von einem Vorgang in einer der Microsoft 365 Defender-APIs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="65ec3-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="65ec3-110">Jede Fehlerantwort enthält eine Fehlermeldung, die helfen kann, das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="65ec3-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="65ec3-111">Die Spalte Fehlermeldung im Abschnitt Table enthält einige Beispiel Meldungen.</span><span class="sxs-lookup"><span data-stu-id="65ec3-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="65ec3-112">Der Inhalt der tatsächlichen Nachrichten variiert je nach den Faktoren, die die Antwort ausgelöst haben.</span><span class="sxs-lookup"><span data-stu-id="65ec3-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="65ec3-113">Variablen Inhalt wird in der Tabelle durch spitzen Klammern angegeben.</span><span class="sxs-lookup"><span data-stu-id="65ec3-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="65ec3-114">Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="65ec3-114">Error codes</span></span>

<span data-ttu-id="65ec3-115">Fehlercode</span><span class="sxs-lookup"><span data-stu-id="65ec3-115">Error code</span></span> | <span data-ttu-id="65ec3-116">HTTP-Statuscode</span><span class="sxs-lookup"><span data-stu-id="65ec3-116">HTTP status code</span></span> | <span data-ttu-id="65ec3-117">Nachricht</span><span class="sxs-lookup"><span data-stu-id="65ec3-117">Message</span></span>
-|-|-
<span data-ttu-id="65ec3-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="65ec3-118">BadRequest</span></span> | <span data-ttu-id="65ec3-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="65ec3-119">BadRequest (400)</span></span> | <span data-ttu-id="65ec3-120">Fehlermeldung allgemeine ungültige Anforderung.</span><span class="sxs-lookup"><span data-stu-id="65ec3-120">General Bad Request error message.</span></span>
<span data-ttu-id="65ec3-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="65ec3-121">ODataError</span></span> | <span data-ttu-id="65ec3-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="65ec3-122">BadRequest (400)</span></span> | <span data-ttu-id="65ec3-123">Ungültige OData-URI \<the specific error is specified\> -Abfrage.</span><span class="sxs-lookup"><span data-stu-id="65ec3-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="65ec3-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="65ec3-124">InvalidInput</span></span> | <span data-ttu-id="65ec3-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="65ec3-125">BadRequest (400)</span></span> | <span data-ttu-id="65ec3-126">Ungültige Eingabe \<the invalid input\> .</span><span class="sxs-lookup"><span data-stu-id="65ec3-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="65ec3-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="65ec3-127">InvalidRequestBody</span></span> | <span data-ttu-id="65ec3-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="65ec3-128">BadRequest (400)</span></span> | <span data-ttu-id="65ec3-129">Ungültiger Anforderungstext.</span><span class="sxs-lookup"><span data-stu-id="65ec3-129">Invalid request body.</span></span>
<span data-ttu-id="65ec3-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="65ec3-130">InvalidHashValue</span></span> | <span data-ttu-id="65ec3-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="65ec3-131">BadRequest (400)</span></span> | <span data-ttu-id="65ec3-132">Der Hashwert \<the invalid hash\> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="65ec3-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="65ec3-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="65ec3-133">InvalidDomainName</span></span> | <span data-ttu-id="65ec3-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="65ec3-134">BadRequest (400)</span></span> | <span data-ttu-id="65ec3-135">Der Domänenname \<the invalid domain\> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="65ec3-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="65ec3-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="65ec3-136">InvalidIpAddress</span></span> | <span data-ttu-id="65ec3-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="65ec3-137">BadRequest (400)</span></span> | <span data-ttu-id="65ec3-138">Die IP-Adresse \<the invalid IP\> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="65ec3-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="65ec3-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="65ec3-139">InvalidUrl</span></span> | <span data-ttu-id="65ec3-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="65ec3-140">BadRequest (400)</span></span> | <span data-ttu-id="65ec3-141">\<the invalid URL\>Die URL ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="65ec3-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="65ec3-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="65ec3-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="65ec3-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="65ec3-143">BadRequest (400)</span></span> | <span data-ttu-id="65ec3-144">Maximale Batchgröße überschritten.</span><span class="sxs-lookup"><span data-stu-id="65ec3-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="65ec3-145">Empfangen: \<batch size received\> , zulässig: {Batchgröße zulässig}.</span><span class="sxs-lookup"><span data-stu-id="65ec3-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="65ec3-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="65ec3-146">MissingRequiredParameter</span></span> | <span data-ttu-id="65ec3-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="65ec3-147">BadRequest (400)</span></span> | <span data-ttu-id="65ec3-148">Parameter \<the missing parameter\> fehlt.</span><span class="sxs-lookup"><span data-stu-id="65ec3-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="65ec3-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="65ec3-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="65ec3-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="65ec3-150">BadRequest (400)</span></span> | <span data-ttu-id="65ec3-151">Die Betriebssystemplattform \<the client OS Platform\> wird für diese Aktion nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="65ec3-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="65ec3-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="65ec3-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="65ec3-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="65ec3-153">BadRequest (400)</span></span> | <span data-ttu-id="65ec3-154">\<The requested action\> wird auf Client Version \<supported client version\> und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="65ec3-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="65ec3-155">Nicht autorisiert (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="65ec3-155">Unauthorized</span></span> | <span data-ttu-id="65ec3-156">Nicht autorisiert (401)</span><span class="sxs-lookup"><span data-stu-id="65ec3-156">Unauthorized (401)</span></span> | <span data-ttu-id="65ec3-157">Nicht autorisiert (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="65ec3-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="65ec3-158">*Hinweis: wird in der Regel durch einen ungültigen oder abgelaufenen Autorisierungsheader verursacht.*</span><span class="sxs-lookup"><span data-stu-id="65ec3-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="65ec3-159">Verboten (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="65ec3-159">Forbidden</span></span> | <span data-ttu-id="65ec3-160">Unzulässig (403)</span><span class="sxs-lookup"><span data-stu-id="65ec3-160">Forbidden (403)</span></span> | <span data-ttu-id="65ec3-161">Verboten (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="65ec3-161">Forbidden</span></span> <br /><br /><span data-ttu-id="65ec3-162">*Hinweis: gültiges Token, jedoch unzureichende Berechtigungen für die Aktion*.</span><span class="sxs-lookup"><span data-stu-id="65ec3-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="65ec3-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="65ec3-163">DisabledFeature</span></span> | <span data-ttu-id="65ec3-164">Unzulässig (403)</span><span class="sxs-lookup"><span data-stu-id="65ec3-164">Forbidden (403)</span></span> | <span data-ttu-id="65ec3-165">Das Mandanten Feature ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="65ec3-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="65ec3-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="65ec3-166">DisallowedOperation</span></span> | <span data-ttu-id="65ec3-167">Unzulässig (403)</span><span class="sxs-lookup"><span data-stu-id="65ec3-167">Forbidden (403)</span></span> | <span data-ttu-id="65ec3-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="65ec3-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="65ec3-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="65ec3-169">NotFound</span></span> | <span data-ttu-id="65ec3-170">Nicht gefunden (404)</span><span class="sxs-lookup"><span data-stu-id="65ec3-170">Not Found (404)</span></span> | <span data-ttu-id="65ec3-171">Fehlermeldung "allgemeine nicht gefunden".</span><span class="sxs-lookup"><span data-stu-id="65ec3-171">General Not Found error message.</span></span>
<span data-ttu-id="65ec3-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="65ec3-172">ResourceNotFound</span></span> | <span data-ttu-id="65ec3-173">Nicht gefunden (404)</span><span class="sxs-lookup"><span data-stu-id="65ec3-173">Not Found (404)</span></span> | <span data-ttu-id="65ec3-174">Ressource \<the requested resource\> wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="65ec3-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="65ec3-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="65ec3-175">InternalServerError</span></span> | <span data-ttu-id="65ec3-176">Interner Server Fehler (500)</span><span class="sxs-lookup"><span data-stu-id="65ec3-176">Internal Server Error (500)</span></span> | <span data-ttu-id="65ec3-177">*Hinweis: keine Fehlermeldung, wiederholen Sie den Vorgang, oder wenden Sie sich an Microsoft, wenn er nicht aufgelöst wird.*</span><span class="sxs-lookup"><span data-stu-id="65ec3-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="65ec3-178">Beispiele</span><span class="sxs-lookup"><span data-stu-id="65ec3-178">Examples</span></span>

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```

```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```

## <a name="body-parameters"></a><span data-ttu-id="65ec3-179">Body parameters</span><span class="sxs-lookup"><span data-stu-id="65ec3-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65ec3-180">Bei den textparametern wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="65ec3-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="65ec3-181">Wenn ein *InvalidRequestBody* -oder *MissingRequiredParameter* -Fehler auftritt, kann dies auf einen Tippfehler zurückzuführen sein.</span><span class="sxs-lookup"><span data-stu-id="65ec3-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="65ec3-182">Lesen Sie in der API-Dokumentation nach, ob die übermittelten Parameter mit dem entsprechenden Beispiel übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="65ec3-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="65ec3-183">Tracking-ID</span><span class="sxs-lookup"><span data-stu-id="65ec3-183">Tracking ID</span></span>

<span data-ttu-id="65ec3-184">Jede Fehlerantwort enthält einen eindeutigen ID-Parameter für die Nachverfolgung.</span><span class="sxs-lookup"><span data-stu-id="65ec3-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="65ec3-185">Der Eigenschaften Name dieses Parameters ist *target*.</span><span class="sxs-lookup"><span data-stu-id="65ec3-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="65ec3-186">Wenn Sie uns über einen Fehler kontaktieren, hilft uns das Anfügen dieser ID, die Ursache des Problems zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="65ec3-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="65ec3-187">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="65ec3-187">Related articles</span></span>

- [<span data-ttu-id="65ec3-188">Microsoft 365 Defender-APIs (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="65ec3-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="65ec3-189">Unterstützte Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="65ec3-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="65ec3-190">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="65ec3-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="65ec3-191">Informationen zu API-Grenzwerten und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="65ec3-191">Learn about API limits and licensing</span></span>](api-terms.md)

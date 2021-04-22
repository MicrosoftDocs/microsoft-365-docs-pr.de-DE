---
title: Allgemeine Microsoft 365 Defender REST-API-Fehlercodes
description: Informationen zu den allgemeinen Microsoft 365 Defender REST-API-Fehlercodes
keywords: api, error, codes, common errors, Microsoft 365 Defender, api error codes
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
ms.openlocfilehash: e621b79d37a2c3a22394bd51e0493334eff461c7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932881"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="cd5f2-104">Allgemeine Microsoft 365 Defender REST-API-Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="cd5f2-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cd5f2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cd5f2-105">**Applies to:**</span></span>

- <span data-ttu-id="cd5f2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd5f2-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd5f2-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cd5f2-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="cd5f2-109">Fehlercodes können von einem Vorgang für eine der Microsoft 365 Defender-APIs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="cd5f2-110">Jede Fehlerantwort enthält eine Fehlermeldung, die zur Lösung des Problems beitragen kann.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="cd5f2-111">Die Fehlermeldungsspalte im Abschnitt Tabelle enthält einige Beispielmeldungen.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="cd5f2-112">Der Inhalt der tatsächlichen Nachrichten variiert je nach den Faktoren, die die Antwort ausgelöst haben.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="cd5f2-113">Variabler Inhalt wird in der Tabelle durch eckige Klammern angegeben.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="cd5f2-114">Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="cd5f2-114">Error codes</span></span>

<span data-ttu-id="cd5f2-115">Fehlercode</span><span class="sxs-lookup"><span data-stu-id="cd5f2-115">Error code</span></span> | <span data-ttu-id="cd5f2-116">HTTP-Statuscode</span><span class="sxs-lookup"><span data-stu-id="cd5f2-116">HTTP status code</span></span> | <span data-ttu-id="cd5f2-117">Message</span><span class="sxs-lookup"><span data-stu-id="cd5f2-117">Message</span></span>
-|-|-
<span data-ttu-id="cd5f2-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="cd5f2-118">BadRequest</span></span> | <span data-ttu-id="cd5f2-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-119">BadRequest (400)</span></span> | <span data-ttu-id="cd5f2-120">Fehlermeldung "Allgemeine ungültige Anforderung".</span><span class="sxs-lookup"><span data-stu-id="cd5f2-120">General Bad Request error message.</span></span>
<span data-ttu-id="cd5f2-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="cd5f2-121">ODataError</span></span> | <span data-ttu-id="cd5f2-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-122">BadRequest (400)</span></span> | <span data-ttu-id="cd5f2-123">Ungültige OData-URI-Abfrage \<the specific error is specified\> .</span><span class="sxs-lookup"><span data-stu-id="cd5f2-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="cd5f2-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="cd5f2-124">InvalidInput</span></span> | <span data-ttu-id="cd5f2-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-125">BadRequest (400)</span></span> | <span data-ttu-id="cd5f2-126">Ungültige Eingabe \<the invalid input\> .</span><span class="sxs-lookup"><span data-stu-id="cd5f2-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="cd5f2-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="cd5f2-127">InvalidRequestBody</span></span> | <span data-ttu-id="cd5f2-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-128">BadRequest (400)</span></span> | <span data-ttu-id="cd5f2-129">Ungültiger Anforderungstext.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-129">Invalid request body.</span></span>
<span data-ttu-id="cd5f2-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="cd5f2-130">InvalidHashValue</span></span> | <span data-ttu-id="cd5f2-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-131">BadRequest (400)</span></span> | <span data-ttu-id="cd5f2-132">Hashwert \<the invalid hash\> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="cd5f2-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="cd5f2-133">InvalidDomainName</span></span> | <span data-ttu-id="cd5f2-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-134">BadRequest (400)</span></span> | <span data-ttu-id="cd5f2-135">Domänenname \<the invalid domain\> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="cd5f2-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="cd5f2-136">InvalidIpAddress</span></span> | <span data-ttu-id="cd5f2-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-137">BadRequest (400)</span></span> | <span data-ttu-id="cd5f2-138">Die \<the invalid IP\> IP-Adresse ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="cd5f2-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="cd5f2-139">InvalidUrl</span></span> | <span data-ttu-id="cd5f2-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-140">BadRequest (400)</span></span> | <span data-ttu-id="cd5f2-141">DIE URL \<the invalid URL\> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="cd5f2-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="cd5f2-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="cd5f2-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-143">BadRequest (400)</span></span> | <span data-ttu-id="cd5f2-144">Die maximale Batchgröße wurde überschritten.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="cd5f2-145">Received: \<batch size received\> , allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="cd5f2-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="cd5f2-146">MissingRequiredParameter</span></span> | <span data-ttu-id="cd5f2-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-147">BadRequest (400)</span></span> | <span data-ttu-id="cd5f2-148">Parameter \<the missing parameter\> fehlt.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="cd5f2-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="cd5f2-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="cd5f2-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-150">BadRequest (400)</span></span> | <span data-ttu-id="cd5f2-151">Die \<the client OS Platform\> Betriebssystemplattform wird für diese Aktion nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="cd5f2-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="cd5f2-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="cd5f2-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-153">BadRequest (400)</span></span> | <span data-ttu-id="cd5f2-154">\<The requested action\> wird für die Clientversion \<supported client version\> und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="cd5f2-155">Nicht autorisiert (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-155">Unauthorized</span></span> | <span data-ttu-id="cd5f2-156">Nicht autorisierter Benutzer (401)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-156">Unauthorized (401)</span></span> | <span data-ttu-id="cd5f2-157">Nicht autorisiert (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="cd5f2-158">*Hinweis: In der Regel durch einen ungültigen oder abgelaufenen Autorisierungsheader verursacht.*</span><span class="sxs-lookup"><span data-stu-id="cd5f2-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="cd5f2-159">Verboten (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-159">Forbidden</span></span> | <span data-ttu-id="cd5f2-160">Verboten (403)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-160">Forbidden (403)</span></span> | <span data-ttu-id="cd5f2-161">Verboten (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-161">Forbidden</span></span> <br /><br /><span data-ttu-id="cd5f2-162">*Hinweis: Gültiges Token, aber unzureichende Berechtigung für die Aktion*.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="cd5f2-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="cd5f2-163">DisabledFeature</span></span> | <span data-ttu-id="cd5f2-164">Verboten (403)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-164">Forbidden (403)</span></span> | <span data-ttu-id="cd5f2-165">Das Mandantenfeature ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="cd5f2-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="cd5f2-166">DisallowedOperation</span></span> | <span data-ttu-id="cd5f2-167">Verboten (403)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-167">Forbidden (403)</span></span> | <span data-ttu-id="cd5f2-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="cd5f2-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="cd5f2-169">NotFound</span></span> | <span data-ttu-id="cd5f2-170">Nicht gefunden (404)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-170">Not Found (404)</span></span> | <span data-ttu-id="cd5f2-171">Fehlermeldung "Allgemein nicht gefunden".</span><span class="sxs-lookup"><span data-stu-id="cd5f2-171">General Not Found error message.</span></span>
<span data-ttu-id="cd5f2-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="cd5f2-172">ResourceNotFound</span></span> | <span data-ttu-id="cd5f2-173">Nicht gefunden (404)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-173">Not Found (404)</span></span> | <span data-ttu-id="cd5f2-174">Ressource \<the requested resource\> wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="cd5f2-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="cd5f2-175">InternalServerError</span></span> | <span data-ttu-id="cd5f2-176">Interner Serverfehler (500)</span><span class="sxs-lookup"><span data-stu-id="cd5f2-176">Internal Server Error (500)</span></span> | <span data-ttu-id="cd5f2-177">*Hinweis: Keine Fehlermeldung, wiederholen Sie den Vorgang, oder wenden Sie sich an Microsoft, wenn sie nicht aufgelöst wird*</span><span class="sxs-lookup"><span data-stu-id="cd5f2-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="cd5f2-178">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd5f2-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="cd5f2-179">Body parameters</span><span class="sxs-lookup"><span data-stu-id="cd5f2-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd5f2-180">Bei Textparametern wird die Zwischenschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="cd5f2-181">Wenn ein *InvalidRequestBody-* oder *MissingRequiredParameter-Fehler* auftritt, kann er durch einen Tippfehler verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="cd5f2-182">Überprüfen Sie die API-Dokumentation, und überprüfen Sie, ob die übermittelten Parameter mit dem entsprechenden Beispiel übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="cd5f2-183">Nachverfolgungs-ID</span><span class="sxs-lookup"><span data-stu-id="cd5f2-183">Tracking ID</span></span>

<span data-ttu-id="cd5f2-184">Jede Fehlerantwort enthält einen eindeutigen ID-Parameter für die Nachverfolgung.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="cd5f2-185">Der Eigenschaftenname dieses Parameters ist *Target*.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="cd5f2-186">Wenn Sie uns über einen Fehler kontaktieren, helfen uns die Anfügen dieser ID, die Ursache des Problems zu finden.</span><span class="sxs-lookup"><span data-stu-id="cd5f2-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cd5f2-187">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="cd5f2-187">Related articles</span></span>

- [<span data-ttu-id="cd5f2-188">Übersicht über Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="cd5f2-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="cd5f2-189">Unterstützte Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="cd5f2-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="cd5f2-190">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="cd5f2-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="cd5f2-191">Informationen zu API-Beschränkungen und -Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="cd5f2-191">Learn about API limits and licensing</span></span>](api-terms.md)

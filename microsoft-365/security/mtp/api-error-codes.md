---
title: Allgemeine Fehlercodes der Microsoft 365 Defender REST-API
description: Erfahren Sie mehr über die allgemeinen Fehlercodes der Microsoft 365 Defender REST-API.
keywords: API, Fehler, Codes, häufige Fehler, Mtp, API-Fehlercodes
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
ms.openlocfilehash: 15eabc8ff28e7cc0313e2a1cb701403de0eab120
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928390"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="dde68-104">Allgemeine Fehlercodes der Microsoft 365 Defender REST-API</span><span class="sxs-lookup"><span data-stu-id="dde68-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="dde68-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="dde68-105">**Applies to:**</span></span>

- <span data-ttu-id="dde68-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="dde68-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dde68-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="dde68-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="dde68-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="dde68-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="dde68-109">Fehlercodes können von einem Vorgang auf einer der Microsoft 365 Defender-APIs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="dde68-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="dde68-110">Jede Fehlerantwort enthält eine Fehlermeldung, die zur Behebung des Problems beitragen kann.</span><span class="sxs-lookup"><span data-stu-id="dde68-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="dde68-111">Die Fehlermeldungsspalte im Tabellenabschnitt enthält einige Beispielmeldungen.</span><span class="sxs-lookup"><span data-stu-id="dde68-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="dde68-112">Der Inhalt tatsächlicher Nachrichten variiert je nach den Faktoren, die die Antwort ausgelöst haben.</span><span class="sxs-lookup"><span data-stu-id="dde68-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="dde68-113">Variabler Inhalt wird in der Tabelle durch spitze Klammern angegeben.</span><span class="sxs-lookup"><span data-stu-id="dde68-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="dde68-114">Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="dde68-114">Error codes</span></span>

<span data-ttu-id="dde68-115">Fehlercode</span><span class="sxs-lookup"><span data-stu-id="dde68-115">Error code</span></span> | <span data-ttu-id="dde68-116">HTTP-Statuscode</span><span class="sxs-lookup"><span data-stu-id="dde68-116">HTTP status code</span></span> | <span data-ttu-id="dde68-117">Message</span><span class="sxs-lookup"><span data-stu-id="dde68-117">Message</span></span>
-|-|-
<span data-ttu-id="dde68-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="dde68-118">BadRequest</span></span> | <span data-ttu-id="dde68-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dde68-119">BadRequest (400)</span></span> | <span data-ttu-id="dde68-120">Fehlermeldung "Allgemeine ungültige Anforderung".</span><span class="sxs-lookup"><span data-stu-id="dde68-120">General Bad Request error message.</span></span>
<span data-ttu-id="dde68-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="dde68-121">ODataError</span></span> | <span data-ttu-id="dde68-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dde68-122">BadRequest (400)</span></span> | <span data-ttu-id="dde68-123">Ungültige OData-URI-Abfrage. \<the specific error is specified\></span><span class="sxs-lookup"><span data-stu-id="dde68-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="dde68-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="dde68-124">InvalidInput</span></span> | <span data-ttu-id="dde68-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dde68-125">BadRequest (400)</span></span> | <span data-ttu-id="dde68-126">Ungültige \<the invalid input\> Eingabe.</span><span class="sxs-lookup"><span data-stu-id="dde68-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="dde68-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="dde68-127">InvalidRequestBody</span></span> | <span data-ttu-id="dde68-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dde68-128">BadRequest (400)</span></span> | <span data-ttu-id="dde68-129">Ungültiger Anforderungstext.</span><span class="sxs-lookup"><span data-stu-id="dde68-129">Invalid request body.</span></span>
<span data-ttu-id="dde68-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="dde68-130">InvalidHashValue</span></span> | <span data-ttu-id="dde68-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dde68-131">BadRequest (400)</span></span> | <span data-ttu-id="dde68-132">Hashwert \<the invalid hash\> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="dde68-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="dde68-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="dde68-133">InvalidDomainName</span></span> | <span data-ttu-id="dde68-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dde68-134">BadRequest (400)</span></span> | <span data-ttu-id="dde68-135">Der \<the invalid domain\> Domänenname ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="dde68-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="dde68-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="dde68-136">InvalidIpAddress</span></span> | <span data-ttu-id="dde68-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dde68-137">BadRequest (400)</span></span> | <span data-ttu-id="dde68-138">Die \<the invalid IP\> IP-Adresse ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="dde68-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="dde68-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="dde68-139">InvalidUrl</span></span> | <span data-ttu-id="dde68-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dde68-140">BadRequest (400)</span></span> | <span data-ttu-id="dde68-141">Die URL \<the invalid URL\> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="dde68-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="dde68-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="dde68-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="dde68-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dde68-143">BadRequest (400)</span></span> | <span data-ttu-id="dde68-144">Die maximale Batchgröße wurde überschritten.</span><span class="sxs-lookup"><span data-stu-id="dde68-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="dde68-145">Received: \<batch size received\> , allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="dde68-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="dde68-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="dde68-146">MissingRequiredParameter</span></span> | <span data-ttu-id="dde68-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dde68-147">BadRequest (400)</span></span> | <span data-ttu-id="dde68-148">Parameter \<the missing parameter\> fehlt.</span><span class="sxs-lookup"><span data-stu-id="dde68-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="dde68-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="dde68-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="dde68-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dde68-150">BadRequest (400)</span></span> | <span data-ttu-id="dde68-151">Die \<the client OS Platform\> Betriebssystemplattform wird für diese Aktion nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dde68-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="dde68-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="dde68-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="dde68-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dde68-153">BadRequest (400)</span></span> | <span data-ttu-id="dde68-154">\<The requested action\> wird für die Clientversion \<supported client version\> und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dde68-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="dde68-155">Nicht autorisiert (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="dde68-155">Unauthorized</span></span> | <span data-ttu-id="dde68-156">Nicht autorisierte (401)</span><span class="sxs-lookup"><span data-stu-id="dde68-156">Unauthorized (401)</span></span> | <span data-ttu-id="dde68-157">Nicht autorisiert (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="dde68-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="dde68-158">*Hinweis: In der Regel durch einen ungültigen oder abgelaufenen Autorisierungsheader verursacht.*</span><span class="sxs-lookup"><span data-stu-id="dde68-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="dde68-159">Verboten (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="dde68-159">Forbidden</span></span> | <span data-ttu-id="dde68-160">Verboten (403)</span><span class="sxs-lookup"><span data-stu-id="dde68-160">Forbidden (403)</span></span> | <span data-ttu-id="dde68-161">Verboten (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="dde68-161">Forbidden</span></span> <br /><br /><span data-ttu-id="dde68-162">*Hinweis: Gültiges Token, aber unzureichende Berechtigung für die Aktion.*</span><span class="sxs-lookup"><span data-stu-id="dde68-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="dde68-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="dde68-163">DisabledFeature</span></span> | <span data-ttu-id="dde68-164">Verboten (403)</span><span class="sxs-lookup"><span data-stu-id="dde68-164">Forbidden (403)</span></span> | <span data-ttu-id="dde68-165">Das Mandantenfeature ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="dde68-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="dde68-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="dde68-166">DisallowedOperation</span></span> | <span data-ttu-id="dde68-167">Verboten (403)</span><span class="sxs-lookup"><span data-stu-id="dde68-167">Forbidden (403)</span></span> | <span data-ttu-id="dde68-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="dde68-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="dde68-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="dde68-169">NotFound</span></span> | <span data-ttu-id="dde68-170">Nicht gefunden (404)</span><span class="sxs-lookup"><span data-stu-id="dde68-170">Not Found (404)</span></span> | <span data-ttu-id="dde68-171">Fehlermeldung "Allgemein nicht gefunden".</span><span class="sxs-lookup"><span data-stu-id="dde68-171">General Not Found error message.</span></span>
<span data-ttu-id="dde68-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="dde68-172">ResourceNotFound</span></span> | <span data-ttu-id="dde68-173">Nicht gefunden (404)</span><span class="sxs-lookup"><span data-stu-id="dde68-173">Not Found (404)</span></span> | <span data-ttu-id="dde68-174">Ressource \<the requested resource\> wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="dde68-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="dde68-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="dde68-175">InternalServerError</span></span> | <span data-ttu-id="dde68-176">Interner Serverfehler (500)</span><span class="sxs-lookup"><span data-stu-id="dde68-176">Internal Server Error (500)</span></span> | <span data-ttu-id="dde68-177">*Hinweis: Keine Fehlermeldung, wiederholen Sie den Vorgang, oder wenden Sie sich an Microsoft, wenn er nicht aufgelöst wird*</span><span class="sxs-lookup"><span data-stu-id="dde68-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="dde68-178">Beispiele</span><span class="sxs-lookup"><span data-stu-id="dde68-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="dde68-179">Body parameters</span><span class="sxs-lookup"><span data-stu-id="dde68-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dde68-180">Bei Textparametern wird die Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="dde68-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="dde68-181">Wenn ein Fehler *"InvalidRequestBody"* oder *"MissingRequiredParameter"* auftritt, kann er durch einen Tippfehler verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="dde68-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="dde68-182">Überprüfen Sie die API-Dokumentation, und überprüfen Sie, ob die übermittelten Parameter mit dem entsprechenden Beispiel übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="dde68-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="dde68-183">Nachverfolgungs-ID</span><span class="sxs-lookup"><span data-stu-id="dde68-183">Tracking ID</span></span>

<span data-ttu-id="dde68-184">Jede Fehlerantwort enthält einen eindeutigen ID-Parameter für die Nachverfolgung.</span><span class="sxs-lookup"><span data-stu-id="dde68-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="dde68-185">Der Eigenschaftenname dieses Parameters ist *Ziel.*</span><span class="sxs-lookup"><span data-stu-id="dde68-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="dde68-186">Wenn Sie uns über einen Fehler kontaktieren, hilft uns das Anfügen dieser ID, die Ursache des Problems zu finden.</span><span class="sxs-lookup"><span data-stu-id="dde68-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="dde68-187">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="dde68-187">Related articles</span></span>

- [<span data-ttu-id="dde68-188">Übersicht über Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="dde68-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="dde68-189">Unterstützte Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="dde68-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="dde68-190">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="dde68-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="dde68-191">Informationen zu API-Beschränkungen und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="dde68-191">Learn about API limits and licensing</span></span>](api-terms.md)

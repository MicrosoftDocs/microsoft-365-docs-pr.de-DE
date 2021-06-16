---
title: Häufige Fehlercodes Microsoft 365 Defender-REST-API
description: Erfahren Sie mehr über die allgemeinen Fehlercodes Microsoft 365 Defender REST-API
keywords: API, Fehler, Codes, häufige Fehler, Microsoft 365 Defender, API-Fehlercodes
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
ms.openlocfilehash: de24856e8ea7555a96de18cabca5ccadfe71b431
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930271"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="cf95b-104">Häufige Fehlercodes Microsoft 365 Defender-REST-API</span><span class="sxs-lookup"><span data-stu-id="cf95b-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cf95b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cf95b-105">**Applies to:**</span></span>

- <span data-ttu-id="cf95b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf95b-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf95b-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="cf95b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cf95b-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="cf95b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="cf95b-109">Fehlercodes können von einem Vorgang für eine der Microsoft 365 Defender-APIs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cf95b-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="cf95b-110">Jede Fehlerantwort enthält eine Fehlermeldung, die bei der Behebung des Problems helfen kann.</span><span class="sxs-lookup"><span data-stu-id="cf95b-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="cf95b-111">Die Fehlermeldungsspalte im Tabellenabschnitt enthält einige Beispielmeldungen.</span><span class="sxs-lookup"><span data-stu-id="cf95b-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="cf95b-112">Der Inhalt der tatsächlichen Nachrichten variiert basierend auf den Faktoren, die die Antwort ausgelöst haben.</span><span class="sxs-lookup"><span data-stu-id="cf95b-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="cf95b-113">Variabler Inhalt wird in der Tabelle durch eckige Klammern angegeben.</span><span class="sxs-lookup"><span data-stu-id="cf95b-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="cf95b-114">Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="cf95b-114">Error codes</span></span>

<span data-ttu-id="cf95b-115">Fehlercode</span><span class="sxs-lookup"><span data-stu-id="cf95b-115">Error code</span></span> | <span data-ttu-id="cf95b-116">HTTP-Statuscode</span><span class="sxs-lookup"><span data-stu-id="cf95b-116">HTTP status code</span></span> | <span data-ttu-id="cf95b-117">Meldung</span><span class="sxs-lookup"><span data-stu-id="cf95b-117">Message</span></span>
-|-|-
<span data-ttu-id="cf95b-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="cf95b-118">BadRequest</span></span> | <span data-ttu-id="cf95b-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cf95b-119">BadRequest (400)</span></span> | <span data-ttu-id="cf95b-120">Fehlermeldung "Allgemeine ungültige Anforderung".</span><span class="sxs-lookup"><span data-stu-id="cf95b-120">General Bad Request error message.</span></span>
<span data-ttu-id="cf95b-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="cf95b-121">ODataError</span></span> | <span data-ttu-id="cf95b-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cf95b-122">BadRequest (400)</span></span> | <span data-ttu-id="cf95b-123">Ungültige OData-URI-Abfrage. \<the specific error is specified\></span><span class="sxs-lookup"><span data-stu-id="cf95b-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="cf95b-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="cf95b-124">InvalidInput</span></span> | <span data-ttu-id="cf95b-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cf95b-125">BadRequest (400)</span></span> | <span data-ttu-id="cf95b-126">Ungültige Eingabe \<the invalid input\> .</span><span class="sxs-lookup"><span data-stu-id="cf95b-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="cf95b-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="cf95b-127">InvalidRequestBody</span></span> | <span data-ttu-id="cf95b-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cf95b-128">BadRequest (400)</span></span> | <span data-ttu-id="cf95b-129">Ungültiger Anforderungstext.</span><span class="sxs-lookup"><span data-stu-id="cf95b-129">Invalid request body.</span></span>
<span data-ttu-id="cf95b-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="cf95b-130">InvalidHashValue</span></span> | <span data-ttu-id="cf95b-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cf95b-131">BadRequest (400)</span></span> | <span data-ttu-id="cf95b-132">Der Hashwert \<the invalid hash\> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="cf95b-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="cf95b-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="cf95b-133">InvalidDomainName</span></span> | <span data-ttu-id="cf95b-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cf95b-134">BadRequest (400)</span></span> | <span data-ttu-id="cf95b-135">Der Domänenname \<the invalid domain\> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="cf95b-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="cf95b-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="cf95b-136">InvalidIpAddress</span></span> | <span data-ttu-id="cf95b-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cf95b-137">BadRequest (400)</span></span> | <span data-ttu-id="cf95b-138">Die IP-Adresse \<the invalid IP\> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="cf95b-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="cf95b-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="cf95b-139">InvalidUrl</span></span> | <span data-ttu-id="cf95b-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cf95b-140">BadRequest (400)</span></span> | <span data-ttu-id="cf95b-141">DIE URL \<the invalid URL\> ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="cf95b-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="cf95b-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="cf95b-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="cf95b-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cf95b-143">BadRequest (400)</span></span> | <span data-ttu-id="cf95b-144">Maximale Batchgröße überschritten.</span><span class="sxs-lookup"><span data-stu-id="cf95b-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="cf95b-145">Received: \<batch size received\> , allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="cf95b-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="cf95b-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="cf95b-146">MissingRequiredParameter</span></span> | <span data-ttu-id="cf95b-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cf95b-147">BadRequest (400)</span></span> | <span data-ttu-id="cf95b-148">Parameter \<the missing parameter\> fehlt.</span><span class="sxs-lookup"><span data-stu-id="cf95b-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="cf95b-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="cf95b-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="cf95b-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cf95b-150">BadRequest (400)</span></span> | <span data-ttu-id="cf95b-151">Die Betriebssystemplattform \<the client OS Platform\> wird für diese Aktion nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cf95b-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="cf95b-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="cf95b-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="cf95b-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="cf95b-153">BadRequest (400)</span></span> | <span data-ttu-id="cf95b-154">\<The requested action\> wird für clientversion \<supported client version\> und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cf95b-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="cf95b-155">Nicht autorisiert (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="cf95b-155">Unauthorized</span></span> | <span data-ttu-id="cf95b-156">Nicht autorisiert (401)</span><span class="sxs-lookup"><span data-stu-id="cf95b-156">Unauthorized (401)</span></span> | <span data-ttu-id="cf95b-157">Nicht autorisiert (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="cf95b-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="cf95b-158">*Hinweis: Wird in der Regel durch einen ungültigen oder abgelaufenen Autorisierungsheader verursacht.*</span><span class="sxs-lookup"><span data-stu-id="cf95b-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="cf95b-159">Verboten (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="cf95b-159">Forbidden</span></span> | <span data-ttu-id="cf95b-160">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="cf95b-160">Forbidden (403)</span></span> | <span data-ttu-id="cf95b-161">Verboten (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="cf95b-161">Forbidden</span></span> <br /><br /><span data-ttu-id="cf95b-162">*Hinweis: Gültiges Token, aber unzureichende Berechtigung für die Aktion.*</span><span class="sxs-lookup"><span data-stu-id="cf95b-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="cf95b-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="cf95b-163">DisabledFeature</span></span> | <span data-ttu-id="cf95b-164">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="cf95b-164">Forbidden (403)</span></span> | <span data-ttu-id="cf95b-165">Mandantenfunktion ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cf95b-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="cf95b-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="cf95b-166">DisallowedOperation</span></span> | <span data-ttu-id="cf95b-167">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="cf95b-167">Forbidden (403)</span></span> | <span data-ttu-id="cf95b-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="cf95b-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="cf95b-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="cf95b-169">NotFound</span></span> | <span data-ttu-id="cf95b-170">Nicht gefunden (404)</span><span class="sxs-lookup"><span data-stu-id="cf95b-170">Not Found (404)</span></span> | <span data-ttu-id="cf95b-171">Fehlermeldung "Allgemein nicht gefunden".</span><span class="sxs-lookup"><span data-stu-id="cf95b-171">General Not Found error message.</span></span>
<span data-ttu-id="cf95b-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="cf95b-172">ResourceNotFound</span></span> | <span data-ttu-id="cf95b-173">Nicht gefunden (404)</span><span class="sxs-lookup"><span data-stu-id="cf95b-173">Not Found (404)</span></span> | <span data-ttu-id="cf95b-174">Ressource \<the requested resource\> wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="cf95b-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="cf95b-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="cf95b-175">InternalServerError</span></span> | <span data-ttu-id="cf95b-176">Interner Serverfehler (500)</span><span class="sxs-lookup"><span data-stu-id="cf95b-176">Internal Server Error (500)</span></span> | <span data-ttu-id="cf95b-177">*Hinweis: Keine Fehlermeldung, wiederholen Sie den Vorgang, oder [wenden Sie sich an Microsoft,](/microsoft-365/business-video/get-help-support) wenn er nicht aufgelöst wird.*</span><span class="sxs-lookup"><span data-stu-id="cf95b-177">*Note: No error message,  retry the operation or [contact Microsoft](/microsoft-365/business-video/get-help-support) if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="cf95b-178">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cf95b-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="cf95b-179">Body parameters</span><span class="sxs-lookup"><span data-stu-id="cf95b-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf95b-180">Bei Body-Parametern wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="cf95b-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="cf95b-181">Wenn ein *InvalidRequestBody-* oder *MissingRequiredParameter-Fehler* auftritt, kann dies durch einen Tippfehler verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="cf95b-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="cf95b-182">Überprüfen Sie die API-Dokumentation, und überprüfen Sie, ob die übermittelten Parameter mit dem entsprechenden Beispiel übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cf95b-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="cf95b-183">Tracking-ID</span><span class="sxs-lookup"><span data-stu-id="cf95b-183">Tracking ID</span></span>

<span data-ttu-id="cf95b-184">Jede Fehlerantwort enthält einen eindeutigen ID-Parameter für die Nachverfolgung.</span><span class="sxs-lookup"><span data-stu-id="cf95b-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="cf95b-185">Der Eigenschaftenname dieses Parameters ist *Ziel.*</span><span class="sxs-lookup"><span data-stu-id="cf95b-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="cf95b-186">Wenn sie uns wegen eines Fehlers kontaktieren, hilft uns das Anhängen dieser ID, die Ursache des Problems zu finden.</span><span class="sxs-lookup"><span data-stu-id="cf95b-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cf95b-187">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="cf95b-187">Related articles</span></span>

- [<span data-ttu-id="cf95b-188">Microsoft 365 Übersicht über Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="cf95b-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="cf95b-189">Unterstützte Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="cf95b-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="cf95b-190">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="cf95b-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="cf95b-191">Informationen zu API-Grenzwerten und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="cf95b-191">Learn about API limits and licensing</span></span>](api-terms.md)

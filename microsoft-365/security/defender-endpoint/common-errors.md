---
title: Häufige Fehler der Microsoft Defender für Endpunkt-API
description: Liste der häufigsten Microsoft Defender für Endpunkt-API-Fehler mit Beschreibungen.
keywords: APIs, Microsoft Defender für Endpunkt-API, Fehler, Problembehandlung
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
ms.openlocfilehash: c2e52b7074dcd15e7f6852a11ccb7793572cd9b5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771009"
---
# <a name="common-rest-api-error-codes"></a><span data-ttu-id="8af65-104">Häufige Rest-API-Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="8af65-104">Common REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* <span data-ttu-id="8af65-105">Die in der folgenden Tabelle aufgeführten Fehlercodes können von einem Vorgang für alle Microsoft Defender für Endpunkt-APIs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8af65-105">The error codes listed in the following table may be returned by an operation on any of Microsoft Defender for Endpoint APIs.</span></span>
* <span data-ttu-id="8af65-106">Zusätzlich zum Fehlercode enthält jede Fehlerantwort eine Fehlermeldung, die bei der Behebung des Problems helfen kann.</span><span class="sxs-lookup"><span data-stu-id="8af65-106">In addition to the error code, every error response contains an error message, which can help resolve the problem.</span></span>
* <span data-ttu-id="8af65-107">Die Nachricht ist ein Freitext, der geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8af65-107">The message is a free text that can be changed.</span></span>
* <span data-ttu-id="8af65-108">Am unteren Rand der Seite finden Sie Antwortbeispiele.</span><span class="sxs-lookup"><span data-stu-id="8af65-108">At the bottom of the page, you can find response examples.</span></span>

><span data-ttu-id="8af65-109">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="8af65-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8af65-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="8af65-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="8af65-111">Fehlercode</span><span class="sxs-lookup"><span data-stu-id="8af65-111">Error code</span></span> |<span data-ttu-id="8af65-112">HTTP-Statuscode</span><span class="sxs-lookup"><span data-stu-id="8af65-112">HTTP status code</span></span> |<span data-ttu-id="8af65-113">Message</span><span class="sxs-lookup"><span data-stu-id="8af65-113">Message</span></span> 
:---|:---|:---
<span data-ttu-id="8af65-114">BadRequest</span><span class="sxs-lookup"><span data-stu-id="8af65-114">BadRequest</span></span> | <span data-ttu-id="8af65-115">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8af65-115">BadRequest (400)</span></span> | <span data-ttu-id="8af65-116">Fehlermeldung "Allgemeine ungültige Anforderung".</span><span class="sxs-lookup"><span data-stu-id="8af65-116">General Bad Request error message.</span></span>
<span data-ttu-id="8af65-117">ODataError</span><span class="sxs-lookup"><span data-stu-id="8af65-117">ODataError</span></span> | <span data-ttu-id="8af65-118">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8af65-118">BadRequest (400)</span></span> | <span data-ttu-id="8af65-119">Ungültige OData-URI-Abfrage (der spezifische Fehler wird angegeben).</span><span class="sxs-lookup"><span data-stu-id="8af65-119">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="8af65-120">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="8af65-120">InvalidInput</span></span> | <span data-ttu-id="8af65-121">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8af65-121">BadRequest (400)</span></span> | <span data-ttu-id="8af65-122">Ungültige Eingabe {die ungültige Eingabe}.</span><span class="sxs-lookup"><span data-stu-id="8af65-122">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="8af65-123">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="8af65-123">InvalidRequestBody</span></span> | <span data-ttu-id="8af65-124">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8af65-124">BadRequest (400)</span></span> | <span data-ttu-id="8af65-125">Ungültiger Anforderungstext.</span><span class="sxs-lookup"><span data-stu-id="8af65-125">Invalid request body.</span></span>
<span data-ttu-id="8af65-126">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="8af65-126">InvalidHashValue</span></span> | <span data-ttu-id="8af65-127">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8af65-127">BadRequest (400)</span></span> | <span data-ttu-id="8af65-128">Der Hashwert {der ungültige Hash} ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="8af65-128">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="8af65-129">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="8af65-129">InvalidDomainName</span></span> | <span data-ttu-id="8af65-130">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8af65-130">BadRequest (400)</span></span> | <span data-ttu-id="8af65-131">Der Domänenname {die ungültige Domäne} ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="8af65-131">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="8af65-132">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="8af65-132">InvalidIpAddress</span></span> | <span data-ttu-id="8af65-133">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8af65-133">BadRequest (400)</span></span> | <span data-ttu-id="8af65-134">Die IP-Adresse {die ungültige IP} ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="8af65-134">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="8af65-135">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="8af65-135">InvalidUrl</span></span> | <span data-ttu-id="8af65-136">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8af65-136">BadRequest (400)</span></span> | <span data-ttu-id="8af65-137">URL {die ungültige URL} ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="8af65-137">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="8af65-138">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="8af65-138">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="8af65-139">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8af65-139">BadRequest (400)</span></span> | <span data-ttu-id="8af65-140">Maximale Batchgröße überschritten.</span><span class="sxs-lookup"><span data-stu-id="8af65-140">Maximum batch size exceeded.</span></span> <span data-ttu-id="8af65-141">Received: {batch size received}, allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="8af65-141">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="8af65-142">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="8af65-142">MissingRequiredParameter</span></span> | <span data-ttu-id="8af65-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8af65-143">BadRequest (400)</span></span> | <span data-ttu-id="8af65-144">Parameter {der fehlende Parameter} fehlt.</span><span class="sxs-lookup"><span data-stu-id="8af65-144">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="8af65-145">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="8af65-145">OsPlatformNotSupported</span></span> | <span data-ttu-id="8af65-146">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8af65-146">BadRequest (400)</span></span> | <span data-ttu-id="8af65-147">Os Platform {the client OS Platform} is not supported for this action.</span><span class="sxs-lookup"><span data-stu-id="8af65-147">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="8af65-148">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="8af65-148">ClientVersionNotSupported</span></span> | <span data-ttu-id="8af65-149">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8af65-149">BadRequest (400)</span></span> | <span data-ttu-id="8af65-150">{Die angeforderte Aktion} wird für Clientversion {unterstützte Clientversion} und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8af65-150">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="8af65-151">Nicht autorisiert (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="8af65-151">Unauthorized</span></span> | <span data-ttu-id="8af65-152">Nicht autorisiert (401)</span><span class="sxs-lookup"><span data-stu-id="8af65-152">Unauthorized (401)</span></span> | <span data-ttu-id="8af65-153">Nicht autorisiert (ungültiger oder abgelaufener Autorisierungsheader).</span><span class="sxs-lookup"><span data-stu-id="8af65-153">Unauthorized (invalid or expired authorization header).</span></span>
<span data-ttu-id="8af65-154">Verboten (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="8af65-154">Forbidden</span></span> | <span data-ttu-id="8af65-155">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="8af65-155">Forbidden (403)</span></span> | <span data-ttu-id="8af65-156">Unzulässig (gültiges Token, aber unzureichende Berechtigung für die Aktion).</span><span class="sxs-lookup"><span data-stu-id="8af65-156">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="8af65-157">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="8af65-157">DisabledFeature</span></span> | <span data-ttu-id="8af65-158">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="8af65-158">Forbidden (403)</span></span> | <span data-ttu-id="8af65-159">Mandantenfunktion ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8af65-159">Tenant feature is not enabled.</span></span>
<span data-ttu-id="8af65-160">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="8af65-160">DisallowedOperation</span></span> | <span data-ttu-id="8af65-161">Forbidden (403)</span><span class="sxs-lookup"><span data-stu-id="8af65-161">Forbidden (403)</span></span> | <span data-ttu-id="8af65-162">{der unzulässige Vorgang und der Grund}.</span><span class="sxs-lookup"><span data-stu-id="8af65-162">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="8af65-163">NotFound</span><span class="sxs-lookup"><span data-stu-id="8af65-163">NotFound</span></span> | <span data-ttu-id="8af65-164">Nicht gefunden (404)</span><span class="sxs-lookup"><span data-stu-id="8af65-164">Not Found (404)</span></span> | <span data-ttu-id="8af65-165">Fehlermeldung "Allgemein nicht gefunden".</span><span class="sxs-lookup"><span data-stu-id="8af65-165">General Not Found error message.</span></span>
<span data-ttu-id="8af65-166">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="8af65-166">ResourceNotFound</span></span> | <span data-ttu-id="8af65-167">Nicht gefunden (404)</span><span class="sxs-lookup"><span data-stu-id="8af65-167">Not Found (404)</span></span> | <span data-ttu-id="8af65-168">Ressource {die angeforderte Ressource} wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="8af65-168">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="8af65-169">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="8af65-169">InternalServerError</span></span> | <span data-ttu-id="8af65-170">Interner Serverfehler (500)</span><span class="sxs-lookup"><span data-stu-id="8af65-170">Internal Server Error (500)</span></span> | <span data-ttu-id="8af65-171">(Keine Fehlermeldung, Vorgang wiederholen)</span><span class="sxs-lookup"><span data-stu-id="8af65-171">(No error message, retry the operation)</span></span>
<span data-ttu-id="8af65-172">TooManyRequests</span><span class="sxs-lookup"><span data-stu-id="8af65-172">TooManyRequests</span></span> | <span data-ttu-id="8af65-173">Zu viele Anforderungen (429)</span><span class="sxs-lookup"><span data-stu-id="8af65-173">Too Many Requests (429)</span></span> | <span data-ttu-id="8af65-174">Die Antwort stellt das Erreichen des Kontingentlimits entweder nach Anzahl der Anforderungen oder nach CPU dar.</span><span class="sxs-lookup"><span data-stu-id="8af65-174">Response will represent reaching quota limit either by number of requests or by CPU.</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="8af65-175">Bei Body-Parametern wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="8af65-175">Body parameters are case-sensitive</span></span>

<span data-ttu-id="8af65-176">Bei den übermittelten Textkörperparametern wird derzeit die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="8af65-176">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="8af65-177">Wenn ein **InvalidRequestBody-** oder **MissingRequiredParameter-Fehler** auftritt, kann dies durch ein falsches Parameterhaupt- oder Kleinbuchstaben verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="8af65-177">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="8af65-178">Überprüfen Sie die API-Dokumentationsseite, und überprüfen Sie, ob die übermittelten Parameter mit dem entsprechenden Beispiel übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8af65-178">Review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="8af65-179">Korrelationsanforderungs-ID</span><span class="sxs-lookup"><span data-stu-id="8af65-179">Correlation request ID</span></span>

<span data-ttu-id="8af65-180">Jede Fehlerantwort enthält einen eindeutigen ID-Parameter für die Nachverfolgung.</span><span class="sxs-lookup"><span data-stu-id="8af65-180">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="8af65-181">Der Eigenschaftenname dieses Parameters lautet "target".</span><span class="sxs-lookup"><span data-stu-id="8af65-181">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="8af65-182">Wenn Sie uns bezüglich eines Fehlers kontaktieren, hilft das Anhängen dieser ID, die Ursache des Problems zu finden.</span><span class="sxs-lookup"><span data-stu-id="8af65-182">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="8af65-183">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8af65-183">Examples</span></span>

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

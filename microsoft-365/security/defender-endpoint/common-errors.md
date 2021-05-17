---
title: Häufige Microsoft Defender für Endpunkt-API-Fehler
description: Liste der häufigen Microsoft Defender for Endpoint-API-Fehler mit Beschreibungen.
keywords: APIs, Microsoft Defender for Endpoint-API, Fehler, Problembehandlung
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
ms.openlocfilehash: 54ae77c28523d3be6092e1567424d2d87a5f2927
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934789"
---
# <a name="common-rest-api-error-codes"></a><span data-ttu-id="bdef8-104">Häufige Rest-API-Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="bdef8-104">Common REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* <span data-ttu-id="bdef8-105">Die in der folgenden Tabelle aufgeführten Fehlercodes können von einem Vorgang für eine beliebige Microsoft Defender for Endpoint-APIs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bdef8-105">The error codes listed in the following table may be returned by an operation on any of Microsoft Defender for Endpoint APIs.</span></span>
* <span data-ttu-id="bdef8-106">Zusätzlich zum Fehlercode enthält jede Fehlerantwort eine Fehlermeldung, mit der das Problem behoben werden kann.</span><span class="sxs-lookup"><span data-stu-id="bdef8-106">In addition to the error code, every error response contains an error message, which can help resolve the problem.</span></span>
* <span data-ttu-id="bdef8-107">Die Nachricht ist ein Freitext, der geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="bdef8-107">The message is a free text that can be changed.</span></span>
* <span data-ttu-id="bdef8-108">Unten auf der Seite finden Sie Antwortbeispiele.</span><span class="sxs-lookup"><span data-stu-id="bdef8-108">At the bottom of the page, you can find response examples.</span></span>

><span data-ttu-id="bdef8-109">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="bdef8-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bdef8-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bdef8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="bdef8-111">Fehlercode</span><span class="sxs-lookup"><span data-stu-id="bdef8-111">Error code</span></span> |<span data-ttu-id="bdef8-112">HTTP-Statuscode</span><span class="sxs-lookup"><span data-stu-id="bdef8-112">HTTP status code</span></span> |<span data-ttu-id="bdef8-113">Message</span><span class="sxs-lookup"><span data-stu-id="bdef8-113">Message</span></span> 
:---|:---|:---
<span data-ttu-id="bdef8-114">BadRequest</span><span class="sxs-lookup"><span data-stu-id="bdef8-114">BadRequest</span></span> | <span data-ttu-id="bdef8-115">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="bdef8-115">BadRequest (400)</span></span> | <span data-ttu-id="bdef8-116">Fehlermeldung "Allgemeine ungültige Anforderung".</span><span class="sxs-lookup"><span data-stu-id="bdef8-116">General Bad Request error message.</span></span>
<span data-ttu-id="bdef8-117">ODataError</span><span class="sxs-lookup"><span data-stu-id="bdef8-117">ODataError</span></span> | <span data-ttu-id="bdef8-118">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="bdef8-118">BadRequest (400)</span></span> | <span data-ttu-id="bdef8-119">Ungültige OData-URI-Abfrage (der spezifische Fehler wird angegeben).</span><span class="sxs-lookup"><span data-stu-id="bdef8-119">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="bdef8-120">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="bdef8-120">InvalidInput</span></span> | <span data-ttu-id="bdef8-121">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="bdef8-121">BadRequest (400)</span></span> | <span data-ttu-id="bdef8-122">Ungültige Eingabe {ungültige Eingabe}.</span><span class="sxs-lookup"><span data-stu-id="bdef8-122">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="bdef8-123">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="bdef8-123">InvalidRequestBody</span></span> | <span data-ttu-id="bdef8-124">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="bdef8-124">BadRequest (400)</span></span> | <span data-ttu-id="bdef8-125">Ungültiger Anforderungstext.</span><span class="sxs-lookup"><span data-stu-id="bdef8-125">Invalid request body.</span></span>
<span data-ttu-id="bdef8-126">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="bdef8-126">InvalidHashValue</span></span> | <span data-ttu-id="bdef8-127">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="bdef8-127">BadRequest (400)</span></span> | <span data-ttu-id="bdef8-128">Der Hashwert {der ungültige Hash} ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="bdef8-128">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="bdef8-129">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="bdef8-129">InvalidDomainName</span></span> | <span data-ttu-id="bdef8-130">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="bdef8-130">BadRequest (400)</span></span> | <span data-ttu-id="bdef8-131">Der Domänenname {die ungültige Domäne} ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="bdef8-131">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="bdef8-132">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="bdef8-132">InvalidIpAddress</span></span> | <span data-ttu-id="bdef8-133">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="bdef8-133">BadRequest (400)</span></span> | <span data-ttu-id="bdef8-134">Die IP-Adresse {die ungültige IP} ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="bdef8-134">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="bdef8-135">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="bdef8-135">InvalidUrl</span></span> | <span data-ttu-id="bdef8-136">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="bdef8-136">BadRequest (400)</span></span> | <span data-ttu-id="bdef8-137">URL {die ungültige URL} ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="bdef8-137">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="bdef8-138">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="bdef8-138">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="bdef8-139">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="bdef8-139">BadRequest (400)</span></span> | <span data-ttu-id="bdef8-140">Die maximale Batchgröße wurde überschritten.</span><span class="sxs-lookup"><span data-stu-id="bdef8-140">Maximum batch size exceeded.</span></span> <span data-ttu-id="bdef8-141">Received: {batch size received}, allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="bdef8-141">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="bdef8-142">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="bdef8-142">MissingRequiredParameter</span></span> | <span data-ttu-id="bdef8-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="bdef8-143">BadRequest (400)</span></span> | <span data-ttu-id="bdef8-144">Parameter {der fehlende Parameter} fehlt.</span><span class="sxs-lookup"><span data-stu-id="bdef8-144">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="bdef8-145">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="bdef8-145">OsPlatformNotSupported</span></span> | <span data-ttu-id="bdef8-146">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="bdef8-146">BadRequest (400)</span></span> | <span data-ttu-id="bdef8-147">Die Betriebssystemplattform {die Clientbetriebssystemplattform} wird für diese Aktion nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bdef8-147">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="bdef8-148">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="bdef8-148">ClientVersionNotSupported</span></span> | <span data-ttu-id="bdef8-149">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="bdef8-149">BadRequest (400)</span></span> | <span data-ttu-id="bdef8-150">{Die angeforderte Aktion} wird für die Clientversion {unterstützte Clientversion} und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bdef8-150">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="bdef8-151">Nicht autorisiert (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="bdef8-151">Unauthorized</span></span> | <span data-ttu-id="bdef8-152">Nicht autorisierter Benutzer (401)</span><span class="sxs-lookup"><span data-stu-id="bdef8-152">Unauthorized (401)</span></span> | <span data-ttu-id="bdef8-153">Nicht autorisiert (ungültiger oder abgelaufener Autorisierungsheader).</span><span class="sxs-lookup"><span data-stu-id="bdef8-153">Unauthorized (invalid or expired authorization header).</span></span>
<span data-ttu-id="bdef8-154">Verboten (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="bdef8-154">Forbidden</span></span> | <span data-ttu-id="bdef8-155">Verboten (403)</span><span class="sxs-lookup"><span data-stu-id="bdef8-155">Forbidden (403)</span></span> | <span data-ttu-id="bdef8-156">Verboten (gültiges Token, aber unzureichende Berechtigung für die Aktion).</span><span class="sxs-lookup"><span data-stu-id="bdef8-156">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="bdef8-157">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="bdef8-157">DisabledFeature</span></span> | <span data-ttu-id="bdef8-158">Verboten (403)</span><span class="sxs-lookup"><span data-stu-id="bdef8-158">Forbidden (403)</span></span> | <span data-ttu-id="bdef8-159">Das Mandantenfeature ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="bdef8-159">Tenant feature is not enabled.</span></span>
<span data-ttu-id="bdef8-160">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="bdef8-160">DisallowedOperation</span></span> | <span data-ttu-id="bdef8-161">Verboten (403)</span><span class="sxs-lookup"><span data-stu-id="bdef8-161">Forbidden (403)</span></span> | <span data-ttu-id="bdef8-162">{der unzulässige Vorgang und der Grund}.</span><span class="sxs-lookup"><span data-stu-id="bdef8-162">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="bdef8-163">NotFound</span><span class="sxs-lookup"><span data-stu-id="bdef8-163">NotFound</span></span> | <span data-ttu-id="bdef8-164">Nicht gefunden (404)</span><span class="sxs-lookup"><span data-stu-id="bdef8-164">Not Found (404)</span></span> | <span data-ttu-id="bdef8-165">Fehlermeldung "Allgemein nicht gefunden".</span><span class="sxs-lookup"><span data-stu-id="bdef8-165">General Not Found error message.</span></span>
<span data-ttu-id="bdef8-166">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="bdef8-166">ResourceNotFound</span></span> | <span data-ttu-id="bdef8-167">Nicht gefunden (404)</span><span class="sxs-lookup"><span data-stu-id="bdef8-167">Not Found (404)</span></span> | <span data-ttu-id="bdef8-168">Ressource {die angeforderte Ressource} wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="bdef8-168">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="bdef8-169">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="bdef8-169">InternalServerError</span></span> | <span data-ttu-id="bdef8-170">Interner Serverfehler (500)</span><span class="sxs-lookup"><span data-stu-id="bdef8-170">Internal Server Error (500)</span></span> | <span data-ttu-id="bdef8-171">(Keine Fehlermeldung, wiederholen Sie den Vorgang)</span><span class="sxs-lookup"><span data-stu-id="bdef8-171">(No error message, retry the operation)</span></span>
<span data-ttu-id="bdef8-172">TooManyRequests</span><span class="sxs-lookup"><span data-stu-id="bdef8-172">TooManyRequests</span></span> | <span data-ttu-id="bdef8-173">Zu viele Anforderungen (429)</span><span class="sxs-lookup"><span data-stu-id="bdef8-173">Too Many Requests (429)</span></span> | <span data-ttu-id="bdef8-174">Die Antwort stellt das Erreichen des Kontingentgrenzwerts entweder nach Anzahl der Anforderungen oder nach CPU dar.</span><span class="sxs-lookup"><span data-stu-id="bdef8-174">Response will represent reaching quota limit either by number of requests or by CPU.</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="bdef8-175">Bei Textparametern wird die Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="bdef8-175">Body parameters are case-sensitive</span></span>

<span data-ttu-id="bdef8-176">Bei den übermittelten Textparametern wird derzeit die Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="bdef8-176">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="bdef8-177">Wenn ein **InvalidRequestBody-** oder **MissingRequiredParameter-Fehler** aufgetreten ist, kann dies durch ein falsches Parameterhaupt- oder Kleinbuchstaben verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="bdef8-177">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="bdef8-178">Überprüfen Sie die Seite API-Dokumentation, und überprüfen Sie, ob die übermittelten Parameter mit dem entsprechenden Beispiel übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="bdef8-178">Review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="bdef8-179">Korrelationsanforderungs-ID</span><span class="sxs-lookup"><span data-stu-id="bdef8-179">Correlation request ID</span></span>

<span data-ttu-id="bdef8-180">Jede Fehlerantwort enthält einen eindeutigen ID-Parameter für die Nachverfolgung.</span><span class="sxs-lookup"><span data-stu-id="bdef8-180">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="bdef8-181">Der Eigenschaftenname dieses Parameters ist "target".</span><span class="sxs-lookup"><span data-stu-id="bdef8-181">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="bdef8-182">Wenn Sie uns über einen Fehler kontaktieren, hilft das Anfügen dieser ID, die Ursache des Problems zu finden.</span><span class="sxs-lookup"><span data-stu-id="bdef8-182">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="bdef8-183">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bdef8-183">Examples</span></span>

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

---
title: Häufige Microsoft Threat Protection-Rest-API-Fehlercodes
description: Erfahren Sie mehr über die allgemeinen Microsoft Threat Protection-Rest-API-Fehlercodes
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
ms.openlocfilehash: 36a1cedacc5f16c422e2b0d458b0d1767cf08b64
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650335"
---
# <a name="common-microsoft-threat-protection-rest-api-error-codes"></a><span data-ttu-id="04928-104">Häufige Microsoft Threat Protection-Rest-API-Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="04928-104">Common Microsoft Threat Protection REST API error codes</span></span>

<span data-ttu-id="04928-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="04928-105">**Applies to:**</span></span>
- <span data-ttu-id="04928-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="04928-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="04928-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="04928-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="04928-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="04928-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="04928-109">Die in der folgenden Tabelle aufgelisteten Fehlercodes werden möglicherweise von einem Vorgang für eine der Microsoft Threat Protection-APIs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="04928-109">The error codes listed in the following table may be returned by an operation on any of Microsoft Threat Protection APIs.</span></span>

<span data-ttu-id="04928-110">Jede Fehlerantwort enthält eine Fehlermeldung, die zur Lösung des Problems beitragen kann.</span><span class="sxs-lookup"><span data-stu-id="04928-110">Every error response contains an error message, which can help resolving the problem.</span></span>

<span data-ttu-id="04928-111">Die Nachricht ist ein freier Text, der geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="04928-111">The message is a free text that can be changed.</span></span>

<span data-ttu-id="04928-112">Unten auf der Seite befinden sich Antwort Beispiele.</span><span class="sxs-lookup"><span data-stu-id="04928-112">At the bottom of the page, you can find response examples.</span></span>

<span data-ttu-id="04928-113">Fehlercode</span><span class="sxs-lookup"><span data-stu-id="04928-113">Error code</span></span> |<span data-ttu-id="04928-114">HTTP-Statuscode</span><span class="sxs-lookup"><span data-stu-id="04928-114">HTTP status code</span></span> |<span data-ttu-id="04928-115">Message</span><span class="sxs-lookup"><span data-stu-id="04928-115">Message</span></span> 
:---|:---|:---
<span data-ttu-id="04928-116">BadRequest</span><span class="sxs-lookup"><span data-stu-id="04928-116">BadRequest</span></span> | <span data-ttu-id="04928-117">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="04928-117">BadRequest (400)</span></span> | <span data-ttu-id="04928-118">Fehlermeldung allgemeine ungültige Anforderung.</span><span class="sxs-lookup"><span data-stu-id="04928-118">General Bad Request error message.</span></span>
<span data-ttu-id="04928-119">ODataError</span><span class="sxs-lookup"><span data-stu-id="04928-119">ODataError</span></span> | <span data-ttu-id="04928-120">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="04928-120">BadRequest (400)</span></span> | <span data-ttu-id="04928-121">Ungültige OData-URI-Abfrage (der spezifische Fehler wird angegeben).</span><span class="sxs-lookup"><span data-stu-id="04928-121">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="04928-122">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="04928-122">InvalidInput</span></span> | <span data-ttu-id="04928-123">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="04928-123">BadRequest (400)</span></span> | <span data-ttu-id="04928-124">Ungültige Eingabe {ungültige Eingabe}.</span><span class="sxs-lookup"><span data-stu-id="04928-124">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="04928-125">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="04928-125">InvalidRequestBody</span></span> | <span data-ttu-id="04928-126">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="04928-126">BadRequest (400)</span></span> | <span data-ttu-id="04928-127">Ungültiger Anforderungstext.</span><span class="sxs-lookup"><span data-stu-id="04928-127">Invalid request body.</span></span>
<span data-ttu-id="04928-128">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="04928-128">InvalidHashValue</span></span> | <span data-ttu-id="04928-129">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="04928-129">BadRequest (400)</span></span> | <span data-ttu-id="04928-130">Der Hashwert {der ungültige Hash} ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="04928-130">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="04928-131">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="04928-131">InvalidDomainName</span></span> | <span data-ttu-id="04928-132">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="04928-132">BadRequest (400)</span></span> | <span data-ttu-id="04928-133">Der Domänenname {ungültige Domäne} ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="04928-133">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="04928-134">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="04928-134">InvalidIpAddress</span></span> | <span data-ttu-id="04928-135">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="04928-135">BadRequest (400)</span></span> | <span data-ttu-id="04928-136">IP-Adresse {Ungültige IP} ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="04928-136">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="04928-137">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="04928-137">InvalidUrl</span></span> | <span data-ttu-id="04928-138">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="04928-138">BadRequest (400)</span></span> | <span data-ttu-id="04928-139">URL {die ungültige URL} ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="04928-139">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="04928-140">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="04928-140">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="04928-141">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="04928-141">BadRequest (400)</span></span> | <span data-ttu-id="04928-142">Maximale Batchgröße überschritten.</span><span class="sxs-lookup"><span data-stu-id="04928-142">Maximum batch size exceeded.</span></span> <span data-ttu-id="04928-143">Empfangen: {Batchgröße empfangen}, zulässig: {Batchgröße zulässig}.</span><span class="sxs-lookup"><span data-stu-id="04928-143">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="04928-144">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="04928-144">MissingRequiredParameter</span></span> | <span data-ttu-id="04928-145">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="04928-145">BadRequest (400)</span></span> | <span data-ttu-id="04928-146">Parameter {der fehlende Parameter} fehlt.</span><span class="sxs-lookup"><span data-stu-id="04928-146">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="04928-147">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="04928-147">OsPlatformNotSupported</span></span> | <span data-ttu-id="04928-148">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="04928-148">BadRequest (400)</span></span> | <span data-ttu-id="04928-149">Betriebssystemplattform {die Client Betriebssystem-Plattform} wird für diese Aktion nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="04928-149">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="04928-150">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="04928-150">ClientVersionNotSupported</span></span> | <span data-ttu-id="04928-151">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="04928-151">BadRequest (400)</span></span> | <span data-ttu-id="04928-152">{Die angeforderte Aktion} wird auf Client Version {unterstützte Client Version} und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="04928-152">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="04928-153">Nicht autorisiert (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="04928-153">Unauthorized</span></span> | <span data-ttu-id="04928-154">Nicht autorisiert (401)</span><span class="sxs-lookup"><span data-stu-id="04928-154">Unauthorized (401)</span></span> | <span data-ttu-id="04928-155">Nicht autorisiert (in der Regel ungültige oder abgelaufene Autorisierungs Kopfzeile).</span><span class="sxs-lookup"><span data-stu-id="04928-155">Unauthorized (usually invalid or expired authorization header).</span></span>
<span data-ttu-id="04928-156">Verboten (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="04928-156">Forbidden</span></span> | <span data-ttu-id="04928-157">Unzulässig (403)</span><span class="sxs-lookup"><span data-stu-id="04928-157">Forbidden (403)</span></span> | <span data-ttu-id="04928-158">Unzulässig (gültiges Token, jedoch unzureichende Berechtigung für die Aktion).</span><span class="sxs-lookup"><span data-stu-id="04928-158">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="04928-159">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="04928-159">DisabledFeature</span></span> | <span data-ttu-id="04928-160">Unzulässig (403)</span><span class="sxs-lookup"><span data-stu-id="04928-160">Forbidden (403)</span></span> | <span data-ttu-id="04928-161">Das Mandanten Feature ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="04928-161">Tenant feature is not enabled.</span></span>
<span data-ttu-id="04928-162">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="04928-162">DisallowedOperation</span></span> | <span data-ttu-id="04928-163">Unzulässig (403)</span><span class="sxs-lookup"><span data-stu-id="04928-163">Forbidden (403)</span></span> | <span data-ttu-id="04928-164">{der nicht zulässige Vorgang und der Grund}.</span><span class="sxs-lookup"><span data-stu-id="04928-164">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="04928-165">NotFound</span><span class="sxs-lookup"><span data-stu-id="04928-165">NotFound</span></span> | <span data-ttu-id="04928-166">Nicht gefunden (404)</span><span class="sxs-lookup"><span data-stu-id="04928-166">Not Found (404)</span></span> | <span data-ttu-id="04928-167">Fehlermeldung "allgemeine nicht gefunden".</span><span class="sxs-lookup"><span data-stu-id="04928-167">General Not Found error message.</span></span>
<span data-ttu-id="04928-168">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="04928-168">ResourceNotFound</span></span> | <span data-ttu-id="04928-169">Nicht gefunden (404)</span><span class="sxs-lookup"><span data-stu-id="04928-169">Not Found (404)</span></span> | <span data-ttu-id="04928-170">Resource {die angeforderte Ressource} wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="04928-170">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="04928-171">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="04928-171">InternalServerError</span></span> | <span data-ttu-id="04928-172">Interner Server Fehler (500)</span><span class="sxs-lookup"><span data-stu-id="04928-172">Internal Server Error (500)</span></span> | <span data-ttu-id="04928-173">(Keine Fehlermeldung, wiederholen Sie den Vorgang, oder kontaktieren Sie uns, wenn er nicht aufgelöst wird)</span><span class="sxs-lookup"><span data-stu-id="04928-173">(No error message,  retry the operation or contact us if it does not get resolved)</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="04928-174">Bei den textparametern wird die Groß-/Kleinschreibung beachtet</span><span class="sxs-lookup"><span data-stu-id="04928-174">Body parameters are case-sensitive</span></span>

<span data-ttu-id="04928-175">Bei den übermittelten textparametern wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="04928-175">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="04928-176">Wenn ein **InvalidRequestBody** -oder **MissingRequiredParameter** -Fehler auftritt, kann dies auf einen falschen Parameter Capital oder einen Kleinbuchstaben zurückzuführen sein.</span><span class="sxs-lookup"><span data-stu-id="04928-176">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="04928-177">Es wird empfohlen, die API-Dokumentationsseite zu überprüfen und zu überprüfen, ob die übermittelten Parameter mit dem entsprechenden Beispiel übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="04928-177">We recommend that you review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="04928-178">Korrelations Anforderungs-ID</span><span class="sxs-lookup"><span data-stu-id="04928-178">Correlation request ID</span></span>

<span data-ttu-id="04928-179">Jede Fehlerantwort enthält einen eindeutigen ID-Parameter für die Nachverfolgung.</span><span class="sxs-lookup"><span data-stu-id="04928-179">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="04928-180">Der Eigenschaften Name dieses Parameters lautet "target".</span><span class="sxs-lookup"><span data-stu-id="04928-180">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="04928-181">Wenn Sie uns über einen Fehler kontaktieren, wird das Anfügen dieser ID dazu beitragen, die Ursache des Problems zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="04928-181">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="04928-182">Beispiele</span><span class="sxs-lookup"><span data-stu-id="04928-182">Examples</span></span>

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


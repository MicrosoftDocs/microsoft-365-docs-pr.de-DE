---
title: BatchDelete
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Verwenden Sie die REST-API, um ein angewendetes Dokumentverständnismodell von einer oder mehreren Bibliotheken zu entfernen.
ms.openlocfilehash: e95c0583b1b0e2f5de08228afbf161c339544047
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177237"
---
# <a name="batchdelete"></a><span data-ttu-id="fb9b4-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="fb9b4-103">BatchDelete</span></span>

<span data-ttu-id="fb9b4-104">Entfernt ein angewendetes Dokumentverständnismodell von einer oder mehreren Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="fb9b4-105">Beachten Sie, dass das Modell von allen Bibliotheken entfernt werden muss, bevor es gelöscht werden kann (siehe [Beispiel](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="fb9b4-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="fb9b4-106">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="fb9b4-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="fb9b4-107">URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="fb9b4-107">URI parameters</span></span>

<span data-ttu-id="fb9b4-108">Keine</span><span class="sxs-lookup"><span data-stu-id="fb9b4-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="fb9b4-109">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="fb9b4-109">Request headers</span></span>

| <span data-ttu-id="fb9b4-110">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="fb9b4-110">Header</span></span> | <span data-ttu-id="fb9b4-111">Wert</span><span class="sxs-lookup"><span data-stu-id="fb9b4-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="fb9b4-112">Annehmen</span><span class="sxs-lookup"><span data-stu-id="fb9b4-112">Accept</span></span>|<span data-ttu-id="fb9b4-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="fb9b4-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="fb9b4-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="fb9b4-114">Content-Type</span></span>|<span data-ttu-id="fb9b4-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="fb9b4-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="fb9b4-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="fb9b4-116">x-requestdigest</span></span>|<span data-ttu-id="fb9b4-117">Der entsprechende Digest für die aktuelle Website.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="fb9b4-118">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="fb9b4-118">Request body</span></span>

| <span data-ttu-id="fb9b4-119">Name</span><span class="sxs-lookup"><span data-stu-id="fb9b4-119">Name</span></span> | <span data-ttu-id="fb9b4-120">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="fb9b4-120">Required</span></span> | <span data-ttu-id="fb9b4-121">Typ</span><span class="sxs-lookup"><span data-stu-id="fb9b4-121">Type</span></span> | <span data-ttu-id="fb9b4-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb9b4-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="fb9b4-123">Publikationen</span><span class="sxs-lookup"><span data-stu-id="fb9b4-123">Publications</span></span>|<span data-ttu-id="fb9b4-124">ja</span><span class="sxs-lookup"><span data-stu-id="fb9b4-124">yes</span></span>|<span data-ttu-id="fb9b4-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="fb9b4-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="fb9b4-126">Die Sammlung von MachineLearningPublicationEntityData, von denen jedes Element das Modell und die Zieldokumentbibliothek angibt.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="fb9b4-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="fb9b4-127">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="fb9b4-128">Name</span><span class="sxs-lookup"><span data-stu-id="fb9b4-128">Name</span></span> | <span data-ttu-id="fb9b4-129">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="fb9b4-129">Required</span></span> | <span data-ttu-id="fb9b4-130">Typ</span><span class="sxs-lookup"><span data-stu-id="fb9b4-130">Type</span></span> | <span data-ttu-id="fb9b4-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb9b4-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="fb9b4-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="fb9b4-132">ModelUniqueId</span></span>|<span data-ttu-id="fb9b4-133">ja</span><span class="sxs-lookup"><span data-stu-id="fb9b4-133">yes</span></span>|<span data-ttu-id="fb9b4-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fb9b4-134">string</span></span>|<span data-ttu-id="fb9b4-135">Die eindeutige ID der Modelldatei.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="fb9b4-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="fb9b4-136">TargetSiteUrl</span></span>|<span data-ttu-id="fb9b4-137">ja</span><span class="sxs-lookup"><span data-stu-id="fb9b4-137">yes</span></span>|<span data-ttu-id="fb9b4-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fb9b4-138">string</span></span>|<span data-ttu-id="fb9b4-139">Die vollständige URL der Zielbibliothekswebsite.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="fb9b4-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="fb9b4-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="fb9b4-141">ja</span><span class="sxs-lookup"><span data-stu-id="fb9b4-141">yes</span></span>|<span data-ttu-id="fb9b4-142">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fb9b4-142">string</span></span>|<span data-ttu-id="fb9b4-143">Die relative Server-URL aus dem Web für die Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="fb9b4-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="fb9b4-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="fb9b4-145">ja</span><span class="sxs-lookup"><span data-stu-id="fb9b4-145">yes</span></span>|<span data-ttu-id="fb9b4-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fb9b4-146">string</span></span>|<span data-ttu-id="fb9b4-147">Die relative Server-URL der Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="fb9b4-148">Antwort</span><span class="sxs-lookup"><span data-stu-id="fb9b4-148">Response</span></span>

| <span data-ttu-id="fb9b4-149">Name</span><span class="sxs-lookup"><span data-stu-id="fb9b4-149">Name</span></span>   | <span data-ttu-id="fb9b4-150">Typ</span><span class="sxs-lookup"><span data-stu-id="fb9b4-150">Type</span></span>  | <span data-ttu-id="fb9b4-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb9b4-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="fb9b4-152">200 OK</span><span class="sxs-lookup"><span data-stu-id="fb9b4-152">200 OK</span></span>||<span data-ttu-id="fb9b4-153">Dies ist ein benutzerdefiniertes API, um das Entfernen eines Modells aus einer Mehrfach-Dokumentbibliothek zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-153">This is a customized API to support removing a model from multi document libraries.</span></span> <span data-ttu-id="fb9b4-154">Im Falle eines Teilerfolgs könnte immer noch „200 OK“ zurückgegeben werden und der Aufrufer muss den Antworttext untersuchen, um zu verstehen, ob das Modell erfolgreich aus einer Dokumentbibliothek entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-154">In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="fb9b4-155">Antworttext</span><span class="sxs-lookup"><span data-stu-id="fb9b4-155">Response Body</span></span>
| <span data-ttu-id="fb9b4-156">Name</span><span class="sxs-lookup"><span data-stu-id="fb9b4-156">Name</span></span>   | <span data-ttu-id="fb9b4-157">Typ</span><span class="sxs-lookup"><span data-stu-id="fb9b4-157">Type</span></span>  | <span data-ttu-id="fb9b4-158">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb9b4-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="fb9b4-159">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="fb9b4-159">TotalSuccesses</span></span>|<span data-ttu-id="fb9b4-160">Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="fb9b4-160">int</span></span>|<span data-ttu-id="fb9b4-161">Die Gesamtzahl eines Modells, das erfolgreich aus einer Dokumentbibliothek entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="fb9b4-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="fb9b4-162">TotalFailures</span></span>|<span data-ttu-id="fb9b4-163">Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="fb9b4-163">int</span></span>|<span data-ttu-id="fb9b4-164">Die Gesamtzahl eines Modells, das nicht aus einer Dokumentbibliothek entfernt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="fb9b4-165">Details</span><span class="sxs-lookup"><span data-stu-id="fb9b4-165">Details</span></span>|<span data-ttu-id="fb9b4-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="fb9b4-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="fb9b4-167">Die Sammlung von MachineLearningPublicationResult, von denen jedes Element das detaillierte Ergebnis der Entfernung des Modells aus der Dokumentbibliothek angibt.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="fb9b4-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="fb9b4-168">MachineLearningPublicationResult</span></span>
| <span data-ttu-id="fb9b4-169">Name</span><span class="sxs-lookup"><span data-stu-id="fb9b4-169">Name</span></span>   | <span data-ttu-id="fb9b4-170">Typ</span><span class="sxs-lookup"><span data-stu-id="fb9b4-170">Type</span></span>  | <span data-ttu-id="fb9b4-171">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb9b4-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="fb9b4-172">StatusCode</span><span class="sxs-lookup"><span data-stu-id="fb9b4-172">StatusCode</span></span>|<span data-ttu-id="fb9b4-173">Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="fb9b4-173">int</span></span>|<span data-ttu-id="fb9b4-174">Der HTTP-Statuscode.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-174">The HTTP status code.</span></span>|
|<span data-ttu-id="fb9b4-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="fb9b4-175">ErrorMessage</span></span>|<span data-ttu-id="fb9b4-176">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fb9b4-176">string</span></span>|<span data-ttu-id="fb9b4-177">Die Fehlermeldung, welche erläutert, was beim Anwenden des Modells auf die Dokumentbibliothek falsch ist.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="fb9b4-178">Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="fb9b4-178">Publication</span></span>|<span data-ttu-id="fb9b4-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="fb9b4-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="fb9b4-180">Es gibt die Modellinformation und die Zieldokumentbibliothek an.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="fb9b4-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="fb9b4-181">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="fb9b4-182">Name</span><span class="sxs-lookup"><span data-stu-id="fb9b4-182">Name</span></span> | <span data-ttu-id="fb9b4-183">Typ</span><span class="sxs-lookup"><span data-stu-id="fb9b4-183">Type</span></span> | <span data-ttu-id="fb9b4-184">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb9b4-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="fb9b4-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="fb9b4-185">ModelUniqueId</span></span>|<span data-ttu-id="fb9b4-186">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fb9b4-186">string</span></span>|<span data-ttu-id="fb9b4-187">Die eindeutige ID der Modelldatei.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="fb9b4-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="fb9b4-188">TargetSiteUrl</span></span>|<span data-ttu-id="fb9b4-189">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fb9b4-189">string</span></span>|<span data-ttu-id="fb9b4-190">Die vollständige URL der Zielbibliothekswebsite.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="fb9b4-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="fb9b4-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="fb9b4-192">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fb9b4-192">string</span></span>|<span data-ttu-id="fb9b4-193">Die relative Server-URL aus dem Web für die Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="fb9b4-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="fb9b4-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="fb9b4-195">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fb9b4-195">string</span></span>|<span data-ttu-id="fb9b4-196">Die relative Server-URL der Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="fb9b4-197">Beispiele</span><span class="sxs-lookup"><span data-stu-id="fb9b4-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="fb9b4-198">Entfernen eines Modells aus der Vertragsdokumentbibliothek in der Repository-Website</span><span class="sxs-lookup"><span data-stu-id="fb9b4-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="fb9b4-199">In diesem Beispiel lautet die ID des Dokumentverständnismodells für den Contoso-Vertrag `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="fb9b4-200">Beispielanfrage</span><span class="sxs-lookup"><span data-stu-id="fb9b4-200">Sample request</span></span>

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```


#### <a name="sample-response"></a><span data-ttu-id="fb9b4-201">Beispielantwort</span><span class="sxs-lookup"><span data-stu-id="fb9b4-201">Sample response</span></span>

<span data-ttu-id="fb9b4-202">In der Antwort beziehen sich TotalFailures und TotalSuccesses auf die Anzahl der Fehlschläge und Erfolge des Modells, das aus den angegebenen Bibliotheken entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="fb9b4-203">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="fb9b4-203">**Status code:** 200</span></span>

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="fb9b4-204">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb9b4-204">See also</span></span>

[<span data-ttu-id="fb9b4-205">Syntex-Dokumentverständnismodell-REST-API</span><span class="sxs-lookup"><span data-stu-id="fb9b4-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)

---
title: Modell mit Batch anwenden
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
description: Verwenden Sie die REST-API, um ein Dokumentverständnismodell auf eine oder mehrere Bibliotheken anzuwenden.
ms.openlocfilehash: 24ea9a480bc3ce5a7745857de17a6fab6ed97685
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177261"
---
# <a name="batch-apply-model"></a><span data-ttu-id="2c1de-103">Modell mit Batch anwenden</span><span class="sxs-lookup"><span data-stu-id="2c1de-103">Batch Apply model</span></span>

<span data-ttu-id="2c1de-104">Wendet ein trainiertes Dokumentverständnismodell auf eine oder mehrere Bibliotheken an (oder synchronisiert es) (siehe [Beispiel](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="2c1de-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="2c1de-105">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="2c1de-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="2c1de-106">URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="2c1de-106">URI parameters</span></span>

<span data-ttu-id="2c1de-107">Keine</span><span class="sxs-lookup"><span data-stu-id="2c1de-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="2c1de-108">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="2c1de-108">Request headers</span></span>

| <span data-ttu-id="2c1de-109">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="2c1de-109">Header</span></span> | <span data-ttu-id="2c1de-110">Wert</span><span class="sxs-lookup"><span data-stu-id="2c1de-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="2c1de-111">Annehmen</span><span class="sxs-lookup"><span data-stu-id="2c1de-111">Accept</span></span>|<span data-ttu-id="2c1de-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="2c1de-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="2c1de-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="2c1de-113">Content-Type</span></span>|<span data-ttu-id="2c1de-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="2c1de-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="2c1de-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="2c1de-115">x-requestdigest</span></span>|<span data-ttu-id="2c1de-116">Der entsprechende Digest für die aktuelle Website.</span><span class="sxs-lookup"><span data-stu-id="2c1de-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="2c1de-117">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="2c1de-117">Request body</span></span>

| <span data-ttu-id="2c1de-118">Name</span><span class="sxs-lookup"><span data-stu-id="2c1de-118">Name</span></span> | <span data-ttu-id="2c1de-119">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2c1de-119">Required</span></span> | <span data-ttu-id="2c1de-120">Typ</span><span class="sxs-lookup"><span data-stu-id="2c1de-120">Type</span></span> | <span data-ttu-id="2c1de-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c1de-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="2c1de-122">__metadata</span><span class="sxs-lookup"><span data-stu-id="2c1de-122">__metadata</span></span>|<span data-ttu-id="2c1de-123">ja</span><span class="sxs-lookup"><span data-stu-id="2c1de-123">yes</span></span>|<span data-ttu-id="2c1de-124">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c1de-124">string</span></span>|<span data-ttu-id="2c1de-125">Festlegen der Objekt-Metadaten auf dem SPO.</span><span class="sxs-lookup"><span data-stu-id="2c1de-125">Set the object meta on the SPO.</span></span> <span data-ttu-id="2c1de-126">Verwenden Sie immer den Wert: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="2c1de-126">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span></span>|
|<span data-ttu-id="2c1de-127">Publikationen</span><span class="sxs-lookup"><span data-stu-id="2c1de-127">Publications</span></span>|<span data-ttu-id="2c1de-128">ja</span><span class="sxs-lookup"><span data-stu-id="2c1de-128">yes</span></span>|<span data-ttu-id="2c1de-129">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="2c1de-129">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="2c1de-130">Die Sammlung von MachineLearningPublicationEntityData, von denen jedes Element das Modell und die Zieldokumentbibliothek angibt.</span><span class="sxs-lookup"><span data-stu-id="2c1de-130">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="2c1de-131">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="2c1de-131">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="2c1de-132">Name</span><span class="sxs-lookup"><span data-stu-id="2c1de-132">Name</span></span> | <span data-ttu-id="2c1de-133">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2c1de-133">Required</span></span> | <span data-ttu-id="2c1de-134">Typ</span><span class="sxs-lookup"><span data-stu-id="2c1de-134">Type</span></span> | <span data-ttu-id="2c1de-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c1de-135">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="2c1de-136">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="2c1de-136">ModelUniqueId</span></span>|<span data-ttu-id="2c1de-137">ja</span><span class="sxs-lookup"><span data-stu-id="2c1de-137">yes</span></span>|<span data-ttu-id="2c1de-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c1de-138">string</span></span>|<span data-ttu-id="2c1de-139">Die eindeutige ID der Modelldatei.</span><span class="sxs-lookup"><span data-stu-id="2c1de-139">The unique ID of the model file.</span></span>|
|<span data-ttu-id="2c1de-140">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="2c1de-140">TargetSiteUrl</span></span>|<span data-ttu-id="2c1de-141">ja</span><span class="sxs-lookup"><span data-stu-id="2c1de-141">yes</span></span>|<span data-ttu-id="2c1de-142">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c1de-142">string</span></span>|<span data-ttu-id="2c1de-143">Die vollständige URL der Zielbibliothekswebsite.</span><span class="sxs-lookup"><span data-stu-id="2c1de-143">The full URL of the target library site.</span></span>|
|<span data-ttu-id="2c1de-144">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="2c1de-144">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="2c1de-145">ja</span><span class="sxs-lookup"><span data-stu-id="2c1de-145">yes</span></span>|<span data-ttu-id="2c1de-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c1de-146">string</span></span>|<span data-ttu-id="2c1de-147">Die relative Server-URL aus dem Web für die Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="2c1de-147">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="2c1de-148">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="2c1de-148">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="2c1de-149">ja</span><span class="sxs-lookup"><span data-stu-id="2c1de-149">yes</span></span>|<span data-ttu-id="2c1de-150">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c1de-150">string</span></span>|<span data-ttu-id="2c1de-151">Die relative Server-URL der Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="2c1de-151">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="2c1de-152">ViewOption</span><span class="sxs-lookup"><span data-stu-id="2c1de-152">ViewOption</span></span>|<span data-ttu-id="2c1de-153">Nein</span><span class="sxs-lookup"><span data-stu-id="2c1de-153">no</span></span>|<span data-ttu-id="2c1de-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c1de-154">string</span></span>|<span data-ttu-id="2c1de-155">Gibt an, ob die Ansicht „neues Modell“ als Bibliotheksstandard festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2c1de-155">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="2c1de-156">Antwort</span><span class="sxs-lookup"><span data-stu-id="2c1de-156">Response</span></span>

| <span data-ttu-id="2c1de-157">Name</span><span class="sxs-lookup"><span data-stu-id="2c1de-157">Name</span></span>   | <span data-ttu-id="2c1de-158">Typ</span><span class="sxs-lookup"><span data-stu-id="2c1de-158">Type</span></span>  | <span data-ttu-id="2c1de-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c1de-159">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="2c1de-160">201 Erstellt</span><span class="sxs-lookup"><span data-stu-id="2c1de-160">201 Created</span></span>||<span data-ttu-id="2c1de-161">Dies ist ein benutzerdefiniertes API zur Unterstützung der Anwendung eines Modells auf Mehrfach-Dokumentbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="2c1de-161">This is a customized API to support applying a model to multi document libraries.</span></span> <span data-ttu-id="2c1de-162">Im Falle eines Teilerfolgs könnte immer noch „201 erstellt“ zurückgegeben werden und der Aufrufer muss den Antworttext untersuchen, um zu verstehen, ob das Modell erfolgreich auf eine Dokumentbibliothek angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2c1de-162">In the case of partial success, 201 created could still be returned and the caller needs to inspect the response body to understand if the model has been successfully applied to a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="2c1de-163">Antworttext</span><span class="sxs-lookup"><span data-stu-id="2c1de-163">Response Body</span></span>
| <span data-ttu-id="2c1de-164">Name</span><span class="sxs-lookup"><span data-stu-id="2c1de-164">Name</span></span>   | <span data-ttu-id="2c1de-165">Typ</span><span class="sxs-lookup"><span data-stu-id="2c1de-165">Type</span></span>  | <span data-ttu-id="2c1de-166">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c1de-166">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="2c1de-167">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="2c1de-167">TotalSuccesses</span></span>|<span data-ttu-id="2c1de-168">Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="2c1de-168">int</span></span>|<span data-ttu-id="2c1de-169">Die Gesamtzahl eines Modells, das erfolgreich auf eine Dokumentbibliothek angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2c1de-169">The total number of a model being successfully applied to a document library.</span></span>|
|<span data-ttu-id="2c1de-170">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="2c1de-170">TotalFailures</span></span>|<span data-ttu-id="2c1de-171">Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="2c1de-171">int</span></span>|<span data-ttu-id="2c1de-172">Die Gesamtzahl eines Modells, das nicht auf eine Dokumentbibliothek angewendet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="2c1de-172">The total number of a model failing to be applied to a document library.</span></span>|
|<span data-ttu-id="2c1de-173">Details</span><span class="sxs-lookup"><span data-stu-id="2c1de-173">Details</span></span>|<span data-ttu-id="2c1de-174">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="2c1de-174">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="2c1de-175">Sie Sammlung von MachineLearningPublicationResult, von denen jedes Element das detaillierte Ergebnis der Anwendung des Modells in der Dokumentbibliothek angibt.</span><span class="sxs-lookup"><span data-stu-id="2c1de-175">The collection of MachineLearningPublicationResult each of which specifies the detailed result of applying the model to the document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="2c1de-176">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="2c1de-176">MachineLearningPublicationResult</span></span>
| <span data-ttu-id="2c1de-177">Name</span><span class="sxs-lookup"><span data-stu-id="2c1de-177">Name</span></span>   | <span data-ttu-id="2c1de-178">Typ</span><span class="sxs-lookup"><span data-stu-id="2c1de-178">Type</span></span>  | <span data-ttu-id="2c1de-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c1de-179">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="2c1de-180">StatusCode</span><span class="sxs-lookup"><span data-stu-id="2c1de-180">StatusCode</span></span>|<span data-ttu-id="2c1de-181">Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="2c1de-181">int</span></span>|<span data-ttu-id="2c1de-182">Der HTTP-Statuscode.</span><span class="sxs-lookup"><span data-stu-id="2c1de-182">The HTTP status code.</span></span>|
|<span data-ttu-id="2c1de-183">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="2c1de-183">ErrorMessage</span></span>|<span data-ttu-id="2c1de-184">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c1de-184">string</span></span>|<span data-ttu-id="2c1de-185">Die Fehlermeldung, welche erläutert, was beim Anwenden des Modells auf die Dokumentbibliothek falsch ist.</span><span class="sxs-lookup"><span data-stu-id="2c1de-185">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="2c1de-186">Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="2c1de-186">Publication</span></span>|<span data-ttu-id="2c1de-187">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="2c1de-187">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="2c1de-188">Es gibt die Modellinformation und die Zieldokumentbibliothek an.</span><span class="sxs-lookup"><span data-stu-id="2c1de-188">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="2c1de-189">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="2c1de-189">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="2c1de-190">Name</span><span class="sxs-lookup"><span data-stu-id="2c1de-190">Name</span></span> | <span data-ttu-id="2c1de-191">Typ</span><span class="sxs-lookup"><span data-stu-id="2c1de-191">Type</span></span> | <span data-ttu-id="2c1de-192">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c1de-192">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="2c1de-193">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="2c1de-193">ModelUniqueId</span></span>|<span data-ttu-id="2c1de-194">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c1de-194">string</span></span>|<span data-ttu-id="2c1de-195">Die eindeutige ID der Modelldatei.</span><span class="sxs-lookup"><span data-stu-id="2c1de-195">The unique ID of the model file.</span></span>|
|<span data-ttu-id="2c1de-196">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="2c1de-196">TargetSiteUrl</span></span>|<span data-ttu-id="2c1de-197">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c1de-197">string</span></span>|<span data-ttu-id="2c1de-198">Die vollständige URL der Zielbibliothekswebsite.</span><span class="sxs-lookup"><span data-stu-id="2c1de-198">The full URL of the target library site.</span></span>|
|<span data-ttu-id="2c1de-199">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="2c1de-199">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="2c1de-200">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c1de-200">string</span></span>|<span data-ttu-id="2c1de-201">Die relative Server-URL aus dem Web für die Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="2c1de-201">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="2c1de-202">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="2c1de-202">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="2c1de-203">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c1de-203">string</span></span>|<span data-ttu-id="2c1de-204">Die relative Server-URL der Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="2c1de-204">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="2c1de-205">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2c1de-205">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="2c1de-206">Anwenden eines Modells auf die Vertragsdokumentbibliothek in der Repository-Website</span><span class="sxs-lookup"><span data-stu-id="2c1de-206">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="2c1de-207">In diesem Beispiel lautet die ID des Dokumentverständnismodells für den Contoso-Vertrag `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="2c1de-207">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="2c1de-208">Beispielanfrage</span><span class="sxs-lookup"><span data-stu-id="2c1de-208">Sample request</span></span>

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a><span data-ttu-id="2c1de-209">Beispielantwort</span><span class="sxs-lookup"><span data-stu-id="2c1de-209">Sample response</span></span>

<span data-ttu-id="2c1de-210">In der Antwort beziehen sich TotalFailures und TotalSuccesses auf die Anzahl der Fehlschläge und Erfolge des Modells, das auf die angegebenen Bibliotheken angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2c1de-210">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="2c1de-211">**Statuscode:** 201</span><span class="sxs-lookup"><span data-stu-id="2c1de-211">**Status code:** 201</span></span>

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="2c1de-212">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c1de-212">See also</span></span>

[<span data-ttu-id="2c1de-213">Syntex-Dokumentverständnismodell-REST-API</span><span class="sxs-lookup"><span data-stu-id="2c1de-213">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)

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
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286537"
---
# <a name="batch-apply-model"></a><span data-ttu-id="5b2b6-103">Modell mit Batch anwenden</span><span class="sxs-lookup"><span data-stu-id="5b2b6-103">Batch Apply model</span></span>

<span data-ttu-id="5b2b6-104">Wendet ein trainiertes Dokumentverständnismodell auf eine oder mehrere Bibliotheken an (oder synchronisiert es) (siehe [Beispiel](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="5b2b6-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="5b2b6-105">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="5b2b6-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="5b2b6-106">URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="5b2b6-106">URI parameters</span></span>

<span data-ttu-id="5b2b6-107">Keine</span><span class="sxs-lookup"><span data-stu-id="5b2b6-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="5b2b6-108">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="5b2b6-108">Request headers</span></span>

| <span data-ttu-id="5b2b6-109">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="5b2b6-109">Header</span></span> | <span data-ttu-id="5b2b6-110">Wert</span><span class="sxs-lookup"><span data-stu-id="5b2b6-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="5b2b6-111">Annehmen</span><span class="sxs-lookup"><span data-stu-id="5b2b6-111">Accept</span></span>|<span data-ttu-id="5b2b6-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="5b2b6-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="5b2b6-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="5b2b6-113">Content-Type</span></span>|<span data-ttu-id="5b2b6-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="5b2b6-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="5b2b6-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="5b2b6-115">x-requestdigest</span></span>|<span data-ttu-id="5b2b6-116">Der entsprechende Digest für die aktuelle Website.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="5b2b6-117">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="5b2b6-117">Request body</span></span>

| <span data-ttu-id="5b2b6-118">Name</span><span class="sxs-lookup"><span data-stu-id="5b2b6-118">Name</span></span> | <span data-ttu-id="5b2b6-119">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="5b2b6-119">Required</span></span> | <span data-ttu-id="5b2b6-120">Typ</span><span class="sxs-lookup"><span data-stu-id="5b2b6-120">Type</span></span> | <span data-ttu-id="5b2b6-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b2b6-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="5b2b6-122">__metadata</span><span class="sxs-lookup"><span data-stu-id="5b2b6-122">__metadata</span></span>|<span data-ttu-id="5b2b6-123">ja</span><span class="sxs-lookup"><span data-stu-id="5b2b6-123">yes</span></span>|<span data-ttu-id="5b2b6-124">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b2b6-124">string</span></span>|<span data-ttu-id="5b2b6-125">Festlegen der Objekt-Metadaten auf dem SPO.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-125">Set the object meta on the SPO.</span></span> <span data-ttu-id="5b2b6-126">Verwenden Sie immer den Wert: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-126">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span></span>|
|<span data-ttu-id="5b2b6-127">Publikationen</span><span class="sxs-lookup"><span data-stu-id="5b2b6-127">Publications</span></span>|<span data-ttu-id="5b2b6-128">ja</span><span class="sxs-lookup"><span data-stu-id="5b2b6-128">yes</span></span>|<span data-ttu-id="5b2b6-129">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="5b2b6-129">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="5b2b6-130">Die Sammlung von MachineLearningPublicationEntityData, von denen jedes Element das Modell und die Zieldokumentbibliothek angibt.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-130">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="5b2b6-131">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="5b2b6-131">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="5b2b6-132">Name</span><span class="sxs-lookup"><span data-stu-id="5b2b6-132">Name</span></span> | <span data-ttu-id="5b2b6-133">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="5b2b6-133">Required</span></span> | <span data-ttu-id="5b2b6-134">Typ</span><span class="sxs-lookup"><span data-stu-id="5b2b6-134">Type</span></span> | <span data-ttu-id="5b2b6-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b2b6-135">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="5b2b6-136">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="5b2b6-136">ModelUniqueId</span></span>|<span data-ttu-id="5b2b6-137">ja</span><span class="sxs-lookup"><span data-stu-id="5b2b6-137">yes</span></span>|<span data-ttu-id="5b2b6-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b2b6-138">string</span></span>|<span data-ttu-id="5b2b6-139">Die eindeutige ID der Modelldatei.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-139">The unique ID of the model file.</span></span>|
|<span data-ttu-id="5b2b6-140">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="5b2b6-140">TargetSiteUrl</span></span>|<span data-ttu-id="5b2b6-141">ja</span><span class="sxs-lookup"><span data-stu-id="5b2b6-141">yes</span></span>|<span data-ttu-id="5b2b6-142">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b2b6-142">string</span></span>|<span data-ttu-id="5b2b6-143">Die vollständige URL der Zielbibliothekswebsite.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-143">The full URL of the target library site.</span></span>|
|<span data-ttu-id="5b2b6-144">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="5b2b6-144">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="5b2b6-145">ja</span><span class="sxs-lookup"><span data-stu-id="5b2b6-145">yes</span></span>|<span data-ttu-id="5b2b6-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b2b6-146">string</span></span>|<span data-ttu-id="5b2b6-147">Die relative Server-URL aus dem Web für die Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-147">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="5b2b6-148">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="5b2b6-148">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="5b2b6-149">ja</span><span class="sxs-lookup"><span data-stu-id="5b2b6-149">yes</span></span>|<span data-ttu-id="5b2b6-150">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b2b6-150">string</span></span>|<span data-ttu-id="5b2b6-151">Die relative Server-URL der Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-151">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="5b2b6-152">ViewOption</span><span class="sxs-lookup"><span data-stu-id="5b2b6-152">ViewOption</span></span>|<span data-ttu-id="5b2b6-153">Nein</span><span class="sxs-lookup"><span data-stu-id="5b2b6-153">no</span></span>|<span data-ttu-id="5b2b6-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b2b6-154">string</span></span>|<span data-ttu-id="5b2b6-155">Gibt an, ob die Ansicht „neues Modell“ als Bibliotheksstandard festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-155">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="5b2b6-156">Antwort</span><span class="sxs-lookup"><span data-stu-id="5b2b6-156">Response</span></span>

| <span data-ttu-id="5b2b6-157">Name</span><span class="sxs-lookup"><span data-stu-id="5b2b6-157">Name</span></span>   | <span data-ttu-id="5b2b6-158">Typ</span><span class="sxs-lookup"><span data-stu-id="5b2b6-158">Type</span></span>  | <span data-ttu-id="5b2b6-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b2b6-159">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="5b2b6-160">201 Erstellt</span><span class="sxs-lookup"><span data-stu-id="5b2b6-160">201 Created</span></span>||<span data-ttu-id="5b2b6-p102">Dies ist eine benutzerdefinierte API, die das Anwenden eines Modells auf mehrere Dokumentbibliotheken unterstützt. Im Falle eines teilweisen Erfolgs könnte immer noch „201 erstellt“ zurückgegeben werden und der Aufrufer muss den Antworttext überprüfen, um zu verstehen, ob das Modell erfolgreich auf eine Dokumentbibliothek angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-p102">This is a customized API to support applying a model to multi document libraries. In the case of partial success, 201 created could still be returned and the caller needs to inspect the response body to understand if the model has been successfully applied to a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="5b2b6-163">Antworttext</span><span class="sxs-lookup"><span data-stu-id="5b2b6-163">Response Body</span></span>

| <span data-ttu-id="5b2b6-164">Name</span><span class="sxs-lookup"><span data-stu-id="5b2b6-164">Name</span></span>   | <span data-ttu-id="5b2b6-165">Typ</span><span class="sxs-lookup"><span data-stu-id="5b2b6-165">Type</span></span>  | <span data-ttu-id="5b2b6-166">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b2b6-166">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="5b2b6-167">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="5b2b6-167">TotalSuccesses</span></span>|<span data-ttu-id="5b2b6-168">Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="5b2b6-168">int</span></span>|<span data-ttu-id="5b2b6-169">Die Gesamtzahl eines Modells, das erfolgreich auf eine Dokumentbibliothek angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-169">The total number of a model being successfully applied to a document library.</span></span>|
|<span data-ttu-id="5b2b6-170">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="5b2b6-170">TotalFailures</span></span>|<span data-ttu-id="5b2b6-171">Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="5b2b6-171">int</span></span>|<span data-ttu-id="5b2b6-172">Die Gesamtzahl eines Modells, das nicht auf eine Dokumentbibliothek angewendet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-172">The total number of a model failing to be applied to a document library.</span></span>|
|<span data-ttu-id="5b2b6-173">Details</span><span class="sxs-lookup"><span data-stu-id="5b2b6-173">Details</span></span>|<span data-ttu-id="5b2b6-174">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="5b2b6-174">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="5b2b6-175">Sie Sammlung von MachineLearningPublicationResult, von denen jedes Element das detaillierte Ergebnis der Anwendung des Modells in der Dokumentbibliothek angibt.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-175">The collection of MachineLearningPublicationResult each of which specifies the detailed result of applying the model to the document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="5b2b6-176">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="5b2b6-176">MachineLearningPublicationResult</span></span>

| <span data-ttu-id="5b2b6-177">Name</span><span class="sxs-lookup"><span data-stu-id="5b2b6-177">Name</span></span>   | <span data-ttu-id="5b2b6-178">Typ</span><span class="sxs-lookup"><span data-stu-id="5b2b6-178">Type</span></span>  | <span data-ttu-id="5b2b6-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b2b6-179">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="5b2b6-180">StatusCode</span><span class="sxs-lookup"><span data-stu-id="5b2b6-180">StatusCode</span></span>|<span data-ttu-id="5b2b6-181">Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="5b2b6-181">int</span></span>|<span data-ttu-id="5b2b6-182">Der HTTP-Statuscode.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-182">The HTTP status code.</span></span>|
|<span data-ttu-id="5b2b6-183">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="5b2b6-183">ErrorMessage</span></span>|<span data-ttu-id="5b2b6-184">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b2b6-184">string</span></span>|<span data-ttu-id="5b2b6-185">Die Fehlermeldung, welche erläutert, was beim Anwenden des Modells auf die Dokumentbibliothek falsch ist.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-185">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="5b2b6-186">Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="5b2b6-186">Publication</span></span>|<span data-ttu-id="5b2b6-187">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="5b2b6-187">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="5b2b6-188">Es gibt die Modellinformation und die Zieldokumentbibliothek an.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-188">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="5b2b6-189">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="5b2b6-189">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="5b2b6-190">Name</span><span class="sxs-lookup"><span data-stu-id="5b2b6-190">Name</span></span> | <span data-ttu-id="5b2b6-191">Typ</span><span class="sxs-lookup"><span data-stu-id="5b2b6-191">Type</span></span> | <span data-ttu-id="5b2b6-192">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b2b6-192">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="5b2b6-193">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="5b2b6-193">ModelUniqueId</span></span>|<span data-ttu-id="5b2b6-194">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b2b6-194">string</span></span>|<span data-ttu-id="5b2b6-195">Die eindeutige ID der Modelldatei.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-195">The unique ID of the model file.</span></span>|
|<span data-ttu-id="5b2b6-196">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="5b2b6-196">TargetSiteUrl</span></span>|<span data-ttu-id="5b2b6-197">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b2b6-197">string</span></span>|<span data-ttu-id="5b2b6-198">Die vollständige URL der Zielbibliothekswebsite.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-198">The full URL of the target library site.</span></span>|
|<span data-ttu-id="5b2b6-199">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="5b2b6-199">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="5b2b6-200">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b2b6-200">string</span></span>|<span data-ttu-id="5b2b6-201">Die relative Server-URL aus dem Web für die Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-201">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="5b2b6-202">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="5b2b6-202">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="5b2b6-203">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5b2b6-203">string</span></span>|<span data-ttu-id="5b2b6-204">Die relative Server-URL der Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-204">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="5b2b6-205">Beispiele</span><span class="sxs-lookup"><span data-stu-id="5b2b6-205">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="5b2b6-206">Anwenden eines Modells auf die Vertragsdokumentbibliothek in der Repository-Website</span><span class="sxs-lookup"><span data-stu-id="5b2b6-206">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="5b2b6-207">In diesem Beispiel lautet die ID des Dokumentverständnismodells für den Contoso-Vertrag `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-207">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="5b2b6-208">Beispielanfrage</span><span class="sxs-lookup"><span data-stu-id="5b2b6-208">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="5b2b6-209">Beispielantwort</span><span class="sxs-lookup"><span data-stu-id="5b2b6-209">Sample response</span></span>

<span data-ttu-id="5b2b6-210">In der Antwort beziehen sich TotalFailures und TotalSuccesses auf die Anzahl der Fehlschläge und Erfolge des Modells, das auf die angegebenen Bibliotheken angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="5b2b6-210">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="5b2b6-211">**Statuscode:** 201</span><span class="sxs-lookup"><span data-stu-id="5b2b6-211">**Status code:** 201</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5b2b6-212">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b2b6-212">See also</span></span>

[<span data-ttu-id="5b2b6-213">Syntex-Dokumentverständnismodell-REST-API</span><span class="sxs-lookup"><span data-stu-id="5b2b6-213">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)

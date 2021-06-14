---
title: Modell- und Bibliotheksinformationen abrufen
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
description: Verwenden Sie die REST-API, um Informationen über das Modell abzurufen und die Bibliothek, auf die es angewendet wurde.
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904225"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="2b48a-103">Modell- und Bibliotheksinformationen abrufen</span><span class="sxs-lookup"><span data-stu-id="2b48a-103">Get model and library information</span></span>

<span data-ttu-id="2b48a-104">Ruft Informationen ab über das Modell und die Bibliothek, auf die es angewendet wurde (siehe [Beispiel](rest-getmodelandlibraryinfo.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="2b48a-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="2b48a-105">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="2b48a-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="2b48a-106">URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="2b48a-106">URI parameters</span></span>

| <span data-ttu-id="2b48a-107">Name</span><span class="sxs-lookup"><span data-stu-id="2b48a-107">Name</span></span> | <span data-ttu-id="2b48a-108">In</span><span class="sxs-lookup"><span data-stu-id="2b48a-108">In</span></span> | <span data-ttu-id="2b48a-109">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2b48a-109">Required</span></span> | <span data-ttu-id="2b48a-110">Typ</span><span class="sxs-lookup"><span data-stu-id="2b48a-110">Type</span></span> | <span data-ttu-id="2b48a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b48a-111">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="2b48a-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="2b48a-112">ModelUniqueId</span></span>|<span data-ttu-id="2b48a-113">Abfrage</span><span class="sxs-lookup"><span data-stu-id="2b48a-113">query</span></span>|<span data-ttu-id="2b48a-114">True</span><span class="sxs-lookup"><span data-stu-id="2b48a-114">True</span></span>|<span data-ttu-id="2b48a-115">GUID</span><span class="sxs-lookup"><span data-stu-id="2b48a-115">GUID</span></span>|<span data-ttu-id="2b48a-116">Die eindeutige ID der Modelldatei.</span><span class="sxs-lookup"><span data-stu-id="2b48a-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="2b48a-117">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="2b48a-117">Request headers</span></span>

| <span data-ttu-id="2b48a-118">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="2b48a-118">Header</span></span> | <span data-ttu-id="2b48a-119">Wert</span><span class="sxs-lookup"><span data-stu-id="2b48a-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="2b48a-120">Annehmen</span><span class="sxs-lookup"><span data-stu-id="2b48a-120">Accept</span></span>|<span data-ttu-id="2b48a-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="2b48a-121">application/json;odata=verbose</span></span>|


## <a name="request-body"></a><span data-ttu-id="2b48a-122">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="2b48a-122">Request body</span></span>

| <span data-ttu-id="2b48a-123">Name</span><span class="sxs-lookup"><span data-stu-id="2b48a-123">Name</span></span> | <span data-ttu-id="2b48a-124">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="2b48a-124">Required</span></span> | <span data-ttu-id="2b48a-125">Typ</span><span class="sxs-lookup"><span data-stu-id="2b48a-125">Type</span></span> | <span data-ttu-id="2b48a-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b48a-126">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="2b48a-127">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="2b48a-127">ModelUniqueId</span></span>|<span data-ttu-id="2b48a-128">ja</span><span class="sxs-lookup"><span data-stu-id="2b48a-128">yes</span></span>|<span data-ttu-id="2b48a-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2b48a-129">string</span></span>|<span data-ttu-id="2b48a-130">Die eindeutige ID der Modelldatei.</span><span class="sxs-lookup"><span data-stu-id="2b48a-130">The unique ID of the model file.</span></span>|
|<span data-ttu-id="2b48a-131">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="2b48a-131">TargetSiteUrl</span></span>|<span data-ttu-id="2b48a-132">ja</span><span class="sxs-lookup"><span data-stu-id="2b48a-132">yes</span></span>|<span data-ttu-id="2b48a-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2b48a-133">string</span></span>|<span data-ttu-id="2b48a-134">Die vollständige URL der Zielbibliothekswebsite.</span><span class="sxs-lookup"><span data-stu-id="2b48a-134">The full URL of the target library site.</span></span>|
|<span data-ttu-id="2b48a-135">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="2b48a-135">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="2b48a-136">ja</span><span class="sxs-lookup"><span data-stu-id="2b48a-136">yes</span></span>|<span data-ttu-id="2b48a-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2b48a-137">string</span></span>|<span data-ttu-id="2b48a-138">Die relative Server-URL aus dem Web für die Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="2b48a-138">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="2b48a-139">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="2b48a-139">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="2b48a-140">ja</span><span class="sxs-lookup"><span data-stu-id="2b48a-140">yes</span></span>|<span data-ttu-id="2b48a-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2b48a-141">string</span></span>|<span data-ttu-id="2b48a-142">Die relative Server-URL der Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="2b48a-142">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="2b48a-143">TargetLibraryRemoved</span><span class="sxs-lookup"><span data-stu-id="2b48a-143">TargetLibraryRemoved</span></span>|<span data-ttu-id="2b48a-144">ja</span><span class="sxs-lookup"><span data-stu-id="2b48a-144">yes</span></span>|<span data-ttu-id="2b48a-145">int</span><span class="sxs-lookup"><span data-stu-id="2b48a-145">int</span></span>|<span data-ttu-id="2b48a-146">Die Kennzeichnung, die angibt, ob die Zielbibliothek entfernt wurde oder nicht.</span><span class="sxs-lookup"><span data-stu-id="2b48a-146">The flag that indicates if the target library has been removed or not.</span></span>|

## <a name="response"></a><span data-ttu-id="2b48a-147">Antwort</span><span class="sxs-lookup"><span data-stu-id="2b48a-147">Response</span></span>

| <span data-ttu-id="2b48a-148">Name</span><span class="sxs-lookup"><span data-stu-id="2b48a-148">Name</span></span>   | <span data-ttu-id="2b48a-149">Typ</span><span class="sxs-lookup"><span data-stu-id="2b48a-149">Type</span></span>  | <span data-ttu-id="2b48a-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b48a-150">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="2b48a-151">200 OK</span><span class="sxs-lookup"><span data-stu-id="2b48a-151">200 OK</span></span>| |<span data-ttu-id="2b48a-152">Erfolg</span><span class="sxs-lookup"><span data-stu-id="2b48a-152">Success</span></span>|
|<span data-ttu-id="2b48a-153">201 Erstellt</span><span class="sxs-lookup"><span data-stu-id="2b48a-153">201 Created</span></span>| |<span data-ttu-id="2b48a-154">Beachten Sie: Da diese API das Anwenden von Modellen auf mehrere Bibliotheken unterstützt, kann ein 201 zurückgegeben werden, auch wenn das Anwenden des Modells auf eine der Bibliotheken fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="2b48a-154">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="2b48a-155">Überprüfen Sie den Antworttext, um zu verstehen, ob das Modell erfolgreich auf alle angegebenen Bibliotheken angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2b48a-155">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="2b48a-156">Weitere Details finden Sie im [Anforderungstext](rest-getmodelandlibraryinfo.md#request-body).</span><span class="sxs-lookup"><span data-stu-id="2b48a-156">See [Request body](rest-getmodelandlibraryinfo.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="2b48a-157">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2b48a-157">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="2b48a-158">Abrufen von Informationen über das Vertragsmodell und die vorbereitete Dokumentenbibliothek in der Repository-Website</span><span class="sxs-lookup"><span data-stu-id="2b48a-158">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="2b48a-159">In diesem Beispiel lautet die ID des Dokumentverständnismodells für den Contoso-Vertrag `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="2b48a-159">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="2b48a-160">Beispielanfrage</span><span class="sxs-lookup"><span data-stu-id="2b48a-160">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a><span data-ttu-id="2b48a-161">Beispielantwort</span><span class="sxs-lookup"><span data-stu-id="2b48a-161">Sample response</span></span>

<span data-ttu-id="2b48a-162">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="2b48a-162">**Status code:** 200</span></span>

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a><span data-ttu-id="2b48a-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b48a-163">See also</span></span>

[<span data-ttu-id="2b48a-164">Syntex-Dokumentverständnismodell-REST-API</span><span class="sxs-lookup"><span data-stu-id="2b48a-164">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)

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
ms.openlocfilehash: 29240a6210e2079a082be6c3a07aae890d932719
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288755"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="7ff40-103">Modell- und Bibliotheksinformationen abrufen</span><span class="sxs-lookup"><span data-stu-id="7ff40-103">Get model and library information</span></span>

<span data-ttu-id="7ff40-104">Ruft Informationen ab über das Modell und die Bibliothek, auf die es angewendet wurde (siehe [Beispiel](rest-getmodelandlibraryinfo.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="7ff40-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="7ff40-105">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="7ff40-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbymodeluniqueid('{modelUniqueId}') HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="7ff40-106">URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="7ff40-106">URI parameters</span></span>

| <span data-ttu-id="7ff40-107">Name</span><span class="sxs-lookup"><span data-stu-id="7ff40-107">Name</span></span> | <span data-ttu-id="7ff40-108">In</span><span class="sxs-lookup"><span data-stu-id="7ff40-108">In</span></span> | <span data-ttu-id="7ff40-109">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="7ff40-109">Required</span></span> | <span data-ttu-id="7ff40-110">Typ</span><span class="sxs-lookup"><span data-stu-id="7ff40-110">Type</span></span> | <span data-ttu-id="7ff40-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ff40-111">Description</span></span> |
|--------|-------|--------|------------|-----------|
|<span data-ttu-id="7ff40-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="7ff40-112">ModelUniqueId</span></span>|<span data-ttu-id="7ff40-113">Abfrage</span><span class="sxs-lookup"><span data-stu-id="7ff40-113">query</span></span>|<span data-ttu-id="7ff40-114">True</span><span class="sxs-lookup"><span data-stu-id="7ff40-114">True</span></span>|<span data-ttu-id="7ff40-115">GUID</span><span class="sxs-lookup"><span data-stu-id="7ff40-115">GUID</span></span>|<span data-ttu-id="7ff40-116">Die eindeutige ID der Modelldatei.</span><span class="sxs-lookup"><span data-stu-id="7ff40-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="7ff40-117">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="7ff40-117">Request headers</span></span>

| <span data-ttu-id="7ff40-118">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="7ff40-118">Header</span></span> | <span data-ttu-id="7ff40-119">Wert</span><span class="sxs-lookup"><span data-stu-id="7ff40-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="7ff40-120">Annehmen</span><span class="sxs-lookup"><span data-stu-id="7ff40-120">Accept</span></span>|<span data-ttu-id="7ff40-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="7ff40-121">application/json;odata=verbose</span></span>|


## <a name="response"></a><span data-ttu-id="7ff40-122">Antwort</span><span class="sxs-lookup"><span data-stu-id="7ff40-122">Response</span></span>

| <span data-ttu-id="7ff40-123">Name</span><span class="sxs-lookup"><span data-stu-id="7ff40-123">Name</span></span>   | <span data-ttu-id="7ff40-124">Typ</span><span class="sxs-lookup"><span data-stu-id="7ff40-124">Type</span></span>  | <span data-ttu-id="7ff40-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ff40-125">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="7ff40-126">200 OK</span><span class="sxs-lookup"><span data-stu-id="7ff40-126">200 OK</span></span>| |<span data-ttu-id="7ff40-127">Erfolg</span><span class="sxs-lookup"><span data-stu-id="7ff40-127">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="7ff40-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7ff40-128">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="7ff40-129">Abrufen von Informationen über das Vertragsmodell und die vorbereitete Dokumentenbibliothek in der Repository-Website</span><span class="sxs-lookup"><span data-stu-id="7ff40-129">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="7ff40-130">In diesem Beispiel lautet die ID des Dokumentverständnismodells für den Contoso-Vertrag `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="7ff40-130">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="7ff40-131">Beispielanfrage</span><span class="sxs-lookup"><span data-stu-id="7ff40-131">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc') HTTP/1.1
```

#### <a name="sample-response"></a><span data-ttu-id="7ff40-132">Beispielantwort</span><span class="sxs-lookup"><span data-stu-id="7ff40-132">Sample response</span></span>

<span data-ttu-id="7ff40-133">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="7ff40-133">**Status code:** 200</span></span>

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
}
```

## <a name="see-also"></a><span data-ttu-id="7ff40-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ff40-134">See also</span></span>

[<span data-ttu-id="7ff40-135">Syntex-Dokumentverständnismodell-REST-API</span><span class="sxs-lookup"><span data-stu-id="7ff40-135">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)

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
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904210"
---
# <a name="batchdelete"></a><span data-ttu-id="58a0f-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="58a0f-103">BatchDelete</span></span>

<span data-ttu-id="58a0f-104">Entfernt ein angewendetes Dokumentverständnismodell von einer oder mehreren Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="58a0f-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="58a0f-105">Beachten Sie, dass das Modell von allen Bibliotheken entfernt werden muss, bevor es gelöscht werden kann (siehe [Beispiel](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="58a0f-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="58a0f-106">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a0f-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="58a0f-107">URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="58a0f-107">URI parameters</span></span>

<span data-ttu-id="58a0f-108">Keine</span><span class="sxs-lookup"><span data-stu-id="58a0f-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="58a0f-109">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="58a0f-109">Request headers</span></span>

| <span data-ttu-id="58a0f-110">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="58a0f-110">Header</span></span> | <span data-ttu-id="58a0f-111">Wert</span><span class="sxs-lookup"><span data-stu-id="58a0f-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="58a0f-112">Annehmen</span><span class="sxs-lookup"><span data-stu-id="58a0f-112">Accept</span></span>|<span data-ttu-id="58a0f-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="58a0f-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="58a0f-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="58a0f-114">Content-Type</span></span>|<span data-ttu-id="58a0f-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="58a0f-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="58a0f-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="58a0f-116">x-requestdigest</span></span>|<span data-ttu-id="58a0f-117">Der entsprechende Digest für die aktuelle Website.</span><span class="sxs-lookup"><span data-stu-id="58a0f-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="58a0f-118">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="58a0f-118">Request body</span></span>

| <span data-ttu-id="58a0f-119">Name</span><span class="sxs-lookup"><span data-stu-id="58a0f-119">Name</span></span> | <span data-ttu-id="58a0f-120">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="58a0f-120">Required</span></span> | <span data-ttu-id="58a0f-121">Typ</span><span class="sxs-lookup"><span data-stu-id="58a0f-121">Type</span></span> | <span data-ttu-id="58a0f-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58a0f-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="58a0f-123">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="58a0f-123">ModelUniqueId</span></span>|<span data-ttu-id="58a0f-124">ja</span><span class="sxs-lookup"><span data-stu-id="58a0f-124">yes</span></span>|<span data-ttu-id="58a0f-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="58a0f-125">string</span></span>|<span data-ttu-id="58a0f-126">Die eindeutige ID der Modelldatei.</span><span class="sxs-lookup"><span data-stu-id="58a0f-126">The unique ID of the model file.</span></span>|
<span data-ttu-id="58a0f-127">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="58a0f-127">TargetSiteUrl</span></span>|<span data-ttu-id="58a0f-128">ja</span><span class="sxs-lookup"><span data-stu-id="58a0f-128">yes</span></span>|<span data-ttu-id="58a0f-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="58a0f-129">string</span></span>|<span data-ttu-id="58a0f-130">Die vollständige URL der Zielbibliothekswebsite.</span><span class="sxs-lookup"><span data-stu-id="58a0f-130">The full URL of the target library site.</span></span>|
<span data-ttu-id="58a0f-131">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="58a0f-131">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="58a0f-132">ja</span><span class="sxs-lookup"><span data-stu-id="58a0f-132">yes</span></span>|<span data-ttu-id="58a0f-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="58a0f-133">string</span></span>|<span data-ttu-id="58a0f-134">Die relative Server-URL aus dem Web für die Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="58a0f-134">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="58a0f-135">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="58a0f-135">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="58a0f-136">ja</span><span class="sxs-lookup"><span data-stu-id="58a0f-136">yes</span></span>|<span data-ttu-id="58a0f-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="58a0f-137">string</span></span>|<span data-ttu-id="58a0f-138">Die relative Server-URL der Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="58a0f-138">The server relative URL of the target library.</span></span>|
<span data-ttu-id="58a0f-139">ViewOption</span><span class="sxs-lookup"><span data-stu-id="58a0f-139">ViewOption</span></span>|<span data-ttu-id="58a0f-140">Nein</span><span class="sxs-lookup"><span data-stu-id="58a0f-140">no</span></span>|<span data-ttu-id="58a0f-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="58a0f-141">string</span></span>|<span data-ttu-id="58a0f-142">Gibt an, ob die Ansicht „neues Modell“ als Bibliotheksstandard festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="58a0f-142">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="58a0f-143">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a0f-143">Response</span></span>

| <span data-ttu-id="58a0f-144">Name</span><span class="sxs-lookup"><span data-stu-id="58a0f-144">Name</span></span>   | <span data-ttu-id="58a0f-145">Typ</span><span class="sxs-lookup"><span data-stu-id="58a0f-145">Type</span></span>  | <span data-ttu-id="58a0f-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58a0f-146">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="58a0f-147">200 OK</span><span class="sxs-lookup"><span data-stu-id="58a0f-147">200 OK</span></span>| |<span data-ttu-id="58a0f-148">Erfolg</span><span class="sxs-lookup"><span data-stu-id="58a0f-148">Success</span></span>|


## <a name="examples"></a><span data-ttu-id="58a0f-149">Beispiele</span><span class="sxs-lookup"><span data-stu-id="58a0f-149">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="58a0f-150">Entfernen eines Modells aus der Vertragsdokumentbibliothek in der Repository-Website</span><span class="sxs-lookup"><span data-stu-id="58a0f-150">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="58a0f-151">In diesem Beispiel lautet die ID des Dokumentverständnismodells für den Contoso-Vertrag `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="58a0f-151">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="58a0f-152">Beispielanfrage</span><span class="sxs-lookup"><span data-stu-id="58a0f-152">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="58a0f-153">Beispielantwort</span><span class="sxs-lookup"><span data-stu-id="58a0f-153">Sample response</span></span>

<span data-ttu-id="58a0f-154">In der Antwort beziehen sich TotalFailures und TotalSuccesses auf die Anzahl der Fehlschläge und Erfolge des Modells, das auf die angegebenen Bibliotheken angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="58a0f-154">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="58a0f-155">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="58a0f-155">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="58a0f-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58a0f-156">See also</span></span>

[<span data-ttu-id="58a0f-157">Syntex-Dokumentverständnismodell-REST-API</span><span class="sxs-lookup"><span data-stu-id="58a0f-157">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)

---
title: Modell anwenden
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
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904266"
---
# <a name="apply-model"></a><span data-ttu-id="140e3-103">Modell anwenden</span><span class="sxs-lookup"><span data-stu-id="140e3-103">Apply model</span></span>

<span data-ttu-id="140e3-104">Wendet ein trainiertes Dokumentverständnismodell auf eine oder mehrere Bibliotheken an (oder synchronisiert es) (siehe [Beispiel](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="140e3-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="140e3-105">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="140e3-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="140e3-106">URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="140e3-106">URI parameters</span></span>

<span data-ttu-id="140e3-107">Keine</span><span class="sxs-lookup"><span data-stu-id="140e3-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="140e3-108">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="140e3-108">Request headers</span></span>

| <span data-ttu-id="140e3-109">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="140e3-109">Header</span></span> | <span data-ttu-id="140e3-110">Wert</span><span class="sxs-lookup"><span data-stu-id="140e3-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="140e3-111">Annehmen</span><span class="sxs-lookup"><span data-stu-id="140e3-111">Accept</span></span>|<span data-ttu-id="140e3-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="140e3-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="140e3-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="140e3-113">Content-Type</span></span>|<span data-ttu-id="140e3-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="140e3-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="140e3-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="140e3-115">x-requestdigest</span></span>|<span data-ttu-id="140e3-116">Der entsprechende Digest für die aktuelle Website.</span><span class="sxs-lookup"><span data-stu-id="140e3-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="140e3-117">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="140e3-117">Request body</span></span>

| <span data-ttu-id="140e3-118">Name</span><span class="sxs-lookup"><span data-stu-id="140e3-118">Name</span></span> | <span data-ttu-id="140e3-119">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="140e3-119">Required</span></span> | <span data-ttu-id="140e3-120">Typ</span><span class="sxs-lookup"><span data-stu-id="140e3-120">Type</span></span> | <span data-ttu-id="140e3-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="140e3-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="140e3-122">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="140e3-122">ModelUniqueId</span></span>|<span data-ttu-id="140e3-123">ja</span><span class="sxs-lookup"><span data-stu-id="140e3-123">yes</span></span>|<span data-ttu-id="140e3-124">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="140e3-124">string</span></span>|<span data-ttu-id="140e3-125">Die eindeutige ID der Modelldatei.</span><span class="sxs-lookup"><span data-stu-id="140e3-125">The unique ID of the model file.</span></span>|
<span data-ttu-id="140e3-126">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="140e3-126">TargetSiteUrl</span></span>|<span data-ttu-id="140e3-127">ja</span><span class="sxs-lookup"><span data-stu-id="140e3-127">yes</span></span>|<span data-ttu-id="140e3-128">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="140e3-128">string</span></span>|<span data-ttu-id="140e3-129">Die vollständige URL der Zielbibliothekswebsite.</span><span class="sxs-lookup"><span data-stu-id="140e3-129">The full URL of the target library site.</span></span>|
<span data-ttu-id="140e3-130">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="140e3-130">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="140e3-131">ja</span><span class="sxs-lookup"><span data-stu-id="140e3-131">yes</span></span>|<span data-ttu-id="140e3-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="140e3-132">string</span></span>|<span data-ttu-id="140e3-133">Die relative Server-URL aus dem Web für die Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="140e3-133">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="140e3-134">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="140e3-134">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="140e3-135">ja</span><span class="sxs-lookup"><span data-stu-id="140e3-135">yes</span></span>|<span data-ttu-id="140e3-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="140e3-136">string</span></span>|<span data-ttu-id="140e3-137">Die relative Server-URL der Zielbibliothek.</span><span class="sxs-lookup"><span data-stu-id="140e3-137">The server relative URL of the target library.</span></span>|
<span data-ttu-id="140e3-138">ViewOption</span><span class="sxs-lookup"><span data-stu-id="140e3-138">ViewOption</span></span>|<span data-ttu-id="140e3-139">Nein</span><span class="sxs-lookup"><span data-stu-id="140e3-139">no</span></span>|<span data-ttu-id="140e3-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="140e3-140">string</span></span>|<span data-ttu-id="140e3-141">Gibt an, ob die Ansicht „neues Modell“ als Bibliotheksstandard festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="140e3-141">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="140e3-142">Antwort</span><span class="sxs-lookup"><span data-stu-id="140e3-142">Response</span></span>

| <span data-ttu-id="140e3-143">Name</span><span class="sxs-lookup"><span data-stu-id="140e3-143">Name</span></span>   | <span data-ttu-id="140e3-144">Typ</span><span class="sxs-lookup"><span data-stu-id="140e3-144">Type</span></span>  | <span data-ttu-id="140e3-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="140e3-145">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="140e3-146">200 OK</span><span class="sxs-lookup"><span data-stu-id="140e3-146">200 OK</span></span>| |<span data-ttu-id="140e3-147">Erfolg</span><span class="sxs-lookup"><span data-stu-id="140e3-147">Success</span></span>|
|<span data-ttu-id="140e3-148">201 Erstellt</span><span class="sxs-lookup"><span data-stu-id="140e3-148">201 Created</span></span>| |<span data-ttu-id="140e3-149">Beachten Sie: Da diese API das Anwenden von Modellen auf mehrere Bibliotheken unterstützt, kann ein 201 zurückgegeben werden, auch wenn das Anwenden des Modells auf eine der Bibliotheken fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="140e3-149">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="140e3-150">Überprüfen Sie den Antworttext, um zu verstehen, ob das Modell erfolgreich auf alle angegebenen Bibliotheken angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="140e3-150">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="140e3-151">Weitere Details finden Sie im [Anforderungstext](rest-applymodel-method.md#request-body).</span><span class="sxs-lookup"><span data-stu-id="140e3-151">See [Request body](rest-applymodel-method.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="140e3-152">Beispiele</span><span class="sxs-lookup"><span data-stu-id="140e3-152">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="140e3-153">Anwenden eines Modells auf die Vertragsdokumentbibliothek in der Repository-Website</span><span class="sxs-lookup"><span data-stu-id="140e3-153">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="140e3-154">In diesem Beispiel lautet die ID des Dokumentverständnismodells für den Contoso-Vertrag `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="140e3-154">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="140e3-155">Beispielanfrage</span><span class="sxs-lookup"><span data-stu-id="140e3-155">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="140e3-156">Beispielantwort</span><span class="sxs-lookup"><span data-stu-id="140e3-156">Sample response</span></span>

<span data-ttu-id="140e3-157">In der Antwort beziehen sich TotalFailures und TotalSuccesses auf die Anzahl der Fehlschläge und Erfolge des Modells, das auf die angegebenen Bibliotheken angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="140e3-157">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="140e3-158">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="140e3-158">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="140e3-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="140e3-159">See also</span></span>

[<span data-ttu-id="140e3-160">Syntex-Dokumentverständnismodell-REST-API</span><span class="sxs-lookup"><span data-stu-id="140e3-160">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)

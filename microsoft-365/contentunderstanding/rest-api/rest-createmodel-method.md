---
title: Ein Modell erstellen
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
description: Verwenden Sie die REST-API, um ein Modell und den zugehörigen Inhaltstyp zu erstellen.
ms.openlocfilehash: 4af980d0733fce63767c6570003342eadb079f26
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904222"
---
# <a name="create-model"></a><span data-ttu-id="8f6e5-103">Ein Modell erstellen</span><span class="sxs-lookup"><span data-stu-id="8f6e5-103">Create model</span></span>

<span data-ttu-id="8f6e5-104">Erstellt ein Modell und den zugehörigen Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="8f6e5-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="8f6e5-105">Beachten Sie, dass dies nur das Modell erstellt.</span><span class="sxs-lookup"><span data-stu-id="8f6e5-105">Note that this only creates the model.</span></span> <span data-ttu-id="8f6e5-106">Es muss noch im Inhaltscenter trainiert werden (siehe [Beispiel](rest-createmodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="8f6e5-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="8f6e5-107">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="8f6e5-107">HTTP request</span></span>

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="8f6e5-108">URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="8f6e5-108">URI Parameters</span></span>

<span data-ttu-id="8f6e5-109">Keine</span><span class="sxs-lookup"><span data-stu-id="8f6e5-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="8f6e5-110">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="8f6e5-110">Request headers</span></span>

| <span data-ttu-id="8f6e5-111">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="8f6e5-111">Header</span></span> | <span data-ttu-id="8f6e5-112">Wert</span><span class="sxs-lookup"><span data-stu-id="8f6e5-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="8f6e5-113">Annehmen</span><span class="sxs-lookup"><span data-stu-id="8f6e5-113">Accept</span></span>|<span data-ttu-id="8f6e5-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="8f6e5-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="8f6e5-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8f6e5-115">Content-Type</span></span>|<span data-ttu-id="8f6e5-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="8f6e5-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="8f6e5-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="8f6e5-117">x-requestdigest</span></span>|<span data-ttu-id="8f6e5-118">Die entsprechende Digest für die aktuelle Website</span><span class="sxs-lookup"><span data-stu-id="8f6e5-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="8f6e5-119">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="8f6e5-119">Request body</span></span>

|<span data-ttu-id="8f6e5-120">Name</span><span class="sxs-lookup"><span data-stu-id="8f6e5-120">Name</span></span>    |<span data-ttu-id="8f6e5-121">Typ</span><span class="sxs-lookup"><span data-stu-id="8f6e5-121">Type</span></span>   |<span data-ttu-id="8f6e5-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f6e5-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="8f6e5-123">_metadata</span><span class="sxs-lookup"><span data-stu-id="8f6e5-123">_metadata</span></span>|  |<span data-ttu-id="8f6e5-124">Festlegen der Objekt-Metadaten auf dem SPO.</span><span class="sxs-lookup"><span data-stu-id="8f6e5-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="8f6e5-125">Verwenden Sie immer den Wert: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="8f6e5-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="8f6e5-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="8f6e5-126">ContentTypeGroup</span></span>|<span data-ttu-id="8f6e5-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8f6e5-127">string</span></span>|<span data-ttu-id="8f6e5-128">Die zugehörige Inhaltstypgruppe, die dem Modell zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8f6e5-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="8f6e5-129">Standardmäßig auf „Intelligente Dokumentinhaltstypen“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8f6e5-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="8f6e5-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="8f6e5-130">ContentTypeName</span></span>|<span data-ttu-id="8f6e5-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8f6e5-131">string</span></span>|<span data-ttu-id="8f6e5-132">Der zugehörige Inhaltstypname.</span><span class="sxs-lookup"><span data-stu-id="8f6e5-132">The associated content type name.</span></span> <span data-ttu-id="8f6e5-133">Die erstellte Modelldatei wird den gleichen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="8f6e5-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="8f6e5-134">Antworten</span><span class="sxs-lookup"><span data-stu-id="8f6e5-134">Responses</span></span>

| <span data-ttu-id="8f6e5-135">Name</span><span class="sxs-lookup"><span data-stu-id="8f6e5-135">Name</span></span>   | <span data-ttu-id="8f6e5-136">Typ</span><span class="sxs-lookup"><span data-stu-id="8f6e5-136">Type</span></span>  | <span data-ttu-id="8f6e5-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f6e5-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="8f6e5-138">201 Erstellt</span><span class="sxs-lookup"><span data-stu-id="8f6e5-138">201 Created</span></span>| |<span data-ttu-id="8f6e5-139">Erfolg</span><span class="sxs-lookup"><span data-stu-id="8f6e5-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="8f6e5-140">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8f6e5-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="8f6e5-141">Erstellen eines neuen Dokumentverständnismodells mit Namen „Contoso-Vertrag“</span><span class="sxs-lookup"><span data-stu-id="8f6e5-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="8f6e5-142">Beispielanfrage</span><span class="sxs-lookup"><span data-stu-id="8f6e5-142">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract",
}
```

#### <a name="sample-response"></a><span data-ttu-id="8f6e5-143">Beispielantwort</span><span class="sxs-lookup"><span data-stu-id="8f6e5-143">Sample response</span></span>

<span data-ttu-id="8f6e5-144">**Statuscode:** 201</span><span class="sxs-lookup"><span data-stu-id="8f6e5-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="8f6e5-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f6e5-145">See also</span></span>

[<span data-ttu-id="8f6e5-146">Syntex-Dokumentverständnismodell-REST-API</span><span class="sxs-lookup"><span data-stu-id="8f6e5-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)

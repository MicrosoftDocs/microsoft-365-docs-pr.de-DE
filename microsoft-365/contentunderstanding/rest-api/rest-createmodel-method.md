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
ms.openlocfilehash: 1c5bd84c777774edc1aa0c2419181f7b84aa4707
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287245"
---
# <a name="create-model"></a><span data-ttu-id="77d08-103">Ein Modell erstellen</span><span class="sxs-lookup"><span data-stu-id="77d08-103">Create model</span></span>

<span data-ttu-id="77d08-104">Erstellt ein Modell und den zugehörigen Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="77d08-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="77d08-105">Beachten Sie, dass dies nur das Modell erstellt.</span><span class="sxs-lookup"><span data-stu-id="77d08-105">Note that this only creates the model.</span></span> <span data-ttu-id="77d08-106">Es muss noch im Inhaltscenter trainiert werden (siehe [Beispiel](rest-createmodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="77d08-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="77d08-107">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="77d08-107">HTTP request</span></span>

```http
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="77d08-108">URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="77d08-108">URI Parameters</span></span>

<span data-ttu-id="77d08-109">Keine</span><span class="sxs-lookup"><span data-stu-id="77d08-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="77d08-110">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="77d08-110">Request headers</span></span>

| <span data-ttu-id="77d08-111">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="77d08-111">Header</span></span> | <span data-ttu-id="77d08-112">Wert</span><span class="sxs-lookup"><span data-stu-id="77d08-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="77d08-113">Annehmen</span><span class="sxs-lookup"><span data-stu-id="77d08-113">Accept</span></span>|<span data-ttu-id="77d08-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="77d08-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="77d08-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="77d08-115">Content-Type</span></span>|<span data-ttu-id="77d08-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="77d08-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="77d08-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="77d08-117">x-requestdigest</span></span>|<span data-ttu-id="77d08-118">Die entsprechende Digest für die aktuelle Website</span><span class="sxs-lookup"><span data-stu-id="77d08-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="77d08-119">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="77d08-119">Request body</span></span>

|<span data-ttu-id="77d08-120">Name</span><span class="sxs-lookup"><span data-stu-id="77d08-120">Name</span></span>    |<span data-ttu-id="77d08-121">Typ</span><span class="sxs-lookup"><span data-stu-id="77d08-121">Type</span></span>   |<span data-ttu-id="77d08-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77d08-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="77d08-123">_metadata</span><span class="sxs-lookup"><span data-stu-id="77d08-123">_metadata</span></span>|  |<span data-ttu-id="77d08-124">Festlegen der Objekt-Metadaten auf dem SPO.</span><span class="sxs-lookup"><span data-stu-id="77d08-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="77d08-125">Verwenden Sie immer den Wert: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="77d08-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="77d08-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="77d08-126">ContentTypeGroup</span></span>|<span data-ttu-id="77d08-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="77d08-127">string</span></span>|<span data-ttu-id="77d08-128">Die zugehörige Inhaltstypgruppe, die dem Modell zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="77d08-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="77d08-129">Standardmäßig auf „Intelligente Dokumentinhaltstypen“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="77d08-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="77d08-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="77d08-130">ContentTypeName</span></span>|<span data-ttu-id="77d08-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="77d08-131">string</span></span>|<span data-ttu-id="77d08-132">Der zugehörige Inhaltstypname.</span><span class="sxs-lookup"><span data-stu-id="77d08-132">The associated content type name.</span></span> <span data-ttu-id="77d08-133">Die erstellte Modelldatei wird den gleichen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="77d08-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="77d08-134">Antworten</span><span class="sxs-lookup"><span data-stu-id="77d08-134">Responses</span></span>

| <span data-ttu-id="77d08-135">Name</span><span class="sxs-lookup"><span data-stu-id="77d08-135">Name</span></span>   | <span data-ttu-id="77d08-136">Typ</span><span class="sxs-lookup"><span data-stu-id="77d08-136">Type</span></span>  | <span data-ttu-id="77d08-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77d08-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="77d08-138">201 Erstellt</span><span class="sxs-lookup"><span data-stu-id="77d08-138">201 Created</span></span>| |<span data-ttu-id="77d08-139">Erfolg</span><span class="sxs-lookup"><span data-stu-id="77d08-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="77d08-140">Beispiele</span><span class="sxs-lookup"><span data-stu-id="77d08-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="77d08-141">Erstellen eines neuen Dokumentverständnismodells mit Namen „Contoso-Vertrag“</span><span class="sxs-lookup"><span data-stu-id="77d08-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="77d08-142">Beispielanfrage</span><span class="sxs-lookup"><span data-stu-id="77d08-142">Sample request</span></span>

```json
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a><span data-ttu-id="77d08-143">Beispielantwort</span><span class="sxs-lookup"><span data-stu-id="77d08-143">Sample response</span></span>

<span data-ttu-id="77d08-144">**Statuscode:** 201</span><span class="sxs-lookup"><span data-stu-id="77d08-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="77d08-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77d08-145">See also</span></span>

[<span data-ttu-id="77d08-146">Syntex-Dokumentverständnismodell-REST-API</span><span class="sxs-lookup"><span data-stu-id="77d08-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)

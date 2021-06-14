---
title: UpdateModelSettings
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
description: Verwenden Sie die REST-API, um die verfügbaren Modelleinstellungen für ein SharePoint Syntex-Dokumentverständnismodell zu aktualisieren.
ms.openlocfilehash: f24fc8428adbf22ded2ca6d7a49cabc84b385770
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904228"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="4231c-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="4231c-103">UpdateModelSettings</span></span>

<span data-ttu-id="4231c-104">Aktualisiert verfügbare Modelleinstellungen (zugehörige Aufbewahrungsbezeichnung und Modellbeschreibung) für eine SharePoint Syntex-Dokumentverständnismodell (siehe [Beispiel](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="4231c-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="4231c-105">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="4231c-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="4231c-106">URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="4231c-106">URI parameters</span></span>

<span data-ttu-id="4231c-107">Keine</span><span class="sxs-lookup"><span data-stu-id="4231c-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="4231c-108">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="4231c-108">Request headers</span></span>

| <span data-ttu-id="4231c-109">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="4231c-109">Header</span></span> | <span data-ttu-id="4231c-110">Wert</span><span class="sxs-lookup"><span data-stu-id="4231c-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="4231c-111">Annehmen</span><span class="sxs-lookup"><span data-stu-id="4231c-111">Accept</span></span>|<span data-ttu-id="4231c-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="4231c-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="4231c-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4231c-113">Content-Type</span></span>|<span data-ttu-id="4231c-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="4231c-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="4231c-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="4231c-115">x-requestdigest</span></span>|<span data-ttu-id="4231c-116">Die entsprechende Digest für die aktuelle Website.</span><span class="sxs-lookup"><span data-stu-id="4231c-116">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="4231c-117">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="4231c-117">Request body</span></span>

|<span data-ttu-id="4231c-118">Name</span><span class="sxs-lookup"><span data-stu-id="4231c-118">Name</span></span>    |<span data-ttu-id="4231c-119">Typ</span><span class="sxs-lookup"><span data-stu-id="4231c-119">Type</span></span>   |<span data-ttu-id="4231c-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4231c-120">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="4231c-121">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="4231c-121">ModelSettings</span></span>|<span data-ttu-id="4231c-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4231c-122">string</span></span>|<span data-ttu-id="4231c-123">JSON der Modelleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="4231c-123">JSON of model settings.</span></span>|
|<span data-ttu-id="4231c-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4231c-124">Description</span></span>|<span data-ttu-id="4231c-125">string</span><span class="sxs-lookup"><span data-stu-id="4231c-125">string</span></span>|<span data-ttu-id="4231c-126">Die Modellbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="4231c-126">The model description.</span></span>|
|<span data-ttu-id="4231c-127">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="4231c-127">RetentionLabel</span></span>| |<span data-ttu-id="4231c-128">Info für die zugehörige Bezeichnung (Bezeichnungs-ID und Name).</span><span class="sxs-lookup"><span data-stu-id="4231c-128">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="4231c-129">Antworten</span><span class="sxs-lookup"><span data-stu-id="4231c-129">Responses</span></span>

| <span data-ttu-id="4231c-130">Name</span><span class="sxs-lookup"><span data-stu-id="4231c-130">Name</span></span>   | <span data-ttu-id="4231c-131">Typ</span><span class="sxs-lookup"><span data-stu-id="4231c-131">Type</span></span>  | <span data-ttu-id="4231c-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4231c-132">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="4231c-133">200 OK</span><span class="sxs-lookup"><span data-stu-id="4231c-133">200 OK</span></span>| |<span data-ttu-id="4231c-134">Erfolg</span><span class="sxs-lookup"><span data-stu-id="4231c-134">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="4231c-135">Beispiele</span><span class="sxs-lookup"><span data-stu-id="4231c-135">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="4231c-136">Aktualisieren der Modelleinstellungen für Contoso-Vertrag</span><span class="sxs-lookup"><span data-stu-id="4231c-136">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="4231c-137">In diesem Beispiel werden die Modellbeschreibung und die Aufbewahrungsbezeichnung „Standard-Aufbewahrung“ aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="4231c-137">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="4231c-138">Die ID der Aufbewahrungsbezeichnung ist `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="4231c-138">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="4231c-139">Beispielanfrage</span><span class="sxs-lookup"><span data-stu-id="4231c-139">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="4231c-140">Beispielantwort</span><span class="sxs-lookup"><span data-stu-id="4231c-140">Sample response</span></span>

<span data-ttu-id="4231c-141">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="4231c-141">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="4231c-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4231c-142">See also</span></span>

[<span data-ttu-id="4231c-143">Syntex-Dokumentverständnismodell-REST-API</span><span class="sxs-lookup"><span data-stu-id="4231c-143">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)

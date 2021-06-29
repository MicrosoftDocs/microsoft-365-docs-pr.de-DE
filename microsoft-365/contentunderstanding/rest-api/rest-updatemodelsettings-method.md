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
ms.openlocfilehash: cd288812044f3b02839c3c11c321947bd02cccaa
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177165"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="8157a-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="8157a-103">UpdateModelSettings</span></span>

<span data-ttu-id="8157a-104">Aktualisiert verfügbare Modelleinstellungen (zugehörige Aufbewahrungsbezeichnung und Modellbeschreibung) für eine SharePoint Syntex-Dokumentverständnismodell (siehe [Beispiel](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="8157a-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="8157a-105">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="8157a-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="8157a-106">URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="8157a-106">URI parameters</span></span>

|<span data-ttu-id="8157a-107">Name</span><span class="sxs-lookup"><span data-stu-id="8157a-107">Name</span></span> |<span data-ttu-id="8157a-108">In</span><span class="sxs-lookup"><span data-stu-id="8157a-108">In</span></span> |<span data-ttu-id="8157a-109">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="8157a-109">Required</span></span>|<span data-ttu-id="8157a-110">Typ</span><span class="sxs-lookup"><span data-stu-id="8157a-110">Type</span></span>|<span data-ttu-id="8157a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8157a-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="8157a-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="8157a-112">modelFileName</span></span>|<span data-ttu-id="8157a-113">Abfrage</span><span class="sxs-lookup"><span data-stu-id="8157a-113">query</span></span>|<span data-ttu-id="8157a-114">True</span><span class="sxs-lookup"><span data-stu-id="8157a-114">True</span></span>|<span data-ttu-id="8157a-115">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8157a-115">string</span></span>|<span data-ttu-id="8157a-116">Name der Syntex-Modelldatei.</span><span class="sxs-lookup"><span data-stu-id="8157a-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="8157a-117">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="8157a-117">Request headers</span></span>

| <span data-ttu-id="8157a-118">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="8157a-118">Header</span></span> | <span data-ttu-id="8157a-119">Wert</span><span class="sxs-lookup"><span data-stu-id="8157a-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="8157a-120">Annehmen</span><span class="sxs-lookup"><span data-stu-id="8157a-120">Accept</span></span>|<span data-ttu-id="8157a-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="8157a-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="8157a-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8157a-122">Content-Type</span></span>|<span data-ttu-id="8157a-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="8157a-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="8157a-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="8157a-124">x-requestdigest</span></span>|<span data-ttu-id="8157a-125">Die entsprechende Digest für die aktuelle Website.</span><span class="sxs-lookup"><span data-stu-id="8157a-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="8157a-126">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="8157a-126">Request body</span></span>

|<span data-ttu-id="8157a-127">Name</span><span class="sxs-lookup"><span data-stu-id="8157a-127">Name</span></span>    |<span data-ttu-id="8157a-128">Typ</span><span class="sxs-lookup"><span data-stu-id="8157a-128">Type</span></span>   |<span data-ttu-id="8157a-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8157a-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="8157a-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="8157a-130">ModelSettings</span></span>|<span data-ttu-id="8157a-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8157a-131">string</span></span>|<span data-ttu-id="8157a-132">JSON der Modelleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="8157a-132">JSON of model settings.</span></span>|
|<span data-ttu-id="8157a-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8157a-133">Description</span></span>|<span data-ttu-id="8157a-134">string</span><span class="sxs-lookup"><span data-stu-id="8157a-134">string</span></span>|<span data-ttu-id="8157a-135">Die Modellbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="8157a-135">The model description.</span></span>|
|<span data-ttu-id="8157a-136">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="8157a-136">RetentionLabel</span></span>| |<span data-ttu-id="8157a-137">Info für die zugehörige Bezeichnung (Bezeichnungs-ID und Name).</span><span class="sxs-lookup"><span data-stu-id="8157a-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="8157a-138">Antworten</span><span class="sxs-lookup"><span data-stu-id="8157a-138">Responses</span></span>

| <span data-ttu-id="8157a-139">Name</span><span class="sxs-lookup"><span data-stu-id="8157a-139">Name</span></span>   | <span data-ttu-id="8157a-140">Typ</span><span class="sxs-lookup"><span data-stu-id="8157a-140">Type</span></span>  | <span data-ttu-id="8157a-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8157a-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="8157a-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="8157a-142">200 OK</span></span>| |<span data-ttu-id="8157a-143">Erfolg</span><span class="sxs-lookup"><span data-stu-id="8157a-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="8157a-144">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8157a-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="8157a-145">Aktualisieren der Modelleinstellungen für Contoso-Vertrag</span><span class="sxs-lookup"><span data-stu-id="8157a-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="8157a-146">In diesem Beispiel werden die Modellbeschreibung und die Aufbewahrungsbezeichnung „Standard-Aufbewahrung“ aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8157a-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="8157a-147">Die ID der Aufbewahrungsbezeichnung ist `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="8157a-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="8157a-148">Beispielanfrage</span><span class="sxs-lookup"><span data-stu-id="8157a-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="8157a-149">Beispielantwort</span><span class="sxs-lookup"><span data-stu-id="8157a-149">Sample response</span></span>

<span data-ttu-id="8157a-150">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="8157a-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="8157a-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8157a-151">See also</span></span>

[<span data-ttu-id="8157a-152">Syntex-Dokumentverständnismodell-REST-API</span><span class="sxs-lookup"><span data-stu-id="8157a-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)

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
ms.openlocfilehash: c75f669913f16233c6015230a60643cf86f33f5a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288647"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="780ed-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="780ed-103">UpdateModelSettings</span></span>

<span data-ttu-id="780ed-104">Aktualisiert verfügbare Modelleinstellungen (zugehörige Aufbewahrungsbezeichnung und Modellbeschreibung) für eine SharePoint Syntex-Dokumentverständnismodell (siehe [Beispiel](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="780ed-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="780ed-105">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="780ed-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="780ed-106">URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="780ed-106">URI parameters</span></span>

|<span data-ttu-id="780ed-107">Name</span><span class="sxs-lookup"><span data-stu-id="780ed-107">Name</span></span> |<span data-ttu-id="780ed-108">In</span><span class="sxs-lookup"><span data-stu-id="780ed-108">In</span></span> |<span data-ttu-id="780ed-109">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="780ed-109">Required</span></span>|<span data-ttu-id="780ed-110">Typ</span><span class="sxs-lookup"><span data-stu-id="780ed-110">Type</span></span>|<span data-ttu-id="780ed-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="780ed-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="780ed-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="780ed-112">modelFileName</span></span>|<span data-ttu-id="780ed-113">Abfrage</span><span class="sxs-lookup"><span data-stu-id="780ed-113">query</span></span>|<span data-ttu-id="780ed-114">True</span><span class="sxs-lookup"><span data-stu-id="780ed-114">True</span></span>|<span data-ttu-id="780ed-115">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="780ed-115">string</span></span>|<span data-ttu-id="780ed-116">Name der Syntex-Modelldatei.</span><span class="sxs-lookup"><span data-stu-id="780ed-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="780ed-117">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="780ed-117">Request headers</span></span>

| <span data-ttu-id="780ed-118">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="780ed-118">Header</span></span> | <span data-ttu-id="780ed-119">Wert</span><span class="sxs-lookup"><span data-stu-id="780ed-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="780ed-120">Annehmen</span><span class="sxs-lookup"><span data-stu-id="780ed-120">Accept</span></span>|<span data-ttu-id="780ed-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="780ed-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="780ed-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="780ed-122">Content-Type</span></span>|<span data-ttu-id="780ed-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="780ed-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="780ed-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="780ed-124">x-requestdigest</span></span>|<span data-ttu-id="780ed-125">Die entsprechende Digest für die aktuelle Website.</span><span class="sxs-lookup"><span data-stu-id="780ed-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="780ed-126">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="780ed-126">Request body</span></span>

|<span data-ttu-id="780ed-127">Name</span><span class="sxs-lookup"><span data-stu-id="780ed-127">Name</span></span>    |<span data-ttu-id="780ed-128">Typ</span><span class="sxs-lookup"><span data-stu-id="780ed-128">Type</span></span>   |<span data-ttu-id="780ed-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="780ed-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="780ed-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="780ed-130">ModelSettings</span></span>|<span data-ttu-id="780ed-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="780ed-131">string</span></span>|<span data-ttu-id="780ed-132">JSON der Modelleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="780ed-132">JSON of model settings.</span></span>|
|<span data-ttu-id="780ed-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="780ed-133">Description</span></span>|<span data-ttu-id="780ed-134">string</span><span class="sxs-lookup"><span data-stu-id="780ed-134">string</span></span>|<span data-ttu-id="780ed-135">Die Modellbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="780ed-135">The model description.</span></span>|
|<span data-ttu-id="780ed-136">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="780ed-136">RetentionLabel</span></span>| |<span data-ttu-id="780ed-137">Info für die zugehörige Bezeichnung (Bezeichnungs-ID und Name).</span><span class="sxs-lookup"><span data-stu-id="780ed-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="780ed-138">Antworten</span><span class="sxs-lookup"><span data-stu-id="780ed-138">Responses</span></span>

| <span data-ttu-id="780ed-139">Name</span><span class="sxs-lookup"><span data-stu-id="780ed-139">Name</span></span>   | <span data-ttu-id="780ed-140">Typ</span><span class="sxs-lookup"><span data-stu-id="780ed-140">Type</span></span>  | <span data-ttu-id="780ed-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="780ed-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="780ed-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="780ed-142">200 OK</span></span>| |<span data-ttu-id="780ed-143">Erfolg</span><span class="sxs-lookup"><span data-stu-id="780ed-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="780ed-144">Beispiele</span><span class="sxs-lookup"><span data-stu-id="780ed-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="780ed-145">Aktualisieren der Modelleinstellungen für Contoso-Vertrag</span><span class="sxs-lookup"><span data-stu-id="780ed-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="780ed-146">In diesem Beispiel werden die Modellbeschreibung und die Aufbewahrungsbezeichnung „Standard-Aufbewahrung“ aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="780ed-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="780ed-147">Die ID der Aufbewahrungsbezeichnung ist `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="780ed-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="780ed-148">Beispielanfrage</span><span class="sxs-lookup"><span data-stu-id="780ed-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="780ed-149">Beispielantwort</span><span class="sxs-lookup"><span data-stu-id="780ed-149">Sample response</span></span>

<span data-ttu-id="780ed-150">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="780ed-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="780ed-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="780ed-151">See also</span></span>

[<span data-ttu-id="780ed-152">Syntex-Dokumentverständnismodell-REST-API</span><span class="sxs-lookup"><span data-stu-id="780ed-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)

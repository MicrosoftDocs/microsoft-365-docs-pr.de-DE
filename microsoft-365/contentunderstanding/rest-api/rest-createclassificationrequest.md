---
title: Erstellen einer Klassifizierungsanforderung
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
description: Verwenden Sie die REST-API, um eine Anforderung zur Klassifizierung einer oder mehrerer Dateien mithilfe eines trainierten Dokumentverständnismodells zu erstellen.
ms.openlocfilehash: 3a796bcdb38a9a6930b51f7d585febb69082732e
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177081"
---
# <a name="create-classification-request"></a><span data-ttu-id="eb27b-103">Erstellen einer Klassifizierungsanforderung</span><span class="sxs-lookup"><span data-stu-id="eb27b-103">Create classification request</span></span>

<span data-ttu-id="eb27b-104">Erstellt eine Anforderung zur Klassifizierung einer oder mehrere Dateien unter Verwendung des angewendeten Dokumentverständnismodells (siehe [Beispiel](rest-createclassificationrequest.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="eb27b-104">Creates a request to classify one or more files using the applied document understanding model (see [example](rest-createclassificationrequest.md#examples)).</span></span>

<span data-ttu-id="eb27b-105">Der REST-Dienst in SharePoint Online (sowie in lokalen Bereitstellungen von SharePoint 2016 und höher) unterstützt die Zusammenfassung mehrerer Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="eb27b-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests.</span></span> <span data-ttu-id="eb27b-106">Anforderungen werden in einem einzelnen Dienstaufruf mithilfe der OData-Abfrageoption „$batch“ kombiniert.</span><span class="sxs-lookup"><span data-stu-id="eb27b-106">Requests are combined into a single call to the service by using the OData $batch query option.</span></span> <span data-ttu-id="eb27b-107">Diese Methode kann verwendet werden, um Arbeitselemente für Klassifizierungen für Hunderte von Dokumenten gleichzeitig in die Warteschlange zu stellen.</span><span class="sxs-lookup"><span data-stu-id="eb27b-107">This method can be used to enqueue classification work items for hundreds of documents at one time.</span></span>

## <a name="http-request"></a><span data-ttu-id="eb27b-108">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="eb27b-108">HTTP request</span></span>

```
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="eb27b-109">URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="eb27b-109">URI Parameters</span></span>

<span data-ttu-id="eb27b-110">Keine</span><span class="sxs-lookup"><span data-stu-id="eb27b-110">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="eb27b-111">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="eb27b-111">Request headers</span></span>

| <span data-ttu-id="eb27b-112">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="eb27b-112">Header</span></span> | <span data-ttu-id="eb27b-113">Wert</span><span class="sxs-lookup"><span data-stu-id="eb27b-113">Value</span></span> |
|--------|-------|
|<span data-ttu-id="eb27b-114">Annehmen</span><span class="sxs-lookup"><span data-stu-id="eb27b-114">Accept</span></span>|<span data-ttu-id="eb27b-115">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="eb27b-115">application/json;odata=verbose</span></span>|
|<span data-ttu-id="eb27b-116">Content-Type</span><span class="sxs-lookup"><span data-stu-id="eb27b-116">Content-Type</span></span>|<span data-ttu-id="eb27b-117">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="eb27b-117">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="eb27b-118">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="eb27b-118">x-requestdigest</span></span>|<span data-ttu-id="eb27b-119">Die entsprechende Digest für die aktuelle Website</span><span class="sxs-lookup"><span data-stu-id="eb27b-119">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="eb27b-120">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="eb27b-120">Request body</span></span>

|<span data-ttu-id="eb27b-121">Name</span><span class="sxs-lookup"><span data-stu-id="eb27b-121">Name</span></span>    |<span data-ttu-id="eb27b-122">Typ</span><span class="sxs-lookup"><span data-stu-id="eb27b-122">Type</span></span>   |<span data-ttu-id="eb27b-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb27b-123">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="eb27b-124">_metadata</span><span class="sxs-lookup"><span data-stu-id="eb27b-124">_metadata</span></span>|<span data-ttu-id="eb27b-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="eb27b-125">string</span></span> |<span data-ttu-id="eb27b-126">Festlegen der Objekt-Metadaten auf dem SPO.</span><span class="sxs-lookup"><span data-stu-id="eb27b-126">Set the object meta on the SPO.</span></span> <span data-ttu-id="eb27b-127">Verwenden Sie immer den Wert: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="eb27b-127">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span></span> |
|<span data-ttu-id="eb27b-128">TargetSiteId</span><span class="sxs-lookup"><span data-stu-id="eb27b-128">TargetSiteId</span></span>|<span data-ttu-id="eb27b-129">GUID</span><span class="sxs-lookup"><span data-stu-id="eb27b-129">guid</span></span>|<span data-ttu-id="eb27b-130">Die ID der Website, auf der sich die zu klassifizierende Datei befindet.</span><span class="sxs-lookup"><span data-stu-id="eb27b-130">The id of the site where the file to classify is located.</span></span>|
|<span data-ttu-id="eb27b-131">TargetWebId</span><span class="sxs-lookup"><span data-stu-id="eb27b-131">TargetWebId</span></span>|<span data-ttu-id="eb27b-132">GUID</span><span class="sxs-lookup"><span data-stu-id="eb27b-132">guid</span></span>|<span data-ttu-id="eb27b-133">Die ID des Web, auf der sich die zu klassifizierende Datei befindet.</span><span class="sxs-lookup"><span data-stu-id="eb27b-133">The id of the web where the file to classify is located.</span></span>|
|<span data-ttu-id="eb27b-134">TargetUniqueId</span><span class="sxs-lookup"><span data-stu-id="eb27b-134">TargetUniqueId</span></span>|<span data-ttu-id="eb27b-135">GUID</span><span class="sxs-lookup"><span data-stu-id="eb27b-135">guid</span></span>|<span data-ttu-id="eb27b-136">Die ID der zu klassifizierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="eb27b-136">The id of the file to classify.</span></span>|

## <a name="responses"></a><span data-ttu-id="eb27b-137">Antworten</span><span class="sxs-lookup"><span data-stu-id="eb27b-137">Responses</span></span>

| <span data-ttu-id="eb27b-138">Name</span><span class="sxs-lookup"><span data-stu-id="eb27b-138">Name</span></span>   | <span data-ttu-id="eb27b-139">Typ</span><span class="sxs-lookup"><span data-stu-id="eb27b-139">Type</span></span>  | <span data-ttu-id="eb27b-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb27b-140">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="eb27b-141">201 Erstellt</span><span class="sxs-lookup"><span data-stu-id="eb27b-141">201 Created</span></span>| |<span data-ttu-id="eb27b-142">Erfolg</span><span class="sxs-lookup"><span data-stu-id="eb27b-142">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="eb27b-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="eb27b-143">Examples</span></span>

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a><span data-ttu-id="eb27b-144">Eine Anforderung für die Klassifizierung einer Datei mit ID „e6cff8b7-c90c-4564-b5b8-033449090932“ in die Warteschlange stellen</span><span class="sxs-lookup"><span data-stu-id="eb27b-144">Enqueue a request to classify a file of id "e6cff8b7-c90c-4564-b5b8-033449090932"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="eb27b-145">Beispielanfrage</span><span class="sxs-lookup"><span data-stu-id="eb27b-145">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a><span data-ttu-id="eb27b-146">Beispielantwort</span><span class="sxs-lookup"><span data-stu-id="eb27b-146">Sample response</span></span>

<span data-ttu-id="eb27b-147">**Statuscode:** 201</span><span class="sxs-lookup"><span data-stu-id="eb27b-147">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="eb27b-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb27b-148">See also</span></span>

[<span data-ttu-id="eb27b-149">Syntex-Dokumentverständnismodell-REST-API</span><span class="sxs-lookup"><span data-stu-id="eb27b-149">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)

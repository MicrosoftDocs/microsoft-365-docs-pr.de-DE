---
title: Import Indicators API
description: Erfahren Sie, wie Sie den Importbatch der Indikator-API in Microsoft Defender for Endpoint verwenden.
keywords: apis, supported apis, submit, ti, indicator, update
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198245"
---
# <a name="import-indicators-api"></a><span data-ttu-id="1abf8-104">Import Indicators API</span><span class="sxs-lookup"><span data-stu-id="1abf8-104">Import Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1abf8-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1abf8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1abf8-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="1abf8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1abf8-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="1abf8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="1abf8-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1abf8-108">API description</span></span>
<span data-ttu-id="1abf8-109">Sendet oder aktualisiert [](ti-indicator.md) Batch von Indicator-Entitäten.</span><span class="sxs-lookup"><span data-stu-id="1abf8-109">Submits or Updates batch of [Indicator](ti-indicator.md) entities.</span></span>
<br><span data-ttu-id="1abf8-110">Die CIDR-Notation für IPs wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1abf8-110">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="1abf8-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1abf8-111">Limitations</span></span>
1. <span data-ttu-id="1abf8-112">Die Geschwindigkeitseinschränkungen für diese API liegen bei 30 Anrufen pro Minute.</span><span class="sxs-lookup"><span data-stu-id="1abf8-112">Rate limitations for this API are 30 calls per minute.</span></span>
2. <span data-ttu-id="1abf8-113">Es gibt einen Grenzwert von 15.000 aktiven [Indikatoren](ti-indicator.md) pro Mandant.</span><span class="sxs-lookup"><span data-stu-id="1abf8-113">There is a limit of 15,000 active [Indicators](ti-indicator.md) per tenant.</span></span> 
3. <span data-ttu-id="1abf8-114">Die maximale Batchgröße für einen API-Aufruf beträgt 500.</span><span class="sxs-lookup"><span data-stu-id="1abf8-114">Maximum batch size for one API call is 500.</span></span>

## <a name="permissions"></a><span data-ttu-id="1abf8-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1abf8-115">Permissions</span></span>
<span data-ttu-id="1abf8-116">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1abf8-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1abf8-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Erste Schritte](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1abf8-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="1abf8-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="1abf8-118">Permission type</span></span> |   <span data-ttu-id="1abf8-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1abf8-119">Permission</span></span>  |   <span data-ttu-id="1abf8-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1abf8-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1abf8-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="1abf8-121">Application</span></span> |   <span data-ttu-id="1abf8-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1abf8-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="1abf8-123">"Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="1abf8-123">'Read and write Indicators'</span></span>
<span data-ttu-id="1abf8-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="1abf8-124">Application</span></span> |   <span data-ttu-id="1abf8-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="1abf8-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="1abf8-126">"Alle Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="1abf8-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="1abf8-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="1abf8-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="1abf8-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1abf8-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="1abf8-129">"Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="1abf8-129">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="1abf8-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="1abf8-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a><span data-ttu-id="1abf8-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="1abf8-131">Request headers</span></span>

<span data-ttu-id="1abf8-132">Name</span><span class="sxs-lookup"><span data-stu-id="1abf8-132">Name</span></span> | <span data-ttu-id="1abf8-133">Typ</span><span class="sxs-lookup"><span data-stu-id="1abf8-133">Type</span></span> | <span data-ttu-id="1abf8-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1abf8-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="1abf8-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="1abf8-135">Authorization</span></span> | <span data-ttu-id="1abf8-136">String</span><span class="sxs-lookup"><span data-stu-id="1abf8-136">String</span></span> | <span data-ttu-id="1abf8-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1abf8-137">Bearer {token}.</span></span> <span data-ttu-id="1abf8-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="1abf8-138">**Required**.</span></span>
<span data-ttu-id="1abf8-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="1abf8-139">Content-Type</span></span> | <span data-ttu-id="1abf8-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1abf8-140">string</span></span> | <span data-ttu-id="1abf8-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="1abf8-141">application/json.</span></span> <span data-ttu-id="1abf8-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="1abf8-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="1abf8-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="1abf8-143">Request body</span></span>
<span data-ttu-id="1abf8-144">Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="1abf8-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="1abf8-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="1abf8-145">Parameter</span></span> | <span data-ttu-id="1abf8-146">Typ</span><span class="sxs-lookup"><span data-stu-id="1abf8-146">Type</span></span>    | <span data-ttu-id="1abf8-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1abf8-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="1abf8-148">Indikatoren</span><span class="sxs-lookup"><span data-stu-id="1abf8-148">Indicators</span></span> | <span data-ttu-id="1abf8-149">Auflisten<[Indikators](ti-indicator.md)></span><span class="sxs-lookup"><span data-stu-id="1abf8-149">List<[Indicator](ti-indicator.md)></span></span> | <span data-ttu-id="1abf8-150">Liste der [Indikatoren](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="1abf8-150">List of [Indicators](ti-indicator.md).</span></span> <span data-ttu-id="1abf8-151">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="1abf8-151">**Required**</span></span>


## <a name="response"></a><span data-ttu-id="1abf8-152">Antwort</span><span class="sxs-lookup"><span data-stu-id="1abf8-152">Response</span></span>
- <span data-ttu-id="1abf8-153">Wenn die Methode erfolgreich ist, gibt sie den Antwortcode 200 – OK mit einer Liste der Importergebnisse pro Indikator zurück, siehe Beispiel unten.</span><span class="sxs-lookup"><span data-stu-id="1abf8-153">If successful, this method returns 200 - OK response code with a list of import results per indicator, see example below.</span></span>
- <span data-ttu-id="1abf8-154">Wenn nicht erfolgreich: Diese Methode gibt 400 – Ungültige Anforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="1abf8-154">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="1abf8-155">Ungültige Anforderung gibt in der Regel einen falschen Textkörper an.</span><span class="sxs-lookup"><span data-stu-id="1abf8-155">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="1abf8-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1abf8-156">Example</span></span>

<span data-ttu-id="1abf8-157">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="1abf8-157">**Request**</span></span>

<span data-ttu-id="1abf8-158">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="1abf8-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

<span data-ttu-id="1abf8-159">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="1abf8-159">**Response**</span></span>

<span data-ttu-id="1abf8-160">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="1abf8-160">Here is an example of the response.</span></span>

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="1abf8-161">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="1abf8-161">Related topic</span></span>
- [<span data-ttu-id="1abf8-162">Verwalten von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="1abf8-162">Manage indicators</span></span>](manage-indicators.md)

---
title: Api "Indikatoren auflisten"
description: Erfahren Sie, wie Sie die List Indicators-API verwenden, um eine Auflistung aller aktiven Indikatoren in Microsoft Defender for Endpoint abzurufen.
keywords: apis, public api, supported apis, Indicators collection
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
ms.openlocfilehash: 868fd141cda3b3d92464a2d9247780e0e74d6de8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198553"
---
# <a name="list-indicators-api"></a><span data-ttu-id="f28e6-104">Api "Indikatoren auflisten"</span><span class="sxs-lookup"><span data-stu-id="f28e6-104">List Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f28e6-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f28e6-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f28e6-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f28e6-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f28e6-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f28e6-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f28e6-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f28e6-108">API description</span></span>
<span data-ttu-id="f28e6-109">Ruft eine Auflistung aller aktiven [Indikatoren ab.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="f28e6-109">Retrieves a collection of all active [Indicators](ti-indicator.md).</span></span>
<br><span data-ttu-id="f28e6-110">Unterstützt [OData V4-Abfragen](https://www.odata.org/documentation/).</span><span class="sxs-lookup"><span data-stu-id="f28e6-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="f28e6-111">Die OData-Abfrage ```$filter``` wird unter den Eigenschaften , , , und ```indicatorValue``` ```indicatorType``` ```creationTimeDateTimeUtc``` ```createdBy``` ```action``` ```severity``` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f28e6-111">The OData's ```$filter``` query is supported on: ```indicatorValue```, ```indicatorType```, ```creationTimeDateTimeUtc```, ```createdBy```, ```action``` and ```severity``` properties.</span></span>
<br><span data-ttu-id="f28e6-112">Beispiele finden Sie [unter OData-Abfragen mit Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="f28e6-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="f28e6-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f28e6-113">Limitations</span></span>
1. <span data-ttu-id="f28e6-114">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="f28e6-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="f28e6-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f28e6-115">Permissions</span></span>
<span data-ttu-id="f28e6-116">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f28e6-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f28e6-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Erste Schritte](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f28e6-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="f28e6-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="f28e6-118">Permission type</span></span> |   <span data-ttu-id="f28e6-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f28e6-119">Permission</span></span>  |   <span data-ttu-id="f28e6-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f28e6-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f28e6-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="f28e6-121">Application</span></span> |   <span data-ttu-id="f28e6-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f28e6-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="f28e6-123">"Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="f28e6-123">'Read and write Indicators'</span></span>
<span data-ttu-id="f28e6-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="f28e6-124">Application</span></span> |   <span data-ttu-id="f28e6-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f28e6-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="f28e6-126">"Alle Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="f28e6-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="f28e6-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="f28e6-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="f28e6-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f28e6-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="f28e6-129">"Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="f28e6-129">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="f28e6-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="f28e6-130">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="f28e6-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="f28e6-131">Request headers</span></span>

<span data-ttu-id="f28e6-132">Name</span><span class="sxs-lookup"><span data-stu-id="f28e6-132">Name</span></span> | <span data-ttu-id="f28e6-133">Typ</span><span class="sxs-lookup"><span data-stu-id="f28e6-133">Type</span></span> | <span data-ttu-id="f28e6-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f28e6-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="f28e6-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="f28e6-135">Authorization</span></span> | <span data-ttu-id="f28e6-136">String</span><span class="sxs-lookup"><span data-stu-id="f28e6-136">String</span></span> | <span data-ttu-id="f28e6-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f28e6-137">Bearer {token}.</span></span> <span data-ttu-id="f28e6-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="f28e6-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f28e6-139">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="f28e6-139">Request body</span></span>
<span data-ttu-id="f28e6-140">Empty</span><span class="sxs-lookup"><span data-stu-id="f28e6-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f28e6-141">Antwort</span><span class="sxs-lookup"><span data-stu-id="f28e6-141">Response</span></span>
<span data-ttu-id="f28e6-142">Wenn die Methode erfolgreich ist, gibt sie den Antwortcode 200, Ok mit einer Auflistung von [Indicator-Entitäten](ti-indicator.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="f28e6-142">If successful, this method returns 200, Ok response code with a collection of [Indicator](ti-indicator.md) entities.</span></span>

>[!Note]
> <span data-ttu-id="f28e6-143">Wenn die Anwendung über die Berechtigung "Ti.ReadWrite.All" verfügt, wird sie für alle Indikatoren verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="f28e6-143">If the Application has 'Ti.ReadWrite.All' permission, it will be exposed to all Indicators.</span></span> <span data-ttu-id="f28e6-144">Andernfalls wird sie nur für die erstellten Indikatoren verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="f28e6-144">Otherwise, it will be exposed only to the Indicators it created.</span></span>

## <a name="example-1"></a><span data-ttu-id="f28e6-145">Beispiel 1:</span><span class="sxs-lookup"><span data-stu-id="f28e6-145">Example 1:</span></span>

<span data-ttu-id="f28e6-146">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="f28e6-146">**Request**</span></span>

<span data-ttu-id="f28e6-147">Hier ist ein Beispiel für eine Anforderung, die alle Indikatoren ruft</span><span class="sxs-lookup"><span data-stu-id="f28e6-147">Here is an example of a request that gets all Indicators</span></span>

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

<span data-ttu-id="f28e6-148">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="f28e6-148">**Response**</span></span>

<span data-ttu-id="f28e6-149">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="f28e6-149">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "995",
            "indicatorValue": "12.13.14.15",
            "indicatorType": "IpAddress",
            "action": "Alert",
            "application": "demo-test",
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test",
            "rbacGroupNames": []
        },
        {
            "id": "996",
            "indicatorValue": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="f28e6-150">Beispiel 2:</span><span class="sxs-lookup"><span data-stu-id="f28e6-150">Example 2:</span></span>

<span data-ttu-id="f28e6-151">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="f28e6-151">**Request**</span></span>

<span data-ttu-id="f28e6-152">Hier ist ein Beispiel für eine Anforderung, die alle Indikatoren mit der Aktion "AlertAndBlock" ruft</span><span class="sxs-lookup"><span data-stu-id="f28e6-152">Here is an example of a request that gets all Indicators with 'AlertAndBlock' action</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

<span data-ttu-id="f28e6-153">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="f28e6-153">**Response**</span></span>

<span data-ttu-id="f28e6-154">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="f28e6-154">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "997",
            "indicatorValue": "111e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

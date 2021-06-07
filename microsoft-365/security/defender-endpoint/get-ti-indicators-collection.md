---
title: API für Listenindikatoren
description: Erfahren Sie, wie Sie die Listenindikatoren-API verwenden, um eine Sammlung aller aktiven Indikatoren in Microsoft Defender für Endpunkt abzurufen.
keywords: APIs, öffentliche API, unterstützte APIs, Indicators-Sammlung
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d9ec8610957af0bc7741848e7c7bd4fe850f5e32
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770424"
---
# <a name="list-indicators-api"></a><span data-ttu-id="68309-104">API für Listenindikatoren</span><span class="sxs-lookup"><span data-stu-id="68309-104">List Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="68309-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="68309-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="68309-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="68309-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="68309-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="68309-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="68309-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68309-108">API description</span></span>
<span data-ttu-id="68309-109">Ruft eine Auflistung aller aktiven [Indikatoren](ti-indicator.md)ab.</span><span class="sxs-lookup"><span data-stu-id="68309-109">Retrieves a collection of all active [Indicators](ti-indicator.md).</span></span>
<br><span data-ttu-id="68309-110">Unterstützt [OData V4-Abfragen.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="68309-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="68309-111">Die ```$filter``` OData-Abfrage wird unterstützt für: ```indicatorValue``` , , , und ```indicatorType``` ```creationTimeDateTimeUtc``` ```createdBy``` ```action``` ```severity``` Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="68309-111">The OData's ```$filter``` query is supported on: ```indicatorValue```, ```indicatorType```, ```creationTimeDateTimeUtc```, ```createdBy```, ```action``` and ```severity``` properties.</span></span>
<br><span data-ttu-id="68309-112">Beispiele für [OData-Abfragen mit Microsoft Defender für Endpunkt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="68309-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="68309-113">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="68309-113">Limitations</span></span>
1. <span data-ttu-id="68309-114">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="68309-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="68309-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="68309-115">Permissions</span></span>
<span data-ttu-id="68309-116">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="68309-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="68309-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter ["Erste Schritte".](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="68309-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="68309-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="68309-118">Permission type</span></span> |   <span data-ttu-id="68309-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="68309-119">Permission</span></span>  |   <span data-ttu-id="68309-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="68309-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="68309-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="68309-121">Application</span></span> |   <span data-ttu-id="68309-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="68309-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="68309-123">"Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="68309-123">'Read and write Indicators'</span></span>
<span data-ttu-id="68309-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="68309-124">Application</span></span> |   <span data-ttu-id="68309-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="68309-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="68309-126">"Alle Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="68309-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="68309-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="68309-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="68309-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="68309-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="68309-129">"Indikatoren lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="68309-129">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="68309-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="68309-130">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="68309-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="68309-131">Request headers</span></span>

<span data-ttu-id="68309-132">Name</span><span class="sxs-lookup"><span data-stu-id="68309-132">Name</span></span> | <span data-ttu-id="68309-133">Typ</span><span class="sxs-lookup"><span data-stu-id="68309-133">Type</span></span> | <span data-ttu-id="68309-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68309-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="68309-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="68309-135">Authorization</span></span> | <span data-ttu-id="68309-136">String</span><span class="sxs-lookup"><span data-stu-id="68309-136">String</span></span> | <span data-ttu-id="68309-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="68309-137">Bearer {token}.</span></span> <span data-ttu-id="68309-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="68309-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="68309-139">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="68309-139">Request body</span></span>
<span data-ttu-id="68309-140">Empty</span><span class="sxs-lookup"><span data-stu-id="68309-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="68309-141">Antwort</span><span class="sxs-lookup"><span data-stu-id="68309-141">Response</span></span>
<span data-ttu-id="68309-142">Bei erfolgreicher Ausführung gibt die Methode den Antwortcode 200,OK mit einer Sammlung von Indikatorentitäten zurück. [](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="68309-142">If successful, this method returns 200, Ok response code with a collection of [Indicator](ti-indicator.md) entities.</span></span>

>[!Note]
> <span data-ttu-id="68309-143">Wenn die Anwendung über die Berechtigung "Ti.ReadWrite.All" verfügt, wird sie für alle Indikatoren verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="68309-143">If the Application has 'Ti.ReadWrite.All' permission, it will be exposed to all Indicators.</span></span> <span data-ttu-id="68309-144">Andernfalls wird sie nur für die erstellten Indikatoren verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="68309-144">Otherwise, it will be exposed only to the Indicators it created.</span></span>

## <a name="example-1"></a><span data-ttu-id="68309-145">Beispiel 1:</span><span class="sxs-lookup"><span data-stu-id="68309-145">Example 1:</span></span>

<span data-ttu-id="68309-146">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="68309-146">**Request**</span></span>

<span data-ttu-id="68309-147">Hier ist ein Beispiel für eine Anforderung, die alle Indikatoren abruft.</span><span class="sxs-lookup"><span data-stu-id="68309-147">Here is an example of a request that gets all Indicators</span></span>

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

<span data-ttu-id="68309-148">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="68309-148">**Response**</span></span>

<span data-ttu-id="68309-149">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="68309-149">Here is an example of the response.</span></span>

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

## <a name="example-2"></a><span data-ttu-id="68309-150">Beispiel 2:</span><span class="sxs-lookup"><span data-stu-id="68309-150">Example 2:</span></span>

<span data-ttu-id="68309-151">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="68309-151">**Request**</span></span>

<span data-ttu-id="68309-152">Hier ist ein Beispiel für eine Anforderung, die alle Indikatoren mit der Aktion "AlertAndBlock" abruft.</span><span class="sxs-lookup"><span data-stu-id="68309-152">Here is an example of a request that gets all Indicators with 'AlertAndBlock' action</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

<span data-ttu-id="68309-153">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="68309-153">**Response**</span></span>

<span data-ttu-id="68309-154">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="68309-154">Here is an example of the response.</span></span>

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

---
title: MachineActions-API auflisten
description: Erfahren Sie, wie Sie die List MachineActions-API verwenden, um eine Sammlung von Computeraktionen in Microsoft Defender for Endpoint abzurufen.
keywords: apis, graph api, supported apis, machineaction collection
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
ms.openlocfilehash: d86303d115912d1c89b5b782bae03db4ccbba6ec
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200401"
---
# <a name="list-machineactions-api"></a><span data-ttu-id="46f84-104">Auflisten der MachineActions-API</span><span class="sxs-lookup"><span data-stu-id="46f84-104">List MachineActions API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="46f84-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="46f84-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="46f84-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="46f84-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="46f84-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="46f84-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="46f84-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46f84-108">API description</span></span>
<span data-ttu-id="46f84-109">Ruft eine Auflistung von [Computeraktionen ab.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="46f84-109">Retrieves a collection of [Machine Actions](machineaction.md).</span></span>
<br><span data-ttu-id="46f84-110">Unterstützt [OData V4-Abfragen](https://www.odata.org/documentation/).</span><span class="sxs-lookup"><span data-stu-id="46f84-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="46f84-111">Die OData-Abfrage ```$filter``` wird für: ```status``` , , und Eigenschaften ```machineId``` ```type``` ```requestor``` ```creationDateTimeUtc``` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="46f84-111">The OData's ```$filter``` query is supported on: ```status```, ```machineId```, ```type```, ```requestor``` and ```creationDateTimeUtc``` properties.</span></span>
<br><span data-ttu-id="46f84-112">Beispiele finden Sie [unter OData-Abfragen mit Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="46f84-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="46f84-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="46f84-113">Limitations</span></span>
1. <span data-ttu-id="46f84-114">Die maximale Seitengröße beträgt 10.000.</span><span class="sxs-lookup"><span data-stu-id="46f84-114">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="46f84-115">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="46f84-115">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="46f84-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="46f84-116">Permissions</span></span>
<span data-ttu-id="46f84-117">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="46f84-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="46f84-118">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="46f84-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="46f84-119">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="46f84-119">Permission type</span></span> |   <span data-ttu-id="46f84-120">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="46f84-120">Permission</span></span>  |   <span data-ttu-id="46f84-121">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="46f84-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="46f84-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="46f84-122">Application</span></span> |   <span data-ttu-id="46f84-123">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="46f84-123">Machine.Read.All</span></span> |  <span data-ttu-id="46f84-124">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="46f84-124">'Read all machine profiles'</span></span>
<span data-ttu-id="46f84-125">Anwendung</span><span class="sxs-lookup"><span data-stu-id="46f84-125">Application</span></span> |   <span data-ttu-id="46f84-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="46f84-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="46f84-127">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="46f84-127">'Read and write all machine information'</span></span>
<span data-ttu-id="46f84-128">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="46f84-128">Delegated (work or school account)</span></span> | <span data-ttu-id="46f84-129">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="46f84-129">Machine.Read</span></span> | <span data-ttu-id="46f84-130">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="46f84-130">'Read machine information'</span></span>
<span data-ttu-id="46f84-131">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="46f84-131">Delegated (work or school account)</span></span> | <span data-ttu-id="46f84-132">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="46f84-132">Machine.ReadWrite</span></span> | <span data-ttu-id="46f84-133">"Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="46f84-133">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="46f84-134">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="46f84-134">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="46f84-135">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="46f84-135">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="46f84-136">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="46f84-136">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

## <a name="request-headers"></a><span data-ttu-id="46f84-137">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="46f84-137">Request headers</span></span>

<span data-ttu-id="46f84-138">Name</span><span class="sxs-lookup"><span data-stu-id="46f84-138">Name</span></span> | <span data-ttu-id="46f84-139">Typ</span><span class="sxs-lookup"><span data-stu-id="46f84-139">Type</span></span> | <span data-ttu-id="46f84-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46f84-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="46f84-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="46f84-141">Authorization</span></span> | <span data-ttu-id="46f84-142">String</span><span class="sxs-lookup"><span data-stu-id="46f84-142">String</span></span> | <span data-ttu-id="46f84-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="46f84-143">Bearer {token}.</span></span> <span data-ttu-id="46f84-144">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="46f84-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="46f84-145">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="46f84-145">Request body</span></span>
<span data-ttu-id="46f84-146">Empty</span><span class="sxs-lookup"><span data-stu-id="46f84-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="46f84-147">Antwort</span><span class="sxs-lookup"><span data-stu-id="46f84-147">Response</span></span>
<span data-ttu-id="46f84-148">Wenn die Methode erfolgreich ist, gibt sie den Antwortcode 200, Ok mit einer Auflistung von [machineAction-Entitäten](machineaction.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="46f84-148">If successful, this method returns 200, Ok response code with a collection of [machineAction](machineaction.md) entities.</span></span>


## <a name="example-1"></a><span data-ttu-id="46f84-149">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="46f84-149">Example 1</span></span>

<span data-ttu-id="46f84-150">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="46f84-150">**Request**</span></span>

<span data-ttu-id="46f84-151">Im Folgenden finden Sie ein Beispiel für die Anforderung für eine Organisation mit drei MachineActions.</span><span class="sxs-lookup"><span data-stu-id="46f84-151">Here is an example of the request on an organization that has three MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

<span data-ttu-id="46f84-152">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="46f84-152">**Response**</span></span>

<span data-ttu-id="46f84-153">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="46f84-153">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        },
        {
            "id": "44cffc15-0e3d-4cbf-96aa-bf76f9b27f5e",
            "type": "StopAndQuarantineFile",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:15:40.6052029Z",
            "lastUpdateTimeUtc": "2018-12-04T12:16:14.2899973Z",
            "relatedFileInfo": {
                "fileIdentifier": "a0c659857ccbe457fdaf5fe21d54efdcbf6f6508",
                "fileIdentifierType": "Sha1"
            }
        }
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="46f84-154">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="46f84-154">Example 2</span></span>

<span data-ttu-id="46f84-155">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="46f84-155">**Request**</span></span>

<span data-ttu-id="46f84-156">Hier ist ein Beispiel für eine Anforderung, die MachineActions nach Computer-ID filtert und die neuesten beiden MachineActions zeigt.</span><span class="sxs-lookup"><span data-stu-id="46f84-156">Here is an example of a request that filters the MachineActions by machine ID and shows the latest two MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions?$filter=machineId eq 'f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f'&$top=2
```

<span data-ttu-id="46f84-157">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="46f84-157">**Response**</span></span>

<span data-ttu-id="46f84-158">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="46f84-158">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="46f84-159">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="46f84-159">Related topics</span></span>
- [<span data-ttu-id="46f84-160">OData-Abfragen mit Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="46f84-160">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)

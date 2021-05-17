---
title: Computer-API auflisten
description: Hier erfahren Sie, wie Sie die Api "Computer auflisten" verwenden, um eine Sammlung von Computern abzurufen, die mit der Microsoft Defender for Endpoint-Cloud kommuniziert haben.
keywords: apis, graph api, supported apis, get, devices
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
ms.openlocfilehash: 01e36427116ad7bd845901e7da7f5aa152bd44f9
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893353"
---
# <a name="list-machines-api"></a><span data-ttu-id="54eb5-104">Computer-API auflisten</span><span class="sxs-lookup"><span data-stu-id="54eb5-104">List machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="54eb5-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="54eb5-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="54eb5-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="54eb5-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="54eb5-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="54eb5-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="54eb5-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54eb5-108">API description</span></span>
<span data-ttu-id="54eb5-109">Ruft eine Sammlung von Computern [ab,](machine.md) die mit der Microsoft Defender for Endpoint-Cloud kommuniziert haben.</span><span class="sxs-lookup"><span data-stu-id="54eb5-109">Retrieves a collection of [Machines](machine.md) that have communicated with  Microsoft Defender for Endpoint cloud.</span></span>
<br><span data-ttu-id="54eb5-110">Unterstützt [OData V4-Abfragen](https://www.odata.org/documentation/).</span><span class="sxs-lookup"><span data-stu-id="54eb5-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="54eb5-111">Die OData-Abfrage `$filter` wird unterstützt unter: , `computerDnsName` , , , und `lastSeen` `healthStatus` `osPlatform` `riskScore` `rbacGroupId` .</span><span class="sxs-lookup"><span data-stu-id="54eb5-111">The OData's `$filter` query is supported on: `computerDnsName`, `lastSeen`, `healthStatus`, `osPlatform`, `riskScore` and `rbacGroupId`.</span></span>
<br><span data-ttu-id="54eb5-112">Beispiele finden Sie unter [OData-Abfragen mit Defender for Endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="54eb5-112">See examples at [OData queries with Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="54eb5-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="54eb5-113">Limitations</span></span>
1. <span data-ttu-id="54eb5-114">Sie können Geräte nach Ihrem konfigurierten Aufbewahrungszeitraum zuletzt sehen.</span><span class="sxs-lookup"><span data-stu-id="54eb5-114">You can get devices last seen according to your configured retention period.</span></span>
2. <span data-ttu-id="54eb5-115">Die maximale Seitengröße beträgt 10.000.</span><span class="sxs-lookup"><span data-stu-id="54eb5-115">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="54eb5-116">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="54eb5-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="54eb5-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="54eb5-117">Permissions</span></span>

<span data-ttu-id="54eb5-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="54eb5-118">Permission type</span></span> |   <span data-ttu-id="54eb5-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="54eb5-119">Permission</span></span>  |   <span data-ttu-id="54eb5-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="54eb5-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="54eb5-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="54eb5-121">Application</span></span> |   <span data-ttu-id="54eb5-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="54eb5-122">Machine.Read.All</span></span> |  <span data-ttu-id="54eb5-123">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="54eb5-123">'Read all machine profiles'</span></span>
<span data-ttu-id="54eb5-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="54eb5-124">Application</span></span> |   <span data-ttu-id="54eb5-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="54eb5-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="54eb5-126">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="54eb5-126">'Read and write all machine information'</span></span>
<span data-ttu-id="54eb5-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="54eb5-127">Delegated (work or school account)</span></span> | <span data-ttu-id="54eb5-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="54eb5-128">Machine.Read</span></span> | <span data-ttu-id="54eb5-129">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="54eb5-129">'Read machine information'</span></span>
<span data-ttu-id="54eb5-130">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="54eb5-130">Delegated (work or school account)</span></span> | <span data-ttu-id="54eb5-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="54eb5-131">Machine.ReadWrite</span></span> | <span data-ttu-id="54eb5-132">"Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="54eb5-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="54eb5-133">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="54eb5-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="54eb5-134">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="54eb5-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="54eb5-135">Die Antwort umfasst nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="54eb5-135">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="54eb5-136">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="54eb5-136">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a><span data-ttu-id="54eb5-137">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="54eb5-137">Request headers</span></span>

<span data-ttu-id="54eb5-138">Name</span><span class="sxs-lookup"><span data-stu-id="54eb5-138">Name</span></span> | <span data-ttu-id="54eb5-139">Typ</span><span class="sxs-lookup"><span data-stu-id="54eb5-139">Type</span></span> | <span data-ttu-id="54eb5-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54eb5-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="54eb5-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="54eb5-141">Authorization</span></span> | <span data-ttu-id="54eb5-142">String</span><span class="sxs-lookup"><span data-stu-id="54eb5-142">String</span></span> | <span data-ttu-id="54eb5-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="54eb5-143">Bearer {token}.</span></span> <span data-ttu-id="54eb5-144">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="54eb5-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="54eb5-145">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="54eb5-145">Request body</span></span>
<span data-ttu-id="54eb5-146">Empty</span><span class="sxs-lookup"><span data-stu-id="54eb5-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="54eb5-147">Antwort</span><span class="sxs-lookup"><span data-stu-id="54eb5-147">Response</span></span>
<span data-ttu-id="54eb5-148">Wenn erfolgreich und Computer vorhanden sind – [](machine.md) 200 OK mit der Liste der Computerentitäten im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="54eb5-148">If successful and machines exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="54eb5-149">Wenn keine aktuellen Computer – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="54eb5-149">If no recent machines - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="54eb5-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="54eb5-150">Example</span></span>

<span data-ttu-id="54eb5-151">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="54eb5-151">**Request**</span></span>

<span data-ttu-id="54eb5-152">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="54eb5-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

<span data-ttu-id="54eb5-153">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="54eb5-153">**Response**</span></span>

<span data-ttu-id="54eb5-154">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="54eb5-154">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="54eb5-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="54eb5-155">Related topics</span></span>
- [<span data-ttu-id="54eb5-156">OData-Abfragen mit Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="54eb5-156">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)

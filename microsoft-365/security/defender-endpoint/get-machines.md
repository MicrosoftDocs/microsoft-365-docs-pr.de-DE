---
title: Computer-API auflisten
description: Erfahren Sie, wie Sie die Computer-API für Listen verwenden, um eine Sammlung von Computern abzurufen, die mit der Microsoft Defender für Endpunkt-Cloud kommuniziert haben.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Geräte
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f06973bc45ecac05c15d48afe5f0e2e9e7788f78
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770746"
---
# <a name="list-machines-api"></a><span data-ttu-id="cdd66-104">Computer-API auflisten</span><span class="sxs-lookup"><span data-stu-id="cdd66-104">List machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cdd66-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="cdd66-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="cdd66-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="cdd66-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cdd66-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cdd66-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="cdd66-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cdd66-108">API description</span></span>
<span data-ttu-id="cdd66-109">Ruft eine Sammlung von [Computern](machine.md) ab, die mit der Microsoft Defender für Endpunkt-Cloud kommuniziert haben.</span><span class="sxs-lookup"><span data-stu-id="cdd66-109">Retrieves a collection of [Machines](machine.md) that have communicated with  Microsoft Defender for Endpoint cloud.</span></span>
<br><span data-ttu-id="cdd66-110">Unterstützt [OData V4-Abfragen.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="cdd66-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="cdd66-111">Die `$filter` OData-Abfrage wird unterstützt für: `computerDnsName` , , , und `lastSeen` `healthStatus` `osPlatform` `riskScore` `rbacGroupId` .</span><span class="sxs-lookup"><span data-stu-id="cdd66-111">The OData's `$filter` query is supported on: `computerDnsName`, `lastSeen`, `healthStatus`, `osPlatform`, `riskScore` and `rbacGroupId`.</span></span>
<br><span data-ttu-id="cdd66-112">Beispiele für [OData-Abfragen mit Defender für Endpunkt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="cdd66-112">See examples at [OData queries with Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="cdd66-113">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="cdd66-113">Limitations</span></span>
1. <span data-ttu-id="cdd66-114">Sie können Geräte abrufen, die zuletzt gemäß Ihrem konfigurierten Aufbewahrungszeitraum angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="cdd66-114">You can get devices last seen according to your configured retention period.</span></span>
2. <span data-ttu-id="cdd66-115">Die maximale Seitengröße beträgt 10.000.</span><span class="sxs-lookup"><span data-stu-id="cdd66-115">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="cdd66-116">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="cdd66-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="cdd66-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="cdd66-117">Permissions</span></span>

<span data-ttu-id="cdd66-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="cdd66-118">Permission type</span></span> |   <span data-ttu-id="cdd66-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="cdd66-119">Permission</span></span>  |   <span data-ttu-id="cdd66-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="cdd66-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cdd66-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="cdd66-121">Application</span></span> |   <span data-ttu-id="cdd66-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="cdd66-122">Machine.Read.All</span></span> |  <span data-ttu-id="cdd66-123">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="cdd66-123">'Read all machine profiles'</span></span>
<span data-ttu-id="cdd66-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="cdd66-124">Application</span></span> |   <span data-ttu-id="cdd66-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cdd66-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="cdd66-126">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="cdd66-126">'Read and write all machine information'</span></span>
<span data-ttu-id="cdd66-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="cdd66-127">Delegated (work or school account)</span></span> | <span data-ttu-id="cdd66-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="cdd66-128">Machine.Read</span></span> | <span data-ttu-id="cdd66-129">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="cdd66-129">'Read machine information'</span></span>
<span data-ttu-id="cdd66-130">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="cdd66-130">Delegated (work or school account)</span></span> | <span data-ttu-id="cdd66-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="cdd66-131">Machine.ReadWrite</span></span> | <span data-ttu-id="cdd66-132">"Lesen und Schreiben von Computerinformationen"</span><span class="sxs-lookup"><span data-stu-id="cdd66-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="cdd66-133">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="cdd66-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="cdd66-134">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="cdd66-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="cdd66-135">Die Antwort enthält nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="cdd66-135">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="cdd66-136">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="cdd66-136">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a><span data-ttu-id="cdd66-137">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="cdd66-137">Request headers</span></span>

<span data-ttu-id="cdd66-138">Name</span><span class="sxs-lookup"><span data-stu-id="cdd66-138">Name</span></span> | <span data-ttu-id="cdd66-139">Typ</span><span class="sxs-lookup"><span data-stu-id="cdd66-139">Type</span></span> | <span data-ttu-id="cdd66-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cdd66-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="cdd66-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="cdd66-141">Authorization</span></span> | <span data-ttu-id="cdd66-142">String</span><span class="sxs-lookup"><span data-stu-id="cdd66-142">String</span></span> | <span data-ttu-id="cdd66-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="cdd66-143">Bearer {token}.</span></span> <span data-ttu-id="cdd66-144">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="cdd66-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="cdd66-145">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="cdd66-145">Request body</span></span>
<span data-ttu-id="cdd66-146">Empty</span><span class="sxs-lookup"><span data-stu-id="cdd66-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cdd66-147">Antwort</span><span class="sxs-lookup"><span data-stu-id="cdd66-147">Response</span></span>
<span data-ttu-id="cdd66-148">Wenn erfolgreich und Computer vorhanden – 200 OK mit liste der Computerentitäten im Textkörper. [](machine.md)</span><span class="sxs-lookup"><span data-stu-id="cdd66-148">If successful and machines exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="cdd66-149">Wenn keine aktuellen Computer – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="cdd66-149">If no recent machines - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="cdd66-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cdd66-150">Example</span></span>

<span data-ttu-id="cdd66-151">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="cdd66-151">**Request**</span></span>

<span data-ttu-id="cdd66-152">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cdd66-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

<span data-ttu-id="cdd66-153">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="cdd66-153">**Response**</span></span>

<span data-ttu-id="cdd66-154">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="cdd66-154">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="cdd66-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cdd66-155">Related topics</span></span>
- [<span data-ttu-id="cdd66-156">OData-Abfragen mit Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cdd66-156">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)

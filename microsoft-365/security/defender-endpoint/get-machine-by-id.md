---
title: Abrufen des Computers nach ID-API
description: Erfahren Sie, wie Sie die Api Computer nach ID abrufen verwenden, um einen Computer mithilfe der Geräte-ID oder des Computernamens in Microsoft Defender for Endpoint abzurufen.
keywords: apis, graph api, supported apis, get, devices, entity, id
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
ms.openlocfilehash: 29423230d0d8d4baaa1acca9a3661dc3436f303d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200094"
---
# <a name="get-machine-by-id-api"></a><span data-ttu-id="229d1-104">Abrufen des Computers nach ID-API</span><span class="sxs-lookup"><span data-stu-id="229d1-104">Get machine by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="229d1-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="229d1-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>


> <span data-ttu-id="229d1-106">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="229d1-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="229d1-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="229d1-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="229d1-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="229d1-108">API description</span></span>
<span data-ttu-id="229d1-109">Ruft einen [bestimmten Computer über](machine.md) die Geräte-ID oder den Computernamen ab.</span><span class="sxs-lookup"><span data-stu-id="229d1-109">Retrieves specific [Machine](machine.md) by its device ID or computer name.</span></span>


## <a name="limitations"></a><span data-ttu-id="229d1-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="229d1-110">Limitations</span></span>
1. <span data-ttu-id="229d1-111">Sie können Geräte gemäß Ihrer konfigurierten Aufbewahrungsrichtlinie zuletzt sehen.</span><span class="sxs-lookup"><span data-stu-id="229d1-111">You can get devices last seen according to your configured retention policy.</span></span>
2. <span data-ttu-id="229d1-112">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="229d1-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="229d1-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="229d1-113">Permissions</span></span>
<span data-ttu-id="229d1-114">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="229d1-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="229d1-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="229d1-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="229d1-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="229d1-116">Permission type</span></span> |   <span data-ttu-id="229d1-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="229d1-117">Permission</span></span>  |   <span data-ttu-id="229d1-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="229d1-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="229d1-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="229d1-119">Application</span></span> |   <span data-ttu-id="229d1-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="229d1-120">Machine.Read.All</span></span> |  <span data-ttu-id="229d1-121">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="229d1-121">'Read all machine profiles'</span></span>
<span data-ttu-id="229d1-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="229d1-122">Application</span></span> |   <span data-ttu-id="229d1-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="229d1-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="229d1-124">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="229d1-124">'Read and write all machine information'</span></span>
<span data-ttu-id="229d1-125">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="229d1-125">Delegated (work or school account)</span></span> | <span data-ttu-id="229d1-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="229d1-126">Machine.Read</span></span> | <span data-ttu-id="229d1-127">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="229d1-127">'Read machine information'</span></span>
<span data-ttu-id="229d1-128">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="229d1-128">Delegated (work or school account)</span></span> | <span data-ttu-id="229d1-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="229d1-129">Machine.ReadWrite</span></span> | <span data-ttu-id="229d1-130">"Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="229d1-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="229d1-131">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="229d1-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="229d1-132">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="229d1-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="229d1-133">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="229d1-133">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="229d1-134">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="229d1-134">HTTP request</span></span>
```http
GET /api/machines/{id}
```

## <a name="request-headers"></a><span data-ttu-id="229d1-135">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="229d1-135">Request headers</span></span>

<span data-ttu-id="229d1-136">Name</span><span class="sxs-lookup"><span data-stu-id="229d1-136">Name</span></span> | <span data-ttu-id="229d1-137">Typ</span><span class="sxs-lookup"><span data-stu-id="229d1-137">Type</span></span> | <span data-ttu-id="229d1-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="229d1-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="229d1-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="229d1-139">Authorization</span></span> | <span data-ttu-id="229d1-140">String</span><span class="sxs-lookup"><span data-stu-id="229d1-140">String</span></span> | <span data-ttu-id="229d1-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="229d1-141">Bearer {token}.</span></span> <span data-ttu-id="229d1-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="229d1-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="229d1-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="229d1-143">Request body</span></span>
<span data-ttu-id="229d1-144">Empty</span><span class="sxs-lookup"><span data-stu-id="229d1-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="229d1-145">Antwort</span><span class="sxs-lookup"><span data-stu-id="229d1-145">Response</span></span>
<span data-ttu-id="229d1-146">Wenn erfolgreich und Gerät vorhanden ist – 200 OK mit der [Computerentität](machine.md) im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="229d1-146">If successful and device exists - 200 OK with the [machine](machine.md) entity in the body.</span></span>
<span data-ttu-id="229d1-147">Wenn computer mit der angegebenen ID nicht gefunden wurde - 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="229d1-147">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="229d1-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="229d1-148">Example</span></span>

<span data-ttu-id="229d1-149">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="229d1-149">**Request**</span></span>

<span data-ttu-id="229d1-150">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="229d1-150">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07
```

<span data-ttu-id="229d1-151">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="229d1-151">**Response**</span></span>

<span data-ttu-id="229d1-152">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="229d1-152">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machine",
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

```

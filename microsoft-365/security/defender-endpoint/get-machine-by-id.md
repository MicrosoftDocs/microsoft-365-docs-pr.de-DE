---
title: Abrufen des Computers nach ID-API
description: Erfahren Sie, wie Sie die API "Computer nach ID abrufen" verwenden, um einen Computer anhand seiner Geräte-ID oder des Computernamens in Microsoft Defender für Endpunkt abzurufen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Geräte, Entität, ID
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
ms.openlocfilehash: e4ed5a68b0f4c5e9472702d3cc2798a810e4f84e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769473"
---
# <a name="get-machine-by-id-api"></a><span data-ttu-id="cdf6e-104">Abrufen des Computers nach ID-API</span><span class="sxs-lookup"><span data-stu-id="cdf6e-104">Get machine by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cdf6e-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="cdf6e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>


> <span data-ttu-id="cdf6e-106">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="cdf6e-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cdf6e-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cdf6e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="cdf6e-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cdf6e-108">API description</span></span>
<span data-ttu-id="cdf6e-109">Ruft einen bestimmten [Computer](machine.md) anhand seiner Geräte-ID oder des Computernamens ab.</span><span class="sxs-lookup"><span data-stu-id="cdf6e-109">Retrieves specific [Machine](machine.md) by its device ID or computer name.</span></span>


## <a name="limitations"></a><span data-ttu-id="cdf6e-110">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="cdf6e-110">Limitations</span></span>
1. <span data-ttu-id="cdf6e-111">Sie können Geräte abrufen, die zuletzt gemäß Ihrer konfigurierten Aufbewahrungsrichtlinie angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="cdf6e-111">You can get devices last seen according to your configured retention policy.</span></span>
2. <span data-ttu-id="cdf6e-112">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="cdf6e-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="cdf6e-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="cdf6e-113">Permissions</span></span>
<span data-ttu-id="cdf6e-114">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="cdf6e-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cdf6e-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cdf6e-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="cdf6e-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="cdf6e-116">Permission type</span></span> |   <span data-ttu-id="cdf6e-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="cdf6e-117">Permission</span></span>  |   <span data-ttu-id="cdf6e-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="cdf6e-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cdf6e-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="cdf6e-119">Application</span></span> |   <span data-ttu-id="cdf6e-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="cdf6e-120">Machine.Read.All</span></span> |  <span data-ttu-id="cdf6e-121">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="cdf6e-121">'Read all machine profiles'</span></span>
<span data-ttu-id="cdf6e-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="cdf6e-122">Application</span></span> |   <span data-ttu-id="cdf6e-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cdf6e-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="cdf6e-124">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="cdf6e-124">'Read and write all machine information'</span></span>
<span data-ttu-id="cdf6e-125">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="cdf6e-125">Delegated (work or school account)</span></span> | <span data-ttu-id="cdf6e-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="cdf6e-126">Machine.Read</span></span> | <span data-ttu-id="cdf6e-127">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="cdf6e-127">'Read machine information'</span></span>
<span data-ttu-id="cdf6e-128">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="cdf6e-128">Delegated (work or school account)</span></span> | <span data-ttu-id="cdf6e-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="cdf6e-129">Machine.ReadWrite</span></span> | <span data-ttu-id="cdf6e-130">"Lesen und Schreiben von Computerinformationen"</span><span class="sxs-lookup"><span data-stu-id="cdf6e-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="cdf6e-131">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="cdf6e-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="cdf6e-132">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="cdf6e-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="cdf6e-133">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="cdf6e-133">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="cdf6e-134">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="cdf6e-134">HTTP request</span></span>
```http
GET /api/machines/{id}
```

## <a name="request-headers"></a><span data-ttu-id="cdf6e-135">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="cdf6e-135">Request headers</span></span>

<span data-ttu-id="cdf6e-136">Name</span><span class="sxs-lookup"><span data-stu-id="cdf6e-136">Name</span></span> | <span data-ttu-id="cdf6e-137">Typ</span><span class="sxs-lookup"><span data-stu-id="cdf6e-137">Type</span></span> | <span data-ttu-id="cdf6e-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cdf6e-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="cdf6e-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="cdf6e-139">Authorization</span></span> | <span data-ttu-id="cdf6e-140">String</span><span class="sxs-lookup"><span data-stu-id="cdf6e-140">String</span></span> | <span data-ttu-id="cdf6e-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="cdf6e-141">Bearer {token}.</span></span> <span data-ttu-id="cdf6e-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="cdf6e-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="cdf6e-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="cdf6e-143">Request body</span></span>
<span data-ttu-id="cdf6e-144">Empty</span><span class="sxs-lookup"><span data-stu-id="cdf6e-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cdf6e-145">Antwort</span><span class="sxs-lookup"><span data-stu-id="cdf6e-145">Response</span></span>
<span data-ttu-id="cdf6e-146">Wenn erfolgreich und Gerät vorhanden – 200 OK mit der [Computerentität](machine.md) im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="cdf6e-146">If successful and device exists - 200 OK with the [machine](machine.md) entity in the body.</span></span>
<span data-ttu-id="cdf6e-147">Wenn der Computer mit der angegebenen ID nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="cdf6e-147">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="cdf6e-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cdf6e-148">Example</span></span>

<span data-ttu-id="cdf6e-149">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="cdf6e-149">**Request**</span></span>

<span data-ttu-id="cdf6e-150">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cdf6e-150">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07
```

<span data-ttu-id="cdf6e-151">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="cdf6e-151">**Response**</span></span>

<span data-ttu-id="cdf6e-152">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="cdf6e-152">Here is an example of the response.</span></span>


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

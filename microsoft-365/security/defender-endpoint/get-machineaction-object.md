---
title: Abrufen der MachineAction-Objekt-API
description: Erfahren Sie, wie Sie die MachineAction-API abrufen verwenden, um eine bestimmte Computeraktion nach ihrer ID in Microsoft Defender for Endpoint abzurufen.
keywords: apis, graph api, supported apis, machineaction object
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
ms.openlocfilehash: 180179d5b1362ad4952618148b11007aa9efe91c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200065"
---
# <a name="get-machineaction-api"></a><span data-ttu-id="cbd31-104">MachineAction-API abrufen</span><span class="sxs-lookup"><span data-stu-id="cbd31-104">Get machineAction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cbd31-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="cbd31-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="cbd31-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="cbd31-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cbd31-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cbd31-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="cbd31-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cbd31-108">API description</span></span>
<span data-ttu-id="cbd31-109">Ruft eine bestimmte [Computeraktion nach](machineaction.md) ihrer ID ab.</span><span class="sxs-lookup"><span data-stu-id="cbd31-109">Retrieves specific [Machine Action](machineaction.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="cbd31-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="cbd31-110">Limitations</span></span>
1. <span data-ttu-id="cbd31-111">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="cbd31-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="cbd31-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="cbd31-112">Permissions</span></span>
<span data-ttu-id="cbd31-113">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cbd31-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cbd31-114">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cbd31-114">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="cbd31-115">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="cbd31-115">Permission type</span></span> |   <span data-ttu-id="cbd31-116">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="cbd31-116">Permission</span></span>  |   <span data-ttu-id="cbd31-117">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="cbd31-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cbd31-118">Anwendung</span><span class="sxs-lookup"><span data-stu-id="cbd31-118">Application</span></span> |   <span data-ttu-id="cbd31-119">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="cbd31-119">Machine.Read.All</span></span> |  <span data-ttu-id="cbd31-120">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="cbd31-120">'Read all machine profiles'</span></span>
<span data-ttu-id="cbd31-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="cbd31-121">Application</span></span> |   <span data-ttu-id="cbd31-122">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cbd31-122">Machine.ReadWrite.All</span></span> | <span data-ttu-id="cbd31-123">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="cbd31-123">'Read and write all machine information'</span></span>
<span data-ttu-id="cbd31-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="cbd31-124">Delegated (work or school account)</span></span> | <span data-ttu-id="cbd31-125">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="cbd31-125">Machine.Read</span></span> | <span data-ttu-id="cbd31-126">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="cbd31-126">'Read machine information'</span></span>
<span data-ttu-id="cbd31-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="cbd31-127">Delegated (work or school account)</span></span> | <span data-ttu-id="cbd31-128">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="cbd31-128">Machine.ReadWrite</span></span> | <span data-ttu-id="cbd31-129">"Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="cbd31-129">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="cbd31-130">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="cbd31-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="cbd31-131">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="cbd31-131">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="cbd31-132">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="cbd31-132">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions/{id}
```

## <a name="request-headers"></a><span data-ttu-id="cbd31-133">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="cbd31-133">Request headers</span></span>

<span data-ttu-id="cbd31-134">Name</span><span class="sxs-lookup"><span data-stu-id="cbd31-134">Name</span></span> | <span data-ttu-id="cbd31-135">Typ</span><span class="sxs-lookup"><span data-stu-id="cbd31-135">Type</span></span> | <span data-ttu-id="cbd31-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cbd31-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="cbd31-137">Authorization</span><span class="sxs-lookup"><span data-stu-id="cbd31-137">Authorization</span></span> | <span data-ttu-id="cbd31-138">String</span><span class="sxs-lookup"><span data-stu-id="cbd31-138">String</span></span> | <span data-ttu-id="cbd31-139">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="cbd31-139">Bearer {token}.</span></span> <span data-ttu-id="cbd31-140">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="cbd31-140">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="cbd31-141">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="cbd31-141">Request body</span></span>
<span data-ttu-id="cbd31-142">Empty</span><span class="sxs-lookup"><span data-stu-id="cbd31-142">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cbd31-143">Antwort</span><span class="sxs-lookup"><span data-stu-id="cbd31-143">Response</span></span>
<span data-ttu-id="cbd31-144">Wenn die Methode erfolgreich ist, gibt sie den Antwortcode 200, Ok mit einer [Machine Action-Entität](machineaction.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="cbd31-144">If successful, this method returns 200, Ok response code with a [Machine Action](machineaction.md) entity.</span></span> <span data-ttu-id="cbd31-145">Wenn die Entität computeraktion mit der angegebenen ID nicht gefunden wurde - 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="cbd31-145">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="cbd31-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cbd31-146">Example</span></span>

<span data-ttu-id="cbd31-147">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="cbd31-147">**Request**</span></span>

<span data-ttu-id="cbd31-148">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cbd31-148">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions/2e9da30d-27f6-4208-81f2-9cd3d67893ba
```

<span data-ttu-id="cbd31-149">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="cbd31-149">**Response**</span></span>

<span data-ttu-id="cbd31-150">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="cbd31-150">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
    "type": "Isolate",
    "scope": "Selective",
    "requestor": "Analyst@TestPrd.onmicrosoft.com",
    "requestorComment": "test for docs",
    "status": "Succeeded",
    "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
    "computerDnsName": "desktop-test",
    "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
    "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
    "relatedFileInfo": null
}


```

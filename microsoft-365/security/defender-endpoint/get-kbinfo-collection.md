---
title: Abrufen der KB-Auflistungs-API
description: Rufen Sie eine Sammlung von Wissensdatenbanken (KB) und KB-Details mit Microsoft Defender for Endpoint ab.
keywords: apis, graph api, supported apis, get, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166728"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="0588a-104">Abrufen der KB-Auflistungs-API</span><span class="sxs-lookup"><span data-stu-id="0588a-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0588a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0588a-105">**Applies to:**</span></span>
- [<span data-ttu-id="0588a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0588a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0588a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0588a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0588a-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0588a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0588a-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0588a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="0588a-110">Ruft eine Auflistung von KB- und KB-Details ab.</span><span class="sxs-lookup"><span data-stu-id="0588a-110">Retrieves a collection of KB's and KB details.</span></span>

## <a name="permissions"></a><span data-ttu-id="0588a-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0588a-111">Permissions</span></span>
<span data-ttu-id="0588a-112">Der Benutzer benötigt Leseberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="0588a-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="0588a-113">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="0588a-113">HTTP request</span></span>
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a><span data-ttu-id="0588a-114">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="0588a-114">Request headers</span></span>

<span data-ttu-id="0588a-115">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="0588a-115">Header</span></span> | <span data-ttu-id="0588a-116">Wert</span><span class="sxs-lookup"><span data-stu-id="0588a-116">Value</span></span> 
:---|:---
<span data-ttu-id="0588a-117">Authorization</span><span class="sxs-lookup"><span data-stu-id="0588a-117">Authorization</span></span> | <span data-ttu-id="0588a-118">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="0588a-118">Bearer {token}.</span></span> <span data-ttu-id="0588a-119">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0588a-119">**Required**.</span></span>
<span data-ttu-id="0588a-120">Inhaltstyp</span><span class="sxs-lookup"><span data-stu-id="0588a-120">Content type</span></span> | <span data-ttu-id="0588a-121">application/json</span><span class="sxs-lookup"><span data-stu-id="0588a-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="0588a-122">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="0588a-122">Request body</span></span>
<span data-ttu-id="0588a-123">Empty</span><span class="sxs-lookup"><span data-stu-id="0588a-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0588a-124">Antwort</span><span class="sxs-lookup"><span data-stu-id="0588a-124">Response</span></span>
<span data-ttu-id="0588a-125">Wenn erfolgreich – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="0588a-125">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="0588a-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0588a-126">Example</span></span>

<span data-ttu-id="0588a-127">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="0588a-127">**Request**</span></span>

<span data-ttu-id="0588a-128">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="0588a-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

<span data-ttu-id="0588a-129">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="0588a-129">**Response**</span></span>

<span data-ttu-id="0588a-130">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="0588a-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```

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
# <a name="get-kb-collection-api"></a><span data-ttu-id="b897e-104">Abrufen der KB-Auflistungs-API</span><span class="sxs-lookup"><span data-stu-id="b897e-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b897e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b897e-105">**Applies to:**</span></span>
- [<span data-ttu-id="b897e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b897e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b897e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b897e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b897e-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b897e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b897e-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b897e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b897e-110">Ruft eine Auflistung von KB- und KB-Details ab.</span><span class="sxs-lookup"><span data-stu-id="b897e-110">Retrieves a collection of KB's and KB details.</span></span>

## <a name="permissions"></a><span data-ttu-id="b897e-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b897e-111">Permissions</span></span>
<span data-ttu-id="b897e-112">Der Benutzer benötigt Leseberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="b897e-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="b897e-113">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="b897e-113">HTTP request</span></span>
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a><span data-ttu-id="b897e-114">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="b897e-114">Request headers</span></span>

<span data-ttu-id="b897e-115">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="b897e-115">Header</span></span> | <span data-ttu-id="b897e-116">Wert</span><span class="sxs-lookup"><span data-stu-id="b897e-116">Value</span></span> 
:---|:---
<span data-ttu-id="b897e-117">Authorization</span><span class="sxs-lookup"><span data-stu-id="b897e-117">Authorization</span></span> | <span data-ttu-id="b897e-118">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b897e-118">Bearer {token}.</span></span> <span data-ttu-id="b897e-119">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b897e-119">**Required**.</span></span>
<span data-ttu-id="b897e-120">Inhaltstyp</span><span class="sxs-lookup"><span data-stu-id="b897e-120">Content type</span></span> | <span data-ttu-id="b897e-121">application/json</span><span class="sxs-lookup"><span data-stu-id="b897e-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="b897e-122">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="b897e-122">Request body</span></span>
<span data-ttu-id="b897e-123">Empty</span><span class="sxs-lookup"><span data-stu-id="b897e-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b897e-124">Antwort</span><span class="sxs-lookup"><span data-stu-id="b897e-124">Response</span></span>
<span data-ttu-id="b897e-125">Wenn erfolgreich – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="b897e-125">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="b897e-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b897e-126">Example</span></span>

<span data-ttu-id="b897e-127">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="b897e-127">**Request**</span></span>

<span data-ttu-id="b897e-128">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="b897e-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

<span data-ttu-id="b897e-129">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="b897e-129">**Response**</span></span>

<span data-ttu-id="b897e-130">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="b897e-130">Here is an example of the response.</span></span>

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

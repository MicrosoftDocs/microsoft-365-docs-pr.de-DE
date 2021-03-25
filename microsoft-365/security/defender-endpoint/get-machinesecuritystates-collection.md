---
title: Abrufen der Sammlungs-API für Computersicherheitszustände
description: Rufen Sie eine Sammlung von Gerätesicherheitszuständen mithilfe von Microsoft Defender for Endpoint ab.
keywords: apis, graph api, supported apis, get, device, security, state
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 9dab4bdccc1fead5bc2cc5b9bdff8f2a45b6c8db
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200365"
---
# <a name="get-machines-security-states-collection-api"></a><span data-ttu-id="51a6a-104">Abrufen der Computersicherheitszustände-Auflistungs-API</span><span class="sxs-lookup"><span data-stu-id="51a6a-104">Get Machines security states collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="51a6a-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="51a6a-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="51a6a-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="51a6a-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="51a6a-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="51a6a-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="51a6a-108">Ruft eine Auflistung von Gerätesicherheitszuständen ab.</span><span class="sxs-lookup"><span data-stu-id="51a6a-108">Retrieves a collection of devices security states.</span></span>

## <a name="permissions"></a><span data-ttu-id="51a6a-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="51a6a-109">Permissions</span></span>
<span data-ttu-id="51a6a-110">Der Benutzer benötigt Leseberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="51a6a-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="51a6a-111">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="51a6a-111">HTTP request</span></span>
```
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a><span data-ttu-id="51a6a-112">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="51a6a-112">Request headers</span></span>

<span data-ttu-id="51a6a-113">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="51a6a-113">Header</span></span> | <span data-ttu-id="51a6a-114">Wert</span><span class="sxs-lookup"><span data-stu-id="51a6a-114">Value</span></span> 
:---|:---
<span data-ttu-id="51a6a-115">Authorization</span><span class="sxs-lookup"><span data-stu-id="51a6a-115">Authorization</span></span> | <span data-ttu-id="51a6a-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="51a6a-116">Bearer {token}.</span></span> <span data-ttu-id="51a6a-117">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="51a6a-117">**Required**.</span></span>
<span data-ttu-id="51a6a-118">Inhaltstyp</span><span class="sxs-lookup"><span data-stu-id="51a6a-118">Content type</span></span> | <span data-ttu-id="51a6a-119">application/json</span><span class="sxs-lookup"><span data-stu-id="51a6a-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="51a6a-120">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="51a6a-120">Request body</span></span>
<span data-ttu-id="51a6a-121">Empty</span><span class="sxs-lookup"><span data-stu-id="51a6a-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="51a6a-122">Antwort</span><span class="sxs-lookup"><span data-stu-id="51a6a-122">Response</span></span>
<span data-ttu-id="51a6a-123">Wenn erfolgreich – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="51a6a-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="51a6a-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51a6a-124">Example</span></span>

<span data-ttu-id="51a6a-125">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="51a6a-125">**Request**</span></span>

<span data-ttu-id="51a6a-126">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="51a6a-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

<span data-ttu-id="51a6a-127">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="51a6a-127">**Response**</span></span>

<span data-ttu-id="51a6a-128">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="51a6a-128">Here is an example of the response.</span></span>
<span data-ttu-id="51a6a-129">Die *Feld-ID* enthält die Geräte-ID und entspricht der *Feld-ID*\* in Geräteinformationen.</span><span class="sxs-lookup"><span data-stu-id="51a6a-129">Field *id* contains device id and equal to the field *id*\* in devices info.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        …
    ]
}
```

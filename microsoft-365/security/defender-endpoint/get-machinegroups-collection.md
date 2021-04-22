---
title: Abrufen der RBAC-Computergruppensammlungs-API
description: Erfahren Sie, wie Sie die KB-Auflistungs-API abrufen verwenden, um eine Auflistung von RBAC-Gerätegruppen in Microsoft Defender for Endpoint abzurufen.
keywords: apis, graph api, supported apis, get, RBAC, group
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
ms.date: 10/07/2018
ms.openlocfilehash: 18566025d79f02281c1d2c1509dd98f1e57879c2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932775"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="ade21-104">Abrufen der KB-Auflistungs-API</span><span class="sxs-lookup"><span data-stu-id="ade21-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ade21-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ade21-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="ade21-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="ade21-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ade21-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="ade21-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="ade21-108">Ruft eine Auflistung von RBAC-Gerätegruppen ab.</span><span class="sxs-lookup"><span data-stu-id="ade21-108">Retrieves a collection of RBAC device groups.</span></span>

## <a name="permissions"></a><span data-ttu-id="ade21-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ade21-109">Permissions</span></span>
<span data-ttu-id="ade21-110">Der Benutzer benötigt Leseberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="ade21-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="ade21-111">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="ade21-111">HTTP request</span></span>
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a><span data-ttu-id="ade21-112">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="ade21-112">Request headers</span></span>

<span data-ttu-id="ade21-113">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="ade21-113">Header</span></span> | <span data-ttu-id="ade21-114">Wert</span><span class="sxs-lookup"><span data-stu-id="ade21-114">Value</span></span> 
:---|:---
<span data-ttu-id="ade21-115">Authorization</span><span class="sxs-lookup"><span data-stu-id="ade21-115">Authorization</span></span> | <span data-ttu-id="ade21-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ade21-116">Bearer {token}.</span></span> <span data-ttu-id="ade21-117">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="ade21-117">**Required**.</span></span>
<span data-ttu-id="ade21-118">Inhaltstyp</span><span class="sxs-lookup"><span data-stu-id="ade21-118">Content type</span></span> | <span data-ttu-id="ade21-119">application/json</span><span class="sxs-lookup"><span data-stu-id="ade21-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="ade21-120">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="ade21-120">Request body</span></span>
<span data-ttu-id="ade21-121">Empty</span><span class="sxs-lookup"><span data-stu-id="ade21-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ade21-122">Antwort</span><span class="sxs-lookup"><span data-stu-id="ade21-122">Response</span></span>
<span data-ttu-id="ade21-123">Wenn erfolgreich – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="ade21-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="ade21-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ade21-124">Example</span></span>

<span data-ttu-id="ade21-125">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="ade21-125">**Request**</span></span>

<span data-ttu-id="ade21-126">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="ade21-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

<span data-ttu-id="ade21-127">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="ade21-127">**Response**</span></span>

<span data-ttu-id="ade21-128">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="ade21-128">Here is an example of the response.</span></span>
<span data-ttu-id="ade21-129">Die Feld-ID  enthält die Gerätegruppen-ID und entspricht dem Feld **rbacGroupId** in Geräteinformationen.</span><span class="sxs-lookup"><span data-stu-id="ade21-129">Field id contains device group **id** and equal to field **rbacGroupId** in devices info.</span></span> <span data-ttu-id="ade21-130">Feld **ungrouped** ist nur für eine Gruppe für alle Geräte true, die keiner Gruppe zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="ade21-130">Field **ungrouped** is true only for one group for all devices that have not been assigned to any group.</span></span> <span data-ttu-id="ade21-131">Diese Gruppe hat wie gewohnt den Namen "UnassignedGroup".</span><span class="sxs-lookup"><span data-stu-id="ade21-131">This group as usual has name "UnassignedGroup".</span></span>

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```

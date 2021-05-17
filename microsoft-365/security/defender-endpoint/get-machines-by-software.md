---
title: Auflisten von Geräten nach Software
description: Rufen Sie eine Liste der Geräte ab, auf der diese Software installiert ist.
keywords: apis, graph api, supported apis, get, list devices, devices list, list devices by software, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: ff0bb9a6f17b8d4dc6432292ec98743d3eaf952c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929097"
---
# <a name="list-devices-by-software"></a><span data-ttu-id="82831-104">Auflisten von Geräten nach Software</span><span class="sxs-lookup"><span data-stu-id="82831-104">List devices by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="82831-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="82831-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="82831-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="82831-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="82831-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="82831-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="82831-108">Rufen Sie eine Liste der Geräteverweise ab, auf die diese Software installiert ist.</span><span class="sxs-lookup"><span data-stu-id="82831-108">Retrieve a list of device references that has this software installed.</span></span>

## <a name="permissions"></a><span data-ttu-id="82831-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="82831-109">Permissions</span></span>
<span data-ttu-id="82831-110">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="82831-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="82831-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.</span><span class="sxs-lookup"><span data-stu-id="82831-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="82831-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="82831-112">Permission type</span></span> |   <span data-ttu-id="82831-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="82831-113">Permission</span></span>  |   <span data-ttu-id="82831-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="82831-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="82831-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="82831-115">Application</span></span> | <span data-ttu-id="82831-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="82831-116">Software.Read.All</span></span> | <span data-ttu-id="82831-117">"Informationen zur Software zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="82831-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="82831-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="82831-118">Delegated (work or school account)</span></span> | <span data-ttu-id="82831-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="82831-119">Software.Read</span></span> | <span data-ttu-id="82831-120">"Informationen zur Software zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="82831-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="82831-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="82831-121">HTTP request</span></span>
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a><span data-ttu-id="82831-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="82831-122">Request headers</span></span>

| <span data-ttu-id="82831-123">Name</span><span class="sxs-lookup"><span data-stu-id="82831-123">Name</span></span>        | <span data-ttu-id="82831-124">Typ</span><span class="sxs-lookup"><span data-stu-id="82831-124">Type</span></span> | <span data-ttu-id="82831-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82831-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="82831-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="82831-126">Authorization</span></span> | <span data-ttu-id="82831-127">String</span><span class="sxs-lookup"><span data-stu-id="82831-127">String</span></span> | <span data-ttu-id="82831-128">Bearer {token}. **Erforderlich.**</span><span class="sxs-lookup"><span data-stu-id="82831-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="82831-129">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="82831-129">Request body</span></span>
<span data-ttu-id="82831-130">Empty</span><span class="sxs-lookup"><span data-stu-id="82831-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="82831-131">Antwort</span><span class="sxs-lookup"><span data-stu-id="82831-131">Response</span></span>
<span data-ttu-id="82831-132">Wenn die Methode erfolgreich ist, werden 200 OK und eine Liste der Geräte zurückgegeben, deren Software im Textkörper installiert ist.</span><span class="sxs-lookup"><span data-stu-id="82831-132">If successful, this method returns 200 OK and a list of devices with the software installed in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="82831-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="82831-133">Example</span></span>

<span data-ttu-id="82831-134">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="82831-134">**Request**</span></span>

<span data-ttu-id="82831-135">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="82831-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

<span data-ttu-id="82831-136">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="82831-136">**Response**</span></span>

<span data-ttu-id="82831-137">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="82831-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="82831-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="82831-138">Related topics</span></span>
- [<span data-ttu-id="82831-139">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="82831-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="82831-140">Softwareinventar & Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="82831-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)

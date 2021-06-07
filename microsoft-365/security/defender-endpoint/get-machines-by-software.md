---
title: Auflisten von Geräten nach Software
description: Rufen Sie eine Liste der Geräte ab, auf denen diese Software installiert ist.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Listengeräte, Geräteliste, Listengeräte nach Software, Microsoft Defender für Endpunkt-TVM-API
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: e1adf28823d6b86417c32578a89480958946c50d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770554"
---
# <a name="list-devices-by-software"></a><span data-ttu-id="35ae7-104">Auflisten von Geräten nach Software</span><span class="sxs-lookup"><span data-stu-id="35ae7-104">List devices by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="35ae7-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="35ae7-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="35ae7-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="35ae7-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="35ae7-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="35ae7-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="35ae7-108">Rufen Sie eine Liste der Geräteverweise ab, auf denen diese Software installiert ist.</span><span class="sxs-lookup"><span data-stu-id="35ae7-108">Retrieve a list of device references that has this software installed.</span></span>

## <a name="permissions"></a><span data-ttu-id="35ae7-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="35ae7-109">Permissions</span></span>
<span data-ttu-id="35ae7-110">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="35ae7-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="35ae7-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="35ae7-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="35ae7-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="35ae7-112">Permission type</span></span> |   <span data-ttu-id="35ae7-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="35ae7-113">Permission</span></span>  |   <span data-ttu-id="35ae7-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="35ae7-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="35ae7-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="35ae7-115">Application</span></span> | <span data-ttu-id="35ae7-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="35ae7-116">Software.Read.All</span></span> | <span data-ttu-id="35ae7-117">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="35ae7-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="35ae7-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="35ae7-118">Delegated (work or school account)</span></span> | <span data-ttu-id="35ae7-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="35ae7-119">Software.Read</span></span> | <span data-ttu-id="35ae7-120">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="35ae7-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="35ae7-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="35ae7-121">HTTP request</span></span>
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a><span data-ttu-id="35ae7-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="35ae7-122">Request headers</span></span>

| <span data-ttu-id="35ae7-123">Name</span><span class="sxs-lookup"><span data-stu-id="35ae7-123">Name</span></span>        | <span data-ttu-id="35ae7-124">Typ</span><span class="sxs-lookup"><span data-stu-id="35ae7-124">Type</span></span> | <span data-ttu-id="35ae7-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35ae7-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="35ae7-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="35ae7-126">Authorization</span></span> | <span data-ttu-id="35ae7-127">String</span><span class="sxs-lookup"><span data-stu-id="35ae7-127">String</span></span> | <span data-ttu-id="35ae7-128">Bearer {token}. **Erforderlich.**</span><span class="sxs-lookup"><span data-stu-id="35ae7-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="35ae7-129">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="35ae7-129">Request body</span></span>
<span data-ttu-id="35ae7-130">Empty</span><span class="sxs-lookup"><span data-stu-id="35ae7-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="35ae7-131">Antwort</span><span class="sxs-lookup"><span data-stu-id="35ae7-131">Response</span></span>
<span data-ttu-id="35ae7-132">Wenn die Methode erfolgreich ist, werden 200 OK und eine Liste der Geräte mit der im Textkörper installierten Software zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="35ae7-132">If successful, this method returns 200 OK and a list of devices with the software installed in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="35ae7-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35ae7-133">Example</span></span>

<span data-ttu-id="35ae7-134">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="35ae7-134">**Request**</span></span>

<span data-ttu-id="35ae7-135">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="35ae7-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

<span data-ttu-id="35ae7-136">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="35ae7-136">**Response**</span></span>

<span data-ttu-id="35ae7-137">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="35ae7-137">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="35ae7-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="35ae7-138">Related topics</span></span>
- [<span data-ttu-id="35ae7-139">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="35ae7-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="35ae7-140">Softwareinventarisierung von Sicherheitsrisiken &</span><span class="sxs-lookup"><span data-stu-id="35ae7-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)

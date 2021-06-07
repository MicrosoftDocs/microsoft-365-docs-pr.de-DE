---
title: Software nach ID abrufen
description: Ruft eine Liste der Belichtungsergebnisse nach Gerätegruppe ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Software, Microsoft Defender für Endpunkt-TVM-API
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
ms.openlocfilehash: 7e9e6b5e64099e7ab49fec624d83f13f18e6029c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769161"
---
# <a name="get-software-by-id"></a><span data-ttu-id="ecd73-104">Software nach ID abrufen</span><span class="sxs-lookup"><span data-stu-id="ecd73-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ecd73-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ecd73-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ecd73-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="ecd73-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ecd73-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="ecd73-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="ecd73-108">Ruft Softwaredetails nach ID ab.</span><span class="sxs-lookup"><span data-stu-id="ecd73-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="ecd73-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ecd73-109">Permissions</span></span>
<span data-ttu-id="ecd73-110">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="ecd73-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ecd73-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ecd73-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="ecd73-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="ecd73-112">Permission type</span></span> |   <span data-ttu-id="ecd73-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="ecd73-113">Permission</span></span>  |   <span data-ttu-id="ecd73-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="ecd73-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ecd73-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="ecd73-115">Application</span></span> | <span data-ttu-id="ecd73-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="ecd73-116">Software.Read.All</span></span> | <span data-ttu-id="ecd73-117">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="ecd73-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="ecd73-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="ecd73-118">Delegated (work or school account)</span></span> | <span data-ttu-id="ecd73-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="ecd73-119">Software.Read</span></span> | <span data-ttu-id="ecd73-120">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="ecd73-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="ecd73-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="ecd73-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="ecd73-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="ecd73-122">Request headers</span></span>

| <span data-ttu-id="ecd73-123">Name</span><span class="sxs-lookup"><span data-stu-id="ecd73-123">Name</span></span>        | <span data-ttu-id="ecd73-124">Typ</span><span class="sxs-lookup"><span data-stu-id="ecd73-124">Type</span></span> | <span data-ttu-id="ecd73-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecd73-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="ecd73-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="ecd73-126">Authorization</span></span> | <span data-ttu-id="ecd73-127">String</span><span class="sxs-lookup"><span data-stu-id="ecd73-127">String</span></span> | <span data-ttu-id="ecd73-128">Bearer {token}. **Erforderlich.**</span><span class="sxs-lookup"><span data-stu-id="ecd73-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="ecd73-129">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="ecd73-129">Request body</span></span>
<span data-ttu-id="ecd73-130">Empty</span><span class="sxs-lookup"><span data-stu-id="ecd73-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ecd73-131">Antwort</span><span class="sxs-lookup"><span data-stu-id="ecd73-131">Response</span></span>
<span data-ttu-id="ecd73-132">Wenn die Methode erfolgreich ist, wird 200 OK mit den angegebenen Softwaredaten im Text zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ecd73-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="ecd73-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ecd73-133">Example</span></span>

<span data-ttu-id="ecd73-134">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="ecd73-134">**Request**</span></span>

<span data-ttu-id="ecd73-135">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="ecd73-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="ecd73-136">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="ecd73-136">**Response**</span></span>

<span data-ttu-id="ecd73-137">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="ecd73-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a><span data-ttu-id="ecd73-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ecd73-138">Related topics</span></span>
- [<span data-ttu-id="ecd73-139">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="ecd73-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="ecd73-140">Softwareinventarisierung von Sicherheitsrisiken &</span><span class="sxs-lookup"><span data-stu-id="ecd73-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)

---
title: Software nach Id herunterladen
description: Ruft eine Liste der Belichtungsergebnisse nach Gerätegruppe ab.
keywords: apis, graph api, supported apis, get, software, mdatp tvm api
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
ms.openlocfilehash: 57d6ccd2c5387d478b75cfb6fb32a5b1052e491c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198589"
---
# <a name="get-software-by-id"></a><span data-ttu-id="1f234-104">Software nach Id herunterladen</span><span class="sxs-lookup"><span data-stu-id="1f234-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1f234-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1f234-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1f234-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="1f234-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1f234-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="1f234-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1f234-108">Ruft Softwaredetails nach ID ab.</span><span class="sxs-lookup"><span data-stu-id="1f234-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="1f234-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1f234-109">Permissions</span></span>
<span data-ttu-id="1f234-110">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1f234-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1f234-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.</span><span class="sxs-lookup"><span data-stu-id="1f234-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="1f234-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="1f234-112">Permission type</span></span> |   <span data-ttu-id="1f234-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1f234-113">Permission</span></span>  |   <span data-ttu-id="1f234-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1f234-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1f234-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="1f234-115">Application</span></span> | <span data-ttu-id="1f234-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="1f234-116">Software.Read.All</span></span> | <span data-ttu-id="1f234-117">"Informationen zur Software zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="1f234-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="1f234-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="1f234-118">Delegated (work or school account)</span></span> | <span data-ttu-id="1f234-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="1f234-119">Software.Read</span></span> | <span data-ttu-id="1f234-120">"Informationen zur Software zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="1f234-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="1f234-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="1f234-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="1f234-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="1f234-122">Request headers</span></span>

| <span data-ttu-id="1f234-123">Name</span><span class="sxs-lookup"><span data-stu-id="1f234-123">Name</span></span>        | <span data-ttu-id="1f234-124">Typ</span><span class="sxs-lookup"><span data-stu-id="1f234-124">Type</span></span> | <span data-ttu-id="1f234-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f234-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="1f234-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="1f234-126">Authorization</span></span> | <span data-ttu-id="1f234-127">String</span><span class="sxs-lookup"><span data-stu-id="1f234-127">String</span></span> | <span data-ttu-id="1f234-128">Bearer {token}. **Erforderlich.**</span><span class="sxs-lookup"><span data-stu-id="1f234-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="1f234-129">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="1f234-129">Request body</span></span>
<span data-ttu-id="1f234-130">Empty</span><span class="sxs-lookup"><span data-stu-id="1f234-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1f234-131">Antwort</span><span class="sxs-lookup"><span data-stu-id="1f234-131">Response</span></span>
<span data-ttu-id="1f234-132">Wenn die Methode erfolgreich ist, gibt sie 200 OK mit den angegebenen Softwaredaten im Textkörper zurück.</span><span class="sxs-lookup"><span data-stu-id="1f234-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="1f234-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1f234-133">Example</span></span>

<span data-ttu-id="1f234-134">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="1f234-134">**Request**</span></span>

<span data-ttu-id="1f234-135">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="1f234-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="1f234-136">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="1f234-136">**Response**</span></span>

<span data-ttu-id="1f234-137">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="1f234-137">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="1f234-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1f234-138">Related topics</span></span>
- [<span data-ttu-id="1f234-139">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="1f234-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="1f234-140">Softwareinventar & Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="1f234-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)

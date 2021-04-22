---
title: Software auflisten
description: Ruft eine Liste des Softwarebestands ab
keywords: apis, graph api, supported apis, get, list, file, information, software inventory, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 6522b546dfde7447a03b3c417be93d288e261908
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934009"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="b9aaf-104">Auflisten der Softwareinventar-API</span><span class="sxs-lookup"><span data-stu-id="b9aaf-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b9aaf-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b9aaf-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b9aaf-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b9aaf-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b9aaf-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b9aaf-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b9aaf-108">Ruft das Softwareinventar der Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="b9aaf-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="b9aaf-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b9aaf-109">Permissions</span></span>
<span data-ttu-id="b9aaf-110">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b9aaf-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b9aaf-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.</span><span class="sxs-lookup"><span data-stu-id="b9aaf-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="b9aaf-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="b9aaf-112">Permission type</span></span> |   <span data-ttu-id="b9aaf-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b9aaf-113">Permission</span></span>  |   <span data-ttu-id="b9aaf-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b9aaf-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b9aaf-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="b9aaf-115">Application</span></span> |<span data-ttu-id="b9aaf-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="b9aaf-116">Software.Read.All</span></span> |    <span data-ttu-id="b9aaf-117">"Informationen zur Software zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="b9aaf-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="b9aaf-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="b9aaf-118">Delegated (work or school account)</span></span> | <span data-ttu-id="b9aaf-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="b9aaf-119">Software.Read</span></span> |    <span data-ttu-id="b9aaf-120">"Informationen zur Software zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="b9aaf-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b9aaf-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="b9aaf-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="b9aaf-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="b9aaf-122">Request headers</span></span>

<span data-ttu-id="b9aaf-123">Name</span><span class="sxs-lookup"><span data-stu-id="b9aaf-123">Name</span></span> | <span data-ttu-id="b9aaf-124">Typ</span><span class="sxs-lookup"><span data-stu-id="b9aaf-124">Type</span></span> | <span data-ttu-id="b9aaf-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9aaf-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="b9aaf-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="b9aaf-126">Authorization</span></span> | <span data-ttu-id="b9aaf-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b9aaf-127">String</span></span> | <span data-ttu-id="b9aaf-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b9aaf-128">Bearer {token}.</span></span> <span data-ttu-id="b9aaf-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b9aaf-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b9aaf-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="b9aaf-130">Request body</span></span>
<span data-ttu-id="b9aaf-131">Empty</span><span class="sxs-lookup"><span data-stu-id="b9aaf-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b9aaf-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="b9aaf-132">Response</span></span>
<span data-ttu-id="b9aaf-133">Wenn die Methode erfolgreich ist, gibt sie 200 OK mit dem Softwarebestand im Textkörper zurück.</span><span class="sxs-lookup"><span data-stu-id="b9aaf-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="b9aaf-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9aaf-134">Example</span></span>

<span data-ttu-id="b9aaf-135">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="b9aaf-135">**Request**</span></span>

<span data-ttu-id="b9aaf-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="b9aaf-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="b9aaf-137">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="b9aaf-137">**Response**</span></span>

<span data-ttu-id="b9aaf-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="b9aaf-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
    "value": [
            {
                "id": "microsoft-_-edge",
                "name": "edge",
                "vendor": "microsoft",
                "weaknesses": 467,
                "publicExploit": true,
                "activeAlert": false,
                "exposedMachines": 172,
                "impactScore": 2.39947438
            }
            ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="b9aaf-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b9aaf-139">Related topics</span></span>
- [<span data-ttu-id="b9aaf-140">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="b9aaf-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b9aaf-141">Softwareinventar & Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="b9aaf-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)

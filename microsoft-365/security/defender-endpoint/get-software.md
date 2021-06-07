---
title: Software auflisten
description: Ruft eine Liste der Softwareinventur ab
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Liste, Datei, Informationen, Softwareinventarisierung, Api für Bedrohungen & Sicherheitsrisikomanagement, Microsoft Defender für Endpunkt-TVM-API
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
ms.openlocfilehash: f7e71c58396fd4b3ed40ba88aab5c2757ae41a41
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771081"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="4c4d8-104">Softwareinventarisierungs-API auflisten</span><span class="sxs-lookup"><span data-stu-id="4c4d8-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4c4d8-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4c4d8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="4c4d8-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="4c4d8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4c4d8-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4c4d8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="4c4d8-108">Ruft den Softwarebestand der Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="4c4d8-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="4c4d8-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4c4d8-109">Permissions</span></span>
<span data-ttu-id="4c4d8-110">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="4c4d8-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4c4d8-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4c4d8-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="4c4d8-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="4c4d8-112">Permission type</span></span> |   <span data-ttu-id="4c4d8-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4c4d8-113">Permission</span></span>  |   <span data-ttu-id="4c4d8-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4c4d8-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4c4d8-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="4c4d8-115">Application</span></span> |<span data-ttu-id="4c4d8-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="4c4d8-116">Software.Read.All</span></span> |    <span data-ttu-id="4c4d8-117">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="4c4d8-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="4c4d8-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="4c4d8-118">Delegated (work or school account)</span></span> | <span data-ttu-id="4c4d8-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="4c4d8-119">Software.Read</span></span> |    <span data-ttu-id="4c4d8-120">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="4c4d8-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="4c4d8-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="4c4d8-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="4c4d8-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="4c4d8-122">Request headers</span></span>

<span data-ttu-id="4c4d8-123">Name</span><span class="sxs-lookup"><span data-stu-id="4c4d8-123">Name</span></span> | <span data-ttu-id="4c4d8-124">Typ</span><span class="sxs-lookup"><span data-stu-id="4c4d8-124">Type</span></span> | <span data-ttu-id="4c4d8-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c4d8-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="4c4d8-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="4c4d8-126">Authorization</span></span> | <span data-ttu-id="4c4d8-127">String</span><span class="sxs-lookup"><span data-stu-id="4c4d8-127">String</span></span> | <span data-ttu-id="4c4d8-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4c4d8-128">Bearer {token}.</span></span> <span data-ttu-id="4c4d8-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="4c4d8-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4c4d8-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="4c4d8-130">Request body</span></span>
<span data-ttu-id="4c4d8-131">Empty</span><span class="sxs-lookup"><span data-stu-id="4c4d8-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4c4d8-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="4c4d8-132">Response</span></span>
<span data-ttu-id="4c4d8-133">Wenn die Methode erfolgreich ist, wird 200 OK mit dem Softwareinventar im Text zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4c4d8-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="4c4d8-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4c4d8-134">Example</span></span>

<span data-ttu-id="4c4d8-135">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="4c4d8-135">**Request**</span></span>

<span data-ttu-id="4c4d8-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4c4d8-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="4c4d8-137">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="4c4d8-137">**Response**</span></span>

<span data-ttu-id="4c4d8-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="4c4d8-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="4c4d8-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4c4d8-139">Related topics</span></span>
- [<span data-ttu-id="4c4d8-140">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="4c4d8-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="4c4d8-141">Softwareinventarisierung von Bedrohungen & Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="4c4d8-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)

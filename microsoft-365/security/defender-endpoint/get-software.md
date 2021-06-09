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
ms.openlocfilehash: 2b7375f04094cdb56b0801adf2c1c0b7a8ab3098
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844274"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="dafb9-104">Softwareinventarisierungs-API auflisten</span><span class="sxs-lookup"><span data-stu-id="dafb9-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dafb9-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="dafb9-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="dafb9-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="dafb9-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dafb9-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="dafb9-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="dafb9-108">Ruft den Softwarebestand der Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="dafb9-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="dafb9-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="dafb9-109">Permissions</span></span>
<span data-ttu-id="dafb9-110">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="dafb9-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="dafb9-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="dafb9-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="dafb9-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="dafb9-112">Permission type</span></span> |   <span data-ttu-id="dafb9-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="dafb9-113">Permission</span></span>  |   <span data-ttu-id="dafb9-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="dafb9-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="dafb9-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="dafb9-115">Application</span></span> |<span data-ttu-id="dafb9-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="dafb9-116">Software.Read.All</span></span> |    <span data-ttu-id="dafb9-117">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="dafb9-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="dafb9-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="dafb9-118">Delegated (work or school account)</span></span> | <span data-ttu-id="dafb9-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="dafb9-119">Software.Read</span></span> |    <span data-ttu-id="dafb9-120">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="dafb9-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="dafb9-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="dafb9-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="dafb9-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="dafb9-122">Request headers</span></span>

<span data-ttu-id="dafb9-123">Name</span><span class="sxs-lookup"><span data-stu-id="dafb9-123">Name</span></span> | <span data-ttu-id="dafb9-124">Typ</span><span class="sxs-lookup"><span data-stu-id="dafb9-124">Type</span></span> | <span data-ttu-id="dafb9-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dafb9-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="dafb9-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="dafb9-126">Authorization</span></span> | <span data-ttu-id="dafb9-127">String</span><span class="sxs-lookup"><span data-stu-id="dafb9-127">String</span></span> | <span data-ttu-id="dafb9-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="dafb9-128">Bearer {token}.</span></span> <span data-ttu-id="dafb9-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="dafb9-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="dafb9-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="dafb9-130">Request body</span></span>
<span data-ttu-id="dafb9-131">Empty</span><span class="sxs-lookup"><span data-stu-id="dafb9-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="dafb9-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="dafb9-132">Response</span></span>
<span data-ttu-id="dafb9-133">Wenn die Methode erfolgreich ist, wird 200 OK mit dem Softwareinventar im Text zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dafb9-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="dafb9-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dafb9-134">Example</span></span>

<span data-ttu-id="dafb9-135">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="dafb9-135">**Request**</span></span>

<span data-ttu-id="dafb9-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="dafb9-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="dafb9-137">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="dafb9-137">**Response**</span></span>

<span data-ttu-id="dafb9-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="dafb9-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="dafb9-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="dafb9-139">Related topics</span></span>
- [<span data-ttu-id="dafb9-140">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="dafb9-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="dafb9-141">Softwareinventarisierung von Bedrohungen & Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="dafb9-141">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)

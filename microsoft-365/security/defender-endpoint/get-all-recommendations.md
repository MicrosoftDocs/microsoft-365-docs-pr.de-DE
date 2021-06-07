---
title: Auflisten aller Empfehlungen
description: Ruft eine Liste aller Sicherheitsempfehlungen ab, die sich auf die Organisation auswirken.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Sicherheitsempfehlungen, Microsoft Defender für Endpunkt-TVM-API, Bedrohungs- und Sicherheitsrisikomanagement, Bedrohungs- und Sicherheitsrisikomanagement-API
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: 0a58287a9bd48a4d19144a40674e1d3ad3bd256a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768928"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="1e35d-104">Auflisten aller Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="1e35d-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1e35d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1e35d-105">**Applies to:**</span></span>
- [<span data-ttu-id="1e35d-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1e35d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1e35d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e35d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="1e35d-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="1e35d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1e35d-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="1e35d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1e35d-110">Ruft eine Liste aller Sicherheitsempfehlungen ab, die sich auf die Organisation auswirken.</span><span class="sxs-lookup"><span data-stu-id="1e35d-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="1e35d-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1e35d-111">Permissions</span></span>
<span data-ttu-id="1e35d-112">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="1e35d-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1e35d-113">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1e35d-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="1e35d-114">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="1e35d-114">Permission type</span></span> |   <span data-ttu-id="1e35d-115">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1e35d-115">Permission</span></span>  |   <span data-ttu-id="1e35d-116">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1e35d-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1e35d-117">Anwendung</span><span class="sxs-lookup"><span data-stu-id="1e35d-117">Application</span></span> |   <span data-ttu-id="1e35d-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="1e35d-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="1e35d-119">"Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="1e35d-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="1e35d-120">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="1e35d-120">Delegated (work or school account)</span></span> | <span data-ttu-id="1e35d-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="1e35d-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="1e35d-122">"Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="1e35d-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="1e35d-123">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="1e35d-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="1e35d-124">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="1e35d-124">Request headers</span></span>

<span data-ttu-id="1e35d-125">Name</span><span class="sxs-lookup"><span data-stu-id="1e35d-125">Name</span></span> | <span data-ttu-id="1e35d-126">Typ</span><span class="sxs-lookup"><span data-stu-id="1e35d-126">Type</span></span> | <span data-ttu-id="1e35d-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e35d-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="1e35d-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="1e35d-128">Authorization</span></span> | <span data-ttu-id="1e35d-129">String</span><span class="sxs-lookup"><span data-stu-id="1e35d-129">String</span></span> | <span data-ttu-id="1e35d-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1e35d-130">Bearer {token}.</span></span> <span data-ttu-id="1e35d-131">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="1e35d-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1e35d-132">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="1e35d-132">Request body</span></span>
<span data-ttu-id="1e35d-133">Empty</span><span class="sxs-lookup"><span data-stu-id="1e35d-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1e35d-134">Antwort</span><span class="sxs-lookup"><span data-stu-id="1e35d-134">Response</span></span>
<span data-ttu-id="1e35d-135">Wenn die Methode erfolgreich ist, wird 200 OK mit der Liste der Sicherheitsempfehlungen im Text zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1e35d-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="1e35d-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e35d-136">Example</span></span>

<span data-ttu-id="1e35d-137">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="1e35d-137">**Request**</span></span>

<span data-ttu-id="1e35d-138">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="1e35d-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="1e35d-139">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="1e35d-139">**Response**</span></span>

<span data-ttu-id="1e35d-140">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="1e35d-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-microsoft-_-windows_10",
            "productName": "windows_10",
            "recommendationName": "Update Windows 10",
            "weaknesses": 397,
            "vendor": "microsoft",
            "recommendedVersion": "",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": true,
            "activeAlert": false,
            "associatedThreats": [
                "3098b8ef-23b1-46b3-aed4-499e1928f9ed",
                "40c189d5-0330-4654-a816-e48c2b7f9c4b",
                "4b0c9702-9b6c-4ca2-9d02-1556869f56f8",
                "e8fc2121-3cf3-4dd2-9ea0-87d7e1d2b29d",
                "94b6e94b-0c1d-4817-ac06-c3b8639be3ab"
            ],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 7.674418604651163,
            "totalMachineCount": 37,
            "exposedMachinesCount": 7,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Windows 10"
        }
        ...
     ]
}
```
## <a name="see-also"></a><span data-ttu-id="1e35d-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e35d-141">See also</span></span>
- [<span data-ttu-id="1e35d-142">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="1e35d-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="1e35d-143">Sicherheitsempfehlungen für Sicherheitsrisiken &</span><span class="sxs-lookup"><span data-stu-id="1e35d-143">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)


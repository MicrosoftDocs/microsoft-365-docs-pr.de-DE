---
title: Auflisten aller Empfehlungen
description: Ruft eine Liste aller Sicherheitsempfehlungen ab, die die Organisation betreffen.
keywords: apis, graph api, supported apis, get, security recommendations, Microsoft Defender for Endpoint tvm api, Bedrohungs- und Sicherheitsrisikomanagement, Bedrohungs- und Sicherheitsrisikomanagement api
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
ms.technology: mde
ms.openlocfilehash: 0cb0a1f8a42b419db960e5097667c335bf7f7877
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935017"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="f10b1-104">Auflisten aller Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="f10b1-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f10b1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f10b1-105">**Applies to:**</span></span>
- [<span data-ttu-id="f10b1-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f10b1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f10b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f10b1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="f10b1-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f10b1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f10b1-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f10b1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f10b1-110">Ruft eine Liste aller Sicherheitsempfehlungen ab, die die Organisation betreffen.</span><span class="sxs-lookup"><span data-stu-id="f10b1-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="f10b1-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f10b1-111">Permissions</span></span>
<span data-ttu-id="f10b1-112">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f10b1-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f10b1-113">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.</span><span class="sxs-lookup"><span data-stu-id="f10b1-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="f10b1-114">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="f10b1-114">Permission type</span></span> |   <span data-ttu-id="f10b1-115">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f10b1-115">Permission</span></span>  |   <span data-ttu-id="f10b1-116">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f10b1-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f10b1-117">Anwendung</span><span class="sxs-lookup"><span data-stu-id="f10b1-117">Application</span></span> |   <span data-ttu-id="f10b1-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="f10b1-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="f10b1-119">"Informationen zur Sicherheitsempfehlung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="f10b1-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="f10b1-120">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="f10b1-120">Delegated (work or school account)</span></span> | <span data-ttu-id="f10b1-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="f10b1-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="f10b1-122">"Informationen zur Sicherheitsempfehlung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="f10b1-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="f10b1-123">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10b1-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="f10b1-124">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="f10b1-124">Request headers</span></span>

<span data-ttu-id="f10b1-125">Name</span><span class="sxs-lookup"><span data-stu-id="f10b1-125">Name</span></span> | <span data-ttu-id="f10b1-126">Typ</span><span class="sxs-lookup"><span data-stu-id="f10b1-126">Type</span></span> | <span data-ttu-id="f10b1-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f10b1-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="f10b1-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="f10b1-128">Authorization</span></span> | <span data-ttu-id="f10b1-129">String</span><span class="sxs-lookup"><span data-stu-id="f10b1-129">String</span></span> | <span data-ttu-id="f10b1-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f10b1-130">Bearer {token}.</span></span> <span data-ttu-id="f10b1-131">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="f10b1-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f10b1-132">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="f10b1-132">Request body</span></span>
<span data-ttu-id="f10b1-133">Empty</span><span class="sxs-lookup"><span data-stu-id="f10b1-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f10b1-134">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10b1-134">Response</span></span>
<span data-ttu-id="f10b1-135">Wenn die Methode erfolgreich ist, gibt sie 200 OK mit der Liste der Sicherheitsempfehlungen im Textkörper zurück.</span><span class="sxs-lookup"><span data-stu-id="f10b1-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="f10b1-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f10b1-136">Example</span></span>

<span data-ttu-id="f10b1-137">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="f10b1-137">**Request**</span></span>

<span data-ttu-id="f10b1-138">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="f10b1-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="f10b1-139">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="f10b1-139">**Response**</span></span>

<span data-ttu-id="f10b1-140">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="f10b1-140">Here is an example of the response.</span></span>


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
## <a name="see-also"></a><span data-ttu-id="f10b1-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f10b1-141">See also</span></span>
- [<span data-ttu-id="f10b1-142">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="f10b1-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="f10b1-143">Sicherheitsempfehlung & Bedrohungsrisikos</span><span class="sxs-lookup"><span data-stu-id="f10b1-143">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)


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
ms.openlocfilehash: eb009a01e36739ab5e9ec009d053a7bd4e177907
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841534"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="bbffa-104">Auflisten aller Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="bbffa-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bbffa-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bbffa-105">**Applies to:**</span></span>
- [<span data-ttu-id="bbffa-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bbffa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bbffa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbffa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="bbffa-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="bbffa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bbffa-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bbffa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="bbffa-110">Ruft eine Liste aller Sicherheitsempfehlungen ab, die sich auf die Organisation auswirken.</span><span class="sxs-lookup"><span data-stu-id="bbffa-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="bbffa-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bbffa-111">Permissions</span></span>
<span data-ttu-id="bbffa-112">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="bbffa-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bbffa-113">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bbffa-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="bbffa-114">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="bbffa-114">Permission type</span></span> |   <span data-ttu-id="bbffa-115">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="bbffa-115">Permission</span></span>  |   <span data-ttu-id="bbffa-116">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="bbffa-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bbffa-117">Anwendung</span><span class="sxs-lookup"><span data-stu-id="bbffa-117">Application</span></span> |   <span data-ttu-id="bbffa-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="bbffa-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="bbffa-119">"Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="bbffa-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="bbffa-120">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="bbffa-120">Delegated (work or school account)</span></span> | <span data-ttu-id="bbffa-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="bbffa-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="bbffa-122">"Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="bbffa-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="bbffa-123">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="bbffa-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="bbffa-124">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="bbffa-124">Request headers</span></span>

<span data-ttu-id="bbffa-125">Name</span><span class="sxs-lookup"><span data-stu-id="bbffa-125">Name</span></span> | <span data-ttu-id="bbffa-126">Typ</span><span class="sxs-lookup"><span data-stu-id="bbffa-126">Type</span></span> | <span data-ttu-id="bbffa-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bbffa-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="bbffa-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="bbffa-128">Authorization</span></span> | <span data-ttu-id="bbffa-129">String</span><span class="sxs-lookup"><span data-stu-id="bbffa-129">String</span></span> | <span data-ttu-id="bbffa-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="bbffa-130">Bearer {token}.</span></span> <span data-ttu-id="bbffa-131">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="bbffa-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="bbffa-132">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="bbffa-132">Request body</span></span>
<span data-ttu-id="bbffa-133">Empty</span><span class="sxs-lookup"><span data-stu-id="bbffa-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="bbffa-134">Antwort</span><span class="sxs-lookup"><span data-stu-id="bbffa-134">Response</span></span>
<span data-ttu-id="bbffa-135">Wenn die Methode erfolgreich ist, wird 200 OK mit der Liste der Sicherheitsempfehlungen im Text zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bbffa-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="bbffa-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bbffa-136">Example</span></span>

<span data-ttu-id="bbffa-137">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="bbffa-137">**Request**</span></span>

<span data-ttu-id="bbffa-138">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="bbffa-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="bbffa-139">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="bbffa-139">**Response**</span></span>

<span data-ttu-id="bbffa-140">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="bbffa-140">Here is an example of the response.</span></span>


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
## <a name="see-also"></a><span data-ttu-id="bbffa-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bbffa-141">See also</span></span>
- [<span data-ttu-id="bbffa-142">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="bbffa-142">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="bbffa-143">Sicherheitsempfehlungen für Sicherheitsrisiken &</span><span class="sxs-lookup"><span data-stu-id="bbffa-143">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)


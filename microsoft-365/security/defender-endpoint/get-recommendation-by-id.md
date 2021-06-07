---
title: Empfehlung nach ID abrufen
description: Ruft eine Sicherheitsempfehlung anhand ihrer ID ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Sicherheitsempfehlungen, Sicherheitsempfehlungen nach ID, Bedrohungs- und Sicherheitsrisikomanagement, Bedrohungs- und Sicherheitsrisikomanagement-API
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
ms.openlocfilehash: 4ec4758453f43cb211143918ed5fe8fe83e91c3f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771801"
---
# <a name="get-recommendation-by-id"></a><span data-ttu-id="b7373-104">Empfehlung nach ID abrufen</span><span class="sxs-lookup"><span data-stu-id="b7373-104">Get recommendation by ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b7373-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b7373-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b7373-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="b7373-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b7373-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b7373-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b7373-108">Ruft eine Sicherheitsempfehlung anhand ihrer ID ab.</span><span class="sxs-lookup"><span data-stu-id="b7373-108">Retrieves a security recommendation by its ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="b7373-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b7373-109">Permissions</span></span>
<span data-ttu-id="b7373-110">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b7373-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b7373-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b7373-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="b7373-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="b7373-112">Permission type</span></span> |   <span data-ttu-id="b7373-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b7373-113">Permission</span></span>  |   <span data-ttu-id="b7373-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b7373-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b7373-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="b7373-115">Application</span></span> |   <span data-ttu-id="b7373-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="b7373-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="b7373-117">"Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="b7373-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="b7373-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="b7373-118">Delegated (work or school account)</span></span> | <span data-ttu-id="b7373-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="b7373-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="b7373-120">"Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="b7373-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b7373-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="b7373-121">HTTP request</span></span>
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="b7373-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="b7373-122">Request headers</span></span>

<span data-ttu-id="b7373-123">Name</span><span class="sxs-lookup"><span data-stu-id="b7373-123">Name</span></span> | <span data-ttu-id="b7373-124">Typ</span><span class="sxs-lookup"><span data-stu-id="b7373-124">Type</span></span> | <span data-ttu-id="b7373-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7373-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="b7373-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="b7373-126">Authorization</span></span> | <span data-ttu-id="b7373-127">String</span><span class="sxs-lookup"><span data-stu-id="b7373-127">String</span></span> | <span data-ttu-id="b7373-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b7373-128">Bearer {token}.</span></span> <span data-ttu-id="b7373-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b7373-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b7373-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="b7373-130">Request body</span></span>
<span data-ttu-id="b7373-131">Empty</span><span class="sxs-lookup"><span data-stu-id="b7373-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b7373-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="b7373-132">Response</span></span>
<span data-ttu-id="b7373-133">Wenn die Methode erfolgreich ist, wird 200 OK mit den Sicherheitsempfehlungen im Text zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b7373-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="b7373-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b7373-134">Example</span></span>

<span data-ttu-id="b7373-135">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="b7373-135">**Request**</span></span>

<span data-ttu-id="b7373-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="b7373-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

<span data-ttu-id="b7373-137">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="b7373-137">**Response**</span></span>

<span data-ttu-id="b7373-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="b7373-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations/$entity",
    "id": "va-_-google-_-chrome",
    "productName": "chrome",
    "recommendationName": "Update Chrome",
    "weaknesses": 38,
    "vendor": "google",
    "recommendedVersion": "",
    "recommendationCategory": "Application",
    "subCategory": "",
    "severityScore": 0,
    "publicExploit": false,
    "activeAlert": false,
    "associatedThreats": [],
    "remediationType": "Update",
    "status": "Active",
    "configScoreImpact": 0,
    "exposureImpact": 3.9441860465116285,
    "totalMachineCount": 6,
    "exposedMachinesCount": 5,
    "nonProductivityImpactedAssets": 0,
    "relatedComponent": "Chrome"
}
```

## <a name="related-topics"></a><span data-ttu-id="b7373-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b7373-139">Related topics</span></span>
- [<span data-ttu-id="b7373-140">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="b7373-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b7373-141">Sicherheitsempfehlungen für Sicherheitsrisiken &</span><span class="sxs-lookup"><span data-stu-id="b7373-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

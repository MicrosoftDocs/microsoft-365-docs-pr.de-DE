---
title: Empfehlung nach Id erhalten
description: Ruft eine Sicherheitsempfehlung nach seiner ID ab.
keywords: apis, graph api, supported apis, get, security recommendation, security recommendation by ID, threat and vulnerability management, threat and vulnerability management api
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
ms.openlocfilehash: 45a151fc5855a4a2b1ba63a50b54737c90e6bdd1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199513"
---
# <a name="get-recommendation-by-id"></a><span data-ttu-id="4b758-104">Empfehlung nach ID erhalten</span><span class="sxs-lookup"><span data-stu-id="4b758-104">Get recommendation by ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4b758-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4b758-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="4b758-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="4b758-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4b758-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4b758-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="4b758-108">Ruft eine Sicherheitsempfehlung nach seiner ID ab.</span><span class="sxs-lookup"><span data-stu-id="4b758-108">Retrieves a security recommendation by its ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="4b758-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4b758-109">Permissions</span></span>
<span data-ttu-id="4b758-110">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4b758-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4b758-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.</span><span class="sxs-lookup"><span data-stu-id="4b758-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="4b758-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="4b758-112">Permission type</span></span> |   <span data-ttu-id="4b758-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4b758-113">Permission</span></span>  |   <span data-ttu-id="4b758-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4b758-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4b758-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="4b758-115">Application</span></span> |   <span data-ttu-id="4b758-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="4b758-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="4b758-117">"Informationen zur Sicherheitsempfehlung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="4b758-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="4b758-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="4b758-118">Delegated (work or school account)</span></span> | <span data-ttu-id="4b758-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="4b758-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="4b758-120">"Informationen zur Sicherheitsempfehlung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="4b758-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="4b758-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="4b758-121">HTTP request</span></span>
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="4b758-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="4b758-122">Request headers</span></span>

<span data-ttu-id="4b758-123">Name</span><span class="sxs-lookup"><span data-stu-id="4b758-123">Name</span></span> | <span data-ttu-id="4b758-124">Typ</span><span class="sxs-lookup"><span data-stu-id="4b758-124">Type</span></span> | <span data-ttu-id="4b758-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b758-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="4b758-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="4b758-126">Authorization</span></span> | <span data-ttu-id="4b758-127">String</span><span class="sxs-lookup"><span data-stu-id="4b758-127">String</span></span> | <span data-ttu-id="4b758-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4b758-128">Bearer {token}.</span></span> <span data-ttu-id="4b758-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="4b758-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4b758-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="4b758-130">Request body</span></span>
<span data-ttu-id="4b758-131">Empty</span><span class="sxs-lookup"><span data-stu-id="4b758-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4b758-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="4b758-132">Response</span></span>
<span data-ttu-id="4b758-133">Wenn die Methode erfolgreich ist, gibt sie 200 OK mit den Sicherheitsempfehlungen im Textkörper zurück.</span><span class="sxs-lookup"><span data-stu-id="4b758-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="4b758-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b758-134">Example</span></span>

<span data-ttu-id="4b758-135">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="4b758-135">**Request**</span></span>

<span data-ttu-id="4b758-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4b758-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

<span data-ttu-id="4b758-137">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="4b758-137">**Response**</span></span>

<span data-ttu-id="4b758-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="4b758-138">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="4b758-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4b758-139">Related topics</span></span>
- [<span data-ttu-id="4b758-140">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="4b758-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="4b758-141">Sicherheitsempfehlung & Bedrohungsrisikos</span><span class="sxs-lookup"><span data-stu-id="4b758-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

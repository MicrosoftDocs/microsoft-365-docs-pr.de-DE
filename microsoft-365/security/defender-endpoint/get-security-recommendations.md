---
title: Erhalten von Sicherheitsempfehlungen
description: Ruft eine Sammlung von Sicherheitsempfehlungen im Zusammenhang mit einer bestimmten Geräte-ID ab.
keywords: apis, graph api, supported apis, get, list, file, information, security recommendation per device, threat & Sicherheitsrisikomanagement api, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: bc209687d51b3e05bfcfd6028042ba5912b877f6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935305"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="aa9aa-104">Erhalten von Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="aa9aa-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aa9aa-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="aa9aa-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="aa9aa-106">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="aa9aa-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aa9aa-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="aa9aa-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="aa9aa-108">Ruft eine Sammlung von Sicherheitsempfehlungen im Zusammenhang mit einer bestimmten Geräte-ID ab.</span><span class="sxs-lookup"><span data-stu-id="aa9aa-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="aa9aa-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="aa9aa-109">Permissions</span></span>
<span data-ttu-id="aa9aa-110">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="aa9aa-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="aa9aa-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="aa9aa-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="aa9aa-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="aa9aa-112">Permission type</span></span> |   <span data-ttu-id="aa9aa-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="aa9aa-113">Permission</span></span>  |   <span data-ttu-id="aa9aa-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="aa9aa-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="aa9aa-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="aa9aa-115">Application</span></span> | <span data-ttu-id="aa9aa-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="aa9aa-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="aa9aa-117">"Informationen zur Sicherheitsempfehlung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="aa9aa-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="aa9aa-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="aa9aa-118">Delegated (work or school account)</span></span> | <span data-ttu-id="aa9aa-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="aa9aa-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="aa9aa-120">"Informationen zur Sicherheitsempfehlung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="aa9aa-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="aa9aa-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="aa9aa-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="aa9aa-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="aa9aa-122">Request headers</span></span>

<span data-ttu-id="aa9aa-123">Name</span><span class="sxs-lookup"><span data-stu-id="aa9aa-123">Name</span></span> | <span data-ttu-id="aa9aa-124">Typ</span><span class="sxs-lookup"><span data-stu-id="aa9aa-124">Type</span></span> | <span data-ttu-id="aa9aa-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa9aa-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="aa9aa-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="aa9aa-126">Authorization</span></span> | <span data-ttu-id="aa9aa-127">String</span><span class="sxs-lookup"><span data-stu-id="aa9aa-127">String</span></span> | <span data-ttu-id="aa9aa-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="aa9aa-128">Bearer {token}.</span></span> <span data-ttu-id="aa9aa-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="aa9aa-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="aa9aa-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="aa9aa-130">Request body</span></span>
<span data-ttu-id="aa9aa-131">Empty</span><span class="sxs-lookup"><span data-stu-id="aa9aa-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="aa9aa-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="aa9aa-132">Response</span></span>
<span data-ttu-id="aa9aa-133">Wenn die Methode erfolgreich ist, gibt sie 200 OK mit den Sicherheitsempfehlungen im Textkörper zurück.</span><span class="sxs-lookup"><span data-stu-id="aa9aa-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="aa9aa-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aa9aa-134">Example</span></span>

<span data-ttu-id="aa9aa-135">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="aa9aa-135">**Request**</span></span>

<span data-ttu-id="aa9aa-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="aa9aa-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="aa9aa-137">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="aa9aa-137">**Response**</span></span>

<span data-ttu-id="aa9aa-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="aa9aa-138">Here is an example of the response.</span></span>


```
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-git-scm-_-git",
            "productName": "git",
            "recommendationName": "Update Git to version 2.24.1.2",
            "weaknesses": 3,
            "vendor": "git-scm",
            "recommendedVersion": "2.24.1.2",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": false,
            "activeAlert": false,
            "associatedThreats": [],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 0,
            "totalMachineCount": 0,
            "exposedMachinesCount": 1,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Git"
        },
…
}
```

## <a name="related-topics"></a><span data-ttu-id="aa9aa-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="aa9aa-139">Related topics</span></span>
- [<span data-ttu-id="aa9aa-140">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="aa9aa-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="aa9aa-141">Sicherheitsempfehlung & Bedrohungsrisikos</span><span class="sxs-lookup"><span data-stu-id="aa9aa-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

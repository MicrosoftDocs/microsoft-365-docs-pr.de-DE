---
title: Sicherheitsempfehlungen erhalten
description: Ruft eine Sammlung von Sicherheitsempfehlungen im Zusammenhang mit einer bestimmten Geräte-ID ab.
keywords: apis, graph api, supported apis, get, list, file, information, security recommendation per device, threat & vulnerability management api, mdatp tvm api
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
ms.openlocfilehash: 6c65926985c7c8a194ab87c44c3fc269488c463c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199766"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="a0898-104">Sicherheitsempfehlungen erhalten</span><span class="sxs-lookup"><span data-stu-id="a0898-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a0898-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a0898-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="a0898-106">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a0898-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a0898-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a0898-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="a0898-108">Ruft eine Sammlung von Sicherheitsempfehlungen im Zusammenhang mit einer bestimmten Geräte-ID ab.</span><span class="sxs-lookup"><span data-stu-id="a0898-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="a0898-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a0898-109">Permissions</span></span>
<span data-ttu-id="a0898-110">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a0898-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a0898-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a0898-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a0898-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="a0898-112">Permission type</span></span> |   <span data-ttu-id="a0898-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a0898-113">Permission</span></span>  |   <span data-ttu-id="a0898-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a0898-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a0898-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="a0898-115">Application</span></span> | <span data-ttu-id="a0898-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="a0898-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="a0898-117">"Informationen zur Sicherheitsempfehlung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="a0898-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="a0898-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="a0898-118">Delegated (work or school account)</span></span> | <span data-ttu-id="a0898-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="a0898-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="a0898-120">"Informationen zur Sicherheitsempfehlung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="a0898-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="a0898-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="a0898-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="a0898-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="a0898-122">Request headers</span></span>

<span data-ttu-id="a0898-123">Name</span><span class="sxs-lookup"><span data-stu-id="a0898-123">Name</span></span> | <span data-ttu-id="a0898-124">Typ</span><span class="sxs-lookup"><span data-stu-id="a0898-124">Type</span></span> | <span data-ttu-id="a0898-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0898-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="a0898-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="a0898-126">Authorization</span></span> | <span data-ttu-id="a0898-127">String</span><span class="sxs-lookup"><span data-stu-id="a0898-127">String</span></span> | <span data-ttu-id="a0898-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a0898-128">Bearer {token}.</span></span> <span data-ttu-id="a0898-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="a0898-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a0898-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="a0898-130">Request body</span></span>
<span data-ttu-id="a0898-131">Empty</span><span class="sxs-lookup"><span data-stu-id="a0898-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a0898-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="a0898-132">Response</span></span>
<span data-ttu-id="a0898-133">Wenn die Methode erfolgreich ist, gibt sie 200 OK mit den Sicherheitsempfehlungen im Textkörper zurück.</span><span class="sxs-lookup"><span data-stu-id="a0898-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="a0898-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a0898-134">Example</span></span>

<span data-ttu-id="a0898-135">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="a0898-135">**Request**</span></span>

<span data-ttu-id="a0898-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="a0898-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="a0898-137">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="a0898-137">**Response**</span></span>

<span data-ttu-id="a0898-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="a0898-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="a0898-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a0898-139">Related topics</span></span>
- [<span data-ttu-id="a0898-140">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="a0898-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="a0898-141">Sicherheitsempfehlung & Bedrohungsrisikos</span><span class="sxs-lookup"><span data-stu-id="a0898-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

---
title: Erhalten von Sicherheitsempfehlungen
description: Ruft eine Sammlung von Sicherheitsempfehlungen im Zusammenhang mit einer bestimmten Geräte-ID ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Liste, Datei, Informationen, Sicherheitsempfehlungen pro Gerät, Api für Bedrohungen & Sicherheitsrisikomanagement, Microsoft Defender für Endpunkt-TVM-API
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
ms.openlocfilehash: 44f64334d08d8d0d6a5ed1e8e06baa2880859ad2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771129"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="97875-104">Erhalten von Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="97875-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="97875-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="97875-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="97875-106">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="97875-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="97875-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="97875-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="97875-108">Ruft eine Sammlung von Sicherheitsempfehlungen im Zusammenhang mit einer bestimmten Geräte-ID ab.</span><span class="sxs-lookup"><span data-stu-id="97875-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="97875-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="97875-109">Permissions</span></span>
<span data-ttu-id="97875-110">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="97875-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="97875-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="97875-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="97875-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="97875-112">Permission type</span></span> |   <span data-ttu-id="97875-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="97875-113">Permission</span></span>  |   <span data-ttu-id="97875-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="97875-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="97875-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="97875-115">Application</span></span> | <span data-ttu-id="97875-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="97875-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="97875-117">"Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="97875-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="97875-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="97875-118">Delegated (work or school account)</span></span> | <span data-ttu-id="97875-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="97875-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="97875-120">"Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="97875-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="97875-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="97875-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="97875-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="97875-122">Request headers</span></span>

<span data-ttu-id="97875-123">Name</span><span class="sxs-lookup"><span data-stu-id="97875-123">Name</span></span> | <span data-ttu-id="97875-124">Typ</span><span class="sxs-lookup"><span data-stu-id="97875-124">Type</span></span> | <span data-ttu-id="97875-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97875-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="97875-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="97875-126">Authorization</span></span> | <span data-ttu-id="97875-127">String</span><span class="sxs-lookup"><span data-stu-id="97875-127">String</span></span> | <span data-ttu-id="97875-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="97875-128">Bearer {token}.</span></span> <span data-ttu-id="97875-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="97875-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="97875-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="97875-130">Request body</span></span>
<span data-ttu-id="97875-131">Empty</span><span class="sxs-lookup"><span data-stu-id="97875-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="97875-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="97875-132">Response</span></span>
<span data-ttu-id="97875-133">Wenn die Methode erfolgreich ist, wird 200 OK mit den Sicherheitsempfehlungen im Text zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="97875-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="97875-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97875-134">Example</span></span>

<span data-ttu-id="97875-135">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="97875-135">**Request**</span></span>

<span data-ttu-id="97875-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="97875-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="97875-137">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="97875-137">**Response**</span></span>

<span data-ttu-id="97875-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="97875-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="97875-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="97875-139">Related topics</span></span>
- [<span data-ttu-id="97875-140">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="97875-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="97875-141">Sicherheitsempfehlungen für Sicherheitsrisiken &</span><span class="sxs-lookup"><span data-stu-id="97875-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

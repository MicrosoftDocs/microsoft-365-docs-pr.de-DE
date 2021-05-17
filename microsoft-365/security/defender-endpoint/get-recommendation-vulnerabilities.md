---
title: Auflisten von Sicherheitsrisiken nach Empfehlung
description: Ruft eine Liste der Sicherheitsrisiken ab, die der Sicherheitsempfehlung zugeordnet sind.
keywords: apis, graph api, supported apis, get, list of vulnerabilities, security recommendation, security recommendation for vulnerabilities, Bedrohungs- und Sicherheitsrisikomanagement, Bedrohungs- und Sicherheitsrisikomanagement api
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
ms.openlocfilehash: b41ee2886d758ab0ab70b78ee6d6d863d0d482a7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198601"
---
# <a name="list-vulnerabilities-by-recommendation"></a><span data-ttu-id="6e268-104">Auflisten von Sicherheitsrisiken nach Empfehlung</span><span class="sxs-lookup"><span data-stu-id="6e268-104">List vulnerabilities by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6e268-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6e268-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="6e268-106">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="6e268-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6e268-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="6e268-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6e268-108">Ruft eine Liste der Sicherheitsrisiken ab, die der Sicherheitsempfehlung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6e268-108">Retrieves a list of vulnerabilities associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="6e268-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6e268-109">Permissions</span></span>
<span data-ttu-id="6e268-110">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6e268-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6e268-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.</span><span class="sxs-lookup"><span data-stu-id="6e268-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="6e268-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="6e268-112">Permission type</span></span> |   <span data-ttu-id="6e268-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="6e268-113">Permission</span></span>  |   <span data-ttu-id="6e268-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="6e268-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6e268-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="6e268-115">Application</span></span> |   <span data-ttu-id="6e268-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="6e268-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="6e268-117">"Informationen zur Sicherheitsempfehlung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="6e268-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="6e268-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="6e268-118">Delegated (work or school account)</span></span> | <span data-ttu-id="6e268-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="6e268-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="6e268-120">"Informationen zur Sicherheitsempfehlung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="6e268-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="6e268-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="6e268-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="6e268-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="6e268-122">Request headers</span></span>

<span data-ttu-id="6e268-123">Name</span><span class="sxs-lookup"><span data-stu-id="6e268-123">Name</span></span> | <span data-ttu-id="6e268-124">Typ</span><span class="sxs-lookup"><span data-stu-id="6e268-124">Type</span></span> | <span data-ttu-id="6e268-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e268-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="6e268-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="6e268-126">Authorization</span></span> | <span data-ttu-id="6e268-127">String</span><span class="sxs-lookup"><span data-stu-id="6e268-127">String</span></span> | <span data-ttu-id="6e268-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6e268-128">Bearer {token}.</span></span> <span data-ttu-id="6e268-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="6e268-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6e268-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="6e268-130">Request body</span></span>
<span data-ttu-id="6e268-131">Empty</span><span class="sxs-lookup"><span data-stu-id="6e268-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6e268-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="6e268-132">Response</span></span>
<span data-ttu-id="6e268-133">Wenn die Methode erfolgreich ist, gibt sie 200 OK zurück, mit der Liste der Sicherheitsrisiken, die der Sicherheitsempfehlung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6e268-133">If successful, this method returns 200 OK, with the list of vulnerabilities associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="6e268-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e268-134">Example</span></span>

<span data-ttu-id="6e268-135">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="6e268-135">**Request**</span></span>

<span data-ttu-id="6e268-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="6e268-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

<span data-ttu-id="6e268-137">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="6e268-137">**Response**</span></span>

<span data-ttu-id="6e268-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="6e268-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-13748",
            "name": "CVE-2019-13748",
            "description": "Insufficient policy enforcement in developer tools in Google Chrome prior to 79.0.3945.79 allowed a local attacker to obtain potentially sensitive information from process memory via a crafted HTML page.",
            "severity": "Medium",
            "cvssV3": 6.5,
            "exposedMachines": 0,
            "publishedOn": "2019-12-10T00:00:00Z",
            "updatedOn": "2019-12-16T12:15:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
        ...
     ]
}
```

## <a name="related-topics"></a><span data-ttu-id="6e268-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6e268-139">Related topics</span></span>
- [<span data-ttu-id="6e268-140">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="6e268-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="6e268-141">Sicherheitsempfehlung & Bedrohungsrisikos</span><span class="sxs-lookup"><span data-stu-id="6e268-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

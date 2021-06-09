---
title: Auflisten von Sicherheitsrisiken nach Empfehlung
description: Ruft eine Liste der Sicherheitsrisiken ab, die der Sicherheitsempfehlung zugeordnet sind.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Liste der Sicherheitsrisiken, Sicherheitsempfehlungen, Sicherheitsempfehlungen für Sicherheitsrisiken, Bedrohungs- und Sicherheitsrisikomanagement, Bedrohungs- und Sicherheitsrisikomanagement-API
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
ms.openlocfilehash: d5a59c3cd57aa369b1edb46eebddffb84a2b8c78
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845150"
---
# <a name="list-vulnerabilities-by-recommendation"></a><span data-ttu-id="945a0-104">Auflisten von Sicherheitsrisiken nach Empfehlung</span><span class="sxs-lookup"><span data-stu-id="945a0-104">List vulnerabilities by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="945a0-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="945a0-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="945a0-106">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="945a0-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="945a0-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="945a0-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="945a0-108">Ruft eine Liste der Sicherheitsrisiken ab, die der Sicherheitsempfehlung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="945a0-108">Retrieves a list of vulnerabilities associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="945a0-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="945a0-109">Permissions</span></span>
<span data-ttu-id="945a0-110">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="945a0-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="945a0-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="945a0-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="945a0-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="945a0-112">Permission type</span></span> |   <span data-ttu-id="945a0-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="945a0-113">Permission</span></span>  |   <span data-ttu-id="945a0-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="945a0-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="945a0-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="945a0-115">Application</span></span> |   <span data-ttu-id="945a0-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="945a0-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="945a0-117">"Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="945a0-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="945a0-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="945a0-118">Delegated (work or school account)</span></span> | <span data-ttu-id="945a0-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="945a0-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="945a0-120">"Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="945a0-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="945a0-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="945a0-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="945a0-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="945a0-122">Request headers</span></span>

<span data-ttu-id="945a0-123">Name</span><span class="sxs-lookup"><span data-stu-id="945a0-123">Name</span></span> | <span data-ttu-id="945a0-124">Typ</span><span class="sxs-lookup"><span data-stu-id="945a0-124">Type</span></span> | <span data-ttu-id="945a0-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="945a0-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="945a0-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="945a0-126">Authorization</span></span> | <span data-ttu-id="945a0-127">String</span><span class="sxs-lookup"><span data-stu-id="945a0-127">String</span></span> | <span data-ttu-id="945a0-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="945a0-128">Bearer {token}.</span></span> <span data-ttu-id="945a0-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="945a0-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="945a0-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="945a0-130">Request body</span></span>
<span data-ttu-id="945a0-131">Empty</span><span class="sxs-lookup"><span data-stu-id="945a0-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="945a0-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="945a0-132">Response</span></span>
<span data-ttu-id="945a0-133">Wenn die Methode erfolgreich ist, wird 200 OK zurückgegeben, wobei die Liste der Sicherheitsrisiken der Sicherheitsempfehlung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="945a0-133">If successful, this method returns 200 OK, with the list of vulnerabilities associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="945a0-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="945a0-134">Example</span></span>

<span data-ttu-id="945a0-135">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="945a0-135">**Request**</span></span>

<span data-ttu-id="945a0-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="945a0-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

<span data-ttu-id="945a0-137">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="945a0-137">**Response**</span></span>

<span data-ttu-id="945a0-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="945a0-138">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="945a0-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="945a0-139">Related topics</span></span>
- [<span data-ttu-id="945a0-140">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="945a0-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="945a0-141">Sicherheitsempfehlungen für Sicherheitsrisiken &</span><span class="sxs-lookup"><span data-stu-id="945a0-141">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

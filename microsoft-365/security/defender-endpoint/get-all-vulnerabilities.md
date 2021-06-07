---
title: Abrufen aller Sicherheitsrisiken
description: Ruft eine Liste aller Sicherheitsrisiken ab, die sich auf die Organisation auswirken.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Sicherheitsrisikoinformationen, Microsoft Defender für Endpunkt-TVM-API
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
ms.openlocfilehash: e9dd7e7d87e9343b0aae93e7ba47d89f9ed4bf41
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769005"
---
# <a name="list-vulnerabilities"></a><span data-ttu-id="bdd67-104">Sicherheitsrisiken auflisten</span><span class="sxs-lookup"><span data-stu-id="bdd67-104">List vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bdd67-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bdd67-105">**Applies to:**</span></span>
- [<span data-ttu-id="bdd67-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bdd67-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bdd67-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bdd67-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bdd67-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="bdd67-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bdd67-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bdd67-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="bdd67-110">Ruft eine Liste aller Sicherheitsrisiken ab, die sich auf die Organisation auswirken.</span><span class="sxs-lookup"><span data-stu-id="bdd67-110">Retrieves a list of all the vulnerabilities affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="bdd67-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bdd67-111">Permissions</span></span>
<span data-ttu-id="bdd67-112">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="bdd67-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bdd67-113">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bdd67-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="bdd67-114">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="bdd67-114">Permission type</span></span> |   <span data-ttu-id="bdd67-115">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="bdd67-115">Permission</span></span>  |   <span data-ttu-id="bdd67-116">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="bdd67-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bdd67-117">Anwendung</span><span class="sxs-lookup"><span data-stu-id="bdd67-117">Application</span></span> |   <span data-ttu-id="bdd67-118">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="bdd67-118">Vulnerability.Read.All</span></span> |    <span data-ttu-id="bdd67-119">"Informationen zu Sicherheitsrisiken und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="bdd67-119">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="bdd67-120">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="bdd67-120">Delegated (work or school account)</span></span> | <span data-ttu-id="bdd67-121">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="bdd67-121">Vulnerability.Read</span></span> |   <span data-ttu-id="bdd67-122">"Informationen zu Sicherheitsrisiken und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="bdd67-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="bdd67-123">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="bdd67-123">HTTP request</span></span>
```
GET /api/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="bdd67-124">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="bdd67-124">Request headers</span></span>

<span data-ttu-id="bdd67-125">Name</span><span class="sxs-lookup"><span data-stu-id="bdd67-125">Name</span></span> | <span data-ttu-id="bdd67-126">Typ</span><span class="sxs-lookup"><span data-stu-id="bdd67-126">Type</span></span> | <span data-ttu-id="bdd67-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bdd67-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="bdd67-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="bdd67-128">Authorization</span></span> | <span data-ttu-id="bdd67-129">String</span><span class="sxs-lookup"><span data-stu-id="bdd67-129">String</span></span> | <span data-ttu-id="bdd67-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="bdd67-130">Bearer {token}.</span></span> <span data-ttu-id="bdd67-131">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="bdd67-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="bdd67-132">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="bdd67-132">Request body</span></span>
<span data-ttu-id="bdd67-133">Empty</span><span class="sxs-lookup"><span data-stu-id="bdd67-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="bdd67-134">Antwort</span><span class="sxs-lookup"><span data-stu-id="bdd67-134">Response</span></span>
<span data-ttu-id="bdd67-135">Wenn die Methode erfolgreich ist, wird 200 OK mit der Liste der Sicherheitsrisiken im Text zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bdd67-135">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="bdd67-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bdd67-136">Example</span></span>

<span data-ttu-id="bdd67-137">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="bdd67-137">**Request**</span></span>

<span data-ttu-id="bdd67-138">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="bdd67-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Vulnerabilities
```

<span data-ttu-id="bdd67-139">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="bdd67-139">**Response**</span></span>

<span data-ttu-id="bdd67-140">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="bdd67-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Vulnerabilities",
    "value": [
        {
            "id": "CVE-2019-0608",
            "name": "CVE-2019-0608",
            "description": "A spoofing vulnerability exists when Microsoft Browsers does not properly parse HTTP content. An attacker who successfully exploited this vulnerability could impersonate a user request by crafting HTTP queries. The specially crafted website could either spoof content or serve as a pivot to chain an attack with other vulnerabilities in web services.To exploit the vulnerability, the user must click a specially crafted URL. In an email attack scenario, an attacker could send an email message containing the specially crafted URL to the user in an attempt to convince the user to click it.In a web-based attack scenario, an attacker could host a specially crafted website designed to appear as a legitimate website to the user. However, the attacker would have no way to force the user to visit the specially crafted website. The attacker would have to convince the user to visit the specially crafted website, typically by way of enticement in an email or instant message, and then convince the user to interact with content on the website.The update addresses the vulnerability by correcting how Microsoft Browsers parses HTTP responses.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 4,
            "publishedOn": "2019-10-08T00:00:00Z",
            "updatedOn": "2019-12-16T16:20:00Z",
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

## <a name="see-also"></a><span data-ttu-id="bdd67-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdd67-141">See also</span></span>
- [<span data-ttu-id="bdd67-142">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="bdd67-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="bdd67-143">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="bdd67-143">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)

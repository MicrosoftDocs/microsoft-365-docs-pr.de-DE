---
title: Auflisten von Sicherheitsrisiken nach Software
description: Rufen Sie eine Liste der Sicherheitsrisiken in der installierten Software ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Liste der Sicherheitslücken, Microsoft Defender für Endpunkt-TVM-API
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
ms.openlocfilehash: 18a2cf87cd0e6b898a9f2aa4d6ecd47a86a8c7f6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769917"
---
# <a name="list-vulnerabilities-by-software"></a><span data-ttu-id="52634-104">Auflisten von Sicherheitsrisiken nach Software</span><span class="sxs-lookup"><span data-stu-id="52634-104">List vulnerabilities by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="52634-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="52634-105">**Applies to:**</span></span>
- [<span data-ttu-id="52634-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="52634-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="52634-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52634-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="52634-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="52634-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="52634-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="52634-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="52634-110">Rufen Sie eine Liste der Sicherheitsrisiken in der installierten Software ab.</span><span class="sxs-lookup"><span data-stu-id="52634-110">Retrieve a list of vulnerabilities in the installed software.</span></span> 

## <a name="permissions"></a><span data-ttu-id="52634-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="52634-111">Permissions</span></span>
<span data-ttu-id="52634-112">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="52634-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="52634-113">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="52634-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="52634-114">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="52634-114">Permission type</span></span> |   <span data-ttu-id="52634-115">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="52634-115">Permission</span></span>  |   <span data-ttu-id="52634-116">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="52634-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="52634-117">Anwendung</span><span class="sxs-lookup"><span data-stu-id="52634-117">Application</span></span> | <span data-ttu-id="52634-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="52634-118">Software.Read.All</span></span> | <span data-ttu-id="52634-119">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="52634-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="52634-120">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="52634-120">Delegated (work or school account)</span></span> | <span data-ttu-id="52634-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="52634-121">Software.Read</span></span> | <span data-ttu-id="52634-122">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="52634-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="52634-123">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="52634-123">HTTP request</span></span>
```
GET /api/Software/{Id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="52634-124">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="52634-124">Request headers</span></span>

| <span data-ttu-id="52634-125">Name</span><span class="sxs-lookup"><span data-stu-id="52634-125">Name</span></span>        | <span data-ttu-id="52634-126">Typ</span><span class="sxs-lookup"><span data-stu-id="52634-126">Type</span></span> | <span data-ttu-id="52634-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52634-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="52634-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="52634-128">Authorization</span></span> | <span data-ttu-id="52634-129">String</span><span class="sxs-lookup"><span data-stu-id="52634-129">String</span></span> | <span data-ttu-id="52634-130">Bearer {token}. **Erforderlich.**</span><span class="sxs-lookup"><span data-stu-id="52634-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="52634-131">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="52634-131">Request body</span></span>
<span data-ttu-id="52634-132">Empty</span><span class="sxs-lookup"><span data-stu-id="52634-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="52634-133">Antwort</span><span class="sxs-lookup"><span data-stu-id="52634-133">Response</span></span>
<span data-ttu-id="52634-134">Wenn die Methode erfolgreich ist, wird 200 OK mit einer Liste von Sicherheitsrisiken zurückgegeben, die von der angegebenen Software verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="52634-134">If successful, this method returns 200 OK with a list of vulnerabilities exposed by the specified software.</span></span> 


## <a name="example"></a><span data-ttu-id="52634-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="52634-135">Example</span></span>

<span data-ttu-id="52634-136">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="52634-136">**Request**</span></span>

<span data-ttu-id="52634-137">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="52634-137">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/vulnerabilities 
```

<span data-ttu-id="52634-138">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="52634-138">**Response**</span></span>

<span data-ttu-id="52634-139">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="52634-139">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
            {
                "id": "CVE-2017-0140",
                "name": "CVE-2017-0140",
                "description": "A security feature bypass vulnerability exists when Microsoft Edge improperly handles requests of different origins. The vulnerability allows Microsoft Edge to bypass Same-Origin Policy (SOP) restrictions, and to allow requests that should otherwise be ignored. An attacker who successfully exploited the vulnerability could force the browser to send data that would otherwise be restricted.In a web-based attack scenario, an attacker could host a specially crafted website that is designed to exploit the vulnerability through Microsoft Edge and then convince a user to view the website. The attacker could also take advantage of compromised websites, and websites that accept or host user-provided content or advertisements. These websites could contain specially crafted content that could exploit the vulnerability.The security update addresses the vulnerability by modifying how affected Microsoft Edge handles different-origin requests.",
                "severity": "Medium",
                "cvssV3": 4.2,
                "exposedMachines": 1,
                "publishedOn": "2017-03-14T00:00:00Z",
                "updatedOn": "2019-10-03T00:03:00Z",
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


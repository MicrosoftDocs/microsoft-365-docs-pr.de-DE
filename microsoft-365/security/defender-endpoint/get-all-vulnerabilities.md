---
title: Alle Sicherheitsrisiken erhalten
description: Ruft eine Liste aller Sicherheitsrisiken ab, die die Organisation betreffen
keywords: apis, graph api, supported apis, get, vulnerability information, Microsoft Defender for Endpoint tvm api
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
ms.technology: mde
ms.openlocfilehash: bfce003f586c5bfa32d65c834bb244ac13f6cf31
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935089"
---
# <a name="list-vulnerabilities"></a><span data-ttu-id="1c5a3-104">Sicherheitsrisiken auflisten</span><span class="sxs-lookup"><span data-stu-id="1c5a3-104">List vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1c5a3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-105">**Applies to:**</span></span>
- [<span data-ttu-id="1c5a3-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1c5a3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1c5a3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c5a3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1c5a3-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="1c5a3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1c5a3-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1c5a3-110">Ruft eine Liste aller Sicherheitsrisiken ab, die die Organisation betreffen.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-110">Retrieves a list of all the vulnerabilities affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="1c5a3-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1c5a3-111">Permissions</span></span>
<span data-ttu-id="1c5a3-112">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1c5a3-113">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="1c5a3-114">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="1c5a3-114">Permission type</span></span> |   <span data-ttu-id="1c5a3-115">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1c5a3-115">Permission</span></span>  |   <span data-ttu-id="1c5a3-116">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1c5a3-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1c5a3-117">Anwendung</span><span class="sxs-lookup"><span data-stu-id="1c5a3-117">Application</span></span> |   <span data-ttu-id="1c5a3-118">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="1c5a3-118">Vulnerability.Read.All</span></span> |    <span data-ttu-id="1c5a3-119">"Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="1c5a3-119">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="1c5a3-120">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="1c5a3-120">Delegated (work or school account)</span></span> | <span data-ttu-id="1c5a3-121">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="1c5a3-121">Vulnerability.Read</span></span> |   <span data-ttu-id="1c5a3-122">"Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="1c5a3-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="1c5a3-123">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="1c5a3-123">HTTP request</span></span>
```
GET /api/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="1c5a3-124">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="1c5a3-124">Request headers</span></span>

<span data-ttu-id="1c5a3-125">Name</span><span class="sxs-lookup"><span data-stu-id="1c5a3-125">Name</span></span> | <span data-ttu-id="1c5a3-126">Typ</span><span class="sxs-lookup"><span data-stu-id="1c5a3-126">Type</span></span> | <span data-ttu-id="1c5a3-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c5a3-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="1c5a3-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="1c5a3-128">Authorization</span></span> | <span data-ttu-id="1c5a3-129">String</span><span class="sxs-lookup"><span data-stu-id="1c5a3-129">String</span></span> | <span data-ttu-id="1c5a3-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-130">Bearer {token}.</span></span> <span data-ttu-id="1c5a3-131">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1c5a3-132">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="1c5a3-132">Request body</span></span>
<span data-ttu-id="1c5a3-133">Empty</span><span class="sxs-lookup"><span data-stu-id="1c5a3-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1c5a3-134">Antwort</span><span class="sxs-lookup"><span data-stu-id="1c5a3-134">Response</span></span>
<span data-ttu-id="1c5a3-135">Wenn die Methode erfolgreich ist, gibt sie 200 OK mit der Liste der Sicherheitsrisiken im Textkörper zurück.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-135">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="1c5a3-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c5a3-136">Example</span></span>

<span data-ttu-id="1c5a3-137">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-137">**Request**</span></span>

<span data-ttu-id="1c5a3-138">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Vulnerabilities
```

<span data-ttu-id="1c5a3-139">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="1c5a3-139">**Response**</span></span>

<span data-ttu-id="1c5a3-140">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="1c5a3-140">Here is an example of the response.</span></span>


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

## <a name="see-also"></a><span data-ttu-id="1c5a3-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c5a3-141">See also</span></span>
- [<span data-ttu-id="1c5a3-142">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="1c5a3-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="1c5a3-143">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="1c5a3-143">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)

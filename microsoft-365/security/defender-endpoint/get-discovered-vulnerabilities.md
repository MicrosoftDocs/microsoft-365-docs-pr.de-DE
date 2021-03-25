---
title: Entdecken von Sicherheitsrisiken
description: Ruft eine Sammlung von entdeckten Sicherheitsrisiken im Zusammenhang mit einer bestimmten Geräte-ID ab.
keywords: apis, graph api, supported apis, get, list, file, information, discovered vulnerabilities, threat & vulnerability management api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 08fa910c8d4c7130fdb3ed564a97cdbd2f31d233
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166573"
---
# <a name="get-discovered-vulnerabilities"></a><span data-ttu-id="dcaa1-104">Entdecken von Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="dcaa1-104">Get discovered vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dcaa1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="dcaa1-105">**Applies to:**</span></span>
- [<span data-ttu-id="dcaa1-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="dcaa1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dcaa1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dcaa1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dcaa1-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="dcaa1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dcaa1-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="dcaa1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="dcaa1-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dcaa1-110">API description</span></span>
<span data-ttu-id="dcaa1-111">Ruft eine Sammlung von entdeckten Sicherheitsrisiken im Zusammenhang mit einer bestimmten Geräte-ID ab.</span><span class="sxs-lookup"><span data-stu-id="dcaa1-111">Retrieves a collection of discovered vulnerabilities related to a given device ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="dcaa1-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="dcaa1-112">Limitations</span></span>
1. <span data-ttu-id="dcaa1-113">Die Tarifeinschränkungen für diese API sind 50 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="dcaa1-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="dcaa1-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="dcaa1-114">Permissions</span></span>

<span data-ttu-id="dcaa1-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dcaa1-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="dcaa1-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="dcaa1-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="dcaa1-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="dcaa1-117">Permission type</span></span> | <span data-ttu-id="dcaa1-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="dcaa1-118">Permission</span></span> | <span data-ttu-id="dcaa1-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="dcaa1-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="dcaa1-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="dcaa1-120">Application</span></span> |<span data-ttu-id="dcaa1-121">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="dcaa1-121">Vulnerability.Read.All</span></span> | <span data-ttu-id="dcaa1-122">"Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="dcaa1-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="dcaa1-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="dcaa1-123">Delegated (work or school account)</span></span> | <span data-ttu-id="dcaa1-124">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="dcaa1-124">Vulnerability.Read</span></span> | <span data-ttu-id="dcaa1-125">"Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="dcaa1-125">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="dcaa1-126">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="dcaa1-126">HTTP request</span></span>

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="dcaa1-127">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="dcaa1-127">Request headers</span></span>

<span data-ttu-id="dcaa1-128">Name</span><span class="sxs-lookup"><span data-stu-id="dcaa1-128">Name</span></span> | <span data-ttu-id="dcaa1-129">Typ</span><span class="sxs-lookup"><span data-stu-id="dcaa1-129">Type</span></span> | <span data-ttu-id="dcaa1-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dcaa1-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="dcaa1-131">Authorization</span><span class="sxs-lookup"><span data-stu-id="dcaa1-131">Authorization</span></span> | <span data-ttu-id="dcaa1-132">String</span><span class="sxs-lookup"><span data-stu-id="dcaa1-132">String</span></span> | <span data-ttu-id="dcaa1-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="dcaa1-133">Bearer {token}.</span></span> <span data-ttu-id="dcaa1-134">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="dcaa1-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="dcaa1-135">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="dcaa1-135">Request body</span></span>

<span data-ttu-id="dcaa1-136">Empty</span><span class="sxs-lookup"><span data-stu-id="dcaa1-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="dcaa1-137">Antwort</span><span class="sxs-lookup"><span data-stu-id="dcaa1-137">Response</span></span>

<span data-ttu-id="dcaa1-138">Wenn die Methode erfolgreich ist, gibt sie 200 OK mit den ermittelten Sicherheitsrisikoinformationen im Textkörper zurück.</span><span class="sxs-lookup"><span data-stu-id="dcaa1-138">If successful, this method returns 200 OK with the discovered vulnerability information in the body.</span></span>

## <a name="example"></a><span data-ttu-id="dcaa1-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dcaa1-139">Example</span></span>

### <a name="request"></a><span data-ttu-id="dcaa1-140">Anforderung</span><span class="sxs-lookup"><span data-stu-id="dcaa1-140">Request</span></span>

<span data-ttu-id="dcaa1-141">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="dcaa1-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a><span data-ttu-id="dcaa1-142">Antwort</span><span class="sxs-lookup"><span data-stu-id="dcaa1-142">Response</span></span>

<span data-ttu-id="dcaa1-143">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="dcaa1-143">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-1348",
            "name": "CVE-2019-1348",
            "description": "Git could allow a remote attacker to bypass security restrictions, caused by a flaw in the --export-marks option of git fast-import. By persuading a victim to import specially-crafted content, an attacker could exploit this vulnerability to overwrite arbitrary paths.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 1,
            "publishedOn": "2019-12-13T00:00:00Z",
            "updatedOn": "2019-12-13T00:00:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
}
```

## <a name="see-also"></a><span data-ttu-id="dcaa1-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dcaa1-144">See also</span></span>

- [<span data-ttu-id="dcaa1-145">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="dcaa1-145">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="dcaa1-146">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="dcaa1-146">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
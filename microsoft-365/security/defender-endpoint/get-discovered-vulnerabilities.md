---
title: Erhalten von entdeckten Sicherheitsrisiken
description: Ruft eine Sammlung von ermittelten Sicherheitsrisiken im Zusammenhang mit einer bestimmten Geräte-ID ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Liste, Datei, Informationen, erkannte Sicherheitsrisiken, Api für Bedrohungen & Sicherheitsrisikomanagement, Microsoft Defender für Endpunkt-TVM-API
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 73d9803736df546f2381b7a84c9089d2460c4c44
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843082"
---
# <a name="get-discovered-vulnerabilities"></a><span data-ttu-id="2f0fe-104">Erhalten von entdeckten Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="2f0fe-104">Get discovered vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2f0fe-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2f0fe-105">**Applies to:**</span></span>
- [<span data-ttu-id="2f0fe-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2f0fe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2f0fe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f0fe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2f0fe-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="2f0fe-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2f0fe-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2f0fe-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="2f0fe-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f0fe-110">API description</span></span>
<span data-ttu-id="2f0fe-111">Ruft eine Sammlung von ermittelten Sicherheitsrisiken im Zusammenhang mit einer bestimmten Geräte-ID ab.</span><span class="sxs-lookup"><span data-stu-id="2f0fe-111">Retrieves a collection of discovered vulnerabilities related to a given device ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="2f0fe-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="2f0fe-112">Limitations</span></span>
1. <span data-ttu-id="2f0fe-113">Die Rateneinschränkungen für diese API sind 50 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="2f0fe-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="2f0fe-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2f0fe-114">Permissions</span></span>

<span data-ttu-id="2f0fe-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2f0fe-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2f0fe-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2f0fe-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2f0fe-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="2f0fe-117">Permission type</span></span> | <span data-ttu-id="2f0fe-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="2f0fe-118">Permission</span></span> | <span data-ttu-id="2f0fe-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="2f0fe-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2f0fe-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="2f0fe-120">Application</span></span> |<span data-ttu-id="2f0fe-121">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="2f0fe-121">Vulnerability.Read.All</span></span> | <span data-ttu-id="2f0fe-122">"Informationen zu Sicherheitsrisiken und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="2f0fe-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="2f0fe-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="2f0fe-123">Delegated (work or school account)</span></span> | <span data-ttu-id="2f0fe-124">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="2f0fe-124">Vulnerability.Read</span></span> | <span data-ttu-id="2f0fe-125">"Informationen zu Sicherheitsrisiken und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="2f0fe-125">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="2f0fe-126">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="2f0fe-126">HTTP request</span></span>

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="2f0fe-127">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="2f0fe-127">Request headers</span></span>

<span data-ttu-id="2f0fe-128">Name</span><span class="sxs-lookup"><span data-stu-id="2f0fe-128">Name</span></span> | <span data-ttu-id="2f0fe-129">Typ</span><span class="sxs-lookup"><span data-stu-id="2f0fe-129">Type</span></span> | <span data-ttu-id="2f0fe-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f0fe-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="2f0fe-131">Authorization</span><span class="sxs-lookup"><span data-stu-id="2f0fe-131">Authorization</span></span> | <span data-ttu-id="2f0fe-132">String</span><span class="sxs-lookup"><span data-stu-id="2f0fe-132">String</span></span> | <span data-ttu-id="2f0fe-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2f0fe-133">Bearer {token}.</span></span> <span data-ttu-id="2f0fe-134">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="2f0fe-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2f0fe-135">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="2f0fe-135">Request body</span></span>

<span data-ttu-id="2f0fe-136">Empty</span><span class="sxs-lookup"><span data-stu-id="2f0fe-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2f0fe-137">Antwort</span><span class="sxs-lookup"><span data-stu-id="2f0fe-137">Response</span></span>

<span data-ttu-id="2f0fe-138">Wenn die Methode erfolgreich ist, wird 200 OK mit den ermittelten Sicherheitsrisikoinformationen im Text zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2f0fe-138">If successful, this method returns 200 OK with the discovered vulnerability information in the body.</span></span>

## <a name="example"></a><span data-ttu-id="2f0fe-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f0fe-139">Example</span></span>

### <a name="request"></a><span data-ttu-id="2f0fe-140">Anforderung</span><span class="sxs-lookup"><span data-stu-id="2f0fe-140">Request</span></span>

<span data-ttu-id="2f0fe-141">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="2f0fe-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a><span data-ttu-id="2f0fe-142">Antwort</span><span class="sxs-lookup"><span data-stu-id="2f0fe-142">Response</span></span>

<span data-ttu-id="2f0fe-143">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="2f0fe-143">Here is an example of the response.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2f0fe-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f0fe-144">See also</span></span>

- [<span data-ttu-id="2f0fe-145">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="2f0fe-145">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="2f0fe-146">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="2f0fe-146">Vulnerabilities in your organization</span></span>](/microsoft-365/security/defender-endpoint/tvm-weaknesses)

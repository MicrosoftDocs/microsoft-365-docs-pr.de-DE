---
title: Alle Sicherheitsrisiken per Computer und Software erhalten
description: Ruft eine Liste aller Sicherheitsrisiken ab, die die Organisation durch Computer und Software betreffen
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
ms.openlocfilehash: 229c1f9e77a0cb85744155e82934b48dd63052b2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933409"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a><span data-ttu-id="8815f-104">Auflisten von Sicherheitsrisiken nach Computer und Software</span><span class="sxs-lookup"><span data-stu-id="8815f-104">List vulnerabilities by machine and software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8815f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8815f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8815f-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8815f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8815f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8815f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8815f-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="8815f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8815f-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="8815f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="8815f-110">Ruft eine Liste aller Sicherheitsrisiken ab, die die Organisation pro [Computer und Software](machine.md) [betreffen.](software.md)</span><span class="sxs-lookup"><span data-stu-id="8815f-110">Retrieves a list of all the vulnerabilities affecting the organization per [machine](machine.md) and [software](software.md).</span></span>
- <span data-ttu-id="8815f-111">Wenn die Sicherheitsanfälligkeit über eine Behebungs-KB verfügt, wird sie in der Antwort angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8815f-111">If the vulnerability has a fixing KB, it will appear in the response.</span></span>
- <span data-ttu-id="8815f-112">Unterstützt [OData V4-Abfragen](https://www.odata.org/documentation/).</span><span class="sxs-lookup"><span data-stu-id="8815f-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
- <span data-ttu-id="8815f-113">Das OData ```$filter``` wird für alle Eigenschaften unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8815f-113">The OData ```$filter``` is supported on all properties.</span></span>

>[!Tip]
><span data-ttu-id="8815f-114">Dies ist eine großartige API für [Power BI Integration.](api-power-bi.md)</span><span class="sxs-lookup"><span data-stu-id="8815f-114">This is great API for [Power BI integration](api-power-bi.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="8815f-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8815f-115">Permissions</span></span>
<span data-ttu-id="8815f-116">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8815f-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8815f-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.</span><span class="sxs-lookup"><span data-stu-id="8815f-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="8815f-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="8815f-118">Permission type</span></span> |   <span data-ttu-id="8815f-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8815f-119">Permission</span></span>  |   <span data-ttu-id="8815f-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8815f-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8815f-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="8815f-121">Application</span></span> |   <span data-ttu-id="8815f-122">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="8815f-122">Vulnerability.Read.All</span></span> |    <span data-ttu-id="8815f-123">"Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="8815f-123">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="8815f-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="8815f-124">Delegated (work or school account)</span></span> | <span data-ttu-id="8815f-125">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="8815f-125">Vulnerability.Read</span></span> |   <span data-ttu-id="8815f-126">"Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="8815f-126">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="8815f-127">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="8815f-127">HTTP request</span></span>
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="8815f-128">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="8815f-128">Request headers</span></span>

<span data-ttu-id="8815f-129">Name</span><span class="sxs-lookup"><span data-stu-id="8815f-129">Name</span></span> | <span data-ttu-id="8815f-130">Typ</span><span class="sxs-lookup"><span data-stu-id="8815f-130">Type</span></span> | <span data-ttu-id="8815f-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8815f-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="8815f-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="8815f-132">Authorization</span></span> | <span data-ttu-id="8815f-133">String</span><span class="sxs-lookup"><span data-stu-id="8815f-133">String</span></span> | <span data-ttu-id="8815f-134">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8815f-134">Bearer {token}.</span></span> <span data-ttu-id="8815f-135">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8815f-135">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="8815f-136">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="8815f-136">Request body</span></span>
<span data-ttu-id="8815f-137">Empty</span><span class="sxs-lookup"><span data-stu-id="8815f-137">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8815f-138">Antwort</span><span class="sxs-lookup"><span data-stu-id="8815f-138">Response</span></span>
<span data-ttu-id="8815f-139">Wenn die Methode erfolgreich ist, gibt sie 200 OK mit der Liste der Sicherheitsrisiken im Textkörper zurück.</span><span class="sxs-lookup"><span data-stu-id="8815f-139">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="8815f-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8815f-140">Example</span></span>

<span data-ttu-id="8815f-141">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="8815f-141">**Request**</span></span>

<span data-ttu-id="8815f-142">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="8815f-142">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

<span data-ttu-id="8815f-143">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="8815f-143">**Response**</span></span>

<span data-ttu-id="8815f-144">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="8815f-144">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a><span data-ttu-id="8815f-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8815f-145">See also</span></span>

- [<span data-ttu-id="8815f-146">Risikobasierte Bedrohungs- und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="8815f-146">Risk-based threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="8815f-147">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="8815f-147">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)

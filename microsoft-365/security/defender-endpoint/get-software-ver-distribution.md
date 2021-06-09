---
title: Softwareversionsverteilung auflisten
description: Ruft eine Liste der Softwareversionsverteilung Ihrer Organisation ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Softwareversionsverteilung, Microsoft Defender für Endpunkt-TVM-API
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
ms.openlocfilehash: 7d0e38789cfc576c0c3f1a8be352796e674ac13a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845006"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="31778-104">Softwareversionsverteilung auflisten</span><span class="sxs-lookup"><span data-stu-id="31778-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="31778-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="31778-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="31778-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="31778-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="31778-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="31778-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="31778-108">Ruft eine Liste der Softwareversionsverteilung Ihrer Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="31778-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="31778-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="31778-109">Permissions</span></span>
<span data-ttu-id="31778-110">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="31778-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="31778-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="31778-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="31778-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="31778-112">Permission type</span></span> |   <span data-ttu-id="31778-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="31778-113">Permission</span></span>  |   <span data-ttu-id="31778-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="31778-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="31778-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="31778-115">Application</span></span> | <span data-ttu-id="31778-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="31778-116">Software.Read.All</span></span> | <span data-ttu-id="31778-117">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="31778-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="31778-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="31778-118">Delegated (work or school account)</span></span> | <span data-ttu-id="31778-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="31778-119">Software.Read</span></span> | <span data-ttu-id="31778-120">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="31778-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="31778-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="31778-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="31778-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="31778-122">Request headers</span></span>

| <span data-ttu-id="31778-123">Name</span><span class="sxs-lookup"><span data-stu-id="31778-123">Name</span></span>        | <span data-ttu-id="31778-124">Typ</span><span class="sxs-lookup"><span data-stu-id="31778-124">Type</span></span> | <span data-ttu-id="31778-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31778-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="31778-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="31778-126">Authorization</span></span> | <span data-ttu-id="31778-127">String</span><span class="sxs-lookup"><span data-stu-id="31778-127">String</span></span> | <span data-ttu-id="31778-128">Bearer {token}. **Erforderlich.**</span><span class="sxs-lookup"><span data-stu-id="31778-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="31778-129">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="31778-129">Request body</span></span>
<span data-ttu-id="31778-130">Empty</span><span class="sxs-lookup"><span data-stu-id="31778-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="31778-131">Antwort</span><span class="sxs-lookup"><span data-stu-id="31778-131">Response</span></span>
<span data-ttu-id="31778-132">Wenn die Methode erfolgreich ist, wird 200 OK mit einer Liste von Softwareverteilungsdaten im Text zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="31778-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="31778-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31778-133">Example</span></span>

<span data-ttu-id="31778-134">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="31778-134">**Request**</span></span>

<span data-ttu-id="31778-135">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="31778-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="31778-136">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="31778-136">**Response**</span></span>

<span data-ttu-id="31778-137">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="31778-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="31778-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="31778-138">Related topics</span></span>
- [<span data-ttu-id="31778-139">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="31778-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="31778-140">Softwareinventarisierung von Bedrohungen & Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="31778-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)

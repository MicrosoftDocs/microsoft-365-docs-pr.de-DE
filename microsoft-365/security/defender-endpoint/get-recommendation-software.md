---
title: Empfehlung nach Software erhalten
description: Ruft eine Sicherheitsempfehlung im Zusammenhang mit einer bestimmten Software ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Sicherheitsempfehlungen, Sicherheitsempfehlungen für Software, Bedrohungs- und Sicherheitsrisikomanagement, Bedrohungs- und Sicherheitsrisikomanagement-API
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
ms.openlocfilehash: 9227987544e1cee1eeb4b65b5ae6bbf719558dd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845208"
---
# <a name="get-recommendation-by-software"></a><span data-ttu-id="48a34-104">Empfehlung nach Software erhalten</span><span class="sxs-lookup"><span data-stu-id="48a34-104">Get recommendation by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="48a34-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="48a34-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="48a34-106">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="48a34-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="48a34-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="48a34-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="48a34-108">Ruft eine Sicherheitsempfehlung im Zusammenhang mit einer bestimmten Software ab.</span><span class="sxs-lookup"><span data-stu-id="48a34-108">Retrieves a security recommendation related to a specific software.</span></span>

## <a name="permissions"></a><span data-ttu-id="48a34-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="48a34-109">Permissions</span></span>
<span data-ttu-id="48a34-110">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="48a34-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="48a34-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="48a34-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="48a34-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="48a34-112">Permission type</span></span> |   <span data-ttu-id="48a34-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="48a34-113">Permission</span></span>  |   <span data-ttu-id="48a34-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="48a34-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="48a34-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="48a34-115">Application</span></span> |   <span data-ttu-id="48a34-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="48a34-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="48a34-117">"Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="48a34-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="48a34-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="48a34-118">Delegated (work or school account)</span></span> | <span data-ttu-id="48a34-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="48a34-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="48a34-120">"Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="48a34-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="48a34-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="48a34-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a><span data-ttu-id="48a34-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="48a34-122">Request headers</span></span>

<span data-ttu-id="48a34-123">Name</span><span class="sxs-lookup"><span data-stu-id="48a34-123">Name</span></span> | <span data-ttu-id="48a34-124">Typ</span><span class="sxs-lookup"><span data-stu-id="48a34-124">Type</span></span> | <span data-ttu-id="48a34-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48a34-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="48a34-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="48a34-126">Authorization</span></span> | <span data-ttu-id="48a34-127">String</span><span class="sxs-lookup"><span data-stu-id="48a34-127">String</span></span> | <span data-ttu-id="48a34-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="48a34-128">Bearer {token}.</span></span> <span data-ttu-id="48a34-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="48a34-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="48a34-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="48a34-130">Request body</span></span>
<span data-ttu-id="48a34-131">Empty</span><span class="sxs-lookup"><span data-stu-id="48a34-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="48a34-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="48a34-132">Response</span></span>
<span data-ttu-id="48a34-133">Wenn die Methode erfolgreich ist, wird 200 OK mit der Software zurückgegeben, die den Sicherheitsempfehlungen im Text zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="48a34-133">If successful, this method returns 200 OK with the software associated with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="48a34-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48a34-134">Example</span></span>

<span data-ttu-id="48a34-135">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="48a34-135">**Request**</span></span>

<span data-ttu-id="48a34-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="48a34-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

<span data-ttu-id="48a34-137">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="48a34-137">**Response**</span></span>

<span data-ttu-id="48a34-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="48a34-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## <a name="related-topics"></a><span data-ttu-id="48a34-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="48a34-139">Related topics</span></span>
- [<span data-ttu-id="48a34-140">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="48a34-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="48a34-141">Sicherheitsempfehlungen für Sicherheitsrisiken &</span><span class="sxs-lookup"><span data-stu-id="48a34-141">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

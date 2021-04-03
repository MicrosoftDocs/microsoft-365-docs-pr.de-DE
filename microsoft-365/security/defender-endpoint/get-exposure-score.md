---
title: Erhalten des Gefährdungsscores
description: Ruft die belichtungsergebnis der Organisation ab.
keywords: apis, graph api, supported apis, get, exposure score, organizational exposure score
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
ms.technology: mde
ms.openlocfilehash: c6b3f965c7abb1cb9208f0bfa157c1fd8aa3f891
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500710"
---
# <a name="get-exposure-score"></a><span data-ttu-id="a9a61-104">Erhalten des Gefährdungsscores</span><span class="sxs-lookup"><span data-stu-id="a9a61-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a9a61-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a9a61-105">**Applies to:**</span></span>
- [<span data-ttu-id="a9a61-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a9a61-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a9a61-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a9a61-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a9a61-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a9a61-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a9a61-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a9a61-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="a9a61-110">Ruft die belichtungsergebnis der Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="a9a61-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="a9a61-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a9a61-111">Permissions</span></span>

<span data-ttu-id="a9a61-112">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a9a61-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a9a61-113">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a9a61-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a9a61-114">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="a9a61-114">Permission type</span></span> | <span data-ttu-id="a9a61-115">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a9a61-115">Permission</span></span> | <span data-ttu-id="a9a61-116">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a9a61-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a9a61-117">Anwendung</span><span class="sxs-lookup"><span data-stu-id="a9a61-117">Application</span></span> | <span data-ttu-id="a9a61-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="a9a61-118">Score.Read.All</span></span> | <span data-ttu-id="a9a61-119">"Bewertung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="a9a61-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="a9a61-120">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="a9a61-120">Delegated (work or school account)</span></span> | <span data-ttu-id="a9a61-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="a9a61-121">Score.Read</span></span> | <span data-ttu-id="a9a61-122">"Bewertung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="a9a61-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="a9a61-123">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="a9a61-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="a9a61-124">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="a9a61-124">Request headers</span></span>

<span data-ttu-id="a9a61-125">Name</span><span class="sxs-lookup"><span data-stu-id="a9a61-125">Name</span></span> | <span data-ttu-id="a9a61-126">Typ</span><span class="sxs-lookup"><span data-stu-id="a9a61-126">Type</span></span> | <span data-ttu-id="a9a61-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9a61-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="a9a61-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="a9a61-128">Authorization</span></span> | <span data-ttu-id="a9a61-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a9a61-129">String</span></span> | <span data-ttu-id="a9a61-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a9a61-130">Bearer {token}.</span></span> <span data-ttu-id="a9a61-131">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="a9a61-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a9a61-132">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="a9a61-132">Request body</span></span>

<span data-ttu-id="a9a61-133">Empty</span><span class="sxs-lookup"><span data-stu-id="a9a61-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a9a61-134">Antwort</span><span class="sxs-lookup"><span data-stu-id="a9a61-134">Response</span></span>

<span data-ttu-id="a9a61-135">Wenn die Methode erfolgreich ist, gibt sie 200 OK zurück, mit den Belichtungsdaten im Antworttext.</span><span class="sxs-lookup"><span data-stu-id="a9a61-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="a9a61-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9a61-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="a9a61-137">Anforderung</span><span class="sxs-lookup"><span data-stu-id="a9a61-137">Request</span></span>

<span data-ttu-id="a9a61-138">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="a9a61-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="a9a61-139">Antwort</span><span class="sxs-lookup"><span data-stu-id="a9a61-139">Response</span></span>

<span data-ttu-id="a9a61-140">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="a9a61-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="a9a61-141">Die hier gezeigte Antwortliste kann aus Kürze gekürzt werden.</span><span class="sxs-lookup"><span data-stu-id="a9a61-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="a9a61-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9a61-142">See also</span></span>

- [<span data-ttu-id="a9a61-143">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="a9a61-143">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="a9a61-144">Gefährdungsrisiko & Gefährdungsrisikos</span><span class="sxs-lookup"><span data-stu-id="a9a61-144">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)

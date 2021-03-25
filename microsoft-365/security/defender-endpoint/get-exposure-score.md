---
title: Belichtungsergebnis erhalten
description: Ruft die belichtungsergebnis der Organisation ab.
keywords: apis, graph api, supported apis, get, exposure score, organizational exposure score
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
ms.openlocfilehash: e7037e49a7f750597af15cfb16e1552aeb98859a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166567"
---
# <a name="get-exposure-score"></a><span data-ttu-id="0115d-104">Belichtungsergebnis erhalten</span><span class="sxs-lookup"><span data-stu-id="0115d-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0115d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0115d-105">**Applies to:**</span></span>
- [<span data-ttu-id="0115d-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0115d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0115d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0115d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0115d-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0115d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0115d-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0115d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="0115d-110">Ruft die belichtungsergebnis der Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="0115d-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="0115d-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0115d-111">Permissions</span></span>

<span data-ttu-id="0115d-112">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0115d-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0115d-113">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0115d-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="0115d-114">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="0115d-114">Permission type</span></span> | <span data-ttu-id="0115d-115">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0115d-115">Permission</span></span> | <span data-ttu-id="0115d-116">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0115d-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0115d-117">Anwendung</span><span class="sxs-lookup"><span data-stu-id="0115d-117">Application</span></span> | <span data-ttu-id="0115d-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="0115d-118">Score.Read.All</span></span> | <span data-ttu-id="0115d-119">"Bewertung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="0115d-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="0115d-120">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="0115d-120">Delegated (work or school account)</span></span> | <span data-ttu-id="0115d-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="0115d-121">Score.Read</span></span> | <span data-ttu-id="0115d-122">"Bewertung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="0115d-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="0115d-123">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="0115d-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="0115d-124">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="0115d-124">Request headers</span></span>

<span data-ttu-id="0115d-125">Name</span><span class="sxs-lookup"><span data-stu-id="0115d-125">Name</span></span> | <span data-ttu-id="0115d-126">Typ</span><span class="sxs-lookup"><span data-stu-id="0115d-126">Type</span></span> | <span data-ttu-id="0115d-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0115d-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="0115d-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="0115d-128">Authorization</span></span> | <span data-ttu-id="0115d-129">String</span><span class="sxs-lookup"><span data-stu-id="0115d-129">String</span></span> | <span data-ttu-id="0115d-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="0115d-130">Bearer {token}.</span></span> <span data-ttu-id="0115d-131">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0115d-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="0115d-132">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="0115d-132">Request body</span></span>

<span data-ttu-id="0115d-133">Empty</span><span class="sxs-lookup"><span data-stu-id="0115d-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0115d-134">Antwort</span><span class="sxs-lookup"><span data-stu-id="0115d-134">Response</span></span>

<span data-ttu-id="0115d-135">Wenn die Methode erfolgreich ist, gibt sie 200 OK zurück, mit den Belichtungsdaten im Antworttext.</span><span class="sxs-lookup"><span data-stu-id="0115d-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="0115d-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0115d-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="0115d-137">Anforderung</span><span class="sxs-lookup"><span data-stu-id="0115d-137">Request</span></span>

<span data-ttu-id="0115d-138">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="0115d-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="0115d-139">Antwort</span><span class="sxs-lookup"><span data-stu-id="0115d-139">Response</span></span>

<span data-ttu-id="0115d-140">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="0115d-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="0115d-141">Die hier gezeigte Antwortliste kann aus Kürze gekürzt werden.</span><span class="sxs-lookup"><span data-stu-id="0115d-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="0115d-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0115d-142">See also</span></span>

- [<span data-ttu-id="0115d-143">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="0115d-143">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="0115d-144">Gefährdungsrisiko & Gefährdungsrisikos</span><span class="sxs-lookup"><span data-stu-id="0115d-144">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)

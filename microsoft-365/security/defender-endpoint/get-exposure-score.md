---
title: Erhalten des Gefährdungsscores
description: Ruft die Belichtungsbewertung der Organisation ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Belichtungsbewertung, Belichtungsbewertung der Organisation
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
ms.openlocfilehash: 071b0e7597d334fe06d5045e06a5c4d82dd65609
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845390"
---
# <a name="get-exposure-score"></a><span data-ttu-id="2a161-104">Erhalten des Gefährdungsscores</span><span class="sxs-lookup"><span data-stu-id="2a161-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2a161-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2a161-105">**Applies to:**</span></span>
- [<span data-ttu-id="2a161-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2a161-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2a161-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a161-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2a161-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="2a161-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2a161-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2a161-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="2a161-110">Ruft die Belichtungsbewertung der Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="2a161-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="2a161-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2a161-111">Permissions</span></span>

<span data-ttu-id="2a161-112">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2a161-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2a161-113">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2a161-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2a161-114">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="2a161-114">Permission type</span></span> | <span data-ttu-id="2a161-115">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="2a161-115">Permission</span></span> | <span data-ttu-id="2a161-116">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="2a161-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2a161-117">Anwendung</span><span class="sxs-lookup"><span data-stu-id="2a161-117">Application</span></span> | <span data-ttu-id="2a161-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="2a161-118">Score.Read.All</span></span> | <span data-ttu-id="2a161-119">"Bewertung der Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="2a161-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="2a161-120">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="2a161-120">Delegated (work or school account)</span></span> | <span data-ttu-id="2a161-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="2a161-121">Score.Read</span></span> | <span data-ttu-id="2a161-122">"Bewertung der Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="2a161-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="2a161-123">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="2a161-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="2a161-124">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="2a161-124">Request headers</span></span>

<span data-ttu-id="2a161-125">Name</span><span class="sxs-lookup"><span data-stu-id="2a161-125">Name</span></span> | <span data-ttu-id="2a161-126">Typ</span><span class="sxs-lookup"><span data-stu-id="2a161-126">Type</span></span> | <span data-ttu-id="2a161-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a161-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="2a161-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="2a161-128">Authorization</span></span> | <span data-ttu-id="2a161-129">String</span><span class="sxs-lookup"><span data-stu-id="2a161-129">String</span></span> | <span data-ttu-id="2a161-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2a161-130">Bearer {token}.</span></span> <span data-ttu-id="2a161-131">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="2a161-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2a161-132">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="2a161-132">Request body</span></span>

<span data-ttu-id="2a161-133">Empty</span><span class="sxs-lookup"><span data-stu-id="2a161-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2a161-134">Antwort</span><span class="sxs-lookup"><span data-stu-id="2a161-134">Response</span></span>

<span data-ttu-id="2a161-135">Wenn die Methode erfolgreich ist, wird 200 OK mit den Belichtungsdaten im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2a161-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="2a161-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2a161-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="2a161-137">Anforderung</span><span class="sxs-lookup"><span data-stu-id="2a161-137">Request</span></span>

<span data-ttu-id="2a161-138">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="2a161-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="2a161-139">Antwort</span><span class="sxs-lookup"><span data-stu-id="2a161-139">Response</span></span>

<span data-ttu-id="2a161-140">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="2a161-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="2a161-141">Die hier gezeigte Antwortliste ist möglicherweise aus Platzgründen abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="2a161-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="2a161-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a161-142">See also</span></span>

- [<span data-ttu-id="2a161-143">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="2a161-143">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="2a161-144">Sicherheitsrisikobewertung & Bedrohungsrisiko</span><span class="sxs-lookup"><span data-stu-id="2a161-144">Threat & Vulnerability exposure score</span></span>](/microsoft-365/security/defender-endpoint/tvm-exposure-score)

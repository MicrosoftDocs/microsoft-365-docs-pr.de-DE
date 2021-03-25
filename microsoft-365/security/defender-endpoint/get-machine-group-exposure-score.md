---
title: Belichtungsergebnis nach Gerätegruppe auflisten
description: Ruft eine Liste der Belichtungsergebnisse nach Gerätegruppe ab.
keywords: apis, graph api, supported apis, get, exposure score, device group, device group exposure score
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: fe4c2d4a4f18a1057472007f21936b4111673849
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166513"
---
# <a name="list-exposure-score-by-device-group"></a><span data-ttu-id="e75a2-104">Belichtungsergebnis nach Gerätegruppe auflisten</span><span class="sxs-lookup"><span data-stu-id="e75a2-104">List exposure score by device group</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e75a2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e75a2-105">**Applies to:**</span></span>
- [<span data-ttu-id="e75a2-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e75a2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e75a2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e75a2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e75a2-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="e75a2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e75a2-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e75a2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e75a2-110">Ruft eine Auflistung von Warnungen im Zusammenhang mit einer bestimmten Domänenadresse ab.</span><span class="sxs-lookup"><span data-stu-id="e75a2-110">Retrieves a collection of alerts related to a given domain address.</span></span>

## <a name="permissions"></a><span data-ttu-id="e75a2-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e75a2-111">Permissions</span></span>

<span data-ttu-id="e75a2-112">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e75a2-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e75a2-113">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e75a2-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e75a2-114">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="e75a2-114">Permission type</span></span> |   <span data-ttu-id="e75a2-115">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e75a2-115">Permission</span></span>  |   <span data-ttu-id="e75a2-116">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e75a2-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e75a2-117">Anwendung</span><span class="sxs-lookup"><span data-stu-id="e75a2-117">Application</span></span> | <span data-ttu-id="e75a2-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="e75a2-118">Score.Read.All</span></span> | <span data-ttu-id="e75a2-119">"Bewertung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="e75a2-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="e75a2-120">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="e75a2-120">Delegated (work or school account)</span></span> | <span data-ttu-id="e75a2-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="e75a2-121">Score.Read</span></span> | <span data-ttu-id="e75a2-122">"Bewertung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="e75a2-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="e75a2-123">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="e75a2-123">HTTP request</span></span>

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a><span data-ttu-id="e75a2-124">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="e75a2-124">Request headers</span></span>

| <span data-ttu-id="e75a2-125">Name</span><span class="sxs-lookup"><span data-stu-id="e75a2-125">Name</span></span>        | <span data-ttu-id="e75a2-126">Typ</span><span class="sxs-lookup"><span data-stu-id="e75a2-126">Type</span></span> | <span data-ttu-id="e75a2-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e75a2-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="e75a2-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="e75a2-128">Authorization</span></span> | <span data-ttu-id="e75a2-129">String</span><span class="sxs-lookup"><span data-stu-id="e75a2-129">String</span></span> | <span data-ttu-id="e75a2-130">Bearer {token}. **Erforderlich.**</span><span class="sxs-lookup"><span data-stu-id="e75a2-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e75a2-131">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="e75a2-131">Request body</span></span>

<span data-ttu-id="e75a2-132">Empty</span><span class="sxs-lookup"><span data-stu-id="e75a2-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e75a2-133">Antwort</span><span class="sxs-lookup"><span data-stu-id="e75a2-133">Response</span></span>

<span data-ttu-id="e75a2-134">Wenn die Methode erfolgreich ist, gibt sie 200 OK zurück, mit einer Liste der Belichtungsergebnis pro Gerätegruppendaten im Antworttext.</span><span class="sxs-lookup"><span data-stu-id="e75a2-134">If successful, this method returns 200 OK, with a list of exposure score per device group data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="e75a2-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e75a2-135">Example</span></span>

### <a name="request"></a><span data-ttu-id="e75a2-136">Anforderung</span><span class="sxs-lookup"><span data-stu-id="e75a2-136">Request</span></span>

<span data-ttu-id="e75a2-137">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="e75a2-137">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a><span data-ttu-id="e75a2-138">Antwort</span><span class="sxs-lookup"><span data-stu-id="e75a2-138">Response</span></span>

<span data-ttu-id="e75a2-139">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="e75a2-139">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="e75a2-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e75a2-140">Related topics</span></span>

- [<span data-ttu-id="e75a2-141">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="e75a2-141">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="e75a2-142">Gefährdungsrisiko & Gefährdungsrisikos</span><span class="sxs-lookup"><span data-stu-id="e75a2-142">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)

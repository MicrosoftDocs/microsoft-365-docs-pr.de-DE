---
title: Erhalten von installierter Software
description: Ruft eine Sammlung der installierten Software im Zusammenhang mit einer bestimmten Geräte-ID ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Liste, Datei, Informationen, Softwareinventarisierung, installierte Software pro Gerät, Bedrohungs-& Sicherheitsrisikomanagement-API, Microsoft Defender für Endpunkt-TVM-API
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: e13e2072ad1c18f3c6bf1abbbe95c95bb519dc3e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841108"
---
# <a name="get-installed-software"></a><span data-ttu-id="326fe-104">Erhalten von installierter Software</span><span class="sxs-lookup"><span data-stu-id="326fe-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="326fe-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="326fe-105">**Applies to:**</span></span>
- [<span data-ttu-id="326fe-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="326fe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="326fe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="326fe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="326fe-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="326fe-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="326fe-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="326fe-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="326fe-110">Ruft eine Sammlung der installierten Software im Zusammenhang mit einer bestimmten Geräte-ID ab.</span><span class="sxs-lookup"><span data-stu-id="326fe-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="326fe-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="326fe-111">Permissions</span></span>
<span data-ttu-id="326fe-112">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="326fe-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="326fe-113">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="326fe-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="326fe-114">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="326fe-114">Permission type</span></span> |   <span data-ttu-id="326fe-115">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="326fe-115">Permission</span></span>  |   <span data-ttu-id="326fe-116">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="326fe-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="326fe-117">Anwendung</span><span class="sxs-lookup"><span data-stu-id="326fe-117">Application</span></span> |<span data-ttu-id="326fe-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="326fe-118">Software.Read.All</span></span> |    <span data-ttu-id="326fe-119">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="326fe-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="326fe-120">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="326fe-120">Delegated (work or school account)</span></span> | <span data-ttu-id="326fe-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="326fe-121">Software.Read</span></span> |    <span data-ttu-id="326fe-122">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="326fe-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="326fe-123">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="326fe-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="326fe-124">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="326fe-124">Request headers</span></span>

<span data-ttu-id="326fe-125">Name</span><span class="sxs-lookup"><span data-stu-id="326fe-125">Name</span></span> | <span data-ttu-id="326fe-126">Typ</span><span class="sxs-lookup"><span data-stu-id="326fe-126">Type</span></span> | <span data-ttu-id="326fe-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="326fe-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="326fe-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="326fe-128">Authorization</span></span> | <span data-ttu-id="326fe-129">String</span><span class="sxs-lookup"><span data-stu-id="326fe-129">String</span></span> | <span data-ttu-id="326fe-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="326fe-130">Bearer {token}.</span></span> <span data-ttu-id="326fe-131">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="326fe-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="326fe-132">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="326fe-132">Request body</span></span>
<span data-ttu-id="326fe-133">Empty</span><span class="sxs-lookup"><span data-stu-id="326fe-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="326fe-134">Antwort</span><span class="sxs-lookup"><span data-stu-id="326fe-134">Response</span></span>
<span data-ttu-id="326fe-135">Wenn die Methode erfolgreich ist, wird 200 OK mit den installierten Softwareinformationen im Text zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="326fe-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="326fe-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="326fe-136">Example</span></span>

<span data-ttu-id="326fe-137">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="326fe-137">**Request**</span></span>

<span data-ttu-id="326fe-138">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="326fe-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="326fe-139">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="326fe-139">**Response**</span></span>

<span data-ttu-id="326fe-140">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="326fe-140">Here is an example of the response.</span></span>


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="326fe-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="326fe-141">See also</span></span>

- [<span data-ttu-id="326fe-142">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="326fe-142">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="326fe-143">Softwareinventarisierung von Bedrohungen & Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="326fe-143">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)

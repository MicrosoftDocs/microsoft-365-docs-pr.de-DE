---
title: Abrufen fehlender KBs nach Software-ID
description: Ruft fehlende Sicherheitsupdates anhand der Software-ID ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Liste, Datei, Informationen, Software-ID, Api für Bedrohungen & Sicherheitsrisikomanagement, Microsoft Defender für Endpunkt-TVM-API
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d9218ad447f926f0086801036277323e7c1efb4c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770559"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="16d59-104">Abrufen fehlender KBs nach Software-ID</span><span class="sxs-lookup"><span data-stu-id="16d59-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="16d59-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="16d59-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="16d59-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="16d59-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="16d59-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="16d59-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="16d59-108">Ruft fehlende KBs (Sicherheitsupdates) anhand der Software-ID ab.</span><span class="sxs-lookup"><span data-stu-id="16d59-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="16d59-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="16d59-109">Permissions</span></span>

<span data-ttu-id="16d59-110">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="16d59-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="16d59-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="16d59-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="16d59-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="16d59-112">Permission type</span></span> |   <span data-ttu-id="16d59-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="16d59-113">Permission</span></span>   |   <span data-ttu-id="16d59-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="16d59-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="16d59-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="16d59-115">Application</span></span> |<span data-ttu-id="16d59-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="16d59-116">Software.Read.All</span></span> |   <span data-ttu-id="16d59-117">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="16d59-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="16d59-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="16d59-118">Delegated (work or school account)</span></span> | <span data-ttu-id="16d59-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="16d59-119">Software.Read</span></span> |   <span data-ttu-id="16d59-120">"Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"</span><span class="sxs-lookup"><span data-stu-id="16d59-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="16d59-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="16d59-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="16d59-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="16d59-122">Request header</span></span>

<span data-ttu-id="16d59-123">Name</span><span class="sxs-lookup"><span data-stu-id="16d59-123">Name</span></span> | <span data-ttu-id="16d59-124">Typ</span><span class="sxs-lookup"><span data-stu-id="16d59-124">Type</span></span> | <span data-ttu-id="16d59-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16d59-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="16d59-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="16d59-126">Authorization</span></span> | <span data-ttu-id="16d59-127">String</span><span class="sxs-lookup"><span data-stu-id="16d59-127">String</span></span> | <span data-ttu-id="16d59-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="16d59-128">Bearer {token}.</span></span> <span data-ttu-id="16d59-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="16d59-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="16d59-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="16d59-130">Request body</span></span>

<span data-ttu-id="16d59-131">Empty</span><span class="sxs-lookup"><span data-stu-id="16d59-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="16d59-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="16d59-132">Response</span></span>

<span data-ttu-id="16d59-133">Wenn die Methode erfolgreich ist, wird 200 OK zurückgegeben, wobei der angegebenen Software kb-Daten im Text fehlen.</span><span class="sxs-lookup"><span data-stu-id="16d59-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="16d59-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16d59-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="16d59-135">Anforderung</span><span class="sxs-lookup"><span data-stu-id="16d59-135">Request</span></span>

<span data-ttu-id="16d59-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="16d59-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="16d59-137">Antwort</span><span class="sxs-lookup"><span data-stu-id="16d59-137">Response</span></span>

<span data-ttu-id="16d59-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="16d59-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="16d59-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="16d59-139">Related topics</span></span>

- [<span data-ttu-id="16d59-140">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="16d59-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="16d59-141">Softwareinventarisierung von Sicherheitsrisiken &</span><span class="sxs-lookup"><span data-stu-id="16d59-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)

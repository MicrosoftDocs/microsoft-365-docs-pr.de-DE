---
title: Fehlende KBs nach Software-ID erhalten
description: Ruft fehlende Sicherheitsupdates nach Software-ID ab
keywords: apis, graph api, supported apis, get, list, file, information, software id, threat & vulnerability management api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: c90854b043674a61c4996456c9d718b3c25afd1c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197786"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="ef24d-104">Fehlende KBs nach Software-ID erhalten</span><span class="sxs-lookup"><span data-stu-id="ef24d-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ef24d-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ef24d-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ef24d-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="ef24d-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ef24d-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="ef24d-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="ef24d-108">Ruft fehlende KBs (Sicherheitsupdates) nach Software-ID ab</span><span class="sxs-lookup"><span data-stu-id="ef24d-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="ef24d-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ef24d-109">Permissions</span></span>

<span data-ttu-id="ef24d-110">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ef24d-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ef24d-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.</span><span class="sxs-lookup"><span data-stu-id="ef24d-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="ef24d-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="ef24d-112">Permission type</span></span> |   <span data-ttu-id="ef24d-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="ef24d-113">Permission</span></span>   |   <span data-ttu-id="ef24d-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="ef24d-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ef24d-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="ef24d-115">Application</span></span> |<span data-ttu-id="ef24d-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="ef24d-116">Software.Read.All</span></span> |   <span data-ttu-id="ef24d-117">"Informationen zur Software zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="ef24d-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="ef24d-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="ef24d-118">Delegated (work or school account)</span></span> | <span data-ttu-id="ef24d-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="ef24d-119">Software.Read</span></span> |   <span data-ttu-id="ef24d-120">"Informationen zur Software zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="ef24d-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="ef24d-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="ef24d-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="ef24d-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="ef24d-122">Request header</span></span>

<span data-ttu-id="ef24d-123">Name</span><span class="sxs-lookup"><span data-stu-id="ef24d-123">Name</span></span> | <span data-ttu-id="ef24d-124">Typ</span><span class="sxs-lookup"><span data-stu-id="ef24d-124">Type</span></span> | <span data-ttu-id="ef24d-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef24d-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="ef24d-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="ef24d-126">Authorization</span></span> | <span data-ttu-id="ef24d-127">String</span><span class="sxs-lookup"><span data-stu-id="ef24d-127">String</span></span> | <span data-ttu-id="ef24d-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ef24d-128">Bearer {token}.</span></span> <span data-ttu-id="ef24d-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="ef24d-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="ef24d-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="ef24d-130">Request body</span></span>

<span data-ttu-id="ef24d-131">Empty</span><span class="sxs-lookup"><span data-stu-id="ef24d-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ef24d-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="ef24d-132">Response</span></span>

<span data-ttu-id="ef24d-133">Wenn die Methode erfolgreich ist, gibt sie 200 OK zurück, und die angegebene Software enthält keine KB-Daten im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="ef24d-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="ef24d-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef24d-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="ef24d-135">Anforderung</span><span class="sxs-lookup"><span data-stu-id="ef24d-135">Request</span></span>

<span data-ttu-id="ef24d-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="ef24d-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="ef24d-137">Antwort</span><span class="sxs-lookup"><span data-stu-id="ef24d-137">Response</span></span>

<span data-ttu-id="ef24d-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="ef24d-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="ef24d-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ef24d-139">Related topics</span></span>

- [<span data-ttu-id="ef24d-140">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="ef24d-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="ef24d-141">Softwareinventar & Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="ef24d-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)

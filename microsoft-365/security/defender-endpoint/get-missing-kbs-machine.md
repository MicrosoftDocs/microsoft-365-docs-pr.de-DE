---
title: Fehlende KBs nach Geräte-ID erhalten
description: Ruft fehlende Sicherheitsupdates nach Geräte-ID ab
keywords: apis, graph api, supported apis, get, list, file, information, device id, threat & vulnerability management api, mdatp tvm api
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
ms.openlocfilehash: 4364e6a38d4597a95d4d9a1f05dcce6fce5797ef
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500704"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="2ba2b-104">Fehlende KBs nach Geräte-ID erhalten</span><span class="sxs-lookup"><span data-stu-id="2ba2b-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ba2b-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2ba2b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2ba2b-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="2ba2b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2ba2b-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2ba2b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="2ba2b-108">Ruft fehlende KBs (Sicherheitsupdates) nach Geräte-ID ab</span><span class="sxs-lookup"><span data-stu-id="2ba2b-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="2ba2b-109">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="2ba2b-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="2ba2b-110">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="2ba2b-110">Request header</span></span>

<span data-ttu-id="2ba2b-111">Name</span><span class="sxs-lookup"><span data-stu-id="2ba2b-111">Name</span></span> | <span data-ttu-id="2ba2b-112">Typ</span><span class="sxs-lookup"><span data-stu-id="2ba2b-112">Type</span></span> | <span data-ttu-id="2ba2b-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ba2b-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="2ba2b-114">Authorization</span><span class="sxs-lookup"><span data-stu-id="2ba2b-114">Authorization</span></span> | <span data-ttu-id="2ba2b-115">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2ba2b-115">String</span></span> | <span data-ttu-id="2ba2b-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2ba2b-116">Bearer {token}.</span></span> <span data-ttu-id="2ba2b-117">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="2ba2b-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2ba2b-118">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="2ba2b-118">Request body</span></span>

<span data-ttu-id="2ba2b-119">Empty</span><span class="sxs-lookup"><span data-stu-id="2ba2b-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2ba2b-120">Antwort</span><span class="sxs-lookup"><span data-stu-id="2ba2b-120">Response</span></span>

<span data-ttu-id="2ba2b-121">Wenn die Methode erfolgreich ist, gibt sie 200 OK zurück, und auf dem angegebenen Gerät fehlen kb-Daten im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="2ba2b-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="2ba2b-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ba2b-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="2ba2b-123">Anforderung</span><span class="sxs-lookup"><span data-stu-id="2ba2b-123">Request</span></span>

<span data-ttu-id="2ba2b-124">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="2ba2b-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="2ba2b-125">Antwort</span><span class="sxs-lookup"><span data-stu-id="2ba2b-125">Response</span></span>

<span data-ttu-id="2ba2b-126">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="2ba2b-126">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="2ba2b-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2ba2b-127">Related topics</span></span>

- [<span data-ttu-id="2ba2b-128">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="2ba2b-128">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="2ba2b-129">Softwareinventar & Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="2ba2b-129">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)

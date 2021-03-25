---
title: Fehlende KBs nach Geräte-ID erhalten
description: Ruft fehlende Sicherheitsupdates nach Geräte-ID ab
keywords: apis, graph api, supported apis, get, list, file, information, device id, threat & vulnerability management api, mdatp tvm api
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
ms.openlocfilehash: 908ddf531a5a20b9811084ba534a152ad6158170
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198849"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="4b80a-104">Fehlende KBs nach Geräte-ID erhalten</span><span class="sxs-lookup"><span data-stu-id="4b80a-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4b80a-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4b80a-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="4b80a-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="4b80a-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4b80a-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4b80a-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="4b80a-108">Ruft fehlende KBs (Sicherheitsupdates) nach Geräte-ID ab</span><span class="sxs-lookup"><span data-stu-id="4b80a-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="4b80a-109">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="4b80a-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="4b80a-110">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="4b80a-110">Request header</span></span>

<span data-ttu-id="4b80a-111">Name</span><span class="sxs-lookup"><span data-stu-id="4b80a-111">Name</span></span> | <span data-ttu-id="4b80a-112">Typ</span><span class="sxs-lookup"><span data-stu-id="4b80a-112">Type</span></span> | <span data-ttu-id="4b80a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b80a-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="4b80a-114">Authorization</span><span class="sxs-lookup"><span data-stu-id="4b80a-114">Authorization</span></span> | <span data-ttu-id="4b80a-115">String</span><span class="sxs-lookup"><span data-stu-id="4b80a-115">String</span></span> | <span data-ttu-id="4b80a-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4b80a-116">Bearer {token}.</span></span> <span data-ttu-id="4b80a-117">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="4b80a-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="4b80a-118">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="4b80a-118">Request body</span></span>

<span data-ttu-id="4b80a-119">Empty</span><span class="sxs-lookup"><span data-stu-id="4b80a-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4b80a-120">Antwort</span><span class="sxs-lookup"><span data-stu-id="4b80a-120">Response</span></span>

<span data-ttu-id="4b80a-121">Wenn die Methode erfolgreich ist, gibt sie 200 OK zurück, und auf dem angegebenen Gerät fehlen kb-Daten im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="4b80a-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="4b80a-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b80a-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="4b80a-123">Anforderung</span><span class="sxs-lookup"><span data-stu-id="4b80a-123">Request</span></span>

<span data-ttu-id="4b80a-124">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4b80a-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="4b80a-125">Antwort</span><span class="sxs-lookup"><span data-stu-id="4b80a-125">Response</span></span>

<span data-ttu-id="4b80a-126">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="4b80a-126">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="4b80a-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4b80a-127">Related topics</span></span>

- [<span data-ttu-id="4b80a-128">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="4b80a-128">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="4b80a-129">Softwareinventar & Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="4b80a-129">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)

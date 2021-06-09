---
title: Abrufen fehlender KBs nach Geräte-ID
description: Ruft fehlende Sicherheitsupdates nach Geräte-ID ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Liste, Datei, Informationen, Geräte-ID, Bedrohungs-& Sicherheitsrisikomanagement-API, Microsoft Defender für Endpunkt-TVM-API
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
ms.openlocfilehash: 63400295061cd7adc58a4ddebf73f4c82b0cc969
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845234"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="dd3d1-104">Abrufen fehlender KBs nach Geräte-ID</span><span class="sxs-lookup"><span data-stu-id="dd3d1-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dd3d1-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="dd3d1-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="dd3d1-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="dd3d1-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dd3d1-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="dd3d1-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="dd3d1-108">Ruft fehlende KBs (Sicherheitsupdates) nach Geräte-ID ab.</span><span class="sxs-lookup"><span data-stu-id="dd3d1-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="dd3d1-109">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="dd3d1-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="dd3d1-110">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="dd3d1-110">Request header</span></span>

<span data-ttu-id="dd3d1-111">Name</span><span class="sxs-lookup"><span data-stu-id="dd3d1-111">Name</span></span> | <span data-ttu-id="dd3d1-112">Typ</span><span class="sxs-lookup"><span data-stu-id="dd3d1-112">Type</span></span> | <span data-ttu-id="dd3d1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd3d1-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="dd3d1-114">Authorization</span><span class="sxs-lookup"><span data-stu-id="dd3d1-114">Authorization</span></span> | <span data-ttu-id="dd3d1-115">String</span><span class="sxs-lookup"><span data-stu-id="dd3d1-115">String</span></span> | <span data-ttu-id="dd3d1-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="dd3d1-116">Bearer {token}.</span></span> <span data-ttu-id="dd3d1-117">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="dd3d1-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="dd3d1-118">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="dd3d1-118">Request body</span></span>

<span data-ttu-id="dd3d1-119">Empty</span><span class="sxs-lookup"><span data-stu-id="dd3d1-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="dd3d1-120">Antwort</span><span class="sxs-lookup"><span data-stu-id="dd3d1-120">Response</span></span>

<span data-ttu-id="dd3d1-121">Wenn die Methode erfolgreich ist, wird 200 OK zurückgegeben, wobei dem angegebenen Gerät kb-Daten im Text fehlen.</span><span class="sxs-lookup"><span data-stu-id="dd3d1-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="dd3d1-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd3d1-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="dd3d1-123">Anforderung</span><span class="sxs-lookup"><span data-stu-id="dd3d1-123">Request</span></span>

<span data-ttu-id="dd3d1-124">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="dd3d1-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="dd3d1-125">Antwort</span><span class="sxs-lookup"><span data-stu-id="dd3d1-125">Response</span></span>

<span data-ttu-id="dd3d1-126">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="dd3d1-126">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="dd3d1-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="dd3d1-127">Related topics</span></span>

- [<span data-ttu-id="dd3d1-128">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="dd3d1-128">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="dd3d1-129">Softwareinventarisierung von Bedrohungen & Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="dd3d1-129">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)

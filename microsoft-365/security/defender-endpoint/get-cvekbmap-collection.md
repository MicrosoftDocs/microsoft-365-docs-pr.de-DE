---
title: CVE-KB-Karten-API abrufen
description: Erfahren Sie, wie Sie die CVE-KB-Karten-API abrufen verwenden, um eine Zuordnung von CVE zu KB- und CVE-Details in Microsoft Defender for Endpoint abzurufen.
keywords: apis, graph api, supported apis, get, cve, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166584"
---
# <a name="get-cve-kb-map-api"></a><span data-ttu-id="19571-104">CVE-KB-Karten-API abrufen</span><span class="sxs-lookup"><span data-stu-id="19571-104">Get CVE-KB map API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="19571-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="19571-105">**Applies to:**</span></span>
- [<span data-ttu-id="19571-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="19571-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="19571-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19571-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="19571-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="19571-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="19571-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="19571-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="19571-110">Ruft eine Zuordnung von CVE zu KB- und CVE-Details ab.</span><span class="sxs-lookup"><span data-stu-id="19571-110">Retrieves a map of CVE's to KB's and CVE details.</span></span>

## <a name="permissions"></a><span data-ttu-id="19571-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="19571-111">Permissions</span></span>
<span data-ttu-id="19571-112">Der Benutzer benötigt Leseberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="19571-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="19571-113">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="19571-113">HTTP request</span></span>
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a><span data-ttu-id="19571-114">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="19571-114">Request headers</span></span>

<span data-ttu-id="19571-115">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="19571-115">Header</span></span> | <span data-ttu-id="19571-116">Wert</span><span class="sxs-lookup"><span data-stu-id="19571-116">Value</span></span> 
:---|:---
<span data-ttu-id="19571-117">Authorization</span><span class="sxs-lookup"><span data-stu-id="19571-117">Authorization</span></span> | <span data-ttu-id="19571-118">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="19571-118">Bearer {token}.</span></span> <span data-ttu-id="19571-119">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="19571-119">**Required**.</span></span>
<span data-ttu-id="19571-120">Inhaltstyp</span><span class="sxs-lookup"><span data-stu-id="19571-120">Content type</span></span> | <span data-ttu-id="19571-121">application/json</span><span class="sxs-lookup"><span data-stu-id="19571-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="19571-122">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="19571-122">Request body</span></span>
<span data-ttu-id="19571-123">Empty</span><span class="sxs-lookup"><span data-stu-id="19571-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="19571-124">Antwort</span><span class="sxs-lookup"><span data-stu-id="19571-124">Response</span></span>
<span data-ttu-id="19571-125">Wenn erfolgreich und Karte vorhanden ist - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="19571-125">If successful and map exists - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="19571-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19571-126">Example</span></span>

<span data-ttu-id="19571-127">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="19571-127">**Request**</span></span>

<span data-ttu-id="19571-128">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="19571-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

<span data-ttu-id="19571-129">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="19571-129">**Response**</span></span>

<span data-ttu-id="19571-130">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="19571-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```

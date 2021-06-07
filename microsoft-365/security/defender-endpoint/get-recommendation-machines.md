---
title: Geräte nach Empfehlung auflisten
description: Ruft eine Liste der Geräte ab, die der Sicherheitsempfehlung zugeordnet sind.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Sicherheitsempfehlungen für gefährdete Geräte, Bedrohungs- und Sicherheitsrisikomanagement, Bedrohungs- und Sicherheitsrisikomanagement-API
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 6c762a15051444ec950e92998317db4f7e51783c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771813"
---
# <a name="list-devices-by-recommendation"></a><span data-ttu-id="10d00-104">Geräte nach Empfehlung auflisten</span><span class="sxs-lookup"><span data-stu-id="10d00-104">List devices by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="10d00-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="10d00-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="10d00-106">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="10d00-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="10d00-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="10d00-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="10d00-108">Ruft eine Liste der Geräte ab, die der Sicherheitsempfehlung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="10d00-108">Retrieves a list of devices associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="10d00-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="10d00-109">Permissions</span></span>
<span data-ttu-id="10d00-110">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="10d00-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="10d00-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="10d00-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="10d00-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="10d00-112">Permission type</span></span> |   <span data-ttu-id="10d00-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="10d00-113">Permission</span></span>  |   <span data-ttu-id="10d00-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="10d00-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="10d00-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="10d00-115">Application</span></span> |   <span data-ttu-id="10d00-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="10d00-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="10d00-117">"Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="10d00-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="10d00-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="10d00-118">Delegated (work or school account)</span></span> | <span data-ttu-id="10d00-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="10d00-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="10d00-120">"Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="10d00-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="10d00-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="10d00-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/machineReferences
```

## <a name="request-headers"></a><span data-ttu-id="10d00-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="10d00-122">Request headers</span></span>

<span data-ttu-id="10d00-123">Name</span><span class="sxs-lookup"><span data-stu-id="10d00-123">Name</span></span> | <span data-ttu-id="10d00-124">Typ</span><span class="sxs-lookup"><span data-stu-id="10d00-124">Type</span></span> | <span data-ttu-id="10d00-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10d00-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="10d00-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="10d00-126">Authorization</span></span> | <span data-ttu-id="10d00-127">String</span><span class="sxs-lookup"><span data-stu-id="10d00-127">String</span></span> | <span data-ttu-id="10d00-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="10d00-128">Bearer {token}.</span></span> <span data-ttu-id="10d00-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="10d00-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="10d00-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="10d00-130">Request body</span></span>
<span data-ttu-id="10d00-131">Empty</span><span class="sxs-lookup"><span data-stu-id="10d00-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="10d00-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="10d00-132">Response</span></span>
<span data-ttu-id="10d00-133">Wenn die Methode erfolgreich ist, wird 200 OK mit der Liste der Geräte zurückgegeben, die der Sicherheitsempfehlung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="10d00-133">If successful, this method returns 200 OK with the list of devices associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="10d00-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10d00-134">Example</span></span>

<span data-ttu-id="10d00-135">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="10d00-135">**Request**</span></span>

<span data-ttu-id="10d00-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="10d00-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/machineReferences
```

<span data-ttu-id="10d00-137">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="10d00-137">**Response**</span></span>

<span data-ttu-id="10d00-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="10d00-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "e058770379bc199a9c179ce52a23e16fd44fd2ee",
            "computerDnsName": "niw_pc",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="10d00-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="10d00-139">Related topics</span></span>
- [<span data-ttu-id="10d00-140">Risikobasiertes Bedrohungs- & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="10d00-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="10d00-141">Sicherheitsempfehlungen für Sicherheitsrisiken &</span><span class="sxs-lookup"><span data-stu-id="10d00-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

---
title: Auflisten von Geräten nach Empfehlung
description: Ruft eine Liste der Geräte ab, die der Sicherheitsempfehlung zugeordnet sind.
keywords: apis, graph api, supported apis, get, security recommendation for vulnerable devices, Bedrohungs- und Sicherheitsrisikomanagement, Bedrohungs- und Sicherheitsrisikomanagement api
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
ms.openlocfilehash: 515542f6eca208e92228a8d0b344b6013b11a148
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198269"
---
# <a name="list-devices-by-recommendation"></a><span data-ttu-id="89073-104">Auflisten von Geräten nach Empfehlung</span><span class="sxs-lookup"><span data-stu-id="89073-104">List devices by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="89073-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="89073-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="89073-106">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="89073-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="89073-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="89073-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="89073-108">Ruft eine Liste der Geräte ab, die der Sicherheitsempfehlung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="89073-108">Retrieves a list of devices associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="89073-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="89073-109">Permissions</span></span>
<span data-ttu-id="89073-110">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="89073-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="89073-111">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.</span><span class="sxs-lookup"><span data-stu-id="89073-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="89073-112">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="89073-112">Permission type</span></span> |   <span data-ttu-id="89073-113">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="89073-113">Permission</span></span>  |   <span data-ttu-id="89073-114">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="89073-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="89073-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="89073-115">Application</span></span> |   <span data-ttu-id="89073-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="89073-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="89073-117">"Informationen zur Sicherheitsempfehlung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="89073-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="89073-118">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="89073-118">Delegated (work or school account)</span></span> | <span data-ttu-id="89073-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="89073-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="89073-120">"Informationen zur Sicherheitsempfehlung zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="89073-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="89073-121">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="89073-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/machineReferences
```

## <a name="request-headers"></a><span data-ttu-id="89073-122">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="89073-122">Request headers</span></span>

<span data-ttu-id="89073-123">Name</span><span class="sxs-lookup"><span data-stu-id="89073-123">Name</span></span> | <span data-ttu-id="89073-124">Typ</span><span class="sxs-lookup"><span data-stu-id="89073-124">Type</span></span> | <span data-ttu-id="89073-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89073-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="89073-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="89073-126">Authorization</span></span> | <span data-ttu-id="89073-127">String</span><span class="sxs-lookup"><span data-stu-id="89073-127">String</span></span> | <span data-ttu-id="89073-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="89073-128">Bearer {token}.</span></span> <span data-ttu-id="89073-129">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="89073-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="89073-130">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="89073-130">Request body</span></span>
<span data-ttu-id="89073-131">Empty</span><span class="sxs-lookup"><span data-stu-id="89073-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="89073-132">Antwort</span><span class="sxs-lookup"><span data-stu-id="89073-132">Response</span></span>
<span data-ttu-id="89073-133">Wenn die Methode erfolgreich ist, gibt sie 200 OK mit der Liste der Geräte zurück, die der Sicherheitsempfehlung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="89073-133">If successful, this method returns 200 OK with the list of devices associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="89073-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89073-134">Example</span></span>

<span data-ttu-id="89073-135">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="89073-135">**Request**</span></span>

<span data-ttu-id="89073-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="89073-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/machineReferences
```

<span data-ttu-id="89073-137">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="89073-137">**Response**</span></span>

<span data-ttu-id="89073-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="89073-138">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="89073-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="89073-139">Related topics</span></span>
- [<span data-ttu-id="89073-140">Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="89073-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="89073-141">Sicherheitsempfehlung & Bedrohungsrisikos</span><span class="sxs-lookup"><span data-stu-id="89073-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

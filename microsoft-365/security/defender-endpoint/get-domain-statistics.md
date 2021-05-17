---
title: Abrufen der Domänenstatistik-API
description: Erfahren Sie, wie Sie die API Domänenstatistiken abrufen verwenden, um die Statistiken für die angegebene Domäne in Microsoft Defender for Endpoint abzurufen.
keywords: apis, graph api, supported apis, get, domain, domain related devices
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: eef06657d7f691a89e5985640431c2cc706557b4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166705"
---
# <a name="get-domain-statistics-api"></a><span data-ttu-id="ac5d6-104">Abrufen der Domänenstatistik-API</span><span class="sxs-lookup"><span data-stu-id="ac5d6-104">Get domain statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ac5d6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ac5d6-105">**Applies to:**</span></span>
- [<span data-ttu-id="ac5d6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ac5d6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ac5d6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac5d6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ac5d6-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="ac5d6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ac5d6-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="ac5d6-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac5d6-110">API description</span></span>
<span data-ttu-id="ac5d6-111">Ruft die Statistiken für die angegebene Domäne ab.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-111">Retrieves the statistics on the given domain.</span></span>


## <a name="limitations"></a><span data-ttu-id="ac5d6-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ac5d6-112">Limitations</span></span>
1. <span data-ttu-id="ac5d6-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="ac5d6-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ac5d6-114">Permissions</span></span>
<span data-ttu-id="ac5d6-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ac5d6-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ac5d6-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ac5d6-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="ac5d6-117">Permission type</span></span> |   <span data-ttu-id="ac5d6-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="ac5d6-118">Permission</span></span>  |   <span data-ttu-id="ac5d6-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="ac5d6-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ac5d6-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="ac5d6-120">Application</span></span> |   <span data-ttu-id="ac5d6-121">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="ac5d6-121">URL.Read.All</span></span> |  <span data-ttu-id="ac5d6-122">'UrLs lesen'</span><span class="sxs-lookup"><span data-stu-id="ac5d6-122">'Read URLs'</span></span>
<span data-ttu-id="ac5d6-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="ac5d6-123">Delegated (work or school account)</span></span> | <span data-ttu-id="ac5d6-124">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="ac5d6-124">URL.Read.All</span></span> | <span data-ttu-id="ac5d6-125">'UrLs lesen'</span><span class="sxs-lookup"><span data-stu-id="ac5d6-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="ac5d6-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="ac5d6-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="ac5d6-127">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="ac5d6-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="ac5d6-128">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="ac5d6-128">HTTP request</span></span>
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a><span data-ttu-id="ac5d6-129">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="ac5d6-129">Request headers</span></span>

<span data-ttu-id="ac5d6-130">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="ac5d6-130">Header</span></span> | <span data-ttu-id="ac5d6-131">Wert</span><span class="sxs-lookup"><span data-stu-id="ac5d6-131">Value</span></span> 
:---|:---
<span data-ttu-id="ac5d6-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="ac5d6-132">Authorization</span></span> | <span data-ttu-id="ac5d6-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-133">Bearer {token}.</span></span> <span data-ttu-id="ac5d6-134">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-134">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="ac5d6-135">Anforderungs-URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="ac5d6-135">Request URI parameters</span></span>

<span data-ttu-id="ac5d6-136">Name</span><span class="sxs-lookup"><span data-stu-id="ac5d6-136">Name</span></span> | <span data-ttu-id="ac5d6-137">Typ</span><span class="sxs-lookup"><span data-stu-id="ac5d6-137">Type</span></span> | <span data-ttu-id="ac5d6-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac5d6-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="ac5d6-139">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="ac5d6-139">lookBackHours</span></span> | <span data-ttu-id="ac5d6-140">Int32</span><span class="sxs-lookup"><span data-stu-id="ac5d6-140">Int32</span></span> | <span data-ttu-id="ac5d6-141">Definiert die Stunden, die wir zurücksuchen, um die Statistiken zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-141">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="ac5d6-142">Standardmäßig 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-142">Defaults to 30 days.</span></span> <span data-ttu-id="ac5d6-143">**Optional**.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-143">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="ac5d6-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="ac5d6-144">Request body</span></span>
<span data-ttu-id="ac5d6-145">Empty</span><span class="sxs-lookup"><span data-stu-id="ac5d6-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ac5d6-146">Antwort</span><span class="sxs-lookup"><span data-stu-id="ac5d6-146">Response</span></span>
<span data-ttu-id="ac5d6-147">Wenn erfolgreich und Domäne vorhanden ist - 200 OK, mit statistics-Objekt im Antworttext.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-147">If successful and domain exists - 200 OK, with statistics object in the response body.</span></span> <span data-ttu-id="ac5d6-148">Wenn domäne nicht vorhanden ist - 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-148">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="ac5d6-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac5d6-149">Example</span></span>

<span data-ttu-id="ac5d6-150">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="ac5d6-150">**Request**</span></span>

<span data-ttu-id="ac5d6-151">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

<span data-ttu-id="ac5d6-152">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="ac5d6-152">**Response**</span></span>

<span data-ttu-id="ac5d6-153">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="ac5d6-153">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "orgPrevalence": "4070",
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```

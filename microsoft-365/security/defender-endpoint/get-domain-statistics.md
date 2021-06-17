---
title: Api zum Abrufen von Domänenstatistiken
description: Erfahren Sie, wie Sie die API zum Abrufen von Domänenstatistiken verwenden, um die Statistiken zu der angegebenen Domäne in Microsoft Defender für Endpunkt abzurufen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Domäne, domänenbezogene Geräte
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 50b05b98ba507e120bbd6a3dc09f4633dac3a005
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998776"
---
# <a name="get-domain-statistics-api"></a><span data-ttu-id="f1242-104">Api zum Abrufen von Domänenstatistiken</span><span class="sxs-lookup"><span data-stu-id="f1242-104">Get domain statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f1242-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f1242-105">**Applies to:**</span></span>
- [<span data-ttu-id="f1242-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f1242-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f1242-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1242-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f1242-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="f1242-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f1242-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="f1242-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f1242-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1242-110">API description</span></span>
<span data-ttu-id="f1242-111">Ruft die Statistiken für die angegebene Domäne ab.</span><span class="sxs-lookup"><span data-stu-id="f1242-111">Retrieves the statistics on the given domain.</span></span>


## <a name="limitations"></a><span data-ttu-id="f1242-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f1242-112">Limitations</span></span>
1. <span data-ttu-id="f1242-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="f1242-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="f1242-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f1242-114">Permissions</span></span>
<span data-ttu-id="f1242-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f1242-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f1242-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f1242-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f1242-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="f1242-117">Permission type</span></span> |   <span data-ttu-id="f1242-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f1242-118">Permission</span></span>  |   <span data-ttu-id="f1242-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f1242-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f1242-120">Application</span><span class="sxs-lookup"><span data-stu-id="f1242-120">Application</span></span> |   <span data-ttu-id="f1242-121">Url. Read.All</span><span class="sxs-lookup"><span data-stu-id="f1242-121">URL.Read.All</span></span> |  <span data-ttu-id="f1242-122">"Lese-URLs"</span><span class="sxs-lookup"><span data-stu-id="f1242-122">'Read URLs'</span></span>
<span data-ttu-id="f1242-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="f1242-123">Delegated (work or school account)</span></span> | <span data-ttu-id="f1242-124">Url. Read.All</span><span class="sxs-lookup"><span data-stu-id="f1242-124">URL.Read.All</span></span> | <span data-ttu-id="f1242-125">"Lese-URLs"</span><span class="sxs-lookup"><span data-stu-id="f1242-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="f1242-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="f1242-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f1242-127">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="f1242-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f1242-128">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="f1242-128">HTTP request</span></span>
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a><span data-ttu-id="f1242-129">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="f1242-129">Request headers</span></span>

<span data-ttu-id="f1242-130">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="f1242-130">Header</span></span> | <span data-ttu-id="f1242-131">Wert</span><span class="sxs-lookup"><span data-stu-id="f1242-131">Value</span></span> 
:---|:---
<span data-ttu-id="f1242-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="f1242-132">Authorization</span></span> | <span data-ttu-id="f1242-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f1242-133">Bearer {token}.</span></span> <span data-ttu-id="f1242-134">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="f1242-134">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="f1242-135">Anforderungs-URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="f1242-135">Request URI parameters</span></span>

<span data-ttu-id="f1242-136">Name</span><span class="sxs-lookup"><span data-stu-id="f1242-136">Name</span></span> | <span data-ttu-id="f1242-137">Typ</span><span class="sxs-lookup"><span data-stu-id="f1242-137">Type</span></span> | <span data-ttu-id="f1242-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1242-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="f1242-139">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="f1242-139">lookBackHours</span></span> | <span data-ttu-id="f1242-140">Int32</span><span class="sxs-lookup"><span data-stu-id="f1242-140">Int32</span></span> | <span data-ttu-id="f1242-141">Definiert die Stunden, die wir zurücksuchen, um die Statistiken abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f1242-141">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="f1242-142">Der Standardwert ist 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="f1242-142">Defaults to 30 days.</span></span> <span data-ttu-id="f1242-143">**Optional**.</span><span class="sxs-lookup"><span data-stu-id="f1242-143">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f1242-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="f1242-144">Request body</span></span>
<span data-ttu-id="f1242-145">Empty</span><span class="sxs-lookup"><span data-stu-id="f1242-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f1242-146">Antwort</span><span class="sxs-lookup"><span data-stu-id="f1242-146">Response</span></span>
<span data-ttu-id="f1242-147">Wenn erfolgreich und Domäne vorhanden – 200 OK, mit Statistikobjekt im Antworttext.</span><span class="sxs-lookup"><span data-stu-id="f1242-147">If successful and domain exists - 200 OK, with statistics object in the response body.</span></span> <span data-ttu-id="f1242-148">Wenn Domäne nicht vorhanden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="f1242-148">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="f1242-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1242-149">Example</span></span>

<span data-ttu-id="f1242-150">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="f1242-150">**Request**</span></span>

<span data-ttu-id="f1242-151">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="f1242-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

<span data-ttu-id="f1242-152">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="f1242-152">**Response**</span></span>

<span data-ttu-id="f1242-153">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="f1242-153">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "organizationPrevalence": 4070,
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```

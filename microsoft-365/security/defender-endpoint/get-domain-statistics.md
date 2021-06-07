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
ms.openlocfilehash: d2edc5d429d124412134b466753b65506d2dd7a9
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772185"
---
# <a name="get-domain-statistics-api"></a><span data-ttu-id="b13d4-104">Api zum Abrufen von Domänenstatistiken</span><span class="sxs-lookup"><span data-stu-id="b13d4-104">Get domain statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b13d4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b13d4-105">**Applies to:**</span></span>
- [<span data-ttu-id="b13d4-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b13d4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b13d4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b13d4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b13d4-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="b13d4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b13d4-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b13d4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b13d4-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b13d4-110">API description</span></span>
<span data-ttu-id="b13d4-111">Ruft die Statistiken für die angegebene Domäne ab.</span><span class="sxs-lookup"><span data-stu-id="b13d4-111">Retrieves the statistics on the given domain.</span></span>


## <a name="limitations"></a><span data-ttu-id="b13d4-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="b13d4-112">Limitations</span></span>
1. <span data-ttu-id="b13d4-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="b13d4-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="b13d4-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b13d4-114">Permissions</span></span>
<span data-ttu-id="b13d4-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b13d4-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b13d4-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b13d4-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b13d4-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="b13d4-117">Permission type</span></span> |   <span data-ttu-id="b13d4-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b13d4-118">Permission</span></span>  |   <span data-ttu-id="b13d4-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b13d4-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b13d4-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="b13d4-120">Application</span></span> |   <span data-ttu-id="b13d4-121">Url. Read.All</span><span class="sxs-lookup"><span data-stu-id="b13d4-121">URL.Read.All</span></span> |  <span data-ttu-id="b13d4-122">"Lese-URLs"</span><span class="sxs-lookup"><span data-stu-id="b13d4-122">'Read URLs'</span></span>
<span data-ttu-id="b13d4-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="b13d4-123">Delegated (work or school account)</span></span> | <span data-ttu-id="b13d4-124">Url. Read.All</span><span class="sxs-lookup"><span data-stu-id="b13d4-124">URL.Read.All</span></span> | <span data-ttu-id="b13d4-125">"Lese-URLs"</span><span class="sxs-lookup"><span data-stu-id="b13d4-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="b13d4-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="b13d4-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b13d4-127">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="b13d4-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b13d4-128">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="b13d4-128">HTTP request</span></span>
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a><span data-ttu-id="b13d4-129">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="b13d4-129">Request headers</span></span>

<span data-ttu-id="b13d4-130">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="b13d4-130">Header</span></span> | <span data-ttu-id="b13d4-131">Wert</span><span class="sxs-lookup"><span data-stu-id="b13d4-131">Value</span></span> 
:---|:---
<span data-ttu-id="b13d4-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="b13d4-132">Authorization</span></span> | <span data-ttu-id="b13d4-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b13d4-133">Bearer {token}.</span></span> <span data-ttu-id="b13d4-134">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b13d4-134">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="b13d4-135">Anforderungs-URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="b13d4-135">Request URI parameters</span></span>

<span data-ttu-id="b13d4-136">Name</span><span class="sxs-lookup"><span data-stu-id="b13d4-136">Name</span></span> | <span data-ttu-id="b13d4-137">Typ</span><span class="sxs-lookup"><span data-stu-id="b13d4-137">Type</span></span> | <span data-ttu-id="b13d4-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b13d4-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="b13d4-139">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="b13d4-139">lookBackHours</span></span> | <span data-ttu-id="b13d4-140">Int32</span><span class="sxs-lookup"><span data-stu-id="b13d4-140">Int32</span></span> | <span data-ttu-id="b13d4-141">Definiert die Stunden, die wir zurücksuchen, um die Statistiken abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b13d4-141">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="b13d4-142">Der Standardwert ist 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="b13d4-142">Defaults to 30 days.</span></span> <span data-ttu-id="b13d4-143">**Optional**.</span><span class="sxs-lookup"><span data-stu-id="b13d4-143">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b13d4-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="b13d4-144">Request body</span></span>
<span data-ttu-id="b13d4-145">Empty</span><span class="sxs-lookup"><span data-stu-id="b13d4-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b13d4-146">Antwort</span><span class="sxs-lookup"><span data-stu-id="b13d4-146">Response</span></span>
<span data-ttu-id="b13d4-147">Wenn erfolgreich und Domäne vorhanden – 200 OK, mit Statistikobjekt im Antworttext.</span><span class="sxs-lookup"><span data-stu-id="b13d4-147">If successful and domain exists - 200 OK, with statistics object in the response body.</span></span> <span data-ttu-id="b13d4-148">Wenn Domäne nicht vorhanden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="b13d4-148">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="b13d4-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b13d4-149">Example</span></span>

<span data-ttu-id="b13d4-150">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="b13d4-150">**Request**</span></span>

<span data-ttu-id="b13d4-151">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="b13d4-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

<span data-ttu-id="b13d4-152">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="b13d4-152">**Response**</span></span>

<span data-ttu-id="b13d4-153">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="b13d4-153">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "orgPrevalence": "4070",
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```

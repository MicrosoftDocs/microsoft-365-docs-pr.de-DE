---
title: Api zum Abrufen von Dateistatistiken
description: Erfahren Sie, wie Sie die API zum Abrufen von Dateistatistiken verwenden, um die Statistiken für die angegebene Datei in Microsoft Defender für Endpunkt abzurufen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Datei, Statistiken
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
ms.openlocfilehash: 6063d29562be40aed3060e241b52b1a2936aa36d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770205"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="c97c6-104">Api zum Abrufen von Dateistatistiken</span><span class="sxs-lookup"><span data-stu-id="c97c6-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c97c6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c97c6-105">**Applies to:**</span></span>
- [<span data-ttu-id="c97c6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c97c6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c97c6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c97c6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c97c6-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="c97c6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c97c6-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c97c6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c97c6-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c97c6-110">API description</span></span>
<span data-ttu-id="c97c6-111">Ruft die Statistiken für die angegebene Datei ab.</span><span class="sxs-lookup"><span data-stu-id="c97c6-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="c97c6-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="c97c6-112">Limitations</span></span>
1. <span data-ttu-id="c97c6-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="c97c6-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="c97c6-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c97c6-114">Permissions</span></span>
<span data-ttu-id="c97c6-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c97c6-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c97c6-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c97c6-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c97c6-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="c97c6-117">Permission type</span></span> |   <span data-ttu-id="c97c6-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c97c6-118">Permission</span></span>  |   <span data-ttu-id="c97c6-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c97c6-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c97c6-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="c97c6-120">Application</span></span> |   <span data-ttu-id="c97c6-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="c97c6-121">File.Read.All</span></span> | <span data-ttu-id="c97c6-122">"Dateiprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="c97c6-122">'Read file profiles'</span></span>
<span data-ttu-id="c97c6-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="c97c6-123">Delegated (work or school account)</span></span> | <span data-ttu-id="c97c6-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="c97c6-124">File.Read.All</span></span> | <span data-ttu-id="c97c6-125">"Dateiprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="c97c6-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="c97c6-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="c97c6-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c97c6-127">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c97c6-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c97c6-128">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="c97c6-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="c97c6-129">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="c97c6-129">Request headers</span></span>

<span data-ttu-id="c97c6-130">Name</span><span class="sxs-lookup"><span data-stu-id="c97c6-130">Name</span></span> | <span data-ttu-id="c97c6-131">Typ</span><span class="sxs-lookup"><span data-stu-id="c97c6-131">Type</span></span> | <span data-ttu-id="c97c6-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c97c6-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="c97c6-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="c97c6-133">Authorization</span></span> | <span data-ttu-id="c97c6-134">String</span><span class="sxs-lookup"><span data-stu-id="c97c6-134">String</span></span> | <span data-ttu-id="c97c6-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c97c6-135">Bearer {token}.</span></span> <span data-ttu-id="c97c6-136">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="c97c6-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="c97c6-137">Anforderungs-URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="c97c6-137">Request URI parameters</span></span>

<span data-ttu-id="c97c6-138">Name</span><span class="sxs-lookup"><span data-stu-id="c97c6-138">Name</span></span> | <span data-ttu-id="c97c6-139">Typ</span><span class="sxs-lookup"><span data-stu-id="c97c6-139">Type</span></span> | <span data-ttu-id="c97c6-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c97c6-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="c97c6-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="c97c6-141">lookBackHours</span></span> | <span data-ttu-id="c97c6-142">Int32</span><span class="sxs-lookup"><span data-stu-id="c97c6-142">Int32</span></span> | <span data-ttu-id="c97c6-143">Definiert die Stunden, die wir zurücksuchen, um die Statistiken abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c97c6-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="c97c6-144">Der Standardwert ist 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="c97c6-144">Defaults to 30 days.</span></span> <span data-ttu-id="c97c6-145">**Optional**.</span><span class="sxs-lookup"><span data-stu-id="c97c6-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c97c6-146">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="c97c6-146">Request body</span></span>
<span data-ttu-id="c97c6-147">Empty</span><span class="sxs-lookup"><span data-stu-id="c97c6-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c97c6-148">Antwort</span><span class="sxs-lookup"><span data-stu-id="c97c6-148">Response</span></span>
<span data-ttu-id="c97c6-149">Wenn erfolgreich und Datei vorhanden – 200 OK mit statistischen Daten im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="c97c6-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="c97c6-150">Wenn datei nicht vorhanden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="c97c6-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="c97c6-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c97c6-151">Example</span></span>

<span data-ttu-id="c97c6-152">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="c97c6-152">**Request**</span></span>

<span data-ttu-id="c97c6-153">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="c97c6-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="c97c6-154">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="c97c6-154">**Response**</span></span>

<span data-ttu-id="c97c6-155">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="c97c6-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "orgPrevalence": "14850",
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globalPrevalence": "705012",
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```

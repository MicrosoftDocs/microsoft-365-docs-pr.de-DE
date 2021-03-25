---
title: Abrufen der Api für Dateistatistiken
description: Erfahren Sie, wie Sie die API Dateistatistik abrufen verwenden, um die Statistiken für die angegebene Datei in Microsoft Defender for Endpoint abzurufen.
keywords: apis, graph api, supported apis, get, file, statistics
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
ms.openlocfilehash: ff43f6c46d89bc92cd1dc2a4fb0f329757b8f69e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166699"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="bc3be-104">Abrufen der Api für Dateistatistiken</span><span class="sxs-lookup"><span data-stu-id="bc3be-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bc3be-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bc3be-105">**Applies to:**</span></span>
- [<span data-ttu-id="bc3be-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bc3be-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bc3be-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc3be-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bc3be-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="bc3be-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bc3be-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bc3be-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="bc3be-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc3be-110">API description</span></span>
<span data-ttu-id="bc3be-111">Ruft die Statistiken für die angegebene Datei ab.</span><span class="sxs-lookup"><span data-stu-id="bc3be-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="bc3be-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="bc3be-112">Limitations</span></span>
1. <span data-ttu-id="bc3be-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="bc3be-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="bc3be-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bc3be-114">Permissions</span></span>
<span data-ttu-id="bc3be-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bc3be-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bc3be-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bc3be-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="bc3be-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="bc3be-117">Permission type</span></span> |   <span data-ttu-id="bc3be-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="bc3be-118">Permission</span></span>  |   <span data-ttu-id="bc3be-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="bc3be-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bc3be-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="bc3be-120">Application</span></span> |   <span data-ttu-id="bc3be-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="bc3be-121">File.Read.All</span></span> | <span data-ttu-id="bc3be-122">"Dateiprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="bc3be-122">'Read file profiles'</span></span>
<span data-ttu-id="bc3be-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="bc3be-123">Delegated (work or school account)</span></span> | <span data-ttu-id="bc3be-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="bc3be-124">File.Read.All</span></span> | <span data-ttu-id="bc3be-125">"Dateiprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="bc3be-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="bc3be-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="bc3be-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="bc3be-127">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="bc3be-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="bc3be-128">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="bc3be-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="bc3be-129">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="bc3be-129">Request headers</span></span>

<span data-ttu-id="bc3be-130">Name</span><span class="sxs-lookup"><span data-stu-id="bc3be-130">Name</span></span> | <span data-ttu-id="bc3be-131">Typ</span><span class="sxs-lookup"><span data-stu-id="bc3be-131">Type</span></span> | <span data-ttu-id="bc3be-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc3be-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="bc3be-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="bc3be-133">Authorization</span></span> | <span data-ttu-id="bc3be-134">String</span><span class="sxs-lookup"><span data-stu-id="bc3be-134">String</span></span> | <span data-ttu-id="bc3be-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="bc3be-135">Bearer {token}.</span></span> <span data-ttu-id="bc3be-136">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="bc3be-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="bc3be-137">Anforderungs-URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="bc3be-137">Request URI parameters</span></span>

<span data-ttu-id="bc3be-138">Name</span><span class="sxs-lookup"><span data-stu-id="bc3be-138">Name</span></span> | <span data-ttu-id="bc3be-139">Typ</span><span class="sxs-lookup"><span data-stu-id="bc3be-139">Type</span></span> | <span data-ttu-id="bc3be-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc3be-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="bc3be-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="bc3be-141">lookBackHours</span></span> | <span data-ttu-id="bc3be-142">Int32</span><span class="sxs-lookup"><span data-stu-id="bc3be-142">Int32</span></span> | <span data-ttu-id="bc3be-143">Definiert die Stunden, die wir zurücksuchen, um die Statistiken zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bc3be-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="bc3be-144">Standardmäßig 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="bc3be-144">Defaults to 30 days.</span></span> <span data-ttu-id="bc3be-145">**Optional**.</span><span class="sxs-lookup"><span data-stu-id="bc3be-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="bc3be-146">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="bc3be-146">Request body</span></span>
<span data-ttu-id="bc3be-147">Empty</span><span class="sxs-lookup"><span data-stu-id="bc3be-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="bc3be-148">Antwort</span><span class="sxs-lookup"><span data-stu-id="bc3be-148">Response</span></span>
<span data-ttu-id="bc3be-149">Wenn erfolgreich und Datei vorhanden ist – 200 OK mit statistischen Daten im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="bc3be-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="bc3be-150">Wenn die Datei nicht vorhanden ist – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="bc3be-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="bc3be-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc3be-151">Example</span></span>

<span data-ttu-id="bc3be-152">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="bc3be-152">**Request**</span></span>

<span data-ttu-id="bc3be-153">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="bc3be-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="bc3be-154">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="bc3be-154">**Response**</span></span>

<span data-ttu-id="bc3be-155">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="bc3be-155">Here is an example of the response.</span></span>


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

---
title: Suchen von Geräteinformationen über die interne IP-API
description: Verwenden Sie diese API, um Anrufe im Zusammenhang mit der Suche nach einem Geräteeintrag um einen bestimmten Zeitstempel durch interne IP zu erstellen.
keywords: ip, apis, graph api, supported apis, find device, device information
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166710"
---
# <a name="find-device-information-by-internal-ip-api"></a><span data-ttu-id="98afa-104">Suchen von Geräteinformationen über die interne IP-API</span><span class="sxs-lookup"><span data-stu-id="98afa-104">Find device information by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="98afa-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="98afa-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="98afa-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="98afa-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="98afa-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="98afa-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="98afa-108">Suchen Sie ein Gerät nach interner IP.</span><span class="sxs-lookup"><span data-stu-id="98afa-108">Find a device by internal IP.</span></span>

>[!NOTE]
><span data-ttu-id="98afa-109">Der Zeitstempel muss innerhalb der letzten 30 Tage sein.</span><span class="sxs-lookup"><span data-stu-id="98afa-109">The timestamp must be within the last 30 days.</span></span>

## <a name="permissions"></a><span data-ttu-id="98afa-110">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="98afa-110">Permissions</span></span>
<span data-ttu-id="98afa-111">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98afa-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="98afa-112">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="98afa-112">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="98afa-113">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="98afa-113">Permission type</span></span> | <span data-ttu-id="98afa-114">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="98afa-114">Permission</span></span> | <span data-ttu-id="98afa-115">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="98afa-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="98afa-116">Anwendung</span><span class="sxs-lookup"><span data-stu-id="98afa-116">Application</span></span> | <span data-ttu-id="98afa-117">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="98afa-117">Machine.Read.All</span></span> | <span data-ttu-id="98afa-118">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="98afa-118">'Read all machine profiles'</span></span>
<span data-ttu-id="98afa-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="98afa-119">Application</span></span> | <span data-ttu-id="98afa-120">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="98afa-120">Machine.ReadWrite.All</span></span> | <span data-ttu-id="98afa-121">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="98afa-121">'Read and write all machine information'</span></span>

## <a name="http-request"></a><span data-ttu-id="98afa-122">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="98afa-122">HTTP request</span></span>
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a><span data-ttu-id="98afa-123">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="98afa-123">Request headers</span></span>

<span data-ttu-id="98afa-124">Name</span><span class="sxs-lookup"><span data-stu-id="98afa-124">Name</span></span> | <span data-ttu-id="98afa-125">Typ</span><span class="sxs-lookup"><span data-stu-id="98afa-125">Type</span></span> | <span data-ttu-id="98afa-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98afa-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="98afa-127">Authorization</span><span class="sxs-lookup"><span data-stu-id="98afa-127">Authorization</span></span> | <span data-ttu-id="98afa-128">String</span><span class="sxs-lookup"><span data-stu-id="98afa-128">String</span></span> | <span data-ttu-id="98afa-129">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="98afa-129">Bearer {token}.</span></span> <span data-ttu-id="98afa-130">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="98afa-130">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="98afa-131">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="98afa-131">Request body</span></span>
<span data-ttu-id="98afa-132">Empty</span><span class="sxs-lookup"><span data-stu-id="98afa-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="98afa-133">Antwort</span><span class="sxs-lookup"><span data-stu-id="98afa-133">Response</span></span>
<span data-ttu-id="98afa-134">Wenn erfolgreich und Computer vorhanden ist – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="98afa-134">If successful and machine exists - 200 OK.</span></span>
<span data-ttu-id="98afa-135">Wenn kein Computer gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="98afa-135">If no machine found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="98afa-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98afa-136">Example</span></span>

<span data-ttu-id="98afa-137">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="98afa-137">**Request**</span></span>

<span data-ttu-id="98afa-138">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="98afa-138">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

<span data-ttu-id="98afa-139">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="98afa-139">**Response**</span></span>

<span data-ttu-id="98afa-140">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="98afa-140">Here is an example of the response.</span></span>

<span data-ttu-id="98afa-141">Die Antwort gibt eine Liste aller Geräte zurück, die diese IP-Adresse innerhalb von sechzehn Minuten vor und nach dem Zeitstempel gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="98afa-141">The response will return a list of all devices that reported this IP address within sixteen minutes prior and after the timestamp.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```

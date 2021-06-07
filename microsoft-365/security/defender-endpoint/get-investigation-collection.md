---
title: Api zum Auflisten von Untersuchungen
description: Verwenden Sie diese API, um Aufrufe im Zusammenhang mit dem Abrufen der Investigations-Sammlung zu erstellen.
keywords: APIs, Graph-API, unterstützte APIs, Investigations-Sammlung
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
ms.openlocfilehash: 38485a5028626153c26cd1e11537ef7a2daf5296
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770145"
---
# <a name="list-investigations-api"></a><span data-ttu-id="e73c9-104">Api zum Auflisten von Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="e73c9-104">List Investigations API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e73c9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e73c9-105">**Applies to:**</span></span>
- [<span data-ttu-id="e73c9-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e73c9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e73c9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e73c9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e73c9-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="e73c9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e73c9-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e73c9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e73c9-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e73c9-110">API description</span></span>
<span data-ttu-id="e73c9-111">Ruft eine Auflistung von [Untersuchungen ab.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="e73c9-111">Retrieves a collection of [Investigations](investigation.md).</span></span>
<br><span data-ttu-id="e73c9-112">Unterstützt [OData V4-Abfragen.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="e73c9-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="e73c9-113">Die ```$filter``` OData-Abfrage wird unterstützt für: ```startTime``` ```state``` , und ```machineId``` ```triggeringAlertId``` Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e73c9-113">The OData's ```$filter``` query is supported on: ```startTime```, ```state```, ```machineId``` and ```triggeringAlertId``` properties.</span></span>
<br><span data-ttu-id="e73c9-114">Beispiele für [OData-Abfragen mit Microsoft Defender für Endpunkt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="e73c9-114">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="e73c9-115">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="e73c9-115">Limitations</span></span>
1. <span data-ttu-id="e73c9-116">Die maximale Seitengröße beträgt 10.000.</span><span class="sxs-lookup"><span data-stu-id="e73c9-116">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="e73c9-117">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="e73c9-117">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="e73c9-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e73c9-118">Permissions</span></span>
<span data-ttu-id="e73c9-119">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e73c9-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e73c9-120">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e73c9-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e73c9-121">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="e73c9-121">Permission type</span></span> |   <span data-ttu-id="e73c9-122">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e73c9-122">Permission</span></span>  |   <span data-ttu-id="e73c9-123">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e73c9-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e73c9-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="e73c9-124">Application</span></span> |   <span data-ttu-id="e73c9-125">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="e73c9-125">Alert.Read.All</span></span> |    <span data-ttu-id="e73c9-126">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="e73c9-126">'Read all alerts'</span></span>
<span data-ttu-id="e73c9-127">Anwendung</span><span class="sxs-lookup"><span data-stu-id="e73c9-127">Application</span></span> |   <span data-ttu-id="e73c9-128">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e73c9-128">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="e73c9-129">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="e73c9-129">'Read and write all alerts'</span></span>
<span data-ttu-id="e73c9-130">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="e73c9-130">Delegated (work or school account)</span></span> | <span data-ttu-id="e73c9-131">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="e73c9-131">Alert.Read</span></span> | <span data-ttu-id="e73c9-132">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="e73c9-132">'Read alerts'</span></span>
<span data-ttu-id="e73c9-133">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="e73c9-133">Delegated (work or school account)</span></span> | <span data-ttu-id="e73c9-134">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e73c9-134">Alert.ReadWrite</span></span> | <span data-ttu-id="e73c9-135">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="e73c9-135">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="e73c9-136">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="e73c9-136">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e73c9-137">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="e73c9-137">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e73c9-138">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="e73c9-138">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a><span data-ttu-id="e73c9-139">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="e73c9-139">Request headers</span></span>

<span data-ttu-id="e73c9-140">Name</span><span class="sxs-lookup"><span data-stu-id="e73c9-140">Name</span></span> | <span data-ttu-id="e73c9-141">Typ</span><span class="sxs-lookup"><span data-stu-id="e73c9-141">Type</span></span> | <span data-ttu-id="e73c9-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e73c9-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="e73c9-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="e73c9-143">Authorization</span></span> | <span data-ttu-id="e73c9-144">String</span><span class="sxs-lookup"><span data-stu-id="e73c9-144">String</span></span> | <span data-ttu-id="e73c9-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e73c9-145">Bearer {token}.</span></span> <span data-ttu-id="e73c9-146">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="e73c9-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e73c9-147">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="e73c9-147">Request body</span></span>
<span data-ttu-id="e73c9-148">Empty</span><span class="sxs-lookup"><span data-stu-id="e73c9-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e73c9-149">Antwort</span><span class="sxs-lookup"><span data-stu-id="e73c9-149">Response</span></span>
<span data-ttu-id="e73c9-150">Bei erfolgreicher Ausführung gibt die Methode den Antwortcode 200,OK mit einer Auflistung von [Untersuchungentitäten](investigation.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="e73c9-150">If successful, this method returns 200, Ok response code with a collection of [Investigations](investigation.md) entities.</span></span>


## <a name="example"></a><span data-ttu-id="e73c9-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e73c9-151">Example</span></span>

<span data-ttu-id="e73c9-152">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="e73c9-152">**Request**</span></span>

<span data-ttu-id="e73c9-153">Hier ist ein Beispiel für eine Anforderung zum Abrufen aller Untersuchungen:</span><span class="sxs-lookup"><span data-stu-id="e73c9-153">Here is an example of a request to get all investigations:</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

<span data-ttu-id="e73c9-154">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="e73c9-154">**Response**</span></span>

<span data-ttu-id="e73c9-155">Nachfolgend sehen Sie ein Beispiel für die Antwort:</span><span class="sxs-lookup"><span data-stu-id="e73c9-155">Here is an example of the response:</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```

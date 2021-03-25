---
title: Auflisten der Untersuchungs-API
description: Verwenden dieser API zum Erstellen von Aufrufen im Zusammenhang mit dem Abrufen der Untersuchungssammlung
keywords: apis, graph api, supported apis, Investigations collection
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
ms.openlocfilehash: 9ad1216a05846b48bff4186c7e6f39e9da3623b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166698"
---
# <a name="list-investigations-api"></a><span data-ttu-id="f6bd1-104">Auflisten der Untersuchungs-API</span><span class="sxs-lookup"><span data-stu-id="f6bd1-104">List Investigations API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f6bd1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f6bd1-105">**Applies to:**</span></span>
- [<span data-ttu-id="f6bd1-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f6bd1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f6bd1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6bd1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f6bd1-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f6bd1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f6bd1-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f6bd1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f6bd1-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6bd1-110">API description</span></span>
<span data-ttu-id="f6bd1-111">Ruft eine Auflistung von [Investigations ab.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="f6bd1-111">Retrieves a collection of [Investigations](investigation.md).</span></span>
<br><span data-ttu-id="f6bd1-112">Unterstützt [OData V4-Abfragen](https://www.odata.org/documentation/).</span><span class="sxs-lookup"><span data-stu-id="f6bd1-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="f6bd1-113">Die OData-Abfrage ```$filter``` wird für: ```startTime``` , und ```state``` Eigenschaften ```machineId``` ```triggeringAlertId``` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f6bd1-113">The OData's ```$filter``` query is supported on: ```startTime```, ```state```, ```machineId``` and ```triggeringAlertId``` properties.</span></span>
<br><span data-ttu-id="f6bd1-114">Beispiele finden Sie [unter OData-Abfragen mit Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="f6bd1-114">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="f6bd1-115">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f6bd1-115">Limitations</span></span>
1. <span data-ttu-id="f6bd1-116">Die maximale Seitengröße beträgt 10.000.</span><span class="sxs-lookup"><span data-stu-id="f6bd1-116">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="f6bd1-117">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="f6bd1-117">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="f6bd1-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f6bd1-118">Permissions</span></span>
<span data-ttu-id="f6bd1-119">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f6bd1-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f6bd1-120">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f6bd1-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f6bd1-121">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="f6bd1-121">Permission type</span></span> |   <span data-ttu-id="f6bd1-122">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f6bd1-122">Permission</span></span>  |   <span data-ttu-id="f6bd1-123">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f6bd1-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f6bd1-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="f6bd1-124">Application</span></span> |   <span data-ttu-id="f6bd1-125">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="f6bd1-125">Alert.Read.All</span></span> |    <span data-ttu-id="f6bd1-126">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="f6bd1-126">'Read all alerts'</span></span>
<span data-ttu-id="f6bd1-127">Anwendung</span><span class="sxs-lookup"><span data-stu-id="f6bd1-127">Application</span></span> |   <span data-ttu-id="f6bd1-128">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f6bd1-128">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="f6bd1-129">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="f6bd1-129">'Read and write all alerts'</span></span>
<span data-ttu-id="f6bd1-130">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="f6bd1-130">Delegated (work or school account)</span></span> | <span data-ttu-id="f6bd1-131">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="f6bd1-131">Alert.Read</span></span> | <span data-ttu-id="f6bd1-132">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="f6bd1-132">'Read alerts'</span></span>
<span data-ttu-id="f6bd1-133">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="f6bd1-133">Delegated (work or school account)</span></span> | <span data-ttu-id="f6bd1-134">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f6bd1-134">Alert.ReadWrite</span></span> | <span data-ttu-id="f6bd1-135">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="f6bd1-135">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="f6bd1-136">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="f6bd1-136">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f6bd1-137">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="f6bd1-137">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f6bd1-138">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="f6bd1-138">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a><span data-ttu-id="f6bd1-139">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="f6bd1-139">Request headers</span></span>

<span data-ttu-id="f6bd1-140">Name</span><span class="sxs-lookup"><span data-stu-id="f6bd1-140">Name</span></span> | <span data-ttu-id="f6bd1-141">Typ</span><span class="sxs-lookup"><span data-stu-id="f6bd1-141">Type</span></span> | <span data-ttu-id="f6bd1-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6bd1-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="f6bd1-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="f6bd1-143">Authorization</span></span> | <span data-ttu-id="f6bd1-144">String</span><span class="sxs-lookup"><span data-stu-id="f6bd1-144">String</span></span> | <span data-ttu-id="f6bd1-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f6bd1-145">Bearer {token}.</span></span> <span data-ttu-id="f6bd1-146">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="f6bd1-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f6bd1-147">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="f6bd1-147">Request body</span></span>
<span data-ttu-id="f6bd1-148">Empty</span><span class="sxs-lookup"><span data-stu-id="f6bd1-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f6bd1-149">Antwort</span><span class="sxs-lookup"><span data-stu-id="f6bd1-149">Response</span></span>
<span data-ttu-id="f6bd1-150">Wenn die Methode erfolgreich ist, gibt sie den Antwortcode 200, Ok mit einer Auflistung von [Investigations-Entitäten](investigation.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="f6bd1-150">If successful, this method returns 200, Ok response code with a collection of [Investigations](investigation.md) entities.</span></span>


## <a name="example"></a><span data-ttu-id="f6bd1-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6bd1-151">Example</span></span>

<span data-ttu-id="f6bd1-152">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="f6bd1-152">**Request**</span></span>

<span data-ttu-id="f6bd1-153">Hier ist ein Beispiel für eine Anforderung, alle Untersuchungen zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="f6bd1-153">Here is an example of a request to get all investigations:</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

<span data-ttu-id="f6bd1-154">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="f6bd1-154">**Response**</span></span>

<span data-ttu-id="f6bd1-155">Hier ein Beispiel für die Antwort:</span><span class="sxs-lookup"><span data-stu-id="f6bd1-155">Here is an example of the response:</span></span>

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

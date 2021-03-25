---
title: Abrufen der Benutzer-API für Computeranmeldungen
description: Erfahren Sie, wie Sie die API Benutzer für die Computeranmeldung abrufen verwenden, um eine Sammlung von angemeldeten Benutzern auf einem Gerät in Microsoft Defender for Endpoint abzurufen.
keywords: apis, graph api, supported apis, get, device, log on, users
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
ms.openlocfilehash: 590bd1dee14e54359dd699e86795664819c23d05
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200095"
---
# <a name="get-machine-logon-users-api"></a><span data-ttu-id="ebbfa-104">Abrufen der Benutzer-API für Computeranmeldungen</span><span class="sxs-lookup"><span data-stu-id="ebbfa-104">Get machine logon users API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ebbfa-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ebbfa-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="ebbfa-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="ebbfa-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ebbfa-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="ebbfa-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebbfa-108">API description</span></span>
<span data-ttu-id="ebbfa-109">Ruft eine Sammlung von angemeldeten Benutzern auf einem bestimmten Gerät ab.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-109">Retrieves a collection of logged on users on a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="ebbfa-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ebbfa-110">Limitations</span></span>
1. <span data-ttu-id="ebbfa-111">Sie können Warnungen abfragen, die zuletzt entsprechend ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-111">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="ebbfa-112">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="ebbfa-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ebbfa-113">Permissions</span></span>
<span data-ttu-id="ebbfa-114">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ebbfa-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ebbfa-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ebbfa-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="ebbfa-116">Permission type</span></span> |   <span data-ttu-id="ebbfa-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="ebbfa-117">Permission</span></span>  |   <span data-ttu-id="ebbfa-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="ebbfa-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ebbfa-119">Application</span><span class="sxs-lookup"><span data-stu-id="ebbfa-119">Application</span></span> |   <span data-ttu-id="ebbfa-120">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="ebbfa-120">User.Read.All</span></span> | <span data-ttu-id="ebbfa-121">"Benutzerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="ebbfa-121">'Read user profiles'</span></span>
<span data-ttu-id="ebbfa-122">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="ebbfa-122">Delegated (work or school account)</span></span> | <span data-ttu-id="ebbfa-123">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="ebbfa-123">User.Read.All</span></span> | <span data-ttu-id="ebbfa-124">"Benutzerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="ebbfa-124">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="ebbfa-125">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="ebbfa-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="ebbfa-126">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen".</span><span class="sxs-lookup"><span data-stu-id="ebbfa-126">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="ebbfa-127">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen](user-roles.md) )</span><span class="sxs-lookup"><span data-stu-id="ebbfa-127">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="ebbfa-128">Die Antwort umfasst nur Benutzer, wenn das Gerät basierend auf den Einstellungen für Gerätegruppen für den Benutzer sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-128">Response will include users only if the device is visible to the user, based on device group settings.</span></span> <span data-ttu-id="ebbfa-129">Weitere Informationen finden Sie unter [Create and manage device groups](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="ebbfa-129">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="ebbfa-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="ebbfa-130">HTTP request</span></span>
```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a><span data-ttu-id="ebbfa-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="ebbfa-131">Request headers</span></span>

<span data-ttu-id="ebbfa-132">Name</span><span class="sxs-lookup"><span data-stu-id="ebbfa-132">Name</span></span> | <span data-ttu-id="ebbfa-133">Typ</span><span class="sxs-lookup"><span data-stu-id="ebbfa-133">Type</span></span> | <span data-ttu-id="ebbfa-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebbfa-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="ebbfa-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="ebbfa-135">Authorization</span></span> | <span data-ttu-id="ebbfa-136">String</span><span class="sxs-lookup"><span data-stu-id="ebbfa-136">String</span></span> | <span data-ttu-id="ebbfa-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-137">Bearer {token}.</span></span> <span data-ttu-id="ebbfa-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ebbfa-139">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="ebbfa-139">Request body</span></span>
<span data-ttu-id="ebbfa-140">Empty</span><span class="sxs-lookup"><span data-stu-id="ebbfa-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ebbfa-141">Antwort</span><span class="sxs-lookup"><span data-stu-id="ebbfa-141">Response</span></span>
<span data-ttu-id="ebbfa-142">Wenn erfolgreich und Gerät vorhanden ist – [](user.md) 200 OK mit liste der Benutzerentitäten im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-142">If successful and device exists - 200 OK with list of [user](user.md) entities in the body.</span></span> <span data-ttu-id="ebbfa-143">Wenn das Gerät nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-143">If device was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="ebbfa-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebbfa-144">Example</span></span>

<span data-ttu-id="ebbfa-145">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="ebbfa-145">**Request**</span></span>

<span data-ttu-id="ebbfa-146">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

<span data-ttu-id="ebbfa-147">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="ebbfa-147">**Response**</span></span>

<span data-ttu-id="ebbfa-148">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-148">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```

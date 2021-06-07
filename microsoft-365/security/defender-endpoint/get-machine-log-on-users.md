---
title: API für Computeranmeldungen abrufen
description: In diesem Artikel erfahren Sie, wie Sie mithilfe der API zum Abrufen von Computern angemeldeter Benutzer eine Sammlung angemeldeter Benutzer auf einem Gerät in Microsoft Defender für Endpunkt abrufen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Gerät, anmelden, Benutzer
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 1c81d2978677b751a8085f88b5c4732fd4a5a247
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770049"
---
# <a name="get-machine-logon-users-api"></a><span data-ttu-id="f8cc8-104">API für Computeranmeldungen abrufen</span><span class="sxs-lookup"><span data-stu-id="f8cc8-104">Get machine logon users API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f8cc8-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f8cc8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="f8cc8-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="f8cc8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f8cc8-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f8cc8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f8cc8-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8cc8-108">API description</span></span>
<span data-ttu-id="f8cc8-109">Ruft eine Sammlung der angemeldeten Benutzer auf einem bestimmten Gerät ab.</span><span class="sxs-lookup"><span data-stu-id="f8cc8-109">Retrieves a collection of logged on users on a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="f8cc8-110">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="f8cc8-110">Limitations</span></span>
1. <span data-ttu-id="f8cc8-111">Sie können nach Warnungen abfragen, die zuletzt gemäß Ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f8cc8-111">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="f8cc8-112">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="f8cc8-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="f8cc8-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f8cc8-113">Permissions</span></span>
<span data-ttu-id="f8cc8-114">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f8cc8-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f8cc8-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f8cc8-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f8cc8-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="f8cc8-116">Permission type</span></span> |   <span data-ttu-id="f8cc8-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f8cc8-117">Permission</span></span>  |   <span data-ttu-id="f8cc8-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f8cc8-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f8cc8-119">Application</span><span class="sxs-lookup"><span data-stu-id="f8cc8-119">Application</span></span> |   <span data-ttu-id="f8cc8-120">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="f8cc8-120">User.Read.All</span></span> | <span data-ttu-id="f8cc8-121">"Benutzerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="f8cc8-121">'Read user profiles'</span></span>
<span data-ttu-id="f8cc8-122">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="f8cc8-122">Delegated (work or school account)</span></span> | <span data-ttu-id="f8cc8-123">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="f8cc8-123">User.Read.All</span></span> | <span data-ttu-id="f8cc8-124">"Benutzerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="f8cc8-124">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="f8cc8-125">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="f8cc8-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f8cc8-126">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen".</span><span class="sxs-lookup"><span data-stu-id="f8cc8-126">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="f8cc8-127">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen](user-roles.md) )</span><span class="sxs-lookup"><span data-stu-id="f8cc8-127">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="f8cc8-128">Die Antwort schließt Benutzer nur ein, wenn das Gerät basierend auf den Gerätegruppeneinstellungen für den Benutzer sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="f8cc8-128">Response will include users only if the device is visible to the user, based on device group settings.</span></span> <span data-ttu-id="f8cc8-129">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="f8cc8-129">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="f8cc8-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="f8cc8-130">HTTP request</span></span>
```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a><span data-ttu-id="f8cc8-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="f8cc8-131">Request headers</span></span>

<span data-ttu-id="f8cc8-132">Name</span><span class="sxs-lookup"><span data-stu-id="f8cc8-132">Name</span></span> | <span data-ttu-id="f8cc8-133">Typ</span><span class="sxs-lookup"><span data-stu-id="f8cc8-133">Type</span></span> | <span data-ttu-id="f8cc8-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8cc8-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="f8cc8-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="f8cc8-135">Authorization</span></span> | <span data-ttu-id="f8cc8-136">String</span><span class="sxs-lookup"><span data-stu-id="f8cc8-136">String</span></span> | <span data-ttu-id="f8cc8-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f8cc8-137">Bearer {token}.</span></span> <span data-ttu-id="f8cc8-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="f8cc8-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f8cc8-139">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="f8cc8-139">Request body</span></span>
<span data-ttu-id="f8cc8-140">Empty</span><span class="sxs-lookup"><span data-stu-id="f8cc8-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f8cc8-141">Antwort</span><span class="sxs-lookup"><span data-stu-id="f8cc8-141">Response</span></span>
<span data-ttu-id="f8cc8-142">Wenn erfolgreich und Gerät vorhanden – 200 OK mit Liste der Benutzerentitäten im Textkörper. [](user.md)</span><span class="sxs-lookup"><span data-stu-id="f8cc8-142">If successful and device exists - 200 OK with list of [user](user.md) entities in the body.</span></span> <span data-ttu-id="f8cc8-143">Wenn das Gerät nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="f8cc8-143">If device was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="f8cc8-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8cc8-144">Example</span></span>

<span data-ttu-id="f8cc8-145">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="f8cc8-145">**Request**</span></span>

<span data-ttu-id="f8cc8-146">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="f8cc8-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

<span data-ttu-id="f8cc8-147">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="f8cc8-147">**Response**</span></span>

<span data-ttu-id="f8cc8-148">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="f8cc8-148">Here is an example of the response.</span></span>


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

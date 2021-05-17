---
title: Erhalten von Informationen zu Benachrichtigungen zu Benutzern
description: Hier erfahren Sie, wie Sie die API Zum Abrufen von Benachrichtigungsinformationen für Benutzer verwenden, um den Benutzer im Zusammenhang mit einer bestimmten Warnung in Microsoft Defender for Endpoint abzurufen.
keywords: apis, graph api, supported apis, get, alert, information, related, user
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
ms.openlocfilehash: aee3c6fb381341c6823fbcb6766c0b761cb3413d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166627"
---
# <a name="get-alert-related-user-information-api"></a><span data-ttu-id="64223-104">Abrufen der Benachrichtigungs-API für Benutzerinformationen</span><span class="sxs-lookup"><span data-stu-id="64223-104">Get alert related user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="64223-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="64223-105">**Applies to:**</span></span>
- [<span data-ttu-id="64223-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="64223-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="64223-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64223-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="64223-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="64223-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="64223-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="64223-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="64223-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64223-110">API description</span></span>
<span data-ttu-id="64223-111">Ruft den Benutzer im Zusammenhang mit einer bestimmten Warnung ab.</span><span class="sxs-lookup"><span data-stu-id="64223-111">Retrieves the User related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="64223-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="64223-112">Limitations</span></span>
1. <span data-ttu-id="64223-113">Sie können Warnungen abfragen, die zuletzt entsprechend ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="64223-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="64223-114">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="64223-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="64223-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="64223-115">Permissions</span></span>
<span data-ttu-id="64223-116">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="64223-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="64223-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="64223-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="64223-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="64223-118">Permission type</span></span> |   <span data-ttu-id="64223-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="64223-119">Permission</span></span>  |   <span data-ttu-id="64223-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="64223-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="64223-121">Application</span><span class="sxs-lookup"><span data-stu-id="64223-121">Application</span></span> |   <span data-ttu-id="64223-122">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="64223-122">User.Read.All</span></span> | <span data-ttu-id="64223-123">"Benutzerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="64223-123">'Read user profiles'</span></span>
<span data-ttu-id="64223-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="64223-124">Delegated (work or school account)</span></span> | <span data-ttu-id="64223-125">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="64223-125">User.Read.All</span></span> | <span data-ttu-id="64223-126">"Benutzerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="64223-126">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="64223-127">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="64223-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="64223-128">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="64223-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="64223-129">Der Benutzer muss auf das Gerät zugreifen können, das der Warnung zugeordnet ist, basierend auf den Gerätegruppeneinstellungen (Weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen)</span><span class="sxs-lookup"><span data-stu-id="64223-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="64223-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="64223-130">HTTP request</span></span>
```
GET /api/alerts/{id}/user
```

## <a name="request-headers"></a><span data-ttu-id="64223-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="64223-131">Request headers</span></span>

<span data-ttu-id="64223-132">Name</span><span class="sxs-lookup"><span data-stu-id="64223-132">Name</span></span> | <span data-ttu-id="64223-133">Typ</span><span class="sxs-lookup"><span data-stu-id="64223-133">Type</span></span> | <span data-ttu-id="64223-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64223-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="64223-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="64223-135">Authorization</span></span> | <span data-ttu-id="64223-136">String</span><span class="sxs-lookup"><span data-stu-id="64223-136">String</span></span> | <span data-ttu-id="64223-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="64223-137">Bearer {token}.</span></span> <span data-ttu-id="64223-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="64223-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="64223-139">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="64223-139">Request body</span></span>
<span data-ttu-id="64223-140">Empty</span><span class="sxs-lookup"><span data-stu-id="64223-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="64223-141">Antwort</span><span class="sxs-lookup"><span data-stu-id="64223-141">Response</span></span>
<span data-ttu-id="64223-142">Wenn erfolgreich und Warnung und ein Benutzer vorhanden ist - 200 OK mit Benutzer im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="64223-142">If successful and alert and a user exists - 200 OK with user in the body.</span></span> <span data-ttu-id="64223-143">Wenn Warnung oder Benutzer nicht gefunden werden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="64223-143">If alert or user not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="64223-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64223-144">Example</span></span>

<span data-ttu-id="64223-145">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="64223-145">**Request**</span></span>

<span data-ttu-id="64223-146">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="64223-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/user
```

<span data-ttu-id="64223-147">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="64223-147">**Response**</span></span>

<span data-ttu-id="64223-148">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="64223-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "contoso\\user1",
    "accountName": "user1",
    "accountDomain": "contoso",
    "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
    "firstSeen": "2019-12-08T06:33:39Z",
    "lastSeen": "2020-01-05T06:58:34Z",
    "mostPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "leastPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "logonTypes": "Network",
    "logOnMachinesCount": 1,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": false
}
```

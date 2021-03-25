---
title: Abrufen der Benutzerinformations-API
description: Erfahren Sie, wie Sie die Benutzerinformations-API abrufen verwenden, um eine Benutzerentität nach Schlüssel oder Benutzername in Microsoft Defender for Endpoint abzurufen.
keywords: apis, graph api, supported apis, get, user, user information
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
ms.openlocfilehash: 1c5b8fa6e0f1fd887c857bd4e6451a5e59b708af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198541"
---
# <a name="get-user-information-api"></a><span data-ttu-id="0e104-104">Abrufen der Benutzerinformations-API</span><span class="sxs-lookup"><span data-stu-id="0e104-104">Get user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0e104-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0e104-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="0e104-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0e104-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0e104-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0e104-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> <span data-ttu-id="0e104-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0e104-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0e104-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0e104-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)
<span data-ttu-id="0e104-110">Abrufen einer User-Entität nach Schlüssel (Benutzername).</span><span class="sxs-lookup"><span data-stu-id="0e104-110">Retrieve a User entity by key (user name).</span></span>

## <a name="permissions"></a><span data-ttu-id="0e104-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0e104-111">Permissions</span></span>
<span data-ttu-id="0e104-112">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0e104-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0e104-113">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0e104-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="0e104-114">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="0e104-114">Permission type</span></span> |   <span data-ttu-id="0e104-115">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0e104-115">Permission</span></span>  |   <span data-ttu-id="0e104-116">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="0e104-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0e104-117">Application</span><span class="sxs-lookup"><span data-stu-id="0e104-117">Application</span></span> |   <span data-ttu-id="0e104-118">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="0e104-118">User.Read.All</span></span> | <span data-ttu-id="0e104-119">"Alle Benutzerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="0e104-119">'Read all user profiles'</span></span>

## <a name="http-request"></a><span data-ttu-id="0e104-120">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="0e104-120">HTTP request</span></span>
```
GET /api/users/{id}/
```

## <a name="request-headers"></a><span data-ttu-id="0e104-121">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="0e104-121">Request headers</span></span>

<span data-ttu-id="0e104-122">Name</span><span class="sxs-lookup"><span data-stu-id="0e104-122">Name</span></span> | <span data-ttu-id="0e104-123">Typ</span><span class="sxs-lookup"><span data-stu-id="0e104-123">Type</span></span> | <span data-ttu-id="0e104-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e104-124">Description</span></span>
:---|:---|:---
<span data-ttu-id="0e104-125">Authorization</span><span class="sxs-lookup"><span data-stu-id="0e104-125">Authorization</span></span> | <span data-ttu-id="0e104-126">String</span><span class="sxs-lookup"><span data-stu-id="0e104-126">String</span></span> | <span data-ttu-id="0e104-127">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="0e104-127">Bearer {token}.</span></span> <span data-ttu-id="0e104-128">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0e104-128">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0e104-129">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="0e104-129">Request body</span></span>
<span data-ttu-id="0e104-130">Empty</span><span class="sxs-lookup"><span data-stu-id="0e104-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0e104-131">Antwort</span><span class="sxs-lookup"><span data-stu-id="0e104-131">Response</span></span>
<span data-ttu-id="0e104-132">Wenn erfolgreich und Benutzer vorhanden ist – 200 OK mit [benutzerentität](user.md) im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="0e104-132">If successful and user exists - 200 OK with [user](user.md) entity in the body.</span></span> <span data-ttu-id="0e104-133">Wenn der Benutzer nicht vorhanden ist - 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="0e104-133">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="0e104-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e104-134">Example</span></span>

<span data-ttu-id="0e104-135">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="0e104-135">**Request**</span></span>

<span data-ttu-id="0e104-136">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="0e104-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/users/user1
Content-type: application/json
```

<span data-ttu-id="0e104-137">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="0e104-137">**Response**</span></span>

<span data-ttu-id="0e104-138">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="0e104-138">Here is an example of the response.</span></span>


```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "user1",
    "firstSeen": "2018-08-02T00:00:00Z",
    "lastSeen": "2018-08-04T00:00:00Z",
    "mostPrevalentMachineId": null,
    "leastPrevalentMachineId": null,
    "logonTypes": "Network",
    "logOnMachinesCount": 3,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": null
}
```

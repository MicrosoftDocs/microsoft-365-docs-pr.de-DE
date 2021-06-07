---
title: Erhalten von Informationen zu Benachrichtigungen zu IPs
description: Rufen Sie alle IPs im Zusammenhang mit einer bestimmten Warnung mit Microsoft Defender für Endpunkt ab.
keywords: APIs, Graph-API, unterstützte APIs, Warnungsinformationen abrufen, Warnungsinformationen, zugehörige IP
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
ms.openlocfilehash: b6ac9746ff82f81772505daac7d7f36249687d7d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772329"
---
# <a name="get-alert-related-ips-information-api"></a><span data-ttu-id="09c17-104">Abrufen der IPs-Informations-API für Warnungen</span><span class="sxs-lookup"><span data-stu-id="09c17-104">Get alert related IPs information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="09c17-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="09c17-105">**Applies to:**</span></span>
- [<span data-ttu-id="09c17-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="09c17-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="09c17-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09c17-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="09c17-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="09c17-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="09c17-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="09c17-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="09c17-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09c17-110">API description</span></span>
<span data-ttu-id="09c17-111">Ruft alle IPs im Zusammenhang mit einer bestimmten Warnung ab.</span><span class="sxs-lookup"><span data-stu-id="09c17-111">Retrieves all IPs related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="09c17-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="09c17-112">Limitations</span></span>
1. <span data-ttu-id="09c17-113">Sie können nach Warnungen abfragen, die zuletzt gemäß Ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="09c17-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="09c17-114">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="09c17-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="09c17-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="09c17-115">Permissions</span></span>
<span data-ttu-id="09c17-116">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="09c17-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="09c17-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="09c17-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="09c17-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="09c17-118">Permission type</span></span> |   <span data-ttu-id="09c17-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="09c17-119">Permission</span></span>  |   <span data-ttu-id="09c17-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="09c17-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="09c17-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="09c17-121">Application</span></span> |   <span data-ttu-id="09c17-122">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="09c17-122">Ip.Read.All</span></span> |   <span data-ttu-id="09c17-123">"Ip-Adressprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="09c17-123">'Read IP address profiles'</span></span>
<span data-ttu-id="09c17-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="09c17-124">Delegated (work or school account)</span></span> | <span data-ttu-id="09c17-125">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="09c17-125">Ip.Read.All</span></span> |  <span data-ttu-id="09c17-126">"Ip-Adressprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="09c17-126">'Read IP address profiles'</span></span>

>[!Note]
> <span data-ttu-id="09c17-127">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="09c17-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="09c17-128">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="09c17-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="09c17-129">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben, das der Warnung zugeordnet ist (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="09c17-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="09c17-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="09c17-130">HTTP request</span></span>
```
GET /api/alerts/{id}/ips
```

## <a name="request-headers"></a><span data-ttu-id="09c17-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="09c17-131">Request headers</span></span>

<span data-ttu-id="09c17-132">Name</span><span class="sxs-lookup"><span data-stu-id="09c17-132">Name</span></span> | <span data-ttu-id="09c17-133">Typ</span><span class="sxs-lookup"><span data-stu-id="09c17-133">Type</span></span> | <span data-ttu-id="09c17-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09c17-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="09c17-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="09c17-135">Authorization</span></span> | <span data-ttu-id="09c17-136">String</span><span class="sxs-lookup"><span data-stu-id="09c17-136">String</span></span> | <span data-ttu-id="09c17-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="09c17-137">Bearer {token}.</span></span> <span data-ttu-id="09c17-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="09c17-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="09c17-139">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="09c17-139">Request body</span></span>
<span data-ttu-id="09c17-140">Empty</span><span class="sxs-lookup"><span data-stu-id="09c17-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="09c17-141">Antwort</span><span class="sxs-lookup"><span data-stu-id="09c17-141">Response</span></span>
<span data-ttu-id="09c17-142">Wenn erfolgreich und Warnung und eine IP vorhanden – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="09c17-142">If successful and alert and an IP exist - 200 OK.</span></span> <span data-ttu-id="09c17-143">Wenn Warnung nicht gefunden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="09c17-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="09c17-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="09c17-144">Example</span></span>

<span data-ttu-id="09c17-145">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="09c17-145">**Request**</span></span>

<span data-ttu-id="09c17-146">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="09c17-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/ips
```

<span data-ttu-id="09c17-147">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="09c17-147">**Response**</span></span>

<span data-ttu-id="09c17-148">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="09c17-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Ips",    
    "value": [
                {
                    "id": "104.80.104.128"
                },
                {
                    "id": "23.203.232.228   
                }
                ...
    ]
}
 
```

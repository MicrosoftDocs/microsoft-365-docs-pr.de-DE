---
title: Informationen zu Benachrichtigungs-IPs
description: Rufen Sie alle IPs im Zusammenhang mit einer bestimmten Warnung mithilfe von Microsoft Defender for Endpoint ab.
keywords: apis, graph api, supported apis, get alert information, alert information, related ip
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
ms.openlocfilehash: 970f82038bd7feb4f0c568ed13b285f75bf1ab19
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166668"
---
# <a name="get-alert-related-ips-information-api"></a><span data-ttu-id="41047-104">Abrufen der Benachrichtigungs-IPs-Informations-API</span><span class="sxs-lookup"><span data-stu-id="41047-104">Get alert related IPs information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="41047-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="41047-105">**Applies to:**</span></span>
- [<span data-ttu-id="41047-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="41047-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="41047-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41047-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="41047-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="41047-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="41047-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="41047-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="41047-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41047-110">API description</span></span>
<span data-ttu-id="41047-111">Ruft alle IPs im Zusammenhang mit einer bestimmten Warnung ab.</span><span class="sxs-lookup"><span data-stu-id="41047-111">Retrieves all IPs related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="41047-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="41047-112">Limitations</span></span>
1. <span data-ttu-id="41047-113">Sie können Warnungen abfragen, die zuletzt entsprechend ihrem konfigurierten Aufbewahrungszeitraum aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="41047-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="41047-114">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="41047-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="41047-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="41047-115">Permissions</span></span>
<span data-ttu-id="41047-116">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="41047-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="41047-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="41047-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="41047-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="41047-118">Permission type</span></span> |   <span data-ttu-id="41047-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="41047-119">Permission</span></span>  |   <span data-ttu-id="41047-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="41047-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="41047-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="41047-121">Application</span></span> |   <span data-ttu-id="41047-122">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="41047-122">Ip.Read.All</span></span> |   <span data-ttu-id="41047-123">"Lesen von IP-Adressprofilen"</span><span class="sxs-lookup"><span data-stu-id="41047-123">'Read IP address profiles'</span></span>
<span data-ttu-id="41047-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="41047-124">Delegated (work or school account)</span></span> | <span data-ttu-id="41047-125">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="41047-125">Ip.Read.All</span></span> |  <span data-ttu-id="41047-126">"Lesen von IP-Adressprofilen"</span><span class="sxs-lookup"><span data-stu-id="41047-126">'Read IP address profiles'</span></span>

>[!Note]
> <span data-ttu-id="41047-127">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="41047-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="41047-128">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="41047-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="41047-129">Der Benutzer muss auf das Gerät zugreifen können, das der Warnung zugeordnet ist, basierend auf den Gerätegruppeneinstellungen (Weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen)</span><span class="sxs-lookup"><span data-stu-id="41047-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="41047-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="41047-130">HTTP request</span></span>
```
GET /api/alerts/{id}/ips
```

## <a name="request-headers"></a><span data-ttu-id="41047-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="41047-131">Request headers</span></span>

<span data-ttu-id="41047-132">Name</span><span class="sxs-lookup"><span data-stu-id="41047-132">Name</span></span> | <span data-ttu-id="41047-133">Typ</span><span class="sxs-lookup"><span data-stu-id="41047-133">Type</span></span> | <span data-ttu-id="41047-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41047-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="41047-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="41047-135">Authorization</span></span> | <span data-ttu-id="41047-136">String</span><span class="sxs-lookup"><span data-stu-id="41047-136">String</span></span> | <span data-ttu-id="41047-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="41047-137">Bearer {token}.</span></span> <span data-ttu-id="41047-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="41047-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="41047-139">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="41047-139">Request body</span></span>
<span data-ttu-id="41047-140">Empty</span><span class="sxs-lookup"><span data-stu-id="41047-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="41047-141">Antwort</span><span class="sxs-lookup"><span data-stu-id="41047-141">Response</span></span>
<span data-ttu-id="41047-142">Wenn erfolgreich und Warnung und eine IP vorhanden sind - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="41047-142">If successful and alert and an IP exist - 200 OK.</span></span> <span data-ttu-id="41047-143">Wenn die Warnung nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="41047-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="41047-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41047-144">Example</span></span>

<span data-ttu-id="41047-145">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="41047-145">**Request**</span></span>

<span data-ttu-id="41047-146">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="41047-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/ips
```

<span data-ttu-id="41047-147">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="41047-147">**Response**</span></span>

<span data-ttu-id="41047-148">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="41047-148">Here is an example of the response.</span></span>


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

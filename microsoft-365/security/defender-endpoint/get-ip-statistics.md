---
title: Abrufen der IP-Statistik-API
description: Mit Microsoft Defender for Endpoint erhalten Sie die neuesten Statistiken für Ihre IP.
keywords: apis, graph api, supported apis, get, ip, statistics, prevalence
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
ms.openlocfilehash: c47a5e58b1888447a4428fad78e71b85cfe79b69
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166729"
---
# <a name="get-ip-statistics-api"></a><span data-ttu-id="97171-104">Abrufen der IP-Statistik-API</span><span class="sxs-lookup"><span data-stu-id="97171-104">Get IP statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="97171-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="97171-105">**Applies to:**</span></span>
- [<span data-ttu-id="97171-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="97171-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="97171-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97171-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="97171-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="97171-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="97171-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="97171-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="97171-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97171-110">API description</span></span>
<span data-ttu-id="97171-111">Ruft die Statistiken für die angegebene IP ab.</span><span class="sxs-lookup"><span data-stu-id="97171-111">Retrieves the statistics for the given IP.</span></span>

## <a name="limitations"></a><span data-ttu-id="97171-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="97171-112">Limitations</span></span>
1. <span data-ttu-id="97171-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="97171-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="97171-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="97171-114">Permissions</span></span>
<span data-ttu-id="97171-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="97171-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="97171-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="97171-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="97171-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="97171-117">Permission type</span></span> |   <span data-ttu-id="97171-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="97171-118">Permission</span></span>  |   <span data-ttu-id="97171-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="97171-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="97171-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="97171-120">Application</span></span> |   <span data-ttu-id="97171-121">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="97171-121">Ip.Read.All</span></span> |   <span data-ttu-id="97171-122">"Lesen von IP-Adressprofilen"</span><span class="sxs-lookup"><span data-stu-id="97171-122">'Read IP address profiles'</span></span>
<span data-ttu-id="97171-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="97171-123">Delegated (work or school account)</span></span> | <span data-ttu-id="97171-124">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="97171-124">Ip.Read.All</span></span> |  <span data-ttu-id="97171-125">"Lesen von IP-Adressprofilen"</span><span class="sxs-lookup"><span data-stu-id="97171-125">'Read IP address profiles'</span></span>

>[!NOTE]
> <span data-ttu-id="97171-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="97171-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="97171-127">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="97171-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="97171-128">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="97171-128">HTTP request</span></span>

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a><span data-ttu-id="97171-129">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="97171-129">Request headers</span></span>

<span data-ttu-id="97171-130">Name</span><span class="sxs-lookup"><span data-stu-id="97171-130">Name</span></span> | <span data-ttu-id="97171-131">Typ</span><span class="sxs-lookup"><span data-stu-id="97171-131">Type</span></span> | <span data-ttu-id="97171-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97171-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="97171-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="97171-133">Authorization</span></span> | <span data-ttu-id="97171-134">String</span><span class="sxs-lookup"><span data-stu-id="97171-134">String</span></span> | <span data-ttu-id="97171-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="97171-135">Bearer {token}.</span></span> <span data-ttu-id="97171-136">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="97171-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="97171-137">Anforderungs-URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="97171-137">Request URI parameters</span></span>

<span data-ttu-id="97171-138">Name</span><span class="sxs-lookup"><span data-stu-id="97171-138">Name</span></span> | <span data-ttu-id="97171-139">Typ</span><span class="sxs-lookup"><span data-stu-id="97171-139">Type</span></span> | <span data-ttu-id="97171-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97171-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="97171-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="97171-141">lookBackHours</span></span> | <span data-ttu-id="97171-142">Int32</span><span class="sxs-lookup"><span data-stu-id="97171-142">Int32</span></span> | <span data-ttu-id="97171-143">Definiert die Stunden, die wir zurücksuchen, um die Statistiken zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="97171-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="97171-144">Standardmäßig 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="97171-144">Defaults to 30 days.</span></span> <span data-ttu-id="97171-145">**Optional**.</span><span class="sxs-lookup"><span data-stu-id="97171-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="97171-146">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="97171-146">Request body</span></span>
<span data-ttu-id="97171-147">Empty</span><span class="sxs-lookup"><span data-stu-id="97171-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="97171-148">Antwort</span><span class="sxs-lookup"><span data-stu-id="97171-148">Response</span></span>
<span data-ttu-id="97171-149">Wenn erfolgreich und ip vorhanden ist – 200 OK mit statistischen Daten im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="97171-149">If successful and ip exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="97171-150">IP nicht vorhanden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="97171-150">IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="97171-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97171-151">Example</span></span>

<span data-ttu-id="97171-152">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="97171-152">**Request**</span></span>

<span data-ttu-id="97171-153">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="97171-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

<span data-ttu-id="97171-154">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="97171-154">**Response**</span></span>

<span data-ttu-id="97171-155">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="97171-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "orgPrevalence": "63515",
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| <span data-ttu-id="97171-156">Name</span><span class="sxs-lookup"><span data-stu-id="97171-156">Name</span></span> | <span data-ttu-id="97171-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97171-157">Description</span></span> |
| :--- | :---------- |
| <span data-ttu-id="97171-158">Organisationsprävalenz</span><span class="sxs-lookup"><span data-stu-id="97171-158">Org prevalence</span></span> | <span data-ttu-id="97171-159">die unterschiedliche Anzahl von Geräten, die die Netzwerkverbindung zu dieser IP geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="97171-159">the distinct count of devices that opened network connection to this IP.</span></span> |
| <span data-ttu-id="97171-160">Org first seen</span><span class="sxs-lookup"><span data-stu-id="97171-160">Org first seen</span></span> | <span data-ttu-id="97171-161">die erste Verbindung für diese IP in der Organisation.</span><span class="sxs-lookup"><span data-stu-id="97171-161">the first connection for this IP in the organization.</span></span> |
| <span data-ttu-id="97171-162">Organisation zuletzt gesehen</span><span class="sxs-lookup"><span data-stu-id="97171-162">Org last seen</span></span>  | <span data-ttu-id="97171-163">die letzte Verbindung für diese IP in der Organisation.</span><span class="sxs-lookup"><span data-stu-id="97171-163">the last connection for this IP in the organization.</span></span> |

> [!NOTE]
> <span data-ttu-id="97171-164">Diese Statistikinformationen basieren auf Daten aus den letzten 30 Tagen.</span><span class="sxs-lookup"><span data-stu-id="97171-164">This statistic information is based on data from the past 30 days.</span></span> 

---
title: IP-Statistik-API abrufen
description: Rufen Sie die neuesten Statistiken für Ihre IP mit Microsoft Defender für Endpunkt ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, IP, Statistiken, Verbreitung
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
ms.openlocfilehash: 4919f082c115d8a57960ec49532b6cda6a63833f
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998728"
---
# <a name="get-ip-statistics-api"></a><span data-ttu-id="8bd8f-104">IP-Statistik-API abrufen</span><span class="sxs-lookup"><span data-stu-id="8bd8f-104">Get IP statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8bd8f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8bd8f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8bd8f-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8bd8f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8bd8f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8bd8f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8bd8f-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="8bd8f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8bd8f-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="8bd8f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="8bd8f-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8bd8f-110">API description</span></span>
<span data-ttu-id="8bd8f-111">Ruft die Statistiken für die angegebene IP ab.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-111">Retrieves the statistics for the given IP.</span></span>

## <a name="limitations"></a><span data-ttu-id="8bd8f-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8bd8f-112">Limitations</span></span>
1. <span data-ttu-id="8bd8f-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="8bd8f-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8bd8f-114">Permissions</span></span>
<span data-ttu-id="8bd8f-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8bd8f-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8bd8f-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8bd8f-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="8bd8f-117">Permission type</span></span> |   <span data-ttu-id="8bd8f-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8bd8f-118">Permission</span></span>  |   <span data-ttu-id="8bd8f-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8bd8f-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8bd8f-120">Application</span><span class="sxs-lookup"><span data-stu-id="8bd8f-120">Application</span></span> |   <span data-ttu-id="8bd8f-121">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="8bd8f-121">Ip.Read.All</span></span> |   <span data-ttu-id="8bd8f-122">"Ip-Adressprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="8bd8f-122">'Read IP address profiles'</span></span>
<span data-ttu-id="8bd8f-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="8bd8f-123">Delegated (work or school account)</span></span> | <span data-ttu-id="8bd8f-124">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="8bd8f-124">Ip.Read.All</span></span> |  <span data-ttu-id="8bd8f-125">"Ip-Adressprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="8bd8f-125">'Read IP address profiles'</span></span>

>[!NOTE]
> <span data-ttu-id="8bd8f-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="8bd8f-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="8bd8f-127">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="8bd8f-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="8bd8f-128">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="8bd8f-128">HTTP request</span></span>

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a><span data-ttu-id="8bd8f-129">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="8bd8f-129">Request headers</span></span>

<span data-ttu-id="8bd8f-130">Name</span><span class="sxs-lookup"><span data-stu-id="8bd8f-130">Name</span></span> | <span data-ttu-id="8bd8f-131">Typ</span><span class="sxs-lookup"><span data-stu-id="8bd8f-131">Type</span></span> | <span data-ttu-id="8bd8f-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8bd8f-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="8bd8f-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="8bd8f-133">Authorization</span></span> | <span data-ttu-id="8bd8f-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8bd8f-134">String</span></span> | <span data-ttu-id="8bd8f-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-135">Bearer {token}.</span></span> <span data-ttu-id="8bd8f-136">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="8bd8f-137">Anforderungs-URI-Parameter</span><span class="sxs-lookup"><span data-stu-id="8bd8f-137">Request URI parameters</span></span>

<span data-ttu-id="8bd8f-138">Name</span><span class="sxs-lookup"><span data-stu-id="8bd8f-138">Name</span></span> | <span data-ttu-id="8bd8f-139">Typ</span><span class="sxs-lookup"><span data-stu-id="8bd8f-139">Type</span></span> | <span data-ttu-id="8bd8f-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8bd8f-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="8bd8f-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="8bd8f-141">lookBackHours</span></span> | <span data-ttu-id="8bd8f-142">Int32</span><span class="sxs-lookup"><span data-stu-id="8bd8f-142">Int32</span></span> | <span data-ttu-id="8bd8f-143">Definiert die Stunden, die wir zurücksuchen, um die Statistiken abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="8bd8f-144">Der Standardwert ist 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-144">Defaults to 30 days.</span></span> <span data-ttu-id="8bd8f-145">**Optional**.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8bd8f-146">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="8bd8f-146">Request body</span></span>
<span data-ttu-id="8bd8f-147">Empty</span><span class="sxs-lookup"><span data-stu-id="8bd8f-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8bd8f-148">Antwort</span><span class="sxs-lookup"><span data-stu-id="8bd8f-148">Response</span></span>
<span data-ttu-id="8bd8f-149">Wenn erfolgreich und ip vorhanden – 200 OK mit statistischen Daten im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-149">If successful and ip exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="8bd8f-150">IP nicht vorhanden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-150">IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="8bd8f-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8bd8f-151">Example</span></span>

<span data-ttu-id="8bd8f-152">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="8bd8f-152">**Request**</span></span>

<span data-ttu-id="8bd8f-153">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

<span data-ttu-id="8bd8f-154">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="8bd8f-154">**Response**</span></span>

<span data-ttu-id="8bd8f-155">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| <span data-ttu-id="8bd8f-156">Name</span><span class="sxs-lookup"><span data-stu-id="8bd8f-156">Name</span></span> | <span data-ttu-id="8bd8f-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8bd8f-157">Description</span></span> |
| :--- | :---------- |
| <span data-ttu-id="8bd8f-158">Verbreitung der Organisation</span><span class="sxs-lookup"><span data-stu-id="8bd8f-158">Organization prevalence</span></span> | <span data-ttu-id="8bd8f-159">die unterschiedliche Anzahl von Geräten, die eine Netzwerkverbindung mit dieser IP-Adresse hergestellt haben.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-159">the distinct count of devices that opened network connection to this IP.</span></span> |
| <span data-ttu-id="8bd8f-160">Organisation zuerst gesehen</span><span class="sxs-lookup"><span data-stu-id="8bd8f-160">Org first seen</span></span> | <span data-ttu-id="8bd8f-161">die erste Verbindung für diese IP in der Organisation.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-161">the first connection for this IP in the organization.</span></span> |
| <span data-ttu-id="8bd8f-162">Organisation zuletzt gesehen</span><span class="sxs-lookup"><span data-stu-id="8bd8f-162">Org last seen</span></span>  | <span data-ttu-id="8bd8f-163">die letzte Verbindung für diese IP in der Organisation.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-163">the last connection for this IP in the organization.</span></span> |

> [!NOTE]
> <span data-ttu-id="8bd8f-164">Diese statistischen Informationen basieren auf Daten aus den letzten 30 Tagen.</span><span class="sxs-lookup"><span data-stu-id="8bd8f-164">This statistic information is based on data from the past 30 days.</span></span> 

---
title: Abrufen der IP-bezogenen Benachrichtigungs-API
description: Abrufen einer Sammlung von Warnungen im Zusammenhang mit einer bestimmten IP-Adresse mithilfe von Microsoft Defender for Endpoint
keywords: apis, graph api, supported apis, get, ip, related, alerts
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
ms.openlocfilehash: dbcde70b32f9a10280dd43e98c5a237a0027a33c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166734"
---
# <a name="get-ip-related-alerts-api"></a><span data-ttu-id="9f53b-104">Abrufen der IP-bezogenen Benachrichtigungs-API</span><span class="sxs-lookup"><span data-stu-id="9f53b-104">Get IP related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9f53b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9f53b-105">**Applies to:**</span></span>
- [<span data-ttu-id="9f53b-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9f53b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9f53b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9f53b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9f53b-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9f53b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9f53b-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9f53b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="9f53b-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f53b-110">API description</span></span>
<span data-ttu-id="9f53b-111">Ruft eine Auflistung von Warnungen im Zusammenhang mit einer bestimmten IP-Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="9f53b-111">Retrieves a collection of alerts related to a given IP address.</span></span>


## <a name="limitations"></a><span data-ttu-id="9f53b-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="9f53b-112">Limitations</span></span>
1. <span data-ttu-id="9f53b-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="9f53b-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="9f53b-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9f53b-114">Permissions</span></span>
<span data-ttu-id="9f53b-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9f53b-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9f53b-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9f53b-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9f53b-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="9f53b-117">Permission type</span></span> |   <span data-ttu-id="9f53b-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="9f53b-118">Permission</span></span>  |   <span data-ttu-id="9f53b-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="9f53b-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9f53b-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="9f53b-120">Application</span></span> |   <span data-ttu-id="9f53b-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="9f53b-121">Alert.Read.All</span></span> |    <span data-ttu-id="9f53b-122">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="9f53b-122">'Read all alerts'</span></span>
<span data-ttu-id="9f53b-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="9f53b-123">Application</span></span> |   <span data-ttu-id="9f53b-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9f53b-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="9f53b-125">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="9f53b-125">'Read and write all alerts'</span></span>
<span data-ttu-id="9f53b-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="9f53b-126">Delegated (work or school account)</span></span> | <span data-ttu-id="9f53b-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="9f53b-127">Alert.Read</span></span> | <span data-ttu-id="9f53b-128">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="9f53b-128">'Read alerts'</span></span>
<span data-ttu-id="9f53b-129">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="9f53b-129">Delegated (work or school account)</span></span> | <span data-ttu-id="9f53b-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9f53b-130">Alert.ReadWrite</span></span> | <span data-ttu-id="9f53b-131">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="9f53b-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="9f53b-132">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="9f53b-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9f53b-133">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="9f53b-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="9f53b-134">Die Antwort umfasst nur Warnungen, die Geräten zugeordnet sind und auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="9f53b-134">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9f53b-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="9f53b-135">HTTP request</span></span>
```
GET /api/ips/{ip}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="9f53b-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="9f53b-136">Request headers</span></span>

<span data-ttu-id="9f53b-137">Name</span><span class="sxs-lookup"><span data-stu-id="9f53b-137">Name</span></span> | <span data-ttu-id="9f53b-138">Typ</span><span class="sxs-lookup"><span data-stu-id="9f53b-138">Type</span></span> | <span data-ttu-id="9f53b-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f53b-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="9f53b-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="9f53b-140">Authorization</span></span> | <span data-ttu-id="9f53b-141">String</span><span class="sxs-lookup"><span data-stu-id="9f53b-141">String</span></span> | <span data-ttu-id="9f53b-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="9f53b-142">Bearer {token}.</span></span> <span data-ttu-id="9f53b-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="9f53b-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9f53b-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="9f53b-144">Request body</span></span>
<span data-ttu-id="9f53b-145">Empty</span><span class="sxs-lookup"><span data-stu-id="9f53b-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9f53b-146">Antwort</span><span class="sxs-lookup"><span data-stu-id="9f53b-146">Response</span></span>
<span data-ttu-id="9f53b-147">Wenn erfolgreich und IP vorhanden ist – 200 OK mit Liste [der](alerts.md) Benachrichtigungsentitäten im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="9f53b-147">If successful and IP exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="9f53b-148">Wenn IP nicht vorhanden ist – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="9f53b-148">If IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="9f53b-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f53b-149">Example</span></span>

<span data-ttu-id="9f53b-150">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="9f53b-150">**Request**</span></span>

<span data-ttu-id="9f53b-151">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="9f53b-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/alerts
```

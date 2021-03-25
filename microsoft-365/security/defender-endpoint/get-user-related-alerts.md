---
title: Abrufen der benutzerbezogenen Benachrichtigungs-API
description: Rufen Sie mithilfe von Microsoft Defender for Endpoint eine Sammlung von Warnungen im Zusammenhang mit einer bestimmten Benutzer-ID ab.
keywords: apis, graph api, supported apis, get, user, related, alerts
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
ms.openlocfilehash: cff4530cfa4ecd6b0d918a9112e7be3c0f30209c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166523"
---
# <a name="get-user-related-alerts-api"></a><span data-ttu-id="39b4b-104">Abrufen der benutzerbezogenen Benachrichtigungs-API</span><span class="sxs-lookup"><span data-stu-id="39b4b-104">Get user-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="39b4b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="39b4b-105">**Applies to:**</span></span>
- [<span data-ttu-id="39b4b-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="39b4b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="39b4b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39b4b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="39b4b-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="39b4b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="39b4b-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="39b4b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="39b4b-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39b4b-110">API description</span></span>
<span data-ttu-id="39b4b-111">Ruft eine Auflistung von Warnungen im Zusammenhang mit einer bestimmten Benutzer-ID ab.</span><span class="sxs-lookup"><span data-stu-id="39b4b-111">Retrieves a collection of alerts related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="39b4b-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="39b4b-112">Limitations</span></span>
1. <span data-ttu-id="39b4b-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="39b4b-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="39b4b-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="39b4b-114">Permissions</span></span>
<span data-ttu-id="39b4b-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="39b4b-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="39b4b-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="39b4b-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="39b4b-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="39b4b-117">Permission type</span></span> |   <span data-ttu-id="39b4b-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="39b4b-118">Permission</span></span>  |   <span data-ttu-id="39b4b-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="39b4b-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="39b4b-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="39b4b-120">Application</span></span> |   <span data-ttu-id="39b4b-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="39b4b-121">Alert.Read.All</span></span> |    <span data-ttu-id="39b4b-122">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="39b4b-122">'Read all alerts'</span></span>
<span data-ttu-id="39b4b-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="39b4b-123">Application</span></span> |   <span data-ttu-id="39b4b-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="39b4b-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="39b4b-125">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="39b4b-125">'Read and write all alerts'</span></span>
<span data-ttu-id="39b4b-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="39b4b-126">Delegated (work or school account)</span></span> | <span data-ttu-id="39b4b-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="39b4b-127">Alert.Read</span></span> | <span data-ttu-id="39b4b-128">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="39b4b-128">'Read alerts'</span></span>
<span data-ttu-id="39b4b-129">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="39b4b-129">Delegated (work or school account)</span></span> | <span data-ttu-id="39b4b-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="39b4b-130">Alert.ReadWrite</span></span> | <span data-ttu-id="39b4b-131">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="39b4b-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="39b4b-132">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="39b4b-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="39b4b-133">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen".</span><span class="sxs-lookup"><span data-stu-id="39b4b-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="39b4b-134">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="39b4b-134">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="39b4b-135">Die Antwort umfasst nur Warnungen, die Geräten zugeordnet sind und auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="39b4b-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="39b4b-136">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="39b4b-136">HTTP request</span></span>
```
GET /api/users/{id}/alerts
```

<span data-ttu-id="39b4b-137">**Die ID ist nicht der vollständige UPN, sondern nur der Benutzername. (Zum Abrufen von Warnungen für user1@contoso.com /api/users/user1/alerts)**</span><span class="sxs-lookup"><span data-stu-id="39b4b-137">**The ID is not the full UPN, but only the user name. (for example, to retrieve alerts for user1@contoso.com use /api/users/user1/alerts)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="39b4b-138">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="39b4b-138">Request headers</span></span>

<span data-ttu-id="39b4b-139">Name</span><span class="sxs-lookup"><span data-stu-id="39b4b-139">Name</span></span> | <span data-ttu-id="39b4b-140">Typ</span><span class="sxs-lookup"><span data-stu-id="39b4b-140">Type</span></span> | <span data-ttu-id="39b4b-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39b4b-141">Description</span></span>
:---|:---|:---
<span data-ttu-id="39b4b-142">Authorization</span><span class="sxs-lookup"><span data-stu-id="39b4b-142">Authorization</span></span> | <span data-ttu-id="39b4b-143">String</span><span class="sxs-lookup"><span data-stu-id="39b4b-143">String</span></span> | <span data-ttu-id="39b4b-144">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="39b4b-144">Bearer {token}.</span></span> <span data-ttu-id="39b4b-145">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="39b4b-145">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="39b4b-146">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="39b4b-146">Request body</span></span>
<span data-ttu-id="39b4b-147">Empty</span><span class="sxs-lookup"><span data-stu-id="39b4b-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="39b4b-148">Antwort</span><span class="sxs-lookup"><span data-stu-id="39b4b-148">Response</span></span>
<span data-ttu-id="39b4b-149">Wenn erfolgreich und Benutzer vorhanden ist – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="39b4b-149">If successful and user exists - 200 OK.</span></span> <span data-ttu-id="39b4b-150">Wenn der Benutzer nicht vorhanden ist - 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="39b4b-150">If the user does not exist - 404 Not Found.</span></span> 


## <a name="example"></a><span data-ttu-id="39b4b-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39b4b-151">Example</span></span>

<span data-ttu-id="39b4b-152">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="39b4b-152">**Request**</span></span>

<span data-ttu-id="39b4b-153">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="39b4b-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```

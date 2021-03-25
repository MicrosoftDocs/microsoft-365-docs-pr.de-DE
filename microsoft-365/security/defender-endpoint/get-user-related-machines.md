---
title: Abrufen der benutzerbezogenen Computer-API
description: Erfahren Sie, wie Sie die API Benutzerbezogene Computer abrufen verwenden, um eine Sammlung von Geräten im Zusammenhang mit einer Benutzer-ID in Microsoft Defender for Endpoint abzurufen.
keywords: apis, graph api, supported apis, get, user, user related alerts
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
ms.openlocfilehash: 135dc1d76a1a90cd7fffba0638211d716865cb0c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166531"
---
# <a name="get-user-related-machines-api"></a><span data-ttu-id="93a75-104">Abrufen der benutzerbezogenen Computer-API</span><span class="sxs-lookup"><span data-stu-id="93a75-104">Get user-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="93a75-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="93a75-105">**Applies to:**</span></span>
- [<span data-ttu-id="93a75-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="93a75-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="93a75-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93a75-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="93a75-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="93a75-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="93a75-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="93a75-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="93a75-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93a75-110">API description</span></span>
<span data-ttu-id="93a75-111">Ruft eine Sammlung von Geräten ab, die mit einer bestimmten Benutzer-ID verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="93a75-111">Retrieves a collection of devices related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="93a75-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="93a75-112">Limitations</span></span>
1. <span data-ttu-id="93a75-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="93a75-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="93a75-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="93a75-114">Permissions</span></span>
<span data-ttu-id="93a75-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="93a75-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="93a75-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="93a75-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="93a75-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="93a75-117">Permission type</span></span> |   <span data-ttu-id="93a75-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="93a75-118">Permission</span></span>  |   <span data-ttu-id="93a75-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="93a75-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="93a75-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="93a75-120">Application</span></span> |   <span data-ttu-id="93a75-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="93a75-121">Machine.Read.All</span></span> |  <span data-ttu-id="93a75-122">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="93a75-122">'Read all machine profiles'</span></span>
<span data-ttu-id="93a75-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="93a75-123">Application</span></span> |   <span data-ttu-id="93a75-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="93a75-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="93a75-125">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="93a75-125">'Read and write all machine information'</span></span>
<span data-ttu-id="93a75-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="93a75-126">Delegated (work or school account)</span></span> | <span data-ttu-id="93a75-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="93a75-127">Machine.Read</span></span> | <span data-ttu-id="93a75-128">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="93a75-128">'Read machine information'</span></span>
<span data-ttu-id="93a75-129">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="93a75-129">Delegated (work or school account)</span></span> | <span data-ttu-id="93a75-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="93a75-130">Machine.ReadWrite</span></span> | <span data-ttu-id="93a75-131">"Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="93a75-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="93a75-132">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="93a75-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="93a75-133">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen".</span><span class="sxs-lookup"><span data-stu-id="93a75-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="93a75-134">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen](user-roles.md) )</span><span class="sxs-lookup"><span data-stu-id="93a75-134">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="93a75-135">Die Antwort umfasst nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="93a75-135">Response will include only devices that the user can access, based on device group settings.</span></span> <span data-ttu-id="93a75-136">Weitere Informationen finden Sie unter [Create and manage device groups](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="93a75-136">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="93a75-137">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="93a75-137">HTTP request</span></span>
```
GET /api/users/{id}/machines
```

<span data-ttu-id="93a75-138">**Die ID ist nicht der vollständige UPN, sondern nur der Benutzername. (z. B. zum Abrufen von Computern für user1@contoso.com /api/users/user1/machines)**</span><span class="sxs-lookup"><span data-stu-id="93a75-138">**The ID is not the full UPN, but only the user name. (for example, to retrieve machines for user1@contoso.com use /api/users/user1/machines)**</span></span>


## <a name="request-headers"></a><span data-ttu-id="93a75-139">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="93a75-139">Request headers</span></span>

<span data-ttu-id="93a75-140">Name</span><span class="sxs-lookup"><span data-stu-id="93a75-140">Name</span></span> | <span data-ttu-id="93a75-141">Typ</span><span class="sxs-lookup"><span data-stu-id="93a75-141">Type</span></span> | <span data-ttu-id="93a75-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93a75-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="93a75-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="93a75-143">Authorization</span></span> | <span data-ttu-id="93a75-144">String</span><span class="sxs-lookup"><span data-stu-id="93a75-144">String</span></span> | <span data-ttu-id="93a75-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="93a75-145">Bearer {token}.</span></span> <span data-ttu-id="93a75-146">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="93a75-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="93a75-147">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="93a75-147">Request body</span></span>
<span data-ttu-id="93a75-148">Empty</span><span class="sxs-lookup"><span data-stu-id="93a75-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="93a75-149">Antwort</span><span class="sxs-lookup"><span data-stu-id="93a75-149">Response</span></span>
<span data-ttu-id="93a75-150">Wenn erfolgreich und Benutzer vorhanden ist – [](machine.md) 200 OK mit der Liste der Computerentitäten im Textkörper.</span><span class="sxs-lookup"><span data-stu-id="93a75-150">If successful and user exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="93a75-151">Wenn der Benutzer nicht vorhanden ist - 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="93a75-151">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="93a75-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93a75-152">Example</span></span>

<span data-ttu-id="93a75-153">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="93a75-153">**Request**</span></span>

<span data-ttu-id="93a75-154">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="93a75-154">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```

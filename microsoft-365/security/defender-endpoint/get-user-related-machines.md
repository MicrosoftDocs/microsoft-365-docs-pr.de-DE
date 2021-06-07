---
title: Abrufen der benutzerbezogenen Computer-API
description: Erfahren Sie, wie Sie die API zum Abrufen von benutzerbezogenen Computern verwenden, um eine Sammlung von Geräten abzurufen, die sich auf eine Benutzer-ID in Microsoft Defender für Endpunkt beziehen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Benutzer, benutzerbezogene Warnungen
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
ms.openlocfilehash: 230af2311c52437e01cdb28d823236347cf34b8f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769897"
---
# <a name="get-user-related-machines-api"></a><span data-ttu-id="9d874-104">Abrufen der benutzerbezogenen Computer-API</span><span class="sxs-lookup"><span data-stu-id="9d874-104">Get user-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9d874-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9d874-105">**Applies to:**</span></span>
- [<span data-ttu-id="9d874-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9d874-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9d874-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d874-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9d874-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="9d874-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9d874-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9d874-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="9d874-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d874-110">API description</span></span>
<span data-ttu-id="9d874-111">Ruft eine Sammlung von Geräten im Zusammenhang mit einer bestimmten Benutzer-ID ab.</span><span class="sxs-lookup"><span data-stu-id="9d874-111">Retrieves a collection of devices related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="9d874-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="9d874-112">Limitations</span></span>
1. <span data-ttu-id="9d874-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="9d874-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="9d874-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9d874-114">Permissions</span></span>
<span data-ttu-id="9d874-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="9d874-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9d874-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9d874-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9d874-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="9d874-117">Permission type</span></span> |   <span data-ttu-id="9d874-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="9d874-118">Permission</span></span>  |   <span data-ttu-id="9d874-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="9d874-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9d874-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="9d874-120">Application</span></span> |   <span data-ttu-id="9d874-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="9d874-121">Machine.Read.All</span></span> |  <span data-ttu-id="9d874-122">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="9d874-122">'Read all machine profiles'</span></span>
<span data-ttu-id="9d874-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="9d874-123">Application</span></span> |   <span data-ttu-id="9d874-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9d874-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="9d874-125">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="9d874-125">'Read and write all machine information'</span></span>
<span data-ttu-id="9d874-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="9d874-126">Delegated (work or school account)</span></span> | <span data-ttu-id="9d874-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="9d874-127">Machine.Read</span></span> | <span data-ttu-id="9d874-128">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="9d874-128">'Read machine information'</span></span>
<span data-ttu-id="9d874-129">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="9d874-129">Delegated (work or school account)</span></span> | <span data-ttu-id="9d874-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9d874-130">Machine.ReadWrite</span></span> | <span data-ttu-id="9d874-131">"Lesen und Schreiben von Computerinformationen"</span><span class="sxs-lookup"><span data-stu-id="9d874-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="9d874-132">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="9d874-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9d874-133">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen".</span><span class="sxs-lookup"><span data-stu-id="9d874-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="9d874-134">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen](user-roles.md) )</span><span class="sxs-lookup"><span data-stu-id="9d874-134">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="9d874-135">Die Antwort enthält nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="9d874-135">Response will include only devices that the user can access, based on device group settings.</span></span> <span data-ttu-id="9d874-136">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="9d874-136">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="9d874-137">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="9d874-137">HTTP request</span></span>
```
GET /api/users/{id}/machines
```

<span data-ttu-id="9d874-138">**Die ID ist nicht der vollständige UPN, sondern nur der Benutzername. (z. B. zum Abrufen von Computern für user1@contoso.com verwenden /api/users/user1/machines)**</span><span class="sxs-lookup"><span data-stu-id="9d874-138">**The ID is not the full UPN, but only the user name. (for example, to retrieve machines for user1@contoso.com use /api/users/user1/machines)**</span></span>


## <a name="request-headers"></a><span data-ttu-id="9d874-139">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="9d874-139">Request headers</span></span>

<span data-ttu-id="9d874-140">Name</span><span class="sxs-lookup"><span data-stu-id="9d874-140">Name</span></span> | <span data-ttu-id="9d874-141">Typ</span><span class="sxs-lookup"><span data-stu-id="9d874-141">Type</span></span> | <span data-ttu-id="9d874-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d874-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="9d874-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="9d874-143">Authorization</span></span> | <span data-ttu-id="9d874-144">String</span><span class="sxs-lookup"><span data-stu-id="9d874-144">String</span></span> | <span data-ttu-id="9d874-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="9d874-145">Bearer {token}.</span></span> <span data-ttu-id="9d874-146">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="9d874-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9d874-147">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="9d874-147">Request body</span></span>
<span data-ttu-id="9d874-148">Empty</span><span class="sxs-lookup"><span data-stu-id="9d874-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9d874-149">Antwort</span><span class="sxs-lookup"><span data-stu-id="9d874-149">Response</span></span>
<span data-ttu-id="9d874-150">Wenn erfolgreich und Benutzer vorhanden – 200 OK mit Liste der Computerentitäten im Textkörper. [](machine.md)</span><span class="sxs-lookup"><span data-stu-id="9d874-150">If successful and user exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="9d874-151">Wenn der Benutzer nicht vorhanden ist – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="9d874-151">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="9d874-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d874-152">Example</span></span>

<span data-ttu-id="9d874-153">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="9d874-153">**Request**</span></span>

<span data-ttu-id="9d874-154">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="9d874-154">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```

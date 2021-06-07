---
title: API zum Abrufen von benutzerbezogenen Warnungen
description: Abrufen einer Sammlung von Warnungen im Zusammenhang mit einer bestimmten Benutzer-ID mitHilfe von Microsoft Defender für Endpunkt.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Benutzer, verwandte, Warnungen
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
ms.openlocfilehash: ab0d0e97365b5ce38b29f2b0d65e3aea48d6c28c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769929"
---
# <a name="get-user-related-alerts-api"></a><span data-ttu-id="6f3e4-104">API zum Abrufen von benutzerbezogenen Warnungen</span><span class="sxs-lookup"><span data-stu-id="6f3e4-104">Get user-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6f3e4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6f3e4-105">**Applies to:**</span></span>
- [<span data-ttu-id="6f3e4-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6f3e4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6f3e4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f3e4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6f3e4-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="6f3e4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6f3e4-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="6f3e4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="6f3e4-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f3e4-110">API description</span></span>
<span data-ttu-id="6f3e4-111">Ruft eine Sammlung von Warnungen im Zusammenhang mit einer bestimmten Benutzer-ID ab.</span><span class="sxs-lookup"><span data-stu-id="6f3e4-111">Retrieves a collection of alerts related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="6f3e4-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="6f3e4-112">Limitations</span></span>
1. <span data-ttu-id="6f3e4-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="6f3e4-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="6f3e4-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6f3e4-114">Permissions</span></span>
<span data-ttu-id="6f3e4-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="6f3e4-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6f3e4-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6f3e4-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="6f3e4-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="6f3e4-117">Permission type</span></span> |   <span data-ttu-id="6f3e4-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="6f3e4-118">Permission</span></span>  |   <span data-ttu-id="6f3e4-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="6f3e4-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6f3e4-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="6f3e4-120">Application</span></span> |   <span data-ttu-id="6f3e4-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="6f3e4-121">Alert.Read.All</span></span> |    <span data-ttu-id="6f3e4-122">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="6f3e4-122">'Read all alerts'</span></span>
<span data-ttu-id="6f3e4-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="6f3e4-123">Application</span></span> |   <span data-ttu-id="6f3e4-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="6f3e4-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="6f3e4-125">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="6f3e4-125">'Read and write all alerts'</span></span>
<span data-ttu-id="6f3e4-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="6f3e4-126">Delegated (work or school account)</span></span> | <span data-ttu-id="6f3e4-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="6f3e4-127">Alert.Read</span></span> | <span data-ttu-id="6f3e4-128">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="6f3e4-128">'Read alerts'</span></span>
<span data-ttu-id="6f3e4-129">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="6f3e4-129">Delegated (work or school account)</span></span> | <span data-ttu-id="6f3e4-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6f3e4-130">Alert.ReadWrite</span></span> | <span data-ttu-id="6f3e4-131">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="6f3e4-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="6f3e4-132">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="6f3e4-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="6f3e4-133">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen".</span><span class="sxs-lookup"><span data-stu-id="6f3e4-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="6f3e4-134">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="6f3e4-134">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="6f3e4-135">Die Antwort enthält nur Warnungen, die Geräten zugeordnet sind, auf die der Benutzer zugriff hat, basierend auf Gerätegruppeneinstellungen (weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="6f3e4-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="6f3e4-136">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="6f3e4-136">HTTP request</span></span>
```
GET /api/users/{id}/alerts
```

<span data-ttu-id="6f3e4-137">**Die ID ist nicht der vollständige UPN, sondern nur der Benutzername. (Beispielsweise zum Abrufen von Warnungen für user1@contoso.com verwenden /api/users/user1/alerts)**</span><span class="sxs-lookup"><span data-stu-id="6f3e4-137">**The ID is not the full UPN, but only the user name. (for example, to retrieve alerts for user1@contoso.com use /api/users/user1/alerts)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="6f3e4-138">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="6f3e4-138">Request headers</span></span>

<span data-ttu-id="6f3e4-139">Name</span><span class="sxs-lookup"><span data-stu-id="6f3e4-139">Name</span></span> | <span data-ttu-id="6f3e4-140">Typ</span><span class="sxs-lookup"><span data-stu-id="6f3e4-140">Type</span></span> | <span data-ttu-id="6f3e4-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f3e4-141">Description</span></span>
:---|:---|:---
<span data-ttu-id="6f3e4-142">Authorization</span><span class="sxs-lookup"><span data-stu-id="6f3e4-142">Authorization</span></span> | <span data-ttu-id="6f3e4-143">String</span><span class="sxs-lookup"><span data-stu-id="6f3e4-143">String</span></span> | <span data-ttu-id="6f3e4-144">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6f3e4-144">Bearer {token}.</span></span> <span data-ttu-id="6f3e4-145">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="6f3e4-145">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6f3e4-146">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="6f3e4-146">Request body</span></span>
<span data-ttu-id="6f3e4-147">Empty</span><span class="sxs-lookup"><span data-stu-id="6f3e4-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6f3e4-148">Antwort</span><span class="sxs-lookup"><span data-stu-id="6f3e4-148">Response</span></span>
<span data-ttu-id="6f3e4-149">Wenn erfolgreich und Benutzer vorhanden – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="6f3e4-149">If successful and user exists - 200 OK.</span></span> <span data-ttu-id="6f3e4-150">Wenn der Benutzer nicht vorhanden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="6f3e4-150">If the user does not exist - 404 Not Found.</span></span> 


## <a name="example"></a><span data-ttu-id="6f3e4-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6f3e4-151">Example</span></span>

<span data-ttu-id="6f3e4-152">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="6f3e4-152">**Request**</span></span>

<span data-ttu-id="6f3e4-153">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="6f3e4-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```

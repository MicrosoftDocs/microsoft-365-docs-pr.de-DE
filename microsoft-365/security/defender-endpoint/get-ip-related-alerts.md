---
title: API zum Abrufen von IP-bezogenen Warnungen
description: Abrufen einer Sammlung von Warnungen im Zusammenhang mit einer bestimmten IP-Adresse mithilfe von Microsoft Defender für Endpunkt
keywords: APIs, Graph-API, unterstützte APIs, abrufen, IP, im Zusammenhang, Warnungen
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
ms.openlocfilehash: a12ae502702b7fc9f69b01cd67857003258c20f2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770121"
---
# <a name="get-ip-related-alerts-api"></a><span data-ttu-id="16fc4-104">API zum Abrufen von IP-bezogenen Warnungen</span><span class="sxs-lookup"><span data-stu-id="16fc4-104">Get IP related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="16fc4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="16fc4-105">**Applies to:**</span></span>
- [<span data-ttu-id="16fc4-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="16fc4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="16fc4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16fc4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="16fc4-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="16fc4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="16fc4-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="16fc4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="16fc4-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16fc4-110">API description</span></span>
<span data-ttu-id="16fc4-111">Ruft eine Sammlung von Warnungen im Zusammenhang mit einer bestimmten IP-Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="16fc4-111">Retrieves a collection of alerts related to a given IP address.</span></span>


## <a name="limitations"></a><span data-ttu-id="16fc4-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="16fc4-112">Limitations</span></span>
1. <span data-ttu-id="16fc4-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="16fc4-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="16fc4-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="16fc4-114">Permissions</span></span>
<span data-ttu-id="16fc4-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="16fc4-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="16fc4-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="16fc4-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="16fc4-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="16fc4-117">Permission type</span></span> |   <span data-ttu-id="16fc4-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="16fc4-118">Permission</span></span>  |   <span data-ttu-id="16fc4-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="16fc4-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="16fc4-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="16fc4-120">Application</span></span> |   <span data-ttu-id="16fc4-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="16fc4-121">Alert.Read.All</span></span> |    <span data-ttu-id="16fc4-122">"Alle Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="16fc4-122">'Read all alerts'</span></span>
<span data-ttu-id="16fc4-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="16fc4-123">Application</span></span> |   <span data-ttu-id="16fc4-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="16fc4-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="16fc4-125">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="16fc4-125">'Read and write all alerts'</span></span>
<span data-ttu-id="16fc4-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="16fc4-126">Delegated (work or school account)</span></span> | <span data-ttu-id="16fc4-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="16fc4-127">Alert.Read</span></span> | <span data-ttu-id="16fc4-128">"Warnungen lesen"</span><span class="sxs-lookup"><span data-stu-id="16fc4-128">'Read alerts'</span></span>
<span data-ttu-id="16fc4-129">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="16fc4-129">Delegated (work or school account)</span></span> | <span data-ttu-id="16fc4-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="16fc4-130">Alert.ReadWrite</span></span> | <span data-ttu-id="16fc4-131">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="16fc4-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="16fc4-132">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="16fc4-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="16fc4-133">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="16fc4-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="16fc4-134">Die Antwort enthält nur Warnungen, die Geräten zugeordnet sind, auf die der Benutzer zugriff hat, basierend auf Gerätegruppeneinstellungen (weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="16fc4-134">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="16fc4-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="16fc4-135">HTTP request</span></span>
```
GET /api/ips/{ip}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="16fc4-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="16fc4-136">Request headers</span></span>

<span data-ttu-id="16fc4-137">Name</span><span class="sxs-lookup"><span data-stu-id="16fc4-137">Name</span></span> | <span data-ttu-id="16fc4-138">Typ</span><span class="sxs-lookup"><span data-stu-id="16fc4-138">Type</span></span> | <span data-ttu-id="16fc4-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16fc4-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="16fc4-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="16fc4-140">Authorization</span></span> | <span data-ttu-id="16fc4-141">String</span><span class="sxs-lookup"><span data-stu-id="16fc4-141">String</span></span> | <span data-ttu-id="16fc4-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="16fc4-142">Bearer {token}.</span></span> <span data-ttu-id="16fc4-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="16fc4-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="16fc4-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="16fc4-144">Request body</span></span>
<span data-ttu-id="16fc4-145">Empty</span><span class="sxs-lookup"><span data-stu-id="16fc4-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="16fc4-146">Antwort</span><span class="sxs-lookup"><span data-stu-id="16fc4-146">Response</span></span>
<span data-ttu-id="16fc4-147">Wenn erfolgreich und IP vorhanden – 200 OK mit Liste der Warnungsentitäten im Textkörper. [](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="16fc4-147">If successful and IP exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="16fc4-148">Wenn ip nicht vorhanden – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="16fc4-148">If IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="16fc4-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16fc4-149">Example</span></span>

<span data-ttu-id="16fc4-150">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="16fc4-150">**Request**</span></span>

<span data-ttu-id="16fc4-151">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="16fc4-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/alerts
```

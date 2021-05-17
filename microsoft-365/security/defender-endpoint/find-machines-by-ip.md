---
title: Suchen von Geräten nach interner IP-API
description: Suchen von Geräten mit der angeforderten internen IP im Zeitraum von 15 Minuten vor und nach einem bestimmten Zeitstempel
keywords: apis, graph api, supported apis, get, device, IP, find, find device, by ip, ip
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
ms.openlocfilehash: fa523a7f9b997f3a8d36dff42d10c1229e7a467f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200437"
---
# <a name="find-devices-by-internal-ip-api"></a><span data-ttu-id="a77b9-104">Suchen von Geräten nach interner IP-API</span><span class="sxs-lookup"><span data-stu-id="a77b9-104">Find devices by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a77b9-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a77b9-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="a77b9-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a77b9-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a77b9-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a77b9-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="a77b9-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a77b9-108">API description</span></span>
<span data-ttu-id="a77b9-109">Suchen [Sie Computer,](machine.md) die mit der angeforderten internen IP im Zeitraum von 15 Minuten vor und nach einem bestimmten Zeitstempel gesehen werden.</span><span class="sxs-lookup"><span data-stu-id="a77b9-109">Find [Machines](machine.md) seen with the requested internal IP in the time range of 15 minutes prior and after a given timestamp.</span></span>


## <a name="limitations"></a><span data-ttu-id="a77b9-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a77b9-110">Limitations</span></span>
1. <span data-ttu-id="a77b9-111">Der angegebene Zeitstempel muss in den letzten 30 Tagen sein.</span><span class="sxs-lookup"><span data-stu-id="a77b9-111">The given timestamp must be in the past 30 days.</span></span>
2. <span data-ttu-id="a77b9-112">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="a77b9-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="a77b9-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a77b9-113">Permissions</span></span>
<span data-ttu-id="a77b9-114">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a77b9-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a77b9-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a77b9-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a77b9-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="a77b9-116">Permission type</span></span> |   <span data-ttu-id="a77b9-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a77b9-117">Permission</span></span>  |   <span data-ttu-id="a77b9-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a77b9-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a77b9-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="a77b9-119">Application</span></span> |   <span data-ttu-id="a77b9-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="a77b9-120">Machine.Read.All</span></span> |  <span data-ttu-id="a77b9-121">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="a77b9-121">'Read all machine profiles'</span></span>
<span data-ttu-id="a77b9-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="a77b9-122">Application</span></span> |   <span data-ttu-id="a77b9-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="a77b9-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="a77b9-124">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="a77b9-124">'Read and write all machine information'</span></span>
<span data-ttu-id="a77b9-125">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="a77b9-125">Delegated (work or school account)</span></span> | <span data-ttu-id="a77b9-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="a77b9-126">Machine.Read</span></span> | <span data-ttu-id="a77b9-127">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="a77b9-127">'Read machine information'</span></span>
<span data-ttu-id="a77b9-128">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="a77b9-128">Delegated (work or school account)</span></span> | <span data-ttu-id="a77b9-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a77b9-129">Machine.ReadWrite</span></span> | <span data-ttu-id="a77b9-130">"Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="a77b9-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="a77b9-131">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="a77b9-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="a77b9-132">Die Antwort umfasst nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="a77b9-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="a77b9-133">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="a77b9-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="a77b9-134">Die Antwort umfasst nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="a77b9-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="a77b9-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="a77b9-135">HTTP request</span></span>
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a><span data-ttu-id="a77b9-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="a77b9-136">Request headers</span></span>

<span data-ttu-id="a77b9-137">Name</span><span class="sxs-lookup"><span data-stu-id="a77b9-137">Name</span></span> | <span data-ttu-id="a77b9-138">Typ</span><span class="sxs-lookup"><span data-stu-id="a77b9-138">Type</span></span> | <span data-ttu-id="a77b9-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a77b9-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="a77b9-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="a77b9-140">Authorization</span></span> | <span data-ttu-id="a77b9-141">String</span><span class="sxs-lookup"><span data-stu-id="a77b9-141">String</span></span> | <span data-ttu-id="a77b9-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a77b9-142">Bearer {token}.</span></span> <span data-ttu-id="a77b9-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="a77b9-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a77b9-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="a77b9-144">Request body</span></span>
<span data-ttu-id="a77b9-145">Empty</span><span class="sxs-lookup"><span data-stu-id="a77b9-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a77b9-146">Antwort</span><span class="sxs-lookup"><span data-stu-id="a77b9-146">Response</span></span>
<span data-ttu-id="a77b9-147">Wenn erfolgreich – 200 OK mit liste der Computer im Antworttext.</span><span class="sxs-lookup"><span data-stu-id="a77b9-147">If successful - 200 OK with list of the machines in the response body.</span></span>
<span data-ttu-id="a77b9-148">Wenn der Zeitstempel nicht in den letzten 30 Tagen liegt – 400 Ungültige Anforderung.</span><span class="sxs-lookup"><span data-stu-id="a77b9-148">If the timestamp is not in the past 30 days - 400 Bad Request.</span></span>

## <a name="example"></a><span data-ttu-id="a77b9-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a77b9-149">Example</span></span>

<span data-ttu-id="a77b9-150">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="a77b9-150">**Request**</span></span>

<span data-ttu-id="a77b9-151">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="a77b9-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```

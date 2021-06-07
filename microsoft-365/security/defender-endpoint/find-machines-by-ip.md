---
title: Suchen von Geräten nach interner IP-API
description: Suchen von Geräten mit der angeforderten internen IP im Zeitraum von 15 Minuten vor und nach einem bestimmten Zeitstempel
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Gerät, IP, suchen, Gerät suchen, nach IP, IP
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
ms.openlocfilehash: 46afa945ce86c35e3af1c542eb1a9770041b3430
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769437"
---
# <a name="find-devices-by-internal-ip-api"></a><span data-ttu-id="9c5a3-104">Suchen von Geräten nach interner IP-API</span><span class="sxs-lookup"><span data-stu-id="9c5a3-104">Find devices by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9c5a3-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9c5a3-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="9c5a3-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="9c5a3-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9c5a3-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="9c5a3-108">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c5a3-108">API description</span></span>
<span data-ttu-id="9c5a3-109">Suchen Sie [Computer](machine.md) mit der angeforderten internen IP im Zeitraum von 15 Minuten vor und nach einem bestimmten Zeitstempel.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-109">Find [Machines](machine.md) seen with the requested internal IP in the time range of 15 minutes prior and after a given timestamp.</span></span>


## <a name="limitations"></a><span data-ttu-id="9c5a3-110">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="9c5a3-110">Limitations</span></span>
1. <span data-ttu-id="9c5a3-111">Der angegebene Zeitstempel muss in den letzten 30 Tagen sein.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-111">The given timestamp must be in the past 30 days.</span></span>
2. <span data-ttu-id="9c5a3-112">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="9c5a3-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9c5a3-113">Permissions</span></span>
<span data-ttu-id="9c5a3-114">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9c5a3-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9c5a3-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9c5a3-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="9c5a3-116">Permission type</span></span> |   <span data-ttu-id="9c5a3-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="9c5a3-117">Permission</span></span>  |   <span data-ttu-id="9c5a3-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="9c5a3-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9c5a3-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="9c5a3-119">Application</span></span> |   <span data-ttu-id="9c5a3-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="9c5a3-120">Machine.Read.All</span></span> |  <span data-ttu-id="9c5a3-121">"Alle Computerprofile lesen"</span><span class="sxs-lookup"><span data-stu-id="9c5a3-121">'Read all machine profiles'</span></span>
<span data-ttu-id="9c5a3-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="9c5a3-122">Application</span></span> |   <span data-ttu-id="9c5a3-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9c5a3-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="9c5a3-124">"Alle Computerinformationen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="9c5a3-124">'Read and write all machine information'</span></span>
<span data-ttu-id="9c5a3-125">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="9c5a3-125">Delegated (work or school account)</span></span> | <span data-ttu-id="9c5a3-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="9c5a3-126">Machine.Read</span></span> | <span data-ttu-id="9c5a3-127">"Computerinformationen lesen"</span><span class="sxs-lookup"><span data-stu-id="9c5a3-127">'Read machine information'</span></span>
<span data-ttu-id="9c5a3-128">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="9c5a3-128">Delegated (work or school account)</span></span> | <span data-ttu-id="9c5a3-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9c5a3-129">Machine.ReadWrite</span></span> | <span data-ttu-id="9c5a3-130">"Lesen und Schreiben von Computerinformationen"</span><span class="sxs-lookup"><span data-stu-id="9c5a3-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="9c5a3-131">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="9c5a3-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="9c5a3-132">Die Antwort enthält nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="9c5a3-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="9c5a3-133">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="9c5a3-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="9c5a3-134">Die Antwort enthält nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="9c5a3-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9c5a3-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="9c5a3-135">HTTP request</span></span>
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a><span data-ttu-id="9c5a3-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="9c5a3-136">Request headers</span></span>

<span data-ttu-id="9c5a3-137">Name</span><span class="sxs-lookup"><span data-stu-id="9c5a3-137">Name</span></span> | <span data-ttu-id="9c5a3-138">Typ</span><span class="sxs-lookup"><span data-stu-id="9c5a3-138">Type</span></span> | <span data-ttu-id="9c5a3-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c5a3-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="9c5a3-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="9c5a3-140">Authorization</span></span> | <span data-ttu-id="9c5a3-141">String</span><span class="sxs-lookup"><span data-stu-id="9c5a3-141">String</span></span> | <span data-ttu-id="9c5a3-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-142">Bearer {token}.</span></span> <span data-ttu-id="9c5a3-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="9c5a3-144">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="9c5a3-144">Request body</span></span>
<span data-ttu-id="9c5a3-145">Empty</span><span class="sxs-lookup"><span data-stu-id="9c5a3-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9c5a3-146">Antwort</span><span class="sxs-lookup"><span data-stu-id="9c5a3-146">Response</span></span>
<span data-ttu-id="9c5a3-147">Wenn erfolgreich – 200 OK mit der Liste der Computer im Antworttext.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-147">If successful - 200 OK with list of the machines in the response body.</span></span>
<span data-ttu-id="9c5a3-148">Wenn der Zeitstempel nicht in den letzten 30 Tagen liegt – 400 Ungültige Anforderung.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-148">If the timestamp is not in the past 30 days - 400 Bad Request.</span></span>

## <a name="example"></a><span data-ttu-id="9c5a3-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c5a3-149">Example</span></span>

<span data-ttu-id="9c5a3-150">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="9c5a3-150">**Request**</span></span>

<span data-ttu-id="9c5a3-151">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```

---
title: Isolieren der Computer-API
description: Hier erfahren Sie, wie Sie die Api "Computer isolieren" verwenden, um ein Gerät vom Zugriff auf ein externes Netzwerk in Microsoft Defender for Endpoint zu isolieren.
keywords: apis, graph api, supported apis, isolate device
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
ms.openlocfilehash: b9c8d4da528ba065dc1b4a68ddaa816a1ad78c4a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187832"
---
# <a name="isolate-machine-api"></a><span data-ttu-id="f2dd1-104">Isolieren der Computer-API</span><span class="sxs-lookup"><span data-stu-id="f2dd1-104">Isolate machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f2dd1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f2dd1-105">**Applies to:**</span></span>
- [<span data-ttu-id="f2dd1-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f2dd1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f2dd1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2dd1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="f2dd1-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f2dd1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f2dd1-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f2dd1-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2dd1-110">API description</span></span>
<span data-ttu-id="f2dd1-111">Isoliert ein Gerät vom Zugriff auf ein externes Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-111">Isolates a device from accessing external network.</span></span>


## <a name="limitations"></a><span data-ttu-id="f2dd1-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f2dd1-112">Limitations</span></span>
1. <span data-ttu-id="f2dd1-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="f2dd1-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f2dd1-114">Permissions</span></span>
<span data-ttu-id="f2dd1-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f2dd1-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f2dd1-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f2dd1-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="f2dd1-117">Permission type</span></span> |   <span data-ttu-id="f2dd1-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f2dd1-118">Permission</span></span>  |   <span data-ttu-id="f2dd1-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f2dd1-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f2dd1-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="f2dd1-120">Application</span></span> |   <span data-ttu-id="f2dd1-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="f2dd1-121">Machine.Isolate</span></span> |   <span data-ttu-id="f2dd1-122">"Computer isolieren"</span><span class="sxs-lookup"><span data-stu-id="f2dd1-122">'Isolate machine'</span></span>
<span data-ttu-id="f2dd1-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="f2dd1-123">Delegated (work or school account)</span></span> | <span data-ttu-id="f2dd1-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="f2dd1-124">Machine.Isolate</span></span> |  <span data-ttu-id="f2dd1-125">"Computer isolieren"</span><span class="sxs-lookup"><span data-stu-id="f2dd1-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="f2dd1-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="f2dd1-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f2dd1-127">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Aktive Korrekturaktionen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="f2dd1-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="f2dd1-128">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="f2dd1-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="f2dd1-129">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="f2dd1-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a><span data-ttu-id="f2dd1-130">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="f2dd1-130">Request headers</span></span>

<span data-ttu-id="f2dd1-131">Name</span><span class="sxs-lookup"><span data-stu-id="f2dd1-131">Name</span></span> | <span data-ttu-id="f2dd1-132">Typ</span><span class="sxs-lookup"><span data-stu-id="f2dd1-132">Type</span></span> | <span data-ttu-id="f2dd1-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2dd1-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="f2dd1-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="f2dd1-134">Authorization</span></span> | <span data-ttu-id="f2dd1-135">String</span><span class="sxs-lookup"><span data-stu-id="f2dd1-135">String</span></span> | <span data-ttu-id="f2dd1-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-136">Bearer {token}.</span></span> <span data-ttu-id="f2dd1-137">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-137">**Required**.</span></span>
<span data-ttu-id="f2dd1-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="f2dd1-138">Content-Type</span></span> | <span data-ttu-id="f2dd1-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f2dd1-139">string</span></span> | <span data-ttu-id="f2dd1-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-140">application/json.</span></span> <span data-ttu-id="f2dd1-141">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f2dd1-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="f2dd1-142">Request body</span></span>
<span data-ttu-id="f2dd1-143">Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f2dd1-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="f2dd1-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2dd1-144">Parameter</span></span> | <span data-ttu-id="f2dd1-145">Typ</span><span class="sxs-lookup"><span data-stu-id="f2dd1-145">Type</span></span>    | <span data-ttu-id="f2dd1-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2dd1-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="f2dd1-147">Kommentar</span><span class="sxs-lookup"><span data-stu-id="f2dd1-147">Comment</span></span> |   <span data-ttu-id="f2dd1-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f2dd1-148">String</span></span> |    <span data-ttu-id="f2dd1-149">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-149">Comment to associate with the action.</span></span> <span data-ttu-id="f2dd1-150">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-150">**Required**.</span></span>
<span data-ttu-id="f2dd1-151">IsolationType</span><span class="sxs-lookup"><span data-stu-id="f2dd1-151">IsolationType</span></span>   | <span data-ttu-id="f2dd1-152">String</span><span class="sxs-lookup"><span data-stu-id="f2dd1-152">String</span></span> |  <span data-ttu-id="f2dd1-153">Typ der Isolation.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-153">Type of the isolation.</span></span> <span data-ttu-id="f2dd1-154">Zulässige Werte sind: "Vollständig" oder "Selektiv".</span><span class="sxs-lookup"><span data-stu-id="f2dd1-154">Allowed values are: 'Full' or 'Selective'.</span></span>

<span data-ttu-id="f2dd1-155">**IsolationType** steuert den typ der durchzuführende Isolation und kann einer der folgenden Sein:</span><span class="sxs-lookup"><span data-stu-id="f2dd1-155">**IsolationType** controls the type of isolation to perform and can be one of the following:</span></span>
- <span data-ttu-id="f2dd1-156">Vollständig – Vollständige Isolation</span><span class="sxs-lookup"><span data-stu-id="f2dd1-156">Full – Full isolation</span></span>
- <span data-ttu-id="f2dd1-157">Selektiv – Beschränken Sie den Zugriff auf das Netzwerk nur auf begrenzte Anwendungen (weitere Informationen finden Sie unter [Isolieren](respond-machine-alerts.md#isolate-devices-from-the-network) von Geräten aus dem Netzwerk)</span><span class="sxs-lookup"><span data-stu-id="f2dd1-157">Selective – Restrict only limited set of applications from accessing the network (see [Isolate devices from the network](respond-machine-alerts.md#isolate-devices-from-the-network) for more details)</span></span>


## <a name="response"></a><span data-ttu-id="f2dd1-158">Antwort</span><span class="sxs-lookup"><span data-stu-id="f2dd1-158">Response</span></span>
<span data-ttu-id="f2dd1-159">Wenn die Methode erfolgreich ist, wird 201 – Antwortcode erstellt und [Computeraktion](machineaction.md) im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-159">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="f2dd1-160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f2dd1-160">Example</span></span>

<span data-ttu-id="f2dd1-161">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="f2dd1-161">**Request**</span></span>

<span data-ttu-id="f2dd1-162">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="f2dd1-162">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- <span data-ttu-id="f2dd1-163">Informationen zur Isolierung eines Geräts finden Sie unter [Release device from isolation](unisolate-machine.md).</span><span class="sxs-lookup"><span data-stu-id="f2dd1-163">To release a device from isolation, see [Release device from isolation](unisolate-machine.md).</span></span>

---
title: Computer-API isolieren
description: Erfahren Sie, wie Sie die Computer-API "Isolieren" verwenden, um ein Gerät vom Zugriff auf das externe Netzwerk in Microsoft Defender für Endpunkt zu isolieren.
keywords: APIs, Graph-API, unterstützte APIs, Gerät isolieren
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
ms.openlocfilehash: 9f3313a08b072f4fb2f699148ab801207e56fc09
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772113"
---
# <a name="isolate-machine-api"></a><span data-ttu-id="013cb-104">Computer-API isolieren</span><span class="sxs-lookup"><span data-stu-id="013cb-104">Isolate machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="013cb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="013cb-105">**Applies to:**</span></span>
- [<span data-ttu-id="013cb-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="013cb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="013cb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="013cb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="013cb-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="013cb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="013cb-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="013cb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="013cb-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="013cb-110">API description</span></span>
<span data-ttu-id="013cb-111">Isoliert ein Gerät am Zugriff auf das externe Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="013cb-111">Isolates a device from accessing external network.</span></span>


## <a name="limitations"></a><span data-ttu-id="013cb-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="013cb-112">Limitations</span></span>
1. <span data-ttu-id="013cb-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="013cb-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="013cb-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="013cb-114">Permissions</span></span>
<span data-ttu-id="013cb-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="013cb-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="013cb-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="013cb-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="013cb-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="013cb-117">Permission type</span></span> |   <span data-ttu-id="013cb-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="013cb-118">Permission</span></span>  |   <span data-ttu-id="013cb-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="013cb-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="013cb-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="013cb-120">Application</span></span> |   <span data-ttu-id="013cb-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="013cb-121">Machine.Isolate</span></span> |   <span data-ttu-id="013cb-122">"Computer isolieren"</span><span class="sxs-lookup"><span data-stu-id="013cb-122">'Isolate machine'</span></span>
<span data-ttu-id="013cb-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="013cb-123">Delegated (work or school account)</span></span> | <span data-ttu-id="013cb-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="013cb-124">Machine.Isolate</span></span> |  <span data-ttu-id="013cb-125">"Computer isolieren"</span><span class="sxs-lookup"><span data-stu-id="013cb-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="013cb-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="013cb-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="013cb-127">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Aktive Korrekturaktionen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="013cb-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="013cb-128">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="013cb-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="013cb-129">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="013cb-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a><span data-ttu-id="013cb-130">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="013cb-130">Request headers</span></span>

<span data-ttu-id="013cb-131">Name</span><span class="sxs-lookup"><span data-stu-id="013cb-131">Name</span></span> | <span data-ttu-id="013cb-132">Typ</span><span class="sxs-lookup"><span data-stu-id="013cb-132">Type</span></span> | <span data-ttu-id="013cb-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="013cb-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="013cb-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="013cb-134">Authorization</span></span> | <span data-ttu-id="013cb-135">String</span><span class="sxs-lookup"><span data-stu-id="013cb-135">String</span></span> | <span data-ttu-id="013cb-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="013cb-136">Bearer {token}.</span></span> <span data-ttu-id="013cb-137">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="013cb-137">**Required**.</span></span>
<span data-ttu-id="013cb-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="013cb-138">Content-Type</span></span> | <span data-ttu-id="013cb-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="013cb-139">string</span></span> | <span data-ttu-id="013cb-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="013cb-140">application/json.</span></span> <span data-ttu-id="013cb-141">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="013cb-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="013cb-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="013cb-142">Request body</span></span>
<span data-ttu-id="013cb-143">Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:</span><span class="sxs-lookup"><span data-stu-id="013cb-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="013cb-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="013cb-144">Parameter</span></span> | <span data-ttu-id="013cb-145">Typ</span><span class="sxs-lookup"><span data-stu-id="013cb-145">Type</span></span>    | <span data-ttu-id="013cb-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="013cb-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="013cb-147">Kommentar</span><span class="sxs-lookup"><span data-stu-id="013cb-147">Comment</span></span> |   <span data-ttu-id="013cb-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="013cb-148">String</span></span> |    <span data-ttu-id="013cb-149">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="013cb-149">Comment to associate with the action.</span></span> <span data-ttu-id="013cb-150">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="013cb-150">**Required**.</span></span>
<span data-ttu-id="013cb-151">IsolationType</span><span class="sxs-lookup"><span data-stu-id="013cb-151">IsolationType</span></span>   | <span data-ttu-id="013cb-152">String</span><span class="sxs-lookup"><span data-stu-id="013cb-152">String</span></span> |  <span data-ttu-id="013cb-153">Typ der Isolation.</span><span class="sxs-lookup"><span data-stu-id="013cb-153">Type of the isolation.</span></span> <span data-ttu-id="013cb-154">Zulässige Werte sind: 'Full' oder 'Selective'.</span><span class="sxs-lookup"><span data-stu-id="013cb-154">Allowed values are: 'Full' or 'Selective'.</span></span>

<span data-ttu-id="013cb-155">**IsolationType** steuert den Typ der auszuführenden Isolierung und kann eine der folgenden Sein:</span><span class="sxs-lookup"><span data-stu-id="013cb-155">**IsolationType** controls the type of isolation to perform and can be one of the following:</span></span>
- <span data-ttu-id="013cb-156">Vollständig – vollständige Isolation</span><span class="sxs-lookup"><span data-stu-id="013cb-156">Full – Full isolation</span></span>
- <span data-ttu-id="013cb-157">Selektiv – Beschränken Sie nur einen begrenzten Satz von Anwendungen auf das Netzwerk (weitere Informationen finden Sie unter ["Isolieren von Geräten aus dem Netzwerk")](respond-machine-alerts.md#isolate-devices-from-the-network)</span><span class="sxs-lookup"><span data-stu-id="013cb-157">Selective – Restrict only limited set of applications from accessing the network (see [Isolate devices from the network](respond-machine-alerts.md#isolate-devices-from-the-network) for more details)</span></span>


## <a name="response"></a><span data-ttu-id="013cb-158">Antwort</span><span class="sxs-lookup"><span data-stu-id="013cb-158">Response</span></span>
<span data-ttu-id="013cb-159">Bei erfolgreicher Ausführung gibt die Methode den Antwortcode 201 – Erstellt und die [Computeraktion](machineaction.md) im Antworttext zurück.</span><span class="sxs-lookup"><span data-stu-id="013cb-159">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="013cb-160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="013cb-160">Example</span></span>

<span data-ttu-id="013cb-161">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="013cb-161">**Request**</span></span>

<span data-ttu-id="013cb-162">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="013cb-162">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- <span data-ttu-id="013cb-163">Informationen zum Aufheben der Isolation eines Geräts finden Sie unter ["Gerät aus Isolation freigeben".](unisolate-machine.md)</span><span class="sxs-lookup"><span data-stu-id="013cb-163">To release a device from isolation, see [Release device from isolation](unisolate-machine.md).</span></span>

---
title: Freigeben des Geräts von der Isolations-API
description: Verwenden Sie diese API, um Aufrufe im Zusammenhang mit der Veröffentlichung eines Geräts aus der Isolation zu erstellen.
keywords: APIs, Graph-API, unterstützte APIs, Gerät aus Isolation entfernen
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
ms.openlocfilehash: 3ed2e7968464320e41e47ad734026bdd9b323ceb
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771273"
---
# <a name="release-device-from-isolation-api"></a><span data-ttu-id="530d1-104">Freigeben des Geräts von der Isolations-API</span><span class="sxs-lookup"><span data-stu-id="530d1-104">Release device from isolation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="530d1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="530d1-105">**Applies to:**</span></span> 
- [<span data-ttu-id="530d1-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="530d1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="530d1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="530d1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="530d1-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="530d1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="530d1-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="530d1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="530d1-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="530d1-110">API description</span></span>
<span data-ttu-id="530d1-111">Aufheben der Isolierung eines Geräts.</span><span class="sxs-lookup"><span data-stu-id="530d1-111">Undo isolation of a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="530d1-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="530d1-112">Limitations</span></span>
1. <span data-ttu-id="530d1-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="530d1-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="530d1-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="530d1-114">Permissions</span></span>
<span data-ttu-id="530d1-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="530d1-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="530d1-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="530d1-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="530d1-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="530d1-117">Permission type</span></span> |   <span data-ttu-id="530d1-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="530d1-118">Permission</span></span>  |   <span data-ttu-id="530d1-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="530d1-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="530d1-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="530d1-120">Application</span></span> |   <span data-ttu-id="530d1-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="530d1-121">Machine.Isolate</span></span> |   <span data-ttu-id="530d1-122">"Computer isolieren"</span><span class="sxs-lookup"><span data-stu-id="530d1-122">'Isolate machine'</span></span>
<span data-ttu-id="530d1-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="530d1-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="530d1-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="530d1-124">Machine.Isolate</span></span> |   <span data-ttu-id="530d1-125">"Computer isolieren"</span><span class="sxs-lookup"><span data-stu-id="530d1-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="530d1-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="530d1-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="530d1-127">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Aktive Korrekturaktionen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="530d1-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="530d1-128">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="530d1-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="530d1-129">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="530d1-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unisolate
```

## <a name="request-headers"></a><span data-ttu-id="530d1-130">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="530d1-130">Request headers</span></span>

<span data-ttu-id="530d1-131">Name</span><span class="sxs-lookup"><span data-stu-id="530d1-131">Name</span></span> | <span data-ttu-id="530d1-132">Typ</span><span class="sxs-lookup"><span data-stu-id="530d1-132">Type</span></span> | <span data-ttu-id="530d1-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="530d1-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="530d1-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="530d1-134">Authorization</span></span> | <span data-ttu-id="530d1-135">String</span><span class="sxs-lookup"><span data-stu-id="530d1-135">String</span></span> | <span data-ttu-id="530d1-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="530d1-136">Bearer {token}.</span></span> <span data-ttu-id="530d1-137">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="530d1-137">**Required**.</span></span>
<span data-ttu-id="530d1-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="530d1-138">Content-Type</span></span> | <span data-ttu-id="530d1-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="530d1-139">string</span></span> | <span data-ttu-id="530d1-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="530d1-140">application/json.</span></span> <span data-ttu-id="530d1-141">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="530d1-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="530d1-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="530d1-142">Request body</span></span>
<span data-ttu-id="530d1-143">Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:</span><span class="sxs-lookup"><span data-stu-id="530d1-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="530d1-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="530d1-144">Parameter</span></span> | <span data-ttu-id="530d1-145">Typ</span><span class="sxs-lookup"><span data-stu-id="530d1-145">Type</span></span>    | <span data-ttu-id="530d1-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="530d1-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="530d1-147">Kommentar</span><span class="sxs-lookup"><span data-stu-id="530d1-147">Comment</span></span> |   <span data-ttu-id="530d1-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="530d1-148">String</span></span> |    <span data-ttu-id="530d1-149">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="530d1-149">Comment to associate with the action.</span></span> <span data-ttu-id="530d1-150">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="530d1-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="530d1-151">Antwort</span><span class="sxs-lookup"><span data-stu-id="530d1-151">Response</span></span>
<span data-ttu-id="530d1-152">Bei erfolgreicher Ausführung gibt die Methode den Antwortcode 201 – Erstellt und die [Computeraktion](machineaction.md) im Antworttext zurück.</span><span class="sxs-lookup"><span data-stu-id="530d1-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="530d1-153">Beispiel</span><span class="sxs-lookup"><span data-stu-id="530d1-153">Example</span></span>

<span data-ttu-id="530d1-154">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="530d1-154">**Request**</span></span>

<span data-ttu-id="530d1-155">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="530d1-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unisolate 
```

```json
{
  "Comment": "Unisolate machine since it was clean and validated"
}

```


- <span data-ttu-id="530d1-156">Informationen zum Isolieren eines Geräts finden Sie unter ["Gerät isolieren".](isolate-machine.md)</span><span class="sxs-lookup"><span data-stu-id="530d1-156">To isolate a device, see [Isolate device](isolate-machine.md).</span></span>


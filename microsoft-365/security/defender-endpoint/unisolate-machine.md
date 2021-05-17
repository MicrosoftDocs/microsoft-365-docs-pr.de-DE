---
title: Isolieren des Geräts aus der Isolations-API
description: Verwenden Sie diese API, um Aufrufe im Zusammenhang mit der Isolierung eines Geräts zu erstellen.
keywords: apis, graph api, supported apis, remove device from isolation
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
ms.openlocfilehash: 036eb6f589c13fb9232557c45619829149179148
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199333"
---
# <a name="release-device-from-isolation-api"></a><span data-ttu-id="15e0a-104">Isolieren des Geräts aus der Isolations-API</span><span class="sxs-lookup"><span data-stu-id="15e0a-104">Release device from isolation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="15e0a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="15e0a-105">**Applies to:**</span></span> 
- [<span data-ttu-id="15e0a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="15e0a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="15e0a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15e0a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="15e0a-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="15e0a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="15e0a-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="15e0a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="15e0a-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15e0a-110">API description</span></span>
<span data-ttu-id="15e0a-111">Rückgängig machen der Isolierung eines Geräts.</span><span class="sxs-lookup"><span data-stu-id="15e0a-111">Undo isolation of a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="15e0a-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="15e0a-112">Limitations</span></span>
1. <span data-ttu-id="15e0a-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="15e0a-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="15e0a-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="15e0a-114">Permissions</span></span>
<span data-ttu-id="15e0a-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="15e0a-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="15e0a-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="15e0a-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="15e0a-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="15e0a-117">Permission type</span></span> |   <span data-ttu-id="15e0a-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="15e0a-118">Permission</span></span>  |   <span data-ttu-id="15e0a-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="15e0a-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="15e0a-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="15e0a-120">Application</span></span> |   <span data-ttu-id="15e0a-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="15e0a-121">Machine.Isolate</span></span> |   <span data-ttu-id="15e0a-122">"Computer isolieren"</span><span class="sxs-lookup"><span data-stu-id="15e0a-122">'Isolate machine'</span></span>
<span data-ttu-id="15e0a-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="15e0a-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="15e0a-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="15e0a-124">Machine.Isolate</span></span> |   <span data-ttu-id="15e0a-125">"Computer isolieren"</span><span class="sxs-lookup"><span data-stu-id="15e0a-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="15e0a-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="15e0a-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="15e0a-127">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Aktive Korrekturaktionen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="15e0a-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="15e0a-128">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="15e0a-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="15e0a-129">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="15e0a-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unisolate
```

## <a name="request-headers"></a><span data-ttu-id="15e0a-130">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="15e0a-130">Request headers</span></span>

<span data-ttu-id="15e0a-131">Name</span><span class="sxs-lookup"><span data-stu-id="15e0a-131">Name</span></span> | <span data-ttu-id="15e0a-132">Typ</span><span class="sxs-lookup"><span data-stu-id="15e0a-132">Type</span></span> | <span data-ttu-id="15e0a-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15e0a-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="15e0a-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="15e0a-134">Authorization</span></span> | <span data-ttu-id="15e0a-135">String</span><span class="sxs-lookup"><span data-stu-id="15e0a-135">String</span></span> | <span data-ttu-id="15e0a-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="15e0a-136">Bearer {token}.</span></span> <span data-ttu-id="15e0a-137">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="15e0a-137">**Required**.</span></span>
<span data-ttu-id="15e0a-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="15e0a-138">Content-Type</span></span> | <span data-ttu-id="15e0a-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="15e0a-139">string</span></span> | <span data-ttu-id="15e0a-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="15e0a-140">application/json.</span></span> <span data-ttu-id="15e0a-141">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="15e0a-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="15e0a-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="15e0a-142">Request body</span></span>
<span data-ttu-id="15e0a-143">Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="15e0a-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="15e0a-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="15e0a-144">Parameter</span></span> | <span data-ttu-id="15e0a-145">Typ</span><span class="sxs-lookup"><span data-stu-id="15e0a-145">Type</span></span>    | <span data-ttu-id="15e0a-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15e0a-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="15e0a-147">Kommentar</span><span class="sxs-lookup"><span data-stu-id="15e0a-147">Comment</span></span> |   <span data-ttu-id="15e0a-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="15e0a-148">String</span></span> |    <span data-ttu-id="15e0a-149">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="15e0a-149">Comment to associate with the action.</span></span> <span data-ttu-id="15e0a-150">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="15e0a-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="15e0a-151">Antwort</span><span class="sxs-lookup"><span data-stu-id="15e0a-151">Response</span></span>
<span data-ttu-id="15e0a-152">Wenn die Methode erfolgreich ist, wird 201 – Antwortcode erstellt und [Computeraktion](machineaction.md) im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="15e0a-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="15e0a-153">Beispiel</span><span class="sxs-lookup"><span data-stu-id="15e0a-153">Example</span></span>

<span data-ttu-id="15e0a-154">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="15e0a-154">**Request**</span></span>

<span data-ttu-id="15e0a-155">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="15e0a-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unisolate 
```

```json
{
  "Comment": "Unisolate machine since it was clean and validated"
}

```


- <span data-ttu-id="15e0a-156">Informationen zum Isolieren eines Geräts finden Sie unter [Isolate device](isolate-machine.md).</span><span class="sxs-lookup"><span data-stu-id="15e0a-156">To isolate a device, see [Isolate device](isolate-machine.md).</span></span>


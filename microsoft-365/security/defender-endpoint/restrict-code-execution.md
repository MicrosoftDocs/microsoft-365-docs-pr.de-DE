---
title: Einschränken der App-Ausführungs-API
description: Verwenden Sie diese API, um Aufrufe im Zusammenhang mit dem Einschränken der Ausführung einer Anwendung zu erstellen.
keywords: apis, graph api, supported apis, collect investigation package
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
ms.openlocfilehash: 149f3aefd963f15eafa15030a322ec588c0615ed
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186779"
---
# <a name="restrict-app-execution-api"></a><span data-ttu-id="b4718-104">Einschränken der App-Ausführungs-API</span><span class="sxs-lookup"><span data-stu-id="b4718-104">Restrict app execution API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b4718-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b4718-105">**Applies to:**</span></span>
- [<span data-ttu-id="b4718-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b4718-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b4718-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4718-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b4718-108">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b4718-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b4718-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b4718-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b4718-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b4718-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b4718-111">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4718-111">API description</span></span>
<span data-ttu-id="b4718-112">Beschränken Sie die Ausführung aller Anwendungen auf dem Gerät mit Ausnahme einer vordefinierten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="b4718-112">Restrict execution of all applications on the device except a predefined set.</span></span>


## <a name="limitations"></a><span data-ttu-id="b4718-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b4718-113">Limitations</span></span>
1. <span data-ttu-id="b4718-114">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="b4718-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="b4718-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b4718-115">Permissions</span></span>
<span data-ttu-id="b4718-116">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4718-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b4718-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b4718-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b4718-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="b4718-118">Permission type</span></span> |   <span data-ttu-id="b4718-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b4718-119">Permission</span></span>  |   <span data-ttu-id="b4718-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="b4718-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b4718-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="b4718-121">Application</span></span> |   <span data-ttu-id="b4718-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="b4718-122">Machine.RestrictExecution</span></span> | <span data-ttu-id="b4718-123">"Codeausführung einschränken"</span><span class="sxs-lookup"><span data-stu-id="b4718-123">'Restrict code execution'</span></span>
<span data-ttu-id="b4718-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="b4718-124">Delegated (work or school account)</span></span> | <span data-ttu-id="b4718-125">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="b4718-125">Machine.RestrictExecution</span></span> | <span data-ttu-id="b4718-126">"Codeausführung einschränken"</span><span class="sxs-lookup"><span data-stu-id="b4718-126">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="b4718-127">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="b4718-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b4718-128">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Aktive Korrekturaktionen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="b4718-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b4718-129">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="b4718-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b4718-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="b4718-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="b4718-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="b4718-131">Request headers</span></span>

<span data-ttu-id="b4718-132">Name</span><span class="sxs-lookup"><span data-stu-id="b4718-132">Name</span></span> | <span data-ttu-id="b4718-133">Typ</span><span class="sxs-lookup"><span data-stu-id="b4718-133">Type</span></span> | <span data-ttu-id="b4718-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4718-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="b4718-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="b4718-135">Authorization</span></span> | <span data-ttu-id="b4718-136">String</span><span class="sxs-lookup"><span data-stu-id="b4718-136">String</span></span> | <span data-ttu-id="b4718-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b4718-137">Bearer {token}.</span></span> <span data-ttu-id="b4718-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b4718-138">**Required**.</span></span>
<span data-ttu-id="b4718-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="b4718-139">Content-Type</span></span> | <span data-ttu-id="b4718-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b4718-140">string</span></span> | <span data-ttu-id="b4718-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="b4718-141">application/json.</span></span> <span data-ttu-id="b4718-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b4718-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b4718-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="b4718-143">Request body</span></span>
<span data-ttu-id="b4718-144">Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b4718-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="b4718-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4718-145">Parameter</span></span> | <span data-ttu-id="b4718-146">Typ</span><span class="sxs-lookup"><span data-stu-id="b4718-146">Type</span></span>    | <span data-ttu-id="b4718-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4718-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="b4718-148">Kommentar</span><span class="sxs-lookup"><span data-stu-id="b4718-148">Comment</span></span> |   <span data-ttu-id="b4718-149">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b4718-149">String</span></span> |    <span data-ttu-id="b4718-150">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b4718-150">Comment to associate with the action.</span></span> <span data-ttu-id="b4718-151">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b4718-151">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="b4718-152">Antwort</span><span class="sxs-lookup"><span data-stu-id="b4718-152">Response</span></span>
<span data-ttu-id="b4718-153">Wenn die Methode erfolgreich ist, wird 201 – Antwortcode erstellt und [Computeraktion](machineaction.md) im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b4718-153">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="b4718-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4718-154">Example</span></span>

<span data-ttu-id="b4718-155">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="b4718-155">**Request**</span></span>

<span data-ttu-id="b4718-156">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="b4718-156">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- <span data-ttu-id="b4718-157">Informationen zum Entfernen der Codeausführungseinschränkung von einem Gerät finden Sie unter [Remove app restriction](unrestrict-code-execution.md).</span><span class="sxs-lookup"><span data-stu-id="b4718-157">To remove code execution restriction from a device, see [Remove app restriction](unrestrict-code-execution.md).</span></span>

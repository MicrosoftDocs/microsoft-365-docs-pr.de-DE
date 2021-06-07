---
title: Einschränken der App-Ausführungs-API
description: Verwenden Sie diese API, um Aufrufe im Zusammenhang mit der Einschränkung der Ausführung einer Anwendung zu erstellen.
keywords: APIs, Graph-API, unterstützte APIs, Untersuchungspaket sammeln
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
ms.openlocfilehash: 7195e91a3a9b7aef6977c925f2c8689d3e461815
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771573"
---
# <a name="restrict-app-execution-api"></a><span data-ttu-id="10134-104">Einschränken der App-Ausführungs-API</span><span class="sxs-lookup"><span data-stu-id="10134-104">Restrict app execution API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="10134-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="10134-105">**Applies to:**</span></span>
- [<span data-ttu-id="10134-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="10134-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="10134-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10134-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="10134-108">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="10134-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="10134-109">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="10134-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="10134-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="10134-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="10134-111">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10134-111">API description</span></span>
<span data-ttu-id="10134-112">Beschränken Sie die Ausführung aller Anwendungen auf dem Gerät mit Ausnahme eines vordefinierten Satzes.</span><span class="sxs-lookup"><span data-stu-id="10134-112">Restrict execution of all applications on the device except a predefined set.</span></span>


## <a name="limitations"></a><span data-ttu-id="10134-113">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="10134-113">Limitations</span></span>
1. <span data-ttu-id="10134-114">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="10134-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="10134-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="10134-115">Permissions</span></span>
<span data-ttu-id="10134-116">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="10134-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="10134-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="10134-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="10134-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="10134-118">Permission type</span></span> |   <span data-ttu-id="10134-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="10134-119">Permission</span></span>  |   <span data-ttu-id="10134-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="10134-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="10134-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="10134-121">Application</span></span> |   <span data-ttu-id="10134-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="10134-122">Machine.RestrictExecution</span></span> | <span data-ttu-id="10134-123">"Einschränken der Codeausführung"</span><span class="sxs-lookup"><span data-stu-id="10134-123">'Restrict code execution'</span></span>
<span data-ttu-id="10134-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="10134-124">Delegated (work or school account)</span></span> | <span data-ttu-id="10134-125">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="10134-125">Machine.RestrictExecution</span></span> | <span data-ttu-id="10134-126">"Einschränken der Codeausführung"</span><span class="sxs-lookup"><span data-stu-id="10134-126">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="10134-127">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="10134-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="10134-128">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Aktive Korrekturaktionen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="10134-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="10134-129">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="10134-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="10134-130">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="10134-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="10134-131">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="10134-131">Request headers</span></span>

<span data-ttu-id="10134-132">Name</span><span class="sxs-lookup"><span data-stu-id="10134-132">Name</span></span> | <span data-ttu-id="10134-133">Typ</span><span class="sxs-lookup"><span data-stu-id="10134-133">Type</span></span> | <span data-ttu-id="10134-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10134-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="10134-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="10134-135">Authorization</span></span> | <span data-ttu-id="10134-136">String</span><span class="sxs-lookup"><span data-stu-id="10134-136">String</span></span> | <span data-ttu-id="10134-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="10134-137">Bearer {token}.</span></span> <span data-ttu-id="10134-138">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="10134-138">**Required**.</span></span>
<span data-ttu-id="10134-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="10134-139">Content-Type</span></span> | <span data-ttu-id="10134-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="10134-140">string</span></span> | <span data-ttu-id="10134-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="10134-141">application/json.</span></span> <span data-ttu-id="10134-142">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="10134-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="10134-143">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="10134-143">Request body</span></span>
<span data-ttu-id="10134-144">Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:</span><span class="sxs-lookup"><span data-stu-id="10134-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="10134-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="10134-145">Parameter</span></span> | <span data-ttu-id="10134-146">Typ</span><span class="sxs-lookup"><span data-stu-id="10134-146">Type</span></span>    | <span data-ttu-id="10134-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10134-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="10134-148">Kommentar</span><span class="sxs-lookup"><span data-stu-id="10134-148">Comment</span></span> |   <span data-ttu-id="10134-149">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="10134-149">String</span></span> |    <span data-ttu-id="10134-150">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="10134-150">Comment to associate with the action.</span></span> <span data-ttu-id="10134-151">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="10134-151">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="10134-152">Antwort</span><span class="sxs-lookup"><span data-stu-id="10134-152">Response</span></span>
<span data-ttu-id="10134-153">Bei erfolgreicher Ausführung gibt die Methode den Antwortcode 201 – Erstellt und die [Computeraktion](machineaction.md) im Antworttext zurück.</span><span class="sxs-lookup"><span data-stu-id="10134-153">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="10134-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10134-154">Example</span></span>

<span data-ttu-id="10134-155">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="10134-155">**Request**</span></span>

<span data-ttu-id="10134-156">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="10134-156">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- <span data-ttu-id="10134-157">Informationen zum Entfernen der Codeausführungseinschränkung von einem Gerät finden Sie unter Entfernen der [App-Einschränkung.](unrestrict-code-execution.md)</span><span class="sxs-lookup"><span data-stu-id="10134-157">To remove code execution restriction from a device, see [Remove app restriction](unrestrict-code-execution.md).</span></span>

---
title: Entfernen der App-Einschränkungs-API
description: Verwenden Sie diese API, um Aufrufe im Zusammenhang mit dem Entfernen einer Einschränkung aus Anwendungen aus der Ausführung zu erstellen.
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
ms.openlocfilehash: abff4e02bfdfe6f5598ca96121815930dce3c85e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199321"
---
# <a name="remove-app-restriction-api"></a><span data-ttu-id="4ddee-104">Entfernen der App-Einschränkungs-API</span><span class="sxs-lookup"><span data-stu-id="4ddee-104">Remove app restriction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4ddee-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4ddee-105">**Applies to:**</span></span>
- [<span data-ttu-id="4ddee-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4ddee-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="4ddee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ddee-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4ddee-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="4ddee-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4ddee-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4ddee-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4ddee-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ddee-110">API description</span></span>
<span data-ttu-id="4ddee-111">Aktivieren Sie die Ausführung einer beliebigen Anwendung auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="4ddee-111">Enable execution of any application on the device.</span></span>


## <a name="limitations"></a><span data-ttu-id="4ddee-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4ddee-112">Limitations</span></span>
1. <span data-ttu-id="4ddee-113">Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="4ddee-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="4ddee-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4ddee-114">Permissions</span></span>
<span data-ttu-id="4ddee-115">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4ddee-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4ddee-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4ddee-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4ddee-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="4ddee-117">Permission type</span></span> |   <span data-ttu-id="4ddee-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4ddee-118">Permission</span></span>  |   <span data-ttu-id="4ddee-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4ddee-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4ddee-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="4ddee-120">Application</span></span> |   <span data-ttu-id="4ddee-121">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="4ddee-121">Machine.RestrictExecution</span></span> | <span data-ttu-id="4ddee-122">"Codeausführung einschränken"</span><span class="sxs-lookup"><span data-stu-id="4ddee-122">'Restrict code execution'</span></span>
<span data-ttu-id="4ddee-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="4ddee-123">Delegated (work or school account)</span></span> | <span data-ttu-id="4ddee-124">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="4ddee-124">Machine.RestrictExecution</span></span> | <span data-ttu-id="4ddee-125">"Codeausführung einschränken"</span><span class="sxs-lookup"><span data-stu-id="4ddee-125">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="4ddee-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="4ddee-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4ddee-127">Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Aktive Korrekturaktionen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)</span><span class="sxs-lookup"><span data-stu-id="4ddee-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="4ddee-128">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).</span><span class="sxs-lookup"><span data-stu-id="4ddee-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4ddee-129">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="4ddee-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unrestrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="4ddee-130">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="4ddee-130">Request headers</span></span>
<span data-ttu-id="4ddee-131">Name</span><span class="sxs-lookup"><span data-stu-id="4ddee-131">Name</span></span> | <span data-ttu-id="4ddee-132">Typ</span><span class="sxs-lookup"><span data-stu-id="4ddee-132">Type</span></span> | <span data-ttu-id="4ddee-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ddee-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="4ddee-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="4ddee-134">Authorization</span></span> | <span data-ttu-id="4ddee-135">String</span><span class="sxs-lookup"><span data-stu-id="4ddee-135">String</span></span> | <span data-ttu-id="4ddee-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4ddee-136">Bearer {token}.</span></span> <span data-ttu-id="4ddee-137">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="4ddee-137">**Required**.</span></span>
<span data-ttu-id="4ddee-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4ddee-138">Content-Type</span></span> | <span data-ttu-id="4ddee-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4ddee-139">string</span></span> | <span data-ttu-id="4ddee-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="4ddee-140">application/json.</span></span> <span data-ttu-id="4ddee-141">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="4ddee-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="4ddee-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="4ddee-142">Request body</span></span>
<span data-ttu-id="4ddee-143">Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="4ddee-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="4ddee-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="4ddee-144">Parameter</span></span> | <span data-ttu-id="4ddee-145">Typ</span><span class="sxs-lookup"><span data-stu-id="4ddee-145">Type</span></span>    | <span data-ttu-id="4ddee-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ddee-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="4ddee-147">Kommentar</span><span class="sxs-lookup"><span data-stu-id="4ddee-147">Comment</span></span> |   <span data-ttu-id="4ddee-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4ddee-148">String</span></span> | <span data-ttu-id="4ddee-149">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4ddee-149">Comment to associate with the action.</span></span> <span data-ttu-id="4ddee-150">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="4ddee-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="4ddee-151">Antwort</span><span class="sxs-lookup"><span data-stu-id="4ddee-151">Response</span></span>
<span data-ttu-id="4ddee-152">Wenn die Methode erfolgreich ist, wird 201 – Antwortcode erstellt und [Computeraktion](machineaction.md) im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4ddee-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="4ddee-153">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ddee-153">Example</span></span>

<span data-ttu-id="4ddee-154">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="4ddee-154">**Request**</span></span>

<span data-ttu-id="4ddee-155">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4ddee-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unrestrictCodeExecution 
```

```json
{
  "Comment": "Unrestrict code execution since machine was cleaned and validated"
}

```


<span data-ttu-id="4ddee-156">Informationen zum Einschränken der Codeausführung auf einem Gerät finden Sie unter [Restrict app execution](restrict-code-execution.md).</span><span class="sxs-lookup"><span data-stu-id="4ddee-156">To restrict code execution on a device, see [Restrict app execution](restrict-code-execution.md).</span></span>

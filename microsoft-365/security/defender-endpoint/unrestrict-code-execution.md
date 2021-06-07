---
title: Entfernen der App-Einschränkungs-API
description: Verwenden Sie diese API, um Aufrufe zu erstellen, die sich auf das Entfernen einer Einschränkung von Anwendungen beziehen.
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
ms.openlocfilehash: 989e44647a5f0661bfdefa184c6c26f4cdf2b456
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770877"
---
# <a name="remove-app-restriction-api"></a><span data-ttu-id="f89b5-104">Entfernen der App-Einschränkungs-API</span><span class="sxs-lookup"><span data-stu-id="f89b5-104">Remove app restriction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f89b5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f89b5-105">**Applies to:**</span></span>
- [<span data-ttu-id="f89b5-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f89b5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f89b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f89b5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f89b5-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="f89b5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f89b5-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f89b5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f89b5-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f89b5-110">API description</span></span>
<span data-ttu-id="f89b5-111">Aktivieren Sie die Ausführung einer beliebigen Anwendung auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="f89b5-111">Enable execution of any application on the device.</span></span>


## <a name="limitations"></a><span data-ttu-id="f89b5-112">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="f89b5-112">Limitations</span></span>
1. <span data-ttu-id="f89b5-113">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="f89b5-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="f89b5-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f89b5-114">Permissions</span></span>
<span data-ttu-id="f89b5-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f89b5-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f89b5-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f89b5-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f89b5-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="f89b5-117">Permission type</span></span> |   <span data-ttu-id="f89b5-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f89b5-118">Permission</span></span>  |   <span data-ttu-id="f89b5-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f89b5-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f89b5-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="f89b5-120">Application</span></span> |   <span data-ttu-id="f89b5-121">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="f89b5-121">Machine.RestrictExecution</span></span> | <span data-ttu-id="f89b5-122">"Einschränken der Codeausführung"</span><span class="sxs-lookup"><span data-stu-id="f89b5-122">'Restrict code execution'</span></span>
<span data-ttu-id="f89b5-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="f89b5-123">Delegated (work or school account)</span></span> | <span data-ttu-id="f89b5-124">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="f89b5-124">Machine.RestrictExecution</span></span> | <span data-ttu-id="f89b5-125">"Einschränken der Codeausführung"</span><span class="sxs-lookup"><span data-stu-id="f89b5-125">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="f89b5-126">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="f89b5-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f89b5-127">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Aktive Korrekturaktionen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="f89b5-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="f89b5-128">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="f89b5-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f89b5-129">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="f89b5-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unrestrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="f89b5-130">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="f89b5-130">Request headers</span></span>
<span data-ttu-id="f89b5-131">Name</span><span class="sxs-lookup"><span data-stu-id="f89b5-131">Name</span></span> | <span data-ttu-id="f89b5-132">Typ</span><span class="sxs-lookup"><span data-stu-id="f89b5-132">Type</span></span> | <span data-ttu-id="f89b5-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f89b5-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="f89b5-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="f89b5-134">Authorization</span></span> | <span data-ttu-id="f89b5-135">String</span><span class="sxs-lookup"><span data-stu-id="f89b5-135">String</span></span> | <span data-ttu-id="f89b5-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f89b5-136">Bearer {token}.</span></span> <span data-ttu-id="f89b5-137">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="f89b5-137">**Required**.</span></span>
<span data-ttu-id="f89b5-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="f89b5-138">Content-Type</span></span> | <span data-ttu-id="f89b5-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f89b5-139">string</span></span> | <span data-ttu-id="f89b5-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="f89b5-140">application/json.</span></span> <span data-ttu-id="f89b5-141">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="f89b5-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f89b5-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="f89b5-142">Request body</span></span>
<span data-ttu-id="f89b5-143">Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:</span><span class="sxs-lookup"><span data-stu-id="f89b5-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="f89b5-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="f89b5-144">Parameter</span></span> | <span data-ttu-id="f89b5-145">Typ</span><span class="sxs-lookup"><span data-stu-id="f89b5-145">Type</span></span>    | <span data-ttu-id="f89b5-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f89b5-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="f89b5-147">Kommentar</span><span class="sxs-lookup"><span data-stu-id="f89b5-147">Comment</span></span> |   <span data-ttu-id="f89b5-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f89b5-148">String</span></span> | <span data-ttu-id="f89b5-149">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f89b5-149">Comment to associate with the action.</span></span> <span data-ttu-id="f89b5-150">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="f89b5-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="f89b5-151">Antwort</span><span class="sxs-lookup"><span data-stu-id="f89b5-151">Response</span></span>
<span data-ttu-id="f89b5-152">Bei erfolgreicher Ausführung gibt die Methode den Antwortcode 201 – Erstellt und die [Computeraktion](machineaction.md) im Antworttext zurück.</span><span class="sxs-lookup"><span data-stu-id="f89b5-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="f89b5-153">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f89b5-153">Example</span></span>

<span data-ttu-id="f89b5-154">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="f89b5-154">**Request**</span></span>

<span data-ttu-id="f89b5-155">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="f89b5-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unrestrictCodeExecution 
```

```json
{
  "Comment": "Unrestrict code execution since machine was cleaned and validated"
}

```


<span data-ttu-id="f89b5-156">Informationen zum Einschränken der Codeausführung auf einem Gerät finden Sie unter "Einschränken der [App-Ausführung".](restrict-code-execution.md)</span><span class="sxs-lookup"><span data-stu-id="f89b5-156">To restrict code execution on a device, see [Restrict app execution](restrict-code-execution.md).</span></span>

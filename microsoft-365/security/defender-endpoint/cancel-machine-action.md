---
title: Api zum Abbrechen von Computeraktionen
description: Erfahren Sie, wie Sie eine bereits gestartete Computeraktion abbrechen
keywords: APIs, Graph-API,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879754"
---
#   <a name="cancel-machine-action-api"></a><span data-ttu-id="74a1a-104">Api zum Abbrechen von Computeraktionen</span><span class="sxs-lookup"><span data-stu-id="74a1a-104">Cancel machine action API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="74a1a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="74a1a-105">**Applies to:**</span></span>
- [<span data-ttu-id="74a1a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="74a1a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="74a1a-107">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="74a1a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="74a1a-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="74a1a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="74a1a-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74a1a-109">API description</span></span>

<span data-ttu-id="74a1a-110">Abbrechen einer bereits gestarteten Computeraktion, die sich noch nicht im endgültigen Zustand befindet (abgeschlossen, abgebrochen, fehlgeschlagen).</span><span class="sxs-lookup"><span data-stu-id="74a1a-110">Cancel an already launched machine action that are not yet in final state (completed, cancelled, failed).</span></span>

## <a name="limitations"></a><span data-ttu-id="74a1a-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="74a1a-111">Limitations</span></span>

1.  <span data-ttu-id="74a1a-112">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="74a1a-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="74a1a-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="74a1a-113">Permissions</span></span>

<span data-ttu-id="74a1a-114">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="74a1a-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="74a1a-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter ["Erste Schritte".](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="74a1a-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

|     <span data-ttu-id="74a1a-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="74a1a-116">Permission    type</span></span>     |     <span data-ttu-id="74a1a-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="74a1a-117">Permission</span></span>     |    <span data-ttu-id="74a1a-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="74a1a-118">Permission    display name</span></span>     |
|-|-|-|
|    <br><span data-ttu-id="74a1a-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="74a1a-119">Application</span></span>    |    <br><span data-ttu-id="74a1a-120">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="74a1a-120">Machine.CollectForensic</span></span><br>   <span data-ttu-id="74a1a-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="74a1a-121">Machine.Isolate</span></span>   <br><span data-ttu-id="74a1a-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="74a1a-122">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="74a1a-123">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="74a1a-123">Machine.Scan</span></span><br>   <span data-ttu-id="74a1a-124">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="74a1a-124">Machine.Offboard</span></span><br>   <span data-ttu-id="74a1a-125">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="74a1a-125">Machine.StopAndQuarantine</span></span><br>   <span data-ttu-id="74a1a-126">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="74a1a-126">Machine.LiveResponse</span></span>    |    <span data-ttu-id="74a1a-127">Forensik sammeln</span><span class="sxs-lookup"><span data-stu-id="74a1a-127">Collect   forensics</span></span>   <br><span data-ttu-id="74a1a-128">Computer isolieren</span><span class="sxs-lookup"><span data-stu-id="74a1a-128">Isolate   machine</span></span><br><span data-ttu-id="74a1a-129">Einschränken der Codeausführung</span><span class="sxs-lookup"><span data-stu-id="74a1a-129">Restrict   code execution</span></span><br>  <span data-ttu-id="74a1a-130">Scancomputer</span><span class="sxs-lookup"><span data-stu-id="74a1a-130">Scan   machine</span></span><br>  <span data-ttu-id="74a1a-131">Offboard-Computer</span><span class="sxs-lookup"><span data-stu-id="74a1a-131">Offboard   machine</span></span><br>   <span data-ttu-id="74a1a-132">Beenden und Isolieren</span><span class="sxs-lookup"><span data-stu-id="74a1a-132">Stop And   Quarantine</span></span><br>   <span data-ttu-id="74a1a-133">Ausführen einer Liveantwort auf einem bestimmten Computer</span><span class="sxs-lookup"><span data-stu-id="74a1a-133">Run live   response on a specific machine</span></span>    |
|    <br><span data-ttu-id="74a1a-134">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="74a1a-134">Delegated   (work or school account)</span></span>    |    <span data-ttu-id="74a1a-135">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="74a1a-135">Machine.CollectForensic</span></span><br>   <span data-ttu-id="74a1a-136">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="74a1a-136">Machine.Isolate</span></span>    <br><span data-ttu-id="74a1a-137">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="74a1a-137">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="74a1a-138">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="74a1a-138">Machine.Scan</span></span><br>   <span data-ttu-id="74a1a-139">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="74a1a-139">Machine.Offboard</span></span><br>   <span data-ttu-id="74a1a-140">Machine.StopAndQuarantineMachine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="74a1a-140">Machine.StopAndQuarantineMachine.LiveResponse</span></span>    |    <span data-ttu-id="74a1a-141">Forensik sammeln</span><span class="sxs-lookup"><span data-stu-id="74a1a-141">Collect   forensics</span></span><br>   <span data-ttu-id="74a1a-142">Computer isolieren</span><span class="sxs-lookup"><span data-stu-id="74a1a-142">Isolate   machine</span></span><br>  <span data-ttu-id="74a1a-143">Einschränken der Codeausführung</span><span class="sxs-lookup"><span data-stu-id="74a1a-143">Restrict   code execution</span></span><br> <span data-ttu-id="74a1a-144">Scancomputer</span><span class="sxs-lookup"><span data-stu-id="74a1a-144">Scan   machine</span></span><br><span data-ttu-id="74a1a-145">Offboard-Computer</span><span class="sxs-lookup"><span data-stu-id="74a1a-145">Offboard   machine</span></span><br> <span data-ttu-id="74a1a-146">Beenden und Isolieren</span><span class="sxs-lookup"><span data-stu-id="74a1a-146">Stop And   Quarantine</span></span><br> <span data-ttu-id="74a1a-147">Ausführen einer Liveantwort auf einem bestimmten Computer</span><span class="sxs-lookup"><span data-stu-id="74a1a-147">Run live   response on a specific machine</span></span>    |


## <a name="http-request"></a><span data-ttu-id="74a1a-148">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="74a1a-148">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a><span data-ttu-id="74a1a-149">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="74a1a-149">Request headers</span></span>

| <span data-ttu-id="74a1a-150">Name</span><span class="sxs-lookup"><span data-stu-id="74a1a-150">Name</span></span>      | <span data-ttu-id="74a1a-151">Typ</span><span class="sxs-lookup"><span data-stu-id="74a1a-151">Type</span></span> | <span data-ttu-id="74a1a-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74a1a-152">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="74a1a-153">Authorization</span><span class="sxs-lookup"><span data-stu-id="74a1a-153">Authorization</span></span> | <span data-ttu-id="74a1a-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="74a1a-154">String</span></span>   | <span data-ttu-id="74a1a-p103">Bearer {token}. Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="74a1a-p103">Bearer {token}. Required.</span></span>   |
| <span data-ttu-id="74a1a-157">Content-Type</span><span class="sxs-lookup"><span data-stu-id="74a1a-157">Content-Type</span></span>  | <span data-ttu-id="74a1a-158">string</span><span class="sxs-lookup"><span data-stu-id="74a1a-158">string</span></span>   | <span data-ttu-id="74a1a-p104">application/json. Erforderlich. </span><span class="sxs-lookup"><span data-stu-id="74a1a-p104">application/json. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="74a1a-161">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="74a1a-161">Request body</span></span>

| <span data-ttu-id="74a1a-162">Parameter</span><span class="sxs-lookup"><span data-stu-id="74a1a-162">Parameter</span></span> | <span data-ttu-id="74a1a-163">Typ</span><span class="sxs-lookup"><span data-stu-id="74a1a-163">Type</span></span> | <span data-ttu-id="74a1a-164">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74a1a-164">Description</span></span>                        |
|---------------|----------|----------------------------------------|
| <span data-ttu-id="74a1a-165">Kommentar</span><span class="sxs-lookup"><span data-stu-id="74a1a-165">Comment</span></span>       | <span data-ttu-id="74a1a-166">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="74a1a-166">String</span></span>   | <span data-ttu-id="74a1a-167">Kommentar, der der Abbruchaktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="74a1a-167">Comment to associate with the cancellation action.</span></span>  |

## <a name="response"></a><span data-ttu-id="74a1a-168">Antwort</span><span class="sxs-lookup"><span data-stu-id="74a1a-168">Response</span></span>

<span data-ttu-id="74a1a-169">Bei erfolgreicher Ausführung gibt die Methode den Antwortcode 200,OK mit einer Computeraktionsentität zurück.</span><span class="sxs-lookup"><span data-stu-id="74a1a-169">If successful, this method returns 200, Ok response code with a Machine Action entity.</span></span> <span data-ttu-id="74a1a-170">Wenn die Computeraktionsentität mit der angegebenen ID nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="74a1a-170">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="74a1a-171">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74a1a-171">Example</span></span>

<span data-ttu-id="74a1a-172">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="74a1a-172">**Request**</span></span>

<span data-ttu-id="74a1a-173">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="74a1a-173">Here is an example of the request.</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a><span data-ttu-id="74a1a-174">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="74a1a-174">Related topic</span></span>

- [<span data-ttu-id="74a1a-175">Api für Computeraktionen abrufen</span><span class="sxs-lookup"><span data-stu-id="74a1a-175">Get machine action API</span></span>](get-machineaction-object.md)
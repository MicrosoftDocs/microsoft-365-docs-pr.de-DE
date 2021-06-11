---
title: Ausführen von Liveantwortbefehlen auf einem Gerät
description: Erfahren Sie, wie Sie eine Sequenz von Liveantwortbefehlen auf einem Gerät ausführen.
keywords: APIs, Graph-API, unterstützte APIs, in Bibliothek hochladen
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
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879700"
---
#  <a name="run-live-response-commands-on-a-device"></a><span data-ttu-id="e36fb-104">Ausführen von Liveantwortbefehlen auf einem Gerät</span><span class="sxs-lookup"><span data-stu-id="e36fb-104">Run live response commands on a device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e36fb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e36fb-105">**Applies to:**</span></span>
- [<span data-ttu-id="e36fb-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e36fb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="e36fb-107">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="e36fb-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e36fb-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e36fb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="e36fb-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e36fb-109">API description</span></span>

<span data-ttu-id="e36fb-110">Führt eine Sequenz von Liveantwortbefehlen auf einem Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="e36fb-110">Runs a sequence of live response commands on a device</span></span>

## <a name="limitations"></a><span data-ttu-id="e36fb-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e36fb-111">Limitations</span></span>

1.  <span data-ttu-id="e36fb-112">Die Rateneinschränkungen für diese API sind 10 Aufrufe pro Minute (zusätzliche Anforderungen werden mit HTTP 429 beantwortet).</span><span class="sxs-lookup"><span data-stu-id="e36fb-112">Rate limitations for this API are 10 calls per minute (additional requests are responded with HTTP 429).</span></span>

2.  <span data-ttu-id="e36fb-113">25 gleichzeitig ausgeführte Sitzungen (Anforderungen, die den Einschränkungsgrenzwert überschreiten, erhalten die Antwort "429 – zu viele Anforderungen").</span><span class="sxs-lookup"><span data-stu-id="e36fb-113">25 concurrently running sessions (requests exceeding the throttling limit will receive a "429 - Too many requests" response).</span></span>

3.  <span data-ttu-id="e36fb-114">Wenn der Computer nicht verfügbar ist, wird die Sitzung bis zu 3 Tage lang in die Warteschlange gestellt.</span><span class="sxs-lookup"><span data-stu-id="e36fb-114">If the machine is not available, the session will be queued for up to 3 days.</span></span>

4.  <span data-ttu-id="e36fb-115">Timeouts für RunScript-Befehle nach 10 Minuten.</span><span class="sxs-lookup"><span data-stu-id="e36fb-115">RunScript command timeouts after 10 minutes.</span></span>

5.  <span data-ttu-id="e36fb-116">Wenn ein Liveantwortbefehl fehlschlägt, werden nicht alle ausgeführten Aktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e36fb-116">When a live response command fails all followed actions will not be executed.</span></span>

## <a name="permissions"></a><span data-ttu-id="e36fb-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e36fb-117">Permissions</span></span>

<span data-ttu-id="e36fb-118">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e36fb-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e36fb-119">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter ["Erste Schritte".](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e36fb-119">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="e36fb-120">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="e36fb-120">Permission type</span></span>                    | <span data-ttu-id="e36fb-121">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e36fb-121">Permission</span></span>           | <span data-ttu-id="e36fb-122">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e36fb-122">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="e36fb-123">Anwendung</span><span class="sxs-lookup"><span data-stu-id="e36fb-123">Application</span></span>                        | <span data-ttu-id="e36fb-124">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="e36fb-124">Machine.LiveResponse</span></span> | <span data-ttu-id="e36fb-125">Ausführen einer Liveantwort auf einem bestimmten Computer</span><span class="sxs-lookup"><span data-stu-id="e36fb-125">Run live response on a specific machine</span></span> |
| <span data-ttu-id="e36fb-126">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="e36fb-126">Delegated (work or school account)</span></span> | <span data-ttu-id="e36fb-127">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="e36fb-127">Machine.LiveResponse</span></span> | <span data-ttu-id="e36fb-128">Ausführen einer Liveantwort auf einem bestimmten Computer</span><span class="sxs-lookup"><span data-stu-id="e36fb-128">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="e36fb-129">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="e36fb-129">HTTP request</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a><span data-ttu-id="e36fb-130">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="e36fb-130">Request headers</span></span>

| <span data-ttu-id="e36fb-131">Name</span><span class="sxs-lookup"><span data-stu-id="e36fb-131">Name</span></span>      | <span data-ttu-id="e36fb-132">Typ</span><span class="sxs-lookup"><span data-stu-id="e36fb-132">Type</span></span> | <span data-ttu-id="e36fb-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e36fb-133">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="e36fb-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="e36fb-134">Authorization</span></span> | <span data-ttu-id="e36fb-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e36fb-135">String</span></span>   | <span data-ttu-id="e36fb-136">Inhaber\<token>\.</span><span class="sxs-lookup"><span data-stu-id="e36fb-136">Bearer\<token>\.</span></span> <span data-ttu-id="e36fb-137">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e36fb-137">Required.</span></span>   |
| <span data-ttu-id="e36fb-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e36fb-138">Content-Type</span></span>  | <span data-ttu-id="e36fb-139">string</span><span class="sxs-lookup"><span data-stu-id="e36fb-139">string</span></span>   | <span data-ttu-id="e36fb-p104">application/json. Erforderlich. </span><span class="sxs-lookup"><span data-stu-id="e36fb-p104">application/json. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="e36fb-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="e36fb-142">Request body</span></span>

| <span data-ttu-id="e36fb-143">Parameter</span><span class="sxs-lookup"><span data-stu-id="e36fb-143">Parameter</span></span> | <span data-ttu-id="e36fb-144">Typ</span><span class="sxs-lookup"><span data-stu-id="e36fb-144">Type</span></span> | <span data-ttu-id="e36fb-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e36fb-145">Description</span></span>                                                        |
|---------------|----------|------------------------------------------------------------------------|
| <span data-ttu-id="e36fb-146">Kommentar</span><span class="sxs-lookup"><span data-stu-id="e36fb-146">Comment</span></span>       | <span data-ttu-id="e36fb-147">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e36fb-147">String</span></span>   | <span data-ttu-id="e36fb-148">Kommentar, der der Aktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e36fb-148">Comment to associate with the action.</span></span>                                 |
| <span data-ttu-id="e36fb-149">Befehle</span><span class="sxs-lookup"><span data-stu-id="e36fb-149">Commands</span></span>      | <span data-ttu-id="e36fb-150">Array</span><span class="sxs-lookup"><span data-stu-id="e36fb-150">Array</span></span>    | <span data-ttu-id="e36fb-151">Auszuführende Befehle.</span><span class="sxs-lookup"><span data-stu-id="e36fb-151">Commands to run.</span></span> <span data-ttu-id="e36fb-152">Zulässige Werte sind PutFile, RunScript, GetFile.</span><span class="sxs-lookup"><span data-stu-id="e36fb-152">Allowed values are PutFile, RunScript, GetFile.</span></span> |

<span data-ttu-id="e36fb-153">Befehle:</span><span class="sxs-lookup"><span data-stu-id="e36fb-153">Commands:</span></span>

| <span data-ttu-id="e36fb-154">Befehlstyp</span><span class="sxs-lookup"><span data-stu-id="e36fb-154">Command Type</span></span> | <span data-ttu-id="e36fb-155">Parameter</span><span class="sxs-lookup"><span data-stu-id="e36fb-155">Parameters</span></span>                                                                          | <span data-ttu-id="e36fb-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e36fb-156">Description</span></span>                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e36fb-157">Putfile</span><span class="sxs-lookup"><span data-stu-id="e36fb-157">PutFile</span></span>      | <span data-ttu-id="e36fb-158">Schlüssel: FileName</span><span class="sxs-lookup"><span data-stu-id="e36fb-158">Key: FileName</span></span>  <br><br>  <span data-ttu-id="e36fb-159">Wert: \<file name\></span><span class="sxs-lookup"><span data-stu-id="e36fb-159">Value: \<file name\></span></span>                                                                          | <span data-ttu-id="e36fb-160">Platziert eine Datei aus der Bibliothek auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="e36fb-160">Puts a file from the library to the device.</span></span> <span data-ttu-id="e36fb-161">Dateien werden in einem Arbeitsordner gespeichert und gelöscht, wenn das Gerät standardmäßig neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="e36fb-161">Files are saved in a working folder and are deleted when the device restarts by default.</span></span>
| <span data-ttu-id="e36fb-162">RunScript</span><span class="sxs-lookup"><span data-stu-id="e36fb-162">RunScript</span></span>    | <span data-ttu-id="e36fb-163">Schlüssel: ScriptName</span><span class="sxs-lookup"><span data-stu-id="e36fb-163">Key: ScriptName</span></span><br><span data-ttu-id="e36fb-164">Wert: \<Script from library\></span><span class="sxs-lookup"><span data-stu-id="e36fb-164">Value: \<Script from library\></span></span> <br><br> <span data-ttu-id="e36fb-165">Schlüssel: Args</span><span class="sxs-lookup"><span data-stu-id="e36fb-165">Key: Args</span></span>  <br> <span data-ttu-id="e36fb-166">Wert: \<Script arguments\></span><span class="sxs-lookup"><span data-stu-id="e36fb-166">Value: \<Script arguments\></span></span>                          | <span data-ttu-id="e36fb-167">Führt ein Skript aus der Bibliothek auf einem Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="e36fb-167">Runs a script from the library on a device.</span></span>    <br><br>  <span data-ttu-id="e36fb-168">Der Args-Parameter wird an Ihr Skript übergeben.</span><span class="sxs-lookup"><span data-stu-id="e36fb-168">The Args parameter is passed to your script.</span></span> <br><br> <span data-ttu-id="e36fb-169">Timeouts nach 10 Minuten.</span><span class="sxs-lookup"><span data-stu-id="e36fb-169">Timeouts after 10 minutes.</span></span>     
| <span data-ttu-id="e36fb-170">GetFile</span><span class="sxs-lookup"><span data-stu-id="e36fb-170">GetFile</span></span>      | <span data-ttu-id="e36fb-171">Schlüssel: Pfad</span><span class="sxs-lookup"><span data-stu-id="e36fb-171">Key: Path</span></span> <br> <span data-ttu-id="e36fb-172">Wert: \<File path\></span><span class="sxs-lookup"><span data-stu-id="e36fb-172">Value: \<File path\></span></span>                                                        | <span data-ttu-id="e36fb-173">Datei von einem Gerät erfassen.</span><span class="sxs-lookup"><span data-stu-id="e36fb-173">Collect file from a device.</span></span> <span data-ttu-id="e36fb-174">HINWEIS: Umgekehrte Schrägstriche im Pfad müssen escaped sein.</span><span class="sxs-lookup"><span data-stu-id="e36fb-174">NOTE: Backslashes in path must be escaped.</span></span>                                                                      |

## <a name="response"></a><span data-ttu-id="e36fb-175">Antwort</span><span class="sxs-lookup"><span data-stu-id="e36fb-175">Response</span></span>

-   <span data-ttu-id="e36fb-176">Wenn die Methode erfolgreich ist, wird "200, Ok" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e36fb-176">If successful, this method returns 200, Ok.</span></span>
    <span data-ttu-id="e36fb-177">Aktionsentität.</span><span class="sxs-lookup"><span data-stu-id="e36fb-177">Action entity.</span></span> <span data-ttu-id="e36fb-178">Wenn der Computer mit der angegebenen ID nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="e36fb-178">If machine with the specified ID was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="e36fb-179">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e36fb-179">Example</span></span>

<span data-ttu-id="e36fb-180">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="e36fb-180">**Request**</span></span>

<span data-ttu-id="e36fb-181">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="e36fb-181">Here is an example of the request.</span></span>

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
<span data-ttu-id="e36fb-182">**Json**</span><span class="sxs-lookup"><span data-stu-id="e36fb-182">**JSON**</span></span>

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

<span data-ttu-id="e36fb-183">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="e36fb-183">**Response**</span></span>

<span data-ttu-id="e36fb-184">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="e36fb-184">Here is an example of the response.</span></span>

```HTTP
HTTP/1.1 200 Ok
```

<span data-ttu-id="e36fb-185">Inhaltstyp: application/json</span><span class="sxs-lookup"><span data-stu-id="e36fb-185">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a><span data-ttu-id="e36fb-186">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e36fb-186">Related topics</span></span>
- [<span data-ttu-id="e36fb-187">Api für Computeraktionen abrufen</span><span class="sxs-lookup"><span data-stu-id="e36fb-187">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="e36fb-188">Abrufen des Ergebnisses der Liveantwort</span><span class="sxs-lookup"><span data-stu-id="e36fb-188">Get live response result</span></span>](get-live-response-result.md)
- [<span data-ttu-id="e36fb-189">Computeraktion abbrechen</span><span class="sxs-lookup"><span data-stu-id="e36fb-189">Cancel machine action</span></span>](cancel-machine-action.md)

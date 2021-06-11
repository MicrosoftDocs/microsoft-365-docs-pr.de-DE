---
title: Abrufen von Liveantwortergebnissen
description: Erfahren Sie, wie Sie ein bestimmtes Ergebnis eines Liveantwortbefehls anhand des Index abrufen.
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
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879733"
---
#  <a name="get-live-response-results"></a><span data-ttu-id="86a65-104">Abrufen von Liveantwortergebnissen</span><span class="sxs-lookup"><span data-stu-id="86a65-104">Get live response results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="86a65-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="86a65-105">**Applies to:**</span></span>
- [<span data-ttu-id="86a65-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="86a65-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="86a65-107">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="86a65-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="86a65-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="86a65-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="86a65-109">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86a65-109">API description</span></span>

<span data-ttu-id="86a65-110">Ruft ein bestimmtes Ergebnis des Liveantwortbefehls anhand seines Index ab.</span><span class="sxs-lookup"><span data-stu-id="86a65-110">Retrieves a specific live response command result by its index.</span></span>

## <a name="limitations"></a><span data-ttu-id="86a65-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="86a65-111">Limitations</span></span>

1.  <span data-ttu-id="86a65-112">Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="86a65-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="86a65-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="86a65-113">Permissions</span></span>

<span data-ttu-id="86a65-114">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="86a65-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="86a65-115">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter ["Erste Schritte".](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="86a65-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="86a65-116">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="86a65-116">Permission type</span></span>                    | <span data-ttu-id="86a65-117">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="86a65-117">Permission</span></span>           | <span data-ttu-id="86a65-118">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="86a65-118">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="86a65-119">Anwendung</span><span class="sxs-lookup"><span data-stu-id="86a65-119">Application</span></span>                        | <span data-ttu-id="86a65-120">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="86a65-120">Machine.LiveResponse</span></span> | <span data-ttu-id="86a65-121">Ausführen einer Liveantwort auf einem bestimmten Computer</span><span class="sxs-lookup"><span data-stu-id="86a65-121">Run live response on a specific machine</span></span> |
| <span data-ttu-id="86a65-122">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="86a65-122">Delegated (work or school account)</span></span> | <span data-ttu-id="86a65-123">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="86a65-123">Machine.LiveResponse</span></span> | <span data-ttu-id="86a65-124">Ausführen einer Liveantwort auf einem bestimmten Computer</span><span class="sxs-lookup"><span data-stu-id="86a65-124">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="86a65-125">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="86a65-125">HTTP request</span></span>

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a><span data-ttu-id="86a65-126">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="86a65-126">Request headers</span></span>

| <span data-ttu-id="86a65-127">Name</span><span class="sxs-lookup"><span data-stu-id="86a65-127">Name</span></span>      | <span data-ttu-id="86a65-128">Typ</span><span class="sxs-lookup"><span data-stu-id="86a65-128">Type</span></span> | <span data-ttu-id="86a65-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86a65-129">Description</span></span>               |
|---------------|----------|-------------------------------|
| <span data-ttu-id="86a65-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="86a65-130">Authorization</span></span> | <span data-ttu-id="86a65-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="86a65-131">String</span></span>   | <span data-ttu-id="86a65-p103">Bearer {token}. Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="86a65-p103">Bearer {token}. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="86a65-134">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="86a65-134">Request body</span></span>

<span data-ttu-id="86a65-135">Empty</span><span class="sxs-lookup"><span data-stu-id="86a65-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="86a65-136">Antwort</span><span class="sxs-lookup"><span data-stu-id="86a65-136">Response</span></span>

<span data-ttu-id="86a65-137">Bei erfolgreicher Ausführung gibt die Methode den Antwortcode 200,Ok mit dem Objekt zurück, das den Link zum Befehlsergebnis in der *Werteigenschaft* enthält.</span><span class="sxs-lookup"><span data-stu-id="86a65-137">If successful, this method returns 200, Ok response code with object that holds the link to the command result in the *value* property.</span></span> <span data-ttu-id="86a65-138">Dieser Link ist 30 Minuten gültig und sollte sofort zum Herunterladen des Pakets in einen lokalen Speicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="86a65-138">This link is valid for 30 minutes and should be used immediately for downloading the package to a local storage.</span></span> <span data-ttu-id="86a65-139">Ein abgelaufener Link kann durch einen anderen Anruf neu erstellt werden, und es ist nicht erforderlich, die Liveantwort erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="86a65-139">An expired link can be re-created by another call, and there is no need to run live response again.</span></span>

<span data-ttu-id="86a65-140">*Runscript-Transkripteigenschaften:*</span><span class="sxs-lookup"><span data-stu-id="86a65-140">*Runscript transcript properties:*</span></span>

| <span data-ttu-id="86a65-141">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="86a65-141">Property</span></span>  | <span data-ttu-id="86a65-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86a65-142">Description</span></span>                       |
|---------------|---------------------------------------|
| <span data-ttu-id="86a65-143">name</span><span class="sxs-lookup"><span data-stu-id="86a65-143">name</span></span>          | <span data-ttu-id="86a65-144">Name des ausgeführten Skripts</span><span class="sxs-lookup"><span data-stu-id="86a65-144">Executed script name</span></span>                  |
| <span data-ttu-id="86a65-145">exit_code</span><span class="sxs-lookup"><span data-stu-id="86a65-145">exit_code</span></span>     | <span data-ttu-id="86a65-146">Ausführungsskript-Exitcode</span><span class="sxs-lookup"><span data-stu-id="86a65-146">Executed script exit code</span></span>             |
| <span data-ttu-id="86a65-147">script_output</span><span class="sxs-lookup"><span data-stu-id="86a65-147">script_output</span></span> | <span data-ttu-id="86a65-148">Standardausgabe für ausgeführte Skripts</span><span class="sxs-lookup"><span data-stu-id="86a65-148">Executed script standard output</span></span>       |
| <span data-ttu-id="86a65-149">script_error</span><span class="sxs-lookup"><span data-stu-id="86a65-149">script_error</span></span>  | <span data-ttu-id="86a65-150">Ausführung der Standardfehlerausgabe für Skripts</span><span class="sxs-lookup"><span data-stu-id="86a65-150">Executed script standard error output</span></span> |

## <a name="example"></a><span data-ttu-id="86a65-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86a65-151">Example</span></span>

<span data-ttu-id="86a65-152">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="86a65-152">**Request**</span></span>

<span data-ttu-id="86a65-153">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="86a65-153">Here is an example of the request.</span></span>

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

<span data-ttu-id="86a65-154">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="86a65-154">**Response**</span></span>

<span data-ttu-id="86a65-155">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="86a65-155">Here is an example of the response.</span></span>

<span data-ttu-id="86a65-156">HTTP/1.1 200 Ok</span><span class="sxs-lookup"><span data-stu-id="86a65-156">HTTP/1.1 200 Ok</span></span>

<span data-ttu-id="86a65-157">Inhaltstyp: application/json</span><span class="sxs-lookup"><span data-stu-id="86a65-157">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

<span data-ttu-id="86a65-158">*Dateiinhalt:*</span><span class="sxs-lookup"><span data-stu-id="86a65-158">*File content:*</span></span> 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a><span data-ttu-id="86a65-159">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="86a65-159">Related topics</span></span>

- [<span data-ttu-id="86a65-160">Api für Computeraktionen abrufen</span><span class="sxs-lookup"><span data-stu-id="86a65-160">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="86a65-161">Computeraktion abbrechen</span><span class="sxs-lookup"><span data-stu-id="86a65-161">Cancel machine action</span></span>](cancel-machine-action.md)
- [<span data-ttu-id="86a65-162">Ausführen einer Liveantwort</span><span class="sxs-lookup"><span data-stu-id="86a65-162">Run live response</span></span>](run-live-response.md) 

---
title: Erweiterte Suche-API
ms.reviewer: ''
description: Erfahren Sie, wie Sie die API für die erweiterte Suche verwenden, um erweiterte Abfragen auf Microsoft Defender für Endpunkt auszuführen. Informieren Sie sich über Einschränkungen, und sehen Sie sich ein Beispiel an.
keywords: APIs, unterstützte APIs, erweiterte Suche, Abfrage
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
ms.openlocfilehash: 0173e271967a1b5b18d69713e9e6540e9cd11a87
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772401"
---
# <a name="advanced-hunting-api"></a><span data-ttu-id="e4edd-105">API für die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="e4edd-105">Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e4edd-106">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e4edd-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="e4edd-107">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="e4edd-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e4edd-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e4edd-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a><span data-ttu-id="e4edd-109">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="e4edd-109">Limitations</span></span>

1. <span data-ttu-id="e4edd-110">Sie können nur eine Abfrage für Daten aus den letzten 30 Tagen ausführen.</span><span class="sxs-lookup"><span data-stu-id="e4edd-110">You can only run a query on data from the last 30 days.</span></span>

2. <span data-ttu-id="e4edd-111">Die Ergebnisse umfassen maximal 100.000 Zeilen.</span><span class="sxs-lookup"><span data-stu-id="e4edd-111">The results will include a maximum of 100,000 rows.</span></span>

3. <span data-ttu-id="e4edd-112">Die Anzahl der Ausführungen ist pro Mandant begrenzt:</span><span class="sxs-lookup"><span data-stu-id="e4edd-112">The number of executions is limited per tenant:</span></span>
   - <span data-ttu-id="e4edd-113">API-Aufrufe: bis zu 45 Aufrufe pro Minute, bis zu 1500 Aufrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="e4edd-113">API calls: Up to 45 calls per minute, up to 1500 calls per hour.</span></span>
   - <span data-ttu-id="e4edd-114">Ausführungszeit: 10 Minuten Laufzeit pro Stunde und 3 Stunden Laufzeit pro Tag.</span><span class="sxs-lookup"><span data-stu-id="e4edd-114">Execution time: 10 minutes of running time every hour and 3 hours of running time a day.</span></span>

4. <span data-ttu-id="e4edd-115">Die maximale Ausführungszeit einer einzelnen Anforderung beträgt 10 Minuten.</span><span class="sxs-lookup"><span data-stu-id="e4edd-115">The maximal execution time of a single request is 10 minutes.</span></span>

5. <span data-ttu-id="e4edd-116">429-Antworten stellen das Erreichen des Kontingentlimits entweder nach Anzahl der Anforderungen oder nach CPU dar.</span><span class="sxs-lookup"><span data-stu-id="e4edd-116">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="e4edd-117">Lesen Sie den Antworttext, um zu verstehen, welcher Grenzwert erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="e4edd-117">Read response body to understand what limit has been reached.</span></span> 

## <a name="permissions"></a><span data-ttu-id="e4edd-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e4edd-118">Permissions</span></span>

<span data-ttu-id="e4edd-119">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e4edd-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e4edd-120">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e4edd-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e4edd-121">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="e4edd-121">Permission type</span></span> |   <span data-ttu-id="e4edd-122">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e4edd-122">Permission</span></span>  |   <span data-ttu-id="e4edd-123">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="e4edd-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e4edd-124">Anwendung</span><span class="sxs-lookup"><span data-stu-id="e4edd-124">Application</span></span> |   <span data-ttu-id="e4edd-125">AdvancedQuery.Read.All</span><span class="sxs-lookup"><span data-stu-id="e4edd-125">AdvancedQuery.Read.All</span></span> |    <span data-ttu-id="e4edd-126">"Ausführen erweiterter Abfragen"</span><span class="sxs-lookup"><span data-stu-id="e4edd-126">'Run advanced queries'</span></span>
<span data-ttu-id="e4edd-127">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="e4edd-127">Delegated (work or school account)</span></span> | <span data-ttu-id="e4edd-128">AdvancedQuery.Read</span><span class="sxs-lookup"><span data-stu-id="e4edd-128">AdvancedQuery.Read</span></span> | <span data-ttu-id="e4edd-129">"Ausführen erweiterter Abfragen"</span><span class="sxs-lookup"><span data-stu-id="e4edd-129">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="e4edd-130">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="e4edd-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e4edd-131">Der Benutzer muss über die AD-Rolle "Daten anzeigen" verfügen.</span><span class="sxs-lookup"><span data-stu-id="e4edd-131">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="e4edd-132">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="e4edd-132">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e4edd-133">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="e4edd-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a><span data-ttu-id="e4edd-134">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="e4edd-134">Request headers</span></span>

<span data-ttu-id="e4edd-135">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="e4edd-135">Header</span></span> | <span data-ttu-id="e4edd-136">Wert</span><span class="sxs-lookup"><span data-stu-id="e4edd-136">Value</span></span> 
:---|:---
<span data-ttu-id="e4edd-137">Authorization</span><span class="sxs-lookup"><span data-stu-id="e4edd-137">Authorization</span></span> | <span data-ttu-id="e4edd-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e4edd-138">Bearer {token}.</span></span> <span data-ttu-id="e4edd-139">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="e4edd-139">**Required**.</span></span>
<span data-ttu-id="e4edd-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e4edd-140">Content-Type</span></span>    | <span data-ttu-id="e4edd-141">application/json</span><span class="sxs-lookup"><span data-stu-id="e4edd-141">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="e4edd-142">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="e4edd-142">Request body</span></span>

<span data-ttu-id="e4edd-143">Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:</span><span class="sxs-lookup"><span data-stu-id="e4edd-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="e4edd-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4edd-144">Parameter</span></span> | <span data-ttu-id="e4edd-145">Typ</span><span class="sxs-lookup"><span data-stu-id="e4edd-145">Type</span></span>    | <span data-ttu-id="e4edd-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4edd-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="e4edd-147">Abfrage</span><span class="sxs-lookup"><span data-stu-id="e4edd-147">Query</span></span> | <span data-ttu-id="e4edd-148">Text</span><span class="sxs-lookup"><span data-stu-id="e4edd-148">Text</span></span> |  <span data-ttu-id="e4edd-149">Die auszuführende Abfrage.</span><span class="sxs-lookup"><span data-stu-id="e4edd-149">The query to run.</span></span> <span data-ttu-id="e4edd-150">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="e4edd-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="e4edd-151">Antwort</span><span class="sxs-lookup"><span data-stu-id="e4edd-151">Response</span></span>

<span data-ttu-id="e4edd-152">Bei erfolgreicher Ausführung gibt die Methode das Objekt 200 OK und das _QueryResponse-Objekt_ im Antworttext zurück.</span><span class="sxs-lookup"><span data-stu-id="e4edd-152">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="e4edd-153">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4edd-153">Example</span></span>

##### <a name="request"></a><span data-ttu-id="e4edd-154">Anforderung</span><span class="sxs-lookup"><span data-stu-id="e4edd-154">Request</span></span>

<span data-ttu-id="e4edd-155">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="e4edd-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

##### <a name="response"></a><span data-ttu-id="e4edd-156">Antwort</span><span class="sxs-lookup"><span data-stu-id="e4edd-156">Response</span></span>

<span data-ttu-id="e4edd-157">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="e4edd-157">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="e4edd-158">Das hier gezeigte Antwortobjekt ist möglicherweise aus Platzgründen abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="e4edd-158">The response object shown here may be truncated for brevity.</span></span> <span data-ttu-id="e4edd-159">Von einem tatsächlichen Aufruf werden alle Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e4edd-159">All of the properties will be returned from an actual call.</span></span>

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="e4edd-160">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e4edd-160">Related topics</span></span>

- [<span data-ttu-id="e4edd-161">Einführung in microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="e4edd-161">Microsoft Defender for Endpoint APIs introduction</span></span>](apis-intro.md)
- [<span data-ttu-id="e4edd-162">Erweiterte Suche über das Portal</span><span class="sxs-lookup"><span data-stu-id="e4edd-162">Advanced Hunting from Portal</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e4edd-163">Erweiterte Bedrohungssuche mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4edd-163">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)

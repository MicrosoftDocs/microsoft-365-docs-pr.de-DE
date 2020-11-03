---
title: Erweiterte Jagd-APIs
description: Erfahren Sie, wie Sie erweiterte Jagd Abfragen mit der Microsoft 365 Defender-API ausführen.
keywords: Erweiterte Suche, APIs, API, MTP
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c43d263009578af6280ffdc780ab0f9a174a3b97
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844032"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="c5087-104">Erweiterte Jagd-APIs</span><span class="sxs-lookup"><span data-stu-id="c5087-104">Advanced hunting APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c5087-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c5087-105">**Applies to:**</span></span>
- <span data-ttu-id="c5087-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5087-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="c5087-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="c5087-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c5087-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="c5087-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="c5087-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c5087-109">Limitations</span></span>
1. <span data-ttu-id="c5087-110">Sie können nur eine Abfrage für Daten der letzten 30 Tage ausführen.</span><span class="sxs-lookup"><span data-stu-id="c5087-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="c5087-111">Die Ergebnisse umfassen maximal 100.000 Zeilen.</span><span class="sxs-lookup"><span data-stu-id="c5087-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="c5087-112">Die Anzahl der Ausführungen ist pro Mandanten limitiert: bis zu 10 Anrufe pro Minute, 10 Minuten Spielzeit stündlich und 4 Stunden Spielzeit pro Tag.</span><span class="sxs-lookup"><span data-stu-id="c5087-112">The number of executions is limited per tenant: up to 10 calls per minute, 10 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="c5087-113">Die maximale Ausführungszeit einer einzelnen Anforderung beträgt 10 Minuten.</span><span class="sxs-lookup"><span data-stu-id="c5087-113">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="c5087-114">429 Antwort stellt eine erreichende Kontingentgrenze nach der Anzahl der Anforderungen oder der CPU dar.</span><span class="sxs-lookup"><span data-stu-id="c5087-114">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="c5087-115">Der 429-Antworttext gibt auch die Zeit an, bis das Kontingent erneuert wird.</span><span class="sxs-lookup"><span data-stu-id="c5087-115">The 429 response body will also indicate the time until the quota is renewed.</span></span> 


## <a name="permissions"></a><span data-ttu-id="c5087-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c5087-116">Permissions</span></span>
<span data-ttu-id="c5087-117">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c5087-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c5087-118">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="c5087-118">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="c5087-119">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="c5087-119">Permission type</span></span> |   <span data-ttu-id="c5087-120">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c5087-120">Permission</span></span>  |   <span data-ttu-id="c5087-121">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c5087-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c5087-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="c5087-122">Application</span></span> |   <span data-ttu-id="c5087-123">AdvancedHunting. Read. all</span><span class="sxs-lookup"><span data-stu-id="c5087-123">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="c5087-124">' Erweiterte Abfragen ausführen '</span><span class="sxs-lookup"><span data-stu-id="c5087-124">'Run advanced queries'</span></span>
<span data-ttu-id="c5087-125">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="c5087-125">Delegated (work or school account)</span></span> | <span data-ttu-id="c5087-126">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="c5087-126">AdvancedHunting.Read</span></span> | <span data-ttu-id="c5087-127">' Erweiterte Abfragen ausführen '</span><span class="sxs-lookup"><span data-stu-id="c5087-127">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="c5087-128">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="c5087-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c5087-129">Der Benutzer muss über die AD-Rolle "Daten anzeigen" verfügen.</span><span class="sxs-lookup"><span data-stu-id="c5087-129">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="c5087-130">Der Benutzer muss auf dem Gerät basierend auf Gerätegruppen Einstellungen Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="c5087-130">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="c5087-131">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="c5087-131">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="c5087-132">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="c5087-132">Request headers</span></span>

<span data-ttu-id="c5087-133">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="c5087-133">Header</span></span> | <span data-ttu-id="c5087-134">Wert</span><span class="sxs-lookup"><span data-stu-id="c5087-134">Value</span></span> 
:---|:---
<span data-ttu-id="c5087-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="c5087-135">Authorization</span></span> | <span data-ttu-id="c5087-136">Bearer {Token}.</span><span class="sxs-lookup"><span data-stu-id="c5087-136">Bearer {token}.</span></span> <span data-ttu-id="c5087-137">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="c5087-137">**Required**.</span></span>
<span data-ttu-id="c5087-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c5087-138">Content-Type</span></span>    | <span data-ttu-id="c5087-139">application/json</span><span class="sxs-lookup"><span data-stu-id="c5087-139">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="c5087-140">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="c5087-140">Request body</span></span>
<span data-ttu-id="c5087-141">Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:</span><span class="sxs-lookup"><span data-stu-id="c5087-141">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c5087-142">Parameter</span><span class="sxs-lookup"><span data-stu-id="c5087-142">Parameter</span></span> | <span data-ttu-id="c5087-143">Typ</span><span class="sxs-lookup"><span data-stu-id="c5087-143">Type</span></span>    | <span data-ttu-id="c5087-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5087-144">Description</span></span>
:---|:---|:---
<span data-ttu-id="c5087-145">Abfrage</span><span class="sxs-lookup"><span data-stu-id="c5087-145">Query</span></span> | <span data-ttu-id="c5087-146">Text</span><span class="sxs-lookup"><span data-stu-id="c5087-146">Text</span></span> |  <span data-ttu-id="c5087-147">Die auszuführende Abfrage.</span><span class="sxs-lookup"><span data-stu-id="c5087-147">The query to run.</span></span> <span data-ttu-id="c5087-148">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="c5087-148">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="c5087-149">Antwort</span><span class="sxs-lookup"><span data-stu-id="c5087-149">Response</span></span>
<span data-ttu-id="c5087-150">Wenn die Methode erfolgreich verläuft, werden 200 OK und das _QueryResponse_ -Objekt im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c5087-150">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="c5087-151">Das Response-Objekt wird in drei Teile (Eigenschaften) aufgeteilt:</span><span class="sxs-lookup"><span data-stu-id="c5087-151">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="c5087-152">```Stats``` -Abfrage Leistungsstatistiken.</span><span class="sxs-lookup"><span data-stu-id="c5087-152">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="c5087-153">```Schema``` – Das Schema der Antwort, eine Liste mit Name-Type-Paaren für jede Spalte.</span><span class="sxs-lookup"><span data-stu-id="c5087-153">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="c5087-154">```Results``` -Eine Liste erweiterter Jagd Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="c5087-154">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="c5087-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5087-155">Example</span></span>

<span data-ttu-id="c5087-156">Anforderung</span><span class="sxs-lookup"><span data-stu-id="c5087-156">Request</span></span>

<span data-ttu-id="c5087-157">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="c5087-157">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="c5087-158">Antwort</span><span class="sxs-lookup"><span data-stu-id="c5087-158">Response</span></span>

<span data-ttu-id="c5087-159">Nachfolgend sehen Sie ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="c5087-159">Here is an example of the response.</span></span>


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
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
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a><span data-ttu-id="c5087-160">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="c5087-160">Related topic</span></span>
- [<span data-ttu-id="c5087-161">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="c5087-161">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)

---
title: Microsoft 365 Defender advanced hunting API
description: Erfahren Sie, wie Sie Abfragen für die erweiterte Suche mit der Api für die erweiterte Suche von Microsoft 365 Defender ausführen.
keywords: Erweiterte Suche, APIs, API, MTP, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 99f39a10de6231a72220c5c2a90ec915b1a4e44a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988116"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="c0253-104">Microsoft 365 Defender Advanced hunting API</span><span class="sxs-lookup"><span data-stu-id="c0253-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c0253-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c0253-105">**Applies to:**</span></span>

- <span data-ttu-id="c0253-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c0253-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0253-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="c0253-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c0253-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="c0253-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c0253-109">[Die erweiterte Suche](advanced-hunting-overview.md) ist ein Tool zur [Bedrohungssuche,](advanced-hunting-query-language.md) das speziell konstruierte Abfragen verwendet, um die Ereignisdaten der letzten 30 Tage in Microsoft 365 Defender zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="c0253-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="c0253-110">Sie können erweiterte Suchabfragen verwenden, um ungewöhnliche Aktivitäten zu untersuchen, mögliche Bedrohungen zu erkennen und sogar auf Angriffe zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="c0253-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="c0253-111">Mit der API für die erweiterte Suche können Sie Ereignisdaten programmgesteuert abfragen.</span><span class="sxs-lookup"><span data-stu-id="c0253-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="c0253-112">Kontingente und Ressourcenzuordnung</span><span class="sxs-lookup"><span data-stu-id="c0253-112">Quotas and resource allocation</span></span>

<span data-ttu-id="c0253-113">Die folgenden Bedingungen beziehen sich auf alle Abfragen.</span><span class="sxs-lookup"><span data-stu-id="c0253-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="c0253-114">Abfragen untersuchen und geben Daten aus den letzten 30 Tagen zurück.</span><span class="sxs-lookup"><span data-stu-id="c0253-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="c0253-115">Ergebnisse können bis zu 100.000 Zeilen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c0253-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="c0253-116">Sie können bis zu 15 Anrufe pro Minute und Mandant erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0253-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="c0253-117">Sie haben 10 Minuten Ausführungszeit pro Stunde und Mandant.</span><span class="sxs-lookup"><span data-stu-id="c0253-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="c0253-118">Sie haben insgesamt vier Stunden Laufzeit pro Tag und Mandant.</span><span class="sxs-lookup"><span data-stu-id="c0253-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="c0253-119">Wenn eine einzelne Anforderung länger als 10 Minuten ausgeführt wird, tritt ein Zeitfehler auf und es wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c0253-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="c0253-120">Ein HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder durch die Anzahl der gesendeten Anforderungen oder durch die `429` zugewiesene Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="c0253-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="c0253-121">Lesen Sie den Antworttext, um den Grenzwert zu verstehen, den Sie erreicht haben.</span><span class="sxs-lookup"><span data-stu-id="c0253-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="c0253-122">Alle oben aufgeführten Kontingente (z. B. 15 Anrufe pro Min.) sind pro Mandantengröße.</span><span class="sxs-lookup"><span data-stu-id="c0253-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="c0253-123">Diese Kontingente sind das Minimum.</span><span class="sxs-lookup"><span data-stu-id="c0253-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="c0253-124">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c0253-124">Permissions</span></span>

<span data-ttu-id="c0253-125">Zum Aufrufen der API für die erweiterte Suche ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c0253-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="c0253-126">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter Zugriff auf [die Microsoft 365 Defender Protection-APIs.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="c0253-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="c0253-127">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="c0253-127">Permission type</span></span> | <span data-ttu-id="c0253-128">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c0253-128">Permission</span></span> | <span data-ttu-id="c0253-129">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c0253-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="c0253-130">Anwendung</span><span class="sxs-lookup"><span data-stu-id="c0253-130">Application</span></span> | <span data-ttu-id="c0253-131">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="c0253-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="c0253-132">Ausführen erweiterter Abfragen</span><span class="sxs-lookup"><span data-stu-id="c0253-132">Run advanced queries</span></span>
<span data-ttu-id="c0253-133">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="c0253-133">Delegated (work or school account)</span></span> | <span data-ttu-id="c0253-134">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="c0253-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="c0253-135">Ausführen erweiterter Abfragen</span><span class="sxs-lookup"><span data-stu-id="c0253-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="c0253-136">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="c0253-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="c0253-137">Der Benutzer benötigt die Ad-Rolle "Daten anzeigen"</span><span class="sxs-lookup"><span data-stu-id="c0253-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="c0253-138">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben.</span><span class="sxs-lookup"><span data-stu-id="c0253-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="c0253-139">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="c0253-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="c0253-140">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="c0253-140">Request headers</span></span>

<span data-ttu-id="c0253-141">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="c0253-141">Header</span></span> | <span data-ttu-id="c0253-142">Wert</span><span class="sxs-lookup"><span data-stu-id="c0253-142">Value</span></span>
-|-
<span data-ttu-id="c0253-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="c0253-143">Authorization</span></span> | <span data-ttu-id="c0253-144">Bearer {token} **Hinweis: erforderlich**</span><span class="sxs-lookup"><span data-stu-id="c0253-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="c0253-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c0253-145">Content-Type</span></span> | <span data-ttu-id="c0253-146">application/json</span><span class="sxs-lookup"><span data-stu-id="c0253-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="c0253-147">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="c0253-147">Request body</span></span>

<span data-ttu-id="c0253-148">Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="c0253-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c0253-149">Parameter</span><span class="sxs-lookup"><span data-stu-id="c0253-149">Parameter</span></span> | <span data-ttu-id="c0253-150">Typ</span><span class="sxs-lookup"><span data-stu-id="c0253-150">Type</span></span> | <span data-ttu-id="c0253-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0253-151">Description</span></span>
-|-|-
<span data-ttu-id="c0253-152">Abfrage</span><span class="sxs-lookup"><span data-stu-id="c0253-152">Query</span></span> | <span data-ttu-id="c0253-153">Text</span><span class="sxs-lookup"><span data-stu-id="c0253-153">Text</span></span> | <span data-ttu-id="c0253-154">Die Abfrage, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0253-154">The query to run.</span></span> <span data-ttu-id="c0253-155">**Hinweis: erforderlich**</span><span class="sxs-lookup"><span data-stu-id="c0253-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="c0253-156">Antwort</span><span class="sxs-lookup"><span data-stu-id="c0253-156">Response</span></span>

<span data-ttu-id="c0253-157">Wenn die Methode erfolgreich ist, wird `200 OK` ein _QueryResponse -Objekt_ im Antworttext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c0253-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="c0253-158">Das Antwortobjekt enthält drei Eigenschaften der obersten Ebene:</span><span class="sxs-lookup"><span data-stu-id="c0253-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="c0253-159">Statistiken – Ein Wörterbuch mit Abfrageleistungsstatistiken.</span><span class="sxs-lookup"><span data-stu-id="c0253-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="c0253-160">Schema – Das Schema der Antwort, eine Liste der Name-Type für jede Spalte.</span><span class="sxs-lookup"><span data-stu-id="c0253-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="c0253-161">Ergebnisse – Eine Liste der Ereignisse der erweiterten Suche.</span><span class="sxs-lookup"><span data-stu-id="c0253-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="c0253-162">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c0253-162">Example</span></span>

<span data-ttu-id="c0253-163">Im folgenden Beispiel sendet ein Benutzer die folgende Abfrage und empfängt ein API-Antwortobjekt mit `Stats` , `Schema` und `Results` .</span><span class="sxs-lookup"><span data-stu-id="c0253-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="c0253-164">Abfrage</span><span class="sxs-lookup"><span data-stu-id="c0253-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="c0253-165">Antwortobjekt</span><span class="sxs-lookup"><span data-stu-id="c0253-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="c0253-166">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="c0253-166">Related articles</span></span>

- [<span data-ttu-id="c0253-167">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="c0253-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="c0253-168">Informationen zu API-Beschränkungen und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="c0253-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="c0253-169">Fehlercodes verstehen</span><span class="sxs-lookup"><span data-stu-id="c0253-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="c0253-170">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="c0253-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)

---
title: Microsoft 365 Defender Advanced Hunting API
description: Hier erfahren Sie, wie Sie erweiterte Jagd Abfragen mit der erweiterten Jagd-API von Microsoft 365 Defender ausführen können.
keywords: Erweiterte Suche, APIs, API, MTP, M365 Defender, Microsoft 365 Defender
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
ms.openlocfilehash: e7cd9192ec25e01ed06b77cb2b39357cb9df79bd
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719380"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="2cccb-104">Microsoft 365 Defender Advanced Hunting API</span><span class="sxs-lookup"><span data-stu-id="2cccb-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2cccb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2cccb-105">**Applies to:**</span></span>

- <span data-ttu-id="2cccb-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2cccb-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2cccb-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="2cccb-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2cccb-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="2cccb-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2cccb-109">[Advanced Hunting](advanced-hunting-overview.md) ist ein Tool zur Gefahren Suche, das [speziell konstruierte Abfragen](advanced-hunting-query-language.md) verwendet, um die letzten 30 Tage der Ereignisdaten in Microsoft 365 Defender zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="2cccb-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="2cccb-110">Sie können erweiterte Jagd Abfragen verwenden, um ungewöhnliche Aktivitäten zu prüfen, mögliche Bedrohungen zu erkennen und sogar auf Angriffe zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="2cccb-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="2cccb-111">Die erweiterte Jagd-API ermöglicht das Programmgesteuertes von Abfrageereignis Daten.</span><span class="sxs-lookup"><span data-stu-id="2cccb-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="2cccb-112">Kontingente und Ressourcenzuteilung</span><span class="sxs-lookup"><span data-stu-id="2cccb-112">Quotas and resource allocation</span></span>

<span data-ttu-id="2cccb-113">Die folgenden Bedingungen beziehen sich auf alle Abfragen.</span><span class="sxs-lookup"><span data-stu-id="2cccb-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="2cccb-114">Abfragen erforschen und Zurückgeben von Daten aus den letzten 30 Tagen.</span><span class="sxs-lookup"><span data-stu-id="2cccb-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="2cccb-115">Ergebnisse können bis zu 100.000 Zeilen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="2cccb-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="2cccb-116">Sie können bis zu 10 Anrufe pro Minute pro Mandant vornehmen.</span><span class="sxs-lookup"><span data-stu-id="2cccb-116">You can make up to 10 calls per minute per tenant.</span></span>
4. <span data-ttu-id="2cccb-117">Sie haben 10 Minuten Spielzeit pro Stunde pro Mandant.</span><span class="sxs-lookup"><span data-stu-id="2cccb-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="2cccb-118">Sie verfügen über vier Gesamtstunden des laufenden Zeit Tages pro Mandant.</span><span class="sxs-lookup"><span data-stu-id="2cccb-118">You have four total hours of running time day per tenant.</span></span>
6. <span data-ttu-id="2cccb-119">Wenn eine einzelne Anforderung länger als 10 Minuten ausgeführt wird, tritt ein Timeout auf, und es wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2cccb-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="2cccb-120">Ein `429` HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder nach der Anzahl der gesendeten Anforderungen oder nach der zugewiesenen Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="2cccb-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="2cccb-121">Der Antworttext enthält die Zeit, bis das von Ihnen erreichte Kontingent zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="2cccb-121">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="2cccb-122">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2cccb-122">Permissions</span></span>

<span data-ttu-id="2cccb-123">Eine der folgenden Berechtigungen ist erforderlich, um die erweiterte Jagd-API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2cccb-123">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="2cccb-124">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="2cccb-124">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="2cccb-125">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="2cccb-125">Permission type</span></span> | <span data-ttu-id="2cccb-126">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="2cccb-126">Permission</span></span> | <span data-ttu-id="2cccb-127">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="2cccb-127">Permission display name</span></span>
-|-|-
<span data-ttu-id="2cccb-128">Anwendung</span><span class="sxs-lookup"><span data-stu-id="2cccb-128">Application</span></span> | <span data-ttu-id="2cccb-129">AdvancedHunting. Read. all</span><span class="sxs-lookup"><span data-stu-id="2cccb-129">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="2cccb-130">Ausführen erweiterter Abfragen</span><span class="sxs-lookup"><span data-stu-id="2cccb-130">Run advanced queries</span></span>
<span data-ttu-id="2cccb-131">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="2cccb-131">Delegated (work or school account)</span></span> | <span data-ttu-id="2cccb-132">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="2cccb-132">AdvancedHunting.Read</span></span> | <span data-ttu-id="2cccb-133">Ausführen erweiterter Abfragen</span><span class="sxs-lookup"><span data-stu-id="2cccb-133">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="2cccb-134">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="2cccb-134">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="2cccb-135">Der Benutzer muss über die AD-Rolle "Daten anzeigen" verfügen.</span><span class="sxs-lookup"><span data-stu-id="2cccb-135">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="2cccb-136">Der Benutzer muss auf dem Gerät basierend auf Gerätegruppen Einstellungen Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="2cccb-136">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="2cccb-137">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="2cccb-137">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="2cccb-138">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="2cccb-138">Request headers</span></span>

<span data-ttu-id="2cccb-139">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="2cccb-139">Header</span></span> | <span data-ttu-id="2cccb-140">Wert</span><span class="sxs-lookup"><span data-stu-id="2cccb-140">Value</span></span>
-|-
<span data-ttu-id="2cccb-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="2cccb-141">Authorization</span></span> | <span data-ttu-id="2cccb-142">Bearer {Token} **Hinweis: erforderlich**</span><span class="sxs-lookup"><span data-stu-id="2cccb-142">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="2cccb-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="2cccb-143">Content-Type</span></span> | <span data-ttu-id="2cccb-144">application/json</span><span class="sxs-lookup"><span data-stu-id="2cccb-144">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="2cccb-145">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="2cccb-145">Request body</span></span>

<span data-ttu-id="2cccb-146">Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:</span><span class="sxs-lookup"><span data-stu-id="2cccb-146">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="2cccb-147">Parameter</span><span class="sxs-lookup"><span data-stu-id="2cccb-147">Parameter</span></span> | <span data-ttu-id="2cccb-148">Typ</span><span class="sxs-lookup"><span data-stu-id="2cccb-148">Type</span></span> | <span data-ttu-id="2cccb-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cccb-149">Description</span></span>
-|-|-
<span data-ttu-id="2cccb-150">Abfrage</span><span class="sxs-lookup"><span data-stu-id="2cccb-150">Query</span></span> | <span data-ttu-id="2cccb-151">Text</span><span class="sxs-lookup"><span data-stu-id="2cccb-151">Text</span></span> | <span data-ttu-id="2cccb-152">Die auszuführende Abfrage.</span><span class="sxs-lookup"><span data-stu-id="2cccb-152">The query to run.</span></span> <span data-ttu-id="2cccb-153">**Hinweis: erforderlich**</span><span class="sxs-lookup"><span data-stu-id="2cccb-153">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="2cccb-154">Antwort</span><span class="sxs-lookup"><span data-stu-id="2cccb-154">Response</span></span>

<span data-ttu-id="2cccb-155">Wenn die Methode erfolgreich verläuft, gibt Sie `200 OK` ein _QueryResponse_ -Objekt im Antworttext zurück.</span><span class="sxs-lookup"><span data-stu-id="2cccb-155">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="2cccb-156">Das Response-Objekt enthält drei Eigenschaften der obersten Ebene:</span><span class="sxs-lookup"><span data-stu-id="2cccb-156">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="2cccb-157">Stats-ein Wörterbuch der Abfrage Leistungsstatistik.</span><span class="sxs-lookup"><span data-stu-id="2cccb-157">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="2cccb-158">Schema – das Schema der Antwort, eine Liste mit Name-Type-Paaren für jede Spalte.</span><span class="sxs-lookup"><span data-stu-id="2cccb-158">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="2cccb-159">Ergebnisse – eine Liste erweiterter Jagd Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="2cccb-159">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="2cccb-160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2cccb-160">Example</span></span>

<span data-ttu-id="2cccb-161">Im folgenden Beispiel sendet ein Benutzer die Abfrage unten und empfängt ein API-Antwortobjekt mit `Stats` , `Schema` und `Results` .</span><span class="sxs-lookup"><span data-stu-id="2cccb-161">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="2cccb-162">Abfrage</span><span class="sxs-lookup"><span data-stu-id="2cccb-162">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="2cccb-163">Response-Objekt</span><span class="sxs-lookup"><span data-stu-id="2cccb-163">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="2cccb-164">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="2cccb-164">Related articles</span></span>

- [<span data-ttu-id="2cccb-165">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="2cccb-165">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="2cccb-166">Informationen zu API-Grenzwerten und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="2cccb-166">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="2cccb-167">Grundlegendes zu Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="2cccb-167">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="2cccb-168">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="2cccb-168">Advanced hunting overview</span></span>](advanced-hunting-overview.md)

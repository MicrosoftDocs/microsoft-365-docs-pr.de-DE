---
title: Microsoft 365 API für die erweiterte Defender-Suche
description: Erfahren Sie, wie Sie Abfragen für die erweiterte Suche mithilfe Microsoft 365 Api für die erweiterte Suche von Defender ausführen.
keywords: Erweiterte Suche, APIs, API, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3ff62265783be846a95964164e372100fe1ef662
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769585"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="6aa2b-104">Microsoft 365 Api für die erweiterte Defender-Suche</span><span class="sxs-lookup"><span data-stu-id="6aa2b-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6aa2b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6aa2b-105">**Applies to:**</span></span>

- <span data-ttu-id="6aa2b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6aa2b-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6aa2b-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6aa2b-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6aa2b-109">[Die erweiterte Suche](advanced-hunting-overview.md) ist ein Tool zur [Bedrohungssuche,](advanced-hunting-query-language.md) das speziell erstellte Abfragen verwendet, um die Ereignisdaten der letzten 30 Tage in Microsoft 365 Defender zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="6aa2b-110">Sie können erweiterte Suchabfragen verwenden, um ungewöhnliche Aktivitäten zu untersuchen, mögliche Bedrohungen zu erkennen und sogar auf Angriffe zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="6aa2b-111">Mit der API für die erweiterte Suche können Sie Ereignisdaten programmgesteuert abfragen.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="6aa2b-112">Kontingente und Ressourcenzuweisung</span><span class="sxs-lookup"><span data-stu-id="6aa2b-112">Quotas and resource allocation</span></span>

<span data-ttu-id="6aa2b-113">Die folgenden Bedingungen beziehen sich auf alle Abfragen.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="6aa2b-114">Abfragen untersuchen Und geben Daten aus den letzten 30 Tagen zurück.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="6aa2b-115">Ergebnisse können bis zu 100.000 Zeilen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="6aa2b-116">Sie können bis zu 15 Anrufe pro Minute und Mandant tätigen.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="6aa2b-117">Abfragen werden blockiert, wenn der Mandant bis nach dem nächsten 15-Minuten-Zyklus 100 % erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-117">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span>
5. <span data-ttu-id="6aa2b-118">Wenn eine einzelne Anforderung länger als 10 Minuten ausgeführt wird, tritt ein Timeout auf und es wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-118">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
6. <span data-ttu-id="6aa2b-119">Ein `429` HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder nach anzahl der gesendeten Anforderungen oder nach zugewiesener Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-119">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="6aa2b-120">Lesen Sie den Antworttext, um den erreichten Grenzwert zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-120">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="6aa2b-121">Alle oben aufgeführten Kontingente (z. B. 15 Anrufe pro Minute) sind pro Mandantengröße.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-121">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="6aa2b-122">Diese Kontingente sind das Minimum.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-122">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="6aa2b-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6aa2b-123">Permissions</span></span>

<span data-ttu-id="6aa2b-124">Eine der folgenden Berechtigungen ist erforderlich, um die API für die erweiterte Suche aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-124">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="6aa2b-125">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="6aa2b-125">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="6aa2b-126">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="6aa2b-126">Permission type</span></span> | <span data-ttu-id="6aa2b-127">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="6aa2b-127">Permission</span></span> | <span data-ttu-id="6aa2b-128">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="6aa2b-128">Permission display name</span></span>
-|-|-
<span data-ttu-id="6aa2b-129">Anwendung</span><span class="sxs-lookup"><span data-stu-id="6aa2b-129">Application</span></span> | <span data-ttu-id="6aa2b-130">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="6aa2b-130">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="6aa2b-131">Ausführen erweiterter Abfragen</span><span class="sxs-lookup"><span data-stu-id="6aa2b-131">Run advanced queries</span></span>
<span data-ttu-id="6aa2b-132">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="6aa2b-132">Delegated (work or school account)</span></span> | <span data-ttu-id="6aa2b-133">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="6aa2b-133">AdvancedHunting.Read</span></span> | <span data-ttu-id="6aa2b-134">Ausführen erweiterter Abfragen</span><span class="sxs-lookup"><span data-stu-id="6aa2b-134">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="6aa2b-135">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="6aa2b-135">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="6aa2b-136">Der Benutzer muss über die AD-Rolle "Daten anzeigen" verfügen.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-136">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="6aa2b-137">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-137">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="6aa2b-138">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="6aa2b-138">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="6aa2b-139">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="6aa2b-139">Request headers</span></span>

<span data-ttu-id="6aa2b-140">Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="6aa2b-140">Header</span></span> | <span data-ttu-id="6aa2b-141">Wert</span><span class="sxs-lookup"><span data-stu-id="6aa2b-141">Value</span></span>
-|-
<span data-ttu-id="6aa2b-142">Authorization</span><span class="sxs-lookup"><span data-stu-id="6aa2b-142">Authorization</span></span> | <span data-ttu-id="6aa2b-143">Bearer {token} **Hinweis: erforderlich**</span><span class="sxs-lookup"><span data-stu-id="6aa2b-143">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="6aa2b-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6aa2b-144">Content-Type</span></span> | <span data-ttu-id="6aa2b-145">application/json</span><span class="sxs-lookup"><span data-stu-id="6aa2b-145">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="6aa2b-146">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="6aa2b-146">Request body</span></span>

<span data-ttu-id="6aa2b-147">Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:</span><span class="sxs-lookup"><span data-stu-id="6aa2b-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="6aa2b-148">Parameter</span><span class="sxs-lookup"><span data-stu-id="6aa2b-148">Parameter</span></span> | <span data-ttu-id="6aa2b-149">Typ</span><span class="sxs-lookup"><span data-stu-id="6aa2b-149">Type</span></span> | <span data-ttu-id="6aa2b-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6aa2b-150">Description</span></span>
-|-|-
<span data-ttu-id="6aa2b-151">Abfrage</span><span class="sxs-lookup"><span data-stu-id="6aa2b-151">Query</span></span> | <span data-ttu-id="6aa2b-152">Text</span><span class="sxs-lookup"><span data-stu-id="6aa2b-152">Text</span></span> | <span data-ttu-id="6aa2b-153">Die auszuführende Abfrage.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-153">The query to run.</span></span> <span data-ttu-id="6aa2b-154">**Hinweis: erforderlich**</span><span class="sxs-lookup"><span data-stu-id="6aa2b-154">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="6aa2b-155">Antwort</span><span class="sxs-lookup"><span data-stu-id="6aa2b-155">Response</span></span>

<span data-ttu-id="6aa2b-156">Bei erfolgreicher Ausführung gibt die Methode ein `200 OK` _QueryResponse-Objekt_ im Antworttext zurück.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-156">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="6aa2b-157">Das Antwortobjekt enthält drei Eigenschaften auf oberster Ebene:</span><span class="sxs-lookup"><span data-stu-id="6aa2b-157">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="6aa2b-158">Statistiken – Ein Wörterbuch mit Abfrageleistungsstatistiken.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-158">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="6aa2b-159">Schema – Das Schema der Antwort, eine Liste Name-Type Paare für jede Spalte.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-159">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="6aa2b-160">Ergebnisse – Eine Liste der Ereignisse der erweiterten Suche.</span><span class="sxs-lookup"><span data-stu-id="6aa2b-160">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="6aa2b-161">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6aa2b-161">Example</span></span>

<span data-ttu-id="6aa2b-162">Im folgenden Beispiel sendet ein Benutzer die folgende Abfrage und empfängt ein API-Antwortobjekt mit `Stats` `Schema` , und `Results` .</span><span class="sxs-lookup"><span data-stu-id="6aa2b-162">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="6aa2b-163">Abfrage</span><span class="sxs-lookup"><span data-stu-id="6aa2b-163">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="6aa2b-164">Response-Objekt</span><span class="sxs-lookup"><span data-stu-id="6aa2b-164">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="6aa2b-165">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="6aa2b-165">Related articles</span></span>

- [<span data-ttu-id="6aa2b-166">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="6aa2b-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="6aa2b-167">Informationen zu API-Grenzwerten und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="6aa2b-167">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="6aa2b-168">Grundlegendes zu Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="6aa2b-168">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="6aa2b-169">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="6aa2b-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)

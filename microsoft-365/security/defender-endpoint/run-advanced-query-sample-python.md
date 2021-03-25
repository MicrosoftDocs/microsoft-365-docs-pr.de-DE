---
title: Leitfaden zur erweiterten Suche mit der Python-API
ms.reviewer: ''
description: Erfahren Sie, wie Sie mithilfe der Microsoft Defender for Endpoint-API mithilfe von Python Abfragen mit Beispielen ausführen.
keywords: apis, supported apis, advanced hunting, query
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
ms.openlocfilehash: 78b6097ea9c3a83f35585f3b13fec4d9056ac25a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199717"
---
# <a name="advanced-hunting-using-python"></a><span data-ttu-id="29deb-104">Erweiterte Suche mithilfe von Python</span><span class="sxs-lookup"><span data-stu-id="29deb-104">Advanced Hunting using Python</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="29deb-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="29deb-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="29deb-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="29deb-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="29deb-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="29deb-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="29deb-108">Führen Sie erweiterte Abfragen mithilfe von Python aus, siehe [Advanced Hunting API](run-advanced-query-api.md).</span><span class="sxs-lookup"><span data-stu-id="29deb-108">Run advanced queries using Python, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="29deb-109">In diesem Abschnitt teilen wir Python-Beispiele, um ein Token abzurufen und es zum Ausführen einer Abfrage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="29deb-109">In this section, we share Python samples to retrieve a token and use it to run a query.</span></span>

><span data-ttu-id="29deb-110">**Voraussetzung:** Sie müssen zuerst [eine App erstellen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="29deb-110">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="get-token"></a><span data-ttu-id="29deb-111">Token erhalten</span><span class="sxs-lookup"><span data-stu-id="29deb-111">Get token</span></span>

- <span data-ttu-id="29deb-112">Führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="29deb-112">Run the following commands:</span></span>

```

import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.microsoftonline.com/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]

```

<span data-ttu-id="29deb-113">where</span><span class="sxs-lookup"><span data-stu-id="29deb-113">where</span></span>
- <span data-ttu-id="29deb-114">tenantId: ID des Mandanten, für den Sie die Abfrage ausführen möchten (d. h., die Abfrage wird auf den Daten dieses Mandanten ausgeführt)</span><span class="sxs-lookup"><span data-stu-id="29deb-114">tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="29deb-115">appId: ID Ihrer Azure AD-App (die App muss über die Berechtigung "Erweiterte Abfragen ausführen" für Microsoft Defender for Endpoint verfügen)</span><span class="sxs-lookup"><span data-stu-id="29deb-115">appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Microsoft Defender for Endpoint)</span></span>
- <span data-ttu-id="29deb-116">appSecret: Geheimnis Ihrer Azure AD-App</span><span class="sxs-lookup"><span data-stu-id="29deb-116">appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="29deb-117">Ausführen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="29deb-117">Run query</span></span>

 <span data-ttu-id="29deb-118">Führen Sie die folgende Abfrage aus:</span><span class="sxs-lookup"><span data-stu-id="29deb-118">Run the following query:</span></span>

```
query = 'RegistryEvents | limit 10' # Paste your own query here

url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
headers = { 
    'Content-Type' : 'application/json',
    'Accept' : 'application/json',
    'Authorization' : "Bearer " + aadToken
}

data = json.dumps({ 'Query' : query }).encode("utf-8")

req = urllib.request.Request(url, data, headers)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
schema = jsonResponse["Schema"]
results = jsonResponse["Results"]

```

- <span data-ttu-id="29deb-119">Schema enthält das Schema der Ergebnisse Ihrer Abfrage</span><span class="sxs-lookup"><span data-stu-id="29deb-119">schema contains the schema of the results of your query</span></span>
- <span data-ttu-id="29deb-120">Ergebnisse enthalten die Ergebnisse Ihrer Abfrage</span><span class="sxs-lookup"><span data-stu-id="29deb-120">results contain the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="29deb-121">Komplexe Abfragen</span><span class="sxs-lookup"><span data-stu-id="29deb-121">Complex queries</span></span>

<span data-ttu-id="29deb-122">Wenn Sie komplexe Abfragen (oder Mehrlinienabfragen) ausführen möchten, speichern Sie ihre Abfrage in einer Datei, und führen Sie anstelle der ersten Zeile im obigen Beispiel den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="29deb-122">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a><span data-ttu-id="29deb-123">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="29deb-123">Work with query results</span></span>

<span data-ttu-id="29deb-124">Sie können jetzt die Abfrageergebnisse verwenden.</span><span class="sxs-lookup"><span data-stu-id="29deb-124">You can now use the query results.</span></span>

<span data-ttu-id="29deb-125">Gehen Sie wie folgt vor, um die Ergebnisse zu durch iterieren:</span><span class="sxs-lookup"><span data-stu-id="29deb-125">To iterate over the results do the below:</span></span>

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


<span data-ttu-id="29deb-126">Gehen Sie wie folgt vor, um die Ergebnisse der Abfrage im CSV-Format in file1.csv aus:</span><span class="sxs-lookup"><span data-stu-id="29deb-126">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

<span data-ttu-id="29deb-127">Gehen Sie wie folgt vor, um die Ergebnisse der Abfrage im JSON-Format in file1.jsaus:</span><span class="sxs-lookup"><span data-stu-id="29deb-127">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a><span data-ttu-id="29deb-128">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="29deb-128">Related topic</span></span>
- [<span data-ttu-id="29deb-129">Microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="29deb-129">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="29deb-130">Erweiterte Suche-API</span><span class="sxs-lookup"><span data-stu-id="29deb-130">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="29deb-131">Erweiterte Suche mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="29deb-131">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)

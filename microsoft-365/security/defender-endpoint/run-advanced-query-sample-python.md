---
title: Leitfaden zur erweiterten Suche mit python-API
ms.reviewer: ''
description: Erfahren Sie, wie Sie mithilfe der Microsoft Defender für Endpunkt-API mithilfe von Python Abfragen mit Beispielen durchführen.
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
ms.openlocfilehash: 17ad28121935adfc958629f7999311c11a8d784e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771443"
---
# <a name="advanced-hunting-using-python"></a><span data-ttu-id="bfa87-104">Erweiterte Bedrohungssuche mit Python</span><span class="sxs-lookup"><span data-stu-id="bfa87-104">Advanced Hunting using Python</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bfa87-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="bfa87-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="bfa87-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="bfa87-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bfa87-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bfa87-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="bfa87-108">Führen Sie erweiterte Abfragen mit Python aus. Weitere Informationen finden Sie unter ["Erweiterte Suche"-API.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="bfa87-108">Run advanced queries using Python, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="bfa87-109">In diesem Abschnitt geben wir Python-Beispiele frei, um ein Token abzurufen und es zum Ausführen einer Abfrage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bfa87-109">In this section, we share Python samples to retrieve a token and use it to run a query.</span></span>

><span data-ttu-id="bfa87-110">**Voraussetzung:** Sie müssen zuerst [eine App erstellen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bfa87-110">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="get-token"></a><span data-ttu-id="bfa87-111">Token abrufen</span><span class="sxs-lookup"><span data-stu-id="bfa87-111">Get token</span></span>

- <span data-ttu-id="bfa87-112">Führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="bfa87-112">Run the following commands:</span></span>

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

<span data-ttu-id="bfa87-113">Wo</span><span class="sxs-lookup"><span data-stu-id="bfa87-113">where</span></span>
- <span data-ttu-id="bfa87-114">tenantId: ID des Mandanten, für den Sie die Abfrage ausführen möchten (d. a. die Abfrage wird auf den Daten dieses Mandanten ausgeführt)</span><span class="sxs-lookup"><span data-stu-id="bfa87-114">tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="bfa87-115">appId: ID Ihrer Azure AD-App (die App muss über die Berechtigung "Erweiterte Abfragen ausführen" für Microsoft Defender für Endpunkt verfügen)</span><span class="sxs-lookup"><span data-stu-id="bfa87-115">appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Microsoft Defender for Endpoint)</span></span>
- <span data-ttu-id="bfa87-116">appSecret: Geheimer Schlüssel Ihrer Azure AD-App</span><span class="sxs-lookup"><span data-stu-id="bfa87-116">appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="bfa87-117">Abfrage ausführen</span><span class="sxs-lookup"><span data-stu-id="bfa87-117">Run query</span></span>

 <span data-ttu-id="bfa87-118">Führen Sie die folgende Abfrage aus:</span><span class="sxs-lookup"><span data-stu-id="bfa87-118">Run the following query:</span></span>

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

- <span data-ttu-id="bfa87-119">schema contains the schema of the results of your query</span><span class="sxs-lookup"><span data-stu-id="bfa87-119">schema contains the schema of the results of your query</span></span>
- <span data-ttu-id="bfa87-120">die Ergebnisse der Abfrage enthalten</span><span class="sxs-lookup"><span data-stu-id="bfa87-120">results contain the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="bfa87-121">Komplexe Abfragen</span><span class="sxs-lookup"><span data-stu-id="bfa87-121">Complex queries</span></span>

<span data-ttu-id="bfa87-122">Wenn Sie komplexe Abfragen (oder Abfragen mit mehreren Leitungen) ausführen möchten, speichern Sie Ihre Abfrage in einer Datei, und führen Sie anstelle der ersten Zeile im obigen Beispiel den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bfa87-122">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a><span data-ttu-id="bfa87-123">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="bfa87-123">Work with query results</span></span>

<span data-ttu-id="bfa87-124">Sie können jetzt die Abfrageergebnisse verwenden.</span><span class="sxs-lookup"><span data-stu-id="bfa87-124">You can now use the query results.</span></span>

<span data-ttu-id="bfa87-125">Führen Sie die folgenden Schritte aus, um die Ergebnisse zu durchlaufen:</span><span class="sxs-lookup"><span data-stu-id="bfa87-125">To iterate over the results do the below:</span></span>

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


<span data-ttu-id="bfa87-126">Gehen Sie wie folgt vor, um die Ergebnisse der Abfrage im CSV-Format in einer Datei auszugeben file1.csv:</span><span class="sxs-lookup"><span data-stu-id="bfa87-126">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

<span data-ttu-id="bfa87-127">Gehen Sie wie folgt vor, um die Ergebnisse der Abfrage im JSON-Format in Datei file1.jsauszugeben:</span><span class="sxs-lookup"><span data-stu-id="bfa87-127">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a><span data-ttu-id="bfa87-128">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="bfa87-128">Related topic</span></span>
- [<span data-ttu-id="bfa87-129">Microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="bfa87-129">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="bfa87-130">Erweiterte Suche-API</span><span class="sxs-lookup"><span data-stu-id="bfa87-130">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="bfa87-131">Erweiterte Bedrohungssuche mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfa87-131">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)

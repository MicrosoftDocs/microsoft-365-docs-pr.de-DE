---
title: Erweiterte Suche mit PowerShell-API-Grundlagen
ms.reviewer: ''
description: Lernen Sie die Grundlagen der Abfrage der Microsoft Defender für Endpunkt-API mithilfe von PowerShell kennen.
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
ms.openlocfilehash: 0d44f59f69c590ecd8d61207de8784af3e32197d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844886"
---
# <a name="advanced-hunting-using-powershell"></a><span data-ttu-id="4349c-104">Erweiterte Bedrohungssuche mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="4349c-104">Advanced Hunting using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4349c-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4349c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="4349c-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="4349c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4349c-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4349c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="4349c-108">Führen Sie erweiterte Abfragen mithilfe von PowerShell aus. Weitere Informationen finden Sie unter ["Erweiterte Suche"-API.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="4349c-108">Run advanced queries using PowerShell, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="4349c-109">In diesem Abschnitt geben wir PowerShell-Beispiele frei, um ein Token abzurufen und es zum Ausführen einer Abfrage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4349c-109">In this section, we share PowerShell samples to retrieve a token and use it to run a query.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4349c-110">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="4349c-110">Before you begin</span></span>
<span data-ttu-id="4349c-111">Zunächst müssen Sie [eine App erstellen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4349c-111">You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="4349c-112">Vorbereitungsanweisungen</span><span class="sxs-lookup"><span data-stu-id="4349c-112">Preparation instructions</span></span>

- <span data-ttu-id="4349c-113">Öffnen Sie ein PowerShell-Fenster.</span><span class="sxs-lookup"><span data-stu-id="4349c-113">Open a PowerShell window.</span></span>
- <span data-ttu-id="4349c-114">Wenn Ihre Richtlinie das Ausführen der PowerShell-Befehle nicht zulässt, können Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="4349c-114">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

><span data-ttu-id="4349c-115">Weitere Informationen finden Sie in der [PowerShell-Dokumentation.](/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="4349c-115">For more information, see [PowerShell documentation](/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="4349c-116">Token abrufen</span><span class="sxs-lookup"><span data-stu-id="4349c-116">Get token</span></span>

- <span data-ttu-id="4349c-117">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="4349c-117">Run the following:</span></span>

```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$body = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$response = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $body -ErrorAction Stop
$aadToken = $response.access_token
```

<span data-ttu-id="4349c-118">Wo</span><span class="sxs-lookup"><span data-stu-id="4349c-118">where</span></span>
- <span data-ttu-id="4349c-119">$tenantId: ID des Mandanten, für den Sie die Abfrage ausführen möchten (d. a. die Abfrage wird auf den Daten dieses Mandanten ausgeführt)</span><span class="sxs-lookup"><span data-stu-id="4349c-119">$tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="4349c-120">$appId: ID Ihrer Azure AD-App (die App muss über die Berechtigung "Erweiterte Abfragen ausführen" für Defender für Endpunkt verfügen)</span><span class="sxs-lookup"><span data-stu-id="4349c-120">$appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="4349c-121">$appSecret: Geheimer Schlüssel Ihrer Azure AD-App</span><span class="sxs-lookup"><span data-stu-id="4349c-121">$appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="4349c-122">Abfrage ausführen</span><span class="sxs-lookup"><span data-stu-id="4349c-122">Run query</span></span>

<span data-ttu-id="4349c-123">Führen Sie die folgende Abfrage aus:</span><span class="sxs-lookup"><span data-stu-id="4349c-123">Run the following query:</span></span>

```
$query = 'RegistryEvents | limit 10' # Paste your own query here

$url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$body = ConvertTo-Json -InputObject @{ 'Query' = $query }
$webResponse = Invoke-WebRequest -Method Post -Uri $url -Headers $headers -Body $body -ErrorAction Stop
$response =  $webResponse | ConvertFrom-Json
$results = $response.Results
$schema = $response.Schema
```

- <span data-ttu-id="4349c-124">$results die Ergebnisse Ihrer Abfrage enthalten</span><span class="sxs-lookup"><span data-stu-id="4349c-124">$results contain the results of your query</span></span>
- <span data-ttu-id="4349c-125">$schema enthält das Schema der Ergebnisse Der Abfrage</span><span class="sxs-lookup"><span data-stu-id="4349c-125">$schema contains the schema of the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="4349c-126">Komplexe Abfragen</span><span class="sxs-lookup"><span data-stu-id="4349c-126">Complex queries</span></span>

<span data-ttu-id="4349c-127">Wenn Sie komplexe Abfragen (oder Abfragen mit mehreren Leitungen) ausführen möchten, speichern Sie Ihre Abfrage in einer Datei, und führen Sie anstelle der ersten Zeile im obigen Beispiel den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="4349c-127">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a><span data-ttu-id="4349c-128">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="4349c-128">Work with query results</span></span>

<span data-ttu-id="4349c-129">Sie können jetzt die Abfrageergebnisse verwenden.</span><span class="sxs-lookup"><span data-stu-id="4349c-129">You can now use the query results.</span></span>

<span data-ttu-id="4349c-130">Gehen Sie wie folgt vor, um die Ergebnisse der Abfrage im CSV-Format in einer Datei auszugeben file1.csv:</span><span class="sxs-lookup"><span data-stu-id="4349c-130">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

<span data-ttu-id="4349c-131">Gehen Sie folgendermaßen vor, um die Ergebnisse der Abfrage im JSON-Format in Datei file1.jsweiter unten auszugeben:</span><span class="sxs-lookup"><span data-stu-id="4349c-131">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a><span data-ttu-id="4349c-132">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="4349c-132">Related topic</span></span>
- [<span data-ttu-id="4349c-133">Microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="4349c-133">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="4349c-134">Erweiterte Suche-API</span><span class="sxs-lookup"><span data-stu-id="4349c-134">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="4349c-135">Erweiterte Bedrohungssuche mit Python</span><span class="sxs-lookup"><span data-stu-id="4349c-135">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)

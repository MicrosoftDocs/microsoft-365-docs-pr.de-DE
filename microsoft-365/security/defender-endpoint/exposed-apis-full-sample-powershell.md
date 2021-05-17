---
title: Leitfaden zur erweiterten Suche mit der PowerShell-API
ms.reviewer: ''
description: Verwenden Sie diese Codebeispiele, und fragen Sie mehrere Microsoft Defender for Endpoint-APIs ab.
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
ms.date: 09/24/2018
ms.technology: mde
ms.openlocfilehash: 9913d1b0b0d5d0462fdee0b9c576a590bd3ddbc9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198323"
---
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a><span data-ttu-id="a9f65-104">Microsoft Defender für Endpunkt-APIs mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9f65-104">Microsoft Defender for Endpoint APIs using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a9f65-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a9f65-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="a9f65-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a9f65-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a9f65-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a9f65-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

><span data-ttu-id="a9f65-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a9f65-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a9f65-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a9f65-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="a9f65-110">Vollständiges Szenario mit mehreren APIs von Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="a9f65-110">Full scenario using multiple APIs from Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="a9f65-111">In diesem Abschnitt teilen wir PowerShell-Beispiele für</span><span class="sxs-lookup"><span data-stu-id="a9f65-111">In this section, we share PowerShell samples to</span></span> 
- <span data-ttu-id="a9f65-112">Abrufen eines Tokens</span><span class="sxs-lookup"><span data-stu-id="a9f65-112">Retrieve a token</span></span> 
- <span data-ttu-id="a9f65-113">Verwenden des Tokens zum Abrufen der neuesten Warnungen in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a9f65-113">Use token to retrieve the latest alerts in Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="a9f65-114">Wenn die Warnung für jede Warnung mittlere oder hohe Priorität hat und noch ausgeführt wird, überprüfen Sie, wie oft das Gerät mit verdächtiger URL verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="a9f65-114">For each alert, if the alert has medium or high priority and is still in progress, check how many times the device has connected to suspicious URL.</span></span>

<span data-ttu-id="a9f65-115">**Voraussetzung:** Sie müssen zuerst [eine App erstellen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a9f65-115">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="a9f65-116">Vorbereitungsanweisungen</span><span class="sxs-lookup"><span data-stu-id="a9f65-116">Preparation instructions</span></span>

- <span data-ttu-id="a9f65-117">Öffnen Sie ein PowerShell-Fenster.</span><span class="sxs-lookup"><span data-stu-id="a9f65-117">Open a PowerShell window.</span></span>
- <span data-ttu-id="a9f65-118">Wenn Die Ausführung der PowerShell-Befehle in Ihrer Richtlinie nicht zulässig ist, können Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="a9f65-118">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

<span data-ttu-id="a9f65-119">Weitere Informationen finden Sie in der [PowerShell-Dokumentation.](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="a9f65-119">For more information, see [PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="a9f65-120">Token erhalten</span><span class="sxs-lookup"><span data-stu-id="a9f65-120">Get token</span></span>

<span data-ttu-id="a9f65-121">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a9f65-121">Run the below:</span></span>

- <span data-ttu-id="a9f65-122">$tenantId: ID des Mandanten, für den Sie die Abfrage ausführen möchten (d. h., die Abfrage wird auf den Daten dieses Mandanten ausgeführt)</span><span class="sxs-lookup"><span data-stu-id="a9f65-122">$tenantId: ID of the tenant on behalf of which you want to run the query (i.e., the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="a9f65-123">$appId: ID Ihrer AAD-App (die App muss über die Berechtigung "Erweiterte Abfragen ausführen" für Defender for Endpoint verfügen)</span><span class="sxs-lookup"><span data-stu-id="a9f65-123">$appId: ID of your AAD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="a9f65-124">$appSecret: Geheimnis Ihrer Azure AD-App</span><span class="sxs-lookup"><span data-stu-id="a9f65-124">$appSecret: Secret of your Azure AD app</span></span>

- <span data-ttu-id="a9f65-125">$suspiciousUrl: Die URL</span><span class="sxs-lookup"><span data-stu-id="a9f65-125">$suspiciousUrl: The URL</span></span>


```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here
$suspiciousUrl = 'www.suspiciousUrl.com' # Paste your own URL here

$resourceAppIdUri = 'https://securitycenter.onmicrosoft.com/windowsatpservice'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$aadToken = $authResponse.access_token


#Get latest alert
$alertUrl = "https://api.securitycenter.microsoft.com/api/alerts?`$top=10"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$alertResponse = Invoke-WebRequest -Method Get -Uri $alertUrl -Headers $headers -ErrorAction Stop
$alerts =  ($alertResponse | ConvertFrom-Json).value

$machinesToInvestigate = New-Object System.Collections.ArrayList

Foreach($alert in $alerts)
{
    #echo $alert.id $alert.machineId    $alert.severity $alert.status

    $isSevereAlert = $alert.severity -in 'Medium', 'High'
    $isOpenAlert = $alert.status -in 'InProgress', 'New'
    if($isOpenAlert -and $isSevereAlert)
    {
        if (-not $machinesToInvestigate.Contains($alert.machineId))
        {
            $machinesToInvestigate.Add($alert.machineId) > $null
        }
    }
}

$commaSeparatedMachines = '"{0}"' -f ($machinesToInvestigate -join '","')

$query = "NetworkCommunicationEvents
| where MachineId in ($commaSeparatedMachines)
| where RemoteUrl  == `"$suspiciousUrl`"
| summarize ConnectionsCount = count() by MachineId"

$queryUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"

$queryBody = ConvertTo-Json -InputObject @{ 'Query' = $query }
$queryResponse = Invoke-WebRequest -Method Post -Uri $queryUrl -Headers $headers -Body $queryBody -ErrorAction Stop
$response =  ($queryResponse | ConvertFrom-Json).Results
$response
```


## <a name="see-also"></a><span data-ttu-id="a9f65-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9f65-126">See also</span></span>
- [<span data-ttu-id="a9f65-127">Microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="a9f65-127">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="a9f65-128">Erweiterte Suche-API</span><span class="sxs-lookup"><span data-stu-id="a9f65-128">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="a9f65-129">Erweiterte Bedrohungssuche mit Python</span><span class="sxs-lookup"><span data-stu-id="a9f65-129">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)

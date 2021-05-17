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
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a>Microsoft Defender für Endpunkt-APIs mit PowerShell

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Vollständiges Szenario mit mehreren APIs von Microsoft Defender for Endpoint.

In diesem Abschnitt teilen wir PowerShell-Beispiele für 
- Abrufen eines Tokens 
- Verwenden des Tokens zum Abrufen der neuesten Warnungen in Microsoft Defender for Endpoint
- Wenn die Warnung für jede Warnung mittlere oder hohe Priorität hat und noch ausgeführt wird, überprüfen Sie, wie oft das Gerät mit verdächtiger URL verbunden ist.

**Voraussetzung:** Sie müssen zuerst [eine App erstellen.](apis-intro.md)

## <a name="preparation-instructions"></a>Vorbereitungsanweisungen

- Öffnen Sie ein PowerShell-Fenster.
- Wenn Die Ausführung der PowerShell-Befehle in Ihrer Richtlinie nicht zulässig ist, können Sie den folgenden Befehl ausführen:
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

Weitere Informationen finden Sie in der [PowerShell-Dokumentation.](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>Token erhalten

Führen Sie die folgenden Schritte aus:

- $tenantId: ID des Mandanten, für den Sie die Abfrage ausführen möchten (d. h., die Abfrage wird auf den Daten dieses Mandanten ausgeführt)
- $appId: ID Ihrer AAD-App (die App muss über die Berechtigung "Erweiterte Abfragen ausführen" für Defender for Endpoint verfügen)
- $appSecret: Geheimnis Ihrer Azure AD-App

- $suspiciousUrl: Die URL


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


## <a name="see-also"></a>Siehe auch
- [Microsoft Defender für Endpunkt-APIs](apis-intro.md)
- [Erweiterte Suche-API](run-advanced-query-api.md)
- [Erweiterte Bedrohungssuche mit Python](run-advanced-query-sample-python.md)

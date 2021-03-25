---
title: Erweiterte Suche mit PowerShell-API-Grundlagen
ms.reviewer: ''
description: Erfahren Sie mehr über die Grundlagen der Abfrage der Microsoft Defender for Endpoint-API mithilfe von PowerShell.
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
ms.openlocfilehash: 20c63daaf61b85f35aaceccb540b6d50824c801d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198671"
---
# <a name="advanced-hunting-using-powershell"></a>Erweiterte Suche mit PowerShell

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Führen Sie erweiterte Abfragen mit PowerShell aus, siehe [Advanced Hunting API](run-advanced-query-api.md).

In diesem Abschnitt teilen wir PowerShell-Beispiele, um ein Token abzurufen und es zum Ausführen einer Abfrage zu verwenden.

## <a name="before-you-begin"></a>Bevor Sie beginnen
Sie müssen zuerst [eine App erstellen.](apis-intro.md)

## <a name="preparation-instructions"></a>Vorbereitungsanweisungen

- Öffnen Sie ein PowerShell-Fenster.
- Wenn Die Ausführung der PowerShell-Befehle in Ihrer Richtlinie nicht zulässig ist, können Sie den folgenden Befehl ausführen:
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

>Weitere Informationen finden Sie in der [PowerShell-Dokumentation.](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>Token erhalten

- Führen Sie den folgenden Befehl aus:

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

where
- $tenantId: ID des Mandanten, für den Sie die Abfrage ausführen möchten (d. h. die Abfrage wird auf den Daten dieses Mandanten ausgeführt)
- $appId: ID Ihrer Azure AD-App (die App muss über die Berechtigung "Erweiterte Abfragen ausführen" für Defender for Endpoint verfügen)
- $appSecret: Geheimnis Ihrer Azure AD-App

## <a name="run-query"></a>Ausführen einer Abfrage

Führen Sie die folgende Abfrage aus:

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

- $results enthalten die Ergebnisse Ihrer Abfrage
- $schema enthält das Schema der Ergebnisse Ihrer Abfrage

### <a name="complex-queries"></a>Komplexe Abfragen

Wenn Sie komplexe Abfragen (oder Mehrlinienabfragen) ausführen möchten, speichern Sie ihre Abfrage in einer Datei, und führen Sie anstelle der ersten Zeile im obigen Beispiel den folgenden Befehl aus:

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a>Arbeiten mit Abfrageergebnissen

Sie können jetzt die Abfrageergebnisse verwenden.

Gehen Sie wie folgt vor, um die Ergebnisse der Abfrage im CSV-Format in file1.csv aus:

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

Gehen Sie wie folgt vor, um die Ergebnisse der Abfrage im JSON-Format in file1.jsaus:

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a>Verwandtes Thema
- [Microsoft Defender für Endpunkt-APIs](apis-intro.md)
- [Erweiterte Suche-API](run-advanced-query-api.md)
- [Erweiterte Suche mithilfe von Python](run-advanced-query-sample-python.md)

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
# <a name="advanced-hunting-using-powershell"></a>Erweiterte Bedrohungssuche mit PowerShell

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Führen Sie erweiterte Abfragen mithilfe von PowerShell aus. Weitere Informationen finden Sie unter ["Erweiterte Suche"-API.](run-advanced-query-api.md)

In diesem Abschnitt geben wir PowerShell-Beispiele frei, um ein Token abzurufen und es zum Ausführen einer Abfrage zu verwenden.

## <a name="before-you-begin"></a>Bevor Sie beginnen
Zunächst müssen Sie [eine App erstellen.](apis-intro.md)

## <a name="preparation-instructions"></a>Vorbereitungsanweisungen

- Öffnen Sie ein PowerShell-Fenster.
- Wenn Ihre Richtlinie das Ausführen der PowerShell-Befehle nicht zulässt, können Sie den folgenden Befehl ausführen:
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

>Weitere Informationen finden Sie in der [PowerShell-Dokumentation.](/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>Token abrufen

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

Wo
- $tenantId: ID des Mandanten, für den Sie die Abfrage ausführen möchten (d. a. die Abfrage wird auf den Daten dieses Mandanten ausgeführt)
- $appId: ID Ihrer Azure AD-App (die App muss über die Berechtigung "Erweiterte Abfragen ausführen" für Defender für Endpunkt verfügen)
- $appSecret: Geheimer Schlüssel Ihrer Azure AD-App

## <a name="run-query"></a>Abfrage ausführen

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

- $results die Ergebnisse Ihrer Abfrage enthalten
- $schema enthält das Schema der Ergebnisse Der Abfrage

### <a name="complex-queries"></a>Komplexe Abfragen

Wenn Sie komplexe Abfragen (oder Abfragen mit mehreren Leitungen) ausführen möchten, speichern Sie Ihre Abfrage in einer Datei, und führen Sie anstelle der ersten Zeile im obigen Beispiel den folgenden Befehl aus:

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a>Arbeiten mit Abfrageergebnissen

Sie können jetzt die Abfrageergebnisse verwenden.

Gehen Sie wie folgt vor, um die Ergebnisse der Abfrage im CSV-Format in einer Datei auszugeben file1.csv:

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

Gehen Sie folgendermaßen vor, um die Ergebnisse der Abfrage im JSON-Format in Datei file1.jsweiter unten auszugeben:

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a>Verwandtes Thema
- [Microsoft Defender für Endpunkt-APIs](apis-intro.md)
- [Erweiterte Suche-API](run-advanced-query-api.md)
- [Erweiterte Bedrohungssuche mit Python](run-advanced-query-sample-python.md)

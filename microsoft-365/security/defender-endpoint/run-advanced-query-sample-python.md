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
# <a name="advanced-hunting-using-python"></a>Erweiterte Bedrohungssuche mit Python

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Führen Sie erweiterte Abfragen mithilfe von Python aus, siehe [Advanced Hunting API](run-advanced-query-api.md).

In diesem Abschnitt teilen wir Python-Beispiele, um ein Token abzurufen und es zum Ausführen einer Abfrage zu verwenden.

>**Voraussetzung:** Sie müssen zuerst [eine App erstellen.](apis-intro.md)

## <a name="get-token"></a>Token erhalten

- Führen Sie die folgenden Befehle aus:

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

where
- tenantId: ID des Mandanten, für den Sie die Abfrage ausführen möchten (d. h., die Abfrage wird auf den Daten dieses Mandanten ausgeführt)
- appId: ID Ihrer Azure AD-App (die App muss über die Berechtigung "Erweiterte Abfragen ausführen" für Microsoft Defender for Endpoint verfügen)
- appSecret: Geheimnis Ihrer Azure AD-App

## <a name="run-query"></a>Ausführen einer Abfrage

 Führen Sie die folgende Abfrage aus:

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

- Schema enthält das Schema der Ergebnisse Ihrer Abfrage
- Ergebnisse enthalten die Ergebnisse Ihrer Abfrage

### <a name="complex-queries"></a>Komplexe Abfragen

Wenn Sie komplexe Abfragen (oder Mehrlinienabfragen) ausführen möchten, speichern Sie ihre Abfrage in einer Datei, und führen Sie anstelle der ersten Zeile im obigen Beispiel den folgenden Befehl aus:

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a>Arbeiten mit Abfrageergebnissen

Sie können jetzt die Abfrageergebnisse verwenden.

Gehen Sie wie folgt vor, um die Ergebnisse zu durch iterieren:

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


Gehen Sie wie folgt vor, um die Ergebnisse der Abfrage im CSV-Format in file1.csv aus:

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

Gehen Sie wie folgt vor, um die Ergebnisse der Abfrage im JSON-Format in file1.jsaus:

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a>Verwandtes Thema
- [Microsoft Defender für Endpunkt-APIs](apis-intro.md)
- [Erweiterte Suche-API](run-advanced-query-api.md)
- [Erweiterte Bedrohungssuche mit PowerShell](run-advanced-query-sample-powershell.md)

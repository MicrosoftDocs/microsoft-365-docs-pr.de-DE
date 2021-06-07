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
# <a name="advanced-hunting-using-python"></a>Erweiterte Bedrohungssuche mit Python

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Führen Sie erweiterte Abfragen mit Python aus. Weitere Informationen finden Sie unter ["Erweiterte Suche"-API.](run-advanced-query-api.md)

In diesem Abschnitt geben wir Python-Beispiele frei, um ein Token abzurufen und es zum Ausführen einer Abfrage zu verwenden.

>**Voraussetzung:** Sie müssen zuerst [eine App erstellen.](apis-intro.md)

## <a name="get-token"></a>Token abrufen

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

Wo
- tenantId: ID des Mandanten, für den Sie die Abfrage ausführen möchten (d. a. die Abfrage wird auf den Daten dieses Mandanten ausgeführt)
- appId: ID Ihrer Azure AD-App (die App muss über die Berechtigung "Erweiterte Abfragen ausführen" für Microsoft Defender für Endpunkt verfügen)
- appSecret: Geheimer Schlüssel Ihrer Azure AD-App

## <a name="run-query"></a>Abfrage ausführen

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

- schema contains the schema of the results of your query
- die Ergebnisse der Abfrage enthalten

### <a name="complex-queries"></a>Komplexe Abfragen

Wenn Sie komplexe Abfragen (oder Abfragen mit mehreren Leitungen) ausführen möchten, speichern Sie Ihre Abfrage in einer Datei, und führen Sie anstelle der ersten Zeile im obigen Beispiel den folgenden Befehl aus:

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a>Arbeiten mit Abfrageergebnissen

Sie können jetzt die Abfrageergebnisse verwenden.

Führen Sie die folgenden Schritte aus, um die Ergebnisse zu durchlaufen:

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


Gehen Sie wie folgt vor, um die Ergebnisse der Abfrage im CSV-Format in einer Datei auszugeben file1.csv:

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

Gehen Sie wie folgt vor, um die Ergebnisse der Abfrage im JSON-Format in Datei file1.jsauszugeben:

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a>Verwandtes Thema
- [Microsoft Defender für Endpunkt-APIs](apis-intro.md)
- [Erweiterte Suche-API](run-advanced-query-api.md)
- [Erweiterte Bedrohungssuche mit PowerShell](run-advanced-query-sample-powershell.md)

---
title: Ausführen von Liveantwortbefehlen auf einem Gerät
description: Erfahren Sie, wie Sie eine Sequenz von Liveantwortbefehlen auf einem Gerät ausführen.
keywords: APIs, Graph-API, unterstützte APIs, in Bibliothek hochladen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879700"
---
#  <a name="run-live-response-commands-on-a-device"></a>Ausführen von Liveantwortbefehlen auf einem Gerät

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

>Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-Beschreibung

Führt eine Sequenz von Liveantwortbefehlen auf einem Gerät aus.

## <a name="limitations"></a>Einschränkungen

1.  Die Rateneinschränkungen für diese API sind 10 Aufrufe pro Minute (zusätzliche Anforderungen werden mit HTTP 429 beantwortet).

2.  25 gleichzeitig ausgeführte Sitzungen (Anforderungen, die den Einschränkungsgrenzwert überschreiten, erhalten die Antwort "429 – zu viele Anforderungen").

3.  Wenn der Computer nicht verfügbar ist, wird die Sitzung bis zu 3 Tage lang in die Warteschlange gestellt.

4.  Timeouts für RunScript-Befehle nach 10 Minuten.

5.  Wenn ein Liveantwortbefehl fehlschlägt, werden nicht alle ausgeführten Aktionen ausgeführt.

## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter ["Erste Schritte".](apis-intro.md)

| Berechtigungstyp                    | Berechtigung           | Anzeigename der Berechtigung                   |
|------------------------------------|----------------------|-------------------------------------------|
| Anwendung                        | Machine.LiveResponse | Ausführen einer Liveantwort auf einem bestimmten Computer |
| Delegiert (Geschäfts-, Schul- oder Unikonto) | Machine.LiveResponse | Ausführen einer Liveantwort auf einem bestimmten Computer |

## <a name="http-request"></a>HTTP-Anforderung

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a>Anforderungsheader

| Name      | Typ | Beschreibung                 |
|---------------|----------|---------------------------------|
| Authorization | Zeichenfolge   | Inhaber\<token>\. Erforderlich.   |
| Content-Type  | string   | application/json. Erforderlich.  |

## <a name="request-body"></a>Anforderungstext

| Parameter | Typ | Beschreibung                                                        |
|---------------|----------|------------------------------------------------------------------------|
| Kommentar       | Zeichenfolge   | Kommentar, der der Aktion zugeordnet werden soll.                                 |
| Befehle      | Array    | Auszuführende Befehle. Zulässige Werte sind PutFile, RunScript, GetFile. |

Befehle:

| Befehlstyp | Parameter                                                                          | Beschreibung                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| Putfile      | Schlüssel: FileName  <br><br>  Wert: \<file name\>                                                                          | Platziert eine Datei aus der Bibliothek auf dem Gerät. Dateien werden in einem Arbeitsordner gespeichert und gelöscht, wenn das Gerät standardmäßig neu gestartet wird.
| RunScript    | Schlüssel: ScriptName<br>Wert: \<Script from library\> <br><br> Schlüssel: Args  <br> Wert: \<Script arguments\>                          | Führt ein Skript aus der Bibliothek auf einem Gerät aus.    <br><br>  Der Args-Parameter wird an Ihr Skript übergeben. <br><br> Timeouts nach 10 Minuten.     
| GetFile      | Schlüssel: Pfad <br> Wert: \<File path\>                                                        | Datei von einem Gerät erfassen. HINWEIS: Umgekehrte Schrägstriche im Pfad müssen escaped sein.                                                                      |

## <a name="response"></a>Antwort

-   Wenn die Methode erfolgreich ist, wird "200, Ok" zurückgegeben.
    Aktionsentität. Wenn der Computer mit der angegebenen ID nicht gefunden wurde – 404 Nicht gefunden.

## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
**Json**

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

**Antwort**

Nachfolgend sehen Sie ein Beispiel der Antwort.

```HTTP
HTTP/1.1 200 Ok
```

Inhaltstyp: application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a>Verwandte Themen
- [Api für Computeraktionen abrufen](get-machineaction-object.md)
- [Abrufen des Ergebnisses der Liveantwort](get-live-response-result.md)
- [Computeraktion abbrechen](cancel-machine-action.md)

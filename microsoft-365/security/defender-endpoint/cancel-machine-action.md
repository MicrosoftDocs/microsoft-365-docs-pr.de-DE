---
title: Api zum Abbrechen von Computeraktionen
description: Erfahren Sie, wie Sie eine bereits gestartete Computeraktion abbrechen
keywords: APIs, Graph-API,
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
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879754"
---
#   <a name="cancel-machine-action-api"></a>Api zum Abbrechen von Computeraktionen 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-Beschreibung

Abbrechen einer bereits gestarteten Computeraktion, die sich noch nicht im endgültigen Zustand befindet (abgeschlossen, abgebrochen, fehlgeschlagen).

## <a name="limitations"></a>Einschränkungen

1.  Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.

## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter ["Erste Schritte".](apis-intro.md)

|     Berechtigungstyp     |     Berechtigung     |    Anzeigename der Berechtigung     |
|-|-|-|
|    <br>Anwendung    |    <br>Machine.CollectForensic<br>   Machine.Isolate   <br>Machine.RestrictExecution<br>   Machine.Scan<br>   Machine.Offboard<br>   Machine.StopAndQuarantine<br>   Machine.LiveResponse    |    Forensik sammeln   <br>Computer isolieren<br>Einschränken der Codeausführung<br>  Scancomputer<br>  Offboard-Computer<br>   Beenden und Isolieren<br>   Ausführen einer Liveantwort auf einem bestimmten Computer    |
|    <br>Delegiert (Geschäfts-, Schul- oder Unikonto)    |    Machine.CollectForensic<br>   Machine.Isolate    <br>Machine.RestrictExecution<br>   Machine.Scan<br>   Machine.Offboard<br>   Machine.StopAndQuarantineMachine.LiveResponse    |    Forensik sammeln<br>   Computer isolieren<br>  Einschränken der Codeausführung<br> Scancomputer<br>Offboard-Computer<br> Beenden und Isolieren<br> Ausführen einer Liveantwort auf einem bestimmten Computer    |


## <a name="http-request"></a>HTTP-Anforderung

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a>Anforderungsheader

| Name      | Typ | Beschreibung                 |
|---------------|----------|---------------------------------|
| Authorization | Zeichenfolge   | Bearer {token}. Erforderlich.   |
| Content-Type  | string   | application/json. Erforderlich.  |

## <a name="request-body"></a>Anforderungstext

| Parameter | Typ | Beschreibung                        |
|---------------|----------|----------------------------------------|
| Kommentar       | Zeichenfolge   | Kommentar, der der Abbruchaktion zugeordnet werden soll.  |

## <a name="response"></a>Antwort

Bei erfolgreicher Ausführung gibt die Methode den Antwortcode 200,OK mit einer Computeraktionsentität zurück. Wenn die Computeraktionsentität mit der angegebenen ID nicht gefunden wurde – 404 Nicht gefunden.

## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a>Verwandtes Thema

- [Api für Computeraktionen abrufen](get-machineaction-object.md)
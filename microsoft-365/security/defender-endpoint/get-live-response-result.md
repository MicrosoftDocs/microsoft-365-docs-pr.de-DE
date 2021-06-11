---
title: Abrufen von Liveantwortergebnissen
description: Erfahren Sie, wie Sie ein bestimmtes Ergebnis eines Liveantwortbefehls anhand des Index abrufen.
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
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879733"
---
#  <a name="get-live-response-results"></a>Abrufen von Liveantwortergebnissen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-Beschreibung

Ruft ein bestimmtes Ergebnis des Liveantwortbefehls anhand seines Index ab.

## <a name="limitations"></a>Einschränkungen

1.  Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.

## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter ["Erste Schritte".](apis-intro.md)

| Berechtigungstyp                    | Berechtigung           | Anzeigename der Berechtigung                   |
|------------------------------------|----------------------|-------------------------------------------|
| Anwendung                        | Machine.LiveResponse | Ausführen einer Liveantwort auf einem bestimmten Computer |
| Delegiert (Geschäfts-, Schul- oder Unikonto) | Machine.LiveResponse | Ausführen einer Liveantwort auf einem bestimmten Computer |

## <a name="http-request"></a>HTTP-Anforderung

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a>Anforderungsheader

| Name      | Typ | Beschreibung               |
|---------------|----------|-------------------------------|
| Authorization | Zeichenfolge   | Bearer {token}. Erforderlich. |

## <a name="request-body"></a>Anforderungstext

Empty

## <a name="response"></a>Antwort

Bei erfolgreicher Ausführung gibt die Methode den Antwortcode 200,Ok mit dem Objekt zurück, das den Link zum Befehlsergebnis in der *Werteigenschaft* enthält. Dieser Link ist 30 Minuten gültig und sollte sofort zum Herunterladen des Pakets in einen lokalen Speicher verwendet werden. Ein abgelaufener Link kann durch einen anderen Anruf neu erstellt werden, und es ist nicht erforderlich, die Liveantwort erneut auszuführen.

*Runscript-Transkripteigenschaften:*

| Eigenschaft  | Beschreibung                       |
|---------------|---------------------------------------|
| name          | Name des ausgeführten Skripts                  |
| exit_code     | Ausführungsskript-Exitcode             |
| script_output | Standardausgabe für ausgeführte Skripts       |
| script_error  | Ausführung der Standardfehlerausgabe für Skripts |

## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

**Antwort**

Nachfolgend sehen Sie ein Beispiel der Antwort.

HTTP/1.1 200 Ok

Inhaltstyp: application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

*Dateiinhalt:* 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a>Verwandte Themen

- [Api für Computeraktionen abrufen](get-machineaction-object.md)
- [Computeraktion abbrechen](cancel-machine-action.md)
- [Ausführen einer Liveantwort](run-live-response.md) 

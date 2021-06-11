---
title: machineAction-Ressourcentyp
description: Erfahren Sie mehr über die Methoden und Eigenschaften des MachineAction-Ressourcentyps in Microsoft Defender für Endpunkt.
keywords: APIs, unterstützte APIs, abrufen, MachineAction, zuletzt verwendet
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
ms.openlocfilehash: a3b017a9a05964c15411668787b035f1052c68cf
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878280"
---
# <a name="machineaction-resource-type"></a>MachineAction-Ressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Weitere Informationen finden Sie unter ["Reaktionsaktionen".](respond-machine-alerts.md) 

| Methode                                                            | Rückgabetyp                        | Beschreibung                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [MachineActions auflisten](get-machineactions-collection.md)           | [Computeraktion](machineaction.md) | Computeraktionsentitäten [auflisten.](machineaction.md)           |
| [MachineAction abrufen](get-machineaction-object.md)                  | [Computeraktion](machineaction.md) | Dient zum [](machineaction.md) Abrufen einer einzelnen Computeraktionsentität.     |
| [Untersuchungspaket sammeln](collect-investigation-package.md) | [Computeraktion](machineaction.md) | Erfassen Des Untersuchungspakets von einem [Computer.](machine.md) |
| [SAS-URI für Untersuchungspaket erhalten](get-package-sas-uri.md)       | [Computeraktion](machineaction.md) | Rufen Sie den URI zum Herunterladen des Untersuchungspakets ab.          |
| [Computer isolieren](isolate-machine.md)                             | [Computeraktion](machineaction.md) | Computer [](machine.md) vom Netzwerk isolieren.                 |
| [Computer von Isolation wieder freigeben](unisolate-machine.md)            | [Computeraktion](machineaction.md) | Aufheben [](machine.md) der Computerisolation.               |
| [Einschränken der App-Ausführung](restrict-code-execution.md)              | [Computeraktion](machineaction.md) | Einschränken der Anwendungsausführung.                             |
| [Entfernen von App-Einschränkungen](unrestrict-code-execution.md)            | [Computeraktion](machineaction.md) | Entfernen Sie die Anwendungsausführungseinschränkung.                   |
| [Antivirusscan ausführen](run-av-scan.md)                              | [Computeraktion](machineaction.md) | Führen Sie einen AV-Scan mit Windows Defender aus (falls zutreffend).    |
| [Offboarding des Computers](offboard-machine-api.md)                       | [Computeraktion](machineaction.md) | [Offboard-Computer](machine.md) von Microsoft Defender für Endpunkt. |
| [Beenden und Datei unter Quarantäne stellen](stop-and-quarantine-file.md)           | [Computeraktion](machineaction.md) | Beenden Sie die Ausführung einer Datei auf einem Computer, und löschen Sie sie.        |
| [Ausführen einer Liveantwort](run-live-response.md)                     | [Computeraktion](machineaction.md)  | Führt eine Sequenz von Liveantwortbefehlen auf einem Gerät aus.                       |
| [Abrufen des Ergebnisses der Liveantwort](get-live-response-result.md) | URL-Entität      | Ruft den Downloadlink für bestimmte Liveantwortbefehle über seinen Index ab. |
|[Computeraktion abbrechen](cancel-machine-action.md)                                | [Computeraktion](machineaction.md)  | Abbrechen einer aktiven Computeraktion.                                            |

<br>

## <a name="properties"></a>Eigenschaften

| Eigenschaft            | Typ           | Beschreibung                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                  | Guid           | Die Identität der Computeraktionsentität. [](machineaction.md)                                                                                                                                                     |
| type                | Enum           | Typ der Aktion. Mögliche Werte sind: "RunAntiVirusScan", "Offboard", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" und "UnrestrictCodeExecution" |
| scope               | string         | Bereich der Aktion. "Vollständig" oder "Selektiv" für Isolation, "Schnell" oder "Vollständig" für Antivirenscans.                                                                                                   |
| Anforderer           | Zeichenfolge         | Die Identität der Person, die die Aktion ausgeführt hat.                                                                                                                                                               |
| requestorComment    | Zeichenfolge         | Kommentar, der beim Ausgeben der Aktion geschrieben wurde.                                                                                                                                                              |
| status              | Enum           | Aktueller Status des Befehls. Mögliche Werte sind: "Pending", "InProgress", "Succeeded", "Failed", "TimeOut" und "Canceled".                                                                                 |
| machineId           | Zeichenfolge         | ID des [Computers,](machine.md) auf dem die Aktion ausgeführt wurde.                                                                                                                                              |
| machineId           | Zeichenfolge         | Name des [Computers,](machine.md) auf dem die Aktion ausgeführt wurde.                                                                                                                                            |
| creationDateTimeUtc | DateTimeOffset | Datum und Uhrzeit der Erstellung der Aktion.                                                                                                                                                                 |
| lastUpdateTimeUtc   | DateTimeOffset | Datum und Uhrzeit der letzten Aktualisierung des Aktionsstatus.                                                                                                                                                     |
| relatedFileInfo     | Klasse          | Enthält zwei Eigenschaften. string ```fileIdentifier``` , Enum ```fileIdentifierType``` with the possible values: "Sha1", "Sha256" and "Md5".                                                                         |



## <a name="json-representation"></a>JSON-Darstellung

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```

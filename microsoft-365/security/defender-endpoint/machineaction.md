---
title: machineAction-Ressourcentyp
description: Erfahren Sie mehr über die Methoden und Eigenschaften des MachineAction-Ressourcentyps in Microsoft Defender for Endpoint.
keywords: apis, supported apis, get, machineaction, recent
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
ms.openlocfilehash: da3722294957593fc9cb89abfaec13e45106eefc
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187385"
---
# <a name="machineaction-resource-type"></a>MachineAction-Ressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Weitere Informationen finden Sie unter [Reaktionsaktionen](respond-machine-alerts.md). 

| Methode                                                            | Rückgabetyp                        | Beschreibung                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [Auflisten von MachineActions](get-machineactions-collection.md)           | [Computeraktion](machineaction.md) | Auflisten von Machine Action-Entitäten. [](machineaction.md)           |
| [MachineAction erhalten](get-machineaction-object.md)                  | [Computeraktion](machineaction.md) | Get a [single Machine Action](machineaction.md) entity.     |
| [Untersuchungspaket sammeln](collect-investigation-package.md) | [Computeraktion](machineaction.md) | Erfassen des Untersuchungspakets von einem [Computer](machine.md). |
| [Get investigation package SAS URI](get-package-sas-uri.md)       | [Computeraktion](machineaction.md) | URI zum Herunterladen des Untersuchungspakets herunterladen.          |
| [Computer isolieren](isolate-machine.md)                             | [Computeraktion](machineaction.md) | [Isolieren des](machine.md) Computers vom Netzwerk.                 |
| [Computer aus Isolation lösen](unisolate-machine.md)            | [Computeraktion](machineaction.md) | Computer [aus](machine.md) Isolation los.               |
| [Einschränken der App-Ausführung](restrict-code-execution.md)              | [Computeraktion](machineaction.md) | Einschränken der Anwendungsausführung.                             |
| [Entfernen der App-Einschränkung](unrestrict-code-execution.md)            | [Computeraktion](machineaction.md) | Entfernen der Anwendungsausführungseinschränkung.                   |
| [Ausführen der Antivirenscans](run-av-scan.md)                              | [Computeraktion](machineaction.md) | Führen Sie einen AV-Scan mit Windows Defender (falls zutreffend) aus.    |
| [Offboardcomputer](offboard-machine-api.md)                       | [Computeraktion](machineaction.md) | [Offboardcomputer](machine.md) von Microsoft Defender for Endpoint. |
| [Datei zum Beenden und Isolieren](stop-and-quarantine-file.md)           | [Computeraktion](machineaction.md) | Beenden Sie die Ausführung einer Datei auf einem Computer, und löschen Sie sie.        |

<br>

## <a name="properties"></a>Eigenschaften

| Eigenschaft            | Typ           | Beschreibung                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                  | Guid           | Die Identität der [Machine Action-Entität.](machineaction.md)                                                                                                                                                     |
| type                | Enum           | Typ der Aktion. Mögliche Werte sind: "RunAntiVirusScan", "Offboard", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" und "UnrestrictCodeExecution" |
| scope               | string         | Aktionsbereich. "Vollständig" oder "Selektiv" für Isolation, "Schnell" oder "Vollständig" für Die Virenscans.                                                                                                   |
| requestor           | String         | Die Identität der Person, die die Aktion ausgeführt hat.                                                                                                                                                               |
| requestorComment    | String         | Kommentar, der beim Ausstellen der Aktion geschrieben wurde.                                                                                                                                                              |
| status              | Enum           | Aktueller Status des Befehls. Mögliche Werte sind: "Pending", "InProgress", "Succeeded", "Failed", "TimeOut" und "Canceled".                                                                                 |
| machineId           | String         | ID des [Computers,](machine.md) auf dem die Aktion ausgeführt wurde.                                                                                                                                              |
| machineId           | String         | Name des [Computers,](machine.md) auf dem die Aktion ausgeführt wurde.                                                                                                                                            |
| creationDateTimeUtc | DateTimeOffset | Datum und Uhrzeit, zu dem die Aktion erstellt wurde.                                                                                                                                                                 |
| lastUpdateTimeUtc   | DateTimeOffset | Das letzte Datum und die Uhrzeit, zu der der Aktionsstatus aktualisiert wurde.                                                                                                                                                     |
| relatedFileInfo     | Klasse          | Enthält zwei Eigenschaften. string ```fileIdentifier``` , Enum ```fileIdentifierType``` mit den möglichen Werten: "Sha1", "Sha256" und "Md5".                                                                         |


## <a name="json-representation"></a>Json-Darstellung

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

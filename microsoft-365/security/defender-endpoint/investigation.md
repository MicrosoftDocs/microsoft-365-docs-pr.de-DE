---
title: Ressourcentyp "Untersuchung"
description: Microsoft Defender ATP Investigation-Entität.
keywords: apis, graph api, supported apis, get, alerts, investigations
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 36adf0fa5c0de79fe0616f1216118a98ba2005a4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187246"
---
# <a name="investigation-resource-type"></a>Ressourcentyp "Untersuchung"

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Stellen Sie eine Automatisierte Untersuchungsentität in Defender for Endpoint dar.
<br> Weitere [Informationen finden Sie unter Übersicht](automated-investigations.md) über automatisierte Untersuchungen.

## <a name="methods"></a>Methoden
Methode|Rückgabetyp |Beschreibung
:---|:---|:---
[Auflisten von Untersuchungen](get-investigation-collection.md) | Untersuchungssammlung | Sammlung von Investigation erhalten
[Einzelne Untersuchung erhalten](get-investigation-object.md) | Untersuchungsentität | Ruft eine einzelne Investigation-Entität ab.
[Untersuchung starten](initiate-autoir-investigation.md) | Untersuchungsentität | Startet die Untersuchung auf einem Gerät.


## <a name="properties"></a>Eigenschaften
Eigenschaft |  Typ    |   Beschreibung
:---|:---|:---
id | String | Identität der Untersuchungsentität. 
startTime | DateTime Nullable | Das Datum und die Uhrzeit, zu der die Untersuchung erstellt wurde. 
endTime | DateTime Nullable | Datum und Uhrzeit des Abschlusses der Untersuchung. 
cancelledBy | String | Die ID des Benutzers/der Anwendung, der diese Untersuchung abgebrochen hat. 
investigationState | Enum | Der aktuelle Status der Untersuchung. Mögliche Werte sind: "Unknown", "Terminated", "SuccessfullyRemediated", "Benign", "Failed", "PartiallyRemediated", "Running", "PendingApproval", "PendingResource", "PartiallyInvestigated", "TerminatedByUser", "TerminatedBySystem", "Queued", "InnerFailure", "PreexistingAlert", "UnsupportedOs", "UnsupportedAlertType", "SuppressedAlert".
statusDetails | String | Zusätzliche Informationen zum Untersuchungsstatus.
machineId | String | Die ID des Geräts, auf dem die Untersuchung ausgeführt wird.
computerDnsName | String | Der Name des Geräts, auf dem die Untersuchung ausgeführt wird.
triggeringAlertId | String | Die ID der Warnung, die die Untersuchung ausgelöst hat.


## <a name="json-representation"></a>Json-Darstellung

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```

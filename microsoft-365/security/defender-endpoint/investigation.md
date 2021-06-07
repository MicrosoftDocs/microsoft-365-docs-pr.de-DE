---
title: Untersuchungsressourcentyp
description: Microsoft Defender für Endpunkt-Untersuchungsentität.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnungen, Untersuchungen
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 252b273995d48d523604802c0c4365a613d86dbe
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771729"
---
# <a name="investigation-resource-type"></a>Untersuchungsressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Stellt eine Entität für automatische Untersuchung in Defender für Endpunkt dar.
<br> Weitere Informationen finden Sie [unter "Übersicht über automatisierte Untersuchungen".](automated-investigations.md)

## <a name="methods"></a>Methoden
Methode|Rückgabetyp |Beschreibung
:---|:---|:---
[Auflisten von Untersuchungen](get-investigation-collection.md) | Untersuchungssammlung | Abrufen der Sammlung von Untersuchungen
[Abrufen einer einzelnen Untersuchung](get-investigation-object.md) | Untersuchungsentität | Ruft eine einzelne Untersuchungsentität ab.
[Untersuchung starten](initiate-autoir-investigation.md) | Untersuchungsentität | Startet die Untersuchung auf einem Gerät.


## <a name="properties"></a>Eigenschaften
Eigenschaft |  Typ    |   Beschreibung
:---|:---|:---
id | String | Die Identität der Untersuchungsentität. 
startTime | DateTime lässt Nullwerte zu | Datum und Uhrzeit der Erstellung der Untersuchung. 
endTime | DateTime lässt Nullwerte zu | Datum und Uhrzeit des Abschlusses der Untersuchung. 
cancelledBy | String | Die ID des Benutzers/der Anwendung, die diese Untersuchung abgebrochen hat. 
investigationState | Enum | Der aktuelle Status der Untersuchung. Mögliche Werte sind: 'Unknown', 'Terminated', 'SuccessfullyRemediated', "Gutartig", "Fehlgeschlagen", "PartiallyRemediated", "Running", "PendingApproval", "PendingResource", "PartiallyInvestigated", "TerminatedByUser", "TerminatedBySystem", "Queued", "InnerFailure", "PreexistingAlert", "UnsupportedOs", "UnsupportedAlertType", "SuppressedAlert".
statusDetails | String | Zusätzliche Informationen zum Untersuchungsstatus.
machineId | String | Die ID des Geräts, auf dem die Untersuchung ausgeführt wird.
computerDnsName | String | Der Name des Geräts, auf dem die Untersuchung ausgeführt wird.
triggeringAlertId | String | Die ID der Warnung, die die Untersuchung ausgelöst hat.


## <a name="json-representation"></a>JSON-Darstellung

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

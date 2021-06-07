---
title: Indikatorressourcentyp
description: Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators mit Microsoft Defender für Endpunkt.
keywords: APIs, unterstützte APIs, abrufen, TiIndicator, Indikator, zuletzt verwendet
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
ms.openlocfilehash: 75b62f1bada67c30dc05237a284f8b64c3c7072d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771381"
---
# <a name="indicator-resource-type"></a>Indikatorressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Weitere Informationen finden Sie auf der entsprechenden [Seite "Indikatoren"](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) im Portal. 

Methode|Rückgabetyp |Beschreibung
:---|:---|:---
[Indikatoren auflisten](get-ti-indicators-collection.md) | [Indikator](ti-indicator.md) Auflistung | Listenindikatorentitäten. [](ti-indicator.md)
[Indikator für "Absenden"](post-ti-indicator.md) | [Indikator](ti-indicator.md) | Senden oder Aktualisieren der Indikatorentität. [](ti-indicator.md)
[Importindikatoren](import-ti-indicators.md) | [Indikator](ti-indicator.md) Auflistung | Übermitteln oder Aktualisieren von Indikatorenentitäten. [](ti-indicator.md)
[Indikator löschen](delete-ti-indicator-by-id.md) | Kein Inhalt | Löscht [](ti-indicator.md) die Indikatorentität.


## <a name="properties"></a>Eigenschaften
Eigenschaft |  Typ    |   Beschreibung
:---|:---|:---
id | String | Die Identität [](ti-indicator.md) der Indikatorentität.
indicatorValue | String | Der Wert des [Indikators](ti-indicator.md).
indicatorType | Enum | Typ des Indikators. Mögliche Werte sind: "FileSha1", "FileSha256", "IpAddress", "DomainName" und "Url".
Anwendung | String | Die Anwendung, die dem Indikator zugeordnet ist. 
Aktion | Enum | Die Aktion, die ausgeführt wird, wenn der Indikator in der Organisation erkannt wird. Mögliche Werte sind: "Alert", "AlertAndBlock" und "Allowed".
Sourcetype | Enum | "Benutzer" für den Fall, dass der Indikator von einem Benutzer erstellt wurde (z. B. aus dem Portal), "AadApp" für den Fall, dass er mithilfe einer automatisierten Anwendung über die API übermittelt wurde.
source | Zeichenfolge | Der Name des Benutzers/der Anwendung, die den Indikator übermittelt hat.
createdBy | Zeichenfolge | Eindeutige Identität des Benutzers/der Anwendung, die den Indikator übermittelt hat.
lastUpdatedBy | String | Die Identität des Benutzers/der Anwendung, die den Indikator zuletzt aktualisiert hat.
creationTimeDateTimeUtc | DateTimeOffset | Datum und Uhrzeit der Erstellung des Indikators.
expirationTime | DateTimeOffset | Die Ablaufzeit des Indikators.
lastUpdateTime | DateTimeOffset | Der Zeitpunkt der letzten Aktualisierung des Indikators.
Schweregrad | Enum | Der Schweregrad des Indikators. Mögliche Werte sind: "Informational", "Low", "Medium" und "High".
title | String | Titel des Indikators.
description | String | Beschreibung des Indikators.
recommendedActions | String | Empfohlene Aktionen für den Indikator.
rbacGroupNames | Liste der Zeichenfolgen | RBAC-Gerätegruppennamen, in denen der Indikator verfügbar und aktiv ist. Leere Liste für den Fall, dass sie für alle Geräte verfügbar gemacht wird.


## <a name="json-representation"></a>JSON-Darstellung

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```

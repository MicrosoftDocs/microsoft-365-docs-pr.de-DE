---
title: Indikatorressourcentyp
description: Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators mithilfe von Microsoft Defender for Endpoint.
keywords: apis, supported apis, get, TiIndicator, Indicator, recent
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
ms.openlocfilehash: bbd908c15f4d65d4923c088261c92de6d2d3cc35
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187206"
---
# <a name="indicator-resource-type"></a>Indikatorressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Weitere Informationen finden Sie [auf der entsprechenden Seite Indikatoren](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) im Portal. 

Methode|Rückgabetyp |Beschreibung
:---|:---|:---
[Auflisten von Indikatoren](get-ti-indicators-collection.md) | [Indikator](ti-indicator.md) Sammlung | Auflisten von Indikatorentitäten. [](ti-indicator.md)
[Submit Indicator](post-ti-indicator.md) | [Indikator](ti-indicator.md) | Senden oder Aktualisieren [der Indicator-Entität.](ti-indicator.md)
[Importindikatoren](import-ti-indicators.md) | [Indikator](ti-indicator.md) Sammlung | Senden oder Aktualisieren von Indicators-Entitäten. [](ti-indicator.md)
[Löschindikator](delete-ti-indicator-by-id.md) | Kein Inhalt | Löscht die [Indicator-Entität.](ti-indicator.md)


## <a name="properties"></a>Eigenschaften
Eigenschaft |  Typ    |   Beschreibung
:---|:---|:---
id | String | Identität der [Indicator-Entität.](ti-indicator.md)
indicatorValue | String | Der Wert des [Indikators](ti-indicator.md).
indicatorType | Enum | Typ des Indikators. Mögliche Werte sind: "FileSha1", "FileSha256", "IpAddress", "DomainName" und "Url".
Anwendung | String | Die Anwendung, die dem Indikator zugeordnet ist. 
Aktion | Enum | Die Aktion, die ergriffen wird, wenn der Indikator in der Organisation ermittelt wird. Mögliche Werte sind: "Alert", "AlertAndBlock" und "Allowed".
sourceType | Enum | "User" für den Fall, dass der indikator, der von einem Benutzer (z. B. aus dem Portal) erstellt wurde, "AadApp" für den Fall, dass er mithilfe einer automatisierten Anwendung über die API übermittelt wurde.
source | Zeichenfolge | Der Name des Benutzers/der Anwendung, der den Indikator übermittelt hat.
createdBy | Zeichenfolge | Eindeutige Identität des Benutzers/der Anwendung, der den Indikator übermittelt hat.
lastUpdatedBy | String | Die Identität des Benutzers/der Anwendung, der den Indikator zuletzt aktualisiert hat.
creationTimeDateTimeUtc | DateTimeOffset | Datum und Uhrzeit, zu der der Indikator erstellt wurde.
expirationTime | DateTimeOffset | Die Ablaufzeit des Indikators.
lastUpdateTime | DateTimeOffset | Das letzte Mal, wenn der Indikator aktualisiert wurde.
Schweregrad | Enum | Der Schweregrad des Indikators. mögliche Werte sind: "Informational", "Low", "Medium" und "High".
title | String | Indikatortitel.
description | String | Beschreibung des Indikators.
recommendedActions | String | Empfohlene Aktionen für den Indikator.
rbacGroupNames | Liste der Zeichenfolgen | RBAC-Gerätegruppennamen, bei denen der Indikator verfügbar und aktiv ist. Leere Liste für den Fall, dass sie für alle Geräte verfügbar gemacht wird.


## <a name="json-representation"></a>Json-Darstellung

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

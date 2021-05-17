---
title: Senden oder Aktualisieren der Indikator-API
description: Erfahren Sie, wie Sie die Submit- oder Update Indicator-API verwenden, um eine neue Indicator-Entität in Microsoft Defender for Endpoint zu übermitteln oder zu aktualisieren.
keywords: apis, graph api, supported apis, submit, ti, indicator, update
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
ms.openlocfilehash: 42bab0a9d20d5e1ef78b98b3538cef209240d890
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187254"
---
# <a name="submit-or-update-indicator-api"></a>Senden oder Aktualisieren der Indikator-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-Beschreibung
Sendet oder aktualisiert die neue [Indicator-Entität.](ti-indicator.md)
<br>Die CIDR-Notation für IPs wird nicht unterstützt.

## <a name="limitations"></a>Einschränkungen
1. Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.
2. Es gibt einen Grenzwert von 15.000 aktiven Indikatoren pro Mandant. 


## <a name="permissions"></a>Berechtigungen
Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Erste Schritte](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   Ti.ReadWrite |  "Indikatoren lesen und schreiben"
Anwendung |   Ti.ReadWrite.All |  "Alle Indikatoren lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) |    Ti.ReadWrite |  "Indikatoren lesen und schreiben"


## <a name="http-request"></a>HTTP-Anforderung
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.
Content-Type | Zeichenfolge | application/json. **Erforderlich**.

## <a name="request-body"></a>Anforderungstext
Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:

Parameter | Typ    | Beschreibung
:---|:---|:---
indicatorValue | String | Identität der [Indicator-Entität.](ti-indicator.md) **Required**
indicatorType | Enum | Typ des Indikators. Mögliche Werte sind: "FileSha1", "FileSha256", "IpAddress", "DomainName" und "Url". **Required**
Aktion | Enum | Die Aktion, die ergriffen wird, wenn der Indikator in der Organisation ermittelt wird. Mögliche Werte sind: "Alert", "AlertAndBlock" und "Allowed". **Required**
Anwendung | String | Die Anwendung, die dem Indikator zugeordnet ist. **Optional**
title | String | Titel der Warnung des Indikators. **Required**
description | String | Beschreibung des Indikators. **Required**
expirationTime | DateTimeOffset | Die Ablaufzeit des Indikators. **Optional**
Schweregrad | Enum | Der Schweregrad des Indikators. mögliche Werte sind: "Informational", "Low", "Medium" und "High". **Optional**
recommendedActions | String | Empfohlene Aktionen zur Warnung des TI-Indikators. **Optional**
rbacGroupNames | String | Durch Kommas getrennte Liste der RBAC-Gruppennamen, auf die der Indikator angewendet werden soll. **Optional**


## <a name="response"></a>Antwort
- Wenn die Methode erfolgreich ist, gibt sie den Antwortcode "200 - OK" und die Entität "Erstellt/aktualisiert [Indikator"](ti-indicator.md) im Antworttext zurück.
- Wenn nicht erfolgreich: Diese Methode gibt 400 – Ungültige Anforderung zurück. Ungültige Anforderung gibt in der Regel einen falschen Textkörper an.

## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a>Verwandtes Thema
- [Indikatoren verwalten](manage-indicators.md)

---
title: Übermitteln oder Aktualisieren der Indikator-API
description: Erfahren Sie, wie Sie die Api zum Senden oder Aktualisieren von Indikatoren verwenden, um eine neue Indikatorentität in Microsoft Defender für Endpunkt zu übermitteln oder zu aktualisieren.
keywords: APIs, Graph-API, unterstützte APIs, übermitteln, TI, Indikator, aktualisieren
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
ms.openlocfilehash: ce0dc0ce255e9717082687bd1f8bf5941739261d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771705"
---
# <a name="submit-or-update-indicator-api"></a>Übermitteln oder Aktualisieren der Indikator-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-Beschreibung
Sendet oder aktualisiert [](ti-indicator.md) die neue Indikatorentität.
<br>Die CIDR-Notation für IPs wird nicht unterstützt.

## <a name="limitations"></a>Begrenzungen
1. Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.
2. Es gibt einen Grenzwert von 15.000 aktiven Indikatoren pro Mandant. 


## <a name="permissions"></a>Berechtigungen
Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter ["Erste Schritte".](apis-intro.md)

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
Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:

Parameter | Typ    | Beschreibung
:---|:---|:---
indicatorValue | String | Die Identität [](ti-indicator.md) der Indikatorentität. **Required**
indicatorType | Enum | Typ des Indikators. Mögliche Werte sind: "FileSha1", "FileSha256", "IpAddress", "DomainName" und "Url". **Required**
Aktion | Enum | Die Aktion, die ausgeführt wird, wenn der Indikator in der Organisation erkannt wird. Mögliche Werte sind: "Alert", "AlertAndBlock" und "Allowed". **Required**
Anwendung | String | Die Anwendung, die dem Indikator zugeordnet ist. **Optional**
title | String | Titel der Indikatorwarnung. **Required**
description | String | Beschreibung des Indikators. **Required**
expirationTime | DateTimeOffset | Die Ablaufzeit des Indikators. **Optional**
Schweregrad | Enum | Der Schweregrad des Indikators. Mögliche Werte sind: "Informational", "Low", "Medium" und "High". **Optional**
recommendedActions | String | Empfohlene Aktionen für TI-Indikatorwarnung. **Optional**
rbacGroupNames | String | Durch Trennzeichen getrennte Liste der RBAC-Gruppennamen, auf die der Indikator angewendet werden würde. **Optional**


## <a name="response"></a>Antwort
- Wenn die Methode erfolgreich ist, werden der Antwortcode 200 – OK und die erstellte/aktualisierte [Indikatorentität](ti-indicator.md) im Antworttext zurückgegeben.
- Wenn nicht erfolgreich: Diese Methode gibt "400 – Ungültige Anforderung" zurück. Eine ungültige Anforderung weist in der Regel auf einen falschen Textkörper hin.

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

---
title: Import Indicators API
description: Erfahren Sie, wie Sie den Importbatch der Indikator-API in Microsoft Defender for Endpoint verwenden.
keywords: apis, supported apis, submit, ti, indicator, update
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198245"
---
# <a name="import-indicators-api"></a>Import Indicators API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung
Sendet oder aktualisiert [](ti-indicator.md) Batch von Indicator-Entitäten.
<br>Die CIDR-Notation für IPs wird nicht unterstützt.

## <a name="limitations"></a>Einschränkungen
1. Die Geschwindigkeitseinschränkungen für diese API liegen bei 30 Anrufen pro Minute.
2. Es gibt einen Grenzwert von 15.000 aktiven [Indikatoren](ti-indicator.md) pro Mandant. 
3. Die maximale Batchgröße für einen API-Aufruf beträgt 500.

## <a name="permissions"></a>Berechtigungen
Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Erste Schritte](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   Ti.ReadWrite |  "Indikatoren lesen und schreiben"
Anwendung |   Ti.ReadWrite.All |  "Alle Indikatoren lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) |    Ti.ReadWrite |  "Indikatoren lesen und schreiben"


## <a name="http-request"></a>HTTP-Anforderung
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
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
Indikatoren | Auflisten<[Indikators](ti-indicator.md)> | Liste der [Indikatoren](ti-indicator.md). **Required**


## <a name="response"></a>Antwort
- Wenn die Methode erfolgreich ist, gibt sie den Antwortcode 200 – OK mit einer Liste der Importergebnisse pro Indikator zurück, siehe Beispiel unten.
- Wenn nicht erfolgreich: Diese Methode gibt 400 – Ungültige Anforderung zurück. Ungültige Anforderung gibt in der Regel einen falschen Textkörper an.

## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

**Antwort**

Nachfolgend sehen Sie ein Beispiel der Antwort.

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a>Verwandtes Thema
- [Indikatoren verwalten](manage-indicators.md)

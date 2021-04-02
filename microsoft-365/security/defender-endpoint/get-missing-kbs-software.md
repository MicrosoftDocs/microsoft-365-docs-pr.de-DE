---
title: Fehlende KBs nach Software-ID erhalten
description: Ruft fehlende Sicherheitsupdates nach Software-ID ab
keywords: apis, graph api, supported apis, get, list, file, information, software id, threat & vulnerability management api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: e5d84a3eadab85713779dd70848bc11d27484dcc
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499394"
---
# <a name="get-missing-kbs-by-software-id"></a>Fehlende KBs nach Software-ID erhalten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Ruft fehlende KBs (Sicherheitsupdates) nach Software-ID ab

## <a name="permissions"></a>Berechtigungen

Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.

Berechtigungstyp |   Berechtigung   |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |Software.Read.All |   "Informationen zur Software zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Software.Read |   "Informationen zur Software zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"

## <a name="http-request"></a>HTTP-Anforderung

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | Zeichenfolge | Bearer {token}. **Erforderlich**.

## <a name="request-body"></a>Anforderungstext

Empty

## <a name="response"></a>Antwort

Wenn die Methode erfolgreich ist, gibt sie 200 OK zurück, und die angegebene Software enthält keine KB-Daten im Textkörper.

## <a name="example"></a>Beispiel

### <a name="request"></a>Anforderung

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a>Antwort

Nachfolgend sehen Sie ein Beispiel der Antwort.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a>Verwandte Themen

- [Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Softwareinventar & Sicherheitsrisiko](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)

---
title: Alle Sicherheitsrisiken per Computer und Software erhalten
description: Ruft eine Liste aller Sicherheitsrisiken ab, die die Organisation durch Computer und Software betreffen
keywords: apis, graph api, supported apis, get, vulnerability information, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 229c1f9e77a0cb85744155e82934b48dd63052b2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933409"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a>Auflisten von Sicherheitsrisiken nach Computer und Software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Ruft eine Liste aller Sicherheitsrisiken ab, die die Organisation pro [Computer und Software](machine.md) [betreffen.](software.md)
- Wenn die Sicherheitsanfälligkeit über eine Behebungs-KB verfügt, wird sie in der Antwort angezeigt.
- Unterstützt [OData V4-Abfragen](https://www.odata.org/documentation/).
- Das OData ```$filter``` wird für alle Eigenschaften unterstützt.

>[!Tip]
>Dies ist eine großartige API für [Power BI Integration.](api-power-bi.md)

## <a name="permissions"></a>Berechtigungen
Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   Vulnerability.Read.All |    "Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Vulnerability.Read |   "Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen"

## <a name="http-request"></a>HTTP-Anforderung
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.


## <a name="request-body"></a>Anforderungstext
Empty

## <a name="response"></a>Antwort
Wenn die Methode erfolgreich ist, gibt sie 200 OK mit der Liste der Sicherheitsrisiken im Textkörper zurück.


## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

**Antwort**

Nachfolgend sehen Sie ein Beispiel der Antwort.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a>Siehe auch

- [Risikobasierte Bedrohungs- und Sicherheitsrisikomanagement](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Sicherheitsrisiken in Ihrer Organisation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)

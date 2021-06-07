---
title: Softwareversionsverteilung auflisten
description: Ruft eine Liste der Softwareversionsverteilung Ihrer Organisation ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Softwareversionsverteilung, Microsoft Defender für Endpunkt-TVM-API
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7ac7fdf4c38846e2e8be614567ddb87a98e3a96c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772125"
---
# <a name="list-software-version-distribution"></a>Softwareversionsverteilung auflisten 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Ruft eine Liste der Softwareversionsverteilung Ihrer Organisation ab. 

## <a name="permissions"></a>Berechtigungen
Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung | Software.Read.All | "Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Software.Read | "Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"

## <a name="http-request"></a>HTTP-Anforderung
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a>Anforderungsheader

| Name        | Typ | Beschreibung
|:--------------|:-------|:--------------|
| Authorization | String | Bearer {token}. **Erforderlich.**

## <a name="request-body"></a>Anforderungstext
Empty

## <a name="response"></a>Antwort
Wenn die Methode erfolgreich ist, wird 200 OK mit einer Liste von Softwareverteilungsdaten im Text zurückgegeben. 


## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

**Antwort**

Nachfolgend sehen Sie ein Beispiel der Antwort.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Verwandte Themen
- [Risikobasiertes Bedrohungs- & Vulnerability Management](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Softwareinventarisierung von Sicherheitsrisiken &](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)

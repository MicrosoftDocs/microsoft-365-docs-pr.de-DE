---
title: Auflisten von Sicherheitsrisiken nach Empfehlung
description: Ruft eine Liste der Sicherheitsrisiken ab, die der Sicherheitsempfehlung zugeordnet sind.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Liste der Sicherheitsrisiken, Sicherheitsempfehlungen, Sicherheitsempfehlungen für Sicherheitsrisiken, Bedrohungs- und Sicherheitsrisikomanagement, Bedrohungs- und Sicherheitsrisikomanagement-API
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
ms.openlocfilehash: d5a59c3cd57aa369b1edb46eebddffb84a2b8c78
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845150"
---
# <a name="list-vulnerabilities-by-recommendation"></a>Auflisten von Sicherheitsrisiken nach Empfehlung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Ruft eine Liste der Sicherheitsrisiken ab, die der Sicherheitsempfehlung zugeordnet sind.

## <a name="permissions"></a>Berechtigungen
Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   SecurityRecommendation.Read.All |   "Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | SecurityRecommendation.Read |  "Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"

## <a name="http-request"></a>HTTP-Anforderung
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.


## <a name="request-body"></a>Anforderungstext
Empty

## <a name="response"></a>Antwort
Wenn die Methode erfolgreich ist, wird 200 OK zurückgegeben, wobei die Liste der Sicherheitsrisiken der Sicherheitsempfehlung zugeordnet ist.


## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

**Antwort**

Nachfolgend sehen Sie ein Beispiel der Antwort.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-13748",
            "name": "CVE-2019-13748",
            "description": "Insufficient policy enforcement in developer tools in Google Chrome prior to 79.0.3945.79 allowed a local attacker to obtain potentially sensitive information from process memory via a crafted HTML page.",
            "severity": "Medium",
            "cvssV3": 6.5,
            "exposedMachines": 0,
            "publishedOn": "2019-12-10T00:00:00Z",
            "updatedOn": "2019-12-16T12:15:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
        ...
     ]
}
```

## <a name="related-topics"></a>Verwandte Themen
- [Risikobasiertes Bedrohungs- & Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Sicherheitsempfehlungen für Sicherheitsrisiken &](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

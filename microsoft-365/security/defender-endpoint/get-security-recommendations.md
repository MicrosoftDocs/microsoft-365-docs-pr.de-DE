---
title: Erhalten von Sicherheitsempfehlungen
description: Ruft eine Sammlung von Sicherheitsempfehlungen im Zusammenhang mit einer bestimmten Geräte-ID ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Liste, Datei, Informationen, Sicherheitsempfehlungen pro Gerät, Api für Bedrohungen & Sicherheitsrisikomanagement, Microsoft Defender für Endpunkt-TVM-API
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
ms.openlocfilehash: 4498761fd21331821cf4676bfe65630be5436ce5
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845131"
---
# <a name="get-security-recommendations"></a>Erhalten von Sicherheitsempfehlungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Ruft eine Sammlung von Sicherheitsempfehlungen im Zusammenhang mit einer bestimmten Geräte-ID ab.

## <a name="permissions"></a>Berechtigungen
Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung | SecurityRecommendation.Read.All | "Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | SecurityRecommendation.Read |  "Sicherheitsempfehlungen zu Bedrohungs- und Sicherheitsrisikoverwaltung lesen"

## <a name="http-request"></a>HTTP-Anforderung
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.


## <a name="request-body"></a>Anforderungstext
Empty

## <a name="response"></a>Antwort
Wenn die Methode erfolgreich ist, wird 200 OK mit den Sicherheitsempfehlungen im Text zurückgegeben.


## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

**Antwort**

Nachfolgend sehen Sie ein Beispiel der Antwort.


```
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-git-scm-_-git",
            "productName": "git",
            "recommendationName": "Update Git to version 2.24.1.2",
            "weaknesses": 3,
            "vendor": "git-scm",
            "recommendedVersion": "2.24.1.2",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": false,
            "activeAlert": false,
            "associatedThreats": [],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 0,
            "totalMachineCount": 0,
            "exposedMachinesCount": 1,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Git"
        },
…
}
```

## <a name="related-topics"></a>Verwandte Themen
- [Risikobasiertes Bedrohungs- & Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Sicherheitsempfehlungen für Sicherheitsrisiken &](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

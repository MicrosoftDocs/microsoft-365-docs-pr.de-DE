---
title: Erhalten des Gefährdungsscores
description: Ruft die Belichtungsbewertung der Organisation ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Belichtungsbewertung, Belichtungsbewertung der Organisation
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 071b0e7597d334fe06d5045e06a5c4d82dd65609
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845390"
---
# <a name="get-exposure-score"></a>Erhalten des Gefährdungsscores

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

Ruft die Belichtungsbewertung der Organisation ab.

## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
:---|:---|:---
Anwendung | Score.Read.All | "Bewertung der Bedrohungs- und Sicherheitsrisikoverwaltung lesen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Score.Read | "Bewertung der Bedrohungs- und Sicherheitsrisikoverwaltung lesen"

## <a name="http-request"></a>HTTP-Anforderung

```
GET /api/exposureScore
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.

## <a name="request-body"></a>Anforderungstext

Empty

## <a name="response"></a>Antwort

Wenn die Methode erfolgreich ist, wird 200 OK mit den Belichtungsdaten im Antworttext zurückgegeben.

## <a name="example"></a>Beispiel

### <a name="request"></a>Anforderung

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a>Antwort

Nachfolgend sehen Sie ein Beispiel der Antwort.

>[!NOTE]
>Die hier gezeigte Antwortliste ist möglicherweise aus Platzgründen abgeschnitten. 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a>Siehe auch

- [Risikobasiertes Bedrohungs- & Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Sicherheitsrisikobewertung & Bedrohungsrisiko](/microsoft-365/security/defender-endpoint/tvm-exposure-score)

---
title: Auflisten von Geräten nach Software
description: Rufen Sie eine Liste der Geräte ab, auf der diese Software installiert ist.
keywords: apis, graph api, supported apis, get, list devices, devices list, list devices by software, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: ff0bb9a6f17b8d4dc6432292ec98743d3eaf952c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929097"
---
# <a name="list-devices-by-software"></a>Auflisten von Geräten nach Software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Rufen Sie eine Liste der Geräteverweise ab, auf die diese Software installiert ist.

## <a name="permissions"></a>Berechtigungen
Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung | Software.Read.All | "Informationen zur Software zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Software.Read | "Informationen zur Software zur Bedrohungs- und Sicherheitsrisikoverwaltung lesen"

## <a name="http-request"></a>HTTP-Anforderung
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a>Anforderungsheader

| Name        | Typ | Beschreibung
|:--------------|:-------|:--------------|
| Authorization | Zeichenfolge | Bearer {token}. **Erforderlich.**

## <a name="request-body"></a>Anforderungstext
Empty

## <a name="response"></a>Antwort
Wenn die Methode erfolgreich ist, werden 200 OK und eine Liste der Geräte zurückgegeben, deren Software im Textkörper installiert ist. 


## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

**Antwort**

Nachfolgend sehen Sie ein Beispiel der Antwort.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Verwandte Themen
- [Risikobasiertes Bedrohungs- & Sicherheitsrisikomanagement](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Softwareinventar & Sicherheitsrisiko](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)

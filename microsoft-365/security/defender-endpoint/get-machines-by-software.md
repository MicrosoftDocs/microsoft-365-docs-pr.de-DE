---
title: Auflisten von Geräten nach Software
description: Rufen Sie eine Liste der Geräte ab, auf denen diese Software installiert ist.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Listengeräte, Geräteliste, Listengeräte nach Software, Microsoft Defender für Endpunkt-TVM-API
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
ms.openlocfilehash: e1adf28823d6b86417c32578a89480958946c50d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770554"
---
# <a name="list-devices-by-software"></a>Auflisten von Geräten nach Software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Rufen Sie eine Liste der Geräteverweise ab, auf denen diese Software installiert ist.

## <a name="permissions"></a>Berechtigungen
Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung | Software.Read.All | "Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Software.Read | "Informationen zur Bedrohungs- und Sicherheitsrisikoverwaltungssoftware lesen"

## <a name="http-request"></a>HTTP-Anforderung
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a>Anforderungsheader

| Name        | Typ | Beschreibung
|:--------------|:-------|:--------------|
| Authorization | String | Bearer {token}. **Erforderlich.**

## <a name="request-body"></a>Anforderungstext
Empty

## <a name="response"></a>Antwort
Wenn die Methode erfolgreich ist, werden 200 OK und eine Liste der Geräte mit der im Textkörper installierten Software zurückgegeben. 


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
- [Risikobasiertes Bedrohungs- & Vulnerability Management](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Softwareinventarisierung von Sicherheitsrisiken &](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)

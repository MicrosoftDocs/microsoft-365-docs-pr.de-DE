---
title: Abrufen der KB-Auflistungs-API
description: Rufen Sie eine Sammlung von Wissensdatenbanken (KB) und KB-Details mit Microsoft Defender for Endpoint ab.
keywords: apis, graph api, supported apis, get, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166728"
---
# <a name="get-kb-collection-api"></a>Abrufen der KB-Auflistungs-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Ruft eine Auflistung von KB- und KB-Details ab.

## <a name="permissions"></a>Berechtigungen
Der Benutzer benötigt Leseberechtigungen.

## <a name="http-request"></a>HTTP-Anforderung
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a>Anforderungsheader

Kopfzeile | Wert 
:---|:---
Authorization | Bearer {token}. **Erforderlich**.
Inhaltstyp | application/json

## <a name="request-body"></a>Anforderungstext
Empty

## <a name="response"></a>Antwort
Wenn erfolgreich – 200 OK.

## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

**Antwort**

Nachfolgend sehen Sie ein Beispiel der Antwort.

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```

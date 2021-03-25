---
title: Abrufen der RBAC-Computergruppensammlungs-API
description: Erfahren Sie, wie Sie die KB-Auflistungs-API abrufen verwenden, um eine Auflistung von RBAC-Gerätegruppen in Microsoft Defender Advanced Threat Protection abzurufen.
keywords: apis, graph api, supported apis, get, RBAC, group
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.date: 10/07/2018
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166650"
---
# <a name="get-kb-collection-api"></a>Abrufen der KB-Auflistungs-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Ruft eine Auflistung von RBAC-Gerätegruppen ab.

## <a name="permissions"></a>Berechtigungen
Der Benutzer benötigt Leseberechtigungen.

## <a name="http-request"></a>HTTP-Anforderung
```
GET /testwdatppreview/machinegroups
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

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

**Antwort**

Nachfolgend sehen Sie ein Beispiel der Antwort.
Die Feld-ID  enthält die Gerätegruppen-ID und entspricht dem Feld **rbacGroupId** in Geräteinformationen. Feld **ungrouped** ist nur für eine Gruppe für alle Geräte true, die keiner Gruppe zugewiesen wurden. Diese Gruppe hat wie gewohnt den Namen "UnassignedGroup".

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```

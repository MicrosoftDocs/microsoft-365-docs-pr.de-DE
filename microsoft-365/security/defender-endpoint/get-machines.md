---
title: Computer-API auflisten
description: Hier erfahren Sie, wie Sie die Api "Computer auflisten" verwenden, um eine Sammlung von Computern abzurufen, die mit der Microsoft Defender for Endpoint-Cloud kommuniziert haben.
keywords: apis, graph api, supported apis, get, devices
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 01e36427116ad7bd845901e7da7f5aa152bd44f9
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893353"
---
# <a name="list-machines-api"></a>Computer-API auflisten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-Beschreibung
Ruft eine Sammlung von Computern [ab,](machine.md) die mit der Microsoft Defender for Endpoint-Cloud kommuniziert haben.
<br>Unterstützt [OData V4-Abfragen](https://www.odata.org/documentation/).
<br>Die OData-Abfrage `$filter` wird unterstützt unter: , `computerDnsName` , , , und `lastSeen` `healthStatus` `osPlatform` `riskScore` `rbacGroupId` .
<br>Beispiele finden Sie unter [OData-Abfragen mit Defender for Endpoint](exposed-apis-odata-samples.md)


## <a name="limitations"></a>Einschränkungen
1. Sie können Geräte nach Ihrem konfigurierten Aufbewahrungszeitraum zuletzt sehen.
2. Die maximale Seitengröße beträgt 10.000.
3. Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde. 


## <a name="permissions"></a>Berechtigungen

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   Machine.Read.All |  "Alle Computerprofile lesen"
Anwendung |   Machine.ReadWrite.All | "Alle Computerinformationen lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Machine.Read | "Computerinformationen lesen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Machine.ReadWrite | "Computerinformationen lesen und schreiben"

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>- Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)
>- Die Antwort umfasst nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).

## <a name="http-request"></a>HTTP-Anforderung

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.


## <a name="request-body"></a>Anforderungstext
Empty

## <a name="response"></a>Antwort
Wenn erfolgreich und Computer vorhanden sind – [](machine.md) 200 OK mit der Liste der Computerentitäten im Textkörper. Wenn keine aktuellen Computer – 404 Nicht gefunden.


## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

**Antwort**

Nachfolgend sehen Sie ein Beispiel der Antwort.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Verwandte Themen
- [OData-Abfragen mit Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)

---
title: Abrufen der IP-Statistik-API
description: Mit Microsoft Defender for Endpoint erhalten Sie die neuesten Statistiken für Ihre IP.
keywords: apis, graph api, supported apis, get, ip, statistics, prevalence
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: c47a5e58b1888447a4428fad78e71b85cfe79b69
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166729"
---
# <a name="get-ip-statistics-api"></a>Abrufen der IP-Statistik-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-Beschreibung
Ruft die Statistiken für die angegebene IP ab.

## <a name="limitations"></a>Einschränkungen
1. Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.

## <a name="permissions"></a>Berechtigungen
Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   Ip.Read.All |   "Lesen von IP-Adressprofilen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Ip.Read.All |  "Lesen von IP-Adressprofilen"

>[!NOTE]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>- Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Daten anzeigen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)

## <a name="http-request"></a>HTTP-Anforderung

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.

## <a name="request-uri-parameters"></a>Anforderungs-URI-Parameter

Name | Typ | Beschreibung
:---|:---|:---
lookBackHours | Int32 | Definiert die Stunden, die wir zurücksuchen, um die Statistiken zu erhalten. Standardmäßig 30 Tage. **Optional**.

## <a name="request-body"></a>Anforderungstext
Empty

## <a name="response"></a>Antwort
Wenn erfolgreich und ip vorhanden ist – 200 OK mit statistischen Daten im Textkörper. IP nicht vorhanden – 404 Nicht gefunden.


## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

**Antwort**

Nachfolgend sehen Sie ein Beispiel der Antwort.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "orgPrevalence": "63515",
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| Name | Beschreibung |
| :--- | :---------- |
| Organisationsprävalenz | die unterschiedliche Anzahl von Geräten, die die Netzwerkverbindung zu dieser IP geöffnet haben. |
| Org first seen | die erste Verbindung für diese IP in der Organisation. |
| Organisation zuletzt gesehen  | die letzte Verbindung für diese IP in der Organisation. |

> [!NOTE]
> Diese Statistikinformationen basieren auf Daten aus den letzten 30 Tagen. 

---
title: Isolieren der Computer-API
description: Hier erfahren Sie, wie Sie die Api "Computer isolieren" verwenden, um ein Gerät vom Zugriff auf ein externes Netzwerk in Microsoft Defender for Endpoint zu isolieren.
keywords: apis, graph api, supported apis, isolate device
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
ms.openlocfilehash: b9c8d4da528ba065dc1b4a68ddaa816a1ad78c4a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187832"
---
# <a name="isolate-machine-api"></a>Isolieren der Computer-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung
Isoliert ein Gerät vom Zugriff auf ein externes Netzwerk.


## <a name="limitations"></a>Einschränkungen
1. Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>Berechtigungen
Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   Machine.Isolate |   "Computer isolieren"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Machine.Isolate |  "Computer isolieren"

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>- Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Aktive Korrekturaktionen" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)
>- Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen).


## <a name="http-request"></a>HTTP-Anforderung
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.
Content-Type | Zeichenfolge | application/json. **Erforderlich**.

## <a name="request-body"></a>Anforderungstext
Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:

Parameter | Typ    | Beschreibung
:---|:---|:---
Kommentar |   Zeichenfolge |    Kommentar, der der Aktion zugeordnet werden soll. **Erforderlich**.
IsolationType   | String |  Typ der Isolation. Zulässige Werte sind: "Vollständig" oder "Selektiv".

**IsolationType** steuert den typ der durchzuführende Isolation und kann einer der folgenden Sein:
- Vollständig – Vollständige Isolation
- Selektiv – Beschränken Sie den Zugriff auf das Netzwerk nur auf begrenzte Anwendungen (weitere Informationen finden Sie unter [Isolieren](respond-machine-alerts.md#isolate-devices-from-the-network) von Geräten aus dem Netzwerk)


## <a name="response"></a>Antwort
Wenn die Methode erfolgreich ist, wird 201 – Antwortcode erstellt und [Computeraktion](machineaction.md) im Antworttext zurückgegeben.


## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- Informationen zur Isolierung eines Geräts finden Sie unter [Release device from isolation](unisolate-machine.md).

---
title: Festlegen der Gerätewert-API
description: Erfahren Sie, wie Sie den Wert eines Geräts mithilfe einer Microsoft Defender for Endpoint-API angeben.
keywords: apis, graph api, supported apis, tags, machine tags
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 76df62243db837ec91819497980ff1de2295e3b6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498315"
---
# <a name="set-device-value-api"></a>Festlegen der Gerätewert-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung

Legen Sie den Gerätewert eines bestimmten Computers [.](machine.md)<br>
Weitere [Informationen finden Sie unter Zuweisen von](tvm-assign-device-value.md) Gerätewerten.

## <a name="limitations"></a>Einschränkungen

1. Sie können auf Geräten posten, die zuletzt gemäß Ihrem konfigurierten Aufbewahrungszeitraum angezeigt wurden.

2. Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.


## <a name="permissions"></a>Berechtigungen

Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Berechtigungstyp |    Berechtigung    |    Anzeigename der Berechtigung
:---|:---|:---
Anwendung |    Machine.ReadWrite.All |    "Alle Computerinformationen lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Machine.ReadWrite | "Computerinformationen lesen und schreiben"

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>
>- Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Sicherheitseinstellung verwalten". Weitere Informationen finden Sie unter [Erstellen und Verwalten von](user-roles.md) Rollen.
>- Der Benutzer muss auf der Grundlage der Computergruppeneinstellungen auf den Computer zugreifen können (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Computergruppen).

## <a name="http-request"></a>HTTP-Anforderung

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.
Content-Type | Zeichenfolge | application/json. **Erforderlich**.

## <a name="request-body"></a>Anforderungstext

Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:

Parameter |    Typ    | Beschreibung
:---|:---|:---
DeviceValue |    Enum |    Gerätewert. Zulässige Werte sind: "Normal", "Niedrig" und "Hoch". **Erforderlich**.

## <a name="response"></a>Antwort

Wenn die Methode erfolgreich ist, werden der Antwortcode 200 – Ok und der aktualisierte Computer im Antworttext zurückgegeben.

## <a name="example"></a>Beispiel

**Anforderung**

Im Folgenden finden Sie ein Beispiel für eine Anforderung, die ein Computertag hinzufügt.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```

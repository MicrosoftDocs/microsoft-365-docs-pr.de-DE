---
title: Festlegen der Gerätewert-API
description: Erfahren Sie, wie Sie den Wert eines Geräts mithilfe einer Microsoft Defender für Endpunkt-API angeben.
keywords: APIs, Graph-API, unterstützte APIs, Tags, Computertags
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: e14e696169a2d1cd76e4fb5b2ee8de951e9e1280
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771405"
---
# <a name="set-device-value-api"></a>Festlegen der Gerätewert-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung

Legen Sie den Gerätewert eines bestimmten [Computers fest.](machine.md)<br>
Weitere Informationen finden Sie unter ["Zuweisen von Gerätewerten".](tvm-assign-device-value.md)

## <a name="limitations"></a>Begrenzungen

1. Sie können Beiträge auf Geräten veröffentlichen, die zuletzt gemäß Ihrem konfigurierten Aufbewahrungszeitraum angezeigt wurden.

2. Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.


## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)

Berechtigungstyp |    Berechtigung    |    Anzeigename der Berechtigung
:---|:---|:---
Anwendung |    Machine.ReadWrite.All |    "Alle Computerinformationen lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Machine.ReadWrite | "Lesen und Schreiben von Computerinformationen"

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>
>- Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Sicherheitseinstellung verwalten". Weitere Informationen (weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen)](user-roles.md)
>- Der Benutzer muss basierend auf den Computergruppeneinstellungen Zugriff auf den Computer haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Computergruppen).](machine-groups.md)

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

Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:

Parameter |    Typ    | Beschreibung
:---|:---|:---
DeviceValue |    Enum |    Gerätewert. Zulässige Werte sind: "Normal", "Niedrig" und "Hoch". **Erforderlich**.

## <a name="response"></a>Antwort

Wenn die Methode erfolgreich ist, werden der Antwortcode "200 – Ok" und der aktualisierte Computer im Antworttext zurückgegeben.

## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel für eine Anforderung, die ein Computertag hinzufügt.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```

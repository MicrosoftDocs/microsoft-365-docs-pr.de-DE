---
title: Aktualisieren der Computerentitäts-API
description: Erfahren Sie, wie Sie Computertags mithilfe dieser API aktualisieren. Sie können die Tags und Gerätewerteigenschaften aktualisieren.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnung, Informationen, ID
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985747"
---
# <a name="update-machine"></a>Aktualisieren des Computers 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung
Aktualisiert die Eigenschaften des vorhandenen [Computers.](machine.md)
<br>Aktualisierbare Eigenschaften sind: ```machineTags``` und ```deviceValue``` .


## <a name="limitations"></a>Einschränkungen
1. Sie können Computer aktualisieren, die in der API verfügbar sind. 
2. Der Updatecomputer fügt nur Tags an die Tagsammlung an. Wenn Tags vorhanden sind, müssen sie in die Tagssammlung im Textkörper eingeschlossen werden.
3. Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.


## <a name="permissions"></a>Berechtigungen
Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Application |   Machine.ReadWrite.All | "Lesen und Schreiben von Computerinformationen für alle Computer"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Machine.ReadWrite | "Lesen und Schreiben von Computerinformationen"

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>- Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Warnungsuntersuchung". Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md)
>- Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben, das der Warnung zugeordnet ist. Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen.](machine-groups.md)

## <a name="http-request"></a>HTTP-Anforderung
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | Zeichenfolge | Bearer {token}. **Erforderlich**.
Content-Type | Zeichenfolge | application/json. **Erforderlich**.


## <a name="request-body"></a>Anforderungstext
Geben Sie im Anforderungstext die Werte für die relevanten Felder an, die aktualisiert werden sollen.
<br>Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre vorherigen Werte oder werden basierend auf Änderungen an anderen Eigenschaftswerten neu berechnet. 
<br>Um eine optimale Leistung zu erzielen, sollten Sie vorhandene Werte, die sich nicht geändert haben, nicht einschließen.

Eigenschaft | Typ | Beschreibung
:---|:---|:---
machineTags | String-Sammlung | Satz [](machine.md) von Computertags.
deviceValue | Nullable Enum | Der [Wert des Geräts.](tvm-assign-device-value.md) Mögliche Werte sind: 'Normal', 'Low' und 'High'.

## <a name="response"></a>Antwort
Wenn die Methode erfolgreich ist, werden 200 OK und die [Computerentität](machine.md) im Antworttext mit den aktualisierten Eigenschaften zurückgegeben. Wenn die Sammlung von Computertags im Textkörper keine vorhandenen Computertags enthält– 400 Ungültige Eingabe und eine Meldung, die über die fehlenden Tags informiert.
Wenn der Computer mit der angegebenen ID nicht gefunden wurde – 404 Nicht gefunden.


## <a name="example"></a>Beispiel

**Anforderung**

Hier ist ein Beispiel für die Anforderung.

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```

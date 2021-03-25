---
title: Erstellen einer Warnung aus der Ereignis-API
description: Erfahren Sie, wie Sie mithilfe der Warnungs-API erstellen eine neue Warnung über Ereignis in Microsoft Defender for Endpoint erstellen.
keywords: apis, graph api, supported apis, get, alert, information, id
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
ms.openlocfilehash: 9066bcdae549f7a6b1372714d567674eb03c1e51
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166674"
---
# <a name="create-alert-api"></a>Erstellen einer Warnungs-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung
Erstellt neue [Warnung](alerts.md) über **Ereignis**.
<br>**Microsoft Defender for Endpoint Event** ist für die Warnungserstellung erforderlich.
<br>Sie müssen 3 Parameter aus dem Ereignis in der Anforderung angeben: **Ereigniszeit**, **Computer-ID** und **Berichts-ID**. Siehe Beispiel unten.
<br>Sie können ein Ereignis in advanced Hunting API oder Portal verwenden.
<br>Wenn auf demselben Gerät mit demselben Titel eine offene Warnung vorhanden ist, wird die neu erstellte Warnung mit ihr zusammengeführt.
<br>Eine automatische Untersuchung wird automatisch für Warnungen gestartet, die über die API erstellt wurden.


## <a name="limitations"></a>Einschränkungen
1. Die Geschwindigkeitseinschränkungen für diese API sind 15 Aufrufe pro Minute.


## <a name="permissions"></a>Berechtigungen

Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   Alerts.ReadWrite.All |  "Alle Warnungen lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Alert.ReadWrite | "Warnungen lesen und schreiben"

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>- Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Warnungsuntersuchung" (Weitere Informationen finden Sie unter [Erstellen](user-roles.md) und Verwalten von Rollen)
>- Der Benutzer muss auf das Gerät zugreifen können, das der Warnung zugeordnet ist, basierend auf den Gerätegruppeneinstellungen (Weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Gerätegruppen)

## <a name="http-request"></a>HTTP-Anforderung

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.
Content-Type | Zeichenfolge | application/json. **Erforderlich**.

## <a name="request-body"></a>Anforderungstext

Geben Sie im Anforderungstext die folgenden Werte an (alle sind erforderlich):

Eigenschaft | Typ | Beschreibung
:---|:---|:---
eventTime | DateTime(UTC) | Die genaue Uhrzeit des Ereignisses als Zeichenfolge, wie von der erweiterten Suche erhalten. z. B. ```2018-08-03T16:45:21.7115183Z``` **Erforderlich.**
reportId | String | Die reportId des Ereignisses, wie von der erweiterten Suche erhalten. **Erforderlich**.
machineId | String | Id des Geräts, auf dem das Ereignis identifiziert wurde. **Erforderlich**.
Schweregrad | String | Der Schweregrad der Warnung. Die Eigenschaftswerte sind: "Low", "Medium" und "High". **Erforderlich**.
title | String | Titel für die Warnung. **Erforderlich**.
description | String | Beschreibung der Warnung. **Erforderlich**.
recommendedAction| String | Aktion, die vom Sicherheitsbeauftragten bei der Analyse der Warnung empfohlen wird. **Erforderlich**.
category| String | Die Kategorie der Warnung. Die Eigenschaftswerte sind: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Erforderlich**.

## <a name="response"></a>Antwort

Wenn die Methode erfolgreich ist, werden 200 OK und ein neues [Warnungsobjekt](alerts.md) im Antworttext zurückgegeben. If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.

## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```

---
title: Erstellen einer Warnung aus der Ereignis-API
description: Erfahren Sie, wie Sie die Api zum Erstellen von Warnungen verwenden, um eine neue Warnung über das Ereignis in Microsoft Defender für Endpunkt zu erstellen.
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
ms.openlocfilehash: 8b05dde015bc96e1ccd3f80e25c416a371e03199
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772389"
---
# <a name="create-alert-api"></a>Erstellen der Warnungs-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung
Erstellt neue [Warnung](alerts.md) am Anfang des **Ereignisses.**
<br>**Das Microsoft Defender für Endpunkt-Ereignis** ist für die Erstellung von Warnungen erforderlich.
<br>Sie müssen 3 Parameter aus dem Ereignis in der Anforderung angeben: **Ereigniszeit,** **Computer-ID** und **Berichts-ID.** Siehe Beispiel unten.
<br>Sie können ein Ereignis in der API für die erweiterte Suche oder im Portal verwenden.
<br>Wenn auf demselben Gerät mit demselben Titel eine geöffnete Warnung vorhanden ist, wird die neu erstellte Warnung mit ihr zusammengeführt.
<br>Bei warnungen, die über die API erstellt wurden, wird automatisch eine automatische Untersuchung gestartet.


## <a name="limitations"></a>Begrenzungen
1. Die Rateneinschränkungen für diese API sind 15 Aufrufe pro Minute.


## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   Alerts.ReadWrite.All |  "Alle Warnungen lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Alert.ReadWrite | "Warnungen lesen und schreiben"

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>- Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Warnungsuntersuchung" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)
>- Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben, das der Warnung zugeordnet ist (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)

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
eventTime | DateTime(UTC) | Der genaue Zeitpunkt des Ereignisses als Zeichenfolge, wie er von der erweiterten Suche abgerufen wurde. z. B. ```2018-08-03T16:45:21.7115183Z``` **Erforderlich.**
reportId | String | Die reportId des Ereignisses, wie sie von der erweiterten Suche abgerufen wurde. **Erforderlich**.
machineId | String | ID des Geräts, auf dem das Ereignis identifiziert wurde. **Erforderlich**.
Schweregrad | String | Der Schweregrad der Warnung. Die Eigenschaftswerte sind: 'Low', 'Medium' und 'High'. **Erforderlich**.
title | String | Titel für die Warnung. **Erforderlich**.
description | String | Beschreibung der Warnung. **Erforderlich**.
recommendedAction| String | Aktion, die vom Sicherheitsbeauftragten bei der Analyse der Warnung empfohlen wird. **Erforderlich**.
category| String | Die Kategorie der Warnung. Die Eigenschaftswerte sind: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.

## <a name="response"></a>Antwort

Bei erfolgreicher Ausführung gibt die Methode 200 OK und ein neues [Warnungsobjekt](alerts.md) im Antworttext zurück. Wenn das Ereignis mit den angegebenen Eigenschaften (_reportId_, _eventTime_ und _machineId_) nicht gefunden wurde – 404 Nicht gefunden.

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

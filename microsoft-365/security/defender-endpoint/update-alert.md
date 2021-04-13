---
title: Aktualisieren der Benachrichtigungsentitäts-API
description: Erfahren Sie, wie Sie eine Microsoft Defender for Endpoint-Warnung mithilfe dieser API aktualisieren. Sie können die Eigenschaften status, determination, classification und assignedTo aktualisieren.
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
ms.openlocfilehash: 94be185bd30cd36f456a66d5ae30a4361abc0c48
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688249"
---
# <a name="update-alert"></a>Warnung aktualisieren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung
Aktualisiert die Eigenschaften der vorhandenen [Warnung](alerts.md).
<br>Die Übermittlung **von Kommentaren** ist mit oder ohne Aktualisierung von Eigenschaften verfügbar.
<br>Die updatablen Eigenschaften sind: ```status``` ```determination``` , und ```classification``` ```assignedTo``` .


## <a name="limitations"></a>Einschränkungen
1. Sie können Warnungen aktualisieren, die in der API verfügbar sind. Weitere Informationen finden Sie unter [Warnungen](get-alerts.md) auflisten.
2. Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.


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
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.
Content-Type | Zeichenfolge | application/json. **Erforderlich**.


## <a name="request-body"></a>Anforderungstext
Stellen Sie im Anforderungstext die Werte für die relevanten Felder zur Verfügung, die aktualisiert werden sollen.
<br>Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre vorherigen Werte oder werden basierend auf Änderungen an anderen Eigenschaftswerten neu berechnet. 
<br>Um eine optimale Leistung zu erzielen, sollten Sie keine vorhandenen Werte enthalten, die sich nicht geändert haben.

Eigenschaft | Typ | Beschreibung
:---|:---|:---
status | String | Gibt den aktuellen Status der Warnung an. Die Eigenschaftswerte sind: 'New', 'InProgress' und 'Resolved'.
assignedTo | String | Besitzer der Warnung
classification | Zeichenfolge | Gibt die Spezifikation der Warnung an. Die Eigenschaftswerte sind: "Unbekannt", "FalsePositive", "TruePositive". 
Bestimmung | String | Gibt die Bestimmung der Warnung an. Die Eigenschaftswerte sind: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other"
comment | String | Kommentar, der der Warnung hinzugefügt werden soll.

## <a name="response"></a>Antwort
Wenn die Methode erfolgreich ist, werden 200 OK und die Warnungsentität im Antworttext mit den aktualisierten Eigenschaften zurückgegeben. [](alerts.md) Wenn eine Warnung mit der angegebenen ID nicht gefunden wurde - 404 Nicht gefunden.


## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```

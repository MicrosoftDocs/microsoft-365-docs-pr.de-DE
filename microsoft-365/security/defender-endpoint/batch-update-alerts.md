---
title: Batch Update alert entities API
description: Erfahren Sie, wie Sie Microsoft Defender for Endpoint-Warnungen in einem Batch mithilfe dieser API aktualisieren. Sie können die Eigenschaften status, determination, classification und assignedTo aktualisieren.
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
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166681"
---
# <a name="batch-update-alerts"></a>Batchupdatewarnungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung
Aktualisiert die Eigenschaften eines Batches vorhandener [Alerts .](alerts.md)
<br>Die Übermittlung **von Kommentaren** ist mit oder ohne Aktualisierung von Eigenschaften verfügbar.
<br>Die updatablen Eigenschaften sind: `status` `determination` , und `classification` `assignedTo` .


## <a name="limitations"></a>Einschränkungen
1. Sie können Warnungen aktualisieren, die in der API verfügbar sind. Weitere Informationen finden Sie unter [Warnungen](get-alerts.md) auflisten.
2. Die Tarifeinschränkungen für diese API sind 10 Anrufe pro Minute und 500 Anrufe pro Stunde.


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
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.
Content-Type | Zeichenfolge | application/json. **Erforderlich**.


## <a name="request-body"></a>Anforderungstext
Stellen Sie im Anforderungstext die IDs der zu aktualisierenden Warnungen und die Werte der relevanten Felder zur Verfügung, die Sie für diese Warnungen aktualisieren möchten.
<br>Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre vorherigen Werte oder werden basierend auf Änderungen an anderen Eigenschaftswerten neu berechnet. 
<br>Aus Gründen der Leistung sollten Sie vorhandene Werte, die nicht geändert wurden, nicht angeben.

Eigenschaft | Typ | Beschreibung
:---|:---|:---
alertIds | &lt;Listenzeichenfolge&gt;| Eine Liste der IDs der zu aktualisierenden Warnungen. **Erforderlich**
status | String | Gibt den aktualisierten Status der angegebenen Warnungen an. Die Eigenschaftswerte sind: 'New', 'InProgress' und 'Resolved'.
assignedTo | String | Besitzer der angegebenen Warnungen
classification | Zeichenfolge | Gibt die Spezifikation der angegebenen Warnungen an. Die Eigenschaftswerte sind: "Unbekannt", "FalsePositive", "TruePositive". 
Bestimmung | String | Gibt die Bestimmung der angegebenen Warnungen an. Die Eigenschaftswerte sind: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other"
comment | String | Kommentar, der den angegebenen Warnungen hinzugefügt werden soll.

## <a name="response"></a>Antwort
Wenn die Methode erfolgreich ist, gibt sie 200 OK mit einem leeren Antworttext zurück.


## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```

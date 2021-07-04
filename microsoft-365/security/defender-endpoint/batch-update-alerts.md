---
title: Api für Batchaktualisierungs-Warnungsentitäten
description: Erfahren Sie, wie Sie Microsoft Defender für Endpunkt-Warnungen mithilfe dieser API in einem Batch aktualisieren. Sie können die Eigenschaften Status, Bestimmung, Klassifizierung und assignedTo aktualisieren.
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
ms.technology: mde
ms.openlocfilehash: 80f88b31c1e07d1f40f3f58a1bd21b4a5c58c60b
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290207"
---
# <a name="batch-update-alerts"></a>Warnungen bei Batchaktualisierungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung

Aktualisiert die Eigenschaften eines Batches vorhandener [Warnungen.](alerts.md)

Die Übermittlung eines **Kommentars** ist mit oder ohne Aktualisierung der Eigenschaften verfügbar.

Aktualisierbare Eigenschaften sind: `status` , `determination` und `classification` `assignedTo` .

## <a name="limitations"></a>Einschränkungen

1. Sie können Warnungen aktualisieren, die in der API verfügbar sind. Weitere Informationen finden Sie unter ["Warnungen auflisten".](get-alerts.md)
2. Die Rateneinschränkungen für diese API sind 10 Anrufe pro Minute und 500 Anrufe pro Stunde.

## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
:---|:---|:---
Anwendung | Alerts.ReadWrite.All | "Alle Warnungen lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Alert.ReadWrite | "Warnungen lesen und schreiben"

> [!NOTE]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>
> - Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Warnungsuntersuchung" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)
> - Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben, das der Warnung zugeordnet ist (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)

## <a name="http-request"></a>HTTP-Anforderung

```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | Zeichenfolge | Bearer {token}. **Erforderlich**.
Content-Type | Zeichenfolge | application/json. **Erforderlich**.

## <a name="request-body"></a>Anforderungstext

Geben Sie im Anforderungstext die IDs der zu aktualisierenden Warnungen und die Werte der relevanten Felder an, die Sie für diese Warnungen aktualisieren möchten.

Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre vorherigen Werte oder werden basierend auf Änderungen an anderen Eigenschaftswerten neu berechnet.

Aus Gründen der Leistung sollten Sie vorhandene Werte, die nicht geändert wurden, nicht angeben.

Eigenschaft | Typ | Beschreibung
:---|:---|:---
alertIds | &lt;Listenzeichenfolge&gt;| Eine Liste der IDs der zu aktualisierenden Warnungen. **Required**
status | Zeichenfolge | Gibt den aktualisierten Status der angegebenen Warnungen an. Die Eigenschaftswerte sind: 'New', 'InProgress' und 'Resolved'.
assignedTo | Zeichenfolge | Besitzer der angegebenen Warnungen
classification | Zeichenfolge | Gibt die Spezifikation der angegebenen Warnungen an. Die Eigenschaftswerte sind: 'Unknown', 'FalsePositive', 'TruePositive'. 
Bestimmung | Zeichenfolge | Gibt die Bestimmung der angegebenen Warnungen an. Die Eigenschaftswerte sind: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'
comment | String | Kommentar, der den angegebenen Warnungen hinzugefügt werden soll.

## <a name="response"></a>Antwort

Wenn die Methode erfolgreich ist, wird 200 OK mit einem leeren Antworttext zurückgegeben.

## <a name="example"></a>Beispiel

### <a name="request"></a>Anforderung

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

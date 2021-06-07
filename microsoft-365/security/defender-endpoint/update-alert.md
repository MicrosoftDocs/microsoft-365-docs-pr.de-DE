---
title: Aktualisieren der Warnungsentitäts-API
description: Erfahren Sie, wie Sie eine Microsoft Defender für Endpunkt-Warnung mithilfe dieser API aktualisieren. Sie können die Eigenschaften Status, Bestimmung, Klassifizierung und assignedTo aktualisieren.
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
ms.openlocfilehash: 043d423e1016d77cad4a175aa41718329f464252
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768925"
---
# <a name="update-alert"></a>Warnung aktualisieren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung
Aktualisiert die Eigenschaften vorhandener [Warnungen.](alerts.md)
<br>Die Übermittlung eines **Kommentars** ist mit oder ohne Aktualisierung der Eigenschaften verfügbar.
<br>Aktualisierbare Eigenschaften sind: ```status``` , ```determination``` und ```classification``` ```assignedTo``` .


## <a name="limitations"></a>Begrenzungen
1. Sie können Warnungen aktualisieren, die in der API verfügbar sind. Weitere Informationen finden Sie unter ["Warnungen auflisten".](get-alerts.md)
2. Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.


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
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.
Content-Type | Zeichenfolge | application/json. **Erforderlich**.


## <a name="request-body"></a>Anforderungstext
Geben Sie im Anforderungstext die Werte für die relevanten Felder an, die aktualisiert werden sollen.
<br>Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre vorherigen Werte oder werden basierend auf Änderungen an anderen Eigenschaftswerten neu berechnet. 
<br>Um eine optimale Leistung zu erzielen, sollten Sie vorhandene Werte, die sich nicht geändert haben, nicht einschließen.

Eigenschaft | Typ | Beschreibung
:---|:---|:---
status | String | Gibt den aktuellen Status der Warnung an. Die Eigenschaftswerte sind: 'New', 'InProgress' und 'Resolved'.
assignedTo | String | Besitzer der Warnung
classification | Zeichenfolge | Gibt die Spezifikation der Warnung an. Die Eigenschaftswerte sind: 'Unknown', 'FalsePositive', 'TruePositive'. 
Bestimmung | String | Gibt die Bestimmung der Warnung an. Die Eigenschaftswerte sind: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'
comment | String | Kommentar, der der Warnung hinzugefügt werden soll.

## <a name="response"></a>Antwort
Wenn die Methode erfolgreich ist, werden 200 OK und die [Warnungsentität](alerts.md) im Antworttext mit den aktualisierten Eigenschaften zurückgegeben. Wenn warnung mit der angegebenen ID nicht gefunden wurde – 404 Nicht gefunden.


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

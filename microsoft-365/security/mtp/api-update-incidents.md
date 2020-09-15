---
title: Update Incidents-API
description: Informationen zum Aktualisieren von Vorfällen mit der Microsoft Threat Protection-API
keywords: Update, API, Vorfall
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e790f4f415575323cfdd5fc15db41baa8b59c7f6
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650310"
---
# <a name="update-incidents-api"></a>Update Incidents-API

**Gilt für:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.


## <a name="api-description"></a>API-Beschreibung
Aktualisiert die Eigenschaften des vorhandenen Vorfalls.
<br>Aktualisierbare Eigenschaften sind: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` und ```tags``` .


## <a name="limitations"></a>Einschränkungen
1. Die Raten Beschränkungen für diese API lauten 50 Anrufe pro Minute und 1500 Anrufe pro Stunde.
2. Sie können den ```determination``` Wert nur festlegen, wenn die Klassifizierung auf TruePositive festgelegt ist.


## <a name="permissions"></a>Berechtigungen
Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [zugreifen auf die Microsoft Threat Protection-APIs](api-access.md).

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   Incident. ReadWrite. all |    "Alle Vorfälle lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Incident. ReadWrite | ' Lesen und Schreiben von Vorfällen '

>[!NOTE]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>- Der Benutzer muss über die Berechtigung verfügen, den Vorfall im Portal zu aktualisieren.


## <a name="http-request"></a>HTTP-Anforderung

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | Zeichenfolge | Bearer {Token}. **Erforderlich**.
Content-Type | Zeichenfolge | application/json. **Erforderlich**.


## <a name="request-body"></a>Anforderungstext
Geben Sie im Anforderungstext die Werte für die relevanten Felder an, die aktualisiert werden sollen.
<br>Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre vorherigen Werte oder werden basierend auf Änderungen an anderen Eigenschaftswerten neu berechnet. 
<br>Für eine optimale Leistung sollten Sie keine vorhandenen Werte einbeziehen, die sich nicht geändert haben.

Eigenschaft | Typ | Beschreibung
:---|:---|:---
status | Enum | Gibt den aktuellen Status der Warnung an. Mögliche Werte sind: ```Active``` ```Resolved``` und ```Redirected``` .
assignedTo | Zeichenfolge | Besitzer des Vorfalls.
classification | Enum | Spezifikation der Warnung. Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.
Bestimmung | Enum | Gibt die Bestimmung der Warnung an. Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Zeichenfolgenliste | Liste der Vorfall Tags.



## <a name="response"></a>Antwort
Wenn die Methode erfolgreich verläuft, werden 200 OK und die Vorfall Entität im Antworttext mit den aktualisierten Eigenschaften zurückgegeben. Wenn Incident mit der angegebenen ID nicht gefunden wurde-404 nicht gefunden.


## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a>Verwandtes Thema
- [Vorfall-APIs](api-incident.md)
- [Vorfälle auflisten](api-list-incidents.md)
---
title: Api zum Aktualisieren von Vorfällen
description: Erfahren Sie, wie Sie Vorfälle mithilfe der Microsoft 365 Defender-API aktualisieren.
keywords: Update, API, Vorfall
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929070"
---
# <a name="update-incidents-api"></a>Api zum Aktualisieren von Vorfällen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

## <a name="api-description"></a>API-Beschreibung

Aktualisiert die Eigenschaften vorhandener Vorfälle. Updatable eigenschaften are: ```status``` , , , , and ```determination``` ```classification``` ```assignedTo``` ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Kontingente, Ressourcenzuordnung und andere Einschränkungen

1. Sie können bis zu 50 Anrufe pro Minute oder 1.500 Anrufe pro Stunde machen, bevor Sie den Einschränkungsschwellenwert erreichen.
2. Sie können die Eigenschaft `determination` nur festlegen, wenn `classification` sie auf "TruePositive" festgelegt ist.

Wenn Ihre Anforderung gedrosselt ist, gibt sie einen `429` Antwortcode zurück. Der Antworttext gibt den Zeitpunkt an, zu dem Sie mit dem Starten neuer Anrufe beginnen können.

## <a name="permissions"></a>Berechtigungen

Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender APIs](api-access.md).

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
-|-|-
Anwendung | Incident.ReadWrite.All | Lesen und Schreiben aller Vorfälle
Delegiert (Geschäfts-, Schul- oder Unikonto) | Incident.ReadWrite | Lesen und Schreiben von Vorfällen

> [!NOTE]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen benötigt der Benutzer die Berechtigung, den Vorfall im Portal zu aktualisieren.

## <a name="http-request"></a>HTTP-Anforderung

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
-|-|-
Authorization | Zeichenfolge | Bearer {token}. **Erforderlich**.
Content-Type | Zeichenfolge | application/json. **Erforderlich**.

## <a name="request-body"></a>Anforderungstext

Stellen Sie im Anforderungstext die Werte für die Felder fest, die aktualisiert werden sollen. Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre Werte bei, es sei denn, sie müssen aufgrund von Änderungen an verwandten Werten neu berechnet werden. Um eine optimale Leistung zu erzielen, sollten Sie vorhandene Werte auslassen, die sich nicht geändert haben.

Eigenschaft | Typ | Beschreibung
-|-|-
status | Enum | Gibt den aktuellen Status der Warnung an. Mögliche Werte sind: ```Active``` ```Resolved``` , und ```Redirected``` .
assignedTo | string | Besitzer des Vorfalls.
classification | Enum | Spezifikation der Warnung. Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.
Bestimmung | Enum | Gibt die Bestimmung der Warnung an. Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Zeichenfolgenliste | Liste der Vorfalltags.

## <a name="response"></a>Antwort

Wenn die Methode erfolgreich ist, wird sie `200 OK` zurückgegeben. Der Antworttext enthält die Vorfallentität mit aktualisierten Eigenschaften. Wenn ein Vorfall mit der angegebenen ID nicht gefunden wurde, gibt die Methode `404 Not Found` zurück.

## <a name="example"></a>Beispiel

**Anforderung**

Hier ist ein Beispiel für die Anforderung.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**Response**

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a>Verwandte Artikel

- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
- [Informationen zu API-Beschränkungen und Lizenzierung](api-terms.md)
- [Fehlercodes verstehen](api-error-codes.md)
- [Vorfall-APIs](api-incident.md)
- [Auflisten von Vorfällen](api-list-incidents.md)
- [Übersicht über Vorfälle](incidents-overview.md)

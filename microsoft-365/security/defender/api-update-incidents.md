---
title: Update incidents API
description: Informationen zum Aktualisieren von Vorfällen mithilfe der Microsoft 365 Defender-API
keywords: update, api, incident
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 549f9bf2b9dc2ea5d1c734a809ad10a168c8123e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060803"
---
# <a name="update-incidents-api"></a>Update incidents API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

## <a name="api-description"></a>API-Beschreibung

Aktualisiert die Eigenschaften vorhandener Vorfälle. Updatable Eigenschaften sind: ```status``` , , , , und ```determination``` ```classification``` ```assignedTo``` ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Kontingente, Ressourcenzuordnung und andere Einschränkungen

1. Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde machen, bevor Sie den Drosselungsschwellenwert erreichen.
2. Sie können die Eigenschaft `determination` nur festlegen, `classification` wenn truePositive festgelegt ist.

Wenn Ihre Anforderung gedrosselt wird, gibt sie einen `429` Antwortcode zurück. Der Antworttext gibt den Zeitpunkt an, zu dem Sie mit dem Starten neuer Anrufe beginnen können.

## <a name="permissions"></a>Berechtigungen

Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender APIs](api-access.md).

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
-|-|-
Anwendung | Incident.ReadWrite.All | Lesen und Schreiben aller Vorfälle
Delegiert (Geschäfts-, Schul- oder Unikonto) | Incident.ReadWrite | Lese- und Schreibvorfälle

> [!NOTE]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen benötigt der Benutzer die Berechtigung, den Vorfall im Portal zu aktualisieren.

## <a name="http-request"></a>HTTP-Anforderung

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
-|-|-
Authorization | String | Bearer {token}. **Erforderlich**.
Content-Type | Zeichenfolge | application/json. **Erforderlich**.

## <a name="request-body"></a>Anforderungstext

Stellen Sie im Anforderungstext die Werte für die Felder zur Verfügung, die aktualisiert werden sollen. Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre Werte bei, es sei denn, sie müssen aufgrund von Änderungen an verwandten Werten neu berechnet werden. Um eine optimale Leistung zu erzielen, sollten Sie vorhandene Werte auslassen, die sich nicht geändert haben.

Eigenschaft | Typ | Beschreibung
-|-|-
status | Enum | Gibt den aktuellen Status der Warnung an. Mögliche Werte sind: ```Active``` ```Resolved``` , , und ```Redirected``` .
assignedTo | Zeichenfolge | Besitzer des Vorfalls.
classification | Enum | Spezifikation der Warnung. Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.
Bestimmung | Enum | Gibt die Bestimmung der Warnung an. Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Zeichenfolgenliste | Liste der Incident-Tags.

## <a name="response"></a>Antwort

Wenn die Methode erfolgreich ist, gibt sie `200 OK` zurück. Der Antworttext enthält die Vorfallentität mit aktualisierten Eigenschaften. Wenn ein Vorfall mit der angegebenen ID nicht gefunden wurde, gibt die Methode `404 Not Found` zurück.

## <a name="example"></a>Beispiel

**Anforderung**

Hier sehen Sie ein Beispiel für die Anforderung.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**Antwort**

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
- [Informationen zu API-Beschränkungen und -Lizenzierung](api-terms.md)
- [Verstehen von Fehlercodes](api-error-codes.md)
- [Vorfall-APIs](api-incident.md)
- [Auflisten von Vorfällen](api-list-incidents.md)
- [Übersicht über Vorfälle](incidents-overview.md)

---
title: Update Incidents-API
description: Informationen zum Aktualisieren von Vorfällen mit der Microsoft 365 Defender-API
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
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719404"
---
# <a name="update-incidents-api"></a>Update Incidents-API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

## <a name="api-description"></a>API-Beschreibung

Aktualisiert die Eigenschaften des vorhandenen Vorfalls. Aktualisierbare Eigenschaften sind: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` , und ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Kontingente, Ressourcenzuweisungen und andere Einschränkungen

1. Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde vornehmen, bevor Sie den Schwellenwert für die Drosselung erreichen.
2. Sie können die `determination` -Eigenschaft nur festlegen `classification` , wenn auf TruePositive festgelegt ist.

Wenn Ihre Anforderung gedrosselt wird, gibt Sie einen `429` Antwortcode zurück. Der Antworttext gibt die Zeit an, zu der Sie mit der Erstellung neuer Anrufe beginnen können.

## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender APIs](api-access.md).

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
-|-|-
Anwendung | Incident. ReadWrite. all | Lesen und Schreiben aller Vorfälle
Delegiert (Geschäfts-, Schul- oder Unikonto) | Incident. ReadWrite | Lese-und Schreib Vorfälle

> [!NOTE]
> Wenn ein Token mithilfe von Benutzeranmeldeinformationen abgerufen wird, muss der Benutzer über die Berechtigung verfügen, den Vorfall im Portal zu aktualisieren.

## <a name="http-request"></a>HTTP-Anforderung

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
-|-|-
Authorization | String | Bearer {Token}. **Erforderlich**.
Content-Type | Zeichenfolge | application/json. **Erforderlich**.

## <a name="request-body"></a>Anforderungstext

Geben Sie im Anforderungstext die Werte für die Felder an, die aktualisiert werden sollen. Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre Werte bei, es sei denn, Sie müssen aufgrund von Änderungen an verwandten Werten neu berechnet werden. Um eine optimale Leistung zu erzielen, sollten Sie vorhandene Werte weglassen, die sich nicht geändert haben.

Eigenschaft | Typ | Beschreibung
-|-|-
status | Enum | Gibt den aktuellen Status der Warnung an. Mögliche Werte sind: ```Active``` , ```Resolved``` und ```Redirected``` .
assignedTo | Zeichenfolge | Besitzer des Vorfalls.
classification | Enum | Spezifikation der Warnung. Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.
Bestimmung | Enum | Gibt die Bestimmung der Warnung an. Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Zeichenfolgenliste | Liste der Vorfall Tags.

## <a name="response"></a>Antwort

Wenn die Methode erfolgreich verläuft, wird diese zurückgegeben `200 OK` . Der Antworttext enthält die Vorfall Entität mit aktualisierten Eigenschaften. Wenn ein Vorfall mit der angegebenen ID nicht gefunden wurde, gibt die Methode zurück `404 Not Found` .

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
- [Informationen zu API-Grenzwerten und Lizenzierung](api-terms.md)
- [Grundlegendes zu Fehlercodes](api-error-codes.md)
- [Vorfall-APIs](api-incident.md)
- [Auflisten von Vorfällen](api-list-incidents.md)
- [Übersicht über Vorfälle](incidents-overview.md)

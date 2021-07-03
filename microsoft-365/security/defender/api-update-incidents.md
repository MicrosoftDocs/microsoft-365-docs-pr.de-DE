---
title: Api zum Aktualisieren von Vorfällen
description: Erfahren Sie, wie Sie Vorfälle mit Microsoft 365 Defender-API aktualisieren
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 60f1209331862eb21d3b1949265f0873dcf2e5a7
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287819"
---
# <a name="update-incidents-api"></a>API zum Aktualisieren von Vorfällen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

## <a name="api-description"></a>API-Beschreibung

Aktualisiert die Eigenschaften eines vorhandenen Vorfalls. Aktualisierbare Eigenschaften sind: ```status``` , , , , und ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Kontingente, Ressourcenzuweisung und andere Einschränkungen

1. Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde tätigen, bevor Sie den Einschränkungsschwellenwert erreichen.
2. Sie können die `determination` Eigenschaft nur festlegen, wenn `classification` sie auf "TruePositive" festgelegt ist.

Wenn Ihre Anforderung gedrosselt wird, wird ein `429` Antwortcode zurückgegeben. Der Antworttext gibt den Zeitpunkt an, zu dem Sie mit neuen Aufrufen beginnen können.

## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access the Microsoft 365 Defender APIs.](api-access.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
-|-|-
Anwendung | Incident.ReadWrite.All | Lesen und Schreiben aller Vorfälle
Delegiert (Geschäfts-, Schul- oder Unikonto) | Incident.ReadWrite | Lesen und Schreiben von Vorfällen

> [!NOTE]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen muss der Benutzer über die Berechtigung zum Aktualisieren des Vorfalls im Portal verfügen.

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

Geben Sie im Anforderungstext die Werte für die Felder an, die aktualisiert werden sollen. Vorhandene Eigenschaften, die nicht im Anforderungstext enthalten sind, behalten ihre Werte bei, es sei denn, sie müssen aufgrund von Änderungen an verwandten Werten neu berechnet werden. Um eine optimale Leistung zu erzielen, sollten Sie vorhandene Werte auslassen, die sich nicht geändert haben.

Eigenschaft | Typ | Beschreibung
-|-|-
status | Enum | Gibt den aktuellen Status des Vorfalls an. Mögliche Werte sind: ```Active``` ```Resolved``` , und ```Redirected``` .
assignedTo | Zeichenfolge | Besitzer des Vorfalls.
classification | Enum | Spezifikation des Vorfalls. Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.
Bestimmung | Enum | Gibt die Ermittlung des Vorfalls an. Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Zeichenfolgenliste | Liste der Vorfalltags.
Kommentar | string | Kommentar, der dem Vorfall hinzugefügt werden soll.

## <a name="response"></a>Antwort

Wenn die Methode erfolgreich ist, wird `200 OK` . Der Antworttext enthält die Vorfallentität mit aktualisierten Eigenschaften. Wenn ein Vorfall mit der angegebenen ID nicht gefunden wurde, gibt die Methode `404 Not Found` zurück.

## <a name="example"></a>Beispiel

**Anforderung**

Hier ist ein Beispiel für die Anforderung.

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
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a>Verwandte Artikel

- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
- [Informationen zu API-Beschränkungen und Lizenzierung](api-terms.md)
- [Grundlegendes zu Fehlercodes](api-error-codes.md)
- [Vorfall-APIs](api-incident.md)
- [Auflisten von Vorfällen](api-list-incidents.md)
- [Übersicht über Vorfälle](incidents-overview.md)

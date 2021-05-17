---
title: Microsoft 365 APIs für Defender-Vorfälle und der Ressourcentyp für Vorfälle
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Ressourcentyps Incident in Microsoft 365 Defender
keywords: Vorfall, Vorfälle, API
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
ms.openlocfilehash: 0a9022c0448ae0ddc16dc996ca93075abf6b2857
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060819"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 Defender Incidents-API und der Ressourcentyp für Vorfälle

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Bei [einem Vorfall](incidents-overview.md) handelt es sich um eine Sammlung verwandter Warnungen, die bei der Beschreibung eines Angriffs helfen. Ereignisse aus verschiedenen Entitäten in Ihrer Organisation werden automatisch von defender Microsoft 365 aggregiert. Sie können die Incidents-API verwenden, um programmgesteuert auf die Vorfälle und zugehörigen Warnungen Ihrer Organisation zu zugreifen.

## <a name="quotas-and-resource-allocation"></a>Kontingente und Ressourcenzuordnung

Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde anfordern. Jede Methode verfügt auch über eigene Kontingente. Weitere Informationen zu methodenspezifischen Kontingenten finden Sie im entsprechenden Artikel für die zu verwendende Methode.

Ein HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder nach der Anzahl der gesendeten Anforderungen oder nach der zugewiesenen `429` Laufzeit. Der Antworttext enthält die Zeit bis zum Zurücksetzen des erreichten Kontingents.

## <a name="permissions"></a>Berechtigungen

Die Incidents-API erfordert unterschiedliche Arten von Berechtigungen für jede ihrer Methoden. Weitere Informationen zu den erforderlichen Berechtigungen finden Sie im Artikel der jeweiligen Methode.

## <a name="methods"></a>Methoden

Methode | Rückgabetyp | Beschreibung
-|-|-
[Auflisten von Vorfällen](api-list-incidents.md) | [Liste der Vorfälle](api-incident.md) | Hier erhalten Sie eine Liste der Vorfälle.
[Aktualisieren von Vorfällen](api-update-incidents.md) | [Vorfall](api-incident.md) | Aktualisieren eines bestimmten Vorfalls.

## <a name="request-body-response-and-examples"></a>Anforderungstext, Antwort und Beispiele

Weitere Informationen zum Erstellen einer Anforderung oder analysieren einer Antwort sowie praktische Beispiele finden Sie in den jeweiligen Methodenartikeln.

## <a name="common-properties"></a>Allgemeine Eigenschaften

Eigenschaft | Typ | Beschreibung
-|-|-
incidentId | long | Eindeutige ID des Vorfalls.
redirectIncidentId | Nullable long | Die Vorfall-ID, mit der der aktuelle Vorfall zusammengeführt wurde.
incidentName | Zeichenfolge | Der Name des Vorfalls.
createdTime | DateTimeOffset | Das Datum und die Uhrzeit (in UTC), zu der der Vorfall erstellt wurde.
lastUpdateTime | DateTimeOffset | Datum und Uhrzeit (in UTC) der Vorfall wurde zuletzt aktualisiert.
assignedTo | Zeichenfolge | Besitzer des Vorfalls.
Schweregrad | Enum | Schweregrad des Vorfalls. Mögliche Werte sind: ```UnSpecified``` , , , , und ```Informational``` ```Low``` ```Medium``` ```High``` .
status | Enum | Gibt den aktuellen Status des Vorfalls an. Mögliche Werte sind: ```Active``` ```Resolved``` , , und ```Redirected``` .
classification | Enum | Spezifikation des Vorfalls. Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.
Bestimmung | Enum | Gibt die Ermittlung des Vorfalls an. Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Zeichenfolgenliste | Liste der Incident-Tags.
Warnungen | Warnungsliste | Liste der zugehörigen Warnungen. Beispiele finden Sie unter [List incidents](api-list-incidents.md) API documentation.

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft 365 Übersicht über Defender-APIs](api-overview.md)
- [Übersicht über Vorfälle](incidents-overview.md)
- [Auflisten der Incidents-API](api-list-incidents.md)
- [Aktualisieren der Vorfall-API](api-update-incidents.md)

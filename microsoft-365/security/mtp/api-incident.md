---
title: Microsoft 365 Defender-Vorfall-APIs und der Ressourcentyp für Vorfälle
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Vorfallressourcentyps in Microsoft 365 Defender
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928354"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 Defender Incidents API und der Ressourcentyp für Vorfälle

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Ein [Vorfall](incidents-overview.md) ist eine Sammlung verwandter Warnungen, die einen Angriff beschreiben. Ereignisse von verschiedenen Entitäten in Ihrer Organisation werden automatisch von Microsoft 365 Defender aggregiert. Sie können die Vorfall-API verwenden, um programmgesteuert auf die Vorfälle und zugehörigen Warnungen Ihrer Organisation zu zugreifen.

## <a name="quotas-and-resource-allocation"></a>Kontingente und Ressourcenzuordnung

Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde anfordern. Jede Methode verfügt auch über eigene Kontingente. Weitere Informationen zu methodenspezifischen Kontingenten finden Sie im entsprechenden Artikel zu der Methode, die Sie verwenden möchten.

Ein HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder durch die Anzahl der gesendeten Anforderungen oder durch die `429` zugewiesene Laufzeit. Der Antworttext enthält die Zeit bis zum Zurücksetzen des erreichten Kontingents.

## <a name="permissions"></a>Berechtigungen

Die Vorfall-API erfordert unterschiedliche Arten von Berechtigungen für jede ihrer Methoden. Weitere Informationen zu den erforderlichen Berechtigungen finden Sie im Artikel der jeweiligen Methode.

## <a name="methods"></a>Methoden

Methode | Rückgabetyp | Beschreibung
-|-|-
[Auflisten von Vorfällen](api-list-incidents.md) | [Vorfallliste](api-incident.md) | Eine Liste der Vorfälle erhalten.
[Aktualisieren von Vorfällen](api-update-incidents.md) | [Vorfall](api-incident.md) | Aktualisieren eines bestimmten Vorfalls.

## <a name="request-body-response-and-examples"></a>Anforderungstext, Antwort und Beispiele

Weitere Informationen zum Erstellen einer Anforderung oder Analysieren einer Antwort sowie praktische Beispiele finden Sie in den jeweiligen Methodenartikeln.

## <a name="common-properties"></a>Allgemeine Eigenschaften

Eigenschaft | Typ | Beschreibung
-|-|-
incidentId | long | Eindeutige VORfall-ID.
redirectIncidentId | Nullwerte zulassend lang | Die Vorfall-ID, mit der der aktuelle Vorfall zusammengeführt wurde.
incidentName | string | Der Name des Vorfalls.
createdTime | DateTimeOffset | Das Datum und die Uhrzeit (in UTC), zu der der Vorfall erstellt wurde.
lastUpdateTime | DateTimeOffset | Datum und Uhrzeit (in UTC), zu der der Vorfall zuletzt aktualisiert wurde.
assignedTo | string | Besitzer des Vorfalls.
Schweregrad | Enum | Schweregrad des Vorfalls. Mögliche Werte sind: ```UnSpecified``` , , , und ```Informational``` ```Low``` ```Medium``` ```High``` .
status | Enum | Gibt den aktuellen Status des Vorfalls an. Mögliche Werte sind: ```Active``` , ```Resolved``` und ```Redirected``` .
classification | Enum | Spezifikation des Vorfalls. Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.
Bestimmung | Enum | Gibt die Ermittlung des Vorfalls an. Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Zeichenfolgenliste | Liste der Vorfalltags.
Warnungen | Warnungsliste | Liste verwandter Warnungen. Beispiele finden Sie in [der Dokumentation zur API für Listenvorfälle.](api-list-incidents.md)

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über Microsoft 365 Defender-APIs](api-overview.md)
- [Übersicht über Vorfälle](incidents-overview.md)
- [Api zum Auflisten von Vorfällen](api-list-incidents.md)
- [Vorfall-API aktualisieren](api-update-incidents.md)

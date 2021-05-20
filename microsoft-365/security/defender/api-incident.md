---
title: Microsoft 365 Defender-Vorfällen-APIs und der Vorfallressourcentyp
description: Weitere Informationen zu den Methoden und Eigenschaften des Ressourcentyps "Vorfall" in Microsoft 365 Defender
keywords: Vorfall, Vorfälle, api
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
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572585"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 Defender-Vorfällen-API und der Ressourcentyp des Vorfalls

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Ein [Vorfall](incidents-overview.md) ist eine Sammlung verwandter Warnungen, die einen Angriff beschreiben. Ereignisse aus verschiedenen Entitäten in Ihrer Organisation werden automatisch von Microsoft 365 Defender aggregiert. Sie können die Vorfall-API verwenden, um programmgesteuert auf Vorfälle und zugehörige Warnungen Ihrer Organisation zuzugreifen.

## <a name="quotas-and-resource-allocation"></a>Kontingente und Ressourcenallokation

Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde anfordern. Jede Methode hat auch ihre eigenen Quoten. Weitere Informationen zu methodenspezifischen Kontingenten finden Sie im entsprechenden Artikel für die Methode, die Sie verwenden möchten.

Ein `429` HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder nach Anzahl der gesendeten Anforderungen oder nach zugeteilter Laufzeit. Der Antworttext enthält die Zeit, bis das erreichte Kontingent zurückgesetzt wird.

## <a name="permissions"></a>Berechtigungen

Die Vorkommniss-API erfordert für jede ihrer Methoden unterschiedliche Arten von Berechtigungen. Weitere Informationen zu den erforderlichen Berechtigungen finden Sie im Artikel der jeweiligen Methode.

## <a name="methods"></a>Methoden

Methode | Rückgabetyp | Beschreibung
-|-|-
[Auflisten von Vorfällen](api-list-incidents.md) | [Vorfallliste](api-incident.md) | Hier erhalten Sie eine Liste der Vorfälle.
[Aktualisieren von Vorfällen](api-update-incidents.md) | [Vorfall](api-incident.md) | Aktualisieren Sie einen bestimmten Vorfall.

## <a name="request-body-response-and-examples"></a>Anforderungstext, Antwort und Beispiele

Weitere Informationen zum Erstellen einer Anforderung oder zum Analysieren einer Antwort sowie praktische Beispiele finden Sie in den entsprechenden Methodenartikeln.

## <a name="common-properties"></a>Allgemeine Eigenschaften

Eigenschaft | Typ | Beschreibung
-|-|-
incidentId | long | Eindeutige ID des Vorfalls.
redirectIncidentId | nullable lange | Die Vorfall-ID, mit der der aktuelle Vorfall zusammengeführt wurde.
incidentName | Zeichenfolge | Der Name des Vorfalls.
createdZeit | DateTimeOffset | Das Datum und die Uhrzeit (in UTC), die der Vorfall erstellt wurde.
lastUpdateTime | DateTimeOffset | Das Datum und die Uhrzeit (in UTC) der Vorfall wurde zuletzt aktualisiert.
assignedTo | Zeichenfolge | Besitzer des Vorfalls.
Schweregrad | Enum | Schweregrad des Vorfalls. Mögliche Werte sind: ```UnSpecified``` , , , , und ```Informational``` ```Low``` ```Medium``` ```High``` .
status | Enum | Gibt den aktuellen Status des Vorfalls an. Mögliche Werte sind: ```Active``` , ```Resolved``` , und ```Redirected``` .
classification | Enum | Spezifikation des Vorfalls. Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.
Bestimmung | Enum | Gibt die Bestimmung des Vorfalls an. Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Zeichenfolgenliste | Liste der Incident-Tags.
Kommentare | Liste der Kommentare zu Vorfällen | Incident Comment-Objekt enthält: Kommentarzeichenfolge, createdBy-Zeichenfolge und createTime-Datumszeit.
Warnungen | Warnungsliste | Liste der zugehörigen Warnungen. Weitere Beispiele finden Sie in der API-Dokumentation Liste von [Vorfällen.](api-list-incidents.md)

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft 365 Übersicht über Defender-APIs](api-overview.md)
- [Übersicht über Vorfälle](incidents-overview.md)
- [Liste der Vorfällen API](api-list-incidents.md)
- [Aktualisieren der Vorfall-API](api-update-incidents.md)

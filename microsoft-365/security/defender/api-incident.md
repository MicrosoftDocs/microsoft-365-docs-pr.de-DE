---
title: Microsoft 365 Defender Incidents-APIs und der Ressourcentyp "Vorfälle"
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Incidents-Ressourcentyps in Microsoft 365 Defender
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
ms.openlocfilehash: 0c0c2e280f63076687a0854e25c47577b050a8f7
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888433"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a>Microsoft 365 Api für Defender-Vorfälle und der Ressourcentyp "Vorfälle"

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Ein [Vorfall](incidents-overview.md) ist eine Sammlung verwandter Warnungen, die einen Angriff beschreiben. Ereignisse aus verschiedenen Entitäten in Ihrer Organisation werden automatisch von Microsoft 365 Defender aggregiert. Sie können die Vorfall-API verwenden, um programmgesteuert auf Vorfälle und zugehörige Warnungen Ihrer Organisation zuzugreifen.

## <a name="quotas-and-resource-allocation"></a>Kontingente und Ressourcenzuweisung

Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde anfordern. Jede Methode verfügt auch über eigene Kontingente. Weitere Informationen zu methodenspezifischen Kontingenten finden Sie im entsprechenden Artikel für die Methode, die Sie verwenden möchten.

Ein `429` HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder nach anzahl der gesendeten Anforderungen oder nach zugewiesener Laufzeit. Der Antworttext enthält die Zeit bis zum Zurücksetzen des erreichten Kontingents.

## <a name="permissions"></a>Berechtigungen

Die Vorfall-API erfordert unterschiedliche Arten von Berechtigungen für jede ihrer Methoden. Weitere Informationen zu den erforderlichen Berechtigungen finden Sie im Artikel der entsprechenden Methode.

## <a name="methods"></a>Methoden

Methode | Rückgabetyp | Beschreibung
-|-|-
[Auflisten von Vorfällen](api-list-incidents.md) | [Vorfallliste](api-incident.md) | Abrufen einer Liste von Vorfällen.
[Aktualisieren von Vorfällen](api-update-incidents.md) | [Vorfall](api-incident.md) | Aktualisieren eines bestimmten Vorfalls.
[Vorfall abrufen](api-get-incident.md) | [Vorfall](api-incident.md) | Rufen Sie einen einzelnen Vorfall ab.

## <a name="request-body-response-and-examples"></a>Anforderungstext, Antwort und Beispiele

Weitere Informationen zum Erstellen einer Anforderung oder Analysieren einer Antwort sowie praktische Beispiele finden Sie in den entsprechenden Methodenartikeln.

## <a name="common-properties"></a>Allgemeine Eigenschaften

Eigenschaft | Typ | Beschreibung
-|-|-
incidentId | long | Eindeutige ID des Vorfalls.
redirectIncidentId | Nullable long | Die Vorfall-ID, mit der der aktuelle Vorfall zusammengeführt wurde.
incidentName | Zeichenfolge | Der Name des Vorfalls.
createdTime | DateTimeOffset | Das Datum und die Uhrzeit (in UTC), zu der der Vorfall erstellt wurde.
lastUpdateTime | DateTimeOffset | Datum und Uhrzeit (in UTC), zu der der Vorfall zuletzt aktualisiert wurde.
assignedTo | Zeichenfolge | Besitzer des Vorfalls.
Schweregrad | Enum | Schweregrad des Vorfalls. Mögliche Werte sind: ```UnSpecified``` , , , und ```Informational``` ```Low``` ```Medium``` ```High``` .
status | Enum | Gibt den aktuellen Status des Vorfalls an. Mögliche Werte sind: ```Active``` ```Resolved``` , und ```Redirected``` .
classification | Enum | Spezifikation des Vorfalls. Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.
Bestimmung | Enum | Gibt die Ermittlung des Vorfalls an. Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Zeichenfolgenliste | Liste der Vorfalltags.
Kommentare | Liste der Vorfallkommentare | Incident Comment-Objekt enthält: Kommentarzeichenfolge, createdBy-Zeichenfolge und createTime-Datumszeit.
Warnungen | Warnungsliste | Liste verwandter Warnungen. Beispiele finden Sie in der API-Dokumentation [für Listenvorfälle.](api-list-incidents.md)

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft 365 Übersicht über Defender-APIs](api-overview.md)
- [Übersicht über Vorfälle](incidents-overview.md)
- [API zum Auflisten von Vorfällen](api-list-incidents.md)
- [Api zum Aktualisieren von Vorfällen](api-update-incidents.md)

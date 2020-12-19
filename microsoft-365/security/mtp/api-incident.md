---
title: Microsoft 365 Defender Incidents-APIs und der Vorfall-Ressourcentyp
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Incident-Ressourcentyps in Microsoft 365 Defender
keywords: Vorfall, Vorfälle, API
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
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719334"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 Defender Incidents-API und der Vorfall-Ressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Bei einem [Vorfall](incidents-overview.md) handelt es sich um eine Sammlung zusammengehöriger Warnungen, die einen Angriff beschreiben. Ereignisse aus unterschiedlichen Entitäten in Ihrer Organisation werden automatisch von Microsoft 365 Defender aggregiert. Sie können die Vorfälle-API verwenden, um Programmgesteuertes auf Vorfälle und Verwandte Warnungen Ihrer Organisation zuzugreifen.

## <a name="quotas-and-resource-allocation"></a>Kontingente und Ressourcenzuteilung

Sie können bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde anfordern. Jede Methode verfügt auch über eigene Kontingente. Weitere Informationen zu Methoden spezifischen Kontingenten finden Sie im jeweiligen Artikel für die Methode, die Sie verwenden möchten.

Ein `429` HTTP-Antwortcode gibt an, dass Sie ein Kontingent erreicht haben, entweder nach der Anzahl der gesendeten Anforderungen oder nach der zugewiesenen Laufzeit. Der Antworttext enthält die Zeit, bis das von Ihnen erreichte Kontingent zurückgesetzt wird.

## <a name="permissions"></a>Berechtigungen

Für die Vorfälle-API sind unterschiedliche Arten von Berechtigungen für jede ihrer Methoden erforderlich. Weitere Informationen zu den erforderlichen Berechtigungen finden Sie im Artikel zur jeweiligen Methode.

## <a name="methods"></a>Methoden

Methode | Rückgabetyp | Beschreibung
-|-|-
[Auflisten von Vorfällen](api-list-incidents.md) | [Vorfall](api-incident.md) Liste | Abrufen einer Liste von Vorfällen.
[Aktualisieren von Vorfällen](api-update-incidents.md) | [Vorfall](api-incident.md) | Einen bestimmten Vorfall aktualisieren.

## <a name="request-body-response-and-examples"></a>Anforderungstext, Antwort und Beispiele

Weitere Informationen zum Erstellen einer Anforderung oder zum Analysieren einer Antwort sowie zu praktischen Beispielen finden Sie in den jeweiligen Methoden Artikeln.

## <a name="common-properties"></a>Allgemeine Eigenschaften

Eigenschaft | Typ | Beschreibung
-|-|-
Vorfall-Nr | long | Vorfall eindeutige ID.
redirectIncidentId | Nullable Long | Die Vorfall-ID, mit der der aktuelle Vorfall zusammengeführt wurde.
Vorfallname | Zeichenfolge | Der Name des Vorfalls.
createdTime | DateTimeOffset | Das Datum und die Uhrzeit (in UTC), an denen der Vorfall erstellt wurde.
Last Update time | DateTimeOffset | Datum und Uhrzeit (in UTC) der Vorfall wurde zuletzt aktualisiert.
assignedTo | Zeichenfolge | Besitzer des Vorfalls.
Schweregrad | Enum | Schweregrad des Vorfalls. Mögliche Werte sind: ```UnSpecified``` , ```Informational``` , ```Low``` , ```Medium``` , und ```High``` .
status | Enum | Gibt den aktuellen Status des Vorfalls an. Mögliche Werte sind: ```Active``` , ```Resolved``` und ```Redirected``` .
classification | Enum | Spezifikation des Vorfalls. Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.
Bestimmung | Enum | Gibt die Ermittlung des Vorfalls an. Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Zeichenfolgenliste | Liste der Vorfall Tags.
Warnungen | Warnungsliste | Liste der zugehörigen Warnungen. Siehe Beispiele unter Documentation [List Incidents](api-list-incidents.md) API.

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft 365 Defender-APIs (Übersicht)](api-overview.md)
- [Übersicht über Vorfälle](incidents-overview.md)
- [Listen Vorfälle-API](api-list-incidents.md)
- [Update Incident API](api-update-incidents.md)

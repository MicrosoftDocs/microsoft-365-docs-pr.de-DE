---
title: Vorfall-Ressourcentyp in der Microsoft Threat Protection-API
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Incident-Ressourcentyps in Microsoft Threat Protection.
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
ms.openlocfilehash: 310e3105c973223ea79373d770eb10f7753b917e
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650330"
---
# <a name="incident-resource-type"></a>Vorfall-Ressourcentyp

**Gilt für:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

## <a name="methods"></a>Methoden

Methode |Rückgabetyp |Beschreibung
:---|:---|:---
[Vorfälle auflisten](api-list-incidents.md) | [Vorfall](api-incident.md) Liste | Abrufen einer Liste von Vorfällen.
[Vorfall aktualisieren](api-update-incidents.md) | [Vorfall](api-incident.md) | Aktualisieren eines bestimmten Vorfalls.


## <a name="properties"></a>Eigenschaften

Eigenschaft |    Typ    |    Beschreibung
:---|:---|:---
Vorfall-Nr | long | Vorfall eindeutige ID.
redirectIncidentId | Nullable Long | Die Vorfall-ID, mit der der aktuelle Vorfall zusammengeführt wurde.
Vorfallname | Zeichenfolge | Der Name des Vorfalls.
createdTime | DateTimeOffset | Das Datum und die Uhrzeit (in UTC), an denen der Vorfall erstellt wurde.
Last Update time | DateTimeOffset | Datum und Uhrzeit (in UTC) der Vorfall wurde zuletzt aktualisiert.
assignedTo | Zeichenfolge | Besitzer des Vorfalls.
Schweregrad | Enum | Schweregrad des Vorfalls. Mögliche Werte sind: ```UnSpecified``` , ```Informational``` , ```Low``` ```Medium``` und ```High``` .
status | Enum | Gibt den aktuellen Status des Vorfalls an. Mögliche Werte sind: ```Active``` ```Resolved``` und ```Redirected``` .
classification | Enum | Spezifikation des Vorfalls. Mögliche Werte sind: ```Unknown```, ```FalsePositive``` und ```TruePositive```.
Bestimmung | Enum | Gibt die Ermittlung des Vorfalls an. Mögliche Werte: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Zeichenfolgenliste | Liste der Vorfall Tags.
Warnungen | Warnungsliste | Liste der zugehörigen Warnungen. Siehe Beispiele unter Documentation [List Incidents](api-list-incidents.md) API.
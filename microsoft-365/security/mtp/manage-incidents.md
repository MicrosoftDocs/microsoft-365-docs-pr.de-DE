---
title: Verwalten von Vorfällen in Microsoft-Bedrohungsschutz
description: Erfahren Sie, wie Sie einen Status zuweisen und aktualisieren können,
keywords: Vorfall, Vorfälle, Alert, korrelierte Alerts, zuweisen, aktualisieren, Status, verwalten, Klassifizierung, Microsoft, 365, m365
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
ms.openlocfilehash: f711cc2ff38f15dfd22097e37a1dec42719eb5aa
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148114"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a>Verwalten von Vorfällen in Microsoft-Bedrohungsschutz

**Gilt für:**
- Microsoft-Bedrohungsschutz



Das Verwalten von Vorfällen ist entscheidend, um sicherzustellen, dass Bedrohungen eingedämmt und bearbeitet werden. Im Microsoft-Bedrohungsschutz haben Sie Zugriff auf die Verwaltung von Vorfällen auf Geräten, Benutzern und in Postfächern. 


Sie können Vorfälle verwalten, indem Sie einen Vorfall aus der Warteschlange **Vorfälle** auswählen. 

Sie können den Namen eines Vorfalls bearbeiten, ihn auflösen, seine Klassifizierung und Bestimmung festlegen. Sie können den Vorfall auch sich selbst zuweisen, Ereigniskategorien und Kommentare hinzufügen.

In Fällen, in denen Sie bei der Untersuchung bestimmte Alerts von einem Vorfall auf einen anderen verschieben möchten, können Sie dies auch über die Registerkarte "Alerts" tun und so einen größeren oder kleineren Vorfall erstellen, der alle relevanten Alerts enthält.

## <a name="edit-incident-name"></a>Name des Vorfalls bearbeiten
Standardmäßig wird einem Vorfall eine Zahl zugewiesen. Sie können den Namen des Vorfalls ändern, damit er besser mit Ihrer bevorzugten Benennungskonvention übereinstimmt.

> [!TIP]
> Um einen Überblick zu erhalten, werden bei der automatischen Benennung von Anteilen, die sich derzeit in der öffentlichen Vorschau befinden, Vorfall Namen basierend auf Warnungs Attributen generiert, beispielsweise die Anzahl betroffener Endpunkte, betroffene Benutzer, Erkennungsquellen oder Kategorien. Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.
>
> Beispiel: *mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet werden.*
>
> Bei Vorfällen, die vor dem Rollout der automatischen Vorfall Benennung vorhanden waren, wird der Name nicht geändert.
>
> Erfahren Sie mehr über das [Aktivieren von Vorschaufunktionen](preview.md#turn-on-preview-features).

## <a name="assign-incidents"></a>Zuweisen von Vorfällen
Falls ein Vorfall noch nicht zugewiesen wurde, können Sie **Mir zuweisen** auswählen, um sich den Vorfall selbst zuzuweisen. Dies setzt voraus, dass nicht nur der Vorfall, sondern auch alle ihm zugeordneten Alerts in Ihrem Besitz sind.

## <a name="set-status-and-classification"></a>Festlegen des Status und der Klassifizierung
### <a name="incident-status"></a>Status des Vorfalls
Sie können Ereignisse kategorisieren (z.B. als **aktive**oder **aufgelöste**), indem Sie deren Status ändern, während ihre Untersuchung voranschreitet. Auf diese Weise können Sie organisieren und verwalten, wie Ihr Team auf Vorfälle reagiert.

So kann Ihr SOC-Analyst beispielsweise die dringlichen **aktiven** Vorfälle für den Tag überprüfen und sich entscheiden, sie sich selbst zur Untersuchung zuzuweisen.

Alternativ kann Ihr SOC-Analyst den Vorfall als **aufgelöst** einstufen, wenn der Vorfall behoben wurde. Wenn Sie einen Vorfall auflösen, werden automatisch alle Alerts geschlossen, die Teil des Vorfalls sind und bis dahin noch offen sind. 

### <a name="classification-and-determination"></a>Klassifizierung und Ermittlung
Sie können festlegen, dass keine Klassifizierung festgelegt wird, oder Sie können angeben, ob ein Vorfall wahr oder falsch ist. Auf diese Weise kann das Team Muster erkennen und von ihnen lernen. 

## <a name="add-comments"></a>Kommentare hinzufügen
Sie können Kommentare hinzufügen und Historien-Ereignisse zu einem Vorfall anzeigen, um die vorherigen vorgenommenen Änderungen anzuzeigen.

Immer wenn eine Änderung an einem Alert vorgenommen oder ein Kommentar zu einem Alert hinterlassen wird, wird dies im Abschnitt Kommentare und Verlauf aufgezeichnet.

Hinzugefügte Kommentare werden sofort in diesem Bereich angezeigt.

## <a name="add-incident-tags"></a>Hinzufügen von Ereigniskategorien
Sie können einem Vorfall benutzerdefinierte Kategorien hinzufügen, um beispielsweise eine Gruppe von Vorfällen mit einer gemeinsamen Charakteristik zu kennzeichnen. Sie können die Liste der Vorfälle später nach allen Einträgen filtern, die eine bestimmte Kategorie enthalten.
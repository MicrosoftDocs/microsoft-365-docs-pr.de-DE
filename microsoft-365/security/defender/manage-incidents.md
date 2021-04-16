---
title: Verwalten von Vorfällen in Microsoft 365 Defender
description: Erfahren Sie, wie Sie einen Status zuweisen und aktualisieren können,
keywords: Vorfall, Vorfälle, Alert, korrelierte Alerts, zuweisen, aktualisieren, Status, verwalten, Klassifizierung, Microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: da5a2190a53dfe7f8dd0cc3cf7b410af92ca4ec5
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861731"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Verwalten von Vorfällen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die Vorfallverwaltung ist von entscheidender Bedeutung, um sicherzustellen, dass Bedrohungen eindämmt und behoben werden.

Sie verwalten Vorfälle aus Vorfällen **& Warnungen > Vorfällen** beim Schnellstart des Microsoft 365 Security Centers ([security.microsoft.com](https://security.microsoft.com)). Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Beispiel für die Warteschlange für Vorfälle":::

Hier sind die Möglichkeiten, wie Sie Ihre Vorfälle verwalten können:

- Ändern des Vorfallnamens
- Fügen Sie Vorfalltags hinzu.
- Zuweisen des Vorfalls zu einem Benutzerkonto
- Auflösen 
- Festlegen der Klassifizierung und Bestimmung
- Fügen Sie Kommentare hinzu.

Sie können Vorfälle im Bereich Vorfall verwalten **für** einen Vorfall verwalten. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Beispiel für den Bereich &quot;Vorfall verwalten&quot; eines Vorfalls":::

Sie können diesen Bereich über **den** Link Vorfall verwalten auf der folgenden Seite anzeigen:

- Eigenschaftenbereich eines Vorfalls in der Vorfallwarteschlange.
- **Zusammenfassungsseite** eines Vorfalls.

In Fällen, in denen Sie während der Untersuchung Warnungen von einem Vorfall zu einem anderen verschieben möchten, können Sie dies auch auf der Registerkarte Warnungen tun, wodurch ein größerer oder kleinerer Vorfall mit allen relevanten Warnungen erstellt wird. 

## <a name="edit-the-incident-name"></a>Bearbeiten des Vorfallnamens

Microsoft 365 Defender weist automatisch einen Namen basierend auf Warnungsattributen zu, z. B. der Anzahl betroffener Endpunkte, betroffener Benutzer, Erkennungsquellen oder Kategorien. Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen. Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet wurden.*

Sie können den Vorfallnamen im Feld **Vorfallname** im Bereich Vorfall **verwalten** bearbeiten.

> [!NOTE]
> Vorfälle, die vor dem Rollout der funktion für die automatische Benennung von Vorfällen vorhanden waren, behalten ihren Namen.

## <a name="add-incident-tags"></a>Hinzufügen von Ereigniskategorien

Sie können einem Vorfall benutzerdefinierte Tags hinzufügen, um beispielsweise eine Gruppe von Vorfällen mit einem gemeinsamen Merkmal zu kennzeichnen. Sie können die Vorfallwarteschlange später nach allen Vorfällen filtern, die ein bestimmtes Tag enthalten.

Wenn Sie mit der Eingabe beginnen, haben Sie die Möglichkeit, aus einer Liste ausgewählter Tags auszuwählen.

## <a name="assign-incidents"></a>Zuweisen von Vorfällen

Wenn ein Vorfall noch nicht zugewiesen wurde, können Sie **Zuweisen zu** auswählen und das Benutzerkonto angeben. Dadurch wird der Besitz des Vorfalls und aller damit verbundenen Warnungen zugewiesen.

## <a name="resolve-incident"></a>Beheben eines Vorfalls

Wenn der Vorfall behoben wurde, wählen Sie **Vorfall** beheben aus, um den Umschalter nach rechts zu verschieben. Beachten Sie, dass beim Auflösen eines Vorfalls auch alle verknüpften und aktiven Warnungen im Zusammenhang mit dem Vorfall behoben werden.

Ein nicht aufgelöster Vorfall wird als **Aktiv angezeigt.**

## <a name="set-the-classification-and-determination"></a>Festlegen der Klassifizierung und Ermittlung

Die Vorfallklassifizierung ist, ob es sich um eine echte warnung oder eine falsche Warnung handelt, die Sie im Feld **Klassifizierung konfigurieren.** 

Wenn es sich um eine echte Warnung handeln sollte, sollten Sie auch angeben, um welche Art von Bedrohung es sich bei dem Feld **Bestimmung handeln** sollte. Das Angeben des Bedrohungstyps hilft Ihrem Sicherheitsteam, Bedrohungsmuster zu erkennen und zu handeln, um Ihre Organisation vor ihnen zu schützen. 

## <a name="add-comments"></a>Kommentare hinzufügen

Sie können einem Vorfall mit dem Feld Kommentar mehrere **Kommentare** hinzufügen. Jeder Kommentar wird den historischen Ereignissen des Vorfalls hinzugefügt. Sie können die Kommentare und den Verlauf eines Vorfalls über den Link **Kommentare und** Verlauf auf der **Seite Zusammenfassung** anzeigen.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Vorfälle](incidents-overview.md)
- [Priorisieren von Vorfällen](incident-queue.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)

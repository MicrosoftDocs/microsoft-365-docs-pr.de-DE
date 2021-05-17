---
title: Schließen oder Löschen eines Falls
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Erfahren Sie, was geschieht, wenn eine Untersuchung oder ein von einem Fall Advanced eDiscovery Fall geschlossen oder gelöscht wird.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419061"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Schließen oder Löschen eines Advanced eDiscovery Fall

Wenn die von einem Fall unterstützte Rechts- oder Advanced eDiscovery abgeschlossen ist, können Sie einen Fall schließen oder löschen. Sie können auch einen geschlossenen Fall erneut öffnen.

## <a name="close-a-case"></a>Schließen eines Falls

Dies geschieht, wenn Sie einen Fall Advanced eDiscovery schließen:

- Wenn der Fall in den Haltebereich versetzte Inhaltsspeicherorte enthält, werden diese Haltebereiche deaktiviert. Nachdem der Haltezeitraum deaktiviert wurde, wird eine 30-tägige Nachfrist (als Verzögerungsverzögerung *bezeichnet)* auf Inhaltsstandorte angewendet, die sich im Haltezeitraum befinden. Dadurch wird verhindert, dass Inhalte sofort gelöscht werden, und Administratoren können Inhalte suchen oder wiederherstellen, die nach Ablauf des Verzögerungszeitraums endgültig gelöscht werden. Weitere Informationen finden Sie unter [Entfernen von Inhaltsstandorten aus einem eDiscovery-Halteraum.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)

- Durch das Abschließen eines Falls werden nur die Haltebereiche deaktiviert, die diesem Fall zugeordnet sind. Wenn an einem Inhaltsspeicherort andere Haltewerte (z. B. ein Rechtsstreitigkeiten, ein Core eDiscovery-Haltebereich oder ein Haltebereich von einem anderen Advanced eDiscovery-Fall) stattfinden, werden diese Haltewerte weiterhin beibehalten.

- Der Fall wird weiterhin auf der eDiscovery-Seite im compliance center Microsoft 365 aufgeführt. Die Details, Haltebereiche, Suchvorgänge und Mitglieder eines abgeschlossenen Falls bleiben erhalten.

- Sie können einen Fall bearbeiten, nachdem er geschlossen wurde. Sie können z. B. Mitglieder hinzufügen oder entfernen, Suchen erstellen, Suchergebnisse exportieren und Suchergebnisse für die Analyse in Advanced eDiscovery. Der Hauptunterschied zwischen aktiven und abgeschlossenen Fällen ist, dass die Haltebereiche beim Abschließen eines Falls deaktiviert werden.

So schließen Sie einen Fall ab

1. Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus, den Sie schließen möchten.

2. Klicken Sie auf der Registerkarte **Einstellungen** unter **Fallinformationen** auf **Auswählen**.

3. Klicken Sie auf **Fall schließen**.

   Es kann bis zu 60 Minuten dauern, bis der Abschlussvorgang abgeschlossen ist.

## <a name="reopen-a-closed-case"></a>Erneuter Öffnen eines geschlossenen Falls

Wenn Sie einen Advanced eDiscovery erneut öffnen, werden alle Haltewerte, die beim Schließen des Falls aktiviert wurden, nicht automatisch wieder aktiviert. Nachdem der Fall erneut geöffnet wurde, müssen  Sie zur Registerkarte Halte halten wechseln und die vorherigen Halte halte aktivieren. Wenn Sie einen Haltebereich aktivieren möchten, wählen Sie ihn aus, um die Flyout-Seite anzuzeigen, und legen Sie dann den **Status** auf **Ein** fest.

So öffnen Sie einen geschlossenen Fall erneut:

1. Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus, den Sie erneut öffnen möchten.

2. Klicken Sie auf der Registerkarte **Einstellungen** unter **Fallinformationen** auf **Auswählen**.

3. Klicken Sie auf **Fall erneut öffnen**.

   Es kann bis zu 60 Minuten dauern, bis der Erneutes Öffnen abgeschlossen ist.

## <a name="delete-a-case"></a>Löschen eines Falls

Sie können sowohl aktive als auch geschlossene Advanced eDiscovery löschen. Wenn Sie einen Fall löschen, werden alle dem Fall zugeordneten Komponenten, z. B. die Liste von Verwaltern, die Kommunikation, Suchvorgänge, Überprüfungssätze und der Exportvorgang, gelöscht. Der Fall wird aus der Liste  der Fälle auf der Advanced eDiscovery im Microsoft 365 Compliance Center entfernt. Sie können einen gelöschten Fall nicht wiederherstellen oder erneut öffnen.

> [!NOTE]
> In Szenarien mit Datenlecks besteht die einzige Möglichkeit zum Entfernen von Elementen in einem Überprüfungssatz in der Löschung Advanced eDiscovery Fall. Andere Such- und Bereinigungsmethoden entfernen keine Elemente aus einem Überprüfungssatz.

Bevor Sie einen Fall löschen können (unabhängig davon, ob  er aktiv oder geschlossen ist), müssen Sie zunächst alle dem Fall zugeordneten Halte halte löschen. Dazu gehört das Löschen von Haltestatus mit dem Status **Aus**.

So löschen Sie halte, die einem Fall zugeordnet sind:

1. Wechseln Sie **in** der Advanced eDiscovery, die Sie löschen möchten, auf die Registerkarte Halte haltet.

2. Klicken Sie auf den Halteraum, den Sie löschen möchten.

3. Klicken Sie auf der Flyoutseite auf **Halten löschen**.

So löschen Sie einen Fall

1. Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus, den Sie löschen möchten.

2. Klicken Sie auf der Registerkarte **Einstellungen** unter **Fallinformationen** auf **Auswählen**.

3. Klicken Sie auf **Fall löschen**.

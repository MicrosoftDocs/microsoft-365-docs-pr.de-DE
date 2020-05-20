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
description: Erfahren Sie, was passiert, wenn eine Untersuchung oder ein Rechtsfall, der von einem erweiterten eDiscovery-Fall unterstützt wird, geschlossen oder gelöscht wird.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e64f5cc0483129396a28cbf657778001e5d372a7
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292411"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Schließen oder Löschen eines erweiterten eDiscovery-Falls

Wenn die von einem erweiterten eDiscovery-Fall unterstützte Rechtssache oder Untersuchung abgeschlossen ist, können Sie einen Fall schließen oder löschen. Sie können auch einen geschlossenen Fall erneut öffnen.

## <a name="close-a-case"></a>Schließen einer Anfrage

Hier erfahren Sie, was passiert, wenn Sie einen erweiterten eDiscovery-Fall schließen:

- Wenn der Fall alle inhaltsspeicherorte enthält, sind diese Haltestatus deaktiviert. Dies kann dazu führen, dass Inhalte dauerhaft gelöscht oder gelöscht werden, entweder durch den Benutzer oder durch einen automatisierten Prozess, beispielsweise eine Löschrichtlinie.

- Durch das Schließen eines Case werden nur die haltebereiche deaktiviert, die diesem Fall zugeordnet sind. Wenn andere Aufbewahrungsorte auf einem Inhaltsspeicherort platziert werden (beispielsweise ein Beweissicherungsverfahren, ein zentrales eDiscovery-Archiv oder ein Haltestatus aus einem anderen erweiterten eDiscovery-Fall), werden diese Haltestatus weiterhin beibehalten.

- Der Fall wird weiterhin auf der Seite "eDiscovery" im Microsoft 365 Compliance Center aufgeführt. Die Details, Aufbewahrungen, Suchvorgänge und Elemente eines geschlossenen Falls werden beibehalten.

- Sie können einen Fall bearbeiten, nachdem er geschlossen wurde. Beispielsweise können Sie Mitglieder hinzufügen oder entfernen, suchen erstellen, Suchergebnisse exportieren und Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten. Der Hauptunterschied zwischen aktiven und geschlossenen Fällen besteht darin, dass die haltebereiche deaktiviert sind, wenn ein Fall geschlossen wird.

So schließen Sie einen Fall:

1. Wählen Sie auf der Seite **Erweiterte eDiscovery** die Groß-/Kleinschreibung aus, die Sie schließen möchten.

2. Klicken Sie auf der Registerkarte **Einstellungen** unter **Fall Informationen**auf **auswählen**.

3. Klicken Sie auf **Fall schließen**.

   Es kann bis zu 60 Minuten dauern, bis der Abschlussprozess abgeschlossen ist.

## <a name="reopen-a-closed-case"></a>Erneutes Öffnen eines geschlossenen Falls

Wenn Sie einen erweiterten eDiscovery-Fall erneut öffnen, werden alle holdes-Objekte, die beim Schließen des Case-Verfahrens vorhanden waren, nicht automatisch wieder eingesetzt. Nachdem der Fall erneut geöffnet wurde, müssen Sie zur Registerkarte "halte **Status** " wechseln und die vorherigen Haltestatus aktivieren. Zum Aktivieren eines haltebereichs wählen Sie ihn aus, um die Flyout-Seite anzuzeigen, und legen Sie dann die **Status** Umschalttaste **auf**ein fest.

So öffnen Sie einen geschlossenen Fall erneut:

1. Wählen Sie auf der Seite **Erweiterte eDiscovery** die Groß-/Kleinschreibung aus, die Sie löschen möchten.

2. Klicken Sie auf der Registerkarte **Einstellungen** unter **Fall Informationen**auf **auswählen**.

3. Klicken Sie auf **Fall erneut öffnen**.

   Es kann bis zu 60 Minuten dauern, bis der Vorgang zum erneuten Öffnen abgeschlossen ist.

## <a name="delete-a-case"></a>Löschen einer Anfrage

Sie können sowohl aktive als auch abgeschlossene erweiterte eDiscovery-Fälle löschen. Wenn Sie einen Fall löschen, werden alle mit dem Fall verknüpften Komponenten gelöscht, beispielsweise die Liste der Verwalter, Kommunikationen, Suchvorgänge, Überprüfungs Sätze und Exportaufträge. Der Fall wird aus der Liste der Fälle auf der Seite " **Advanced eDiscovery** " im Microsoft 365 Compliance Center entfernt. Ein gelöschter Fall kann nicht wiederhergestellt oder erneut geöffnet werden.

> [!NOTE]
> In Szenarien mit Datenüberlauf besteht die einzige Möglichkeit zum Entfernen von Elementen in einem Überprüfungs Satzes darin, den erweiterten eDiscovery-Fall zu löschen. Andere Methoden zum Suchen und löschen entfernen keine Elemente aus einem Überprüfungs Satzes.

Bevor Sie einen Fall löschen können (ob er aktiv oder geschlossen ist), müssen Sie zunächst *alle* Haltestatus löschen, die mit der Groß-/Kleinschreibung verknüpft sind. Dies umfasst das Löschen von Haltebereichen mit dem Status **Off**.

So löschen Sie haltebereiche, die einem Fall zugeordnet sind:

1. Wechseln Sie zur Registerkarte halte **Status** im erweiterten eDiscovery-Fall, den Sie löschen möchten.

2. Klicken Sie auf den Haltestatus, den Sie löschen möchten.

3. Klicken Sie auf der Flyout-Seite auf **Haltestatus löschen**.

So löschen Sie einen Fall:

1. Wählen Sie auf der Seite **Erweiterte eDiscovery** die Groß-/Kleinschreibung aus, die Sie löschen möchten.

2. Klicken Sie auf der Registerkarte **Einstellungen** unter **Fall Informationen**auf **auswählen**.

3. Klicken Sie auf **Fall löschen**.

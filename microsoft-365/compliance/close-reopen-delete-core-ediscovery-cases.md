---
title: Schließen, erneutes Öffnen und Löschen von zentralen eDiscovery-Fällen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: In diesem Artikel wird beschrieben, wie Sie zentrale eDiscovery-Fälle verwalten. Dazu gehört das Schließen einer Anfrage, das erneute Öffnen eines geschlossenen Falls und das Löschen einer Anfrage.
ms.openlocfilehash: 41ba622a58b0abb5ce668e6d94d89b1694a328c9
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551423"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a>Schließen, erneutes Öffnen und Löschen eines zentralen eDiscovery-Falls

In diesem Artikel wird beschrieben, wie Sie zentrale eDiscovery-Fälle in Microsoft 365 schließen, erneut öffnen und löschen.

## <a name="close-a-case"></a>Schließen einer Anfrage

Wenn die von einem zentralen eDiscovery-Fall unterstützte Rechtssache oder Untersuchung abgeschlossen ist, können Sie den Fall schließen. Hier erfahren Sie, was passiert, wenn Sie einen Fall schließen:
  
- Wenn der Fall inhaltsspeicherorte in der eDiscovery-Aufbewahrungsstelle enthält, werden diese Haltestatus deaktiviert. Dies kann dazu führen, dass Inhalte dauerhaft gelöscht oder gelöscht werden, entweder durch den Benutzer oder durch einen automatisierten Prozess, beispielsweise eine Löschrichtlinie.

- Durch das Schließen eines Case werden nur die haltebereiche deaktiviert, die diesem Fall zugeordnet sind. Wenn andere haltebereiche an einem Inhaltsspeicherort (beispielsweise ein Beweissicherungsverfahren, eine Aufbewahrungsrichtlinie oder ein Haltestatus von einem anderen zentralen eDiscovery-Fall) gespeichert werden, werden diese Aufbewahrungsorte weiterhin beibehalten.

- Der Fall wird weiterhin auf der zentralen eDiscovery-Seite im Microsoft 365 Compliance Center aufgeführt. Die Details, Aufbewahrungen, Suchvorgänge und Elemente eines geschlossenen Falls werden beibehalten.

- Sie können einen Fall bearbeiten, nachdem er geschlossen wurde. Beispielsweise können Sie Mitglieder hinzufügen oder entfernen, suchen erstellen und Suchergebnisse exportieren. Der Hauptunterschied zwischen aktiven und geschlossenen Fällen besteht darin, dass eDiscovery-Haltestatus deaktiviert sind, wenn ein Fall geschlossen wird.

So schließen Sie einen Fall:
  
1. Klicken Sie im Microsoft 365-Compliance-Eingabefeld auf **eDiscovery** > **Core** , um die Liste der zentralen eDiscovery-Fälle in Ihrer Organisation anzuzeigen.

2. Klicken Sie auf den Namen der Groß-/Kleinschreibung, die Sie schließen möchten.

    Die Dropdown Seite **diesen Fall verwalten** wird angezeigt.

3. Klicken Sie unter **Fall Status verwalten**auf **Schließ Fall**.

    Es wird eine Warnung angezeigt, die besagt, dass die dem Fall zugeordneten Haltestatus deaktiviert werden.

4. Klicken Sie auf **Ja** , um den Fall zu schließen.

    Der Status auf der Flyout-Seite " **diesen Fall verwalten** " wird von " **aktiv** " in " **Schließen**" geändert.

5. Schließen Sie die Seite **diesen Fall verwalten** .

6. Klicken Sie auf der **zentralen eDiscovery** -Seite auf **Aktualisieren** , um den Status des geschlossenen Falls zu aktualisieren. Es kann bis zu 60 Minuten dauern, bis der Abschlussprozess abgeschlossen ist.

    Wenn der Prozess abgeschlossen ist, wird der Status der Anfrage in **geschlossen** auf der **zentralen eDiscovery** -Seite geändert. Klicken Sie erneut auf den Namen der Anfrage, um die Flyout-Seite " **diesen Fall verwalten** " anzuzeigen, die Informationen dazu enthält, wann der Fall geschlossen wurde und wer ihn geschlossen hat.

## <a name="reopen-a-closed-case"></a>Erneutes Öffnen eines geschlossenen Falls

Wenn Sie einen Fall erneut öffnen, werden alle eDiscovery-Aufbewahrungsorte, die bei der Schließung des Falles abgeschlossen wurden, nicht automatisch wieder eingesetzt. Nachdem der Fall erneut geöffnet wurde, müssen Sie zur Seite "halte **Status** " wechseln und die vorherigen Haltestatus aktivieren. Zum Aktivieren eines haltebereichs wählen Sie ihn aus, um die Flyout-Seite anzuzeigen, und legen Sie dann die **Status** Umschalttaste **auf**ein fest.
  
1. Klicken Sie im Microsoft 365-Compliance-Eingabefeld auf **eDiscovery** > **Core** , um die Liste der zentralen eDiscovery-Fälle in Ihrer Organisation anzuzeigen.

2. Klicken Sie auf den Namen der Groß-/Kleinschreibung, die Sie erneut öffnen möchten.

    Die Dropdown Seite **diesen Fall verwalten** wird angezeigt. 

3. Klicken Sie unter **Fall Status verwalten**auf **erneuter Fall öffnen**.

    Es wird eine Warnung angezeigt, die besagt, dass die haltebereiche, die dem Fall beim Schließen zugeordnet waren, nicht automatisch aktiviert werden.

4. Klicken Sie auf **Ja** , um die Anfrage erneut zu öffnen.

    Der Status auf der Flyout-Seite " **diesen Fall verwalten** " wird von " **geschlossen** " in " **aktiv**" geändert.

5. Schließen Sie die Seite **diesen Fall verwalten** . 

6. Klicken Sie auf der **zentralen eDiscovery** -Seite auf **Aktualisieren** , um den Status des erneut geöffneten Falls zu aktualisieren. Es kann bis zu 60 Minuten dauern, bis der Vorgang zum erneuten Öffnen abgeschlossen ist. 

    Wenn der Prozess abgeschlossen ist, wird der Status der Groß-/Kleinschreibung auf der **zentralen eDiscovery** -Seite in " **aktiv** " geändert. 
  
## <a name="delete-a-case"></a>Löschen einer Anfrage

Sie können auch aktive und geschlossene Haupt-eDiscovery-Fälle löschen. Wenn Sie einen Fall löschen, werden alle Suchvorgänge und Exporte gelöscht, und der Fall wird aus der Liste der Fälle auf der **zentralen eDiscovery** -Seite im Microsoft 365 Compliance Center entfernt. Sie können einen gelöschten Fall nicht erneut öffnen.

Bevor Sie einen Fall löschen können (ob er aktiv oder geschlossen ist), müssen Sie zuerst *alle* eDiscovery-Haltestatus löschen, die mit der Anfrage verknüpft sind. Dies umfasst das Löschen von Haltebereichen mit dem Status **Off**. 

So löschen Sie eine eDiscovery-Sperre:

1. Wechseln Sie zur Registerkarte halte **Status** in dem Fall, den Sie löschen möchten.

2. Klicken Sie auf den Haltestatus, den Sie löschen möchten.

3. Klicken Sie auf der Flyout-Seite auf **Haltestatus löschen**.

So löschen Sie einen Fall:

1. Klicken Sie im Microsoft 365-Compliance-Eingabefeld auf **eDiscovery** > **Core** , um die Liste der zentralen eDiscovery-Fälle in Ihrer Organisation anzuzeigen.

2. Klicken Sie auf den Namen der Groß-/Kleinschreibung, die Sie löschen möchten.

3. Klicken Sie unter **Fall Status verwalten** auf der Flyout-Seite auf **Fall löschen**.

Wenn der Fall, den Sie löschen möchten, weiterhin eDiscovery-Haltestatus enthält, erhalten Sie eine Fehlermeldung. Sie müssen alle dem Fall zugeordneten haltebereiche löschen und dann erneut versuchen, die Groß-/Kleinschreibung zu löschen.

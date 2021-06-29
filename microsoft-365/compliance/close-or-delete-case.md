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
description: Erfahren Sie, was geschieht, wenn eine Untersuchung oder ein Rechtsfall, der von einem Advanced eDiscovery Fall unterstützt wird, geschlossen oder gelöscht wird.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: efbcbe34e6d7d8b564bcfa0cf9bbd8a1fbb59709
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194628"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Schließen oder Löschen eines Advanced eDiscovery Falls

Wenn der von einem Advanced eDiscovery Fall unterstützte Rechtsfall oder die Untersuchung abgeschlossen ist, können Sie einen Fall schließen oder löschen. Sie können auch einen geschlossenen Fall erneut öffnen.

## <a name="close-a-case"></a>Schließen eines Falls

Dies geschieht, wenn Sie einen Advanced eDiscovery Fall schließen:

- Wenn der Fall in den Haltebereich versetzte Inhaltsspeicherorte enthält, werden diese Haltebereiche deaktiviert. Nachdem die Aufbewahrung deaktiviert wurde, wird eine 30-tägige Nachfrist (als *Verzögerungssperre* bezeichnet) auf Inhaltsspeicherorte angewendet, die in der Warteschleife waren. Dadurch wird verhindert, dass Inhalte sofort gelöscht werden, und Administratoren erhalten die Möglichkeit, nach Inhalten zu suchen oder sie wiederherzustellen, die nach Ablauf der Verzögerungssperre endgültig gelöscht werden. Weitere Informationen finden Sie unter [Entfernen von Inhaltsspeicherorten aus einem eDiscovery-Haltebereich.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)

- Durch das Abschließen eines Falls werden nur die Haltebereiche deaktiviert, die diesem Fall zugeordnet sind. Wenn andere Haltebereiche an einem Inhaltsspeicherort (z. B. einem Beweissicherungsverfahren, einem Core eDiscovery-Haltebereich oder einem Haltebereich eines anderen Advanced eDiscovery Falls) platziert werden, werden diese Haltebereiche weiterhin beibehalten.

- The case is still listed on the eDiscovery page in the Microsoft 365 Compliance Center. Die Details, Haltebereiche, Suchvorgänge und Mitglieder eines abgeschlossenen Falls bleiben erhalten.

- Sie können einen Fall bearbeiten, nachdem er geschlossen wurde. Sie können beispielsweise Mitglieder hinzufügen oder entfernen, Suchen erstellen, Suchergebnisse exportieren und Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten. Der Hauptunterschied zwischen aktiven und abgeschlossenen Fällen ist, dass die Haltebereiche beim Abschließen eines Falls deaktiviert werden.

So schließen Sie einen Fall ab

1. Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus, den Sie schließen möchten.

2. Klicken Sie auf der Registerkarte **Einstellungen** unter **Fallinformationen** auf **Auswählen**.

   ![Zugreifen auf die Flyoutseite für Fallinformationen in einem Advanced eDiscovery Fall](..\media\AeDSelectCaseInformation.png) 

3. Klicken Sie unten auf der Flyoutseite **"Fallinformationen"** auf **"Aktionen",** und klicken Sie dann auf **"Groß-/Kleinschreibung schließen".**

   Es kann bis zu 60 Minuten dauern, bis der Abschlussvorgang abgeschlossen ist.

## <a name="reopen-a-closed-case"></a>Erneutes Öffnen eines geschlossenen Falls

Wenn Sie einen Advanced eDiscovery Fall erneut öffnen, werden alle Haltebereiche, die beim Schließen des Falls vorhanden waren, nicht automatisch wiederhergestellt. Nachdem der Fall erneut geöffnet wurde, müssen Sie zur Registerkarte **"Haltebereiche"** wechseln und die vorherigen Haltebereiche aktivieren. Wenn Sie einen Haltebereich aktivieren möchten, wählen Sie ihn aus, um die Flyout-Seite anzuzeigen, und legen Sie dann den **Status** auf **Ein** fest.

So öffnen Sie einen geschlossenen Fall erneut:

1. Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus, den Sie erneut öffnen möchten.

2. Klicken Sie auf der Registerkarte **Einstellungen** unter **Fallinformationen** auf **Auswählen**.

3. Klicken Sie unten auf der Flyoutseite **"Fallinformationen"** auf **"Aktionen"** und dann auf **"Groß-/Kleinschreibung erneut öffnen".**

   Es kann bis zu 60 Minuten dauern, bis der erneute Vorgang abgeschlossen ist.

## <a name="delete-a-case"></a>Löschen eines Falls

Sie können aktive und geschlossene Advanced eDiscovery Fälle löschen. Wenn Sie einen Fall löschen, werden alle dem Fall zugeordneten Komponenten, z. B. die Liste von Verwaltern, die Kommunikation, Suchvorgänge, Überprüfungssätze und der Exportvorgang, gelöscht. Der Fall wird aus der Liste der Fälle auf der **Advanced eDiscovery** Seite im Microsoft 365 Compliance Center entfernt. Sie können einen gelöschten Fall nicht wiederherstellen oder erneut öffnen.

> [!NOTE]
> In Szenarien mit Datenlecks besteht die einzige Möglichkeit zum Entfernen von Elementen in einem Prüfdateisatz darin, den Advanced eDiscovery Fall zu löschen. Andere "Such- und Bereinigungsmethoden" entfernen keine Elemente aus einem Prüfdateisatz.

Bevor Sie einen Fall löschen können (unabhängig davon, ob er aktiv oder geschlossen ist), müssen Sie zunächst *alle* haltebereiche löschen, die dem Fall zugeordnet sind. Dazu gehört das Löschen von Haltebereichen mit dem Status **"Aus".**

So löschen Sie haltebereiche, die einem Fall zugeordnet sind:

1. Wechseln Sie zur Registerkarte **"Haltebereiche"** im Advanced eDiscovery Fall, den Sie löschen möchten.

2. Klicken Sie auf den Haltebereich, den Sie löschen möchten.

3. Klicken Sie auf der Flyoutseite auf **"Haltebereich löschen".**

So löschen Sie einen Fall

1. Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus, den Sie löschen möchten.

2. Klicken Sie auf der Registerkarte **Einstellungen** unter **Fallinformationen** auf **Auswählen**.

3. Klicken Sie unten auf der Flyoutseite **"Fallinformationen"** auf **"Aktionen",** und klicken Sie dann auf **"Groß-/Kleinschreibung löschen".**


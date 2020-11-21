---
title: Zuweisen und Abschließen von Verbesserungs Aktionen im Microsoft Compliance-Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie Implementierungen und Tests für Steuerelemente im Microsoft Compliance-Manager durchführen. Zuweisen von Arbeit, Speichern einer Dokumentation und Exportieren von Berichten
ms.openlocfilehash: 4b7ece89752a2c3e54a0a69bade2f489feacd0c3
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376526"
---
# <a name="assign-and-complete-improvement-actions-in-compliance-manager"></a>Zuweisen und Abschließen von Verbesserungs Aktionen im Compliance-Manager

**In diesem Artikel:** In diesem Artikel wird erläutert, wie **Sie den Compliance-Workflow** mit Verbesserungs Aktionen verwalten. Hier erfahren Sie, wie Sie **Verbesserungs Aktionen** für Implementierung und Test, **Verwalten von Updates** und Exportieren von **Berichten** zuweisen.

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Verwalten von Compliance-Workflows mit Verbesserungs Aktionen

Verbesserungs Aktionen zentralisieren Sie Ihre Compliance-Aktivitäten. Jede Verbesserungs Aktion enthält detaillierte Anweisungen zur Implementierung, die Sie bei der Anpassung an Datenschutzbestimmungen und-Standards unterstützen. Aktionen können Benutzern in Ihrer Organisation zugewiesen werden, um Implementierungs-und Testaufgaben auszuführen. Sie können auch Dokumentation, Notizen und Datensatzstatus Aktualisierungen in der Aktion speichern.

Alle Ihre Verbesserungs Aktionen werden auf der Seite Verbesserungs Aktionen aufgelistet. Erfahren Sie mehr über [das Anzeigen von Verbesserungs Aktionen](compliance-manager-setup.md#improvement-actions-page).

## <a name="improvement-actions-details-page"></a>Detailseite für Verbesserungs Aktionen

Jede Verbesserungs Aktion verfügt über eine Detailseite mit dem aktuellen Status, den zugehörigen Standards und behördlichen Anforderungen sowie empfohlenen Implementierungsanleitungen. [Technische Aktionen](compliance-score-calculation.md#technical-and-non-technical-actions) umfassen einen Link **jetzt starten** , der Sie zur geeigneten Lösung für die Implementierung führt. Sie können die Implementierungs-und Testdokumentation direkt an der Detailseite einer Verbesserungs Aktion anfügen.

So zeigen Sie die Detailseite einer Verbesserungs Aktion an:

1. Wechseln Sie zur Seite Verbesserungs Aktionen.
2. Wählen Sie die Zeile der beabsichtigten Verbesserungs Aktion aus, in der die zugehörige Detailseite geöffnet wird.

Sie können die nächste oder frühere Verbesserungs Aktion ganz einfach in der Liste anzeigen, indem Sie den nach-oben-oder nach-unten-Pfeil in der oberen rechten Ecke des Bildschirms auswählen. Wenn Sie Ihre Liste auf der Seite Verbesserungs Aktionen gefiltert haben, gelangen Sie zum nächsten Element in der gefilterten Liste, indem Sie nach oben oder unten navigieren.

## <a name="assign-improvement-actions"></a>Zuweisen von Verbesserungs Aktionen

Um mit der Implementierung an einer Verbesserungs Aktion zu beginnen, können Sie die Arbeit selbst durchführen oder einem anderen Benutzer zuweisen. Die zugewiesene Person kann Folgendes sein:

- Der Besitzer einer Unternehmensrichtlinie
- Ein IT-Implementierer
- Ein weiterer Mitarbeiter, der für die Ausführung der Aufgabe zuständig ist

Wenn Sie den entsprechenden Empfänger identifiziert haben, müssen Sie sicherstellen, dass er eine ausreichende [Compliance-Manager-Rolle](compliance-manager-setup.md#set-user-permissions-and-assign-roles) besitzt, um die Arbeit auszuführen. Führen Sie dann die folgenden Schritte aus, um die Verbesserungs Aktion zuzuweisen:

1. Klicken Sie auf der Seite Details zur Verbesserungs Aktionen im oberen linken Bereich des Bildschirms auf **Status bearbeiten** .

2. Aktivieren Sie im Flyout-Dialogfeld Status bearbeiten das Kontrollkästchen **zugewiesen an** , um eine Liste der Benutzer **vorgeschlagener Personen** anzuzeigen. Sie können den Benutzer aus der Liste auswählen oder die e-Mail-Adresse der Person eingeben, der Sie diese zuweisen möchten.

3. Wählen Sie **Speichern und schließen** aus. Der zugewiesene Benutzer erhält eine e-Mail mit der Erklärung, dass ihm die Verbesserungs Aktion zugewiesen wurde, mit einem direkten Link zur Verbesserungs Aktion. (Hinweis: High-End-Kunden der US Government Community (gcc) erhalten keine e-Mail, wenn Ihnen Aktionen zugewiesen sind.)

Der zugewiesene Benutzer kann dann die empfohlenen Aktionen ausführen.

## <a name="perform-work-and-store-documentation"></a>Ausführen der Dokumentation zu Arbeits-und Speicheraufgaben

Sie können Dateien und Notizen im Zusammenhang mit Implementierungs-und Testaufgaben direkt im Abschnitt **Hinweise und Dokumentation** hochladen. Diese Umgebung ist ein sicheres, zentralisiertes Repository, mit dem Sie die Zufriedenheit von Steuerelementen zur Erfüllung von Compliance-Standards und-Vorschriften demonstrieren können. Jeder Benutzer mit schreibgeschütztem Zugriff kann Inhalt in diesem Abschnitt lesen. Nur Benutzer mit Bearbeitungsrechten können Dateien hochladen und herunterladen sowie Notizen eingeben oder bearbeiten.

Der Abschnitt " **Notizen und Dokumentation** " enthält Felder für hochgeladene Dokumente, Implementierungshinweise, Test Notizen und zusätzliche Notizen.

#### <a name="uploaded-documents"></a>Hochgeladene Dokumente

- Wählen Sie **Dokumente verwalten** aus, um relevante Dateien hochzuladen.
- Wenn der Fensterausschnitt zum Verwalten von Dokumenten geöffnet wird, wählen Sie **Dokument hinzufügen** aus, und wählen Sie dann Ihre Datei von Ihrem System aus. Akzeptierte Dateitypen:
    - Dokumente (. doc,. xls,. ppt,. txt,. pdf)
    - Bilder (. jpg,. png)
    - Video (. MKV)
    - Komprimierte Dateien (ZIP, rar)
- Nachdem die Datei im Bereich aufgelöst wurde, wählen Sie **Close** aus, wodurch die Dateianlage automatisch gespeichert wird. Anschließend wird die Datei unterhalb der **hochgeladenen Dokumente** aufgeführt angezeigt.
- Um das Dokument herunterzuladen oder zu löschen, wählen Sie Dokumente aus unterhalb der Liste der Dokumente **Verwalten** aus. Wählen Sie im Flyout-Bereich die Dokumentzeile aus, um Sie hervorzuheben, und wählen Sie dann **herunterladen** oder **Löschen** aus.

#### <a name="implementation-notes-test-notes-and-additional-notes"></a>Implementierungshinweise, Test Notizen und zusätzliche Hinweise

- Wenn Sie in einem dieser drei Felder Notizen hinzufügen möchten, wählen Sie unter einem dieser Felder die Option " **Implementierungshinweise bearbeiten** " aus.
- Wenn der Flyout-Bereich geöffnet wird, geben Sie Notizen in das Textfeld ein, und klicken Sie dann auf **Speichern und schließen**.
- Um Notizen zu bearbeiten, wählen Sie **Anmerkungen zur Implementierung bearbeiten** aus, nehmen Sie Ihre Änderungen vor, und klicken Sie dann auf **Speichern und schließen**.

In den Notizen Feldern ist kein Zeichen Grenzwert vorhanden. Es wird empfohlen, Notizen kurz aufzubewahren, damit Sie Sie auf der Detailseite der Verbesserungs Aktionen ganz einfach anzeigen und bearbeiten können.

## <a name="change-improvement-action-status"></a>Status der Änderungs Verbesserungs Aktion

Sie können den Status und das Datum der Implementierung sowie den Teststatus und das Datum für jede Verbesserungs Aktion aufzeichnen. Die Felder " **Implementierung** " und " **Teststatus** " können von jedem Benutzer mit Bearbeitungsberechtigungen bearbeitet werden, nicht nur von der zugewiesenen Person.

Um den Status einer Verbesserungs Aktion zu bearbeiten, wählen Sie im Abschnitt oben links auf der Seite Details die Option **Status bearbeiten** aus. Im folgenden finden Sie die verfügbaren Felder und Statusoptionen:

- **Implementierungsstatus**
    - **Nicht implementiert** – Aktion noch nicht implementiert
    - **Implementiert** -Aktion implementiert
    - **Alternative Implementierung** : Wählen Sie diese Option aus, wenn Sie andere Tools von Drittanbietern verwendet haben oder andere Aktionen ergriffen haben, die nicht in Microsoft-Empfehlungen enthalten sind.
    - **Geplante** Aktion ist für die Implementierung geplant
    - **Außerhalb des Bereichs** – Aktionen sind für Ihre Organisation nicht relevant und tragen nicht zu ihrer Bewertung bei.
- **Implementierungsdatum**: verfügbar zur Auswahl, wenn der Implementierungsstatus "implementiert" oder "alternative Implementierung" lautet
- **Test Status**: verfügbar zur Auswahl, wenn der Implementierungsstatus "implementiert" oder "alternative Implementierung" lautet:
    - **Nicht bewertet** – Aktion wurde nicht getestet
    - Die **übergebene** Implementierung wurde von einem Auditor überprüft.
    - **Fehlgeschlagenes niedriges Risiko** – Testfehler, geringes Risiko
    - **Fehler bei mittlerem Risiko** – Testfehler, mittleres Risiko
    - **Gescheitertes hohes Risiko** – Testfehler, hohes Risiko
    - **Außerhalb des Gültigkeitsbereichs** – die Aktion liegt außerhalb des Bereichs für die Bewertung und trägt nicht zu ihrem Ergebnis bei.
- **Testdatum**: wechselt durch das Popup Kalenderfenster, um das Datum auszuwählen.

Häufige Aktionen synchronisieren gruppenübergreifend. Wenn zwei unterschiedliche Bewertungen in der gleichen Gruppe Verbesserungen durchführen, die von Ihnen verwaltet werden, werden alle Aktualisierungen, die Sie an den Implementierungsdetails oder Status einer Aktion vornehmen, automatisch mit derselben Aktion in einer anderen Bewertung in der Gruppe synchronisiert. Mit dieser Synchronisierung können Sie eine Verbesserungs Aktion implementieren und mehrere Anforderungen in mehreren Bestimmungen erfüllen.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Zuweisen von Verbesserungs Aktionen zum Abschlussprüfer

Nachdem Sie die Arbeit abgeschlossen, Tests durchgeführt und Beweise hochgeladen haben, besteht der nächste Schritt darin, die Verbesserungs Aktion einem Gutachter zur Überprüfung zuzuweisen. Der Assessor überprüft die Arbeit und untersucht die Dokumentation und wählt den entsprechenden Teststatus aus.

**Wenn der Teststatus auf "übergeben" festgelegt ist**: die Aktion ist abgeschlossen, und die erreichten Punkte zeigen die erreichten maximalpunkte. Die Punkte werden dann auf Ihre gesamte Konformitätsbewertung gezählt.

**Wenn der Teststatus auf "failed" festgelegt ist**: die Aktion erfüllt die Anforderungen nicht, und der Auditor kann Sie dem entsprechenden Benutzer für zusätzliche Arbeit zurückzuweisen.

## <a name="accepting-updates-to-improvement-actions"></a>Akzeptieren von Aktualisierungen für Verbesserungs Aktionen

Wenn ein Update für eine Verbesserungs Aktion verfügbar ist, wird neben dem Namen eine Benachrichtigung angezeigt. Sie können entweder das Update annehmen oder es zu einem späteren Zeitpunkt verschieben.

#### <a name="what-causes-an-update"></a>Was bewirkt, dass ein Update

Eine Aktualisierung tritt auf, wenn Änderungen im Zusammenhang mit Scoring, Automatisierung oder Bereich vorgenommen werden. Änderungen können neue Richtlinien für Verbesserungs Aktionen basierend auf regulatorischen Änderungen oder aufgrund von Produktänderungen beinhalten. Nur die von ihren Organisationen verwalteten Verbesserungs Aktionen erhalten Aktualisierungsbenachrichtigungen.

#### <a name="where-youll-see-assessment-update-notifications"></a>Wo Sie Benachrichtigungen über Bewertungs Updates sehen

Wenn eine Verbesserungs Aktion aktualisiert wird, wird eine **ausstehende Update** Bezeichnung neben dem Namen auf der Seite Verbesserungs Aktionen und auf der Seite Details der zugehörigen Bewertungen angezeigt.

Wechseln Sie zur Detailseite der Verbesserungs Aktion, und wählen Sie die Schaltfläche **Update überprüfen** im oberen Banner aus, um Details zu den Änderungen zu überprüfen und das Update zu akzeptieren oder zu verschieben.

#### <a name="review-update-to-accept-or-defer"></a>Überprüfen der Aktualisierung zur Annahme oder Verschiebung

Nachdem Sie **Update überprüfen** auf der Seite Details zur Verbesserungs Aktion ausgewählt haben, wird auf der rechten Seite des Bildschirms ein Flyout-Bereich angezeigt. Der Flyout-Bereich enthält wichtige Details zum Update, beispielsweise die Auswirkungen auf die Bewertung und die Änderungen in der Bewertung und im Bereich.

Wählen Sie **Update akzeptieren** aus, um alle Änderungen an der Verbesserungs Aktion zu akzeptieren. **Akzeptierte Änderungen sind dauerhaft**.

> [!NOTE]
> Wenn Sie eine Aktualisierung einer Aktion akzeptieren, akzeptieren Sie auch Aktualisierungen für andere Versionen oder Instanzen dieser Aktion. Updates werden mandantenweit für Technische Aktionen weitergegeben und werden gruppenweit für nicht technische Aktionen weitergegeben.

Wenn Sie **Abbrechen** auswählen, wird das Update nicht auf die Verbesserungs Aktion angewendet. Die Benachrichtigung über **ausstehende Updates** wird jedoch weiterhin angezeigt, bis Sie das Update akzeptieren.

**Warum wird empfohlen, Updates zu akzeptieren?**

Durch das akzeptieren von Updates können Sie sicherstellen, dass Sie über die neuesten Anleitungen zur Verwendung von Lösungen und geeignete Verbesserungsmaßnahmen verfügen, die Ihnen helfen, die Anforderungen der Zertifizierung zur Hand zu erfüllen.

**Warum Sie ein Update möglicherweise verschieben möchten**

Wenn Sie sich mitten in einer Bewertung befinden, die die Verbesserungs Aktion enthält, sollten Sie sicherstellen, dass Sie die Arbeit daran abgeschlossen haben, bevor Sie das Update akzeptieren. Sie können das Update zu einem späteren Zeitpunkt verschieben, indem Sie im Flyout-Bereich Update aktualisieren die Option **Abbrechen** auswählen.

## <a name="export-a-report"></a>Exportieren eines Berichts

Wählen Sie in der oberen linken Ecke des Bildschirms **exportieren** aus, um ein Excel-Arbeitsblatt herunterzuladen, das alle Ihre Verbesserungs Aktionen und die Filterkategorien enthält, die auf der Seite Verbesserungs Aktionen angezeigt werden.
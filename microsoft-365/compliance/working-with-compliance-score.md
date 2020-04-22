---
title: Arbeiten mit dem Microsoft Compliance Score
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
description: In diesem Artikel erfahren Sie, wie Sie mithilfe der Workflowtools in Microsoft Compliance Score die Compliance für Ihre Organisation verwalten können.
ms.openlocfilehash: 8bef3e09decede679d5d0667360ba87b7cd7e6ad
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626221"
---
# <a name="working-with-microsoft-compliance-score-preview"></a>Arbeiten mit Microsoft Compliance Score (Vorschau)

In diesem Artikel wird erläutert, wie Sie mit den wichtigsten Elementen der Konformitätsbewertung arbeiten. In diesem Artikel erfahren Sie, wie Sie mithilfe von **Verbesserungs Aktionen** den Compliance-Workflow verwalten. Außerdem erfahren Sie, wie Sie die Informationen auf Ihren **Lösungen** und **Bewertungs** Seiten verwenden und wie Sie Berichte erstellen.

## <a name="manage-your-workflow-with-improvement-actions"></a>Verwalten des Workflows mit Verbesserungs Aktionen

**Verbesserungs Aktionen** zentralisieren Sie Ihre Compliance-Aktivitäten. Jede Verbesserungs Aktion enthält detaillierte Anweisungen zur Implementierung, die Sie bei der Anpassung an Datenschutzbestimmungen und-Standards unterstützen. Aktionen können Benutzern in Ihrer Organisation zugewiesen werden, um Implementierungs-und Testaufgaben auszuführen. Sie können auch Dokumentation, Notizen und Datensatzstatus Aktualisierungen in der Verbesserungs Aktion speichern.

## <a name="view-your-improvement-actions"></a>Anzeigen von Verbesserungs Aktionen

Das Kompatibilitäts Bewertungs Dashboard zeigt Ihre **wichtigsten Verbesserungs Aktionen**an – diejenigen mit den am besten verfügbaren Punkten, die die wichtigsten Probleme behandeln.

Um alle Ihre Verbesserungs Aktionen auf der Seite **Verbesserungs Aktionen** anzuzeigen, wählen Sie die Registerkarte **Verbesserungs** Aktionen in Ihrem Dashboard aus. Oder wählen Sie **alle Verbesserungs Aktionen** unterhalb der Liste der wichtigsten Verbesserungs Aktionen in Ihrem Dashboard anzeigen aus.

Wenn Sie eine lange Liste von Aktionen haben, ist es möglicherweise hilfreich, Ihre Ansicht zu filtern. Wählen Sie in der Liste Aktionen in der rechten oberen Ecke den **Filter** aus. Wenn der **Filter** Flyout-Bereich angezeigt wird, wählen Sie Ihre Kriterien basierend auf Regeln und Standards, Lösung und Gruppe aus. Sie können die Ansicht auch anpassen, indem Sie in der oberen rechten Ecke die Option **Gruppe** auswählen. Wählen Sie im Dropdownmenü die Option aus, um nach Gruppe, Lösung, Kategorie, Aktionstyp oder Status anzuzeigen.

In der Standardansicht für diese Seite werden keine Verbesserungs Aktionen mit dem Teststatus " **übergeben**" angezeigt. Zum Anzeigen von Aktionen, die Tests bestanden haben, aktivieren Sie das Kontrollkästchen **übergebenes** Feld im Dropdownbereich **Filter** . Nur Aktionen mit einem Teststatus der **übergebenen** Zählung zu Ihrer Partitur.

Auf der Seite Verbesserungs Aktionen werden die folgenden Datenpunkte für jede Verbesserungs Aktion angezeigt:

- **Ergebnisauswirkung**: die Punkte, um die sich die Gesamtpunktzahl beim Abschließen der Aktion erhöht
- **Bestimmungen**: die Richtlinie oder Norm im Zusammenhang mit der Aktion
- **Gruppe**: die Gruppe, der Sie die Aktion zugewiesen haben
- **Lösungen**: die Lösung, mit der Sie zur Ausführung der Aktion wechseln können
- **Assessments**: die Bewertung (die Steuerelemente zur Erfüllung eines bestimmten Compliance-Ziels organisiert), in dem sich die Aktion befindet
- **Kategorien**: die zugehörige Datenschutzkategorie (beispielsweise zum Schutz von Informationen, Verwalten von Geräten usw.)
- **Test Status**:
    - **None** : keine Statusaktualisierung aufgezeichnet
    - **Nicht bewertet** – Test wurde nicht gestartet
    - **Nicht im Bereich** – wird von der Berechnung der Konformitätsbewertung ausgeschlossen und erhöht nicht Ihre Punktzahl
    - **Teilweise getestet** – Test ist noch nicht abgeschlossen
    - **Fehlerhafte hohe Risiko** Tests für die Implementierung sind fehlgeschlagen, und das Risiko der Nichteinhaltung des anwendbaren Standards ist hoch
    - **Übergebene** Implementierung erfolgreich getestet
- **Erzielter Punkt**: zeigt Punkte an, die aus dem Maximum erreicht wurden, das erzielt werden konnte.

### <a name="improvement-actions-details"></a>Details zur Verbesserungs Aktionen

Jede Verbesserungs Aktion verfügt über eine Detailseite. Auf dieser Seite finden Sie detaillierte Anweisungen zur Implementierung der empfohlenen Aktionen zur Behebung der entsprechenden Standards und behördlichen Anforderungen, die unter der Überschrift " **auf einen Blick** " aufgeführt sind.

Auf der Seite Details können Sie die empfohlene Aktion starten. Sie können die Arbeit auch einem anderen Benutzer zuweisen, den Status aktualisieren und Notizen und Dokumentation anfügen.

So zeigen Sie die Detailseite einer Verbesserungs Aktion an:

1. Wechseln Sie zur Seite Verbesserungs Aktionen.
2. Klicken oder tippen Sie auf eine beliebige Stelle in der Zeile der beabsichtigten Verbesserungs Aktion, in der die zugehörige Detailseite geöffnet wird.

Sie können die nächste oder frühere Verbesserungs Aktion ganz einfach in der Liste anzeigen, indem Sie den nach-oben-oder nach-unten-Pfeil in der oberen rechten Ecke des Bildschirms auswählen. Wenn Sie Ihre Liste auf der Seite Verbesserungs Aktionen gefiltert haben, gelangen Sie zum nächsten Element in der gefilterten Liste, das Sie nach oben oder unten verschiebt.

## <a name="assign-improvement-actions"></a>Zuweisen von Verbesserungs Aktionen

Um mit der Implementierung an einer Verbesserungs Aktion zu beginnen, können Sie die Arbeit selbst durchführen oder einem anderen Benutzer zuweisen. Die zugewiesene Person kann Folgendes sein:

- Der Besitzer einer Unternehmensrichtlinie
- Ein IT-Implementierer
- Ein weiterer Mitarbeiter, der für die Ausführung der Aufgabe zuständig ist

Wenn die richtige Person identifiziert wurde, stellen Sie sicher, dass Sie eine ausreichende [Rolle](compliance-score-setup.md#set-user-permissions-and-assign-roles) in Compliance Score (Compliance-Administrator, Kompatibilitätsdaten Administrator, Sicherheitsadministrator oder globaler Administrator) besitzen, um die Arbeit auszuführen, und führen Sie dann die folgenden Schritte aus: 

1. Klicken Sie auf der Seite Details zur Verbesserungs Aktionen im oberen linken Bereich des Bildschirms auf **Status bearbeiten** . 

2. Klicken oder tippen Sie im Flyout-Fensterbereich Bearbeitungsstatus auf das Feld **zugewiesen an** , in dem eine Liste der **vorgeschlagenen Personen** mit Benutzern aufgefüllt wird. Sie können den Benutzer aus der Liste auswählen oder die e-Mail-Adresse der Person eingeben, der Sie die Aktion zuweisen möchten.

3. Klicken Sie auf **Speichern und schließen** , um die Zuordnung abzuschließen. Der zugewiesene Benutzer erhält eine e-Mail, der die Verbesserungs Aktion zugewiesen wurde, und er kann dann die Verbesserungs Aktion in seinem Dashboard öffnen.

Der zugewiesene Benutzer kann dann die empfohlenen Aktionen ausführen, die in den Anweisungen zur Implementierung beschrieben sind.

## <a name="perform-work-and-store-documentation"></a>Ausführen der Dokumentation zu Arbeits-und Speicheraufgaben

Wenn Sie Implementierungsaufgaben ausführen, können Sie Dateien und Notizen direkt in die Verbesserungs Aktion im Abschnitt **Hinweise und Dokumentation** hochladen.  Diese Umgebung ist ein sicheres, zentralisiertes Repository, mit dem Sie die Zufriedenheit von Steuerelementen zur Erfüllung von Compliance-Standards und-Vorschriften demonstrieren können. Jeder Benutzer mit schreibgeschütztem Zugriff kann Inhalt in diesem Abschnitt lesen. Nur Benutzer mit Bearbeitungsrechten können Dateien hochladen und herunterladen sowie Notizen eingeben oder bearbeiten.

Die Felder im Abschnitt " **Notizen und Dokumentation** " umfassen Folgendes:

**Hochgeladene Dokumente**

- Wählen Sie **Dokumente verwalten** aus, um relevante Dateien hochzuladen.
- Wenn der Fensterausschnitt zum Verwalten von Dokumenten geöffnet wird, wählen Sie **Dokument hinzufügen**aus, und wählen Sie dann Ihre Datei von Ihrem System aus. Akzeptierte Dateitypen: 
  - Dokumente (. doc,. xls,. ppt,. txt,. pdf)
  - Bilder (. jpg,. png)
  - Video (. MKV)
  - Komprimierte Dateien (ZIP, rar)
- Nachdem Ihre Datei im Bereich aufgelöst wurde, wählen Sie **Close aus,** wodurch die Dateianlage automatisch gespeichert wird. Anschließend wird die Datei unterhalb der **hochgeladenen Dokumente** aufgeführt angezeigt. 
- Um das Dokument herunterzuladen oder zu löschen, wählen Sie Dokumente aus unterhalb der Liste der Dokumente **Verwalten** aus. Klicken oder tippen Sie im Flyout-Bereich auf die Dokumentzeile, um Sie hervorzuheben, und wählen Sie dann **herunterladen** oder **Löschen aus.**

**Implementierung, Test und zusätzliche Hinweise**

- Wenn Sie in einem dieser drei Felder Notizen hinzufügen möchten, wählen Sie unter einem dieser Felder die Option " **Implementierungshinweise bearbeiten** " aus.
- Wenn der Flyout-Bereich geöffnet wird, geben Sie Notizen in das Textfeld ein, und klicken Sie dann auf **Speichern und schließen**.
- Um Notizen zu bearbeiten, wählen Sie **Anmerkungen zur Implementierung bearbeiten**aus, nehmen Sie Ihre Änderungen vor, und klicken Sie dann auf **Speichern und schließen**.

In den Notizen Feldern ist kein Zeichen Grenzwert vorhanden. Es wird empfohlen, Notizen kurz aufzubewahren, damit Sie Sie auf der Detailseite der Verbesserungs Aktionen ganz einfach anzeigen und bearbeiten können.

## <a name="change-improvement-action-status"></a>Status der Änderungs Verbesserungs Aktion

Sie können den Status und das Datum der Implementierung sowie den Teststatus und das Datum für jede Verbesserungs Aktion aufzeichnen. Im folgenden finden Sie die verfügbaren Felder und Statusoptionen:

- **Implementierungsstatus**: Wählen Sie aus den folgenden Statusoptionen aus:
    - **Nicht implementiert** – Aktion noch nicht implementiert
    - **Implementiert** -Aktion implementiert
    - **Alternative Implementierung** : Wählen Sie diese Option aus, wenn Sie andere Tools von Drittanbietern verwendet haben oder andere Aktionen ergriffen haben, die nicht in Microsoft-Empfehlungen enthalten sind.
    - **Geplante** Aktion ist für die Implementierung geplant
    - **Nicht im Bereich** – eine Option für Aktionen, die für Ihre Organisation nicht relevant sind; Wenn Sie diesen Status auswählen, wird die Aktion von der Bewertung ausgeschlossen. durch Aufheben der Auswahl wird die Aktion in Scoring eingeschlossen.
- **Implementierungsdatum**: verfügbares Feld, wenn der Implementierungsstatus auf **implementiert** oder **alternative Implementierung**festgelegt ist. Umschalten des Kalender Popups, um das Datum auszuwählen
- **Test Status**: Wählen Sie eine der folgenden Optionen aus:
    - **Nicht bewertet** – Test wurde nicht gestartet
    - **Übergebene**Implementierung erfolgreich getestet
    - **Fehlgeschlagenes niedriges Risiko** – Testfehler, geringes Risiko
    - **Fehler bei mittlerem Risiko** – Testfehler, mittleres Risiko
    - Fehler **hafte hohe Risiko** Tests, hohes Risiko
- **Testdatum**: wechselt durch das Popup Kalenderfenster, um das Datum auszuwählen.

> [!NOTE]
> Die Felder "Implementierung" und "Teststatus" können von jedem Benutzer mit Bearbeitungsberechtigungen bearbeitet werden, nicht nur dem Benutzer **zugewiesen** .

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Zuweisen von Verbesserungs Aktionen zum Abschlussprüfer

Nachdem Sie die Arbeit abgeschlossen und Beweise hochgeladen haben, besteht der nächste Schritt darin, den Implementierungsstatus und das Datum festzulegen und die Verbesserungs Aktion einem Gutachter zur Validierung zuzuweisen.

Zu den Typen von Gutachtern gehören:

- Interne Prüfer, die die Validierung von Steuerelementen in Ihrer Organisation durchführen
- Externe Prüfer, die die Konformität prüfen, überprüfen und zertifizieren, beispielsweise unabhängige Drittanbieter Organisationen, die Microsoft Cloud-Dienste überwachen

Der Assessor überprüft die Arbeit und untersucht die Dokumentation und wählt den entsprechenden Teststatus aus.

**Wenn der Teststatus "übergeben" lautet**: die Aktion ist abgeschlossen, und die **erreichten Punkte** zeigen die gesamte Anzahl der möglichen Punkte, die erreicht wurden und in Bezug auf ihr allgemeines Konformitäts Ergebnis gezählt wurden.

**Wenn der Teststatus einen beliebigen Grad an "fehlgeschlagen" lautet**: die Aktion erfüllt die Anforderungen nicht, und der Assessor kann Sie dem entsprechenden Benutzer für zusätzliche Arbeit zurückzuweisen.

## <a name="solutions-page"></a>Seite "Lösungen"

Die **Seite Lösungen** ist ein weiterer Ausgangspunkt für die Arbeit an Verbesserungs Aktionen, um Ihre Punktzahl zu verbessern. 

Um zur Seite Lösungen zu gelangen, wählen Sie die Registerkarte **Lösungen** in Ihrem Dashboard aus, oder wählen Sie **alle Lösungen** unterhalb von **Lösungen anzeigen, die Ihre Punktzahl** im oberen rechten Bereich des Dashboards betreffen.

Auf der Seite Lösungen wird der Anteil der gesammelten und potenziellen Punkte wie in der Lösung organisiert dargestellt. Das Anzeigen der verbleibenden Punkte und Verbesserungs Aktionen in dieser Ansicht hilft Ihnen zu verstehen, welche Lösungen mehr sofortige Aufmerksamkeit benötigen.

### <a name="filtering-your-solutions-view"></a>Filtern der Lösungs Ansicht

So filtern Sie die Ansicht von Lösungen:

1. Wählen Sie in der oberen linken Ecke der Liste Bewertungen die Option **Filter** aus.
2. Platzieren Sie im **Bereich** flyoutfilter eine Überprüfung neben den gewünschten Kriterien (Normen und Verordnungen, Lösung, Aktionstyp, Compliance-Manager-Gruppe, Kategorie).
3. Klicken Sie auf die Schaltfläche über **nehmen** . Der Filterbereich wird geschlossen, und die gefilterte Ansicht wird angezeigt.

Sie können Ihre Ansicht auch so ändern, dass Bewertungen nach Gruppe, Produkt oder Regulierung angezeigt werden, indem Sie den Typ der Gruppierung aus dem Dropdownmenü **Gruppieren** oberhalb Ihrer Bewertungsliste auswählen.

### <a name="taking-actions-from-the-solutions-page"></a>Erstellen von Aktionen auf der Seite "Lösungen"

Auf der Seite Lösungen werden die Lösungen Ihrer Organisation angezeigt, die mit Verbesserungs Aktionen verbunden sind. In der Tabelle sind die Beiträge der einzelnen Lösungen zu ihrer Gesamtpunktzahl, die erzielten Punkte Verbesserungen und mögliche Ergebnisse in dieser Lösung sowie die verbleibende Anzahl von Verbesserungs Aktionen, die in dieser Lösung gruppiert sind, aufgeführt, die Ihre Punktzahl erhöhen können.

Es gibt zwei Möglichkeiten, auf diesem Bildschirm Maßnahmen zu ergreifen:

1. Wählen Sie in der Zeile der gewünschten Lösung unter der Spalte **verbleibende Aktionen** die mit Hyperlinks verlinkte Nummer aus. Auf dem Bildschirm Verbesserungs Aktionen wird eine gefilterte Ansicht angezeigt, in der nicht getestete Verbesserungs Aktionen für diese Lösung angezeigt werden.

2. Wählen Sie in der Zeile der gewünschten Lösung unter der Spalte **Open Solution** die Option **Öffnen**aus. Sie sehen die Lösung oder den Standort im Sicherheits-und Compliance Center von Microsoft 365 und Office 365, in der Sie die empfohlene Aktion durchführen können.

## <a name="assessments-page"></a>Seite "Bewertungen"

Auf der Seite "Bewertungen" werden die Bewertungen aufgeführt, die Sie für die Nachverfolgung Ihrer Organisation ausgewählt haben. Der Nenner der Konformitätsbewertung wird durch alle nachverfolgten Bewertungen bestimmt. Je mehr Bewertungen Sie hinzufügen, desto mehr Verbesserungs Aktionen sehen Sie auf der Seite Verbesserungs Aktionen und desto höher ist Ihr Ergebnis Nenner.

Um zur Seite "Bewertungen" zu gelangen, wählen Sie die Registerkarte " **Assessments** " in Ihrem Dashboard aus.

Auf dieser Seite können Sie schnell wichtige Informationen zu den einzelnen Bewertungen anzeigen:

- **Status**: der Status bis zum Abschluss aller Verbesserungs Aktionen in der Bewertung wird entweder als aufgelistet:
    - **Nicht konform**: die Verbesserungs Aktionen in der Bewertung wurden nicht implementiert und erfolgreich getestet. die Arbeit wurde noch nicht begonnen.
    - **In Bearbeitung**: Es sind Arbeiten zur Implementierung oder zum Testen der Verbesserungs Aktionen im Gange; beispielsweise wurde eine Verbesserungs Aktion in der Bewertung für Arbeit zugewiesen, wird derzeit implementiert und getestet.
- **Bewertungs Fortschritt**: der Prozentsatz der Arbeit, der für die abschließende Fertigstellung der Bewertung geleistet wurde, gemessen an der Anzahl der erfolgreich getesteten Steuerelemente.
- Von **Kunden verwaltete Aktionen**: die Anzahl der abgeschlossenen Aktionen zur Erfüllung der Implementierung ihrer vom Kunden verwalteten Steuerelemente
- Von **Microsoft verwaltete Aktionen**: die Anzahl der abgeschlossenen Aktionen zur Erfüllung der Implementierung von von Microsoft verwalteten Steuerelementen
- **Assessment Group**: Name der Gruppe, die Sie erstellt haben, in der sich die Bewertung befindet
- **Verwandte Dienste**: zugeordneter Microsoft 365-Dienst
- **Verwandte Bestimmungen**: der gesetzliche Standard, die Richtlinie oder das Recht, das die Bewertung erfüllen soll

### <a name="default-assessments"></a>Standardbewertungen

Standardmäßig wird die Microsoft 365-Datenschutz-Basisbewertung auf der Seite "Bewertungen" angezeigt. Compliance Score bietet auch mehrere vorkonfigurierte Bewertungen ([vollständige Liste anzeigen](compliance-score.md#templates)). Sie können weitere Bewertungen hinzufügen, um zusätzliche Vorschriften und Standards im Compliance-Manager abzudecken.

### <a name="managing-assessments"></a>Verwalten von Bewertungen

Während der öffentlichen Vorschau gelangen Sie zum Compliance-Manager-Tool, um Ihre Bewertungen zu verschachteln, anzupassen und zu verwalten.

Wählen Sie auf der Seite " **Bewertungen** " unter Konformitätsbewertung in **Compliance-Manager** die Option "Bewertungen verwalten" oben in der Liste "Bewertungen" aus. Über diesen Link gelangen Sie zu Ihrem **Assessments** -Dashboard im Compliance-Manager.

Der andere Link oben in der Liste "Assessments", **Microsoft-Aktionen im Compliance-Manager**, führt Sie zum **Steuerelement-Info** -Dashboard im Compliance-Manager, der Microsoft-Steuerelemente anzeigt, die zur Konformitätsbewertung beitragen.

### <a name="filtering-your-assessments-view"></a>Filtern der Ansicht "Bewertungen"

So filtern Sie die Ansicht von Bewertungen:

1. Wählen Sie in der oberen linken Ecke der Liste Bewertungen die Option **Filter** aus.
2. Platzieren Sie im **Bereich** flyoutfilter eine Überprüfung neben den gewünschten Kriterien (Normen und Verordnungen, Compliance-Manager-Gruppe).
3. Klicken Sie auf die Schaltfläche über **nehmen** . Der Filterbereich wird geschlossen, und die gefilterte Ansicht wird angezeigt.

Sie können Ihre Ansicht auch so ändern, dass Bewertungen nach Gruppe, Produkt oder Regulierung angezeigt werden, indem Sie den Typ der Gruppierung aus dem Dropdownmenü **Gruppieren** oberhalb Ihrer Bewertungsliste auswählen.

### <a name="managing-improvement-actions-within-an-assessment"></a>Verwalten von Verbesserungs Aktionen innerhalb eines Assessments

Wählen Sie in der Liste Bewertung in der Spalte **Kunden verwaltete Aktionen** den verknüpften Text in der Zeile der beabsichtigten Bewertung aus. Dadurch wird eine gefilterte Ansicht der Seite Verbesserungs Aktionen angezeigt, die die Aktionen innerhalb dieser Bewertung anzeigt.

## <a name="reporting"></a>Reporting

Sie können einen Bericht über alle Ihre Verbesserungs Aktionen in der Kompatibilitätsbewertung exportieren. Wählen Sie auf der Seite **Verbesserungs Aktionen** in der oberen linken Ecke des Bildschirms oberhalb der Liste der Aktionen die Option **exportieren** aus. Dadurch wird ein Excel-Arbeitsblatt mit allen ihren Verbesserungs Aktionen und den Filterkategorien erstellt, die auf der Seite **Verbesserungs Aktionen** angezeigt werden.

Sie können einen Bericht auch aus dem Compliance-Manager exportieren, indem Sie die folgenden Schritte ausführen:

1. Navigieren Sie im Compliance-Manager zu Ihrem **Steuerelement-Info** -Dashboard.
2. Es wird eine Registerkarte " **Bewertung** " und eine Registerkarte " **Vorlage** " angezeigt.  
3. So exportieren Sie eine Bewertung: Wählen Sie die Registerkarte **Bewertung** aus. verwenden Sie die Dropdownmenüs **Gruppieren** und **bewerten** , um die Bewertung auszuwählen, die Sie exportieren möchten. Wählen Sie in der oberen rechten Ecke des Bildschirms **exportieren** aus. Eine Excel-Datei wird heruntergeladen. Es enthält eine Liste von Aktionen, gruppiert nach Steuerelement, mit ihrer Implementierung und Testdetails.
4. So exportieren Sie eine Vorlage: Wählen Sie die Registerkarte **Vorlage** aus, und wählen Sie im Dropdownmenü **Vorlage** die Vorlage aus, die Sie exportieren möchten. Wählen Sie in der oberen rechten Ecke des Bildschirms **exportieren** aus. Eine Excel-Datei wird heruntergeladen. Es enthält eine Liste von Aktionen, gruppiert nach Steuerelement, mit ihrer Implementierung und Testdetails.
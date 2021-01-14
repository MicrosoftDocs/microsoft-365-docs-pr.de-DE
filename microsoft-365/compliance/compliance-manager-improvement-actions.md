---
title: Zuweisen und Abschließen von Verbesserungsmaßnahmen im Microsoft Compliance Manager
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
description: Erfahren Sie, wie Sie Die Implementierung und das Testen von Steuerelementen im Microsoft Compliance Manager durchführen. Weisen Sie Arbeits-, Speicherdokumentations- und Exportberichte zu.
ms.openlocfilehash: c465a574ed9c1a8ad8ef9e2bfc7f864545ae28d9
ms.sourcegitcommit: 00d231bf0100e843a5a93161695e87ceff9e1349
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49849592"
---
# <a name="assign-and-complete-improvement-actions-in-compliance-manager"></a>Zuweisen und Abschließen von Verbesserungsmaßnahmen im Compliance-Manager

**In diesem Artikel:** In diesem Artikel wird erläutert, wie **Sie Ihren Complianceworkflow mit** Verbesserungsmaßnahmen verwalten. Erfahren Sie, **wie Sie Verbesserungsmaßnahmen** für Implementierung und Tests zuweisen, **Updates verwalten** und Berichte **exportieren.**

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Verwalten von Complianceworkflows mit Verbesserungsmaßnahmen

Verbesserungsmaßnahmen zentralisieren Ihre Complianceaktivitäten. Jede Verbesserungsaktion bietet detaillierte Implementierungsanleitungen, die Ihnen dabei helfen, sich an den Datenschutzbestimmungen und -standards auszurichten. Benutzern in Ihrer Organisation können Aktionen zugewiesen werden, um Implementierungs- und Testarbeiten durchzuführen. Sie können auch Dokumentationen, Notizen und Statusaktualisierungen innerhalb der Aktion speichern.

Alle Verbesserungsmaßnahmen werden auf der Seite mit den Verbesserungsmaßnahmen aufgeführt. Erfahren Sie mehr [über das Anzeigen Ihrer Verbesserungsmaßnahmen.](compliance-manager-setup.md#improvement-actions-page)

## <a name="improvement-actions-details-page"></a>Detailseite zu Verbesserungsmaßnahmen

Jede Verbesserungsaktion verfügt über eine Detailseite, auf der der aktuelle Status, die zugehörigen Standards und behördlichen Anforderungen sowie empfohlene Implementierungsleitfäden angezeigt werden. [Zu den technischen](compliance-score-calculation.md#technical-and-non-technical-actions) Aktionen gehört **ein Link** "Jetzt starten", über den Sie zur entsprechenden Lösung für die Implementierung kommen. Sie können die Implementierungs- und Testdokumentation direkt auf der Detailseite einer Verbesserungsaktion anfügen.

So zeigen Sie die Detailseite einer Verbesserungsaktion an:

1. Wechseln Sie zur Seite "Verbesserungsmaßnahmen".
2. Wählen Sie die Zeile der beabsichtigten Verbesserungsaktion aus, die die Detailseite öffnet.

Sie können ganz einfach die nächste oder vorherige Verbesserungsaktion in der Liste anzeigen, indem Sie den Pfeil nach oben oder unten in der oberen rechten Ecke des Bildschirms auswählen. Wenn Sie Ihre Liste auf der Seite mit verbesserungsaktionen gefiltert haben, gelangen Sie beim Nach-oben- oder Abwärtswechsel zum nächsten Element in dieser gefilterten Liste.

## <a name="assign-improvement-actions"></a>Zuweisen von Verbesserungsmaßnahmen

Um mit der Implementierung einer Verbesserungsaktion zu beginnen, können Sie die Arbeit selbst oder einem anderen Benutzer zuweisen. Die zugewiesene Person könnte:

- Der Besitzer einer Unternehmensrichtlinie
- Ein IT-Implementierer
- Ein anderer Mitarbeiter, der für die Ausführung der Aufgabe verantwortlich ist

Sobald Sie den entsprechenden Zugewiesenen identifiziert haben, stellen Sie sicher, dass er über eine ausreichende [Compliance-Manager-Rolle](compliance-manager-setup.md#set-user-permissions-and-assign-roles) zum Ausführen der Arbeit verkn nnen. Führen Sie dann die folgenden Schritte aus, um die Verbesserungsaktion zuzuordnen:

1. Wählen Sie auf der Detailseite für Verbesserungsmaßnahmen den Status **"Bearbeiten"** im linken oberen Bereich des Bildschirms aus.

2. Wählen Sie im Flyoutbereich "Status bearbeiten" das Feld "Zugewiesen **zu"** aus, um eine Liste vorgeschlagener **Personen** mit Benutzern anzuzeigen. Sie können den Benutzer aus der Liste auswählen oder die E-Mail-Adresse der Person eingeben, der Sie ihn zuweisen möchten.

3. Wählen Sie **"Speichern" und "Schließen" aus.** Der zugewiesene Benutzer erhält eine E-Mail mit der Erläuterung, dass ihm die Verbesserungsaktion zugewiesen wurde, mit einem direkten Link zur Verbesserungsaktion. (Hinweis: Hohe Kunden der US Government Community (GCC) erhalten keine E-Mail, wenn ihnen Aktionen zugewiesen werden.)

Der zugewiesene Benutzer kann dann die empfohlenen Aktionen ausführen.

#### <a name="assign-multiple-improvement-actions-to-a-single-user"></a>Zuweisen mehrerer Verbesserungsmaßnahmen zu einem einzelnen Benutzer

Sie können einem Benutzer mehrere Verbesserungsmaßnahmen zuweisen, indem Sie die folgenden Schritte ausführen:

1. Wechseln Sie zur Seite "Verbesserungsmaßnahmen".
2. Wählen Sie den Bereich links vom Namen der Verbesserungsaktion aus. Ein Roundchecksymbol wird angezeigt, das angibt, dass Sie diese Aktion ausgewählt haben. Überprüfen Sie alle Aktionen, die Sie zuweisen möchten.
3. Wählen Sie **oben in der** Tabelle mit den Verbesserungsmaßnahmen den Link "Benutzer zuweisen" aus.
4. Ein Popupfenster wird geöffnet. Beginnen Sie im Feld "Zuweisen **zu"** mit der Eingabe des Namens der Person, der Sie die Aktionen zuweisen möchten. Sie können auch aus der Liste der vorgeschlagenen Personen auswählen.
5. Nachdem Sie das Feld "Zuweisen **zu"** mit dem Namen des Zugewiesenen auffüllen, wählen Sie **"Zuweisen" aus.**
6. Dann wird die Seite mit verbesserungsaktionen mit dem neuen Zugewiesenen für die Aktionen angezeigt, die Sie gerade zugewiesen haben.

## <a name="perform-work-and-store-documentation"></a>Ausführen von Arbeits- und Speicherdokumentation

Sie können Dateien und Notizen im Zusammenhang mit Implementierungs- und Testarbeiten direkt in den Abschnitt **"Hinweise und Dokumentation"** hochladen. Diese Umgebung ist ein sicheres, zentralisiertes Repository, das Ihnen dabei hilft, die Zufriedenheit der Steuerelemente zur Einhaltung von Compliancestandards und -vorschriften zu demonstrieren. Jeder Benutzer mit schreibgeschützten Zugriff kann Inhalte in diesem Abschnitt lesen. Nur Benutzer mit Bearbeitungsrechten können Dateien hochladen und herunterladen sowie Notizen eingeben oder bearbeiten.

Der **Abschnitt "Hinweise und Dokumentation"** enthält Felder für hochgeladene Dokumente, Implementierungshinweise, Testhinweise und zusätzliche Hinweise.

#### <a name="uploaded-documents"></a>Hochgeladene Dokumente

- Wählen **Sie "Dokumente verwalten"** aus, um relevante Dateien hochzuladen.
- Wenn der Flyoutbereich "Dokumente verwalten" geöffnet wird, wählen Sie "Dokument **hinzufügen"** aus, und wählen Sie dann Ihre Datei aus Ihrem System aus. Akzeptierte Dateitypen:
    - Dokumente (DOC, XLS, PPT, TXT, PDF)
    - Bilder (.jpg, .png)
    - Video (.mkv)
    - Komprimierte Dateien (ZIP, RAR)
- Sobald die Datei im Bereich aufgelöst wird, wählen **Sie "Schließen"** aus, wodurch die Dateianlage automatisch gespeichert wird. Dann wird die Datei unter hochgeladenen **Dokumenten aufgeführt.**
- Um das Dokument herunterzuladen oder zu löschen, **wählen** Sie unter der Liste der Dokumente die Option "Dokumente verwalten" aus. Wählen Sie im Flyoutbereich die Dokumentzeile aus, um sie zu markieren, und wählen Sie dann **Herunterladen** oder **Löschen aus.**

#### <a name="implementation-notes-test-notes-and-additional-notes"></a>Implementierungshinweise, Testhinweise und zusätzliche Hinweise

- Wenn Sie Notizen in einem dieser drei Felder hinzufügen möchten, wählen Sie **unter** einem dieser Felder die Option "Implementierungshinweise bearbeiten" aus.
- Wenn der Flyoutbereich geöffnet wird, geben Sie Notizen in das Textfeld ein, und wählen Sie dann **Speichern und Schließen aus.**
- Um Notizen zu bearbeiten, wählen **Sie "Implementierungsnotizen bearbeiten" aus,** nehmen Sie Ihre Änderungen vor, und wählen Sie dann **"Speichern" und "Schließen" aus.**

In den Notizenfeldern gibt es keine Zeichenbeschränkung. Es wird empfohlen, Notizen kurz zu halten, damit Sie sie auf der Detailseite zu Verbesserungsmaßnahmen einfach anzeigen und bearbeiten können.

## <a name="change-improvement-action-status"></a>Ändern des Verbesserungsaktionsstatus

Sie können den Implementierungsstatus und das Datum sowie den Teststatus und das Datum für jede Verbesserungsaktion aufzeichnen. Die **Implementierungs-** **und Teststatusfelder** können von jedem Benutzer mit Bearbeitungsberechtigungen bearbeitet werden, nicht nur von der zugewiesenen Person.

Um den Status einer Verbesserungsaktion zu bearbeiten, wählen Sie im oberen linken Abschnitt der Detailseite den Status "Bearbeiten" aus.  Unten sind die verfügbaren Felder und Statusoptionen aufgeführt:

- **Implementierungsstatus**
    - **Nicht implementiert** – Aktion noch nicht implementiert
    - **Implementiert** – Implementierte Aktion
    - **Alternative Implementierung** – Wählen Sie diese Option aus, wenn Sie andere Drittanbietertools verwendet oder andere Aktionen ergreifen, die nicht in den Empfehlungen von Microsoft enthalten sind.
    - **Geplant** – Die Aktion ist für die Implementierung geplant
    - **Nicht relevant** – Aktion ist für Ihre Organisation nicht relevant und trägt nicht zu Ihrer Bewertung bei.
- **Implementierungsdatum:** verfügbar, um auszuwählen, wann der Implementierungsstatus "implementiert" oder "alternative Implementierung" ist
- **Teststatus:** Verfügbar, um auszuwählen, wann der Implementierungsstatus "implementiert" oder "alternative Implementierung" ist:
    - **Nicht bewertet** – Aktion wurde nicht getestet
    - **Übergeben** – Implementierung wurde von einem Gutachter überprüft
    - **Fehlgeschlagenes niedriges Risiko** – Test fehlgeschlagen, niedriges Risiko
    - **Mittleres Risiko fehlgeschlagen** – Test fehlgeschlagen, mittleres Risiko
    - **Fehlgeschlagenes hohes Risiko** – Test fehlgeschlagen, hohes Risiko
    - **Nicht im Bereich –** die Aktion liegt nicht im Bereich der Bewertung und trägt nicht zu Ihrer Bewertung bei.
- **Testdatum:** Umschalten durch das Kalenderpop-up, um das Datum auszuwählen

Allgemeine Aktionen werden gruppenübergreifend synchronisiert. Wenn zwei verschiedene Bewertungen in derselben Gruppe Verbesserungsmaßnahmen gemeinsam nutzen, die Von Ihnen verwaltet werden, werden alle Aktualisierungen, die Sie an den Implementierungsdetails oder dem Status einer Aktion vornehmen, automatisch mit derselben Aktion in jeder anderen Bewertung in der Gruppe synchronisiert. Mit dieser Synchronisierung können Sie eine Verbesserungsaktion implementieren und mehrere Anforderungen in mehreren Vorschriften erfüllen.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Zuweisen von Verbesserungsmaßnahmen zum Abschluss an den Gutachter

Nachdem Sie die Arbeit abgeschlossen, Tests durchgeführt und Nachweise hochgeladen haben, besteht der nächste Schritt im Zuweisen der Verbesserungsaktion zu einem Gutachter zur Überprüfung. Der Prüfer überprüft die Arbeit, untersucht die Dokumentation und wählt den entsprechenden Teststatus aus.

**Wenn der Teststatus auf "Übergeben" festgelegt** ist: Die Aktion ist abgeschlossen, und die erreichten Punkte zeigen die maximal erreichten Punkte an. Die Punkte werden dann auf Ihre Gesamt-Compliance-Bewertung angerechnet.

**Wenn der Teststatus auf "Fehlgeschlagen"** festgelegt ist: Die Aktion erfüllt nicht die Anforderungen, und der Gutachter kann sie dem entsprechenden Benutzer zuweisen, um zusätzliche Arbeit zu erhalten.

## <a name="accepting-updates-to-improvement-actions"></a>Akzeptieren von Updates für Verbesserungsmaßnahmen

Wenn ein Update für eine Verbesserungsaktion verfügbar ist, wird neben dem Namen eine Benachrichtigung angezeigt. Sie können das Update entweder akzeptieren oder für einen späteren Zeitpunkt zurückdebeben.

#### <a name="what-causes-an-update"></a>Ursachen eines Updates

Eine Aktualisierung erfolgt, wenn Änderungen im Zusammenhang mit Bewertung, Automatisierung oder Bereich vorgenommen werden. Änderungen können neue Anleitungen für Verbesserungsmaßnahmen basierend auf gesetzlichen Änderungen oder aufgrund von Produktänderungen beinhalten. Nur die von Ihren Organisationen verwalteten Verbesserungsmaßnahmen erhalten Updatebenachrichtigungen.

#### <a name="where-youll-see-assessment-update-notifications"></a>Wo Sie Benachrichtigungen über Bewertungsupdates sehen

Wenn eine Verbesserungsaktion aktualisiert wird,  wird neben dem Namen auf der Seite mit den Verbesserungsmaßnahmen und auf der Detailseite der zugehörigen Bewertungen eine Bezeichnung für ausstehende Updates angezeigt.

Wechseln Sie zur Detailseite der Verbesserungsaktion, und wählen Sie im oberen Banner die Schaltfläche "Update überprüfen" aus, um Details zu den Änderungen zu überprüfen und das Update zu akzeptieren oder zurück zu halten. 

#### <a name="review-update-to-accept-or-defer"></a>Überprüfen des Updates, um zu akzeptieren oder zu verzingen

Nachdem Sie **auf der** Seite mit den Details zur Verbesserungsaktion die Option "Update überprüfen" ausgewählt haben, wird auf der rechten Seite des Bildschirms ein Flyoutbereich angezeigt. Der Flyoutbereich enthält wichtige Details zum Update, z. B. die auswirkungen auf die Bewertungen und Änderungen in Punktzahl und Umfang.

Wählen **Sie "Update akzeptieren"** aus, um alle Änderungen an der Verbesserungsaktion zu übernehmen. **Akzeptierte Änderungen sind dauerhaft.**

> [!NOTE]
> Wenn Sie eine Aktualisierung einer Aktion akzeptieren, akzeptieren Sie auch Updates für andere Versionen oder Instanzen dieser Aktion. Updates werden mandantenweit für technische Aktionen und gruppenweit für nicht technische Aktionen veröffentlicht.

Wenn Sie **"Abbrechen"** auswählen, wird das Update nicht auf die Verbesserungsaktion angewendet. Es wird jedoch weiterhin die **Benachrichtigung** über ausstehende Updates angezeigt, bis Sie das Update akzeptieren.

**Warum wir empfehlen, Updates zu akzeptieren**

Durch das Akzeptieren von Updates können Sie sicherstellen, dass Sie über die neuesten Anleitungen zur Verwendung von Lösungen verfügen und geeignete Verbesserungsmaßnahmen ergreifen, um die Anforderungen der zertifizierung zu erfüllen.

**Gründe für die Verschiebung eines Updates**

Wenn Sie gerade eine Bewertung abschließen, die die Verbesserungsaktion enthält, sollten Sie sicherstellen, dass Sie die Arbeit daran abgeschlossen haben, bevor Sie das Update akzeptieren. Sie können das Update zu einem späteren Zeitpunkt zurückdrücken, indem Sie **im** Flyoutbereich "Überprüfungsupdate" die Option Abbrechen auswählen.

#### <a name="accept-all-updates-at-once"></a>Alle Updates auf einmal akzeptieren

Wenn Sie über mehrere Updates verfügen und alle gleichzeitig  akzeptieren möchten, wählen Sie oben in der Tabelle mit den Verbesserungsmaßnahmen den Link "Alle Updates akzeptieren" aus. Es wird ein Flyoutbereich mit der Anzahl der zu aktualisierende Aktionen angezeigt. Wählen Sie die Schaltfläche **"Updates akzeptieren"** aus, um alle Updates anzuwenden.

Beachten Sie, dass bei der Rückkehr zur Seite mit Verbesserungsmaßnahmen am oberen Rand der Seite möglicherweise eine Meldung angezeigt wird, in der Sie aufgefordert werden, die Seite zu aktualisieren, damit die Updates abgeschlossen werden.

## <a name="export-a-report"></a>Exportieren eines Berichts

Wählen **Sie "Exportieren"** in der oberen linken Ecke des Bildschirms aus, um ein Excel-Arbeitsblatt herunterzuladen, das alle Verbesserungsmaßnahmen und filterkategorien enthält, die auf der Seite "Verbesserungsmaßnahmen" angezeigt werden.
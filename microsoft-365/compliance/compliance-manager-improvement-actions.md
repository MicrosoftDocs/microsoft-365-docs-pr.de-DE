---
title: Zuweisen und Abschließen von Verbesserungsmaßnahmen im Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie die Implementierung und das Testen von Steuerelementen im Microsoft Compliance Manager durchführen. Zuweisen von Arbeits-, Speicherdokumentations- und Exportberichten.
ms.openlocfilehash: f2674e24ed38362c5c7563a574e0dba9c81f2584
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149034"
---
# <a name="assign-and-complete-improvement-actions-in-compliance-manager"></a>Zuweisen und Abschließen von Verbesserungsmaßnahmen im Compliance-Manager

**In diesem Artikel:** In diesem Artikel wird erläutert, wie **Sie Ihren Compliance-Workflow** mit Verbesserungsmaßnahmen verwalten. Erfahren Sie, wie Sie **Verbesserungsmaßnahmen** für Implementierung und Tests zuweisen, **Updates verwalten** und **Berichte** exportieren.

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Verwalten von Complianceworkflows mit Verbesserungsmaßnahmen

Verbesserungsmaßnahmen zentralisieren Ihre Complianceaktivitäten. Jede Verbesserungsmaßnahme bietet detaillierte Implementierungsleitlinien, die Ihnen dabei helfen, sich an Datenschutzbestimmungen und -standards zu orientieren. Aktionen können Benutzern in Ihrer Organisation zugewiesen werden, um Implementierungs- und Testarbeiten durchzuführen. Sie können auch Dokumentationen, Notizen und Statusaktualisierungen innerhalb der Aktion speichern.

Alle Ihre Verbesserungsmaßnahmen sind auf der Seite "Verbesserungsmaßnahmen" aufgeführt. Erfahren Sie mehr über [das Anzeigen Ihrer Verbesserungsmaßnahmen.](compliance-manager-setup.md#improvement-actions-page)

## <a name="improvement-actions-details-page"></a>Detailseite zu Verbesserungsmaßnahmen

Jede Verbesserungsmaßnahme enthält eine Detailseite mit dem aktuellen Status, den zugehörigen Standards und behördlichen Anforderungen sowie den empfohlenen Implementierungsleitlinien. [Zu den technischen Aktionen](compliance-score-calculation.md#technical-and-non-technical-actions) gehört ein Link **"Jetzt starten",** der Sie zur entsprechenden Lösung für die Implementierung führt. Sie können die Implementierungs- und Testdokumentation direkt an die Detailseite einer Verbesserungsmaßnahme anfügen.

So zeigen Sie die Detailseite einer Verbesserungsmaßnahme an:

1. Wechseln Sie zur Seite "Verbesserungsmaßnahmen".
2. Wählen Sie die Zeile der beabsichtigten Verbesserungsmaßnahme aus, die die Detailseite öffnet.

Sie können die nächste oder vorherige Verbesserungsmaßnahme in der Liste ganz einfach anzeigen, indem Sie den Pfeil nach oben oder unten in der oberen rechten Ecke des Bildschirms auswählen. Wenn Sie Ihre Liste auf der Seite "Verbesserungsmaßnahmen" gefiltert haben, gelangen Sie nach oben oder unten zum nächsten Element in dieser gefilterten Liste.

## <a name="assign-improvement-actions"></a>Zuweisen von Verbesserungsmaßnahmen

Um mit der Implementierung einer Verbesserungsmaßnahme zu beginnen, können Sie die Arbeit selbst ausführen oder einem anderen Benutzer zuweisen. Die zugewiesene Person kann folgendermaßen sein:

- Der Besitzer einer Unternehmensrichtlinie
- Ein IT-Implementierer
- Ein anderer Mitarbeiter, der für die Ausführung der Aufgabe verantwortlich ist

Nachdem Sie den entsprechenden Zugewiesenen identifiziert haben, stellen Sie sicher, dass er über eine ausreichende [Compliance-Manager-Rolle](compliance-manager-setup.md#set-user-permissions-and-assign-roles) verfügt, um die Arbeit auszuführen. Führen Sie dann die folgenden Schritte aus, um die Verbesserungsmaßnahmen zuzuweisen:

1. Wählen Sie auf der Detailseite für Verbesserungsmaßnahmen den **Status "Bearbeiten"** im oberen linken Bereich des Bildschirms aus.

2. Wählen Sie im Flyoutbereich "Bearbeitungsstatus" das Feld **"Zugewiesen an"** aus, um eine Liste der **vorgeschlagenen Personen** von Benutzern anzuzeigen. Sie können den Benutzer aus der Liste auswählen oder die E-Mail-Adresse der Person eingeben, der Sie ihn zuweisen möchten.

3. Wählen Sie **Speichern und schließen** aus. Der zugewiesene Benutzer erhält eine E-Mail, in der erläutert wird, dass ihm die Verbesserungsmaßnahme zugewiesen wurde, mit einem direkten Link zu der Verbesserungsmaßnahme. 
> [!NOTE]
> Us Government Community (GCC) High and Department of Defense (DoD) customers won't receive an email when improvement actions are assigned to them.

Der zugewiesene Benutzer kann dann die empfohlenen Aktionen ausführen.

#### <a name="assign-multiple-improvement-actions-to-a-single-user"></a>Zuweisen mehrerer Verbesserungsmaßnahmen zu einem einzelnen Benutzer

Sie können einem Benutzer mehrere Verbesserungsmaßnahmen zuweisen, indem Sie die folgenden Schritte ausführen:

1. Wechseln Sie zur Seite "Verbesserungsmaßnahmen".
2. Wählen Sie den Bereich links neben dem Namen der Verbesserungsmaßnahme aus. Ein Roundchecksymbol wird angezeigt, das angibt, dass Sie diese Aktion ausgewählt haben. Überprüfen Sie alle Aktionen, die Sie zuweisen möchten.
3. Wählen Sie oben in der Tabelle "Verbesserungsmaßnahmen" den Link "Benutzer **zuweisen"** aus.
4. Ein Popupfenster wird geöffnet. Beginnen Sie im Feld **"Zuweisen"** mit der Eingabe des Namens der Person, der Sie die Aktionen zuweisen möchten. Sie können auch aus der Liste der vorgeschlagenen Personen auswählen.
5. Nachdem Sie das Feld **Assign** to mit dem Namen des Zugewiesenen aufgefüllt haben, wählen Sie **Zuweisen aus.**
6. Dann wird die Seite "Verbesserungsmaßnahmen" angezeigt, auf der der neue Zugewiesene für die soeben zugewiesenen Aktionen aufgelistet ist.

## <a name="perform-work-and-store-documentation"></a>Durchführen von Arbeits- und Speicherdokumentation

Sie können Dateien und Notizen im Zusammenhang mit Implementierungs- und Testarbeiten direkt in den Abschnitt **"Hinweise und Dokumentation"** hochladen. Diese Umgebung ist ein sicheres, zentralisiertes Repository, das Ihnen hilft, die Zufriedenheit der Kontrollen zur Einhaltung von Compliancestandards und -vorschriften zu demonstrieren. Jeder Benutzer mit schreibgeschütztem Zugriff kann Inhalte in diesem Abschnitt lesen. Nur Benutzer mit Bearbeitungsrechten können Dateien hochladen und herunterladen und Notizen eingeben oder bearbeiten.

Der Abschnitt **"Hinweise und Dokumentation"** enthält Felder für hochgeladene Dokumente, Implementierungshinweise, Testnotizen und zusätzliche Hinweise.

#### <a name="uploaded-documents"></a>Hochgeladene Dokumente

- Wählen Sie **"Dokumente verwalten"** aus, um alle relevanten Dateien hochzuladen.
- Wenn der Flyoutbereich "Dokumente verwalten" geöffnet wird, wählen Sie **"Dokument hinzufügen"** und dann Ihre Datei im System aus. Akzeptierte Dateitypen:
    - Dokumente (.doc, .xls, .ppt, .txt, .pdf)
    - Bilder (.jpg, .png)
    - Video (MKV)
    - Komprimierte Dateien (.zip, .rar)
- Sobald ihre Datei im Bereich aufgelöst wird, wählen Sie **"Schließen"** aus, wodurch die Dateianlage automatisch gespeichert wird. Die Datei wird dann unter den **hochgeladenen Dokumenten** aufgeführt.
- Um das Dokument herunterzuladen oder zu löschen, wählen Sie **"Dokumente verwalten"** unterhalb der Liste der Dokumente aus. Wählen Sie im Flyoutbereich die Dokumentzeile aus, um sie hervorzuheben, und wählen Sie dann **Herunterladen** oder **Löschen** aus.

#### <a name="implementation-notes-test-notes-and-additional-notes"></a>Implementierungshinweise, Testnotizen und zusätzliche Hinweise

- Um Notizen in einem dieser drei Felder hinzuzufügen, wählen Sie **Implementierungsnotizen** unter einem dieser Felder bearbeiten aus.
- Wenn der Flyoutbereich geöffnet wird, geben Sie Notizen in das Textfeld ein, und wählen Sie dann **Speichern und schließen** aus.
- Um Notizen zu bearbeiten, wählen Sie **Implementierungsnotizen bearbeiten** aus, nehmen Sie Ihre Änderungen vor, und wählen Sie dann **Speichern und schließen** aus.

Es gibt keine Zeichenbegrenzung in den Notizenfeldern. Es wird empfohlen, die Notizen kurz zu halten, damit Sie sie auf der Detailseite für Verbesserungsmaßnahmen auf einfache Weise anzeigen und bearbeiten können.

## <a name="change-improvement-action-status"></a>Status der Änderungsverbesserungsmaßnahme

Sie können den Implementierungsstatus und das Datum sowie den Teststatus und das Datum für jede Verbesserungsmaßnahme aufzeichnen. Die **Implementierungs-** und **Teststatusfelder** können von jedem Benutzer mit Bearbeitungsberechtigungen bearbeitet werden, nicht nur von der zugewiesenen Person.

Um den Status einer Verbesserungsmaßnahme zu bearbeiten, wählen Sie im linken oberen Abschnitt der Detailseite den **Status "Bearbeiten"** aus. Nachfolgend sind die verfügbaren Felder und Statusoptionen aufgeführt:

- **Implementierungsstatus**
    - **Nicht implementiert** – Aktion noch nicht implementiert
    - **Implementiert** – implementierte Aktion
    - **Alternative Implementierung** – Wählen Sie diese Option aus, wenn Sie andere Drittanbietertools verwendet oder andere Aktionen ausgeführt haben, die nicht in den Empfehlungen von Microsoft enthalten sind.
    - **Geplant** – Aktion ist für die Implementierung geplant
    - **Außerhalb des Bereichs** – Aktion ist für Ihre Organisation nicht relevant und trägt nicht zu Ihrer Bewertung bei
- **Implementierungsdatum:** kann ausgewählt werden, wenn der Implementierungsstatus "implementiert" oder "alternative Implementierung" ist
- **Teststatus:** kann ausgewählt werden, wenn der Implementierungsstatus "implementiert" oder "alternative Implementierung" ist:
    - **Nicht bewertet** – Aktion wurde nicht getestet
    - **Erfolgreich** – Implementierung wurde von einem Prüfer überprüft
    - **Niedriges Risiko fehlgeschlagen** – Fehler beim Testen, geringes Risiko
    - **Mittleres Risiko fehlgeschlagen** – Fehler beim Testen, mittleres Risiko
    - **Hohes Risiko fehlgeschlagen** – Fehler bei Tests, hohes Risiko
    - **Außerhalb des Bereichs** – die Aktion liegt außerhalb des Bereichs für die Bewertung und trägt nicht zu Ihrer Bewertung bei
- **Testdatum:** Umschalten durch das Kalender-Popup, um das Datum auszuwählen

Allgemeine Aktionen werden gruppenübergreifend synchronisiert. Wenn zwei unterschiedliche Bewertungen in derselben Gruppe Verbesserungsmaßnahmen teilen, die von Ihnen verwaltet werden, werden alle Aktualisierungen, die Sie an den Implementierungsdetails oder dem Status einer Aktion vornehmen, automatisch mit derselben Aktion in jeder anderen Bewertung in der Gruppe synchronisiert. Mit dieser Synchronisierung können Sie eine Verbesserungsmaßnahme implementieren und mehrere Anforderungen über mehrere Vorschriften hinweg erfüllen.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Zuweisen von Verbesserungsmaßnahmen zum Abschluss an den Prüfer

Nachdem Sie die Arbeit abgeschlossen, Tests durchgeführt und Nachweise hochgeladen haben, besteht der nächste Schritt darin, die Verbesserungsmaßnahme einem Prüfer zur Validierung zuzuweisen. Der Prüfer überprüft die Arbeit und überprüft die Dokumentation und wählt den entsprechenden Teststatus aus.

**Wenn der Teststatus auf "Übergeben" festgelegt ist:** Die Aktion ist abgeschlossen, und die erreichten Punkte zeigen die maximal erreichten Punkte an. Die Punkte werden dann auf Ihre Gesamtcompliancebewertung gezählt.

Wenn der **Teststatus auf "Fehlgeschlagen" festgelegt ist:** Die Aktion erfüllt nicht die Anforderungen, und der Prüfer kann ihn dem entsprechenden Benutzer für zusätzliche Arbeit zuweisen.

## <a name="accepting-updates-to-improvement-actions"></a>Akzeptieren von Updates für Verbesserungsmaßnahmen

Wenn ein Update für eine Verbesserungsmaßnahme verfügbar ist, wird neben dem Namen eine Benachrichtigung angezeigt. Sie können das Update entweder akzeptieren oder für einen späteren Zeitpunkt zurückstellen.

#### <a name="what-causes-an-update"></a>Gründe für ein Update

Eine Aktualisierung erfolgt, wenn Es Änderungen im Zusammenhang mit der Bewertung, Automatisierung oder dem Bereich gibt. Änderungen können neue Anleitungen für Verbesserungsmaßnahmen enthalten, die auf regulatorischen Änderungen basieren, oder aufgrund von Produktänderungen. Nur die von Ihren Organisationen verwalteten Verbesserungsmaßnahmen erhalten Updatebenachrichtigungen.

#### <a name="where-youll-see-assessment-update-notifications"></a>Wo Benachrichtigungen zu Bewertungsupdates angezeigt werden

Wenn eine Verbesserungsmaßnahme aktualisiert wird, wird neben dem Namen eine Bezeichnung für **ausstehende Updates** auf der Seite "Verbesserungsmaßnahmen" und auf der Detailseite der zugehörigen Bewertungen angezeigt.

Wechseln Sie zur Detailseite der Verbesserungsmaßnahme, und wählen Sie die Schaltfläche **"Update überprüfen"** im oberen Banner aus, um Details zu den Änderungen zu überprüfen und das Update zu akzeptieren oder zurückstellen.

#### <a name="review-update-to-accept-or-defer"></a>Überprüfen des Updates zum Akzeptieren oder Zurückstellen

Nachdem Sie **"Update überprüfen"** auf der Detailseite für Verbesserungsmaßnahmen ausgewählt haben, wird auf der rechten Seite des Bildschirms ein Flyoutbereich angezeigt. Der Flyoutbereich enthält wichtige Details zum Update, z. B. die betroffenen Bewertungen und Änderungen in Punktzahl und Umfang.

Wählen Sie **"Update annehmen"** aus, um alle Änderungen an der Verbesserungsmaßnahme zu akzeptieren. **Akzeptierte Änderungen sind dauerhaft.**

> [!NOTE]
> Wenn Sie ein Update für eine Aktion akzeptieren, akzeptieren Sie auch Updates für alle anderen Versionen oder Instanzen dieser Aktion. Updates werden mandantenweit für technische Aktionen verteilt und gruppenweit für nicht technische Aktionen verteilt.

Wenn Sie **"Abbrechen"** auswählen, wird die Aktualisierung nicht auf die Verbesserungsmaßnahme angewendet. Die **Benachrichtigung** über ausstehende Updates wird jedoch weiterhin angezeigt, bis Sie das Update akzeptiert haben.

**Warum wir empfehlen, Updates zu akzeptieren**

Durch das Akzeptieren von Updates können Sie sicherstellen, dass Sie über die neuesten Anleitungen zur Verwendung von Lösungen und geeignete Verbesserungsmaßnahmen verfügen, um die Anforderungen der jeweiligen Zertifizierung zu erfüllen.

**Warum Sie ein Update möglicherweise zurückstellen möchten**

Wenn Sie gerade eine Bewertung abschließen, die die Verbesserungsmaßnahme enthält, sollten Sie sicherstellen, dass Sie die Arbeit daran abgeschlossen haben, bevor Sie das Update akzeptieren. Sie können das Update zu einem späteren Zeitpunkt zurückstellen, indem Sie im Flyoutbereich zum Überprüfen des Updates **"Abbrechen"** auswählen.

#### <a name="accept-all-updates-at-once"></a>Alle Updates gleichzeitig akzeptieren

Wenn Sie über mehrere Updates verfügen und alle gleichzeitig akzeptieren möchten, wählen Sie den Link **"Alle Updates akzeptieren"** oben in der Tabelle "Verbesserungsmaßnahmen" aus. Es wird ein Flyoutbereich angezeigt, in dem die Anzahl der zu aktualisierenden Aktionen aufgeführt ist. Wählen Sie die Schaltfläche **"Updates annehmen"** aus, um alle Updates anzuwenden.

Beachten Sie, dass, wenn Sie zu Ihrer Seite für Verbesserungsmaßnahmen zurückkehren, oben auf der Seite möglicherweise eine Meldung angezeigt wird, in der Sie aufgefordert werden, die Seite zu aktualisieren, damit die Updates abgeschlossen werden.

## <a name="export-a-report"></a>Exportieren eines Berichts

Wählen Sie in der oberen linken Ecke des Bildschirms **"Exportieren"** aus, um ein Excel Arbeitsblatt herunterzuladen, das alle Verbesserungsmaßnahmen und die auf der Seite "Verbesserungsmaßnahmen" angezeigten Filterkategorien enthält.
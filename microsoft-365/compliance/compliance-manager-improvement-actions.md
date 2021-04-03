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
description: Erfahren Sie, wie Sie Implementierung und Tests von Steuerelementen im Microsoft Compliance Manager durchführen. Zuweisen von Arbeits-, Speicherdokumentations- und Exportberichten.
ms.openlocfilehash: e761d8d4410f1c52bb79d4a225eec407f1fd6a6e
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570384"
---
# <a name="assign-and-complete-improvement-actions-in-compliance-manager"></a>Zuweisen und Abschließen von Verbesserungsmaßnahmen im Compliance-Manager

**In diesem Artikel:** In diesem Artikel wird erläutert, wie **Sie Ihren Complianceworkflow mit** Verbesserungsmaßnahmen verwalten. Erfahren Sie, **wie Sie Verbesserungsmaßnahmen für** Implementierung und Tests zuweisen, Updates **verwalten** und Berichte **exportieren.**

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Verwalten von Complianceworkflows mit Verbesserungsmaßnahmen

Verbesserungsmaßnahmen zentralisieren Ihre Complianceaktivitäten. Jede Verbesserungsaktion enthält detaillierte Implementierungsanleitungen, mit deren Hilfe Sie sich an Datenschutzbestimmungen und -standards ausrichten können. Aktionen können Benutzern in Ihrer Organisation zugewiesen werden, um Implementierungs- und Testarbeiten durchzuführen. Sie können auch Dokumentation, Notizen und Statusaktualisierungen innerhalb der Aktion speichern.

Alle Verbesserungsmaßnahmen sind auf der Seite Verbesserungsmaßnahmen aufgeführt. Erfahren Sie mehr über [das Anzeigen Ihrer Verbesserungsaktionen.](compliance-manager-setup.md#improvement-actions-page)

## <a name="improvement-actions-details-page"></a>Detailseite für Verbesserungsmaßnahmen

Jede Verbesserungsaktion verfügt über eine Detailseite mit dem aktuellen Status, den zugehörigen Standards und behördlichen Anforderungen sowie empfohlenen Implementierungsleitfäden. [Zu den technischen](compliance-score-calculation.md#technical-and-non-technical-actions) Aktionen gehört **ein Link "Jetzt** starten", der Sie zur geeigneten Lösung für die Implementierung führt. Sie können die Implementierungs- und Testdokumentation direkt an die Detailseite einer Verbesserungsaktion anfügen.

So zeigen Sie die Detailseite einer Verbesserungsaktion an:

1. Wechseln Sie zu Ihrer Seite verbesserungsaktionen.
2. Wählen Sie die Zeile der beabsichtigten Verbesserungsaktion aus, die die Detailseite öffnet.

Sie können ganz einfach die nächste oder vorherige Verbesserungsaktion in der Liste anzeigen, indem Sie den Pfeil nach oben oder unten in der oberen rechten Ecke des Bildschirms auswählen. Wenn Sie Ihre Liste auf der Seite verbesserungsaktionen gefiltert haben, gelangen Sie beim Nach- oder Abwärtswechsel zum nächsten Element in dieser gefilterten Liste.

## <a name="assign-improvement-actions"></a>Zuweisen von Verbesserungsmaßnahmen

Um mit der Implementierung einer Verbesserungsaktion zu beginnen, können Sie die Arbeit selbst oder einem anderen Benutzer zuweisen. Die zugewiesene Person kann sein:

- Der Besitzer einer Unternehmensrichtlinie
- Ein IT-Implementierer
- Ein anderer Mitarbeiter, der für die Ausführung der Aufgabe verantwortlich ist

Nachdem Sie den geeigneten Zuordnende identifiziert haben, müssen Sie sicherstellen, dass er über eine ausreichende Rolle für [den Compliance-Manager](compliance-manager-setup.md#set-user-permissions-and-assign-roles) für die Ausführung der Arbeit verkn?nnen kann. Führen Sie dann die folgenden Schritte aus, um die Verbesserungsaktion zuzuordnen:

1. Wählen Sie auf der Seite Details zu Verbesserungsmaßnahmen die Option **Status bearbeiten** im oberen linken Bereich des Bildschirms aus.

2. Wählen Sie im Flyoutbereich Bearbeitungsstatus das Feld **Zugewiesen für** aus, um eine **Liste** vorgeschlagener Personen mit Benutzern anzuzeigen. Sie können den Benutzer aus der Liste auswählen oder die E-Mail-Adresse der Person eingeben, der Sie ihn zuweisen möchten.

3. Wählen **Sie Speichern und Schließen aus.** Der zugewiesene Benutzer erhält eine E-Mail mit der Erläuterung, dass ihm die Verbesserungsaktion zugewiesen wurde, mit einem direkten Link zur Verbesserungsaktion. 
> [!NOTE]
> Kunden der US Government Community (GCC) high and Department of Defense (DoD) erhalten keine E-Mail, wenn ihnen Verbesserungsmaßnahmen zugewiesen werden.

Der zugewiesene Benutzer kann dann die empfohlenen Aktionen ausführen.

#### <a name="assign-multiple-improvement-actions-to-a-single-user"></a>Zuweisen mehrerer Verbesserungsmaßnahmen zu einem einzelnen Benutzer

Sie können einem Benutzer mehrere Verbesserungsmaßnahmen zuweisen, indem Sie die folgenden Schritte ausführen:

1. Wechseln Sie zur Seite Verbesserungsaktionen.
2. Wählen Sie den Bereich links vom Namen der Verbesserungsaktion aus. Es wird ein Rundes Überprüfungssymbol angezeigt, das angibt, dass Sie diese Aktion ausgewählt haben. Überprüfen Sie alle Aktionen, die Sie zuweisen möchten.
3. Wählen Sie **oben in der** Tabelle Verbesserungsaktionen den Link Benutzer zuweisen aus.
4. Ein Popupfenster wird geöffnet. Geben Sie im Feld **Zuweisen** zu den Namen der Person ein, der Sie die Aktionen zuweisen möchten. Sie können auch aus der Liste der vorgeschlagenen Personen auswählen.
5. Nachdem Sie das Feld **Zuweisen an** mit dem Namen des Zuordnende auffüllen, wählen Sie **Zuweisen aus.**
6. Anschließend sehen Sie die Seite Verbesserungsaktionen mit dem neuen Zuordnende für die Aktionen, die Sie gerade zugewiesen haben.

## <a name="perform-work-and-store-documentation"></a>Ausführen von Arbeits- und Speicherdokumentation

Sie können Dateien und Notizen im Zusammenhang mit Implementierungs- und Testarbeiten direkt in den **Abschnitt Notizen und Dokumentation** hochladen. Diese Umgebung ist ein sicheres, zentrales Repository, das Ihnen hilft, die Zufriedenheit der Kontrollen zu demonstrieren, um Compliancestandards und -vorschriften zu erfüllen. Jeder Benutzer mit schreibgeschützten Zugriff kann Inhalte in diesem Abschnitt lesen. Nur Benutzer mit Bearbeitungsrechten können Dateien hochladen und herunterladen sowie Notizen eingeben oder bearbeiten.

Der **Abschnitt Notizen und Dokumentation** enthält Felder für hochgeladene Dokumente, Implementierungshinweise, Testnotizen und zusätzliche Notizen.

#### <a name="uploaded-documents"></a>Hochgeladene Dokumente

- Wählen **Sie Dokumente verwalten** aus, um relevante Dateien hochzuladen.
- Wenn der Flyoutbereich Dokumente verwalten geöffnet wird, wählen Sie **Dokument hinzufügen** aus, und wählen Sie dann Ihre Datei aus Ihrem System aus. Akzeptierte Dateitypen:
    - Dokumente (.doc, .xls, .ppt, .txt, .pdf)
    - Bilder (.jpg, .png)
    - Video (.mkv)
    - Komprimierte Dateien (.zip, .rar)
- Sobald die Datei im Bereich aufgelöst wurde, wählen **Sie Schließen** aus, wodurch die Dateianlage automatisch gespeichert wird. Anschließend wird die Datei unter Hochgeladene Dokumente **aufgeführt.**
- Wenn Sie das Dokument herunterladen oder löschen möchten, wählen Sie **Dokumente verwalten** unter der Liste der Dokumente aus. Wählen Sie im Flyoutbereich die Dokumentzeile aus, um sie zu markieren, und wählen Sie **dann Herunterladen** oder **Löschen aus.**

#### <a name="implementation-notes-test-notes-and-additional-notes"></a>Implementierungshinweise, Testnotizen und zusätzliche Hinweise

- Wenn Sie Notizen in einem dieser drei Felder hinzufügen möchten, wählen Sie **Implementierungshinweise** bearbeiten unter einem dieser Felder aus.
- Wenn der Flyoutbereich geöffnet wird, geben Sie Notizen in das Textfeld ein, und wählen Sie **Dann Speichern und Schließen aus.**
- Um Notizen zu bearbeiten, wählen Sie **Implementierungsnotizen bearbeiten** aus, nehmen Sie Ihre Bearbeitungen vor, und wählen Sie **dann Speichern und Schließen aus.**

In den Notizenfeldern gibt es keine Zeichenbeschränkung. Es wird empfohlen, Notizen kurz zu halten, damit Sie sie auf der Detailseite zu Verbesserungsmaßnahmen auf einfache Weise anzeigen und bearbeiten können.

## <a name="change-improvement-action-status"></a>Status der Verbesserungsaktion ändern

Sie können den Implementierungsstatus und das Implementierungsdatum sowie den Teststatus und das Testdatum für jede Verbesserungsaktion aufzeichnen. Die **Implementierungs-** **und Teststatusfelder** können von jedem Benutzer mit Bearbeitungsberechtigungen bearbeitet werden, nicht nur von der zugewiesenen Person.

Um den Status einer Verbesserungsaktion zu bearbeiten, wählen Sie **im** oberen linken Abschnitt der Detailseite Den Status bearbeiten aus. Nachfolgend finden Sie die verfügbaren Felder und Statusoptionen:

- **Implementierungsstatus**
    - **Nicht implementiert** – Aktion noch nicht implementiert
    - **Implementiert** – Aktion implementiert
    - **Alternative Implementierung** – Wählen Sie diese Option aus, wenn Sie andere Tools von Drittanbietern verwendet oder andere Aktionen ergreifen, die nicht in den Microsoft-Empfehlungen enthalten sind.
    - **Geplant** – Aktion ist für die Implementierung geplant
    - **Nicht relevant** – Aktion ist für Ihre Organisation nicht relevant und trägt nicht zu Ihrer Bewertung bei
- **Implementierungsdatum**: verfügbar, um auszuwählen, wann der Implementierungsstatus "implementiert" oder "alternative Implementierung" ist
- **Teststatus**: verfügbar, um auszuwählen, wann der Implementierungsstatus "implementiert" oder "alternative Implementierung" ist:
    - **Nicht bewertet** – Aktion wurde nicht getestet
    - **Bestanden** – Implementierung wurde von einem Gutachter überprüft
    - **Fehlgeschlagenes niedriges Risiko** – Tests fehlgeschlagen, geringes Risiko
    - **Fehlgeschlagenes mittleres Risiko** – Test fehlgeschlagen, mittleres Risiko
    - **Fehlgeschlagenes hohes Risiko** – Test fehlgeschlagen, hohes Risiko
    - **Out of scope** – die Aktion ist nicht für die Bewertung und trägt nicht zu Ihrer Bewertung bei.
- **Testdatum:** Umschalten durch das Kalenderpop-up, um das Datum auszuwählen

Allgemeine Aktionen werden gruppenübergreifend synchronisiert. Wenn zwei unterschiedliche Bewertungen in derselben Gruppe Von Ihnen verwaltete Verbesserungsmaßnahmen freigeben, werden alle Aktualisierungen, die Sie an den Implementierungsdetails oder dem Status einer Aktion vornehmen, automatisch mit derselben Aktion in jeder anderen Bewertung in der Gruppe synchronisiert. Mit dieser Synchronisierung können Sie eine Verbesserungsaktion implementieren und mehrere Anforderungen in mehreren Vorschriften erfüllen.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Zuweisen von Verbesserungsmaßnahmen zum Abschluss an den Bewerter

Nachdem Sie die Arbeit abgeschlossen, Tests durchgeführt und Nachweise hochgeladen haben, besteht der nächste Schritt in der Zuweisung der Verbesserungsaktion an einen Bewerter zur Überprüfung. Der Prüfer überprüft die Arbeit, prüft die Dokumentation und wählt den entsprechenden Teststatus aus.

**Wenn der Teststatus auf "Bestanden"** festgelegt ist: Die Aktion ist abgeschlossen, und die erzielten Punkte zeigen die maximal erzielten Punkte an. Die Punkte werden dann auf Ihre Gesamtkonformitätsnote angerechnet.

**Wenn der Teststatus auf "Fehlgeschlagen"** festgelegt ist: Die Aktion erfüllt nicht die Anforderungen, und der Bewerter kann sie dem entsprechenden Benutzer für zusätzliche Arbeit zuweisen.

## <a name="accepting-updates-to-improvement-actions"></a>Akzeptieren von Updates für Verbesserungsmaßnahmen

Wenn ein Update für eine Verbesserungsaktion verfügbar ist, wird neben dem Namen eine Benachrichtigung angezeigt. Sie können das Update entweder akzeptieren oder es für einen späteren Zeitpunkt zurückdingen.

#### <a name="what-causes-an-update"></a>Ursachen eines Updates

Ein Update tritt auf, wenn Änderungen im Zusammenhang mit Bewertung, Automatisierung oder Bereich vorgenommen werden. Änderungen können neue Anleitungen für Verbesserungsmaßnahmen beinhalten, die auf behördlichen Änderungen basieren, oder aufgrund von Produktänderungen. Nur die von Ihrer Organisation verwalteten Verbesserungsmaßnahmen erhalten Updatebenachrichtigungen.

#### <a name="where-youll-see-assessment-update-notifications"></a>Dort werden Benachrichtigungen zu Bewertungsupdates angezeigt

Wenn eine Verbesserungsaktion aktualisiert wird,  wird neben dem Namen auf der Seite Verbesserungsmaßnahmen und auf der Detailseite der zugehörigen Bewertungen eine Ausstehende Aktualisierungsbezeichnung angezeigt.

Wechseln Sie zur Detailseite der Verbesserungsaktion, und wählen Sie die Schaltfläche Update überprüfen im oberen Banner aus, um Details zu den Änderungen zu überprüfen und das Update zu akzeptieren oder zurück zu legen. 

#### <a name="review-update-to-accept-or-defer"></a>Überprüfen des Updates auf Annahme oder Verschiebung

Nachdem Sie **auf der** Seite Verbesserungsaktionsdetails die Option Update überprüfen ausgewählt haben, wird auf der rechten Seite des Bildschirms ein Flyoutbereich angezeigt. Der Flyoutbereich enthält wichtige Details zum Update, z. B. die Auswirkungen der Bewertungen und Änderungen in Punktzahl und Umfang.

Wählen **Sie Update akzeptieren** aus, um alle Änderungen an der Verbesserungsaktion zu akzeptieren. **Akzeptierte Änderungen sind dauerhaft.**

> [!NOTE]
> Wenn Sie ein Update für eine Aktion akzeptieren, akzeptieren Sie auch Updates für andere Versionen oder Instanzen dieser Aktion. Updates werden mandantenweit für technische Aktionen und gruppenweit für nicht technische Aktionen weiterverbreitet.

Wenn Sie **Abbrechen** auswählen, wird das Update nicht auf die Verbesserungsaktion angewendet. Es wird jedoch weiterhin die **Benachrichtigung** über ausstehende Updates angezeigt, bis Sie das Update akzeptieren.

**Warum wir empfehlen, Updates zu akzeptieren**

Das Akzeptieren von Updates trägt dazu bei, dass Sie über die neuesten Anleitungen zur Verwendung von Lösungen verfügen und geeignete Verbesserungsmaßnahmen ergreifen, um die Anforderungen der Zertifizierung zu erfüllen.

**Gründe für die Verschiebung eines Updates**

Wenn Sie gerade eine Bewertung abschließen, die die Verbesserungsaktion enthält, sollten Sie sicherstellen, dass Sie die Arbeit daran abgeschlossen haben, bevor Sie das Update akzeptieren. Sie können das Update für einen späteren Zeitpunkt zurückdingen, indem Sie im Flyoutbereich für das Überprüfungsupdate die Option **Abbrechen** auswählen.

#### <a name="accept-all-updates-at-once"></a>Alle Updates gleichzeitig akzeptieren

Wenn Sie über mehrere Updates verfügen und sie alle  gleichzeitig akzeptieren möchten, wählen Sie oben in der Tabelle Verbesserungsmaßnahmen den Link Alle Updates akzeptieren aus. Es wird ein Flyoutbereich angezeigt, der die Anzahl der zu aktualisierende Aktionen auflistet. Wählen Sie die **Schaltfläche Updates akzeptieren** aus, um alle Updates anzuwenden.

Beachten Sie, dass beim Zurückkehren zu Ihrer Seite mit Verbesserungsmaßnahmen möglicherweise eine Meldung am oberen Rand der Seite angezeigt wird, in der Sie aufgefordert werden, die Seite zu aktualisieren, damit die Updates abgeschlossen werden.

## <a name="export-a-report"></a>Exportieren eines Berichts

Wählen **Sie Exportieren** in der oberen linken Ecke Des Bildschirms aus, um ein Excel-Arbeitsblatt herunterzuladen, das alle Verbesserungsmaßnahmen und filterkategorien enthält, die auf der Seite Verbesserungsmaßnahmen angezeigt werden.
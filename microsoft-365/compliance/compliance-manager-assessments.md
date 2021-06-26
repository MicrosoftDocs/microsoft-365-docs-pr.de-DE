---
title: Erstellen und Verwalten von Bewertungen im Microsoft Compliance Manager
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
description: Erstellen Sie Bewertungen im Microsoft Compliance Manager, um ihnen zu helfen, die Anforderungen von Vorschriften und Zertifizierungen zu erfüllen, die für Ihre Organisation wichtig sind.
ms.openlocfilehash: 4530f8544834c672b3ae1ebb70625ffe8f2ae4ae
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2021
ms.locfileid: "53148938"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Erstellen und Verwalten von Bewertungen im Compliance-Manager

**In diesem Artikel:** Erfahren Sie, wie Sie compliance-Manager für Ihre Organisation anpassen, indem Sie **Bewertungen** erstellen und verwalten. Dieser Artikel führt Sie durch das Erstellen von Bewertungen, das Organisieren dieser Bewertungen in **Gruppen,** das Arbeiten mit **Steuerelementen,** das Akzeptieren von **Updates** und das Exportieren von **Bewertungsberichten.**

## <a name="introduction-to-assessments"></a>Einführung in Bewertungen

Compliance-Manager hilft Ihnen bei der Erstellung von Bewertungen, die Ihre Compliance mit branchen- und regionalen Vorschriften bewerten, die für Ihre Organisation gelten. Bewertungen basieren auf dem Framework von Bewertungsvorlagen, die die erforderlichen Kontrollen, Verbesserungsmaßnahmen und Microsoft-Maßnahmen zum Abschließen der Bewertung enthalten. Das Einrichten der relevantesten Bewertungen für Ihre Organisation kann Ihnen bei der Implementierung von Richtlinien und betrieblichen Verfahren helfen, um Ihr Compliancerisiko zu begrenzen.

Alle Ihre Bewertungen sind auf der Registerkarte "Bewertungen" des Compliance-Managers aufgeführt. Erfahren Sie mehr [darüber, wie Sie Ihre Ansicht Ihrer Bewertungen filtern und Statuszustände interpretieren.](compliance-manager-setup.md#assessments-page)

> [!IMPORTANT]
> Die Vorlagen, die Ihrer Organisation für die Erstellung von Bewertungen zur Verfügung stehen, hängen von Ihrem Lizenzvertrag ab. [Überprüfen Sie die Lizenzierungsdetails.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="data-protection-baseline-default-assessment"></a>Standardbewertung der Datenschutzgrundwerte

Für die ersten Schritte bietet Microsoft eine **Standardbewertung** im Compliance-Manager für die **Microsoft 365 Datenschutzgrundwerte** an. Diese Baselinebewertung enthält eine Reihe von Kontrollen für wichtige Vorschriften und Standards für Datenschutz und allgemeine Datengovernance. Diese Baseline basiert hauptsächlich auf NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) und ISO (International Organization for Standardization) sowie aus FedRAMP (Federal Risk and Authorization Management Program) und der DSGVO (General Data Protection Regulation of the European Union).

Diese Bewertung wird verwendet, um Ihre anfängliche Compliancebewertung zu berechnen, wenn Sie zum ersten Mal zum Compliance-Manager kommen, bevor Sie andere Bewertungen konfigurieren. Compliance-Manager sammelt erste Signale von Ihren Microsoft 365 Lösungen. Sie sehen auf einen Blick, wie Ihre Organisation im Verhältnis zu wichtigen Datenschutzstandards und -vorschriften funktioniert, und sehen, welche Verbesserungsmaßnahmen sie ergreifen müssen.

Compliance-Manager wird hilfreicher, wenn Sie Ihre eigenen Bewertungen erstellen und verwalten, um die besonderen Anforderungen Ihrer Organisation zu erfüllen.

## <a name="understand-groups-before-creating-assessments"></a>Verstehen von Gruppen vor dem Erstellen von Bewertungen

Wenn Sie eine Bewertung erstellen, müssen Sie sie einer Gruppe zuweisen. Gruppen sind Container, mit denen Sie Bewertungen so organisieren können, dass sie für Sie logisch sind, z. B. nach Jahr oder Verordnung oder basierend auf den Abteilungen oder Regionen Ihrer Organisation. Aus diesem Grund empfehlen wir die Planung einer Gruppierungsstrategie, bevor Sie Bewertungen erstellen.

Nachfolgend finden Sie Beispiele für zwei Gruppen und deren zugrunde liegende Bewertungen:

- **FFIEC IS Assessment 2020**
  - FFIEC IS
- **Bewertungen der Datensicherheit und des Datenschutzes**
  - ISO 27001:2013
  - ISO 27018:2014

Wenn zwei verschiedene Bewertungen in derselben Gruppe Verbesserungsmaßnahmen teilen, die Sie verwalten, werden alle Aktualisierungen, die Sie an den Implementierungsdetails oder dem Status einer Aktion vornehmen, automatisch in der gesamten Gruppe synchronisiert. Mit dieser Synchronisierung können Sie eine Verbesserungsmaßnahme implementieren und mehrere Anforderungen gleichzeitig erfüllen.

### <a name="create-a-group"></a>Erstellen einer Gruppe

Sie können eine Gruppe erstellen, während Sie eine neue Bewertung erstellen. Gruppen können nicht als eigenständige Entitäten erstellt werden.

### <a name="what-to-know-when-working-with-groups"></a>Wissenswertes beim Arbeiten mit Gruppen

- Eine Gruppe muss mindestens eine Bewertung enthalten.
- Gruppennamen müssen innerhalb Ihrer Organisation eindeutig sein.
- Gruppen verfügen nicht über Sicherheitseigenschaften. Alle Berechtigungen sind Bewertungen zugeordnet.
- Nachdem Sie einer Gruppe eine Bewertung hinzugefügt haben, kann die Gruppierung nicht mehr geändert werden.
- Wenn Sie einer vorhandenen Gruppe eine neue Bewertung hinzufügen, werden allgemeine Informationen aus Bewertungen in dieser Gruppe in die neue Bewertung kopiert.
- Verwandte Bewertungssteuerelemente in verschiedenen Bewertungen innerhalb derselben Gruppe werden automatisch aktualisiert, wenn sie abgeschlossen sind.
- Wenn eine Änderung an einer Verbesserung vorgenommen wird, die in mehreren Gruppen angezeigt wird, wird diese Änderung in allen Fällen dieser Verbesserungsmaßnahme widergespiegelt.
- Gruppen können Bewertungen für die gleiche Zertifizierung oder Vorschrift enthalten, aber jede Gruppe kann nur eine Bewertung für ein bestimmtes Produkt-Zertifizierungspaar enthalten. Beispielsweise kann eine Gruppe keine zwei Bewertungen für Office 365 und NIST CSF enthalten. Eine Gruppe kann nur dann mehrere Bewertungen für dasselbe Produkt enthalten, wenn die entsprechende Zertifizierung oder Verordnung für jedes Produkt unterschiedlich ist.
- Durch das Löschen einer Bewertung wird die Beziehung zwischen dieser Bewertung und der Gruppe unterbrochen.
- Gruppen können nicht manuell gelöscht werden.

## <a name="create-assessments"></a>Erstellen von Bewertungen

> [!NOTE]
> Nur Benutzer mit einer Rolle als globaler Administrator, Compliance-Manager-Administration oder Compliance-Manager-Prüfer können Bewertungen erstellen und ändern. Erfahren Sie mehr über [Rollen und Berechtigungen.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

Führen Sie die folgenden Schritte aus, um mit dem Erstellen von Bewertungen zu beginnen.

1. Wissen Sie, welcher Gruppe Sie Ihre Bewertung zuweisen oder bereit sind, eine neue für diese Bewertung zu erstellen.

2. Öffnen Sie den Bewertungs-Assistenten. Sie können von einem von zwei Stellen aus auf diesen Flyoutbereich zugreifen:
    - Wechseln Sie im Compliance-Manager zu Ihrer **Bewertungsseite,** und wählen Sie Bewertung **hinzufügen** aus. Oder
    - Suchen Sie die Vorlage, die Sie auf der Registerkarte **"Bewertungsvorlagen"** verwenden möchten, zeigen Sie deren Details an, und wählen Sie **"Bewertung erstellen"** aus. Dadurch wird das Vorlagenauswahlfeld des Assistenten für Sie aufgefüllt.

3. **Wählen Sie eine Vorlage** aus: Wenn Sie in Schritt 2 noch keine Vorlage ausgewählt haben, wählen Sie eine Vorlage aus, die als Grundlage für Ihre Bewertung dient. Sie sehen die Liste der Vorlagen, die in eingeschlossene und Premiumkategorien unterteilt sind (weitere Informationen finden Sie unter [Vorlagentypen).](compliance-manager-templates.md#template-availability-and-licensing) Wählen Sie das Optionsfeld neben der ausgewählten Vorlage aus, und klicken Sie dann auf **"Weiter".**

4. **Name und Gruppe:** Legen Sie diese Eigenschaften fest, um Ihre Bewertung zu identifizieren und einer Gruppe zuzuweisen.
    - **Name:** Geben Sie im Feld **"Bewertungsname"** einen Namen für Ihre Bewertung ein. Bewertungsnamen müssen innerhalb von Gruppen eindeutig sein. Wenn der Name Ihrer Bewertung mit dem Namen einer anderen Bewertung in einer bestimmten Gruppe übereinstimmt, erhalten Sie eine Fehlermeldung, in der Sie aufgefordert werden, einen anderen Namen zu erstellen.
    - **Gruppe:** Weisen Sie Ihre Bewertung einer Gruppe zu. Sie können eine der folgenden Aktionen ausführen:
        - Wählen Sie **"Vorhandene Gruppe verwenden"** aus, um sie einer gruppe zuzuweisen, die Sie bereits erstellt haben. Oder
        - Wählen Sie **"Neue Gruppe erstellen"** aus, um eine neue Gruppe zu erstellen, und weisen Sie ihr diese Bewertung zu:
            - Ermitteln Sie einen Namen für Ihre Gruppe, und geben Sie ihn in das Feld unterhalb des Optionsfelds ein.
            - Sie können **Daten aus einer vorhandenen Gruppe kopieren,** z. B. Implementierungs- und Testdetails und Dokumente, indem Sie die entsprechenden Felder auswählen.

    Wenn Sie fertig sind, wählen Sie **Weiter**.

5. **Überprüfen und beenden Sie:** Auf dem letzten Bildschirm des Assistenten werden die Vorlage, der Name und die Gruppe angezeigt, die für die Bewertung ausgewählt wurden. Sie können alle diese Einstellungen über die Links auf dem Bildschirm bearbeiten, die Sie zurück zu den relevanten Schritten im Assistenten führen. Wenn Sie bereit sind, wählen Sie **Bewertung erstellen** aus.

6. Der nächste Bildschirm bestätigt, dass Sie Ihre neue Bewertung erfolgreich erstellt haben. Wählen Sie **"Fertig"** aus, um den Assistenten zu schließen, und die Detailseite der neuen Bewertung wird auf dem Bildschirm angezeigt.

Wenn nach dem Auswählen der Option **"Bewertung erstellen"** ein **fehlgeschlagener** Bewertungsbildschirm angezeigt wird, wählen Sie **"Erneut versuchen"** aus, um Ihre Bewertung neu zu erstellen.

Sie können den Namen Ihrer Bewertung ändern, nachdem Sie sie erstellt haben, indem Sie in der oberen rechten Ecke der [Detailseite](#monitor-assessment-progress-and-controls)der Bewertung die Schaltfläche **"Namen bearbeiten"** auswählen.

## <a name="monitor-assessment-progress-and-controls"></a>Überwachen des Bewertungsfortschritts und der Steuerelemente

Jede Bewertung verfügt über eine Detailseite, die einen Überblick über ihren Fortschritt beim Abschließen der Bewertung bietet. Die Seite zeigt Ihren Fortschritt beim Abschließen von Steuerelementen und den Teststatus der wichtigsten Verbesserungsmaßnahmen innerhalb dieser Steuerelemente.

### <a name="overview-tab"></a>Registerkarte „Übersicht“

Die Registerkarte "Übersicht" enthält ein Diagramm, das Ihren Prozentsatz für den Abschluss der Bewertung anzeigt. Dieses Diagramm enthält eine Aufschlüsselung von Punkten aus Aktionen, die Sie besitzen, und Punkt aus Aktionen, die Microsoft gehört, damit Sie sehen können, wie viele weitere Punkte Sie benötigen, um die Bewertung abzuschließen.

Die wichtigsten Verbesserungsmaßnahmen für Steuerelemente in der Bewertung werden in der Reihenfolge der größten potenziellen Auswirkungen aufgelistet, um Punkte zu erzielen. Das zugeordnete Diagramm zeigt den aggregierten Teststatus Ihrer Verbesserungsmaßnahmen an, damit Sie schnell ermitteln können, was getestet wurde und was noch zu tun ist.

Um auf einzelne Verbesserungsmaßnahmen zuzugreifen, besuchen Sie die Registerkarte **"Steuerelemente"** oder die Registerkarte **"Verbesserungsmaßnahmen".**

### <a name="controls-tab"></a>Registerkarte "Steuerelemente"

Auf der Registerkarte "Steuerelemente" werden detaillierte Informationen für jedes Steuerelement angezeigt, das der Bewertung zugeordnet ist. Ein Übersichtsdiagramm zum **Steuerelementstatus** zeigt den Status von Steuerelementen nach Familie, sodass Sie auf einen Blick sehen können, welche Gruppierungen von Steuerelementen Aufmerksamkeit benötigen.

Unterhalb des Diagramms enthält eine Tabelle detaillierte Informationen zu den einzelnen Steuerelementen innerhalb der Bewertung. Steuerelemente werden nach Steuerelementfamilie gruppiert. Erweitern Sie jeden Nachnamen, um die einzelnen darin enthaltenen Steuerelemente einzugeben. Die für jedes Steuerelement aufgeführten Informationen umfassen:

- **Steuerelementtitel**
- **Status**: gibt den Teststatus der Verbesserungsmaßnahmen innerhalb des Steuerelements wieder. 
    - **Erfolgreich** – alle Verbesserungsmaßnahmen weisen den Teststatus "bestanden" auf, oder mindestens eine wird übergeben, und der Rest liegt außerhalb des Gültigkeitsbereichs.
    -  **Fehlgeschlagen** – mindestens eine Verbesserungsmaßnahme weist den Teststatus "fehlgeschlagen" auf.
    - **Keine** – alle Verbesserungsmaßnahmen wurden nicht getestet
    - **Außerhalb des Gültigkeitsbereichs** – alle Verbesserungsmaßnahmen sind für diese Bewertung nicht in Reichweite
    - **In Bearbeitung** – Verbesserungsmaßnahmen haben einen anderen Status als die oben aufgeführten, die "in Bearbeitung", "teilweise Gutschrift" oder "nicht erkannt" umfassen könnten.
- **Steuerelement-ID:** Die Identifikationsnummer des Steuerelements, die durch die entsprechende Verordnung, den Standard oder die Richtlinie zugewiesen wird
- **Erreichte Punkte:** die Anzahl der Punkte, die durch das Abschließen von Aktionen erzielt werden, von der Gesamtzahl der erreichbaren Punkte. 
- **Ihre Aktionen:** die Anzahl der abgeschlossenen Aktionen aus der Gesamtzahl der auszuführenden Aktionen.
- **Microsoft-Aktionen:** Die Anzahl der von Microsoft abgeschlossenen Aktionen 

Um die Details eines Steuerelements anzuzeigen, wählen Sie es aus der Zeile in der Tabelle aus. Die Seite mit den Steuerelementdetails zeigt ein Diagramm, das den Teststatus der Aktionen innerhalb dieses Steuerelements angibt. Eine Tabelle unterhalb des Diagramms zeigt die wichtigsten Verbesserungsmaßnahmen für dieses Steuerelement.

Wählen Sie eine Verbesserungsmaßnahme aus der Liste aus, um einen Drilldown zur Detailseite der Verbesserungsmaßnahme auszuführen. Auf den Detailseiten werden Teststatus, Implementierungshinweise und der Start in der empfohlenen Lösung angezeigt.

### <a name="your-improvement-actions-tab"></a>Registerkarte "Verbesserungsmaßnahmen"

Die Registerkarte für Ihre Verbesserungsmaßnahmen listet alle Steuerelemente in der Bewertung auf, die von Ihrer Organisation verwaltet werden. Die Statusleiste beschreibt den aggregierten Teststatus Ihrer Verbesserungsmaßnahmen in der Bewertung, damit Sie schnell ermitteln können, was getestet wurde und was noch ausgeführt werden muss. Unterhalb der Leiste finden Sie eine vollständige Liste der Verbesserungsmaßnahmen und wichtigsten Details, einschließlich: Teststatus, Anzahl potenzieller und erzielter Punkte, zugehörige Vorschriften und Standards, anwendbare Lösung, Aktionstyp und Kontrollfamilie. Erfahren Sie mehr [darüber, wie Aktionen zu Ihrer Compliancebewertung beitragen.](compliance-score-calculation.md#action-types-and-points)

Wählen Sie eine Verbesserungsmaßnahme aus, um die Detailseite anzuzeigen, und wählen Sie den Link **"Jetzt starten"** aus, um die Lösung zu öffnen, um Maßnahmen zu ergreifen.

### <a name="microsoft-actions-tab"></a>Registerkarte "Microsoft-Aktionen"

Die Registerkarte "Microsoft-Aktionen" listet alle Aktionen in der Bewertung auf, die von Microsoft verwaltet werden. Die Liste enthält wichtige Aktionsdetails, einschließlich: Teststatus, Punkte, die zu Ihrer allgemeinen Compliancebewertung beitragen, zugehörige Vorschriften und Standards, zutreffende Lösung, Aktionstyp und Steuerelementfamilie. Wählen Sie eine Verbesserungsmaßnahme aus, um die Detailseite anzuzeigen.

Erfahren Sie mehr [darüber, wie Steuerelemente und Verbesserungsmaßnahmen nachverfolgt und bewertet werden.](compliance-score-calculation.md)

## <a name="accept-updates-to-assessments"></a>Akzeptieren von Updates für Bewertungen

Wenn ein Update für eine Bewertung verfügbar ist, wird eine Benachrichtigung angezeigt, und Sie haben die Möglichkeit, das Update zu akzeptieren oder für einen späteren Zeitpunkt zurückstellen.

### <a name="what-causes-an-update"></a>Gründe für ein Update

Eine Bewertungsaktualisierung erfolgt, wenn zugrunde liegende Vorlagenänderungen vorhanden sind, die sich auf die Bewertung auswirken. Änderungen können eine Anpassung der Steuerungszuordnung oder andere Anleitungen auf der Grundlage von regulatorischen Änderungen oder Produktänderungen umfassen. Bewertungsupdates können sowohl von Ihrer Organisation (z. B. wenn eine [benutzerdefinierte Vorlage geändert wird)](compliance-manager-templates.md#modify-a-template)als auch von Microsoft stammen.

Wenn Microsoft eine compliance-Manager-Vorlage aktualisiert, die Sie erweitert haben, erbt Ihre Bewertung diese Updates, sobald Sie sie akzeptiert haben. Ihre Bewertung behält die zusätzlichen Attribute bei, die Sie auf die Bewertung angewendet haben, wenn Sie sie erweitert haben.

Benutzerdefinierte Bewertungen, die Sie erstellen, erhalten keine Vorlagenupdates von Microsoft. Benutzerdefinierte Bewertungen können Aktualisierungen von Verbesserungsmaßnahmen erhalten, aber alle Microsoft-Updates zur Steuerung der Zuordnung zwischen Bewertungen und Verbesserungsmaßnahmen gelten nicht für benutzerdefinierte Vorlagen.

> [!NOTE]
> Aktualisierungen von Bewertungen gelten nur auf Gruppenebene. Wenn Sie zwei Bewertungen aus derselben Vorlage erstellt haben, die in zwei verschiedenen Gruppen vorhanden sind, hat jede Bewertung eine ausstehende Updatebenachrichtigung, und Sie müssen das Update für jede Bewertung in der jeweiligen Gruppe einzeln akzeptieren.

#### <a name="where-youll-see-assessment-update-notifications"></a>Wo Benachrichtigungen zu Bewertungsupdates angezeigt werden

Auf der Seite mit den Bewertungsdetails wird neben der Bewertung auch eine Bezeichnung für **ausstehende Updates** mit einem Update angezeigt. Wählen Sie diese Bewertung aus, um zur Detailseite zu gelangen.

Eine Meldung am oberen Rand der Bewertungsdetailseite zeigt, dass für diese Bewertung ein Update verfügbar ist. Wählen Sie im Banner die Schaltfläche **"Update überprüfen"** aus, um die spezifischen Änderungen zu überprüfen und das Update zu akzeptieren oder zurückstellen.

Auf der Seite mit den Bewertungsdetails sind möglicherweise auch Verbesserungsmaßnahmen aufgeführt, die neben ihnen eine Bezeichnung für **ausstehende Updates** haben. Diese Updates sind für bestimmte Änderungen an den Verbesserungsmaßnahmen selbst vorgesehen und müssen separat akzeptiert werden. Besuchen Sie ["Akzeptieren von Updates für Verbesserungsmaßnahmen",](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) um mehr zu erfahren.

#### <a name="review-update-to-accept-or-defer"></a>Überprüfen des Updates zum Akzeptieren oder Zurückstellen

Nachdem Sie **"Update überprüfen"** auf der Seite mit den Bewertungsdetails ausgewählt haben, wird auf der rechten Seite des Bildschirms ein Flyoutbereich angezeigt. Der Flyoutbereich enthält die wichtigsten Details zum ausstehenden Update unten:

- Der Vorlagentitel
- Quelle des Updates (Microsoft, Ihre Organisation oder ein bestimmter Benutzer)
- Das Erstellungsdatum des Updates
- Eine Übersicht, in der das Update erläutert wird
- Spezifische Details zu den Änderungen, einschließlich der Auswirkungen auf Ihre Compliancebewertung, den Fortschritt beim Abschluss der Bewertung und die spezifische Anzahl von Änderungen an Verbesserungsmaßnahmen und Steuerelementen.

Wenn Sie den Link **"Aktualisierte Vorlage"** auswählen, wird eine Excel Datei mit Steuerelementdaten für die Version der Vorlage mit den ausstehenden Updates heruntergeladen. Wenn Sie den Link **"Aktuelle Vorlage"** auswählen, wird eine Datei der vorhandenen Vorlage ohne die Änderungen heruntergeladen.

Um das Update zu akzeptieren und die Änderungen an Ihrer Bewertung vorzunehmen, wählen Sie **Update akzeptieren** aus. Akzeptierte Änderungen sind dauerhaft.

Wenn Sie **"Abbrechen"** auswählen, wird die Aktualisierung nicht auf die Bewertung angewendet. Die **Benachrichtigung** über ausstehende Updates wird jedoch weiterhin angezeigt, bis Sie das Update akzeptiert haben.

**Warum wir empfehlen, Updates zu akzeptieren**

Durch das Akzeptieren von Updates können Sie sicherstellen, dass Sie über die neuesten Anleitungen zur Verwendung von Lösungen und geeignete Verbesserungsmaßnahmen verfügen, um die Anforderungen der jeweiligen Zertifizierung zu erfüllen.

**Warum Sie ein Update möglicherweise zurückstellen möchten**

Wenn Sie gerade eine Bewertung abschließen, sollten Sie sicherstellen, dass Sie die Arbeit daran abgeschlossen haben, bevor Sie eine Aktualisierung der Bewertung akzeptieren, die die Steuerungszuordnung unterbrechen könnte. Sie können das Update zu einem späteren Zeitpunkt zurückstellen, indem Sie im Flyoutbereich zum Überprüfen des Updates **"Abbrechen"** auswählen.

## <a name="export-an-assessment-report"></a>Exportieren eines Bewertungsberichts

Sie können eine Bewertung in eine Excel datei für Compliance-Interessengruppen in Ihrer Organisation oder für externe Prüfer und Regulierungsbehörden exportieren. Wählen Sie auf der Seite mit den Bewertungsdetails die Schaltfläche **"Bericht generieren"** oben auf der Seite aus, wodurch eine Excel Datei erstellt wird, die Sie speichern und freigeben können.

Der Bericht ist eine Momentaufnahme der Bewertung zum Datum und zur Uhrzeit des Exports. Es enthält die Details zu steuerelementen, die von Ihnen und Microsoft verwaltet werden, einschließlich Implementierungsstatus, Testdatum und Testergebnissen.

## <a name="delete-an-assessment"></a>Löschen einer Bewertung

Wenn Sie eine Bewertung löschen, wird sie aus der Liste auf Ihrer Bewertungsseite entfernt. Beachten Sie die folgenden wichtigen Punkte zum Löschen von Bewertungen:

- **Das Löschen einer Bewertung ist dauerhaft. Sie können es nicht zurückgeben.** Wenn Sie dieselbe Bewertung erneut verwenden möchten, müssen Sie sie erneut erstellen.
- Wenn die Verbesserungsmaßnahmen in der Bewertung in keiner anderen Bewertung angezeigt werden, werden sie gelöscht, wenn die Bewertung gelöscht wird.
- Es wird [empfohlen, einen Bericht](#export-an-assessment-report) über die Bewertung zu exportieren, bevor Sie ihn endgültig löschen.

Führen Sie die folgenden Schritte aus, um eine Bewertung zu löschen:

1. Wählen Sie auf **der** Bewertungsseite die Bewertung aus, die Sie löschen möchten, um die Detailseite dieser Bewertung zu öffnen.

2. Wählen Sie in der oberen rechten Ecke des Bildschirms die **Option "Bewertung löschen"** aus.

3. Es wird ein Fenster angezeigt, in dem Sie aufgefordert werden, zu bestätigen, dass Sie die Bewertung dauerhaft löschen möchten. Wählen Sie **"Bewertung löschen"** aus, um das Fenster zu schließen. Sie erhalten ein Bestätigungsfenster, dass Ihre Bewertung aus dem Compliance-Manager gelöscht wurde.

Wenn Sie die einzige Bewertung in einer Gruppe löschen, wird diese Gruppe auch aus dem Compliance-Manager gelöscht.

> [!NOTE]
> Sie können nicht alle Ihre Bewertungen löschen. Organisationen benötigen mindestens eine Bewertung, damit Compliance-Manager ordnungsgemäß funktioniert. Wenn die Bewertung, die Sie löschen möchten, die einzige ist, fügen Sie eine weitere Bewertung hinzu, bevor Sie die andere Bewertung löschen.

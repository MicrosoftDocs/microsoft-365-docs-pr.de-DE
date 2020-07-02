---
title: Anpassen des Microsoft-Konformitäts Bewertungsergebnisses mit Bewertungen
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
description: Design Customization Microsoft-Konformitätsbewertung durch Erstellen von Bewertungen, die Ihnen bei der Verwaltung der Compliance für Ihre Organisation helfen.
ms.openlocfilehash: 45a5e76aa4f6581146ded510f75d772c202751ee
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023308"
---
# <a name="customize-compliance-score-preview-with-assessments"></a>Anpassen der Konformitätsbewertung (Vorschau) mit Bewertungen

**In diesem Artikel:** In diesem Artikel erfahren Sie, wie Sie die Konformitätsbewertung anpassen können, indem Sie **Assessments**für die Verwendung einrichten. Hier erfahren Sie, wie Sie die **Vorlage** für eine Bewertung ändern und ihre eigenen benutzerdefinierten Bewertungen erstellen, die den Anforderungen Ihrer Organisation entsprechen. In diesem Artikel wird auch erläutert, wie Sie Bewertungen in **Gruppen**organisieren, mit **Steuerelementen**arbeiten und Bewertungs **Berichte**exportieren.

## <a name="introduction-to-assessments"></a>Einführung in Assessments

Compliance Score unterstützt Sie bei der Verwaltung der Konformität mit Assessments für die Vorschriften und Zertifizierungen, die für Ihre Organisation gelten. Bei den Bewertungen handelt es sich um Gruppierungen von Steuerelementen aus einer bestimmten Verordnung, Norm oder Richtlinie. Compliance Score erleichtert das Nachverfolgen der Compliance durch Bereitstellung von Assessments, die eine Vielzahl von Branchen-und regionalen Vorschriften und Zertifizierungen abdecken.

Jede Bewertung wird aus einer Vorlage erstellt, die als Framework dient, in dem die erforderlichen Steuerelemente und Verbesserungs Aktionen für die Abschlussprüfung enthalten sind. Durch das Einrichten der relevantesten Bewertungen für Ihre Organisation können Sie sicherstellen, dass Sie Richtlinien und Betriebsverfahren implementieren, mit denen das Compliance-Risiko eingeschränkt werden kann.

Alle Ihre Bewertungen werden auf der Seite "Bewertungen" aufgeführt. [Erfahren Sie mehr](compliance-score-setup.md#assessments-page) darüber, wie Sie Ihre Ansicht Ihrer Bewertungen Filtern und Statuszustände interpretieren.

## <a name="data-protection-baseline-default-assessment"></a>Standardbewertung der Datenschutz Basis

Um Ihnen den Einstieg zu erleichtern, bietet Microsoft eine **Standard** Bewertung in Compliance Score für Sie an, die die Microsoft 365-Datenschutz Basislinie enthält. Dieser Basisplan umfasst eine Reihe von Steuerelementen, die wichtige Regeln und Standards für den Datenschutz und die allgemeine Datensteuerung beinhalten. Dieser Basisplan zeichnet Elemente in erster Linie vom NIST-GFK (National Institute of Standards and Technology Cyber Framework) und ISO (International Organization for Standardisierungs) sowie von FedRAMP (Bundes Risiko-und Autorisierungs Management Programm) und dsgvo (allgemeine Datenschutzverordnung der Europäischen Union).

Diese Bewertung wird verwendet, um ihre anfängliche Bewertung zu berechnen, wenn Sie das erste Mal zur Kompatibilitätsbewertung kommen, bevor Sie andere Bewertungen konfigurieren. Das Kompatibilitäts Ergebnis sammelt erste Signale von Ihren Microsoft 365-Lösungen. Sie sehen auf einen Blick, wie Ihre Organisation im Verhältnis zu wichtigen Datenschutzstandards und-Vorschriften arbeitet, und wie Sie die vorgeschlagenen Verbesserungsmaßnahmen durchführen.

Da jede Organisation spezifische Anforderungen hat, beruht Compliance Score darauf, dass Sie eigene Bewertungen einrichten und verwalten, um das Risiko so umfassend wie möglich zu minimieren und möglichst weit zu mindern.

## <a name="assessment-creation-overview"></a>Übersicht über die Beurteilungs Erstellung

Es gibt drei Möglichkeiten zum Einrichten von Bewertungen:

1. Wählen Sie eine Ready to use-Bewertung aus.
2. Ändern Sie die Vorlage einer Bewertung entsprechend ihren eigenen Anforderungen.
3. Erstellen Sie Ihre eigene benutzerdefinierte Bewertung.

Benutzer müssen eine Rolle des globalen Administrators, des Compliance-Administrators, des Compliance-Daten Administrators oder des Sicherheitsadministrators innehaben, um Bewertungen zu erstellen oder zu ändern. Erfahren Sie mehr über [Rollen und Berechtigungen](compliance-score-setup.md#set-user-permissions-and-assign-roles).

> [!NOTE]
> Alle Bewertungen, die in der Kompatibilitätsbewertung erstellt oder geändert wurden, werden auch im Compliance-Manager berücksichtigt. Erfahren Sie mehr über die [Beziehung zwischen Compliance Score und Compliance-Manager](compliance-score.md#relationship-to-compliance-manager).

### <a name="ready-to-use-assessments"></a>Gebrauchsfertige Bewertungen

Kicken Sie Ihre Compliance-Reise an, indem Sie unter Compliance Scores Auswahl von [Vorlagen](compliance-score-templates.md) zum Erstellen von Bewertungen auswählen. Vorlagen enthalten die Steuerelemente und Verbesserungs Aktionen, die für jede einzelne Bewertung erforderlich sind. Die Vorlagen für Compliance Score umfassen Vorschriften und Zertifizierungen, die sich an Branchen, Regionen und gemeinsame Datenschutzstandards wie dsgvo und ISO 27001 ausrichten.

Wenn Sie **eine Bewertung einrichten möchten**, wählen Sie eine der Vorlagen aus, wenn Sie mit [dem Erstellen der Bewertung im Assistenten](#create-an-assessment)beginnen.

### <a name="modify-the-template-of-an-assessment"></a>Ändern der Vorlage einer Bewertung

Sie haben die Möglichkeit, Konformitäts Bewertungs Vorlagen für Bewertungen zu ändern, um den Anforderungen Ihrer Organisation besser gerecht zu werden. Wenn Sie beispielsweise im Allgemeinen die HIPAA-Richtlinie einhalten müssen, aber zusätzliche Datenschutz-oder Sicherheitskontrollen benötigen, können Sie unsere HIPAA-Vorlage und eigene benutzerdefinierte Felder hinzufügen, um eine neue Bewertung zu erstellen, die Ihren Fortschritt in den von Ihnen benötigten Methoden überwacht. Während der öffentlichen Vorschau müssen Sie zu Compliance-Manager wechseln, um Vorlagen zu ändern.

Befolgen Sie die folgenden Anweisungen, **um die Vorlage für eine Bewertung zu ändern**:

1. Zeigen Sie die Liste der verfügbaren [Vorlagen](compliance-score-templates.md) in der Konformitätsbewertung an, um zu bestimmen, welche Sie ändern möchten.
2. Lesen Sie die [Anweisungen für den Compliance-Manager, um eine Vorlage mithilfe des Erweiterungsprozesses anzupassen](working-with-compliance-manager.md#customize-a-template-through-the-extension-process).
3. Nachdem Sie Ihre Vorlage erstellt und in Compliance Manger importiert haben, können Sie Ihre neue Bewertung in Compliance Score erstellen. Befolgen Sie die Schritte zum Erstellen der Bewertung mit dem [Assistenten zum Erstellen von Bewertungen](#create-an-assessment).

> [!NOTE]
> Erfahren Sie mehr über die [Beziehung zwischen Compliance Score und Compliance-Manager](compliance-score.md#relationship-to-compliance-manager) während der öffentlichen Vorschau.

### <a name="create-your-own-custom-assessment"></a>Erstellen einer eigenen benutzerdefinierten Bewertung

Sie können eine eigene Bewertung ganz von Grund auf erstellen, um genau nachzuverfolgen, was Ihre Organisation benötigt. Wie beim oben beschriebenen Änderungsverfahren müssen Sie zunächst eine eigene Vorlage für die Bewertung im Compliance-Manager erstellen.

Befolgen Sie die folgenden Anweisungen, **um Ihre eigene benutzerdefinierte Bewertung zu erstellen**:

1. Hier erfahren Sie, wie Sie [eine eigene Vorlage im Compliance-Manager erstellen](working-with-compliance-manager.md#create-your-own-template-and-import-it-into-compliance-manager).
2. Nachdem Sie Ihre Vorlage erstellt und in Compliance Manger importiert haben, können Sie Ihre neue Bewertung in Compliance Score erstellen. Befolgen Sie die Schritte zum Erstellen der Bewertung mit dem [Assistenten zum Erstellen von Bewertungen](#create-an-assessment).

## <a name="understand-groups-before-creating-assessments"></a>Grundlegendes zu Gruppen vor dem Erstellen von Bewertungen

Bevor Sie Assessments erstellen oder ändern, ist es wichtig zu verstehen, wie Gruppen funktionieren. Wenn Sie eine Bewertung erstellen, müssen Sie Sie während dieses Prozesses einer Gruppe zuweisen. Es wird daher empfohlen, eine Gruppierungs Strategie für Ihre Bewertungen zu planen, bevor Sie Bewertungen erstellen.

### <a name="what-are-groups"></a>Was sind Gruppen

Gruppen sind Container, mit denen Sie Bewertungen organisieren können. Sie können Bewertungen auf eine Weise gruppieren, die für Sie logisch ist, beispielsweise nach Jahr oder Regulierung oder basierend auf den Abteilungen oder Geographien Ihrer Organisation. Im folgenden finden Sie Beispiele aus zwei Gruppen und deren zugrunde liegenden Bewertungen:

- **FFIEC ist Assessments 2020**
  - Office 365 + FFIEC ist
  - InTune + FFIEC ist
- **Sicherheits-und Datenschutz Bewertungen**
  - Office 365 + ISO 27001:2013
  - Office 365 + ISO 27018:2014

Wenn zwei unterschiedliche Bewertungen in der gleichen Gruppe Verbesserungen durchführen, die von Ihnen verwaltet werden, werden alle Aktualisierungen, die Sie an den Implementierungsdetails oder Status einer Aktion vornehmen, automatisch mit derselben Aktion in einer anderen Bewertung in der Gruppe synchronisiert. Mit dieser Synchronisierung können Sie eine Verbesserungs Aktion implementieren und mehrere Anforderungen in mehreren Bestimmungen erfüllen.

### <a name="how-to-create-a-group"></a>Vorgehensweise Erstellen einer Gruppe

Sie erstellen eine Gruppe während des Prozesses zum [Erstellen einer neuen Bewertung](#create-an-assessment).

Gruppen können nicht als eigenständige Entitäten erstellt werden; eine Gruppe muss mindestens eine Bewertung enthalten. Um eine Gruppe zu erstellen, müssen Sie zuerst eine Bewertung erstellen, um Sie in die Gruppe einzufügen.

### <a name="what-to-know-when-working-with-groups"></a>Was Sie beim Arbeiten mit Gruppen wissen sollten

- Gruppennamen müssen innerhalb Ihrer Organisation eindeutig sein.
- Gruppen verfügen nicht über Sicherheitseigenschaften. Alle Berechtigungen sind Assessments zugeordnet.
- Nachdem Sie eine Bewertung zu einer Gruppe hinzugefügt haben, kann die Gruppierung nicht mehr geändert werden.
- Zugehörige bewertungssteuerelemente in unterschiedlichen Bewertungen innerhalb derselben Gruppe werden automatisch aktualisiert, wenn Sie abgeschlossen werden.
- Wenn Sie einer vorhandenen Gruppe eine neue Bewertung hinzufügen, werden allgemeine Informationen aus Bewertungen in dieser Gruppe in die neue Bewertung kopiert.
- Gruppen können Bewertungen für dieselbe Zertifizierung oder Regel enthalten, aber jede Gruppe kann nur eine Bewertung für ein bestimmtes Produkt-Zertifizierungs Paar enthalten. Beispielsweise kann eine Gruppe keine zwei Bewertungen für Office 365 und das NIST-GfK enthalten. Eine Gruppe kann mehrere Bewertungen für dasselbe Produkt nur dann enthalten, wenn die entsprechende Zertifizierung oder Regulierung für jede andere unterschiedlich ist.
- Durch das Löschen eines Assessments wird die Beziehung zwischen dieser Bewertung und der Gruppe unterbrochen.
- Gruppen können nicht gelöscht werden.
- Wenn eine Änderung an einer Verbesserung vorgenommen wird, die in mehreren Gruppen angezeigt wird, wird diese Änderung in allen Instanzen dieser Verbesserungs Aktion widergespiegelt.

## <a name="create-an-assessment"></a>Erstellen einer Bewertung

Führen Sie die folgenden Schritte aus, um eine Bewertung in Compliance Score zu erstellen:

1. Wählen Sie auf der Seite Bewertungen die Option **Bewertung hinzufügen**aus. Ein Bewertungs-Assistent wird in einem großen Flyout-Bereich angezeigt.

2. **Wählen Sie eine Vorlage aus:** Wählen Sie eine Vorlage aus, die als Grundlage für Ihre Bewertung dient. Sie können die Vorlage "Ready to use" oder eine Vorlage auswählen, die Sie geändert oder erstellt haben. Wählen Sie das Optionsfeld neben der ausgewählten Vorlage aus, und wählen Sie dann **weiter**aus.

> [!NOTE]
> Weitere Informationen finden Sie unter [Anweisungen zum Erstellen und Ändern von Vorlagen](working-with-compliance-manager.md#templates), einem Prozess, der im Compliance-Manager verarbeitet wird.

3. **Name und Gruppe:** Geben Sie einen Namen für Ihre Bewertung in das Feld " **Bewertungs Name** " ein. Die Bewertungs Namen müssen innerhalb von Gruppen eindeutig sein. Wenn der Name der Bewertung mit dem Namen einer anderen Bewertung in einer bestimmten Gruppe übereinstimmt, wird eine Fehlermeldung angezeigt, in der Sie aufgefordert werden, einen anderen Namen zu erstellen.

4. Weisen Sie Ihre Bewertung einer Gruppe zu. Sie können eine der folgenden Aktionen ausführen:
    - Wählen Sie **vorhandene Gruppe verwenden** aus, um Sie einer bereits erstellten Gruppe zuzuweisen. oder
    - Wählen Sie **neue Gruppe erstellen** aus, um eine neue Gruppe zu erstellen und dieser Bewertung zuzuweisen. Bestimmen Sie einen Namen für Ihre Gruppe, und geben Sie ihn in das Feld unterhalb des Optionsfelds ein.

5. **Überprüfen und fertig stellen:** Auf dem letzten Bildschirm des Assistenten werden die Vorlage, der Name und die Gruppe angezeigt, die für die Bewertung ausgewählt wurden. Sie können diese Einstellungen über die Links auf dem Bildschirm bearbeiten, die Sie zurück zu den entsprechenden Schritten im Assistenten führen. Wenn Sie mit den Einstellungen zufrieden sind, wählen Sie **Bewertung erstellen**aus.

6. Auf dem nächsten Bildschirm wird bestätigt, dass Sie Ihren neuen Test erfolgreich erstellt haben. Klicken Sie auf **Fertig** , um den Assistenten zu schließen, und die Seite Details der neuen Bewertung wird auf dem Bildschirm angezeigt.

Wenn auf dem Bildschirm **Bewertung fehlgeschlagen** angezeigt wird, nachdem Sie **Assessment erstellen**ausgewählt haben, wählen Sie **erneut versuchen** aus, um die Bewertung erneut zu erstellen.

## <a name="delete-an-assessment"></a>Löschen einer Bewertung

Wenn Sie einen Test löschen, wird dieser aus der Liste auf der Seite "Bewertungen" entfernt. **Das Löschen einer Bewertung ist dauerhaft; Sie können Sie nicht zurück erhalten.** Wenn Sie die gleiche Bewertung erneut durchsetzen möchten, muss Sie von Grund auf neu erstellt werden. Wenn die Verbesserungs Aktionen in der Bewertung nicht in einer anderen Bewertung angezeigt werden, werden Sie gelöscht, wenn die Bewertung gelöscht wird. Es wird empfohlen, einen Bericht über die Bewertung zu exportieren, bevor Sie ihn endgültig löschen.

Führen Sie die folgenden Schritte aus, um eine Bewertung zu löschen:

1. Wählen Sie auf der Seite "Bewertungen" die Bewertung aus, die Sie löschen möchten, um die Detailseite dieser Bewertung zu öffnen.
2. Wählen Sie in der oberen rechten Ecke des Bildschirms die Option **Bewertung löschen** aus.
3. Ein Fenster wird angezeigt, in dem Sie aufgefordert werden, zu bestätigen, dass der Test endgültig gelöscht werden soll. Wählen Sie **Bewertung löschen** aus, um das Fenster zu schließen. Sie erhalten ein Bestätigungsfenster, dass Ihre Bewertung aus dem Kompatibilitäts Bewertungsergebnis gelöscht wurde.

Wenn Sie die einzige Bewertung in einer Gruppe löschen, wird diese Gruppe auch aus der Kompatibilitätsbewertung gelöscht.

## <a name="monitor-assessment-progress-and-controls"></a>Überwachen des Status der Bewertung und der Steuerelemente

Jede Bewertung verfügt über eine Detailseite, die eine Übersicht über den Fortschritt beim Abschluss der Bewertung bietet. Die Seite zeigt den Fortschritt beim Abschließen von Steuerelementen und den Teststatus von wichtigen Verbesserungs Aktionen innerhalb dieser Steuerelemente.

### <a name="overview-tab"></a>Registerkarte "Übersicht"

Die Registerkarte Übersicht enthält ein Diagramm, in dem Ihr Prozentsatz zum Abschluss der Bewertung angezeigt wird. Dieses Diagramm enthält eine Aufschlüsselung der Punkte aus den Aktionen, die Sie besitzen, und verweist auf Aktionen, die Microsoft gehören, sodass Sie sehen können, wie viele Punkte Sie zum Abschließen der Bewertung benötigen.

Die wichtigsten Verbesserungs Aktionen für Steuerelemente in der Bewertung werden in der Reihenfolge der größten potenziellen Auswirkungen aufgelistet, um Punkte zu sammeln. Das zugeordnete Diagramm enthält Informationen zum aggregierten Teststatus ihrer Verbesserungs Aktionen, sodass Sie schnell abwägen können, was getestet wurde und was noch erledigt werden muss.

Um auf einzelne Verbesserungs Aktionen zuzugreifen, wechseln Sie zur Registerkarte Steuerelemente.

### <a name="controls-tab"></a>Registerkarte "Steuerelemente"

Auf der Registerkarte Steuerelemente werden detaillierte Informationen zu den einzelnen Steuerelementen angezeigt, die der Bewertung zugeordnet sind. Ein **Steuerelementstatus-Aufgliederungs** Diagramm zeigt den Status von Steuerelementen nach Familie an, sodass Sie auf einen Blick sehen können, welche Gruppierungen von Steuerelementen Aufmerksamkeit benötigen.

Unter dem Diagramm werden in einer Tabelle detaillierte Informationen zu den einzelnen Steuerelementen in der Bewertung aufgelistet. Steuerelemente werden nach Steuerelement Familie gruppiert. Erweitern Sie jeden Familiennamen, um die einzelnen Steuerelemente anzuzeigen, die darin enthalten sind. Die für die einzelnen Steuerelemente aufgelisteten Informationen umfassen Folgendes:

- **Steuerelement Titel**
- **Status**: gibt den Teststatus der Verbesserungs Aktionen innerhalb des Steuerelements wieder. 
    - **Übergebene** -alle Verbesserungs Aktionen haben den Teststatus "bestanden" oder mindestens eine wird übergeben, und der Rest ist "außerhalb des Bereichs"
    -  **Fehler** – mindestens eine Verbesserungs Aktion hat den Teststatus "Fehler".
    - **None** : alle Verbesserungs Aktionen wurden nicht getestet
    - **Außerhalb des Bereichs** – alle Verbesserungs Aktionen liegen außerhalb des Bereichs für diese Bewertung
    - **In Progress** -Verbesserungs Aktionen haben einen anderen Status als die oben aufgeführten, was "in Progress", "teilweiser Kredit" oder "unentdeckt" umfassen könnte.
- **Steuerelement-ID**: die Identifikationsnummer des Steuerelements, die durch die entsprechende Regulierung, Standard oder Richtlinie zugewiesen ist
- **Erreichte Punkte**: die Anzahl der Punkte, die durch das Abschließen von Aktionen erzielt wurden, aus der Gesamtzahl der erreichbaren Punkte 
- **Ihre Aktionen**: die Anzahl der ausgeführten Aktionen aus der Gesamtzahl der Aktionen, die ausgeführt werden müssen.
- **Microsoft-Aktionen**: die Anzahl der von Microsoft abgeschlossenen Aktionen 

Wenn Sie die Details eines Steuerelements anzeigen möchten, wählen Sie es aus der Zeile in der Tabelle aus. Die Seite Steuerelement Details zeigt einen Graphen an, der den Teststatus der Aktionen in diesem Steuerelement angibt. Eine Tabelle unterhalb des Diagramms zeigt wichtige Verbesserungs Aktionen für dieses Steuerelement.

Wählen Sie in der Liste eine Verbesserungs Aktion aus, um auf die Detailseite der Verbesserungs Aktion zu bohren. Die Detailseiten zeigen Teststatus, Implementierungshinweise und starten in der empfohlenen Lösung.

#### <a name="learn-more"></a>Weitere Informationen
[Erfahren Sie, wie Steuerelemente und Verbesserungs Aktionen nachverfolgt und durch den Kompatibilitäts Faktor bewertet werden.](compliance-score-methodology.md)

## <a name="export-an-assessment-report"></a>Exportieren eines Bewertungsberichts

Sie können eine Bewertung in eine Excel-Datei für Compliance-Beteiligte in Ihrer Organisation oder für externe Prüfer und Regulierer exportieren, indem Sie [die folgenden Anweisungen befolgen](working-with-compliance-manager.md#reports). Sie müssen den Compliance-Manager besuchen, um den Bericht zu exportieren.

Der Bericht ist eine Momentaufnahme der Bewertung zum Datum und zur Uhrzeit des Exports. Sie enthält die Details für Steuerelemente, die sowohl von Ihnen als auch von Microsoft verwaltet werden, einschließlich Implementierungsstatus, Test Datum, Testergebnisse und Links zu hochgeladenen Beweisdokumenten.
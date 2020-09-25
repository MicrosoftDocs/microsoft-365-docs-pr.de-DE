---
title: Erstellen und Verwalten von Assessments im Microsoft Compliance-Manager
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
description: Erstellen Sie Assessments in Microsoft Compliance Manager, um die Anforderungen von Vorschriften und Zertifizierungen zu erfüllen, die für Ihre Organisation wichtig sind.
ms.openlocfilehash: d09103f58be3a5fa39b57ca35da411e8046aace5
ms.sourcegitcommit: 61d7284b412d0f7bbd8bbb2225c2e6324f86b717
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262290"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Erstellen und Verwalten von Bewertungen im Compliance-Manager

**In diesem Artikel:** In diesem Artikel erfahren Sie, wie Sie den Compliance-Manager für Ihre Organisation anpassen können, indem Sie **Bewertungen**erstellen und verwalten. In diesem Artikel erfahren Sie, wie Sie Assessments erstellen, wie Sie diese in **Gruppen**organisieren, mit **Steuerelementen**arbeiten, **Updates**akzeptieren und Bewertungs **Berichte**exportieren.

> [!IMPORTANT]
> Die für Ihre Organisation verfügbaren Bewertungen hängen von Ihrem Lizenzvertrag ab. Über [prüfen Sie die Details](https://go.microsoft.com/fwlink/?linkid=2132371).

## <a name="introduction-to-assessments"></a>Einführung in Assessments

Compliance-Manager unterstützt Sie bei der Verwaltung der Compliance mit Assessments für die Vorschriften und Zertifizierungen, die für Ihre Organisation gelten. Bei den Bewertungen handelt es sich um Gruppierungen von Steuerelementen aus einer bestimmten Verordnung, Norm oder Richtlinie. Compliance-Manager erleichtert das Nachverfolgen Ihrer Compliance, indem vordefinierte Bewertungen bereitgestellt werden, die eine Vielzahl von Branchen-und regionalen Vorschriften und Zertifizierungen abdecken.

Jede Bewertung wird anhand einer [Bewertungs Vorlage](compliance-manager-templates.md)erstellt. Vorlagen dienen als Framework, in dem die erforderlichen Steuerelemente, Verbesserungs Aktionen und Microsoft-Aktionen für die Abschlussprüfung enthalten sind. Das Einrichten der relevantesten Bewertungen für Ihre Organisation kann Ihnen bei der Implementierung von Richtlinien und Betriebsverfahren helfen, um das Compliance-Risiko einzuschränken.

Alle Ihre Bewertungen werden auf der Seite "Bewertungen" aufgeführt. Erfahren Sie mehr darüber [, wie Sie Ihre Ansicht Ihrer Bewertungen Filtern und Statuszustände interpretieren](compliance-manager-setup.md#assessments-page).

## <a name="data-protection-baseline-default-assessment"></a>Standardbewertung der Datenschutz Basis

Um Ihnen den Einstieg zu erleichtern, bietet Microsoft eine **Standard** Bewertung im Compliance-Manager für die **Microsoft 365-Datenschutz Basis**. Diese grundlegende Bewertung umfasst eine Reihe von Steuerelementen für wichtige Regeln und Standards für den Datenschutz und die allgemeine Datensteuerung. Dieser Basisplan zeichnet Elemente in erster Linie vom NIST-GFK (National Institute of Standards and Technology Cyber Framework) und ISO (International Organization for Standardisierungs) sowie von FedRAMP (Bundes Risiko-und Autorisierungs Management Programm) und dsgvo (allgemeine Datenschutzverordnung der Europäischen Union).

Diese Bewertung wird verwendet, um das anfängliche Kompatibilitäts Ergebnis zu berechnen, wenn Sie den Compliance-Manager zum ersten Mal besuchen, bevor Sie andere Bewertungen konfigurieren. Compliance-Manager sammelt erste Signale von Ihren Microsoft 365-Lösungen. Sie sehen auf einen Blick, wie Ihre Organisation im Verhältnis zu wichtigen Datenschutzstandards und-Vorschriften arbeitet, und wie Sie die vorgeschlagenen Verbesserungsmaßnahmen durchführen.

Compliance-Manager wird bei der Erstellung und Verwaltung eigener Bewertungen zur Erfüllung der besonderen Anforderungen Ihrer Organisation immer hilfreicher.

## <a name="assessment-creation-overview"></a>Übersicht über die Beurteilungs Erstellung

Es gibt drei Möglichkeiten zum Einrichten von Bewertungen:

1. [Verwenden Sie eine vordefinierte Bewertung](#use-a-pre-built-assessment).
2. [Erweitern Sie eine vordefinierte Bewertung entsprechend ihren eigenen Anforderungen](#extend-a-pre-built-assessment).
3. [Erstellen Sie Ihre eigene benutzerdefinierte Bewertung](#create-your-own-custom-assessment).

> [!NOTE]
> Nur Benutzer, die eine globale Administrator-oder Compliance-Manager-Verwaltungsrolle innehaben, können Bewertungen erstellen und ändern. Erfahren Sie mehr über [Rollen und Berechtigungen](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

**Verwenden einer vordefinierten Bewertung**

Kicken Sie Ihre Compliance-Reise, indem Sie eine Bewertung auswählen, die bereits vom Compliance-Manager eingerichtet wurde. Wir bieten eine große Auswahl an [Vorlagen](compliance-manager-templates.md) für Vorschriften und Zertifizierungen, die sich an Branchen, Regionen und gemeinsame Datenschutzstandards wie dsgvo und ISO 27001 ausrichten. Vorlagen enthalten die Steuerelemente und Verbesserungs Aktionen für die Unterstützung bei der Erfüllung der Anforderungen einer bestimmten Zertifizierung. Sie werden aufgefordert, eine Vorlage auszuwählen, wenn Sie mit [dem Erstellen einer Bewertung](#use-a-pre-built-assessment)beginnen.

**Erweitern einer vordefinierten Bewertung entsprechend Ihren Anforderungen**

Sie können eine Konformitäts-Manager-Bewertung – einen Prozess, den wir als "erweitern" bezeichnen – ändern, indem Sie eigene Steuerelemente und Aktionen hinzufügen, um den Anforderungen Ihrer Organisation besser gerecht zu werden. Wenn Sie beispielsweise im allgemeinen HIPAA einhalten müssen, jedoch zusätzliche Datenschutz-oder Sicherheitskontrollen benötigen, können Sie die HIPAA-Vorlage erweitern, indem Sie Ihr eigene Steuerelemente hinzufügen. Weitere Informationen finden Sie in den Anweisungen zum [Erweitern einer vordefinierten Bewertung](#extend-a-pre-built-assessment).

**Erstellen einer eigenen benutzerdefinierten Bewertung**

Sie können eine eigene Bewertung ganz von Grund auf erstellen, um genau nachzuverfolgen, was Ihre Organisation benötigt. Zum Erstellen einer eigenen Bewertung müssen Sie zunächst eine eigene Vorlage für die Bewertung im Compliance-Manager erstellen. Lesen Sie die Anweisungen zum [Erstellen einer eigenen benutzerdefinierten Bewertung](#create-your-own-custom-assessment).

## <a name="understand-groups-before-creating-assessments"></a>Grundlegendes zu Gruppen vor dem Erstellen von Bewertungen

Bevor Sie Assessments erstellen oder ändern, ist es wichtig zu verstehen, wie Gruppen funktionieren. Wenn Sie eine Bewertung erstellen, müssen Sie Sie während des Prozesses einer Gruppe zuweisen. Aus diesem Grund wird empfohlen, vor dem Erstellen von Assessments eine Gruppierungs Strategie für Ihre Bewertungen zu planen.

### <a name="what-are-groups"></a>Was sind Gruppen

Gruppen sind Container, mit denen Sie Bewertungen organisieren können. Sie können Bewertungen auf eine Weise gruppieren, die für Sie logisch ist, beispielsweise nach Jahr oder Regulierung oder basierend auf den Abteilungen oder Geographien Ihrer Organisation. Im folgenden finden Sie Beispiele aus zwei Gruppen und deren zugrunde liegenden Bewertungen:

- **FFIEC ist Assessment 2020**
  - FFIEC ist
- **Sicherheits-und Datenschutz Bewertungen**
  - ISO 27001:2013
  - ISO 27018:2014

Wenn zwei unterschiedliche Bewertungen in der gleichen Gruppe Verbesserungen durchführen, die von Ihnen verwaltet werden, werden alle Aktualisierungen, die Sie an den Implementierungsdetails oder Status einer Aktion vornehmen, automatisch mit derselben Aktion in einer anderen Bewertung in der Gruppe synchronisiert. Mit dieser Synchronisierung können Sie eine Verbesserungs Aktion implementieren und mehrere Anforderungen in mehreren Bestimmungen erfüllen.

### <a name="how-to-create-a-group"></a>Vorgehensweise Erstellen einer Gruppe

Sie erstellen eine Gruppe während des Prozesses zum [Erstellen einer neuen Bewertung](#to-create-an-assessment).

Gruppen können nicht als eigenständige Entitäten erstellt werden. Eine Gruppe muss mindestens eine Bewertung enthalten. Um eine Gruppe zu erstellen, müssen Sie zuerst eine Bewertung erstellen, um Sie in die Gruppe einzufügen.

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

## <a name="use-a-pre-built-assessment"></a>Verwenden einer vordefinierten Bewertung

Es gibt zwei Ausgangspunkte für das Erstellen einer Bewertung aus einer Compliance-Manager-Vorlage.

Sie können den Vorgang auf der Seite "Bewertungen" beginnen, indem Sie die Schaltfläche " **Bewertung hinzufügen** " auswählen und dann den Assistenten zum Erstellen von Tests verwenden. Die Schritte für diesen Prozess finden Sie weiter unten.

Sie können auch auf der Seite mit den Bewertungs Vorlagen beginnen, indem Sie die gewünschte Vorlage suchen und Sie in der Liste auswählen, um auf der Detailseite anzukommen. Wählen Sie auf der Seite Vorlagen Details die Option **Bewertung erstellen**aus. Anschließend geben Sie den Assistenten ein, damit Ihre Vorlage bereits ausgewählt ist.

### <a name="to-create-an-assessment"></a>So erstellen Sie eine Bewertung

1. Kennen Sie die Gruppe, der Sie Ihre Bewertung zuweisen möchten, oder bereiten Sie sich darauf vor, für diese Bewertung einen neuen zu erstellen. [Erfahren Sie mehr über Gruppen](#understand-groups-before-creating-assessments).  

2. Wechseln Sie zur Seite **Assessments** im Compliance-Manager, und wählen Sie **Bewertung hinzufügen**aus. Ein Bewertungs-Assistent wird in einem großen Flyout-Bereich angezeigt.

3. **Wählen Sie eine Vorlage**aus: Wählen Sie eine Vorlage aus, die als Grundlage für Ihre Bewertung dient. Wählen Sie das Optionsfeld neben der ausgewählten Vorlage aus, und wählen Sie dann **weiter**aus.

4. **Name und Gruppe:** Geben Sie einen Namen für Ihre Bewertung in das Feld " **Bewertungs Name** " ein. Die Bewertungs Namen müssen innerhalb von Gruppen eindeutig sein. Wenn der Name der Bewertung mit dem Namen einer anderen Bewertung in einer bestimmten Gruppe übereinstimmt, wird eine Fehlermeldung angezeigt, in der Sie aufgefordert werden, einen anderen Namen zu erstellen.

5. Weisen Sie Ihre Bewertung einer Gruppe zu. Sie können eine der folgenden Aktionen ausführen:
    - Wählen Sie **vorhandene Gruppe verwenden** aus, um Sie einer bereits erstellten Gruppe zuzuweisen. oder
    - Wählen Sie **neue Gruppe erstellen** aus, um eine neue Gruppe zu erstellen und dieser Bewertung zuzuweisen:
        - Bestimmen Sie einen Namen für Ihre Gruppe, und geben Sie ihn in das Feld unterhalb des Optionsfelds ein.
        - Sie können **Daten aus einer vorhandenen Gruppe**wie Implementierungs-und Testdetails und Dokumente kopieren, indem Sie die entsprechenden Felder auswählen.

    Wenn Sie fertig sind, wählen Sie **weiter**aus.

6. **Überprüfen und fertig stellen:** Auf dem letzten Bildschirm des Assistenten werden die Vorlage, der Name und die Gruppe angezeigt, die für die Bewertung ausgewählt wurden. Sie können diese Einstellungen über die Links auf dem Bildschirm bearbeiten, die Sie zurück zu den entsprechenden Schritten im Assistenten führen. Wenn Sie fertig sind, wählen Sie **Bewertung erstellen**aus.

7. Auf dem nächsten Bildschirm wird bestätigt, dass Sie Ihren neuen Test erfolgreich erstellt haben. Klicken Sie auf **Fertig** , um den Assistenten zu schließen, und die Seite Details der neuen Bewertung wird auf dem Bildschirm angezeigt.

Wenn auf dem Bildschirm **Bewertung fehlgeschlagen** angezeigt wird, nachdem Sie **Assessment erstellen**ausgewählt haben, wählen Sie **erneut versuchen** aus, um die Bewertung erneut zu erstellen.

Sie können den Namen der Bewertung nach dem Erstellen ändern, indem Sie in der rechten oberen Ecke der [Detailseite des Assessments](#monitor-assessment-progress-and-controls)auf die Schaltfläche **Namen bearbeiten** klicken.

## <a name="extend-a-pre-built-assessment"></a>Erweitern einer vordefinierten Bewertung

Sie können eine vordefinierte Bewertung ändern, indem Sie Ihre eigenen Steuerelemente und Verbesserungs Aktionen zur Vorlage der Bewertung hinzufügen. Dieser Vorgang wird als "Erweitern einer Microsoft-Vorlage" im Compliance-Manager bezeichnet. Wenn Sie die Vorlage einer Bewertung erweitern, erhält Sie alle von Microsoft veröffentlichten Updates, was passieren kann, wenn Änderungen an der entsprechenden Verordnung oder dem betreffenden Produkt vorgenommen werden (siehe [akzeptieren von Updates für Bewertungen](#accepting-updates-to-assessments)).

Sie führen diesen Vorgang aus, indem Sie auf der Seite mit den **Bewertungs Vorlagen** statt auf der Seite mit den **Bewertungen** beginnen.

**Bevor Sie beginnen:**

Um diesen Prozess vorzubereiten, müssen Sie zunächst eine speziell formatierte Excel-Arbeitsmappe zusammenstellen, um die erforderlichen Vorlagendaten zu importieren. Es gibt spezielle Anforderungen für die [formatierten Excel-Dateien](compliance-manager-templates.md#formatting-your-template-data-with-excel) , die im Erweiterungsprozess verwendet werden. Lesen Sie diese zusätzlichen Punkte, um Fehler im Importprozess zu verhindern:

- Ihre Tabelle sollte nur die Aktionen und Steuerelemente enthalten, die Sie der Bewertung hinzufügen möchten. 
- Das Arbeitsblatt kann keine der Steuerelemente oder Aktionen enthalten, die bereits in der Bewertung vorhanden sind, die Sie ändern möchten.
- Betrachten Sie auch "Erweiterung" in den Titel Ihrer Vorlage, beispielsweise "dsgvo – [Name Ihres Unternehmens]". Dies erleichtert die Identifizierung in der Liste auf der Seite " **Bewertungs Vorlagen** " im Gegensatz zur von Microsoft bereitgestellten Standardvorlage oder einer benutzerdefinierten Vorlage mit einem ähnlichen Namen.

Führen Sie nach dem Formatieren des Arbeitsblatts die folgenden Schritte aus.

**Schritte zum Erweitern einer Compliance-Manager-Vorlage**

1. Wechseln Sie zur Seite **Bewertungs Vorlagen** , und wählen Sie **neue Vorlage erstellen**aus. Ein Vorlagen Erstellungs-Assistent wird geöffnet.

2. Wählen Sie den Typ der Vorlage aus, die Sie erstellen möchten. Wählen Sie in diesem Fall **Microsoft-Vorlage erweitern**aus, und **Wählen Sie dann aus**.

3. Auf der rechten Seite des Bildschirms wird ein Flyout-Fensterausschnitt Vorlagenauswahl angezeigt. Verwenden der **Suche** zum Anwenden von Filtern zum Auffinden der gewünschten Vorlage

4. Nachdem Sie Ihre Vorlage gefunden haben, wählen Sie das Optionsfeld links neben dem Namen aus, und wählen Sie dann **Speichern**aus.

5. Auf dem nächsten Bildschirm wird die ausgewählte Vorlage angezeigt. Wenn zutreffend, wählen Sie **weiter**aus. (Falls falsch, wählen Sie **eine andere Vorlage auswählen** aus, um Sie erneut auszuwählen.)

6. Wählen Sie auf dem Bildschirm **Datei hochladen** die Option **Durchsuchen** aus, um die formatierte Excel-Datei zu suchen und hochzuladen, die alle erforderlichen Vorlagendaten enthält.

7. Wenn keine Probleme mit Ihrer Datei auftreten, zeigt der nächste Bildschirm den Namen der hochgeladenen Datei an. Wählen Sie **weiter** aus, um den Vorgang fortzusetzen (wenn Sie die Datei ändern müssen, wählen Sie **Hochladen einer anderen Datei**aus).

    - Wenn ein Problem mit Ihrer Datei vorliegt, wird in einer Fehlermeldung am oberen Rand erläutert, was falsch ist. Sie müssen die Datei korrigieren und erneut hochladen. Wenn Ihr Arbeitsblatt nicht ordnungsgemäß formatiert ist oder wenn ungültige Informationen in bestimmten Feldern vorhanden sind, treten Fehler auf.
 
8. Auf dem Bildschirm **überprüfen und beenden** werden die Anzahl der Verbesserungs Aktionen und-Steuerelemente sowie die maximale Punktzahl für die Vorlage angezeigt. Wenn Sie zur Genehmigung berechtigt sind, wählen Sie **weiter**aus. (Wenn Sie Änderungen vornehmen müssen, wählen Sie **Hochladen einer anderen Datei**aus.)

9. Auf dem letzten Bildschirm wird bestätigt, dass eine neue Vorlage erstellt wurde. Wählen Sie **Fertig** aus, um den Assistenten zu beenden.

10. Sie gelangen auf die Detailseite ihrer neuen Vorlage. Von hier aus können Sie Ihre Bewertung erstellen, indem Sie **Bewertung erstellen**auswählen. Um Anleitungen zu erhalten, beginnen Sie mit Schritt #4 in den [oben beschriebenen Anweisungen zur Erstellung der Bewertung](#to-create-an-assessment).

## <a name="create-your-own-custom-assessment"></a>Erstellen einer eigenen benutzerdefinierten Bewertung

Zum Erstellen einer benutzerdefinierten Bewertung im Compliance-Manager müssen Sie eine eigene Vorlage erstellen. Um eine eigene Vorlage zu erstellen, müssen Sie zuerst eine formatierte Excel-Arbeitsmappe zusammenstellen, um die erforderlichen Vorlagendaten zu importieren. Es hilft auch, im Voraus zu entscheiden, welcher Gruppe Sie Ihre Bewertung zuweisen, wenn Sie Sie erstellen (Weitere Informationen zu [Gruppen](#what-are-groups)).

**Führen Sie die folgenden Schritte aus, um die benutzerdefinierte Bewertung zu erstellen:**

1. **Formatieren Sie die Excel-Datei.** Beginnen Sie mit der Formatierung Ihrer Vorlagendaten in einer Excel-Tabelle mithilfe [dieser Anweisungen](compliance-manager-templates.md#formatting-your-template-data-with-excel).

2. **Erstellen Sie Ihre Vorlage** , indem Sie [diese Anweisungen](compliance-manager-templates.md#create-a-new-template)befolgen.

3. **Erstellen Sie Ihre Bewertung** anhand der Vorlage. Sie können zunächst die Detailseite der Vorlage öffnen und " **Bewertung erstellen**" auswählen, oder zur Seite " **Bewertungen** " wechseln und " **Bewertung erstellen**" auswählen.

4. Ein Assistent zum Erstellen von Tests wird in einem großen Flyout-Bereich angezeigt. Von hier aus können Sie den Anweisungen unter Verwendung der neuen benutzerdefinierten Vorlage für die Bewertung folgen, die mit Schritt #3 der [Anweisungen zur Erstellung der Bewertung](#to-create-an-assessment)beginnen.

## <a name="delete-an-assessment"></a>Löschen einer Bewertung

Wenn Sie einen Test löschen, wird dieser aus der Liste auf der Seite "Bewertungen" entfernt. Beachten Sie die folgenden wichtigen Punkte zum Löschen von Bewertungen:

- **Das Löschen einer Bewertung ist dauerhaft; Sie können Sie nicht zurück erhalten.** Wenn Sie die gleiche Bewertung erneut verwenden möchten, müssen Sie Sie neu erstellen.
- Wenn die Verbesserungs Aktionen in der Bewertung nicht in einer anderen Bewertung angezeigt werden, werden Sie gelöscht, wenn die Bewertung gelöscht wird.
- Es wird empfohlen, [einen Bericht](#export-an-assessment-report) über die Bewertung zu exportieren, bevor Sie ihn endgültig löschen.

Führen Sie die folgenden Schritte aus, um eine Bewertung zu löschen:

1. Wählen Sie auf der Seite " **Bewertungen** " die Bewertung aus, die Sie löschen möchten, um die Detailseite dieser Bewertung zu öffnen.

2. Wählen Sie in der oberen rechten Ecke des Bildschirms die Option **Bewertung löschen** aus.

3. Ein Fenster wird angezeigt, in dem Sie aufgefordert werden, zu bestätigen, dass der Test endgültig gelöscht werden soll. Wählen Sie **Bewertung löschen** aus, um das Fenster zu schließen. Sie erhalten ein Bestätigungsfenster, dass Ihre Bewertung aus dem Compliance-Manager gelöscht wurde.

Wenn Sie die einzige Bewertung in einer Gruppe löschen, wird diese Gruppe auch aus dem Compliance-Manager gelöscht.

> [!NOTE]
> Alle Ihre Bewertungen können nicht gelöscht werden. Organisationen benötigen mindestens eine Bewertung, damit Compliance-Manager ordnungsgemäß funktioniert. Wenn die Bewertung, die Sie löschen möchten, die einzige ist, fügen Sie eine weitere Bewertung hinzu, bevor Sie die andere Bewertung löschen.

## <a name="monitor-assessment-progress-and-controls"></a>Überwachen des Status der Bewertung und der Steuerelemente

Jede Bewertung verfügt über eine Detailseite, die eine Übersicht über den Fortschritt beim Abschluss der Bewertung bietet. Die Seite zeigt den Fortschritt beim Abschließen von Steuerelementen und den Teststatus von wichtigen Verbesserungs Aktionen innerhalb dieser Steuerelemente.

### <a name="overview-tab"></a>Registerkarte "Übersicht"

Die Registerkarte Übersicht enthält ein Diagramm, in dem Ihr Prozentsatz zum Abschluss der Bewertung angezeigt wird. Dieses Diagramm enthält eine Aufschlüsselung der Punkte aus den Aktionen, die Sie besitzen, und verweist auf Aktionen, die Microsoft gehören, sodass Sie sehen können, wie viele Punkte Sie zum Abschließen der Bewertung benötigen.

Die wichtigsten Verbesserungs Aktionen für Steuerelemente in der Bewertung werden in der Reihenfolge der größten potenziellen Auswirkungen aufgelistet, um Punkte zu sammeln. Das zugeordnete Diagramm enthält Informationen zum aggregierten Teststatus ihrer Verbesserungs Aktionen, sodass Sie schnell abwägen können, was getestet wurde und was noch erledigt werden muss.

Um auf einzelne Verbesserungs Aktionen zuzugreifen, besuchen Sie die Registerkarte **Steuerelemente** oder die Registerkarte **Ihre Verbesserungs Aktionen** .

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

### <a name="your-improvement-actions-tab"></a>Registerkarte "Verbesserungs Aktionen"

Die Registerkarte für Ihre Verbesserungs Aktionen listet alle Steuerelemente in der Bewertung auf, die von Ihrer Organisation verwaltet werden. In der Statusleiste wird der aggregierte Teststatus ihrer Verbesserungs Aktionen in der Bewertung näher erläutert, sodass Sie schnell abwägen können, was getestet wurde und was noch erledigt werden muss. Unter der Leiste finden Sie eine vollständige Liste der Verbesserungs Aktionen und der wichtigsten Details, einschließlich: Teststatus, die Anzahl der potenziellen und gesammelten Punkte, die zugehörigen Verordnungen und Standards, die jeweilige Lösung, den Aktionstyp und die Kontroll Familie. Erfahren Sie mehr darüber [, wie Aktionen zur Konformitätsbewertung beitragen](compliance-score-calculation.md#action-types-and-points).

Wählen Sie eine Verbesserungs Aktion aus, um die zugehörige Detailseite anzuzeigen, und wählen Sie den Link **jetzt starten** aus, um die Lösung zu öffnen, um Maßnahmen zu ergreifen.

### <a name="microsoft-actions-tab"></a>Registerkarte "Microsoft-Aktionen"

Auf der Registerkarte Microsoft-Aktionen werden alle Aktionen in der Bewertung aufgeführt, die von Microsoft verwaltet werden. Die Liste enthält wichtige Aktionsdetails, einschließlich: Teststatus, Punkte, die zu Ihrem allgemeinen Konformitäts Bewertungsergebnis, zu den zugehörigen Vorschriften und Standards, zur jeweiligen Lösung, zum Aktionstyp und zur Steuerelement Familie beitragen. Wählen Sie eine Verbesserungs Aktion aus, um die zugehörige Detailseite anzuzeigen.

Erfahren Sie mehr darüber [, wie Steuerelemente und Verbesserungs Aktionen nachverfolgt und bewertet werden.](compliance-score-calculation.md)

## <a name="accepting-updates-to-assessments"></a>Akzeptieren von Updates für Bewertungen

Wenn ein Update für eine Bewertung zur Verfügung steht, wird eine Benachrichtigung angezeigt, und Sie haben die Möglichkeit, das Update zu akzeptieren oder zu einem späteren Zeitpunkt zu verschieben.

### <a name="what-causes-an-update"></a>Was bewirkt, dass ein Update

Eine Bewertungs Aktualisierung tritt auf, wenn zugrunde liegende Vorlagenänderungen auftreten, die sich auf die Bewertung auswirken. Änderungen umfassen möglicherweise die Anpassung der Steuerungs Zuordnung oder andere Anleitungen basierend auf regulatorischen Änderungen oder Produktänderungen. Bewertungs Aktualisierungen können aus Ihrer Organisation stammen (beispielsweise, wenn eine [benutzerdefinierte Vorlage geändert wird](compliance-manager-templates.md#modify-a-template)) sowie von Microsoft.

Wenn Microsoft eine von Ihnen erweiterte Compliance-Manager-Vorlage aktualisiert, erbt ihr Assessment diese Updates, sobald Sie Sie akzeptieren. Bei der Bewertung werden die zusätzlichen Attribute beibehalten, die Sie beim Erweitern auf die Bewertung angewendet haben.

Für benutzerdefinierte Bewertungen, die Sie erstellen, werden keine Vorlagen Updates von Microsoft empfangen. Benutzerdefinierte Bewertungen können Aktualisierungen für Verbesserungs Aktionen erhalten, aber alle Microsoft-Updates zur Steuerung der Zuordnung zwischen Beurteilungen und Verbesserungs Aktionen gelten nicht für benutzerdefinierte Vorlagen.

> [!NOTE]
> Updates für Bewertungen gelten nur auf Gruppenebene. Wenn Sie zwei Bewertungen aus derselben Vorlage erstellt haben, die in zwei verschiedenen Gruppen vorhanden sind, wird für jede Bewertung eine Update Benachrichtigung ausstehen, und Sie müssen die Aktualisierung für jede Bewertung in der jeweiligen Gruppe einzeln akzeptieren.

#### <a name="where-youll-see-assessment-update-notifications"></a>Wo Sie Benachrichtigungen über Bewertungs Updates sehen

Auf der Seite mit den Bewertungsdetails wird auch eine **ausstehende Update** Bezeichnung neben der Bewertung mit einem Update angezeigt. Wählen Sie diese Bewertung aus, um zur Detailseite zu gelangen.

Eine Nachricht im oberen Bereich der Seite mit den Bewertungsdetails zeigt, dass für diese Bewertung ein Update verfügbar ist. Wählen Sie die Schaltfläche **Update überprüfen** im Banner aus, um die spezifischen Änderungen zu überprüfen und das Update zu akzeptieren oder zu verschieben.

Auf der Seite mit den Bewertungsdetails werden möglicherweise auch Verbesserungs Aktionen aufgelistet, bei denen eine **Update Bezeichnung aussteht** . Diese Updates gelten für spezifische Änderungen an den Verbesserungs Aktionen selbst und müssen separat akzeptiert werden. Weitere Informationen finden Sie unter [akzeptieren von Updates für Verbesserungs Aktionen](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) .

#### <a name="review-update-to-accept-or-defer"></a>Überprüfen der Aktualisierung zur Annahme oder Verschiebung

Nachdem Sie auf der Seite mit den Bewertungsdetails die Option **Update überprüfen** ausgewählt haben, wird auf der rechten Seite des Bildschirms ein Flyout-Bereich angezeigt. Der Flyout-Bereich enthält die wichtigsten Details zu der ausstehenden Aktualisierung:

- Der Vorlagentitel
- Quelle des Updates (Microsoft, Ihre Organisation oder ein bestimmter Benutzer)
- Das Datum, an dem die Aktualisierung erstellt wurde
- Eine Übersicht über das Update
- Spezifische Details zu den Änderungen, einschließlich der Auswirkungen auf die Konformitätsbewertung, die Höhe des Fortschritts bis zum Abschluss der Bewertung und die spezifische Anzahl von Änderungen an Verbesserungs Aktionen und-Steuerelementen.

Durch Auswahl des **aktualisierten Vorlagen** Links wird eine Excel-Datei heruntergeladen, die Steuerelementdaten für die Version der Vorlage mit den ausstehenden Updates enthält. Durch Auswahl des **aktuellen Vorlagen** Links wird eine Datei der vorhandenen Vorlage ohne die Änderungen heruntergeladen.

Um das Update anzunehmen und die Änderungen an ihrer Bewertung vorzunehmen, wählen Sie **Update akzeptieren**aus. Akzeptierte Änderungen sind dauerhaft.

Wenn Sie **Abbrechen**auswählen, wird das Update nicht auf die Bewertung angewendet. Die Benachrichtigung über **ausstehende Updates** wird jedoch weiterhin angezeigt, bis Sie das Update akzeptieren.

**Warum wird empfohlen, Updates zu akzeptieren?**

Durch das akzeptieren von Updates können Sie sicherstellen, dass Sie über die neuesten Anleitungen zur Verwendung von Lösungen und geeignete Verbesserungsmaßnahmen verfügen, die Ihnen helfen, die Anforderungen der Zertifizierung zur Hand zu erfüllen.

**Warum Sie ein Update möglicherweise verschieben möchten**

Wenn Sie mitten in einer Bewertung sind, sollten Sie sicherstellen, dass Sie die Arbeit daran abgeschlossen haben, bevor Sie eine Aktualisierung der Bewertung akzeptieren, die die Steuerung der Zuordnung stören könnte. Sie können das Update zu einem späteren Zeitpunkt verschieben, indem Sie im Flyout-Bereich Update aktualisieren die Option **Abbrechen** auswählen.

## <a name="export-an-assessment-report"></a>Exportieren eines Bewertungsberichts

Sie können eine Bewertung in eine Excel-Datei für Compliance-Beteiligte in Ihrer Organisation oder für externe Prüfer und Regulierer exportieren. Wählen Sie auf der Seite mit den Bewertungsdetails die Schaltfläche **Bericht generieren** oben auf der Seite aus, um eine Excel-Datei zu erstellen, die Sie speichern und freigeben können.

Der Bericht ist eine Momentaufnahme der Bewertung zum Datum und zur Uhrzeit des Exports. Sie enthält die Details für Steuerelemente, die sowohl von Ihnen als auch von Microsoft verwaltet werden, einschließlich Implementierungsstatus, Test Datum und Testergebnisse.
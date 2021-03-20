---
title: Erstellen und Verwalten von Bewertungen im Microsoft Compliance Manager
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
description: Erstellen Sie Bewertungen im Microsoft Compliance Manager, um Ihnen zu helfen, die Anforderungen von Vorschriften und Zertifizierungen zu erfüllen, die für Ihre Organisation wichtig sind.
ms.openlocfilehash: ff2aa41b91f3cb019dbed542c422d61c79c4ecb5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908595"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Erstellen und Verwalten von Bewertungen im Compliance Manager

**In diesem Artikel:** Erfahren Sie, wie Sie Compliance Manager für Ihre Organisation anpassen, indem Sie Bewertungen erstellen und **verwalten.** In diesem Artikel erfahren Sie, wie Sie Bewertungen erstellen, sie  **in** Gruppen organisieren, mit Steuerelementen **arbeiten,** Updates akzeptieren und Bewertungsberichte **exportieren.**

> [!IMPORTANT]
> Die für Ihre Organisation verfügbaren Bewertungen hängen von Ihrem Lizenzvertrag ab. [Überprüfen Sie die Details](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="introduction-to-assessments"></a>Einführung in Bewertungen

Der Compliance-Manager hilft Ihnen, die Einhaltung von Bewertungen für die für Ihre Organisation geltenden Vorschriften und Zertifizierungen zu verwalten. Bewertungen sind Gruppierungen von Steuerelementen aus einer bestimmten Verordnung, einem Standard oder einer Bestimmten Richtlinie. Der Compliance-Manager erleichtert die Nachverfolgung Ihrer Compliance, indem er vordefinierte Bewertungen für eine Vielzahl von branchen- und regionalen Vorschriften und Zertifizierungen bietet.

Jede Bewertung wird aus einer [Bewertungsvorlage erstellt.](compliance-manager-templates.md) Vorlagen dienen als Framework, das die erforderlichen Steuerelemente, Verbesserungsmaßnahmen und Microsoft-Aktionen zum Abschließen der Bewertung enthält. Das Einrichten der relevantesten Bewertungen für Ihre Organisation hilft Ihnen bei der Implementierung von Richtlinien und operativen Verfahren, um Ihr Compliancerisiko zu begrenzen.

Alle Bewertungen sind auf der Bewertungsseite aufgeführt. Erfahren Sie mehr darüber, wie Sie Ihre Ansicht Ihrer Bewertungen filtern und [Statuszustände interpretieren.](compliance-manager-setup.md#assessments-page)

## <a name="data-protection-baseline-default-assessment"></a>Standardbewertung des Datenschutzgrundwerts

Als Einstieg bietet Microsoft  eine Standardbewertung im Compliance Manager für die **Microsoft 365 Data Protection Baseline an.** Diese Basisbewertung enthält eine Reihe von Kontrollen für wichtige Vorschriften und Standards für den Datenschutz und die allgemeine Datenkontrolle. Diese Basislinie bezieht elemente hauptsächlich aus NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) und ISO (International Organization for Standardization), sowie aus FedRAMP (Federal Risk and Authorization Management Program) und DSGVO (General Data Protection Regulation of the European Union).

Diese Bewertung wird verwendet, um Ihre anfängliche Compliancebewertung zu berechnen, wenn Sie das erste Mal im Compliance Manager sind, bevor Sie andere Bewertungen konfigurieren. Compliance Manager sammelt erste Signale von Ihren Microsoft 365-Lösungen. Sie sehen auf einen Blick, wie Ihre Organisation im Vergleich zu wichtigen Datenschutzstandards und -vorschriften funktioniert, und sehen sich verbesserungswürdige Maßnahmen an.

Compliance Manager wird hilfreicher, wenn Sie Ihre eigenen Bewertungen erstellen und verwalten, um die speziellen Anforderungen Ihrer Organisation zu erfüllen.

## <a name="assessment-creation-overview"></a>Übersicht über die Bewertungserstellung

Es gibt drei Möglichkeiten zum Einrichten von Bewertungen:

1. [Verwenden Sie eine vordefinierte Bewertung](#use-a-pre-built-assessment).
2. [Erweitern Sie eine vordefinierte Bewertung entsprechend Ihren eigenen Anforderungen.](#extend-a-pre-built-assessment)
3. [Erstellen Sie Ihre eigene benutzerdefinierte Bewertung](#create-your-own-custom-assessment).

> [!NOTE]
> Nur Benutzer, die eine Rolle als globaler Administrator oder Compliance-Manager haben, können Bewertungen erstellen und ändern. Erfahren Sie mehr über [Rollen und Berechtigungen](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

**Verwenden einer vordefinierten Bewertung**

Starten Sie Ihren Compliance-Weg, indem Sie eine bewertung auswählen, die bereits vom Compliance Manager eingerichtet wurde. Wir bieten eine [](compliance-manager-templates.md) breite Auswahl an Vorlagen für Vorschriften und Zertifizierungen, die an Branchen, Regionen und gemeinsamen Datenschutzstandards wie DSGVO und ISO 27001 ausgerichtet sind. Vorlagen enthalten die Steuerelemente und Verbesserungsmaßnahmen, mit deren Hilfe Sie die Anforderungen einer bestimmten Zertifizierung erfüllen können. Sie werden aufgefordert, eine Vorlage zu wählen, wenn Sie mit dem [Erstellen einer Bewertung beginnen.](#use-a-pre-built-assessment)

**Erweitern einer vordefinierten Bewertung für Ihre Anforderungen**

Sie können eine Compliance-Manager-Bewertung – einen Prozess, den wir als "erweitern" bezeichnen – ändern, indem Sie Eigene Steuerelemente und Aktionen hinzufügen, um die Anforderungen Ihrer Organisation besser zu erfüllen. Wenn Sie z. B. HIPAA im Allgemeinen einhalten müssen, aber zusätzliche Datenschutz- oder Sicherheitskontrollen benötigen, können Sie unsere HIPAA-Vorlage erweitern, indem Sie ihr eigene Steuerelemente hinzufügen. Weitere Informationen finden Sie in [den Anweisungen zum Erweitern einer vordefinierten Bewertung.](#extend-a-pre-built-assessment)

**Erstellen Einer eigenen benutzerdefinierten Bewertung**

Sie können Ihre eigene Bewertung vollständig neu erstellen, um genau zu verfolgen, was Ihre Organisation benötigt. Wenn Sie Eine eigene Bewertung erstellen, müssen Sie zunächst eine eigene Vorlage für die Bewertung im Compliance-Manager erstellen. Weitere Informationen finden Sie in [den Anweisungen zum Erstellen Ihrer eigenen benutzerdefinierten Bewertung.](#create-your-own-custom-assessment)

## <a name="understand-groups-before-creating-assessments"></a>Verstehen von Gruppen vor dem Erstellen von Bewertungen

Bevor Sie Bewertungen erstellen oder ändern, müssen Sie wissen, wie Gruppen funktionieren. Wenn Sie eine Bewertung erstellen, müssen Sie sie während des Prozesses einer Gruppe zuweisen. Aus diesem Grund wird empfohlen, eine Gruppierungsstrategie für Ihre Bewertungen zu planen, bevor Sie Bewertungen erstellen.

### <a name="what-are-groups"></a>Was sind Gruppen?

Gruppen sind Container, mit denen Sie Bewertungen organisieren können. Sie können Bewertungen auf eine Für Sie logische Weise gruppieren, z. B. nach Jahr oder Verordnung oder basierend auf den Abteilungen oder Regionen Ihrer Organisation. Nachfolgend finden Sie Beispiele für zwei Gruppen und deren zugrunde liegende Bewertungen:

- **FFIEC IS Assessment 2020**
  - FFIEC IS
- **Datensicherheits- und Datenschutzbewertungen**
  - ISO 27001:2013
  - ISO 27018:2014

Wenn zwei unterschiedliche Bewertungen in derselben Gruppe Von Ihnen verwaltete Verbesserungsmaßnahmen freigeben, werden alle Aktualisierungen, die Sie an den Implementierungsdetails oder dem Status einer Aktion vornehmen, automatisch mit derselben Aktion in jeder anderen Bewertung in der Gruppe synchronisiert. Mit dieser Synchronisierung können Sie eine Verbesserungsaktion implementieren und mehrere Anforderungen in mehreren Vorschriften erfüllen.

### <a name="how-to-create-a-group"></a>Erstellen einer Gruppe

Sie erstellen während des Erstellens einer neuen Bewertung [eine Gruppe.](#to-create-an-assessment)

Gruppen können nicht als eigenständige Entitäten erstellt werden. Eine Gruppe muss mindestens eine Bewertung enthalten. Zum Erstellen einer Gruppe müssen Sie zunächst eine Bewertung erstellen, die in der Gruppe erstellt werden soll.

### <a name="what-to-know-when-working-with-groups"></a>Wissen bei der Arbeit mit Gruppen

- Gruppennamen müssen innerhalb Ihrer Organisation eindeutig sein.
- Gruppen verfügen nicht über Sicherheitseigenschaften. Alle Berechtigungen sind Bewertungen zugeordnet.
- Nachdem Sie einer Gruppe eine Bewertung hinzugefügt haben, kann die Gruppierung nicht mehr geändert werden.
- Verwandte Bewertungssteuerelemente in unterschiedlichen Bewertungen innerhalb derselben Gruppe werden nach Abschluss automatisch aktualisiert.
- Wenn Sie einer vorhandenen Gruppe eine neue Bewertung hinzufügen, werden allgemeine Informationen aus Bewertungen in dieser Gruppe in die neue Bewertung kopiert.
- Gruppen können Bewertungen für dieselbe Zertifizierung oder Verordnung enthalten, aber jede Gruppe kann nur eine Bewertung für ein bestimmtes Produktzertifizierungspaar enthalten. Beispielsweise kann eine Gruppe keine zwei Bewertungen für Office 365 und NIST CSF enthalten. Eine Gruppe kann mehrere Bewertungen für dasselbe Produkt nur enthalten, wenn die entsprechende Zertifizierung oder Vorschrift für jedes Produkt unterschiedlich ist.
- Das Löschen einer Bewertung bricht die Beziehung zwischen dieser Bewertung und der Gruppe.
- Gruppen können nicht gelöscht werden.
- Wenn eine Änderung an einer Verbesserung vorgenommen wird, die in mehreren Gruppen angezeigt wird, wird diese Änderung in allen Instanzen dieser Verbesserungsaktion widerspiegelt.

## <a name="use-a-pre-built-assessment"></a>Verwenden einer vordefinierten Bewertung

Es gibt zwei Ausgangspunkte für das Erstellen einer Bewertung aus einer Compliance-Manager-Vorlage.

Sie können den Prozess von Ihrer Bewertungsseite aus beginnen, indem Sie die Schaltfläche Bewertung hinzufügen **auswählen** und dann den Assistenten zum Erstellen von Bewertungen durchgehen. Die Schritte für diesen Prozess sind unten aufgeführt.

Sie können auch von ihrer Bewertungsvorlagenseite aus beginnen, indem Sie die vorlage suchen, die Sie möchten, und sie aus der Liste auswählen, um zur Detailseite zu gelangen. Wählen Sie auf der Seite Vorlagendetails die Option **Bewertung erstellen aus.** Anschließend geben Sie den Assistenten mit der bereits ausgewählten Vorlage ein.

### <a name="to-create-an-assessment"></a>So erstellen Sie eine Bewertung

1. Wissen Sie, welcher Gruppe Sie Ihre Bewertung zuweisen, oder bereit sein, eine neue Gruppe für diese Bewertung zu erstellen. [Erfahren Sie mehr über Gruppen](#understand-groups-before-creating-assessments).  

2. Wechseln Sie zu Ihrer **Bewertungsseite** im Compliance-Manager, und wählen **Sie Bewertung hinzufügen aus.** Ein Bewertungs-Assistent wird in einem großen Flyoutbereich angezeigt.

3. **Vorlage auswählen:** Wählen Sie eine Vorlage aus, die als Grundlage für Ihre Bewertung dienen soll. Sie sehen die Liste der Vorlagen, die in enthaltene und Premium-Kategorien unterteilt sind (weitere Informationen finden Sie unter [Vorlagentypen).](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) Wählen Sie das Optionsfeld neben der ausgewählten Vorlage aus, und wählen Sie dann **Weiter aus.**

4. **Name und Gruppe:** Geben Sie im Feld Bewertungsname einen Namen **für Ihre Bewertung** ein. Bewertungsnamen müssen innerhalb von Gruppen eindeutig sein. Wenn der Name Ihrer Bewertung dem Namen einer anderen Bewertung in einer bestimmten Gruppe entspricht, wird eine Fehlermeldung angezeigt, in der Sie aufgefordert werden, einen anderen Namen zu erstellen.

5. Weisen Sie Ihre Bewertung einer Gruppe zu. Sie können eine der folgenden Aktionen ausführen:
    - Wählen **Sie Vorhandene Gruppe verwenden aus,** um sie einer bereits erstellten Gruppe zuzuordnen. oder
    - Wählen **Sie Neue Gruppe erstellen aus,** um eine neue Gruppe zu erstellen, und weisen Sie ihr diese Bewertung zu:
        - Bestimmen Sie einen Namen für Ihre Gruppe, und geben Sie ihn in das Feld unter dem Optionsfeld ein.
        - Sie können **Daten aus einer vorhandenen** Gruppe kopieren, z. B. Implementierungs- und Testdetails und Dokumente, indem Sie die entsprechenden Felder auswählen.

    Wenn Sie fertig sind, wählen Sie **Weiter** aus.

6. **Überprüfen und Fertig stellen:** Der letzte Bildschirm des Assistenten zeigt die Vorlage, den Namen und die Gruppe an, die für die Bewertung ausgewählt wurden. Sie können alle diese Einstellungen über die Links auf dem Bildschirm bearbeiten, die Sie zu den relevanten Schritten im Assistenten zurückverdienen. Wenn Sie bereit sind, wählen Sie Bewertung **erstellen aus.**

7. Der nächste Bildschirm bestätigt, dass Sie Ihre neue Bewertung erfolgreich erstellt haben. Wählen **Sie Fertig** aus, um den Assistenten zu schließen, und die Detailseite Ihrer neuen Bewertung wird auf dem Bildschirm angezeigt.

Wenn nach auswahl der **Option Bewertung erstellen** ein Bildschirm mit einem Fehler bei der Bewertung angezeigt wird, wählen Sie **Erneut** versuchen aus, um Ihre Bewertung neu zu erstellen. 

Sie können den Namen Ihrer Bewertung ändern,  nachdem Sie sie erstellt haben, indem Sie die Schaltfläche Name bearbeiten in der oberen rechten Ecke der Detailseite der [Bewertung auswählen.](#monitor-assessment-progress-and-controls)

## <a name="extend-a-pre-built-assessment"></a>Erweitern einer vordefinierten Bewertung

Sie können eine vordefinierte Bewertung ändern, indem Sie der Vorlage der Bewertung eigene Steuerelemente und Verbesserungsmaßnahmen hinzufügen. Dieser Vorgang wird im Compliance Manager als "Erweitern einer Microsoft-Vorlage" bezeichnet. Wenn Sie die Vorlage einer Bewertung erweitern, erhält sie alle von Microsoft veröffentlichten Updates, die auftreten können, wenn Änderungen an der zugehörigen Verordnung oder dem zugehörigen Produkt vorgenommen werden (siehe Akzeptieren von Updates für [Bewertungen](#accepting-updates-to-assessments)).

Führen Sie diesen Prozess aus, indem Sie auf der Seite mit **Bewertungsvorlagen** und nicht auf der **Bewertungsseite** beginnen.

**Bevor Sie beginnen:**

Zur Vorbereitung auf diesen Prozess müssen Sie zunächst eine speziell formatierte Excel-Kalkulationstabelle zusammenstellen, um die erforderlichen Vorlagendaten zu importieren. Es gibt spezielle Anforderungen für die [formatierten Excel-Dateien, die](compliance-manager-templates.md#formatting-your-template-data-with-excel) im Erweiterungsprozess verwendet werden. Sehen Sie sich die folgenden zusätzlichen Punkte an, um Fehler im Importvorgang zu verhindern:

- Ihre Kalkulationstabelle sollte nur die Aktionen und Steuerelemente enthalten, die Sie der Bewertung hinzufügen möchten. 
- Die Kalkulationstabelle kann keine Steuerelemente oder Aktionen enthalten, die bereits in der Bewertung vorhanden sind, die Sie ändern möchten.
- Erwägen Sie, "Erweiterung" in den Titel Ihrer Vorlage zu nehmen, z. B. "DSGVO – [Ihr Firmenname]-Erweiterung". Dies erleichtert die Identifizierung in  der Liste auf ihrer Bewertungsvorlagenseite im Unterschied zur von Microsoft bereitgestellten Standardvorlage oder einer benutzerdefinierten Vorlage mit einem ähnlichen Namen.

Führen Sie nach dem Formatieren der Kalkulationstabelle die folgenden Schritte aus.

**Schritte zum Erweitern einer Compliance -Manager-Vorlage**

1. Wechseln Sie zur **Seite Bewertungsvorlagen,** und wählen **Sie Neue Vorlage erstellen aus.** Ein Vorlagenerstellungs-Assistent wird geöffnet.

2. Wählen Sie den Typ der Vorlage aus, die Sie erstellen möchten. Wählen Sie in diesem Fall **Erweitern einer Microsoft-Vorlage aus,** und wählen **Sie dann Microsoft-Vorlage auswählen aus.**

3. Auf der rechten Seite des Bildschirms wird ein Flyoutbereich für die Vorlagenauswahl angezeigt, in dem eine Liste aller Vorlagen und deren Status als aktiv oder inaktiv angezeigt werden. Der **Indikator für aktivierte** Vorlagen zeigt an, wie viele Vorlagen derzeit von der Gesamtzahl der verfügbaren Vorlagen verwendet werden. Wenn Sie ihren Grenzwert überschreiten, wird eine Meldungsleiste angezeigt. Weitere [Informationen finden Sie unter Vorlagentypen.](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive)

4. Auf der rechten Seite des Bildschirms wird ein Flyoutbereich für die Vorlagenauswahl angezeigt. Verwenden **der Suche** zum Anwenden von Filtern zum Suchen der vorlage, die Sie möchten

5. Nachdem Sie die Vorlage gefunden haben, wählen Sie das Optionsfeld links vom Namen aus, und wählen Sie **dann Speichern aus.**

6. Auf dem nächsten Bildschirm wird die ausgewählte Vorlage angezeigt. Wenn dies richtig ist, wählen Sie **Weiter aus.** (Wenn falsch, wählen **Sie Wählen Sie eine andere Vorlage aus,** um erneut auszuwählen.)

7. Wählen Sie **auf dem Bildschirm** Datei hochladen die Option **Durchsuchen** aus, um die formatierte Excel-Datei mit allen erforderlichen Vorlagendaten zu suchen und hochzuladen.

8. Wenn keine Probleme mit ihrer Datei auftreten, wird auf dem nächsten Bildschirm der Name der hochgeladenen Datei angezeigt. Wählen **Sie Weiter** aus, um fortzufahren (wenn Sie die Datei ändern müssen, wählen Sie Hochladen einer anderen Datei **aus).**

    - Wenn ein Problem mit Ihrer Datei vor liegt, wird in einer Fehlermeldung oben erklärt, was falsch ist. Sie müssen Ihre Datei korrigieren und erneut hochladen. Fehler resultieren, wenn Ihre Kalkulationstabelle nicht ordnungsgemäß formatiert ist oder wenn in bestimmten Feldern ungültige Informationen enthalten sind.
 
9. Der **Bildschirm Überprüfen und Fertig** stellen zeigt die Anzahl der Verbesserungsaktionen und -steuerelemente sowie die maximale Bewertung für die Vorlage an. Wenn Sie zur Genehmigung bereit sind, wählen Sie **Weiter aus.** (Wenn Sie Änderungen vornehmen müssen, wählen Sie **Hochladen einer anderen Datei aus.)**

10. Der letzte Bildschirm bestätigt, dass eine neue Vorlage erstellt wurde. Wählen **Sie Fertig** aus, um den Assistenten zu beenden.

11. Sie gelangen zur Detailseite Ihrer neuen Vorlage. Hier können Sie Ihre Bewertung erstellen, indem Sie **Bewertung erstellen auswählen.** Anleitungen finden Sie unter Schritt #4 in den [oben aufgeführten Anweisungen zur Bewertungserstellung.](#to-create-an-assessment)

## <a name="create-your-own-custom-assessment"></a>Erstellen Einer eigenen benutzerdefinierten Bewertung

Für das Erstellen einer benutzerdefinierten Bewertung im Compliance-Manager müssen Sie eine eigene Vorlage erstellen. Um Eine eigene Vorlage zu erstellen, stellen Sie zunächst eine formatierte Excel-Kalkulationstabelle zusammen, um die erforderlichen Vorlagendaten zu importieren. Außerdem hilft es, im Voraus zu entscheiden, welcher Gruppe Sie Ihre Bewertung beim Erstellen zuweisen (weitere Informationen zu [Gruppen).](#what-are-groups)

**Führen Sie die folgenden Schritte aus, um Ihre benutzerdefinierte Bewertung zu erstellen:**

1. **Formatieren Sie Ihre Excel-Datei.** Formatieren Sie zunächst Ihre Vorlagendaten mithilfe dieser Anweisungen in [einer Excel-Kalkulationstabelle.](compliance-manager-templates.md#formatting-your-template-data-with-excel)

2. **Erstellen Sie Ihre Vorlage,** indem Sie [die folgenden Anweisungen befolgen.](compliance-manager-templates.md#create-a-new-template)

3. **Erstellen Sie Ihre Bewertung** aus der Vorlage. Sie können zunächst die Detailseite der Vorlage öffnen und **Bewertung** erstellen auswählen oder zu Ihrer **Bewertungsseite** wechseln und **Bewertung erstellen auswählen.**

4. Ein Bewertungserstellungs-Assistent wird in einem großen Flyoutbereich angezeigt. Von hier aus können Sie die Anleitungen befolgen, die unter Schritt #3 der Anweisungen zum Erstellen der Bewertung [beginnen,](#to-create-an-assessment)indem Sie Ihre neue benutzerdefinierte Vorlage für Ihre Bewertung verwenden.

## <a name="delete-an-assessment"></a>Löschen einer Bewertung

Wenn Sie eine Bewertung löschen, wird sie aus der Liste auf der Bewertungsseite entfernt. Beachten Sie die folgenden wichtigen Punkte zum Löschen von Bewertungen:

- **Das Löschen einer Bewertung ist dauerhaft. Sie können es nicht zurück.** Wenn Sie dieselbe Bewertung erneut verwenden möchten, müssen Sie sie neu erstellen.
- Wenn die Verbesserungsmaßnahmen in der Bewertung nicht in einer anderen Bewertung angezeigt werden, werden sie gelöscht, wenn die Bewertung gelöscht wird.
- Es wird [empfohlen, einen Bericht der](#export-an-assessment-report) Bewertung zu exportieren, bevor Sie ihn endgültig löschen.

Führen Sie die folgenden Schritte aus, um eine Bewertung zu löschen:

1. Wählen Sie **auf der Bewertungsseite** die Bewertung aus, die Sie löschen möchten, um die Detailseite dieser Bewertung zu öffnen.

2. Wählen **Sie Bewertung löschen** in der oberen rechten Ecke des Bildschirms aus.

3. Es wird ein Fenster angezeigt, in dem Sie aufgefordert werden, zu bestätigen, dass Sie die Bewertung dauerhaft löschen möchten. Wählen **Sie Bewertung löschen aus,** um das Fenster zu schließen. Sie erhalten ein Bestätigungsfenster, dass Ihre Bewertung aus dem Compliance-Manager gelöscht wurde.

Wenn Sie die einzige Bewertung in einer Gruppe löschen, wird diese Gruppe auch aus dem Compliance-Manager gelöscht.

> [!NOTE]
> Sie können nicht alle Bewertungen löschen. Organisationen benötigen mindestens eine Bewertung, damit Compliance Manager ordnungsgemäß funktioniert. Wenn die Bewertung, die Sie löschen möchten, die einzige ist, fügen Sie eine weitere Bewertung hinzu, bevor Sie die andere Bewertung löschen.

## <a name="monitor-assessment-progress-and-controls"></a>Überwachen des Bewertungsfortschritts und der Steuerelemente

Jede Bewertung verfügt über eine Detailseite, die auf einen Blick einen Überblick über Ihre Fortschritte beim Abschließen der Bewertung bietet. Die Seite zeigt Den Fortschritt beim Abschließen von Steuerelementen und den Teststatus wichtiger Verbesserungsmaßnahmen innerhalb dieser Steuerelemente.

### <a name="overview-tab"></a>Registerkarte "Übersicht"

Die Registerkarte Übersicht enthält ein Diagramm, das Ihren Prozentsatz zum Abschluss der Bewertung zeigt. Dieses Diagramm enthält eine Aufschlüsselung der Punkte aus Aktionen, die Sie besitzen, sowie Punkte von Aktionen im Besitz von Microsoft, damit Sie sehen können, wie viele weitere Punkte Sie zum Abschließen der Bewertung benötigen.

Die wichtigsten Verbesserungsmaßnahmen für Steuerelemente in der Bewertung werden in der Reihenfolge der größten potenziellen Auswirkungen aufgelistet, um Punkte zu sammeln. Im zugeordneten Diagramm wird der aggregierte Teststatus Ihrer Verbesserungsmaßnahmen dargestellt, damit Sie schnell abschätzen können, was getestet wurde und was noch zu tun ist.

Um auf einzelne Verbesserungsaktionen zu zugreifen, besuchen Sie die Registerkarte **Steuerelemente** oder die Registerkarte **Ihre Verbesserungsaktionen.**

### <a name="controls-tab"></a>Registerkarte "Steuerelemente"

Auf der Registerkarte Steuerelemente werden detaillierte Informationen für jedes Steuerelement angezeigt, das der Bewertung zugeordnet ist. Ein **Diagramm zum Aufschlüsseln** des Steuerelementstatus zeigt den Status von Steuerelementen nach Familie, sodass Sie auf einen Blick sehen können, welche Gruppierungen von Steuerelementen Aufmerksamkeit benötigen.

Unterhalb des Diagramms enthält eine Tabelle detaillierte Informationen zu den einzelnen Steuerelementen in der Bewertung. Steuerelemente werden nach Steuerelementfamilien gruppieren. Erweitern Sie die einzelnen Familiennamen, um die einzelnen Steuerelemente, die sie enthalten, offen zu zeigen. Die für jedes Steuerelement aufgeführten Informationen umfassen:

- **Steuerelementtitel**
- **Status**: gibt den Teststatus der Verbesserungsmaßnahmen innerhalb des Steuerelements an. 
    - **Übergeben** – Alle Verbesserungsmaßnahmen haben den Teststatus "bestanden", oder mindestens eine wurde bestanden, und die restlichen Aktionen sind "nicht im Bereich"
    -  **Fehlgeschlagen** – mindestens eine Verbesserungsaktion hat den Teststatus "fehlgeschlagen".
    - **Keine** – alle Verbesserungsmaßnahmen wurden nicht getestet
    - **Out of scope** – alle Verbesserungsmaßnahmen sind für diese Bewertung nicht in den Bereich
    - **In Bearbeitung** – Verbesserungsmaßnahmen haben einen anderen Status als die oben aufgeführten, die "in Bearbeitung", "Teilgutschrift" oder "unentdeckt" enthalten können.
- **Steuerelement-ID:** die Identifikationsnummer des Steuerelements, zugewiesen durch die entsprechende Verordnung, den Standard oder die Richtlinie
- **Punkte erreicht:** Die Anzahl der Punkte, die durch Das Abschließen von Aktionen erzielt wurden, von der Gesamtzahl der erreichbaren Punkte. 
- **Ihre Aktionen**: Die Anzahl der abgeschlossenen Aktionen aus der Gesamtzahl der zu erledigende Aktionen
- **Microsoft-Aktionen**: Die Anzahl der von Microsoft abgeschlossenen Aktionen 

Um die Details eines Steuerelements anzuzeigen, wählen Sie es aus der Zeile in der Tabelle aus. Die Seite "Steuerelementdetails" zeigt ein Diagramm, das den Teststatus der Aktionen innerhalb dieses Steuerelements angibt. Eine Tabelle unterhalb des Diagramms zeigt die wichtigsten Verbesserungsmaßnahmen für dieses Steuerelement.

Wählen Sie eine Verbesserungsaktion aus der Liste aus, um einen Drilldown auf der Detailseite der Verbesserungsaktion zu erstellen. Die Detailseiten zeigen den Teststatus, Implementierungshinweise und starten in der empfohlenen Lösung.

### <a name="your-improvement-actions-tab"></a>Registerkarte Verbesserungsmaßnahmen

Auf der Registerkarte für Ihre Verbesserungsmaßnahmen sind alle Steuerelemente in der Bewertung aufgeführt, die von Ihrer Organisation verwaltet werden. In der Statusleiste wird der aggregierte Teststatus Ihrer Verbesserungsmaßnahmen in der Bewertung angezeigt, damit Sie schnell abschätzen können, was getestet wurde und was noch zu tun ist. Unterhalb der Leiste befindet sich die vollständige Liste der Verbesserungsmaßnahmen und wichtigsten Details, einschließlich: Teststatus, Anzahl potenzieller und verdienter Punkte, zugehörige Vorschriften und Standards, anwendbare Lösung, Aktionstyp und Steuerungsfamilie. Erfahren Sie mehr [darüber, wie Aktionen zu Ihrer Compliance-Bewertung beitragen.](compliance-score-calculation.md#action-types-and-points)

Wählen Sie eine Verbesserungsaktion aus, um die Detailseite anzuzeigen, und wählen Sie **den** Link Jetzt starten aus, um die Lösung zu öffnen, um Maßnahmen zu ergreifen.

### <a name="microsoft-actions-tab"></a>Registerkarte "Microsoft-Aktionen"

Auf der Registerkarte Microsoft-Aktionen werden alle Aktionen in der Bewertung aufgeführt, die von Microsoft verwaltet werden. Die Liste enthält wichtige Aktionsdetails, einschließlich: Teststatus, Punkte, die zu Ihrer allgemeinen Compliance-Bewertung beitragen, zugehörige Vorschriften und Standards, anwendbare Lösung, Aktionstyp und Steuerungsfamilie. Wählen Sie eine Verbesserungsaktion aus, um die Detailseite anzuzeigen.

Erfahren Sie mehr über die Nachverfolgung und Bewertung [von Steuerelementen und Verbesserungsaktionen.](compliance-score-calculation.md)

## <a name="accepting-updates-to-assessments"></a>Akzeptieren von Updates für Bewertungen

Wenn ein Update für eine Bewertung verfügbar ist, wird eine Benachrichtigung angezeigt, und Sie haben die Möglichkeit, das Update zu akzeptieren oder es für einen späteren Zeitpunkt zurück zu stellen.

### <a name="what-causes-an-update"></a>Ursachen eines Updates

Eine Bewertungsaktualisierung tritt auf, wenn zugrunde liegende Vorlagenänderungen auftreten, die sich auf die Bewertung auswirken. Änderungen können eine Anpassung der Steuerelementzuordnung oder andere Anleitungen basierend auf behördlichen Änderungen oder Produktänderungen umfassen. Bewertungsupdates können von Ihrer Organisation (z. B. wenn eine benutzerdefinierte Vorlage [geändert](compliance-manager-templates.md#modify-a-template)wird) sowie von Microsoft stammen.

Wenn Microsoft eine von Ihnen erweiterte Compliance -Manager-Vorlage aktualisiert, erbt Ihre Bewertung diese Updates, sobald Sie sie akzeptieren. Ihre Bewertung behält die zusätzlichen Attribute bei, die Sie bei der Erweiterung auf die Bewertung angewendet haben.

Benutzerdefinierte Bewertungen, die Sie erstellen, erhalten keine Vorlagenupdates von Microsoft. Benutzerdefinierte Bewertungen können Aktualisierungen von Verbesserungsaktionen erhalten, aber alle Microsoft-Updates zur Steuerung der Zuordnung zwischen Bewertungen und Verbesserungsmaßnahmen gelten nicht für benutzerdefinierte Vorlagen.

> [!NOTE]
> Aktualisierungen von Bewertungen gelten nur auf Gruppenebene. Wenn Sie zwei Bewertungen aus derselben Vorlage erstellen, die in zwei verschiedenen Gruppen vorhanden sind, enthält jede Bewertung eine Benachrichtigung über ausstehende Updates, und Sie müssen das Update für jede Bewertung in der jeweiligen Gruppe einzeln akzeptieren.

#### <a name="where-youll-see-assessment-update-notifications"></a>Dort werden Benachrichtigungen zu Bewertungsupdates angezeigt

Auf der Seite mit den Bewertungsdetails wird auch eine **Bezeichnung für ausstehende** Updates neben der Bewertung mit einem Update angezeigt. Wählen Sie diese Bewertung aus, um zur Detailseite zu gelangen.

Eine Meldung am oberen Rand der Seite mit den Bewertungsdetails zeigt, dass für diese Bewertung ein Update verfügbar ist. Wählen Sie **die Schaltfläche Update** überprüfen im Banner aus, um die spezifischen Änderungen zu überprüfen und das Update zu akzeptieren oder zurück zu legen.

Auf der Seite bewertungsdetails können auch Verbesserungsmaßnahmen aufgeführt werden, die eine **Ausstehende** Aktualisierungsbezeichnung daneben enthalten. Diese Updates sind für bestimmte Änderungen an den Verbesserungsmaßnahmen selbst und müssen separat akzeptiert werden. Weitere Informationen finden Sie [unter Akzeptieren von Updates zu Verbesserungsmaßnahmen.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

#### <a name="review-update-to-accept-or-defer"></a>Überprüfen des Updates auf Annahme oder Verschiebung

Nachdem Sie **auf der** Seite Bewertungsdetails die Option Update überprüfen ausgewählt haben, wird auf der rechten Seite des Bildschirms ein Flyoutbereich angezeigt. Der Flyoutbereich enthält die wichtigsten Details zum ausstehenden Update:

- Der Vorlagentitel
- Quelle des Updates (Microsoft, Ihre Organisation oder ein bestimmter Benutzer)
- Das Datum, an dem das Update erstellt wurde
- Eine Übersicht über das Update
- Spezifische Details zu den Änderungen, einschließlich der Auswirkungen auf Ihre Compliancebewertung, des Fortschritts bis zum Abschluss der Bewertung und der spezifischen Anzahl von Änderungen an Verbesserungsmaßnahmen und Steuerelementen.

Wenn Sie **den Link Aktualisierte Vorlage** auswählen, wird eine Excel-Datei mit Steuerelementdaten für die Version der Vorlage mit den ausstehenden Updates heruntergeladen. Wenn Sie den **Link Aktuelle Vorlage** auswählen, wird eine Datei der vorhandenen Vorlage ohne die Änderungen heruntergeladen.

Wählen Sie Update akzeptieren aus, um das Update zu akzeptieren und die Änderungen an Ihrer **Bewertung vorzunehmen.** Akzeptierte Änderungen sind dauerhaft.

Wenn Sie **Abbrechen** auswählen, wird das Update nicht auf die Bewertung angewendet. Es wird jedoch weiterhin die **Benachrichtigung** über ausstehende Updates angezeigt, bis Sie das Update akzeptieren.

**Warum wir empfehlen, Updates zu akzeptieren**

Das Akzeptieren von Updates trägt dazu bei, dass Sie über die neuesten Anleitungen zur Verwendung von Lösungen verfügen und geeignete Verbesserungsmaßnahmen ergreifen, um die Anforderungen der Zertifizierung zu erfüllen.

**Gründe für die Verschiebung eines Updates**

Wenn Sie gerade dabei sind, eine Bewertung zu erstellen, sollten Sie sicherstellen, dass Sie die Arbeit daran abgeschlossen haben, bevor Sie ein Update der Bewertung akzeptieren, das die Steuerungszuordnung unterbrechen könnte. Sie können das Update für einen späteren Zeitpunkt zurückdingen, indem Sie im Flyoutbereich für das Überprüfungsupdate die Option **Abbrechen** auswählen.

## <a name="export-an-assessment-report"></a>Exportieren eines Bewertungsberichts

Sie können eine Bewertung in eine Excel-Datei für Compliance-Interessengruppen in Ihrer Organisation oder für externe Auditoren und Aufsichtsbehörden exportieren. Wählen Sie auf der  Seite Bewertungsdetails die Schaltfläche Bericht generieren am oberen Rand der Seite aus, wodurch eine Excel-Datei erstellt wird, die Sie speichern und freigeben können.

Der Bericht ist eine Momentaufnahme der Bewertung zum Datum und zur Uhrzeit des Exports. Sie enthält die Details für Steuerelemente, die sowohl von Ihnen als auch von Microsoft verwaltet werden, einschließlich Implementierungsstatus, Testdatum und Testergebnissen.
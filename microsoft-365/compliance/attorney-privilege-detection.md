---
title: Einrichten der Erkennung von Anwalts Mandanten-Berechtigungen in Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: Verwenden Sie das Erkennungs Modell "Attorney-Client-Berechtigung", um die Lern basierte Erkennung privilegierter Inhalte zu verwenden, wenn Sie Inhalte in einem erweiterten eDiscovery-Fall überprüfen.
ms.openlocfilehash: 943b788dfea62433f0f6c1dca3b6b105cf92bae8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081081"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a>Einrichten der Erkennung von Anwalts Mandanten-Berechtigungen in Advanced eDiscovery

Ein wichtiger und kostspieliger Aspekt der Überprüfungsphase eines eDiscovery-Prozesses besteht darin, Dokumente für privilegierte Inhalte zu überprüfen. Advanced eDiscovery bietet eine maschinelle Lern basierte Erkennung von privilegierten Inhalten, um diesen Prozess effizienter zu gestalten. Dieses Feature wird als *Anwalts Client-Berechtigungs Erkennung*bezeichnet.

> [!NOTE]
> Sie müssen sich für das Erkennungs Modell für Anwalts-und Client Rechte entscheiden, bevor Sie es verwenden können. Anweisungen finden Sie in [Schritt 1](#step-1-opt-in-to-attorney-client-privilege-detection) .

## <a name="how-does-it-work"></a>Wie funktioniert dies?

Wenn die Erkennung der Anwalts-Client-Rechte aktiviert ist, werden alle Dokumente in einem Überprüfungs Satzes vom Anwalt-Client-Berechtigungs Erkennungs Modell verarbeitet, wenn Sie [die Daten](analyzing-data-in-review-set.md) im Überprüfungspaket analysieren. Das Modell sucht zwei Dinge:

- Privilegierte Inhalte – das Modell verwendet Maschinelles Lernen, um die Wahrscheinlichkeit zu ermitteln, dass das Dokumentinhalte enthält, die in der Natur legal sind.

- Teilnehmer – im Rahmen der Einrichtung der Anwalts-Client-Berechtigungs Erkennung müssen Sie eine Liste der Anwälte für Ihre Organisation übermitteln. Das Modell vergleicht dann die Teilnehmer des Dokuments mit der anwaltsliste, um festzustellen, ob ein Dokument mindestens einen Anwalts Teilnehmer hat.

Das Modell erzeugt für jedes Dokument die folgenden drei Eigenschaften:

- **AttorneyClientPrivilegeScore** – die Wahrscheinlichkeit, dass das Dokument in der Natur legal ist; die Werte für die Partitur liegen zwischen **0** und **1**.

- **HasAttorney** – diese Eigenschaft wird auf **true** festgelegt, wenn einer der Dokument Teilnehmer in der anwaltsliste aufgeführt ist; Andernfalls ist der Wert **false**. Der Wert ist auch auf " **false** " festgelegt, wenn Ihre Organisation keine anwaltsliste hochgeladen hat.

- **Isprivilege** – diese Eigenschaft wird auf **true** festgelegt, wenn der Wert für **AttorneyClientPrivilegeScore** oberhalb des Schwellenwerts liegt *oder* wenn das Dokument über einen Anwalts Teilnehmer verfügt; Andernfalls wird der Wert auf **false**festgelegt.

Diese Eigenschaften (und die entsprechenden Werte) werden den Datei Metadaten der Dokumente in einem Überprüfungs Satzes hinzugefügt, wie im folgenden Screenshot dargestellt:

![In Datei Metadaten angezeigte Anwalts-Client-Berechtigungs Eigenschaften](media/AeDAttorneyClientPrivilegeMetadata.png)

Diese drei Eigenschaften können auch innerhalb eines Überprüfungs Satzes durchsucht werden. Weitere Informationen finden Sie unter [Abfragen der Daten in einem Überprüfungs Satzes](review-set-search.md).

## <a name="set-up-the-attorney-client-privilege-detection-model"></a>Einrichten des Erkennungs Modells für Anwalts Client-Berechtigungen

Um das Erkennungs Modell für das Attorney-Client-Privileg zu aktivieren, muss Ihre Organisation sich anmelden und dann eine anwaltsliste hochladen.

### <a name="step-1-opt-in-to-attorney-client-privilege-detection"></a>Schritt 1: Anmelden bei der Erkennung von Anwalts-und Client rechten

Wie bereits erwähnt, befindet sich das Erkennungs Modell für das Anwalts Client-Recht in der Vorschau. Daher muss sich eine Person in Ihrem Unternehmen eDiscovery Administrator (ein Mitglied der Untergruppe eDiscovery Administrator in der Rollengruppe eDiscovery-Manager) anmelden, um das Modell in ihren erweiterten eDiscovery-Fällen zur Verfügung zu stellen.

1. Wechseln Sie im Security #a0 Compliance Center zu **eDiscovery #a1 Advanced eDiscovery**.

2. Klicken Sie auf der Seite für die **Erweiterte eDiscovery** -Homepage auf der Kachel **Einstellungen** auf **experimentelle Features konfigurieren**.

   ![Klicken Sie auf "experimentelle Features konfigurieren".](media/AeDExperimentalFeatures.png)

3. Klicken Sie auf der Registerkarte **experimentelle Features** auf **Attorney-Client-Berechtigungseinstellung verwalten**.

4. Klicken Sie auf der Seite " **Attorney-Client-Privilege-** Flyout" auf die Umschaltfläche, um das Feature zu aktivieren, und klicken Sie dann auf **Speichern**.

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>Schritt 2: Hochladen einer Liste von Anwälten (optional)

Um das Erkennungs Modell "Attorney-Client-Berechtigung" vollständig zu nutzen und die Ergebnisse des " **hat Attorney** " oder der **potenziell privilegierten** Erkennung zu verwenden, die zuvor beschrieben wurde, empfehlen wir Ihnen, eine Liste mit e-Mail-Adressen für folgendes hochzuladen: Juristen und juristische Personen, die für Ihre Organisation arbeiten. 

So laden Sie eine anwaltsliste für das Erkennungs Modell "Attorney-Client-Berechtigung" hoch:

1. Erstellen Sie eine CSV-Datei (ohne Kopfzeile), und fügen Sie die e-Mail-Adresse für jede entsprechende Person in einer separaten Zeile hinzu. Speichern Sie diese Datei auf Ihrem lokalen Computer.

2. Klicken Sie auf der Seite für die **Erweiterte eDiscovery** -Homepage auf der Kachel **Einstellungen** auf **experimentelle Features konfigurieren**, und klicken Sie dann auf **Anwalts-Client-Berechtigungseinstellung verwalten**.

   Die Seite " **Attorney-Client-Privilege** " wird angezeigt, und die Option " **Anwalt-Client-Berechtigung erkennen** " ist aktiviert.

   ![Flyout-Seite "Attorney-Client-Privilegien"](media/AeDUploadAttorneyList.png)

3. Klicken Sie auf **Durchsuchen** , und suchen Sie dann nach der CSV-Datei, die Sie in Schritt 1 erstellt haben.

4. Klicken Sie auf **Speichern** , um die anwaltsliste hochzuladen.

## <a name="use-the-attorney-client-privilege-detection-model"></a>Verwenden des Erkennungs Modells für Anwalts Client-Berechtigungen

Führen Sie die Schritte in diesem Abschnitt aus, um die Erkennung von Anwalts Mandanten-Berechtigungen für Dokumente in einem Überprüfungs Sätze zu verwenden.

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>Schritt 1: Erstellen einer smarttaggruppe mit dem Anwalt-Client-Berechtigungs Erkennungs Modell

Eine der wichtigsten Methoden zum Anzeigen der Ergebnisse der Erkennung von Anwalts Client-Berechtigungen in Ihrem Überprüfungsprozess ist die Verwendung einer smarttaggruppe. Eine smarttaggruppe gibt die Ergebnisse der Anwalts-Client-Berechtigungs Erkennung an und zeigt die Ergebnisse Inline neben den Tags in einer smarttaggruppe an. Auf diese Weise können Sie während der Dokumentüberprüfung schnell potenziell privilegierte Dokumente identifizieren. Darüber hinaus können Sie die Tags in der smarttaggruppe auch verwenden, um Dokumente als privilegiertes oder als nicht privilegiertes Tag zu kennzeichnen. Weitere Informationen zu Smarttags finden Sie unter [Einrichten von Smart Tags in Advanced eDiscovery](smart-tags.md).

1. Klicken Sie in der Überprüfungsgruppe mit den Dokumenten, die Sie in Schritt 1 analysiert haben, auf **Überarbeitungs Gruppe verwalten** , und klicken Sie dann auf **Tags verwalten**.
 
2. Klicken Sie unter **Tags**auf die Dropdown Seite neben **Gruppe hinzufügen** , und klicken Sie dann auf **smarttaggruppe hinzufügen**.

   ![Klicken Sie auf Smart Tag-Gruppe hinzufügen.](media/AeDCreateSmartTag.png)

3. Klicken Sie auf der Seite **Modell für Smarttag auswählen** auf neben **Anwalts Mandanten-Privileg** **auswählen** .

   Es wird eine Transpondergruppe namens " **Attorney-Client Privilege** " angezeigt. Sie enthält zwei untergeordnete Tags mit dem Namen " **positiv** " und " **negativ**", die den möglichen Ergebnissen entsprechen, die das Modell erzeugt.

   ![Smarttaggruppe "Attorney-Client Privilege"](media/AeDAttorneyClientSmartTagGroup.png)

3. Benennen Sie die Tag-Gruppe und die Tags entsprechend ihrer Überprüfung um. Sie können beispielsweise " **positiv** " in " **privilegierte** " und " **negativ** " in " **nicht privilegierte**" umbenennen.

### <a name="step-2-analyze-a-review-set"></a>Schritt 2: Analysieren eines Überprüfungs Satzes

Wenn Sie die Dokumente in einem Überprüfungs Satzes analysieren, wird auch das Clientzugriffs Berechtigungs-Erkennungs Modell ausgeführt und die entsprechenden Eigenschaften (beschrieben in[How is it work?](#how-does-it-work) wird jedem Dokument in der Überprüfungsgruppe hinzugefügt. Weitere Informationen zum Analysieren von Daten in Überprüfungs Sätzen finden Sie unter [Analysieren von Daten in einer Überprüfungsgruppe in Advanced eDiscovery](analyzing-data-in-review-set.md).

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a>Schritt 3: Verwenden der smarttaggruppe zur Überprüfung von privilegierten Inhalten

Nach der Analyse des Überprüfungs Satzes und der Einrichtung von Smarttags besteht der nächste Schritt darin, die Dokumente zu überprüfen. Wenn das Modell festgestellt hat, dass das Dokument möglicherweise privilegiert ist, zeigt das entsprechende Smarttag im **taggingbereich** die folgenden Ergebnisse an, die von der Berechtigung "Anwalt-Client-Erkennung" erzeugt werden:

- Wenn das Dokumentinhalt enthält, der möglicherweise zulässig ist, wird der **rechtliche Inhalt** der Bezeichnung neben dem entsprechenden Smarttag angezeigt (in diesem Fall das standardmäßige **positive** Tag).

- Wenn das Dokument über einen Teilnehmer verfügt, der in der anwaltsliste Ihrer Organisation gefunden wird, wird der Bezeichnungs **Anwalt** neben dem entsprechenden Smarttag angezeigt (in diesem Fall ist dies auch das standardmäßige **positive** Tag).

- Wenn das Dokumentinhalte enthält, die möglicherweise legal sind *und* ein Teilnehmer in der anwaltsliste gefunden wird, werden sowohl die **rechtlichen Inhalte** als auch rechts **Anwalts** Bezeichnungen angezeigt. 

Wenn das Modell feststellt, dass ein Dokument keine Inhalte enthält, die in der Natur legal sind oder keinen Teilnehmer aus der anwaltsliste enthalten, wird im taggingbereich keine Bezeichnung angezeigt.

Die folgenden Screenshots zeigen beispielsweise zwei Dokumente; der erste enthält Inhalte, die in der Natur legal sind und einen Teilnehmer in der Liste der Rechtsanwälte gefunden haben. der zweite enthält weder und daher keine Beschriftungen angezeigt.

![Dokument mit Rechtsanwalt und rechtlichen Inhalts Bezeichnungen](media/AeDTaggingPanelLegalContentAttorney.png)

![Dokument ohne Beschriftungen](media/AeDTaggingPanelNegative.png)

Nachdem Sie ein Dokument überprüft haben, um festzustellen, ob es privilegierte Inhalte enthält, können Sie das Dokument mit dem entsprechenden Tag versehen.
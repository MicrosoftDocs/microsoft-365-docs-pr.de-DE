---
title: Untersuchen und Beheben von Warnungen zur Kommunikationscompliance
description: Untersuchen und Behebung von Warnungen zur Kommunikationskonformität in Microsoft 365.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: ea96780846507e7fc3edccb28e04055ce79261fa
ms.sourcegitcommit: c10eb675da725830e9776d2a0566ba3622eb361c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980098"
---
# <a name="investigate-and-remediate-communication-compliance-alerts"></a>Untersuchen und Beheben von Warnungen zur Kommunikationscompliance

Nachdem Sie Ihre Richtlinien für die Kommunikationskonformität konfiguriert haben, erhalten Sie Benachrichtigungen im Microsoft 365 Compliance Center für Nachrichtenprobleme, die Ihren Richtlinienbedingungen entsprechen. Folgen Sie hier den Workflowanweisungen, um Warnungsprobleme zu untersuchen und zu beheben.

## <a name="investigate-alerts"></a>Untersuchen von Warnungen

Der erste Schritt zur Untersuchung von Problemen, die von Ihren Richtlinien erkannt werden, besteht in der Überprüfung von Warnungen zur Kommunikationskonformität im Microsoft 365 Compliance Center. Es gibt verschiedene Bereiche im Bereich der Kommunikationskonformitätslösung, die Ihnen dabei helfen, Warnungen schnell zu untersuchen, je nachdem, wie Sie die Warnungsgruppe anzeigen möchten:

- **Seite**"Kommunikationskonformitätsrichtlinie": Wenn Sie sich bei der Verwendung von Anmeldeinformationen für ein Administratorkonto in Ihrer [https://compliance.microsoft.com](https://compliance.microsoft.com) Microsoft 365-Organisation anmelden,  wählen Sie "Kommunikationskonformität" aus, um die Seite "Richtlinie zur Kommunikationskonformität" anzeigen zu können.  Auf dieser Seite werden Richtlinien zur Kommunikationskonformität angezeigt, die für Ihre Microsoft 365-Organisation konfiguriert sind, sowie Links zu empfohlenen Richtlinienvorlagen. Jede aufgeführte Richtlinie enthält die Anzahl der Warnungen, die überprüft werden müssen, die Anzahl der eskalierten und aufgelösten Elemente, den Status der Richtlinie sowie Datum und Uhrzeit der letzten Richtlinienüberprüfung. Beim Auswählen einer Richtlinie werden alle ausstehenden Warnungen für Übereinstimmungen mit der Richtlinie angezeigt. Wählen Sie eine bestimmte Warnung aus, um die Seite mit den Richtliniendetails zu starten und Korrekturmaßnahmen zu ergreifen.
- **Warnungen:** Navigieren Sie **zu** Benachrichtigungen zur Kommunikationskonformität, um die letzten 30 Tage der  >   Warnungen nach Richtlinien übereinstimmungen anzuzeigen. In dieser Ansicht können Sie schnell erkennen, welche Richtlinien der Kommunikationscompliance die meisten Warnungen nach Schweregraden generieren. Um Korrekturaktionen zu starten, wählen Sie die Richtlinie aus, die der Warnung zugeordnet ist, um die Seite mit den **Richtliniendetails zu** starten. Auf  der Seite "Richtliniendetails" können Sie eine  Zusammenfassung der Aktivitäten auf der  Seite "Übersicht" anzeigen, Warnmeldungen auf  der Seite "Ausstehend" überprüfen und reagieren oder den Verlauf geschlossener Warnungen auf der Seite "Aufgelöst" überprüfen.
- **Berichte:** Navigieren Sie zu **"Kommunikationskonformitätsberichte",**  >   um Widgets für Berichte zur Kommunikationskonformität anzuzeigen. Jedes Widget bietet eine Übersicht über Aktivitäten und Status der Kommunikationskonformität, einschließlich Zugriff auf tiefere Einblicke in Richtlinienübereinander und Abhilfemaßnahmen.

### <a name="using-filters"></a>Verwenden von Filtern

Der nächste Schritt besteht darin, die Nachrichten zu sortieren, um die Warnungen leichter untersuchen zu können. Auf der **Seite "Richtliniendetails"** unterstützt die Kommunikationskonformität die mehrstufige Filterung für mehrere Nachrichtenfelder, damit Sie Nachrichten mit Richtlinien übereinstimmungen schnell untersuchen und überprüfen können. Die Filterung ist für ausstehende und gelöste Elemente für jede konfigurierte Richtlinie verfügbar. Sie können Filterabfragen für eine Richtlinie konfigurieren oder benutzerdefinierte und standardmäßige Filterabfragen für die Verwendung in jeder bestimmten Richtlinie konfigurieren. Nachdem Sie die Felder für einen Filter konfiguriert haben, werden die Filterfelder oben in der Warteschlange für die Warnmeldung angezeigt, die Sie für bestimmte Filterwerte konfigurieren können.

Eine vollständige Liste der Filter und Felddetails finden Sie im [Artikel](communication-compliance-feature-reference.md#filters) zur Featurereferenz unter "Filter".

#### <a name="to-configure-a-filter"></a>So konfigurieren Sie einen Filter

1. Melden Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Microsoft 365 Compliance Center zu **Kommunikationskonformität.**

3. Wählen Sie **die Registerkarte** "Richtlinien" aus, und wählen Sie dann eine Richtlinie für die Untersuchung aus, doppelklicken Sie, um die Seite **"Richtlinie" zu** öffnen.

4. Wählen Sie **auf der Seite** "Richtlinie" entweder die Registerkarte **"Ausstehend"** oder **"Aufgelöst"** aus, um die Elemente zum Filtern anzeigen.

5. Wählen Sie das **Steuerelement "Filter"** aus, um die Seite **"Filterdetails"** zu öffnen.

6. Aktivieren Sie ein oder mehrere Kontrollkästchen, um Filter für diese Warnungen zu aktivieren. Sie können aus zahlreichen Filtern auswählen, einschließlich *Datum,* *Absender,* *Betreff/Titel,* *Klassifizierungen* und mehr.

7. Wenn Sie den ausgewählten Filter als Standardfilter speichern möchten, wählen Sie **"Als Standard speichern" aus.** Wenn Sie diesen Filter als gespeicherten Filter verwenden möchten, wählen Sie **"Fertig" aus.**

8. Wenn Sie die ausgewählten Filter als Filterabfrage speichern  möchten, wählen Sie "Abfragesteuerelement speichern" aus, nachdem Sie mindestens einen Filterwert konfiguriert haben. Geben Sie einen Namen für die Filterabfrage ein, und wählen Sie **"Speichern" aus.** Dieser Filter kann nur für diese Richtlinie verwendet  werden und ist im Abschnitt "Gespeicherte Filterabfragen" der Seite **"Filterdetails"** aufgeführt.

    ![Filterdetailsteuerelemente für Kommunikationskonformität](../media/communication-compliance-filter-detail-controls.png)

### <a name="using-near-and-exact-duplicate-analysis"></a>Verwenden der Analyse naher und genauer Duplikate

Richtlinien zur Kommunikationscompliance werden automatisch gescannt und nahe und genaue Nachrichtenduplikate ohne zusätzliche Konfigurationsschritte vorgruppiert. Mit dieser Ansicht können Sie schnell auf ähnliche Nachrichten eins-nach-eins oder als Gruppe reagieren, wodurch der Aufwand für die Nachrichtenuntersuchung für Prüfer reduziert wird. Wenn Duplikate erkannt werden, werden die Steuerelemente **Nahe Duplikate** und/oder **Exakte Duplikate** in der Symbolleiste für Korrekturmaßnahmen angezeigt. Diese Ansicht ist nicht verfügbar, wenn keine fasten oder exakten Duplikate gefunden werden.

#### <a name="to-remediate-duplicates"></a>So entfernen Sie Duplikate

1. Melden Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Microsoft 365 Compliance Center zu **Kommunikationskonformität.**

3. Wählen Sie **die Registerkarte** "Richtlinien" aus, und wählen Sie dann eine Richtlinie für die Untersuchung aus, doppelklicken Sie, um die Seite **"Richtlinie" zu** öffnen.

4. Wählen Sie **auf der Seite "Richtlinie"** entweder die Registerkarte **"Ausstehend"** oder **"Aufgelöst"** aus, um doppelte Nachrichten anzeigen zu können.

5. Wählen Sie **die Steuerelemente "Near Duplicates"** oder **"Exact Duplicates"** aus, um die Detailseite für Duplikate zu öffnen.

6. Wählen Sie eine oder mehrere Meldungen aus, um Aktionssteuerelemente für diese Nachrichten zu löschen.

7. Wählen **Sie "Auflösen",**"Benachrichtigen", **"Eskalieren"** oder **"Herunterladen"** aus, um die Aktion auf die ausgewählten doppelten Nachrichten als Standardfilter anzuwenden. 

8. Wählen **Sie "Schließen"** aus, nachdem Sie die Korrekturaktionen für die Nachrichten abgeschlossen haben.

    ![Kommunikationskonformität : Exakte Duplizieren von Steuerelementen](../media/communication-compliance-duplicates-controls.png)

## <a name="remediate-alerts"></a>Behebung von Warnungen

Unabhängig davon, wo Sie mit der Überprüfung von Warnungen oder der von Ihnen konfigurierten Filterung beginnen, besteht der nächste Schritt darin, Korrekturmaßnahmen zur Lösung der Warnung zu ergreifen. Starten Sie die Warnungsbehebung mithilfe des folgenden Workflows auf den Seiten **"Richtlinien"** **oder "Benachrichtigungen".**

### <a name="step-1-examine-the-message-basics"></a>Schritt 1: Überprüfen der Grundlagen der Nachricht

 Manchmal ist es aus der Quelle oder dem Betreff offensichtlich, dass eine Nachricht sofort behoben werden kann. Es kann sein, dass die Nachricht fälschlicherweise oder fälschlicherweise mit einer Richtlinie übereinstimmen und als falsch positives Ergebnis aufgelöst werden sollte. Wählen Sie die Steuerung für **Fehlmeldungen**, um die Warnung sofort zu lösen und aus der Warteschlange für ausstehende Warnungen zu entfernen. Anhand der Quell- oder Absenderinformationen wissen Sie möglicherweise bereits, wie die Nachricht unter diesen Bedingungen geroutet oder behandelt werden sollte. Erwägen Sie die Verwendung der Steuerelemente **Kennzeichnen als** oder **Eskalieren**, um entsprechenden Nachrichten eine Kennzeichnung zuzuweisen oder Nachrichten an einen bestimmten Bearbeiter zu senden.

![Kommunikationskonformitäts-Korrekturkontrollen](../media/communication-compliance-remediation-controls.png)

### <a name="step-2-examine-the-message-details"></a>Schritt 2: Überprüfen der Nachrichtendetails

Nach der Überprüfung der Grundlagen der Nachricht ist es an der Zeit, eine Nachricht zu öffnen, um die Details zu untersuchen und weitere Abhilfemaßnahmen zu ermitteln. Wählen Sie eine Nachricht aus, um den gesamten Nachrichtenkopf und die Textkörperinformationen anzuzeigen. Es stehen mehrere Ansichten zur Verfügung, die Ihnen bei der Entscheidung zur richtigen Vorgehensweise helfen:

- **Quellansicht**: Diese Ansicht ist die standardmäßige Nachrichtenansicht, die häufig in den meisten webbasierten Messaging-Plattformen zu sehen ist. Die Kopfzeileninformationen sind in der normalen Formatvorlage formatiert, und der Nachrichtentext unterstützt formatierte Grafikdateien und umbrochenen Text.
- **Textansicht:** Die Textansicht zeigt eine nur zeilennummerierte Textansicht der Nachricht an und enthält die Hervorhebung von Schlüsselwörtern in Nachrichten und Anlagen für Begriffe, die in der zugeordneten Kommunikationskonformitätsrichtlinie übereinstimmen. Die Hervorhebung von Schlüsselwörtern kann Ihnen helfen, lange Nachrichten und Anlagen schnell für den Bereich des Interesses zu überprüfen. In einigen Fällen ist hervorgehobener Text möglicherweise nur in Anlagen für Nachrichten enthalten, die den Richtlinienbedingungen entsprechende. Eingebettete Dateien werden nicht angezeigt, und die Zeilennummerierung in dieser Ansicht ist hilfreich, um relevante Details zwischen mehreren Prüfern zu referenzieren.
- **Anmerkungenansicht**: In dieser Ansicht können Prüfer Anmerkungen direkt zu der Nachricht hinzufügen, die in der Nachrichtenansicht gespeichert werden.
- **Benutzerhistorie**: Die Ansicht "Benutzerhistorie" zeigt alle anderen Warnungen an, die durch eine Richtlinie zur Kommunikationscompliance für den Benutzer, der die Nachricht sendet, generiert wurden.
- **Nachrichtendetailansicht:** Erweiterte Ansicht von Nachrichtenmetadaten und Konfigurationsinformationen.
- **Mustererkennungsbenachrichtigung (Vorschau):** Viele Läster- und Mobbingaktionen im Laufe der Zeit und beinhalten das erneute Ausführen von Instanzen desselben Verhaltens durch einen Benutzer. Die *erkannte Benachrichtigung* "Muster" wird in den Warnungsdetails angezeigt und weckt die Aufmerksamkeit auf die Warnung. Die Erkennung von Mustern wird auf Richtlinienbasis durchgeführt und wertet das Verhalten der letzten 30 Tage aus, wenn mindestens zwei Nachrichten von einem Absender an denselben Empfänger gesendet werden. Ermittler und Prüfer können diese Benachrichtigung verwenden, um wiederholtes Verhalten zu identifizieren, um die Warnung gegebenenfalls auszuwerten.

    ![Steuerelemente für die Nachrichtenansicht der Kommunikationskonformität](../media/communication-compliance-message-views.png)

### <a name="step-3-decide-on-a-remediation-action"></a>Schritt 3: Festlegen einer Korrekturaktion

Nachdem Sie nun die Details der Nachricht für die Warnung überprüft haben, können Sie mehrere Abhilfemaßnahmen auswählen:

- **Auflösen:** Wenn Sie das **Steuerelement "Auflösen"** auswählen, wird die Nachricht sofort aus der Warteschlange für ausstehende Warnungen entfernt, und es kann keine weitere Aktion für die Nachricht ergriffen werden.  Durch Auswählen **von "Auflösen"** haben Sie die Warnung im Wesentlichen ohne weitere Klassifizierung geschlossen, und sie kann für weitere Aktionen nicht erneut geöffnet werden. Alle aufgelösten Nachrichten werden auf der Registerkarte **"Aufgelöst"** angezeigt.
- **Falsch positives** Ergebnis: Sie können eine Nachricht jederzeit während des Workflows zur Nachrichtenüberprüfung als falsch positives Ergebnis auflösen. Falsch positives Ergebnis bedeutet, dass die Warnung nicht aktivierbar war oder dass die Warnung vom Benachrichtigungsprozess fälschlicherweise generiert wurde. Die Nachricht kann nicht erneut geöffnet werden, und  alle falsch positiven Nachrichten werden auf der Registerkarte "Aufgelöst" angezeigt.
- **Power Automate (Vorschau):** Verwenden Sie einen Power Automate-Fluss, um Prozessaufgaben für eine Warnmeldung zu automatisieren. Standardmäßig umfasst die Kommunikationskonformität den Notify *Manager,* wenn ein Benutzer über eine Warnungsflussvorlage für die Kommunikationskonformität verfügt, die Prüfer verwenden können, um den Benachrichtigungsprozess für Benutzer mit Nachrichtenwarnungen zu automatisieren. Weitere Informationen zum Erstellen und Verwalten von Power Automate-Flüssen in der Kommunikationskonformität finden Sie im Referenzartikel zu [Kommunikations-Compliance-Features.](communication-compliance-feature-reference.md#power-automate-flows)
- **Tag as**: Tag the message as *compliant*, *non-compliant*, or as *questionable* as it relates to the policies and standards for your organization. Das Hinzufügen von Tags und Taggingkommentaren hilft Ihnen, Richtlinienwarnungen für Eskalationen oder als Teil anderer interner Überprüfungsprozesse zu filtern. Nachdem die Markierung abgeschlossen ist, können Sie die Nachricht auch auflösen, um sie aus der ausstehenden Überprüfungswarteschlange zu verschieben.
- **Benachrichtigen**: Sie  können das Benachrichtigungssteuerelement verwenden, um der Warnung eine benutzerdefinierte Benachrichtigungsvorlage zuzuordnen und eine Warnmeldung an den Benutzer zu senden. Wählen Sie die entsprechende Benachrichtigungsvorlage aus,  die im Bereich "Kommunikationskonformitätseinstellungen" konfiguriert ist, und wählen Sie "Senden, um eine Erinnerung an den Benutzer zu senden, der die Nachricht gesendet hat, und um das Problem zu beheben". 
- **Eskalieren:** Mit dem **Steuerelement "Eskalieren"** können Sie auswählen, wer die Nachricht von anderen Personen in Ihrer Organisation überprüfen soll. Wählen Sie aus einer Liste von Prüfern aus, die in der Kommunikationskonformitätsrichtlinie konfiguriert sind, um eine E-Mail-Benachrichtigung zu senden, die eine zusätzliche Überprüfung der Nachrichtenwarnung anfordert. Der ausgewählte Prüfer kann einen Link in der E-Mail-Benachrichtigung verwenden, um direkt zu den an ihn zur Prüfung eskalierten Elementen zu gelangen.
- **Eskalieren zur Untersuchung:** Mithilfe der **Eskalation** für die Untersuchungskontrolle können Sie einen neuen [Advanced eDiscovery-Fall](overview-ediscovery-20.md) für einzelne oder mehrere Nachrichten erstellen. Sie geben einen Namen und Notizen für den neuen Fall an, und der Benutzer, der die Nachricht gesendet hat, die mit der Richtlinie übereinstimmen, wird automatisch als Fallverwahrer zugewiesen. Sie benötigen keine zusätzlichen Berechtigungen, um den Fall zu verwalten. Beim Erstellen eines Falls wird kein neues Tag für die Nachricht aufgelöst oder erstellt. Sie können insgesamt 100 Nachrichten auswählen, wenn Sie während des Korrekturprozesses einen Advanced eDiscovery-Fall erstellen. Nachrichten in allen Kommunikationskanälen, die von der Kommunikationskonformität überwacht werden, werden unterstützt. Sie können beispielsweise 50 Microsoft Teams-Chats, 25 Exchange Online-E-Mail-Nachrichten und 25 Yammer-Nachrichten auswählen, wenn Sie einen neuen Advanced eDiscovery-Fall für einen Benutzer öffnen.
- **Verbesserung der Klassifizierung (Vorschau):** Warnungen, die aus Übereinstimmungen mit Klassifizierertypen erstellt wurden, benötigen möglicherweise Feedback, um falsch positive Ergebnisse in Ihrer Organisation zu minimieren. Verwenden Sie das Steuerelement "Klassifizierung **verbessern",** um Feedback dazu zu geben, ob die Klassifizierung der Kommunikationskonformität gültig ist, oder um andere trainierbare Klassifizierungen für diese Art von Übereinstimmung zu vorschlagen. Sie können bestätigen, dass die  Klassifizierungen entweder eine Übereinstimmung oder keine Übereinstimmung *sind,* oder andere trainierbare Klassifizierungen vorschlagen, die dieser Art von Warnungsaktivität in Zukunft zugeordnet werden sollen.

    1. Wählen Sie eine Nachricht aus der Warnungsliste aus.
    2. Wählen Sie die Auslassungspunkte aus, und wählen **Sie "Klassifizierung verbessern" aus.**
    3. Wenn es **sich bei** dem Element um ein echtes positives Element handelt, wählen Sie im Feedbackbereich "Detaillierte Klassifizierung" die Option **"Übereinstimmung" aus.**  Wenn das Element fälschlicherweise als falsch positives Ergebnis in der Kategorie enthalten war, wählen Sie **"Keine Übereinstimmung" aus.**
    4. Wenn es eine andere Klassifizierung gibt, die für das Element besser geeignet ist, wählen Sie es aus der Liste "Andere trainierbare **Klassifizierer** vorschlagen" aus. Dieses Feedback löst die andere Klassifizierung aus, um das Element auszuwerten.

    > [!TIP]
    > Sie können feedback zu mehreren Elementen gleichzeitig bereitstellen, indem Sie sie alle auswählen und dann **in** der Befehlsleiste detailliertes Feedback bereitstellen auswählen.

    5. Wählen **Sie "Feedback senden"** aus, um Ihre Bewertung der Klassifizierungen  **"Übereinstimmung"** und "Keine Übereinstimmung" zu senden, und schlagen Sie andere trainierbare Klassifizierungen vor. Wenn Sie einem Klassifikator 30 Instanzen des Feedbacks bereitgestellt haben, wird er automatisch erneut trainiert. Die Erneute Schulung kann 1 bis 4 Stunden dauern. Klassifizierer können nur zweimal pro Tag erneut trainiert werden.

    > [!IMPORTANT]
    > Diese Informationen gehen an den Klassifikator in Ihrem Mandanten, **sie gehen nicht zurück zu Microsoft.**

    Weitere Informationen zum Umschulungsklassifikator für die Kommunikationskonformität finden Sie im Artikel "Wie sie einen [Klassifikator in Kommunikationskonformität erneut](classifier-how-to-retrain-comms-compliance.md) trainieren".

    ![Verbesserung der Klassifizierung der Kommunikationskonformität](../media/communication-compliance-improve-classifier.png)

- **Nachricht in Teams** entfernen: Mit dem Steuerelement "Nachricht **in Teams** entfernen" können Sie unangemessene Nachrichten und Inhalte blockieren, die in Warnungen aus Microsoft Teams-Kanälen sowie 1:1- und Gruppenchats identifiziert wurden. Entfernte Nachrichten und Inhalte werden durch einen Richtlinientipp ersetzt, in dem erläutert wird, dass sie blockiert sind und die Richtlinie, die für das Entfernen aus der Ansicht gilt. Empfänger erhalten einen Link im Richtlinientipp, um mehr über die anwendbare Richtlinie und den Überprüfungsprozess zu erfahren. Der Absender erhält einen Richtlinientipp für die blockierte Nachricht und den Inhalt, kann jedoch die Details der blockierten Nachricht und des Inhalts im Zusammenhang mit dem Entfernen überprüfen.

    ![Entfernen einer Nachricht aus Microsoft Teams](../media/communication-compliance-remove-teams-message.png)

### <a name="step-4-determine-if-message-details-should-be-archived-outside-of-communication-compliance"></a>Schritt 4: Ermitteln, ob Nachrichtendetails außerhalb der Kommunikationskonformität archiviert werden sollen

Nachrichtendetails können exportiert oder heruntergeladen werden, wenn Sie die Nachrichten in einer separaten Speicherlösung archivieren müssen. Durch Auswahl des Steuerelements **Herunterladen** werden ausgewählte Nachrichten automatisch einer ZIP-Datei hinzugefügt, die außerhalb von Microsoft 365 gespeichert werden kann.

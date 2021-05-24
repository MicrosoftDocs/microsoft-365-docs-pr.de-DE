---
title: Untersuchen und Beheben von Warnungen zur Kommunikationscompliance
description: Untersuchen und Behebung von Kommunikationskonformitätswarnungen in Microsoft 365.
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
ms.openlocfilehash: 02fbd70e7456f95ded920faa8004eedadb35d4f5
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624245"
---
# <a name="investigate-and-remediate-communication-compliance-alerts"></a>Untersuchen und Beheben von Warnungen zur Kommunikationscompliance

Nachdem Sie Ihre Kommunikationskonformitätsrichtlinien konfiguriert haben, erhalten Sie im Microsoft 365 Compliance Center Benachrichtigungen für Nachrichtenprobleme, die Ihren Richtlinienbedingungen entsprechen. Befolgen Sie hier die Workflowanweisungen, um Warnungen zu untersuchen und zu beheben.

## <a name="investigate-alerts"></a>Untersuchen von Warnungen

Der erste Schritt zur Untersuchung von Problemen, die von Ihren Richtlinien erkannt werden, besteht in der Überprüfung von Warnungen zur Kommunikationskonformität im Microsoft 365 Compliance Center. Es gibt mehrere Bereiche im Bereich der Kommunikationskonformitätslösung, die Ihnen dabei helfen, Warnungen schnell zu untersuchen, je nachdem, wie Sie die Benachrichtigungsgruppe anzeigen möchten:

- **Seite**"Kommunikationskonformitätsrichtlinie": Wenn Sie sich bei der Verwendung von Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation anmelden, wählen Sie Kommunikationskonformität aus, um die Seite Kommunikationskonformitätsrichtlinie [https://compliance.microsoft.com](https://compliance.microsoft.com) anzeigen zu  können.  Auf dieser Seite werden Richtlinien zur Kommunikationskonformität angezeigt, die für Microsoft 365 konfiguriert sind, sowie Links zu empfohlenen Richtlinienvorlagen. Jede aufgeführte Richtlinie enthält die Anzahl der Warnungen, die überprüft werden müssen, die Anzahl der eskalierten und aufgelösten Elemente, den Status der Richtlinie sowie das Datum und die Uhrzeit der letzten Richtlinienüberprüfung. Beim Auswählen einer Richtlinie werden alle ausstehenden Warnungen für Übereinstimmungen mit der Richtlinie angezeigt. Wählen Sie eine bestimmte Warnung aus, um die Seite mit den Richtliniendetails zu starten und Korrekturmaßnahmen zu ergreifen.
- **Warnungen**: Navigieren Sie zu **Kommunikationskonformitätswarnungen,** um die letzten 30 Tage von Warnungen nach Richtlinien  >   übereinstimmungen gruppieren anzuzeigen. In dieser Ansicht können Sie schnell erkennen, welche Richtlinien der Kommunikationscompliance die meisten Warnungen nach Schweregraden generieren. Wählen Sie zum Starten von Korrekturaktionen die der Warnung zugeordnete Richtlinie aus, um die Seite **Richtliniendetails zu** starten. Auf  der Seite Richtliniendetails können Sie eine Zusammenfassung  der Aktivitäten auf der Seite Übersicht anzeigen, Benachrichtigungen auf der Seite **Ausstehend** überprüfen und reagieren oder den Verlauf geschlossener Warnungen auf der Seite **Aufgelöst** überprüfen.
- **Berichte**: Navigieren Sie zu **Kommunikationskonformitätsberichte,**  >   um Widgets für Kommunikationskonformitätsbericht anzuzeigen. Jedes Widget bietet eine Übersicht über Aktivitäten und Status der Kommunikationskonformität, einschließlich Zugriff auf tiefere Einblicke in Richtlinienüberein übereinstimmungen und Korrekturaktionen.

### <a name="using-filters"></a>Verwenden von Filtern

Der nächste Schritt besteht darin, die Nachrichten zu sortieren, um die Warnungen leichter untersuchen zu können. Auf der **Seite Richtliniendetails** unterstützt die Kommunikationskonformität die mehrstufige Filterung für mehrere Nachrichtenfelder, damit Sie Nachrichten mit Richtlinien übereinstimmungen schnell untersuchen und überprüfen können. Die Filterung ist für ausstehende und gelöste Elemente für jede konfigurierte Richtlinie verfügbar. Sie können Filterabfragen für eine Richtlinie konfigurieren oder benutzerdefinierte und standardmäßige Filterabfragen für die Verwendung in jeder bestimmten Richtlinie konfigurieren. Nachdem Sie die Felder für einen Filter konfiguriert haben, werden die Filterfelder oben in der Warteschlange für die Warnmeldung angezeigt, die Sie für bestimmte Filterwerte konfigurieren können.

Eine vollständige Liste der Filter und Felddetails finden Sie unter [Filter](communication-compliance-feature-reference.md#filters) im Featurereferenzartikel.

#### <a name="to-configure-a-filter"></a>So konfigurieren Sie einen Filter

1. Melden Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 an.

2. Wechseln Sie Microsoft 365 Compliance Center zu **Kommunikationskonformität**.

3. Wählen Sie **die Registerkarte** Richtlinien aus, und wählen Sie dann eine Richtlinie für die Untersuchung aus, doppelklicken Sie auf, um die Seite **Richtlinie zu** öffnen.

4. Wählen Sie **auf der** Seite Richtlinie  entweder die Registerkarte **Ausstehend** oder Aufgelöst aus, um die Elemente zum Filtern anzeigen zu können.

5. Wählen Sie das **Steuerelement Filter** aus, um die Seite **Filterdetails** zu öffnen.

6. Aktivieren Sie mindestens ein Kontrollkästchen, um Filter für diese Warnungen zu aktivieren. Sie können aus zahlreichen Filtern auswählen, z. B. *Date*, *Sender*, *Subject/Title*, *Classifiers*, *Language* und vieles mehr.

7. Wenn Sie den als Standardfilter ausgewählten Filter speichern möchten, wählen **Sie Als Standard speichern aus.** Wenn Sie diesen Filter als gespeicherten Filter verwenden möchten, wählen Sie **Fertig aus.**

8. Wenn Sie die ausgewählten Filter als Filterabfrage speichern möchten, wählen Sie **Das** Abfragesteuerelement speichern aus, nachdem Sie mindestens einen Filterwert konfiguriert haben. Geben Sie einen Namen für die Filterabfrage ein, und wählen Sie **Speichern aus.** Dieser Filter kann nur für diese Richtlinie verwendet werden und ist im Abschnitt Gespeicherte **Filterabfragen** auf der Seite **Filterdetails** aufgeführt.

    ![Detailsteuerelemente für Kommunikationskonformitätsfilter](../media/communication-compliance-filter-detail-controls.png)

### <a name="using-near-and-exact-duplicate-analysis"></a>Verwenden der Analyse naher und genauer Duplikate

Richtlinien zur Kommunikationscompliance werden automatisch gescannt und nahe und genaue Nachrichtenduplikate ohne zusätzliche Konfigurationsschritte vorgruppiert. Mit dieser Ansicht können Sie auf ähnliche Nachrichten 1:1 oder als Gruppe schnell reagieren, wodurch die Belastung der Nachrichtenuntersuchung für Prüfer reduziert wird. Wenn Duplikate erkannt werden, werden die Steuerelemente **Nahe Duplikate** und/oder **Exakte Duplikate** in der Symbolleiste für Korrekturmaßnahmen angezeigt. Diese Ansicht ist nicht verfügbar, wenn keine näheren oder exakten Duplikate gefunden werden.

#### <a name="to-remediate-duplicates"></a>So entfernen Sie Duplikate

1. Melden Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 an.

2. Wechseln Sie Microsoft 365 Compliance Center zu **Kommunikationskonformität**.

3. Wählen Sie **die Registerkarte** Richtlinien aus, und wählen Sie dann eine Richtlinie für die Untersuchung aus, doppelklicken Sie auf, um die Seite **Richtlinie zu** öffnen.

4. Wählen Sie **auf der** Seite Richtlinie  die Registerkarte **Ausstehend** oder Aufgelöst aus, um doppelte Nachrichten anzeigen zu können.

5. Wählen Sie **die Steuerelemente Near Duplicates** oder **Exact Duplicates** aus, um die Seite Duplikatdetails zu öffnen.

6. Wählen Sie eine oder mehrere Nachrichten aus, um Aktionssteuerelemente für diese Nachrichten zu löschen.

7. Wählen **Sie Auflösen,** **Benachrichtigen,** **Eskalieren** oder **Herunterladen** aus, um die Aktion auf die ausgewählten doppelten Nachrichten als Standardfilter anzuwenden.

8. Wählen **Sie Schließen** aus, nachdem Sie die Korrekturaktionen für die Nachrichten abgeschlossen haben.

    ![Kommunikationskonformität: Exakte Duplikate von Steuerelementen](../media/communication-compliance-duplicates-controls.png)

## <a name="remediate-alerts"></a>Behebung von Warnungen

Unabhängig davon, wo Sie mit der Überprüfung von Warnungen oder der von Ihnen konfigurierten Filterung beginnen, besteht der nächste Schritt darin, Korrekturmaßnahmen zur Lösung der Warnung zu ergreifen. Starten Sie die Warnungsbehebung mithilfe des folgenden Workflows auf den **Seiten Richtlinien** oder **Warnungen.**

### <a name="step-1-examine-the-message-basics"></a>Schritt 1: Untersuchen der Grundlagen der Nachricht

 Manchmal liegt es an der Quelle oder dem Betreff nahe, dass eine Nachricht sofort behoben werden kann. Es kann sein, dass die Nachricht falsch oder falsch mit einer Richtlinie übereinstimmen und als falsch positiv aufgelöst werden sollte. Wählen Sie die Steuerung für **Fehlmeldungen**, um die Warnung sofort zu lösen und aus der Warteschlange für ausstehende Warnungen zu entfernen. Anhand der Quell- oder Absenderinformationen wissen Sie möglicherweise bereits, wie die Nachricht unter diesen Bedingungen geroutet oder behandelt werden sollte. Erwägen Sie die Verwendung der Steuerelemente **Kennzeichnen als** oder **Eskalieren**, um entsprechenden Nachrichten eine Kennzeichnung zuzuweisen oder Nachrichten an einen bestimmten Bearbeiter zu senden.

![Kommunikationskonformitätsbehebungssteuerelemente](../media/communication-compliance-remediation-controls.png)

### <a name="step-2-examine-the-message-details"></a>Schritt 2: Überprüfen der Nachrichtendetails

Nach der Überprüfung der Grundlagen der Nachricht ist es an der Zeit, eine Nachricht zu öffnen, um die Details zu untersuchen und weitere Korrekturaktionen zu ermitteln. Wählen Sie eine Nachricht aus, um den gesamten Nachrichtenkopf und die Textkörperinformationen anzuzeigen. Es stehen mehrere Ansichten zur Verfügung, die Ihnen bei der Entscheidung zur richtigen Vorgehensweise helfen:

- **Quellansicht**: Diese Ansicht ist die standardmäßige Nachrichtenansicht, die häufig in den meisten webbasierten Messaging-Plattformen zu sehen ist. Die Kopfzeileninformationen sind in der normalen Formatvorlage formatiert, und der Nachrichtentext unterstützt imbedded Grafikdateien und textgepackten Text. Wenn [die optische Zeichenerkennung (OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr) für die Richtlinie aktiviert ist, werden Bilder mit gedrucktem oder handschriftlichem Text, der richtlinienbedingten Übereinstimmungen entspricht, als untergeordnetes Element für die zugeordnete Nachricht in dieser Ansicht angezeigt.
- **Textansicht:** In der Textansicht wird eine nur zeilennummerierte Textansicht der Nachricht angezeigt, und sie enthält Die Hervorhebung von Schlüsselwörtern in Nachrichten und Anlagen für Begriffe oder Schlüsselwörter vom Typ vertraulicher Informationen, die in der zugeordneten Kommunikationskonformitätsrichtlinie übereinstimmen. Das Hervorheben von Schlüsselwörtern kann Ihnen dabei helfen, lange Nachrichten und Anlagen schnell auf den Interessenbereich zu überprüfen. In einigen Fällen kann hervorgehobener Text nur in Anlagen für Nachrichten enthalten sein, die Richtlinienbedingungen erfüllen. Die Hervorhebung von Schlüsselwörtern wird für Begriffe, die von integrierten Klassifizierungen identifiziert werden, die einer Richtlinie zugewiesen sind, nicht unterstützt. Eingebettete Dateien werden nicht angezeigt, und die Zeilennummerierung dieser Ansicht ist hilfreich, um auf relevante Details zwischen mehreren Prüfern zu verweisen.
- **Anmerkungenansicht**: In dieser Ansicht können Prüfer Anmerkungen direkt zu der Nachricht hinzufügen, die in der Nachrichtenansicht gespeichert werden. Wenn [OCR](communication-compliance-feature-reference.md#optical-character-recognition-ocr) für die Richtlinie aktiviert ist, werden Bilder, die gedruckten oder handschriftlichen Text enthalten, der richtlinienbedingten Übereinstimmungen entspricht, als untergeordnetes Element für die zugeordnete Nachricht in dieser Ansicht angezeigt und können mit Anmerkungen versehen werden.
- **Benutzerhistorie**: Die Ansicht "Benutzerhistorie" zeigt alle anderen Warnungen an, die durch eine Richtlinie zur Kommunikationscompliance für den Benutzer, der die Nachricht sendet, generiert wurden.
- **Mustererkennungsbenachrichtigung:** Viele Schikanierungs- und Mobbingaktionen im Laufe der Zeit und das erneute Auftreten von Instanzen desselben Verhaltens durch einen Benutzer. Die *Benachrichtigung "Muster erkannt"* wird in den Warnungsdetails angezeigt und weckt die Aufmerksamkeit auf die Warnung. Die Erkennung von Mustern wird auf Richtlinienbasis durchgeführt und bewertet das Verhalten in den letzten 30 Tagen, wenn mindestens zwei Nachrichten von einem Absender an denselben Empfänger gesendet werden. Ermittler und Prüfer können diese Benachrichtigung verwenden, um wiederholtes Verhalten zu identifizieren, um die Warnung gegebenenfalls auszuwerten.
- **Ansicht "Übersetzen** anzeigen": In dieser Ansicht wird der  Benachrichtigungstext automatisch in die Sprache konvertiert, die in der Einstellung Angezeigte Sprache im Microsoft 365 für jeden Prüfer konfiguriert ist. Die Translate-Ansicht hilft, die Unterstützung von Ermittlungen für Organisationen mit mehrsprachigen Benutzern zu erweitern, und es ist nicht mehr nötig, zusätzliche Übersetzungsdienste außerhalb des Prozesses zur Überprüfung der Kommunikationskonformität zu benötigen. Mithilfe von Microsoft Translate-Diensten kann die Translate-Ansicht nach Bedarf aktiviert und deaktiviert werden und unterstützt eine vielzahl von Sprachen. Eine vollständige Liste der unterstützten Sprachen finden Sie unter [Microsoft Translator Languages](https://www.microsoft.com/translator/business/languages/). Sprachen, die in der *Translator aufgeführt sind,* werden in der Ansicht Übersetzen unterstützt.

    ![Nachrichtenansichtssteuerelemente zur Kommunikationskonformität](../media/communication-compliance-message-views.png)

### <a name="step-3-decide-on-a-remediation-action"></a>Schritt 3: Entscheiden einer Korrekturaktion

Nachdem Sie nun die Details der Nachricht für die Warnung überprüft haben, können Sie mehrere Korrekturaktionen auswählen:

- **Resolve**: Durch Auswählen des **Resolve-Steuerelements** wird die Nachricht sofort aus der Warteschlange für ausstehende **Warnungen** entfernt, und es können keine weiteren Aktionen für die Nachricht ergriffen werden. Durch Auswählen **von Resolve** haben Sie die Warnung im Wesentlichen ohne weitere Klassifizierung geschlossen, und sie kann nicht erneut für weitere Aktionen geöffnet werden. Alle aufgelösten Nachrichten werden auf der Registerkarte **Aufgelöst** angezeigt.
- **Falsch positiv:** Sie können eine Nachricht jederzeit während des Workflow für die Nachrichtenüberprüfung als falsch positive Nachricht auflösen. Falsch positiv bedeutet, dass die Warnung nicht aktivierbar war oder dass die Warnung beim Benachrichtigungsprozess falsch generiert wurde. Die Nachricht kann nicht erneut geöffnet werden, und alle falsch positiven Nachrichten werden auf der Registerkarte **Aufgelöst** angezeigt.
- **Power Automate (Vorschau):** Verwenden Sie einen Power Automate, um Prozessaufgaben für eine Warnmeldung zu automatisieren. Standardmäßig umfasst die Kommunikationskonformität den *Benachrichtigungs-Manager,* wenn ein Benutzer über eine Benachrichtigungsflussvorlage zur Kommunikationskonformität verfügt, die Prüfer verwenden können, um den Benachrichtigungsprozess für Benutzer mit Nachrichtenwarnungen zu automatisieren. Weitere Informationen zum Erstellen und Verwalten von Power Automate kommunikationskonformität finden Sie im [Referenzartikel](communication-compliance-feature-reference.md#power-automate-flows) zur Kommunikationskonformität.
- **Tag as**: Tag the message as *compliant*, *non-compliant*, or as *questionable* as it relates to the policies and standards for your organization. Das Hinzufügen von Tags und Taggingkommentaren hilft Ihnen beim Mikrofiltern von Richtlinienwarnungen für Eskalationen oder als Teil anderer interner Überprüfungsprozesse. Nachdem das Tagging abgeschlossen ist, können Sie die Nachricht auch auflösen, um sie aus der warteschlange für ausstehende Überprüfungen zu verschieben.
- **Benachrichtigen**: Sie können das **Notify-Steuerelement** verwenden, um der Warnung eine benutzerdefinierte Benachrichtigungsvorlage zuzuordnen und eine Warnmeldung an den Benutzer zu senden. Wählen Sie die entsprechende Benachrichtigungsvorlage aus, die im Bereich Kommunikationskonformitätseinstellungen konfiguriert ist, und wählen Sie **Senden** an eine E-Mail-Erinnerung an den Benutzer aus, der die Nachricht gesendet hat, und um das Problem zu beheben. 
- **Eskalieren**: Mit dem **Steuerelement Eskalieren** können Sie auswählen, wer die Nachricht von anderen Personen in Ihrer Organisation überprüfen soll. Wählen Sie aus einer Liste von Prüfern aus, die in der Kommunikationskonformitätsrichtlinie konfiguriert sind, um eine E-Mail-Benachrichtigung zu senden, die eine zusätzliche Überprüfung der Nachrichtenwarnung anfordert. Der ausgewählte Prüfer kann einen Link in der E-Mail-Benachrichtigung verwenden, um direkt zu den an ihn zur Prüfung eskalierten Elementen zu gelangen.
- **Eskalieren zur Untersuchung:** Mithilfe der **Eskalation** für die [Untersuchungskontrolle](overview-ediscovery-20.md) können Sie einen neuen Fall für Advanced eDiscovery oder mehrere Nachrichten erstellen. Sie geben einen Namen und Notizen für den neuen Fall an, und der Benutzer, der die Nachricht gesendet hat, die mit der Richtlinie übereinstimmen, wird automatisch als Fallverwahrer zugewiesen. Sie benötigen keine zusätzlichen Berechtigungen, um den Fall zu verwalten. Beim Erstellen eines Falls wird kein neues Tag für die Nachricht aufgelöst oder erstellt. Sie können insgesamt 100 Nachrichten beim Erstellen eines Advanced eDiscovery während des Korrekturprozesses auswählen. Nachrichten in allen Kommunikationskanälen, die von der Kommunikationskonformität überwacht werden, werden unterstützt. Sie können beispielsweise 50 Microsoft Teams Chats, 25 Exchange Online E-Mail-Nachrichten und 25 Yammer-Nachrichten auswählen, wenn Sie einen neuen Advanced eDiscovery-Fall für einen Benutzer öffnen.
- Nachricht **in Teams** entfernen: Mithilfe des Steuerelements Nachricht **in Teams** entfernen können Sie unangemessene Nachrichten und Inhalte blockieren, die in Warnungen aus Microsoft Teams Kanälen und 1:1- und Gruppenchats identifiziert wurden. Entfernte Nachrichten und Inhalte werden durch einen Richtlinientipp ersetzt, der erläutert, dass sie blockiert ist und die Richtlinie, die für das Entfernen aus der Ansicht gilt. Empfängern wird ein Link im Richtlinientipp bereitgestellt, um mehr über die anwendbare Richtlinie und den Überprüfungsprozess zu erfahren. Der Absender erhält einen Richtlinientipp für die blockierte Nachricht und den Inhalt, kann jedoch die Details der blockierten Nachricht und des Inhalts für kontextbezogene Entfernungen überprüfen.

    ![Entfernen einer Nachricht aus Microsoft Teams](../media/communication-compliance-remove-teams-message.png)

### <a name="step-4-determine-if-message-details-should-be-archived-outside-of-communication-compliance"></a>Schritt 4: Ermitteln, ob Nachrichtendetails außerhalb der Kommunikationskonformität archiviert werden sollen

Nachrichtendetails können exportiert oder heruntergeladen werden, wenn Sie die Nachrichten in einer separaten Speicherlösung archivieren müssen. Durch Auswahl des Steuerelements **Herunterladen** werden ausgewählte Nachrichten automatisch einer ZIP-Datei hinzugefügt, die außerhalb von Microsoft 365 gespeichert werden kann.

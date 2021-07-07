---
title: Untersuchen und Beheben von Warnungen zur Kommunikationscompliance
description: Untersuchen und Beheben von Kommunikationscompliancewarnungen in Microsoft 365.
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
ms.openlocfilehash: e24b59958e5ef933b42294636ce6a1cc11528bb8
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322245"
---
# <a name="investigate-and-remediate-communication-compliance-alerts"></a>Untersuchen und Beheben von Warnungen zur Kommunikationscompliance

Nachdem Sie Ihre Richtlinien für die Kommunikationscompliance konfiguriert haben, erhalten Sie Benachrichtigungen im Microsoft 365 Compliance Center für Nachrichtenprobleme, die Ihren Richtlinienbedingungen entsprechen. Folgen Sie den Workflowanweisungen hier, um Warnungsprobleme zu untersuchen und zu beheben.

## <a name="investigate-alerts"></a>Untersuchen von Warnungen

Der erste Schritt zur Untersuchung von Problemen, die von Ihren Richtlinien erkannt werden, besteht darin, Warnungen zur Kommunikationscompliance im Microsoft 365 Compliance Center zu überprüfen. Es gibt mehrere Bereiche im Bereich der Kommunikationscompliance-Lösung, die Ihnen helfen, Warnungen schnell zu untersuchen, je nachdem, wie Sie es vorziehen, die Warnungsgruppierung anzuzeigen:

- **Seite "Kommunikationscompliancerichtlinie":** Wenn Sie sich [https://compliance.microsoft.com](https://compliance.microsoft.com) mithilfe von Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 Organisation anmelden, wählen Sie **"Kommunikationscompliance"** aus, um die Seite "Kommunikationscompliancerichtlinie" anzuzeigen.  Auf dieser Seite werden für Ihre Microsoft 365 Organisation konfigurierte Richtlinien für die Kommunikationscompliance sowie Links zu empfohlenen Richtlinienvorlagen angezeigt. Jede aufgeführte Richtlinie enthält die Anzahl der Warnungen, die überprüft werden müssen, die Anzahl der eskalierten und aufgelösten Elemente, den Status der Richtlinie sowie das Datum und die Uhrzeit der letzten Richtlinienüberprüfung. Beim Auswählen einer Richtlinie werden alle ausstehenden Warnungen für Übereinstimmungen mit der Richtlinie angezeigt. Wählen Sie eine bestimmte Warnung aus, um die Seite mit den Richtliniendetails zu starten und Korrekturmaßnahmen zu ergreifen.
- **Warnungen:** Navigieren Sie zu Warnungen zur **Kommunikationscompliance,**  >   um die letzten 30 Tage von Warnungen nach Richtlinienüberstimmungen gruppiert anzuzeigen. In dieser Ansicht können Sie schnell erkennen, welche Richtlinien der Kommunikationscompliance die meisten Warnungen nach Schweregraden generieren. Um Korrekturaktionen zu starten, wählen Sie die Richtlinie aus, die der Warnung zugeordnet ist, um die **Seite "Richtliniendetails"** zu starten. Auf der Seite **"Richtliniendetails"** können Sie eine Zusammenfassung der Aktivitäten auf der Seite **"Übersicht"** anzeigen, Warnmeldungen auf der **Seite "Ausstehend"** überprüfen und darauf reagieren oder den Verlauf geschlossener Warnungen auf der Seite **"Aufgelöst"** überprüfen.
- **Berichte:** Navigieren Sie zu **Kommunikationscomplianceberichte,**  >   um Kommunikationscompliancebericht-Widgets anzuzeigen. Jedes Widget bietet eine Übersicht über Kommunikationscomplianceaktivitäten und -status, einschließlich des Zugriffs auf tiefere Einblicke in Richtlinienüberstimmungen und Abhilfemaßnahmen.

### <a name="using-filters"></a>Verwenden von Filtern

Der nächste Schritt besteht darin, die Nachrichten zu sortieren, um die Warnungen leichter untersuchen zu können. Auf der Seite **"Richtliniendetails"** unterstützt die Kommunikationscompliance die mehrstufige Filterung nach mehreren Nachrichtenfeldern, damit Sie Nachrichten mit Richtlinienüberstimmungen schnell untersuchen und überprüfen können. Die Filterung ist für ausstehende und gelöste Elemente für jede konfigurierte Richtlinie verfügbar. Sie können Filterabfragen für eine Richtlinie konfigurieren oder benutzerdefinierte und standardmäßige Filterabfragen für die Verwendung in jeder bestimmten Richtlinie konfigurieren. Nachdem Sie die Felder für einen Filter konfiguriert haben, werden die Filterfelder oben in der Warteschlange für die Warnmeldung angezeigt, die Sie für bestimmte Filterwerte konfigurieren können.

Eine vollständige Liste der Filter und Felddetails finden Sie unter ["Filter"](communication-compliance-feature-reference.md#filters) im Featurereferenzartikel.

#### <a name="to-configure-a-filter"></a>So konfigurieren Sie einen Filter

1. Melden Sie sich [https://compliance.microsoft.com](https://compliance.microsoft.com) mithilfe von Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 Organisation an.

2. Wechseln Sie im Microsoft 365 Compliance Center zur **Kommunikationscompliance.**

3. Wählen Sie die Registerkarte **"Richtlinien"** aus, und wählen Sie dann eine Richtlinie für die Untersuchung aus, doppelklicken Sie, um die **Seite "Richtlinie"** zu öffnen.

4. Wählen Sie auf der Seite **"Richtlinie"** entweder die Registerkarte **"Ausstehend"** oder **"Aufgelöst"** aus, um die Elemente für die Filterung anzuzeigen.

5. Wählen Sie das **Filtersteuerelement aus,** um die Detailseite **"Filter"** zu öffnen.

6. Aktivieren Sie ein oder mehrere Kontrollkästchen, um Filter für diese Warnungen zu aktivieren. Sie können aus zahlreichen Filtern wählen, einschließlich *Datum,* *Absender,* *Betreff/Titel,* *Klassifizierer,* *Sprache* und mehr.

7. Wenn Sie den als Standardfilter ausgewählten Filter speichern möchten, wählen Sie **"Als Standard speichern"** aus. Wenn Sie diesen Filter als gespeicherten Filter verwenden möchten, wählen Sie **"Fertig"** aus.

8. Wenn Sie die ausgewählten Filter als Filterabfrage speichern möchten, wählen Sie **das Abfragesteuerelement speichern** aus, nachdem Sie mindestens einen Filterwert konfiguriert haben. Geben Sie einen Namen für die Filterabfrage ein, und wählen Sie **"Speichern"** aus. Dieser Filter ist nur für diese Richtlinie verfügbar und wird im Abschnitt **"Gespeicherte Filterabfragen"** der Detailseite **"Filter"** aufgeführt.

    ![Kommunikationscompliancefilter-Detailsteuerelemente](../media/communication-compliance-filter-detail-controls.png)

### <a name="using-near-and-exact-duplicate-analysis"></a>Verwenden der Analyse naher und genauer Duplikate

Richtlinien zur Kommunikationscompliance werden automatisch gescannt und nahe und genaue Nachrichtenduplikate ohne zusätzliche Konfigurationsschritte vorgruppiert. Mit dieser Ansicht können Sie schnell nacheinander auf ähnliche Nachrichten oder als Gruppe reagieren, wodurch der Aufwand für die Untersuchung von Nachrichten für Prüfer reduziert wird. Wenn Duplikate erkannt werden, werden die Steuerelemente **Nahe Duplikate** und/oder **Exakte Duplikate** in der Symbolleiste für Korrekturmaßnahmen angezeigt. Diese Ansicht ist nicht verfügbar, wenn nahe oder genaue Duplikate nicht gefunden werden.

#### <a name="to-remediate-duplicates"></a>So korrigieren Sie Duplikate

1. Melden Sie sich [https://compliance.microsoft.com](https://compliance.microsoft.com) mithilfe von Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 Organisation an.

2. Wechseln Sie im Microsoft 365 Compliance Center zur **Kommunikationscompliance.**

3. Wählen Sie die Registerkarte **"Richtlinien"** aus, und wählen Sie dann eine Richtlinie für die Untersuchung aus, doppelklicken Sie, um die **Seite "Richtlinie"** zu öffnen.

4. Wählen Sie auf der Seite **"Richtlinie"** entweder die Registerkarte **"Ausstehend"** oder **"Aufgelöst"** aus, um doppelte Nachrichten anzuzeigen.

5. Wählen Sie die Steuerelemente **"Near Duplicates"** oder **"Exact Duplicates" aus,** um die Detailseite für Duplikate zu öffnen.

6. Wählen Sie eine oder mehrere Nachrichten aus, um Aktionssteuerelemente für diese Nachrichten zu beheben.

7. Wählen Sie **"Auflösen",** **"Benachrichtigen",** **"Eskalieren"** oder **"Herunterladen"** aus, um die Aktion auf die ausgewählten doppelten Nachrichten als Standardfilter anzuwenden.

8. Wählen Sie nach Abschluss der Korrekturaktionen für die Nachrichten **"Schließen"** aus.

    ![Kommunikationscompliance – exakte Duplikate von Steuerelementen](../media/communication-compliance-duplicates-controls.png)

## <a name="remediate-alerts"></a>Beheben von Warnungen

Unabhängig davon, wo Sie mit der Überprüfung von Warnungen oder der von Ihnen konfigurierten Filterung beginnen, besteht der nächste Schritt darin, Korrekturmaßnahmen zur Lösung der Warnung zu ergreifen. Starten Sie die Warnungsbehebung mit dem folgenden Workflow auf **den** Richtlinien- oder **Benachrichtigungsseiten.**

### <a name="step-1-examine-the-message-basics"></a>Schritt 1: Untersuchen der Nachrichtengrundlagen

 Manchmal ist es aus der Quelle oder dem Betreff ersichtlich, dass eine Nachricht sofort behoben werden kann. Möglicherweise ist die Nachricht falsch oder falsch mit einer Richtlinie abgeglichen und sollte als falsch klassifiziert aufgelöst werden. Wählen Sie den **Bericht als falsch klassifiziertes** Steuerelement aus, um falsch klassifizierte Inhalte für Microsoft freizugeben, die Warnung sofort aufzulösen und aus der warenden Warnungswarteschlange zu entfernen. Anhand der Quell- oder Absenderinformationen wissen Sie möglicherweise bereits, wie die Nachricht unter diesen Bedingungen geroutet oder behandelt werden sollte. Erwägen Sie die Verwendung der Steuerelemente **Kennzeichnen als** oder **Eskalieren**, um entsprechenden Nachrichten eine Kennzeichnung zuzuweisen oder Nachrichten an einen bestimmten Bearbeiter zu senden.

![Kontrollen zur Verbesserung der Kommunikationscompliance](../media/communication-compliance-remediation-controls.png)

### <a name="step-2-examine-the-message-details"></a>Schritt 2: Überprüfen der Nachrichtendetails

Nach der Überprüfung der Nachrichtengrundlagen ist es an der Zeit, eine Nachricht zu öffnen, um die Details zu untersuchen und weitere Abhilfemaßnahmen zu ermitteln. Wählen Sie eine Nachricht aus, um den gesamten Nachrichtenkopf und die Textkörperinformationen anzuzeigen. Es stehen mehrere Ansichten zur Verfügung, die Ihnen bei der Entscheidung zur richtigen Vorgehensweise helfen:

- **Quellansicht**: Diese Ansicht ist die standardmäßige Nachrichtenansicht, die häufig in den meisten webbasierten Messaging-Plattformen zu sehen ist. Die Kopfzeileninformationen werden in der normalen Formatvorlage formatiert, und der Nachrichtentext unterstützt imbeddierte Grafikdateien und textumschlossene Wörter. Wenn [die optische Zeichenerkennung (OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr) für die Richtlinie aktiviert ist, werden Bilder, die gedruckten oder handschriftlichen Text enthalten, der der Richtlinienbedingung entspricht, als untergeordnetes Element für die zugeordnete Nachricht in dieser Ansicht angezeigt.
- **Textansicht:** In der Textansicht wird eine nur zeilennummerierte Textansicht der Nachricht angezeigt und die Schlüsselworthervorhebung in Nachrichten und Anlagen für Begriffe vertraulicher Informationstypen oder Schlüsselwörter, die in der zugeordneten Kommunikationscompliancerichtlinie übereinstimmen, eingeschlossen. Die Hervorhebung von Schlüsselwörtern kann Ihnen dabei helfen, lange Nachrichten und Anlagen schnell auf den gewünschten Bereich zu überprüfen. In einigen Fällen kann sich hervorgehobener Text nur in Anlagen für Nachrichten befinden, die Richtlinienbedingungen entsprechen. Die Hervorhebung von Schlüsselwörtern wird für Ausdrücke, die von integrierten Klassifizierern identifiziert werden, die einer Richtlinie zugewiesen sind, nicht unterstützt. Eingebettete Dateien werden nicht angezeigt, und die Zeilennummerierung dieser Ansicht ist hilfreich, um auf relevante Details unter mehreren Prüfern zu verweisen.
- **Anmerkungenansicht**: In dieser Ansicht können Prüfer Anmerkungen direkt zu der Nachricht hinzufügen, die in der Nachrichtenansicht gespeichert werden. Wenn OCR für die Richtlinie [aktiviert ist,](communication-compliance-feature-reference.md#optical-character-recognition-ocr) werden Bilder, die gedruckten oder handschriftlichen Text enthalten, der der Richtlinienbedingung entspricht, als untergeordnetes Element für die zugeordnete Nachricht in dieser Ansicht angezeigt und können kommentiert werden.
- **Unterhaltungsansicht (Vorschau):** Diese Ansicht ist für Microsoft Teams Chatnachrichten verfügbar und zeigt bis zu fünf Nachrichten vor und nach einer Warnmeldung an, damit Prüfer die Aktivität im Unterhaltungskontext anzeigen können. Dieser Kontext hilft Prüfern, Nachrichten schnell auszuwerten und fundierte entscheidungen zur Nachrichtenauflösung zu treffen. Ergänzungen zu Unterhaltungen in Echtzeit werden angezeigt, einschließlich aller Inlinebilder, Emojis und Aufkleber, die in Teams verfügbar sind. An Nachrichten angefügte Bilder oder Textdateien werden nicht angezeigt. Benachrichtigungen werden automatisch für Nachrichten angezeigt, die bearbeitet wurden, oder für Nachrichten, die aus dem Unterhaltungsfenster gelöscht wurden. Wenn eine Nachricht aufgelöst wird, werden die zugeordneten Unterhaltungsnachrichten nicht mit der aufgelösten Nachricht aufbewahrt. Unterhaltungsnachrichten sind bis zu 60 Tage lang verfügbar, nachdem die Warnmeldung identifiziert wurde.
- **Benutzerhistorie**: Die Ansicht "Benutzerhistorie" zeigt alle anderen Warnungen an, die durch eine Richtlinie zur Kommunikationscompliance für den Benutzer, der die Nachricht sendet, generiert wurden.
- **Muster erkannte Benachrichtigung:** Viele Aktionen, die sich im Laufe der Zeit wiederholen und instanzen desselben Verhaltens durch einen Benutzer beinhalten. Die *erkannten Musterbenachrichtigungen* werden in den Warnungsdetails angezeigt und lenken die Aufmerksamkeit auf die Warnung. Die Erkennung von Mustern erfolgt pro Richtlinie und wertet das Verhalten in den letzten 30 Tagen aus, wenn mindestens zwei Nachrichten von einem Absender an denselben Empfänger gesendet werden. Ermittler und Prüfer können diese Benachrichtigung verwenden, um wiederholtes Verhalten zu identifizieren, um die Warnung nach Bedarf auszuwerten.
- **Ansicht "Übersetzen" anzeigen:** In dieser Ansicht wird der Text von Warnmeldungen automatisch in die Sprache konvertiert, die in der Einstellung *"Angezeigte Sprache"* im Microsoft 365-Abonnement für jeden Prüfer konfiguriert ist. Die Translate-Ansicht hilft dabei, die Ermittlungsunterstützung für Organisationen mit mehrsprachigen Benutzern zu erweitern und die Notwendigkeit zusätzlicher Übersetzungsdienste außerhalb des Überprüfungsprozesses zur Kommunikationscompliance zu vermeiden. Mithilfe von Microsoft Translate-Diensten kann die Translate-Ansicht bei Bedarf aktiviert und deaktiviert werden und unterstützt eine Vielzahl von Sprachen. Eine vollständige Liste der unterstützten Sprachen finden Sie unter [Microsoft Translator Sprachen.](https://www.microsoft.com/translator/business/languages/) Sprachen, die in der *Translator Sprachenliste* aufgeführt sind, werden in der Ansicht "Übersetzen" unterstützt.

    ![Steuerelemente für die Nachrichtenansicht der Kommunikationscompliance](../media/communication-compliance-message-views.png)

### <a name="step-3-decide-on-a-remediation-action"></a>Schritt 3: Entscheiden sie sich für eine Korrekturmaßnahme

Nachdem Sie nun die Details der Nachricht für die Warnung überprüft haben, können Sie mehrere Korrekturaktionen auswählen:

- **Auflösen:** Wenn Sie das **Steuerelement "Auflösen"** auswählen, wird die Nachricht sofort aus der Warteschlange mit **ausstehenden Warnungen** entfernt, und es können keine weiteren Aktionen für die Nachricht ausgeführt werden. Wenn Sie **"Auflösen"** auswählen, haben Sie die Warnung im Wesentlichen ohne weitere Klassifizierung geschlossen, und sie kann nicht für weitere Aktionen erneut geöffnet werden. Alle aufgelösten Nachrichten werden auf der Registerkarte **"Aufgelöst"** angezeigt.
- **Bericht als falsch klassifiziert (Vorschau):** Sie können eine Nachricht jederzeit während des Nachrichtenüberprüfungsworkflows als falsch klassifiziert auflösen. Falsch klassifiziert bedeutet, dass die Warnung nicht umsetzbar war oder dass die Warnung vom Warnungsprozess und allen trainierbaren Klassifizierern falsch generiert wurde. Wenn das Element als falsch klassifiziert aufgelöst aufgelöst wird, werden Nachrichteninhalte, Anlagen und der Nachrichtenbetreff (einschließlich Metadaten) an Microsoft gesendet, um trainierbare Klassifizierungen zu verbessern. Daten, die an Microsoft gesendet werden, enthalten keine Informationen, die Benutzer in Ihrer Organisation identifizieren oder verwenden können. Weitere Aktionen für die Nachricht können nicht ausgeführt werden, und alle falsch klassifizierten Nachrichten werden auf der Registerkarte **"Aufgelöst"** angezeigt.
- **Power Automate (Vorschau):** Verwenden Sie einen Power Automate Ablauf, um Prozessaufgaben für eine Warnmeldung zu automatisieren. Standardmäßig umfasst die Kommunikationscompliance den *Benachrichtigungs-Manager, wenn ein Benutzer über eine Vorlage für den Kommunikationscompliance-Warnungsfluss verfügt,* die Prüfer verwenden können, um den Benachrichtigungsprozess für Benutzer mit Nachrichtenbenachrichtigungen zu automatisieren. Weitere Informationen zum Erstellen und Verwalten von Power Automate Flüssen in der Kommunikationscompliance finden Sie im Referenzartikel zu [Kommunikationscompliancefeatures.](communication-compliance-feature-reference.md#power-automate-flows)
- **Tag as:** Tag the message as *compliant*, *non-compliant*, or as *questionable* as it relates to the policies and standards for your organization. Durch das Hinzufügen von Tags und Taggingkommentaren können Sie Richtlinienwarnungen für Eskalationen oder als Teil anderer interner Überprüfungsprozesse mikrofiltern. Nachdem die Markierung abgeschlossen ist, können Sie auch die Nachricht auflösen, um sie aus der ausstehenden Überprüfungswarteschlange zu verschieben.
- **Benachrichtigen**: Sie können das **Steuerelement "Benachrichtigen"** verwenden, um der Warnung eine benutzerdefinierte Benachrichtigungsvorlage zuzuweisen und dem Benutzer einen Warnhinweis zu senden. Wählen Sie die entsprechende Benachrichtigungsvorlage aus, die im Bereich **"Kommunikationscomplianceeinstellungen"** konfiguriert ist, und wählen Sie **"Senden"** aus, um dem Benutzer, der die Nachricht gesendet hat, eine Erinnerung per E-Mail zu senden und das Problem zu beheben.
- **Eskalieren:** Mithilfe des **Steuerelements "Eskalieren"** können Sie auswählen, wer in Ihrer Organisation die Nachricht überprüfen soll. Wählen Sie aus einer Liste der Prüfer aus, die in der Richtlinie zur Kommunikationscompliance konfiguriert sind, um eine E-Mail-Benachrichtigung zu senden, die eine zusätzliche Überprüfung der Nachrichtenbenachrichtigung anfordert. Der ausgewählte Prüfer kann einen Link in der E-Mail-Benachrichtigung verwenden, um direkt zu den an ihn zur Prüfung eskalierten Elementen zu gelangen.
- **Eskalieren zur Untersuchung:** Mithilfe der **Eskalierung für die Untersuchungssteuerung** können Sie einen neuen [Advanced eDiscovery Fall](overview-ediscovery-20.md) für einzelne oder mehrere Nachrichten erstellen. Sie geben einen Namen und Notizen für den neuen Fall an, und der Benutzer, der die Nachricht gesendet hat, die mit der Richtlinie übereinstimmt, wird automatisch als Fallverwahrer zugewiesen. Sie benötigen keine zusätzlichen Berechtigungen, um den Fall zu verwalten. Das Erstellen eines Falls wird nicht aufgelöst oder ein neues Tag für die Nachricht erstellt. Sie können insgesamt 100 Nachrichten auswählen, wenn Sie während des Korrekturprozesses einen Advanced eDiscovery Fall erstellen. Nachrichten in allen Kommunikationskanälen, die von der Kommunikationscompliance überwacht werden, werden unterstützt. Sie können beispielsweise 50 Microsoft Teams Chats, 25 Exchange Online E-Mail-Nachrichten und 25 Yammer Nachrichten auswählen, wenn Sie einen neuen Advanced eDiscovery Fall für einen Benutzer öffnen.
- **Entfernen von Nachrichten in Teams:** Mithilfe der **"Nachricht in Teams-Steuerelement entfernen"** können Sie unangemessene Nachrichten und Inhalte blockieren, die in Warnungen von Microsoft Teams Kanälen und 1:1- und Gruppenchats identifiziert werden. Entfernte Nachrichten und Inhalte werden durch einen Richtlinientipp ersetzt, der erläutert, dass sie blockiert sind und die Richtlinie, die für die Entfernung aus der Ansicht gilt. Empfängern wird ein Link im Richtlinientipp bereitgestellt, um mehr über die zutreffende Richtlinie und den Überprüfungsprozess zu erfahren. Der Absender erhält einen Richtlinientipp für die blockierte Nachricht und den Inhalt, kann aber die Details der blockierten Nachricht und des Inhalts auf Kontext bezüglich der Entfernung überprüfen.

    ![Entfernen einer Nachricht aus Microsoft Teams](../media/communication-compliance-remove-teams-message.png)

### <a name="step-4-determine-if-message-details-should-be-archived-outside-of-communication-compliance"></a>Schritt 4: Ermitteln, ob Nachrichtendetails außerhalb der Kommunikationscompliance archiviert werden sollen

Nachrichtendetails können exportiert oder heruntergeladen werden, wenn Sie die Nachrichten in einer separaten Speicherlösung archivieren müssen. Durch Auswahl des Steuerelements **Herunterladen** werden ausgewählte Nachrichten automatisch einer ZIP-Datei hinzugefügt, die außerhalb von Microsoft 365 gespeichert werden kann.

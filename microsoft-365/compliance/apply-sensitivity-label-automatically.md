---
title: Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: Wenn Sie eine Vertraulichkeitsbezeichnung erstellen, können Sie eine Bezeichnung automatisch einem Dokument oder einer E-Mail zuweisen oder die Benutzer dazu auffordern, die von Ihnen empfohlene Bezeichnung auszuwählen.
ms.openlocfilehash: 7bbfb85746c114fa277f28a87c04194bd290c1fd
ms.sourcegitcommit: d1909d34ac0cddeb776ff5eb8414bfc9707d5ac1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "43163875"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a>Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit & Compliance](https://aka.ms/ComplianceSD).*

Wenn Sie ein Vertraulichkeitsbezeichnung erstellen, können Sie dieses Etikett automatisch zu Inhalt zuweisen, wenn er den von Ihnen angegebenen Bedingungen entspricht.

Die Möglichkeit, Vertraulichkeitsbezeichnungen automatisch auf Inhalte anzuwenden, ist aus den folgenden Gründen wichtig:

- Sie müssen die Benutzer nicht schulen, wann sie Ihre Klassifizierungen verwenden sollen.

- Sie müssen sich nicht darauf verlassen, dass die Benutzer alle Inhalte richtig klassifizieren.

- Benutzer müssen nicht mehr über Ihre Richtlinien Bescheid wissen, sondern können sich stattdessen auf ihre Arbeit konzentrieren.

Es gibt zwei unterschiedliche Methoden für die automatische Anwendung einer Vertraulichkeitsbezeichnung:

- **Clientseitige Bezeichnung, wenn Benutzer Dokumente bearbeiten oder E-Mails verfassen (auch beantworten oder weiterleiten)**: Verwenden Sie ein Label, das für die automatische Bezeichnung für Office-Anwendungen (Word, Excel, PowerPoint und Outlook) konfiguriert ist. 
    
    Diese Methode unterstützt das Empfehlen einer Bezeichnung für Benutzer sowie das automatische Anwenden einer Bezeichnung. In beiden Fällen entscheidet der Benutzer aber, ob die Bezeichnung angenommen oder abgelehnt werden soll, um die richtige Bezeichnung von Inhalten zu gewährleisten. Diese clientseitige Beschriftung hat nur minimale Verzögerungen für Dokumente, da die Bezeichnung noch vor dem Speichern des Dokuments angewendet werden kann. Allerdings unterstützen nicht alle Client-Apps die automatische Bezeichnung. Diese Fähigkeit wird durch den Assistent für einheitliche Bezeichnungen von Azure Information Protection und [einige Versionen von Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) unterstützt. 
    
    Konfigurationsanweisungen finden Sie unter [Konfigurieren der automatischen Bezeichnung von Office-Apps](#how-to-configure-auto-labeling-for-office-apps) auf dieser Seite.

- **Dienstseitige Kennzeichnung, wenn der Inhalt bereits gespeichert (in SharePoint Online oder OneDrive for Business) oder per E-Mail versandt (von Exchange Online verarbeitet) wurde**: Verwenden Sie eine automatische Bezeichnungsrichtlinie – aktuell in der Vorschau. 
    
    > [!NOTE]
    > Sehen Sie sich die Ankündigung der Vorschau an, die die [Public Preview der automatischen Klassifizierung mit Vertraulichkeitsbezeichnungen in Microsoft 365-Diensten ankündigt](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-public-preview-of-auto-classification-with/ba-p/1279961).
    
    Diese Methode wird Autoklassifizierung mit Vertraulichkeitsbezeichnungen genannt. Möglicherweise wird sie auch als automatische Bezeichnung für ruhende Daten (Dokumente in Microsoft Office SharePoint Online und OneDrive) und Daten im Transit (E-Mails, die von Exchange gesendet oder empfangen werden). Bei Exchange sind keine ruhenden E-Mail-Nachrichten enthalten (Postfächer). 
    
    Da diese Bezeichnung eher von Diensten als von Anwendungen angewendet wird, müssen Sie sich keine Gedanken darüber machen, welche Apps-Benutzer über welche Version verfügen. Dies hat zur Folge, dass diese Funktion sofort in ihrer gesamten Organisation zur Verfügung steht, und sie eignet sich für Bezeichnungen jeder Größe. Richtlinien zum automatischen Bezeichnen unterstützen die empfohlene Bezeichnung nicht, da der Benutzer nicht mit dem Bezeichnungsprozess interagiert. Stattdessen führt der Administrator die Richtlinien im Simulationsmodus aus, um sicherzustellen, dass der Inhalt korrekt bezeichnet wird, bevor die Bezeichnung tatsächlich angewendet wird.
    
    Konfigurationsanweisungen finden Sie unter [Konfigurieren von Richtlinien zum automatischen Bezeichnen für Microsoft Office SharePoint Online, OneDrive und Exchange](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) auf dieser Seite.
    
    Speziell für die automatische Bezeichnung von Microsoft Office SharePoint Online und OneDrive gilt:
    - maximale Anzahl von 25.000 Dateien (Word, PowerPoint oder Excel) in Ihrem Mandanten pro Tag
    - maximale Anzahl von 10 Websitesammlungen in allen Richtlinien
    - maximale Anzahl von 10 Richtlinien für den gesamten Mandanten

    Spezifisch für die automatische Bezeichnung für Exchange gilt:
    - Im Gegensatz zur manuellen oder automatischen Bezeichnung von Office-Apps werden Office-Anlagen ebenfalls auf die Bedingungen überprüft, die Sie in der Richtlinie zur automatischen Bezeichnung angeben. Wenn es eine Übereinstimmung gibt, wird die E-Mail-Adresse, aber nicht die Anlage bezeichnet.
    - Wenn Sie über Exchange-Mailflussregeln oder DLP-Richtlinien (Verhinderung von Datenverlust) verfügen, welche die IRM-Verschlüsselung anwenden: Wenn Inhalte durch diese Regeln oder Richtlinien und eine Richtlinie zum automatischen Bezeichnen identifiziert werden, wird die Bezeichnung angewendet. Wenn diese Bezeichnung Verschlüsselung anwendet, werden die IRM-Einstellungen aus den Exchange-E-Mail-Flussregeln oder DLP-Richtlinien ignoriert. Wenn diese Bezeichnung jedoch keine Verschlüsselung anwendet, werden die IRM-Einstellungen aus den E-Mail-Flussregeln oder DLP-Richtlinien zusätzlich zu der Bezeichnung angewendet.
    - E-Mails, die eine IRM-Verschlüsselung ohne Bezeichnung haben, werden durch eine Bezeichnung mit beliebigen Verschlüsselungseinstellungen ersetzt, wenn eine Übereinstimmung durch die Verwendung automatischer Bezeichnung vorliegt.
    - Eingehende E-Mails werden bezeichnet, wenn eine Übereinstimmung mit den Bedingungen für die automatische Bezeichnung vorliegt. Wenn die Bezeichnung für die Verschlüsselung konfiguriert ist, wird diese Verschlüsselung jedoch nicht angewendet.
    

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a>Vergleichen Sie das automatische Bezeichnen für Office-Anwendungen mit den Richtlinien für das automatische Bezeichnen

Verwenden Sie die folgende Tabelle, um die Unterschiede im Verhalten der beiden sich ergänzenden, automatischen Bezeichnungsmethoden zu erkennen:

|Feature oder Verhalten|Bezeichnungseinstellung: automatisches Bezeichnen für Office-Anwendungen |Richtlinie: automatisches Bezeichnen|
|:-----|:-----|:-----|:-----|
|App-Abhängigkeit|[Ja](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |Nein |
|Nach Speicherort einschränken|Nein |Ja |
|Bedingungen: trainierbare Klassifizierer|Ja (beschränkte Vorschau) |Nein |
|Bedingungen: Freigabeoptionen und zusätzliche E-Mail-Optionen|Nein |Ja |
|Empfehlungen, Richtlinien-Tooltipps und Benutzer-Außerkraftsetzungen|Ja |Nein |
|Simulationsmodus|Nein |Ja |
|Exchange-Anlagen auf Bedingungen geprüft|Nein | Ja|
|Visuelle Markierungen anwenden |Ja |Ja (nur E-Mail) |
|Außerkraftsetzen der IRM-Verschlüsselung ohne Bezeichnung angewendet|Ja, wenn der Benutzer das Mindestnutzungsrecht des Exportierens hat |Ja (nur E-Mail) |
|Bezeichnen eingehender E-Mails|Nein |Ja (Verschlüsselung nicht angewendet) |

> [!NOTE]
> Wenn der Inhalt manuell bezeichnet wurde, wird diese Bezeichnung niemals durch automatisches Bezeichnen ersetzt. Richtlinien der automatischen Bezeichnung können jedoch eine [Bezeichnung niedrigerer Priorität](sensitivity-labels.md#label-priority-order-matters) ersetzen, das durch die Verwendung der automatischen Bezeichnung für Office-Anwendungen angewendet wurde.

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a>Auswerten mehrerer Kriterien, wenn sie für mehr als eine Bezeichnung zutreffen

Die Bezeichnungen werden je nach Position, die Sie in der Richtlinie festlegen, sortiert: die Bezeichnung an erster Stelle hat die niedrigste Position (am wenigsten vertraulich) und die Bezeichnung an letzter Stelle hat die höchste Position (am meisten vertraulich). Weitere Informationen zur Priorität finden Sie unter [Priorität der Bezeichnungen (Reihenfolge wesentlich)](sensitivity-labels.md#label-priority-order-matters).

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a>Konfigurieren Sie keine übergeordnete Bezeichnung, die automatisch angewendet oder empfohlen wird.

Denken Sie daran, dass Sie eine übergeordnete Bezeichnung (eine Bezeichnung mit Unterbezeichnungen) nicht auf Inhalt anwenden können. Stellen Sie sicher, dass Sie eine übergeordnete Bezeichnung nicht so konfigurieren, dass sie automatisch angewendet oder empfohlen wird, da die übergeordnete Bezeichnung nicht auf Inhalt in Office-Apps angewendet wird, die den Azure Information Protection-Client mit einheitlichen Bezeichnungen verwenden. Weitere Informationen zu übergeordneten Bezeichnungen und Unterbezeichnungen finden Sie unter [Unterbezeichnungen (Gruppierungsbezeichnungen)](sensitivity-labels.md#sublabels-grouping-labels).

## <a name="how-to-configure-auto-labeling-for-office-apps"></a>Konfigurieren der automatischen Bezeichnung für Office-Apps

Die automatische Zuweisung von Bezeichnungen in Office-Apps für Windows wird durch den Client mit einheitlichen Bezeichnungen von Azure Information Protection unterstützt. Für integrierte Bezeichnungen in Office-Apps befindet sich diese Funktion [für einigen Apps in der Vorschau](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

Die Einstellungen für automatische Zuweisung von Bezeichnungen für Office-Apps sind verfügbar, wenn Sie [eine Vertraulichkeitsbezeichnung erstellen oder bearbeiten](create-sensitivity-labels.md):

![Optionen der automatischen Zuweisung von Bezeichnungen für Vertraulichkeitsbezeichnungen](../media/sensitivity-labels-auto-labeling-options.png)

Sie können sich dafür entscheiden, Inhalten automatisch Vertraulichkeitsbezeichnungen zuzuordnen, wenn diese Inhalte bestimmte Arten von sensiblen Informationen enthalten. Wählen Sie aus einer Liste von Arten von sensiblen Informationen oder Klassifizierungen:

![Bezeichnungsbedingungen für die automatische Zuweisung von Bezeichnungen in Office-Apps](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> Derzeit befindet sich die Option für **Klassifizierungen** in einer begrenzten Vorschau und erfordert, dass Sie ein Formular an Microsoft senden, um diese Funktion für Ihren Mandanten zu aktivieren. Weitere Informationen finden Sie im Blogbeitrag [Announcing automatic labeling in Office Apps using built-in classifiers – Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889) (Ankündigung der automatischen Zuweisung von Bezeichnungen in Office-Apps mit integrierten Klassifizierungen – begrenzte Vorschau).

Wenn eine Vertraulichkeitsbezeichnung automatisch angewendet wird, wird dem Benutzer eine Benachrichtigung in der Office-App angezeigt. Zum Beispiel:

![Benachrichtigung darüber, dass ein Dokument automatisch mit einer Bezeichnung versehen wurde](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a>Konfigurieren von Typen vertraulicher Informationen für eine Bezeichnung

Wenn Sie die Option **Typen vertraulicher Informationen** auswählen, wird dieselbe Liste von vertraulichen Informationen wie beim Erstellen einer DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust) angezeigt. So können Sie z. B. auf alle Inhalte, die persönlich identifizierbare Informationen (PII) von Kunden enthalten, wie z. B. Kreditkartennummern oder Sozialversicherungsnummern, automatisch die Bezeichnung "Streng vertraulich" anwenden:

![Typen vertraulicher Informationen für die automatische Zuweisung von Bezeichnungen in Office-Apps](../media/sensitivity-labels-sensitive-info-types.png)

Nachdem Sie die Typen vertraulicher Informationen ausgewählt haben, können Sie die Kriterien eingrenzen, indem Sie die Instanzenanzahl oder Übereinstimmungsgenauigkeit ändern. Weitere Informationen finden Sie unter [Optimieren von Regeln, um die Übereinstimmung zu vereinfachen oder zu erschweren](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).

Darüber hinaus können Sie auswählen, ob eine Bedingung alle vertraulichen Informationstypen oder nur einen dieser Typen erkennen muss. Und um Ihre Bedingungen flexibler oder komplexer zu gestalten, können Sie Gruppen hinzufügen und logische Operatoren zwischen den Gruppen verwenden. Weitere Informationen finden Sie unter [Gruppieren und logische Operatoren](data-loss-prevention-policies.md#grouping-and-logical-operators).

![Optionen für Instanzenanzahl und Übereinstimmungsgenauigkeit](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a>Konfigurieren von Klassifizierungen für eine Bezeichnung

Wenn Sie die Option **Klassifizierungen** auswählen, wählen Sie eine oder mehrere der integrierten Klassifizierungen aus:

![Optionen für Klassifizierungen und Vertraulichkeitsbezeichnungen](../media/sensitivity-labels-classifers.png)

Weitere Informationen zu diesen Klassifizierungen finden Sie unter [Erste Schritte mit trainierbaren Klassifizierungen (Vorschau)](classifier-getting-started-with.md).

Während des Vorschauzeitraums unterstützen die folgenden Apps Klassifizierungen für Vertraulichkeitsbezeichnungen:

- Office 365 ProPlus-Desktop-Apps für Windows, von [Office Insider](https://office.com/insider):
    - Word
    - Excel
    - PowerPoint

- Office für das Web-Apps, wenn Sie über [aktivierte Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive (öffentliche Vorschau)](sensitivity-labels-sharepoint-onedrive-files.md) verfügen:
    - Word
    - Excel
    - PowerPoint
    - Outlook

### <a name="recommend-that-the-user-applies-a-sensitivity-label-in-office-apps"></a>Empfehlen des Anwendens einer Vertraulichkeitsbezeichnung in Office-Apps

Wenn Sie es vorziehen, können Sie Ihren Benutzern empfehlen, die Bezeichnung anzuwenden. Mithilfe dieser Option können Ihre Benutzer die Klassifizierung und alle zugehörigen Schutzmaßnahmen akzeptieren oder die Empfehlung zurückweisen, wenn die Bezeichnung für ihre Inhalte ungeeignet ist.

![Option zum Empfehlen einer Vertraulichkeitsbezeichnung](../media/Sensitivity-labels-Recommended-label-option.png)

Im Folgenden finden Sie ein Beispiel für eine Aufforderung des Azure Information Protection-Clients mit einheitlichen Bezeichnungen, wenn Sie eine Bedingung zum Anwenden einer Bezeichnung als empfohlene Aktion konfigurieren, und einen benutzerdefinierten Richtlinientipp. Sie können den Text festlegen, der im Richtlinientipp angezeigt wird.

![Aufforderung zum Anwenden einer empfohlene Bezeichnung](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied-in-office-apps"></a>Wenn automatische oder empfohlene Bezeichnungen in Office-Anwendungen angewendet werden

Die Implementierung der automatischen und empfohlenen Bezeichnung in Office-Apps hängt davon ab, ob Sie eine in Office integrierte Bezeichnung oder den Azure Information Protection-Client mit einheitlichen Bezeichnungen verwenden. In beiden Fällen gilt jedoch:

- Sie können keine automatische Zuweisung von Bezeichnungen für Dokumente und E-Mails verwenden, die zuvor manuell bezeichnet oder automatisch mit einer höheren Vertraulichkeit gekennzeichnet wurden. Denken Sie daran, dass Sie einem Dokument oder einer E-Mail-Nachricht nur eine einzige Vertraulichkeitsbezeichnung zuweisen können (zusätzlich zu einer einzigen Aufbewahrungsbezeichnung).

- Sie können die empfohlenen Bezeichnungen für Dokumente oder E-Mails, die zuvor mit einer höheren Vertraulichkeit gekennzeichnet wurden, nicht verwenden. Wenn der Inhalt bereits mit einer höheren Vertraulichkeit gekennzeichnet ist, wird dem Benutzer die Eingabeaufforderung mit der Empfehlung und dem Richtlinientipp nicht angezeigt.

Spezifisch für integrierte Bezeichnungen:

- Nicht alle Office-Apps unterstützen automatische (und empfohlene) Bezeichnungen. Weitere Informationen finden Sie unter [Unterstützung der Funktion Vertraulichkeitsbezeichnungen in Apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

- Bei empfohlenen Bezeichnungen in den Desktopversionen von Word wird der sensible Inhalt, der die Empfehlung ausgelöst hat, markiert, sodass Benutzer den sensiblen Inhalt überprüfen und entfernen können, anstatt die empfohlene Vertraulichkeitsbezeichnung anzuwenden.

- Ausführliche Informationen dazu, wie diese Bezeichnungen in Office-Apps angewendet werden, Beispielscreenshots und wie vertrauliche Informationen erkannt werden, finden Sie unter [Automatisches Anwenden oder Empfehlen von Vertraulichkeitsbezeichnungen für Ihre Dateien und E-Mails in Office](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).

Spezifisch für Azure Information Protection-Clients mit einheitlichen Bezeichnungen:

-  Automatische und empfohlene Bezeichnungen gelten für Word, Excel und PowerPoint beim Speichern eines Dokuments, und für Outlook beim Senden einer E-Mail.

- Damit Outlook die empfohlenen Bezeichnungen unterstützt, müssen Sie zunächst eine [erweiterte Richtlinieneinstellung](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook) konfigurieren.

- Vertrauliche Informationen können im Text von Dokumenten und E-Mails sowie in Kopf- und Fußzeilen, aber nicht in der Betreffzeile oder E-Mail-Anlagen erkannt werden.

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a>Konfigurieren von Richtlinien für die automatische Bezeichnung von Microsoft Office SharePoint Online, OneDrive und Exchange
> [!NOTE]
> Richtlinien der automatischen Bezeichnung werden nach und nach in Public Preview und vorbehaltlich Änderungen an Mandanten bereitgestellt.

### <a name="prerequisites-for-auto-labeling-policies"></a>Voraussetzungen für Richtlinien der automatischen Bezeichnung

- Die Überwachung von Office 365 muss für den Simulationsmodus aktiviert sein. Wenn Sie die Überwachung aktivieren oder sich nicht sicher sind, ob die Überwachung bereits aktiviert ist, lesen Sie [Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche](turn-audit-log-search-on-or-off.md).

- Automatisches Bezeichnen von Dateien in Microsoft Office SharePoint Online und OneDrive:
    - Sie haben [Vertraulichkeitsbezeichnungen für Office-Dateien in Microsoft Office SharePoint Online und OneDrive (Public Preview) aktiviert](sensitivity-labels-sharepoint-onedrive-files.md).
    - Zum Zeitpunkt der Ausführung der Richtlinie zum automatischen Bezeichnen darf die Datei nicht von einem anderen Prozess oder Benutzer geöffnet sein.

- Wenn Sie vorhaben, anstelle der integrierten Vertraulichkeitstypen [benutzerdefinierte sensible Informationstypen](custom-sensitive-info-types.md) zu verwenden: 
    - Benutzerdefinierte Vertraulichkeitsinformationstypen werden für Inhalte ausgewertet, die nach dem Speichern der benutzerdefinierten Vertraulichkeitsinformationstypen erstellt werden. 
    - Um neue benutzerdefinierte Typen sensibler Informationen zu testen, erstellen Sie diese, bevor Sie Ihre Richtlinie zum automatischen Bezeichnen erstellen, und erstellen Sie dann neue Dokumente mit Beispieldaten zum Testen.

- Eine oder mehrere Vertraulichkeitsbezeichnungen [erstellt und veröffentlicht](create-sensitivity-labels.md) (für mindestens einen Benutzer), die Sie für Ihre Richtlinie der automatischen Bezeichnung auswählen können. Für diese Bezeichnungen:
    - Es spielt keine Rolle, ob das automatische Bezeichnen in den Bezeichnungseinstellungen der Office-Anwendungen ein- oder ausgeschaltet ist, da diese Bezeichnungseinstellungen die Richtlinien für die automatische Bezeichnung ergänzen, wie in der Einführung erläutert. 
    - Wenn die Etiketten, die Sie für die automatische Bezeichung verwenden möchten, für die Verwendung visueller Markierungen (Kopf- und Fußzeilen, Wasserzeichen) konfiguriert sind, beachten Sie, dass diese nicht auf Dokumente angewendet werden.

### <a name="learn-about-simulation-mode"></a>Informationen zum Simulationsmodus

Der Simulationsmodus ist einzigartig für Richtlinien zum automatischen Bezeichnen und in den Arbeitsablauf eingearbeitet. Sie können Dokumente und E-Mails erst dann automatisch bezeichnen, wenn Ihre Richtlinie mindestens eine Simulation ausgeführt hat.

Workflow für die Richtlinie zum automatischen Bezeichnen:

1. Erstellen und Konfigurieren einer Richtlinie zum automatischen Bezeichnen

2. Führen Sie die Richtlinie im Simulationsmodus aus und warten Sie mindestens 24 Stunden.

3. Überprüfen Sie die Ergebnisse, und verfeinern Sie, falls erforderlich, Ihre Richtlinie, führen Sie den Simulationsmodus erneut durch, und warten Sie mindestens 24 Stunden.

4. Wiederholen Sie Schritt 3 nach Bedarf.

5. Bereitstellen in der Produktion

Die simulierte Bereitstellung wird wie der WhatIf-Parameter für PowerShell ausgeführt. Die Ergebnisse werden so gemeldet, als ob die Richtlinie zum automatischen Bezeichnen Ihre ausgewählte Bezeichnung unter Verwendung der von Ihnen definierten Regeln angewendet hätte. Sie können dann bei Bedarf Ihre Genauigkeitsregeln verfeinern und die Simulation erneut ausführen. Da die automatische Bezeichnung für Exchange für E-Mails gilt, die gesendet und empfangen werden, und nicht für E-Mails, die in Postfächern gespeichert sind, erwarten Sie jedoch nicht, dass die Ergebnisse für E-Mails in einer Simulation konsistent sind, es sei denn, Sie sind in der Lage, genau die gleichen E-Mail-Nachrichten zu senden und zu empfangen.

Mit dem Simulationsmodus können Sie auch den Umfang Ihrer Richtlinie zum automatischen Bezeichnen vor dem Einsatz schrittweise vergrößern. Sie können z. B. mit einem einzigen Ort, wie z. B. einer Microsoft Office SharePoint Online-Website, mit einer einzigen Dokumentbibliothek beginnen. Erweitern Sie dann mit iterativen Änderungen den Geltungsbereich auf mehrere Standorte und dann auf einen anderen Standort, z. B. OneDrive.

Schließlich können Sie den Simulationsmodus verwenden, um einen Näherungswert für die Zeit zu erhalten, die für die Ausführung Ihrer Richtlinie zum automatischen Bezeichnen benötigt wird, um Ihnen bei der Planung und Terminierung zu helfen, wann diese ohne Simulationsmodus ausgeführt werden soll.

### <a name="creating-an-auto-labeling-policy"></a>Erstellen einer Richtlinie für die automatische Bezeichnung

1. Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu Vertraulichkeitsbezeichnungen:
    
    - **Lösungen** > **Informationsschutz**
    
    Wenn diese Option nicht sofort angezeigt wird, wählen Sie zunächst **Alle anzeigen** aus.

2. Wählen Sie die Registerkarte **Automatisches Bezeichnen (Vorschau)** aus:
    
    ![Registerkarte „Automatisches Bezeichnen“ (Vorschau)](../media/auto-labeling-tab.png)

3. Wählen Sie **+ Richtlinie erstellen** aus.

4. Wählen Sie für die Seite **Informationen auswählen, auf die diese Bezeichnung angewendet werden soll**, eine der Vorlagen aus, z. B. **Finanzen** oder **Datenschutz**. Sie können die Suche verfeinern, indem Sie die Dropdownliste **Optionen anzeigen für** verwenden. Sie können aber auch **Benutzerdefinierte Richtlinie** auswählen, wenn die Vorlagen Ihren Anforderungen nicht entsprechen. Wählen Sie **Weiter** aus.

5. Für die Seite **Benennen Sie Ihre Richtlinie zum automatischen Bezeichnen**: Geben Sie einen eindeutigen Namen und optional eine Beschreibung an, um die automatisch angewandte Bezeichnung, die Speicherorte und Bedingungen zu identifizieren, die den zu bezeichnenden Inhalt identifizieren.

6. Für die Seite **Wählen Sie Orte aus, an denen Sie die Bezeichnung anwenden möchten**: Wählen und geben Sie Orte für Exchange, Microsoft Office SharePoint Online-Websites und OneDrive an. Wählen Sie dann **Weiter** aus.

7. Für die **Richtlinieneinstellungen definieren** Seite: Behalten Sie die Standardeinstellung **Inhalte suchen, der enthält** bei, um Regeln zu definieren, mit denen zu bezeichnende Inhalte für alle ausgewählten Speicherorte identifiziert werden. Wenn Sie pro Speicherort unterschiedliche Regeln benötigen, wählen Sie **Erweiterte Einstellungen** aus. Wählen Sie dann **Weiter** aus.
    
    Die Regeln verwenden Bedingungen, die sensible Informationstypen und Freigabeoptionen umfassen:
    - Sie können integrierte und benutzerdefinierte Typen für vertrauliche Informationen auswählen.
    - Bei den freigegebenen Optionen können Sie **nur für Personen in meiner Organisation** oder **mit Personen außerhalb meiner Organisation** auswählen.
    
    Wenn Ihr einziger Speicherort **Exchange ** ist oder Sie **Erweiterte Einstellungen** auswählen, können Sie zusätzliche Bedingungen auswählen:
    - IP-Adresse des Absenders lautet
    - Empfängerdomäne lautet
    - Empfänger lautet
    - Dateierweiterung der Anlage lautet
    - Anlage ist passwortgeschützt
    - Dokumenteigenschaft lautet
    - Der Inhalt einer E-Mail-Anlage konnte nicht vollständig gescannt werden
    - Der Inhalt einer E-Mail-Anlage wurde nicht vollständig gescannt

8. Für die Seite **Regeln einrichten, um zu definieren, welche Inhalte bezeichnet werden**: Wählen Sie **+ Regel erstellen** und dann **Nächste** aus.

9. Benennen und definieren Sie auf der Seite **Regel erstellen** die Regel unter Verwendung von sensibler Informationstypen oder der Freigabeoption, und wählen Sie dann **Speichern** aus.
    
    Die Konfigurationsoptionen für Typen sensibler Informationen sind die gleichen wie die, die Sie für das automatische Bezeichnen von Office-Anwendungen auswählen. Wenn Sie weitere Informationen benötigen, lesen Sie [Konfigurieren sensibler Informationstypen für eine Bezeichnung](#configuring-sensitive-info-types-for-a-label).

10. Zurück zur Seite **Regeln einrichten, um zu definieren, welche Inhalte bezeichnet werden**: Wählen Sie erneut **+ Regel erstellen** aus, wenn Sie eine weitere Regel benötigen, um den zu bezeichnenden Inhalt zu identifizieren, und wiederholen Sie den vorherigen Schritt. Wenn Sie alle erforderlichen Regeln definiert und bestätigt haben, dass der Status aktiviert ist, wählen Sie **nächsten**aus.

11. Für die Seite **Wählen Sie eine Bezeichnung zum automatischen Bezeichnen aus**: Wählen Sie **+ Wählen Sie eine Bezeichnung aus**, eine Bezeichnung aus dem Bereich **Wählen Sie ein Vertraulichkeitsbezeichnung** und dann **Weiter** aus.

12. Wählen Sie für die Seite **Wählen Sie einen Modus für die Richtlinie aus** **Probieren Sie ihn aus** aus, wenn Sie die Richtlinie für die automatische Bezeichnung jetzt im Simulationsmodus ausführen möchten. Andernfalls wählen Sie **Deaktiviert lassen** aus. Wählen Sie **Weiter** aus. 

13. Auf der Seite **Zusammenfassung**: Überprüfen Sie die Konfiguration der Richtlinie für die automatische Bezeichnung, nehmen Sie die erforderlichen Änderungen vor, und schließen Sie den Assistenten ab.
    
    Im Gegensatz zur automatischen Bezeichnung für Office-Anwendungen gibt es keine separate Veröffentlichungsoption. Wie bei Veröffentlichungsbezeichnungen sollten Sie jedoch bis zu 24 Stunden Zeit einräumen, damit sich die Richtlinie für die automatische Bezeichnung in Ihrer gesamten Organisation replizieren kann.

Auf der Seite **Informationsschutz** der Registerkarte **Automatische Bezeichnung (Vorschau)** wird die Richtlinie zur automatischen Bezeichnung im Abschnitt **Test** angezeigt. Wählen Sie Ihre Richtlinie aus, um die Details der Konfiguration und des Status zu sehen (z. B. "wird noch getestet" oder "Test abgeschlossen"). Wählen Sie die Registerkarte **Übereinstimmende Elemente** aus, um zu sehen, welche E-Mails oder Dokumente den von Ihnen festgelegten Regeln entsprechen.

Sie können Ihre Richtlinie direkt über diese Benutzeroberfläche ändern, indem Sie oben auf der Seite die Option **Bearbeiten** auswählen.

Wenn Sie die Richtlinie ohne Simulation ausführen möchten, wählen Sie die Option **Aktivieren** aus.

Sie können die Ergebnisse der Richtlinie für die automatische Bezeichnung auch anzeigen, indem Sie [Inhalts-Explorer](data-classification-content-explorer.md) verwenden, wenn Sie über die entsprechenden [Berechtigungen](data-classification-content-explorer.md#permissions) verfügen:
- In der **Inhalts-Explorer-Listenanzeige** können Sie die Bezeichnung einer Datei anzeigen, aber nicht den Inhalt der Datei.
- **Inhalts-Explorer-Inhaltsanzeige** können Sie den Inhalt der Datei anzeigen.

> [!TIP]
> Sie können den Inhalts-Explorer auch verwenden, um Speicherorte zu identifizieren, die nicht bezeichnete Dokumente mit sensiblen Informationen enthalten. Anhand dieser Informationen können Sie diese Speicherorte ihrer Richtlinie zur automatischen Bezeichnung hinzufügen und die identifizierten Typen vertraulicher Informationen als Regeln aufnehmen.



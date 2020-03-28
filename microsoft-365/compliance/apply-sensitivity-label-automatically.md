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
ms.openlocfilehash: 7edfa83648ecb86ab23a898299edb63df851d123
ms.sourcegitcommit: 7eaecb91c7cb1f8679f99882563f5c1149175992
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "43022932"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a>Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte

Wenn Sie eine Vertraulichkeitsbezeichnung erstellen, können Sie diese Bezeichnung automatisch Inhalten mit vertraulichen Informationen zuweisen oder die Benutzer dazu auffordern, die von Ihnen empfohlene Bezeichnung anzuwenden.

Die Möglichkeit, Vertraulichkeitsbezeichnungen automatisch auf Inhalte anzuwenden, ist aus den folgenden Gründen wichtig:

- Sie müssen die Benutzer nicht schulen, damit sie alle Ihre Klassifizierungen kennen.

- Sie müssen sich nicht darauf verlassen, dass die Benutzer alle Inhalte richtig klassifizieren.

- Benutzer müssen nicht mehr über Ihre Richtlinien Bescheid wissen, sondern können sich stattdessen auf ihre Arbeit konzentrieren.

Die automatische Zuweisung von Bezeichnungen in Office-Apps für Windows wird durch den Client mit einheitlichen Bezeichnungen von Azure Information Protection unterstützt. Für integrierte Bezeichnungen in Office-Apps befindet sich diese Funktion [für einigen Apps in der Vorschau](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

Die Einstellungen für automatische Zuweisung von Bezeichnungen für Office-Apps sind verfügbar, wenn Sie [eine Vertraulichkeitsbezeichnung erstellen oder bearbeiten](create-sensitivity-labels.md):

![Optionen der automatischen Zuweisung von Bezeichnungen für Vertraulichkeitsbezeichnungen](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a>Konfigurieren der automatischen Zuweisung von Bezeichnungen für Office-Apps

Eines der leistungsstärksten Features von Vertraulichkeitsbezeichnungen ist die Möglichkeit, sie automatisch auf Inhalte anzuwenden, die spezielle Bedingungen erfüllen. In diesem Fall müssen die Personen in Ihrer Organisation die Vertraulichkeitsbezeichnungen nicht selber anwenden – dies erledigt Office 365 automatisch.

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

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a>Empfehlen des Anwendens einer Vertraulichkeitsbezeichnung

Wenn Sie es vorziehen, können Sie Ihren Benutzern empfehlen, die Bezeichnung anzuwenden. Mithilfe dieser Option können Ihre Benutzer die Klassifizierung und alle zugehörigen Schutzmaßnahmen akzeptieren oder die Empfehlung zurückweisen, wenn die Bezeichnung für ihre Inhalte ungeeignet ist.

![Option zum Empfehlen einer Vertraulichkeitsbezeichnung](../media/Sensitivity-labels-Recommended-label-option.png)

Im Folgenden finden Sie ein Beispiel für eine Aufforderung des Azure Information Protection-Clients mit einheitlichen Bezeichnungen, wenn Sie eine Bedingung zum Anwenden einer Bezeichnung als empfohlene Aktion konfigurieren, und einen benutzerdefinierten Richtlinientipp. Sie können den Text festlegen, der im Richtlinientipp angezeigt wird.

![Aufforderung zum Anwenden einer empfohlene Bezeichnung](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a>Anwenden automatischer oder empfohlener Bezeichnungen

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

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a>Auswerten mehrerer Kriterien, wenn sie für mehr als eine Bezeichnung zutreffen

Die Bezeichnungen werden je nach Position, die Sie in der Richtlinie festlegen, sortiert: die Bezeichnung an erster Stelle hat die niedrigste Position (am wenigsten vertraulich) und die Bezeichnung an letzter Stelle hat die höchste Position (am meisten vertraulich). Weitere Informationen zur Priorität finden Sie unter [Priorität der Bezeichnungen (Reihenfolge wesentlich)](sensitivity-labels.md#label-priority-order-matters).

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a>Konfigurieren Sie keine übergeordnete Bezeichnung, die automatisch angewendet oder empfohlen wird.

Denken Sie daran, dass Sie eine übergeordnete Bezeichnung (eine Bezeichnung mit Unterbezeichnungen) nicht auf Inhalt anwenden können. Stellen Sie sicher, dass Sie eine übergeordnete Bezeichnung nicht so konfigurieren, dass sie automatisch angewendet oder empfohlen wird, da die übergeordnete Bezeichnung nicht auf Inhalt in Office-Apps angewendet wird, die den Azure Information Protection-Client mit einheitlichen Bezeichnungen verwenden. Weitere Informationen zu übergeordneten Bezeichnungen und Unterbezeichnungen finden Sie unter [Unterbezeichnungen (Gruppierungsbezeichnungen)](sensitivity-labels.md#sublabels-grouping-labels).

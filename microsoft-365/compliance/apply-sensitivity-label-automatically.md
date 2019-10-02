---
title: Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte
ms.author: laurawi
author: laurawi
manager: laurawi
audience: Admin
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: Wenn Sie eine Vertraulichkeitsbezeichnung erstellen, können Sie eine Bezeichnung automatisch einem Dokument oder einer E-Mail zuweisen oder die Benutzer dazu auffordern, die von Ihnen empfohlene Bezeichnung auszuwählen.
ms.openlocfilehash: f0287eff3a462bc6f30c18c561203ba1a9a9dc19
ms.sourcegitcommit: 1eecd7b127462585c35b0c96a179d37db45f6013
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "37343108"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a>Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte

Wenn Sie eine Vertraulichkeitsbezeichnung erstellen, können Sie diese Bezeichnung automatisch Inhalten mit vertraulichen Informationen zuweisen oder die Benutzer dazu auffordern, die von Ihnen empfohlene Bezeichnung anzuwenden.

Die Möglichkeit, Vertraulichkeitsbezeichnungen automatisch auf Inhalte anzuwenden, ist aus den folgenden Gründen wichtig:

- Sie müssen die Benutzer nicht schulen, damit sie alle Ihre Klassifizierungen kennen.

- Sie müssen sich nicht darauf verlassen, dass die Benutzer alle Inhalte richtig klassifizieren.

- Benutzer müssen nicht mehr über die Richtlinien Bescheid wissen, sondern können sich stattdessen auf ihre Arbeit konzentrieren.

> [!NOTE]
> Für die Funktion zum automatischen Anwenden von Bezeichnungen ist ein Azure Information Protection P2-Abonnement erforderlich. Um diese Funktion zu verwenden, müssen Sie [den Azure Information Protection-Client für einheitliche Bezeichnungen herunterladen und installieren](https://docs.microsoft.com/de-DE/azure/information-protection/rms-client/install-unifiedlabelingclient-app). Wir arbeiten an einer systemeigenen Unterstützung für diese Funktion in Office-Apps, damit der Azure Information Protection-Client für einheitliche Bezeichnungen nicht länger erforderlich ist. Darüber hinaus wird der Client für einheitliche Bezeichnungen nur unter Windows ausgeführt, sodass die Funktion derzeit nicht unter Mac, iOS und Android unterstützt wird.

Die Bezeichnungseinstellungen sind verfügbar, wenn Sie eine Vertraulichkeitzbezeichnung im Microsoft 365 Compliance Center, Microsoft 365 Security Center oder Office 365 Security & Compliance Center unter **Klassifizierung** > **Vertraulichkeitsbezeichnungen** erstellen.

![Automatische Bezeichnungsoptionen für Vertraulichkeitsbezeichnungen](media/Sensitivity-labels-Auto-labeling-options.png)

## <a name="apply-a-sensitivity-label-automatically-based-on-conditions"></a>Automatisches Anwenden einer Vertraulichkeitsbezeichnung basierend auf Kriterien

Eines der leistungsstärksten Funktionen von Vertraulichkeitsbezeichnungen ist die Möglichkeit, sie automatisch auf Inhalte anzuwenden, die bestimmte Kriterien erfüllen. In diesem Fall müssen Personen in Ihrer Organisation die Vertraulichkeitsbezeichnungen nicht selbst anwenden – Office 365 erledigt dies für sie.
   
Sie können festlegen, dass Vertraulichkeitsbezeichnungen automatisch auf Inhalte angewendet werden, wenn bestimmte Typen vertraulicher Informationen enthalten sind. Wenn Se festlegen, dass eine Vertraulichkeitsbezeichnung automatisch angewendet werden soll, wird dieselbe Liste mit Typen vertraulicher Informationen angezeigt wie beim Erstellen einer DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust). So können Sie z. B. automatisch die Bezeichnung „Streng vertraulich“ auf Inhalte anwenden, die personenbezogene Kundendaten wie Kreditkartennummern oder Sozialversicherungsnummern enthalten. 

![Optionen für Instanzenanzahl und Übereinstimmungsgenauigkeit](media/Sensitivity-labels-instance-count-match-accuracy.png)

Nachdem Sie die Typen vertraulicher Informationen ausgewählt haben, können Sie die Kriterien eingrenzen, indem Sie die Instanzenanzahl oder Übereinstimmungsgenauigkeit ändern. Weitere Informationen finden Sie unter [Optimieren der Regeln für niedrigere oder höhere Übereinstimmungsgenauigkeit](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).

Darüber hinaus können Sie auswählen, ob die Kriterien alle Typen vertraulicher Informationen oder nur einen Typ feststellen müssen. Damit die Kriterien flexibler oder komplexer sind, können Sie Gruppen hinzufügen und logische Operatoren zwischen den Gruppen verwenden. Weitere Informationen finden Sie unter [Gruppieren und logische Operatoren](data-loss-prevention-policies.md#grouping-and-logical-operators).

Wenn eine Vertraulichkeitsbezeichnung automatisch angewendet wird, wird dem Benutzer eine Benachrichtigung in der Office-App angezeigt. Sie können **OK** auswählen, um die Benachrichtigung zu schließen.

![Benachrichtigung darüber, dass ein Dokument automatisch mit einer Bezeichnung versehen wurde](media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a>Empfehlen des Anwendens einer Vertraulichkeitsbezeichnung

Auf Wunsch können Sie, anstatt eine Vertraulichkeitsbezeichnung automatisch auf Inhalte anzuwenden, Benutzern empfehlen, die Bezeichnung anzuwenden. Diese Option bietet Benutzern die Möglichkeit, die Klassifizierung und den dazugehörigen Schutz zu akzeptieren oder die Empfehlung abzulehnen, falls die Bezeichnung für das Dokument oder die E-Mail nicht geeignet ist.

Beachten Sie, dass empfohlene Bezeichnungen in Word, PowerPoint und Excel unterstützt werden (Azure Information Protection-Client für einheitliche Bezeichnungen muss installiert sein). Wir arbeiten daran, dass die empfohlenen Bezeichnungen in Outlook unterstützt werden.

![Option zum Empfehlen einer Vertraulichkeitsbezeichnung](media/Sensitivity-labels-Recommended-label-option.png)

Im Folgenden finden Sie ein Beispiel für eine Aufforderung, wenn Sie Kriterien zum Anwenden einer Bezeichnung als empfohlene Aktion, und einen benutzerdefinierten Richtlinientipp. Sie können den Text festlegen, der im Richtlinientipp angezeigt wird.

![Aufforderung zum Anwenden einer empfohlene Bezeichnung](media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a>Anwenden automatischer oder empfohlener Bezeichnungen

- Das automatische Anwenden von Bezeichnungen gilt für Word, Excel und PowerPoint, wenn Dokumente gespeichert werden, und für Outlook, wenn E-Mails gesendet werden. Diese Kriterien erkennen vertrauliche Informationen im Text in den Dokumenten und E-Mails sowie in Kopf-und Fußzeilen, jedoch nicht in der Betreffzeile oder Anlagen von E-Mails.

- Die automatische Klassifizierung kann nicht für Dokumente und E-Mails verwendet werden, die zuvor manuell mit einer Bezeichnung versehen wurden oder automatisch mit einer Bezeichnung mit höherer Klassifizierung versehen wurden. Ein Dokument oder eine E-Mail darf nur über eine angewendete Vertraulichkeitsbezeichnung verfügen (zusätzlich zu einer einzelnen Aufbewahrungsbezeichnung).

- Die Empfohlene Klassifizierung gilt für Word, Excel und PowerPoint, wenn Dokumente gespeichert werden. Wir arbeiten daran, dass das Anwenden empfohlener Bezeichnungen in Outlook unterstützt wird.

- Die empfohlene Klassifizierung kann nicht für Dokumente verwendet werden, die bereits mit einer Bezeichnung mit höherer Klassifizierung versehen wurden. Wenn der Inhalt bereits mit einer Bezeichnung mit höherer Klassifizierung versehen ist, wird in diesem Fall dem Benutzer keine Aufforderung mit der Empfehlung und dem Richtlinientipp angezeigt.

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a>Auswerten mehrerer Kriterien, wenn sie für mehr als eine Bezeichnung zutreffen

Die Bezeichnungen werden je nach Position, die Sie in der Richtlinie festlegen, sortiert: die Bezeichnung an erster Stelle hat die niedrigste Position (am wenigsten vertraulich) und die Bezeichnung an letzter Stelle hat die höchste Position (am meisten vertraulich). Weitere Informationen zur Priorität finden Sie unter [Priorität der Bezeichnungen (Reihenfolge wesentlich)](sensitivity-labels.md#label-priority-order-matters).

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a>Konfigurieren Sie keine übergeordnete Bezeichnung, die automatisch angewendet oder empfohlen wird.

Denken Sie daran, dass eine übergeordnete Bezeichnung (eine Bezeichnung mit Unterbezeichnungen) nicht auf Inhalt angewendet werden kann. Stellen Sie sicher, dass Sie eine übergeordnete Bezeichnung nicht so konfigurieren, dass sie automatisch angewendet oder empfohlen wird, da die übergeordnete Bezeichnung nicht auf Inhalt in Office-Apps angewendet wird, die den Azure Information Protection-Client mit einheitlichen Bezeichnungen verwenden. Weitere Informationen zu übergeordneten Bezeichnungen und Unterbezeichnungen finden Sie unter [Unterbezeichnungen (Gruppierungsbezeichnungen)](sensitivity-labels.md#sublabels-grouping-labels).

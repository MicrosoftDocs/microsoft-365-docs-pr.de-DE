---
title: Richtlinien für Benutzer Übermittlungen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie ein Postfach So konfigurieren, dass Spam-und Phishing-e-Mails erfasst werden, die von Benutzern gemeldet werden.
ms.openlocfilehash: bffa70184a9307869ce6170ba1ea05ae3f084ccf
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350275"
---
# <a name="user-submissions-policies"></a>Richtlinien für Benutzer Übermittlungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Exchange Online Postfächern können Sie ein Postfach für den Empfang von Nachrichten angeben, die von Benutzern als bösartig oder nicht bösartig gemeldet werden. Wenn Benutzer Nachrichten über die verschiedenen Berichtsoptionen übermitteln, können Sie dieses Postfach zum Abfangen von Nachrichten (nur an das benutzerdefinierte Postfach senden) oder zum Empfangen von Kopien von Nachrichten (senden an das benutzerdefinierte Postfach und Microsoft) verwenden. Dieses Feature funktioniert mit den folgenden Optionen für die Nachrichtenberichterstattung:

- [Das Add-in "Berichtsnachricht"](enable-the-report-message-add-in.md)

- [Integrierte Berichterstellung in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (früher bekannt als Outlook Web App)

- [Integrierte Berichterstellung in Outlook für IOS und Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Wenn die Berichterstellung [in Outlook im Internet deaktiviert](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)wurde, werden durch die Aktivierung von Benutzereingaben hier die Einstellungen außer Kraft gesetzt, und Benutzer können erneut Nachrichten in Outlook im Internet melden.

Sie können auch Nachrichten Berichterstattungstools von Drittanbietern konfigurieren, um Nachrichten an das von Ihnen angegebene Postfach weiterzuleiten.

Durch das Übermitteln von Benutzern gemeldeten Nachrichten an ein benutzerdefiniertes Postfach anstatt direkt an Microsoft können Ihre Administratoren Nachrichten selektiv und manuell über [Administrator Übermittlung](admin-submission.md)an Microsoft melden.

## <a name="custom-mailbox-prerequisites"></a>Voraussetzungen für benutzerdefinierte Postfächer

Verwenden Sie die folgenden Artikel, um die erforderlichen Voraussetzungen zu konfigurieren, damit Benutzer gemeldete Nachrichten an Ihr benutzerdefiniertes Postfach wechseln:

- Überspringen Sie die Spamfilterung durch Erstellen einer Exchange-Nachrichtenfluss Regel zum Festlegen der Spam Zuverlässigkeitsstufe. Weitere Informationen finden Sie unter [Verwenden der Exchange-Verwaltungskonsole zum Erstellen einer e-Mail-Fluss Regel, die den SCL-Wert einer Nachricht festlegt](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages?view=o365-worldwide#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) , um den SCL auf **-1**festzulegen

- Deaktivieren Sie die Überprüfung von Anlagen für Schadsoftware. Verwenden Sie [einrichten (oder bearbeiten) einer Richtlinie für ATP-sichere Anlagen](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide#step-2-set-up-or-edit-an-atp-safe-attachments-policy) zum Erstellen einer Richtlinie für sichere Anlagen mit der Einstellung **Off-Attachment wird nicht auf aktivierte Schadsoftware überprüft** .

- Deaktivieren Sie die URL-Überprüfung für Nachrichten. Verwenden Sie [Richtlinien für ATP-sichere Links hinzufügen (oder bearbeiten), die für alle oder bestimmte e-Mail-Empfänger gelten](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-links-policies?view=o365-worldwide#step-3-add-or-edit-atp-safe-links-policies-that-apply-to-all-or-specific-email-recipients) , um eine Richtlinie für sichere Links zu erstellen, und **Wählen Sie die Aktion für unbekannte potenziell bösartige URLs in Nachrichten** auf **Off**aus.

- Erstellen Sie eine Richtlinie zum Schutz vor Schadsoftware, um die automatische Säuberungsaktion für Malware zu deaktivieren. Weitere Informationen finden Sie unter [Verwenden des Security & Compliance Center zum Erstellen von Antischadsoftware-Richtlinien](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide#use-the-security--compliance-center-to-create-anti-spam-policies) , um die **Automatische Bereinigung von Schadsoftware** auf **Off**festzulegen.

- Erstellen Sie eine Spamfilter Richtlinie zum Deaktivieren der automatischen Säuberungs-e-Mail-Löschung (zap) für Spam Zap und Phishing zap. Weitere Informationen finden Sie unter [use the Security & Compliance Center zum Erstellen von Anti-Spam-Richtlinien](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide#use-the-security--compliance-center-to-create-anti-spam-policies) und deaktivieren **der Kontrollkästchen** für Spam Zap und Phishing zap.

- Deaktivieren Sie die Junk-e-Mail-Regel. Verwenden Sie zum Deaktivieren der Junk-e-Mail-Regel [Junk-e-Mail-Einstellungen in Exchange Online Postfächern konfigurieren](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes?view=o365-worldwide) Nach der Deaktivierung können EoP Nachrichten nicht in den Junk-e-Mail-Ordner basierend auf der Spamfilter-Urteils Aktion " **Nachricht in Junk-e-Mail-Ordner"** oder "Sammlung von Listen sicherer Adressen" im Postfach migrieren

Nachdem Sie sichergestellt haben, dass Ihr Postfach alle anwendbaren Voraussetzungen erfüllt, [verwenden Sie das Sicherheits & Compliance Center, um das Postfach "Benutzer Übermittlungen" zu konfigurieren](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in diesem Artikel).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Wenn Sie direkt zur Seite **Benutzereingaben** wechseln möchten, verwenden Sie <https://protection.office.com/userSubmissionsReportMessage> .

- Um die Konfiguration für Benutzer Übermittlungen zu ändern, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

  - **Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
  - **Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Konfigurieren des Postfachs für Benutzer Übermittlungen mithilfe des Security & Compliance Centers

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Users Submissions**.

2. Wählen Sie auf der Seite **Benutzereingaben** , die angezeigt wird, eine der folgenden Optionen aus:

   a. **Aktivieren der Berichtsnachrichten Funktion für Outlook (empfohlen)**: Wählen Sie diese Option aus, wenn Sie das Add-in "Berichtsnachricht" oder die integrierte Berichterstellung in Outlook im Internet verwenden, und konfigurieren Sie dann die folgenden Einstellungen:

      - **Anpassen der Bestätigungsnachricht für Endbenutzer**: Klicken Sie auf diesen Link. Konfigurieren Sie im angezeigten Flyout für die **Bestätigung der Nachrichten Anpassung** die folgenden Einstellungen:

      - **Vor der Übermittlung**: Geben Sie in den Feldern **Titel** und **Bestätigungsmeldung** den beschreibenden Text ein, den Benutzer sehen, bevor Sie eine Nachricht mithilfe des Berichtsnachrichten-Add-Ins melden. Sie können die Variable% type% verwenden, um den Übermittlungs einzubeziehen (Junk, not Junk, Phishing, etc.).

        Wenn Sie eine Option auswählen, die die gemeldeten Nachrichten an Microsoft sendet, wird der Benachrichtigung auch der folgende Text hinzugefügt:

        > Ihre e-Mail-Nachricht wird an Microsoft zur Analyse übermittelt. Einige e-Mails enthalten möglicherweise persönliche oder vertrauliche Informationen.

      - **Nach der Übermittlung**: Klicken Sie auf ![ Symbol erweitern ](../../media/scc-expand-icon.png) . Geben Sie in die **Meldungs** Felder **Titel** und Bestätigung den beschreibenden Text ein, den Benutzer sehen, nachdem Sie eine Nachricht mithilfe des Berichtsnachrichten-Add-ins gemeldet haben. Sie können die Variable% type% verwenden, um den Übermittlungs einzubeziehen.

      Klicken Sie nach Abschluss des Vorgangs auf **Speichern**. Klicken Sie auf der Seite **Benutzereingaben** auf wieder **herstellen** , um diese Werte zu löschen.

      - **Senden Sie die gemeldeten Nachrichten an**: führen Sie eine der folgenden Optionen aus:

        - **Microsoft (empfohlen)**: das Postfach "Benutzer Übermittlungen" wird nicht verwendet (alle gemeldeten Nachrichten werden an Microsoft weitergegeben).

        - **Microsoft und ein benutzerdefiniertes Postfach**: Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein. Verteilergruppen sind nicht zulässig. Benutzer Übermittlungen werden sowohl an Microsoft für die Analyse als auch an das benutzerdefinierte Postfach für Ihr Administrator-oder Sicherheits Betriebsteam zu analysieren gehen.

        - **Benutzerdefiniertes Postfach**: Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein. Verteilergruppen sind nicht zulässig. Verwenden Sie diese Option, wenn die Nachricht nur für die Analyse zuerst an ein Administrator-oder Sicherheits Betriebsteam gesendet werden soll. Nachrichten werden nicht an Microsoft weitergeleitet, es sei denn, der Administrator leitet Sie selbst weiter.

        > [!NOTE]
        > US-Regierungsorganisationen (gcc, gcc-H und DoD) können nur **benutzerdefiniertes Postfach**konfigurieren. Die beiden anderen Optionen sind deaktiviert. 

      Wenn Sie fertig sind, klicken Sie auf **bestätigen**.

      > [!CAUTION]
      > Wenn Sie die [Junk-e-Mail-Berichterstellung in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) im Internet mit Outlook im WebPost Fach Richtlinien deaktiviert haben, aber eine der vorherigen Einstellungen für das Melden von Nachrichten an Microsoft konfiguriert haben, können Benutzer Nachrichten an Microsoft in Outlook im Internet über das Add-in "Berichtsnachricht" melden.

   - **Deaktivieren der Berichtsnachrichten Funktion für Outlook**: Wählen Sie diese Option aus, wenn Sie Drittanbieter-Berichterstattungstools anstelle des Berichtsnachrichten-Add-Ins oder der integrierten Berichterstellung in Outlook im Internet verwenden, und konfigurieren Sie dann die folgenden Einstellungen:

      Wählen Sie **dieses benutzerdefinierte Postfach verwenden aus, um Benutzer gemeldete Übermittlungen zu empfangen**. Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Postfachs ein, das sich bereits in Office 365 befindet. Hierbei muss es sich um ein vorhandenes Postfach in Exchange Online handeln, das e-Mails empfangen kann.

      Wenn Sie fertig sind, klicken Sie auf **bestätigen**.

## <a name="message-submission-format"></a>Nachrichten Übermittlungs Format

Nachrichten, die an benutzerdefinierte Postfächer gesendet werden, müssen einem bestimmten Übermittlungs Nachrichtenformat entsprechen. Der Betreff (Umschlag Titel) der Übermittlung sollte in folgendem Format vorliegen:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

were SafetyAPIAction ist einer der folgenden Integer-Werte:

- 1: Junk
- 2: NotJunk
- 3: Phishing

Im folgenden Beispiel:

- Die Nachricht wird als Phishing gemeldet.
- Die Netzwerknachrichten-ID lautet 49871234-6dc6-43E8-ABCD-08d797f20abe.
- Die Absender-IP-Adresse lautet 167.220.232.101.
- Die von-Adresse lautet Test@contoso.com.
- Die Betreffzeile der Nachricht lautet "Testen der Phishing-Übermittlung"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

Nachrichten, die diesem Format nicht entsprechen, werden im Übermittlungen-Portal nicht ordnungsgemäß angezeigt.

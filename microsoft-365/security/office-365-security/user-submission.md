---
title: Richtlinie für Benutzerübermittlungen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren erfahren, wie Sie ein Postfach zum Sammeln von Spam- und Phishing-E-Mails konfigurieren, die von Benutzern gemeldet werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0ac1028ca3485f75518ccca298a1fd85a7bf40ec
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922390"
---
# <a name="user-submissions-policy"></a>Richtlinie für Benutzerübermittlungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Exchange Online-Postfächern können Sie ein Postfach angeben, um Nachrichten zu empfangen, die Benutzer als bösartig oder nicht bösartig melden. Wenn Benutzer Nachrichten mithilfe der verschiedenen Berichtsoptionen übermitteln, können Sie dieses Postfach verwenden, um Nachrichten abzufangen (nur an das benutzerdefinierte Postfach zu senden) oder Kopien von Nachrichten zu empfangen (an das benutzerdefinierte Postfach und Microsoft senden). Dieses Feature funktioniert mit den folgenden Nachrichtenberichtsoptionen:

- [Das Berichtsnachrichten-Add-In](enable-the-report-message-add-in.md)

- [Das Phishing-Add-In melden](enable-the-report-phish-add-in.md)

- [Integrierte Berichterstellung in Outlook im Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (früher als Outlook Web App bekannt)

- [Integrierte Berichterstellung in Outlook für iOS und Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Wenn die Berichterstellung [in Outlook im](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)Web deaktiviert wurde, setzt das Aktivieren von Benutzerübermittlungen hier diese Einstellung außer Kraft und ermöglicht Benutzern, Nachrichten in Outlook im Web erneut zu melden.

Sie können auch Tools für die Nachrichtenberichterstellung von Drittanbietern konfigurieren, um Nachrichten an das von Ihnen festgelegte Postfach weiter zu senden.

Das Senden von vom Benutzer gemeldeten Nachrichten an ein benutzerdefiniertes Postfach anstatt direkt an Microsoft ermöglicht es Ihren Administratoren, Nachrichten mithilfe der Admin-Übermittlung selektiv und manuell an Microsoft [zu melden.](admin-submission.md)

## <a name="custom-mailbox-prerequisites"></a>Voraussetzungen für benutzerdefinierte Postfächer

Verwenden Sie die folgenden Artikel, um die erforderlichen Voraussetzungen zu konfigurieren, damit vom Benutzer gemeldete Nachrichten an Ihr benutzerdefiniertes Postfach gesendet werden:

- Überspringen Sie die Spamfilterung für das benutzerdefinierte Postfach, indem Sie eine Exchange-Nachrichtenflussregel zum Festlegen der Spamsicherheitsstufe erstellen. Weitere Informationen finden Sie unter [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **-1**.

- Deaktivieren Sie das Scannen von Anlagen auf Schadsoftware im benutzerdefinierten Postfach. Verwenden [Sie Set up Safe Attachments policies in Defender for Office 365,](set-up-atp-safe-attachments-policies.md) um eine Richtlinie für sichere Anlagen mit der Einstellung **Off** for Safe Attachments unknown malware response **zu erstellen.**

- Deaktivieren Sie die URL-Überprüfung für Nachrichten im benutzerdefinierten Postfach. Verwenden [Sie Set up Safe Links policies in Defender for Office 365,](set-up-atp-safe-links-policies.md) um eine Richtlinie für sichere Links mit der Einstellung **Off** for Select the action for unknown potentially **malicious URLs in messages zu erstellen.**

- Erstellen Sie eine Richtlinie für Schadsoftware, um die automatische Bereinigung von Schadsoftware in null Stunden zu deaktivieren. Weitere Informationen finden Sie unter Use [the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set Malware **Zero-hour Auto Purge** to **Off**.

- Erstellen Sie eine Spamfilterrichtlinie, um die automatische Reinigung (Zero-Hour Auto Purge, ZAP) für Spam und Phishing im benutzerdefinierten Postfach zu deaktivieren. Weitere Informationen finden Sie unter Verwenden des Security & Compliance Center zum Erstellen von [Antispamrichtlinien](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) und Löschen der Kontrollkästchen **Ein** für **Spam ZAP** und **Phish ZAP**.

- Deaktivieren Sie die Junk-E-Mail-Regel im benutzerdefinierten Postfach. Verwenden [Sie Konfigurieren von Junk-E-Mail-Einstellungen in Exchange Online-Postfächern,](configure-junk-email-settings-on-exo-mailboxes.md) um die Junk-E-Mail-Regel zu deaktivieren. Nach der Deaktivierung kann EOP Nachrichten nicht in den Junk-E-Mail-Ordner verschieben, basierend auf der Spamfilterungsaktion **Nachricht** in Junk-E-Mail-Ordner oder die Sammlung sicherer Adressen im Postfach verschieben.

Nachdem Sie überprüft haben, ob Ihr Postfach alle erforderlichen Voraussetzungen erfüllt, konfigurieren Sie das Benutzerübermittlungspostfach im [Security & Compliance Center](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in diesem Artikel).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Benutzerübermittlungen zu** wechseln, verwenden Sie <https://protection.office.com/userSubmissionsReportMessage> .

- Zum Ändern der Konfiguration für Benutzerübermittlungen müssen Sie Mitglied einer der folgenden Rollengruppen sein:

  - **Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
  - **Organisationsverwaltung** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- Sie benötigen Zugriff auf Exchange Online PowerShell. Wenn das Konto, das Sie verwenden möchten, keinen Zugriff auf Exchange Online PowerShell hat, wird beim Angeben des Übermittlungspostfachs eine Fehlermeldung angezeigt, die wie dies aussieht:

  > Angeben einer E-Mail-Adresse in Ihrer Domäne

  Weitere Informationen zum Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell finden Sie in den folgenden Themen:

  - [Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Clientzugriffsregeln in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Konfigurieren des Benutzerübermittlungspostfachs mithilfe des Security & Compliance Center

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für **die Bedrohungsverwaltung** \>  \> **Benutzerübermittlungen**.

2. Wählen Sie **auf** der angezeigten Seite Benutzerübermittlungen eine der folgenden Optionen aus:

      1. Aktivieren Des Berichtsnachrichtenfeatures für **Outlook (empfohlen):** Wählen Sie diese Option aus, wenn Sie das Add-In "Nachricht melden", das Phishing-Add-In melden oder die integrierte Berichterstellung in Outlook im Web verwenden und dann die folgenden Einstellungen konfigurieren:

    - **Anpassen der Bestätigungsnachricht für Endbenutzer**: Klicken Sie auf diesen Link. Konfigurieren Sie **im angezeigten** Flyout Bestätigungsnachricht anpassen die folgenden Einstellungen:

        - **Vor der** Übermittlung:  Geben Sie in die Meldungsfelder Titel und Bestätigung den beschreibenden Text ein, der Benutzern angezeigt wird, bevor sie eine Nachricht mithilfe des Add-Ins "Nachricht melden" oder des Phishing-Add-Ins melden melden.  Sie können die Variable %type% verwenden, um den Übermittlungstyp (Junk, nicht Junk, Phish usw.) zu verwenden.

            Wie bereits erwähnt, wird der Benachrichtigung auch der folgende Text hinzugefügt, wenn Sie eine Option auswählen, die die gemeldeten Nachrichten an Microsoft sendet:

        > Ihre E-Mails werden wie folgt zur Analyse an Microsoft übermittelt. Einige E-Mails enthalten möglicherweise persönliche oder vertrauliche Informationen.

        - **Nach der Übermittlung**: Klicken Sie ![ auf Erweitern ](../../media/scc-expand-icon.png) (Symbol). Geben Sie  **in** die Meldungsfelder Titel und Bestätigung den beschreibenden Text ein, der Benutzern angezeigt wird, nachdem sie eine Nachricht mithilfe des Berichtsnachrichten-Add-Ins oder des Phishing-Add-Ins Melden gemeldet haben. Sie können die Variable %type% verwenden, um den Übermittlungstyp zu verwenden.

      Klicken Sie nach Abschluss des Vorgangs auf **Speichern**. Klicken Sie auf der Seite Benutzerübermittlungen auf **Wiederherstellen,** um diese **Werte zu** löschen.
    
    - **Anpassen der Berichtsoptionen für Endbenutzer**: Klicken Sie auf diesen Link. Geben Sie im angezeigten Flyout Optionen für die Endbenutzerberichterstellung anpassen den beschreibenden Text für **Junk-E-Mail-Berichtsoptionen** ein. 
Wählen **Sie unter Optionen zum Anzeigen, wann Nachrichten gemeldet werden,** mindestens eine der folgenden Optionen aus:
        - **Fragen Sie mich vor dem Senden eines Berichts**
        - **Automatisches Senden von Berichten**
        -  **Niemals Berichte senden** \
   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.
              - **Senden Sie die gemeldeten Nachrichten an**: Nehmen Sie eine der folgenden Auswahlen vor:
              - **Microsoft (empfohlen):** Das Benutzerübermittlungspostfach wird nicht verwendet (alle gemeldeten Nachrichten gehen an Microsoft).
              - **Microsoft und ein benutzerdefiniertes Postfach:** Geben Sie in das angezeigte Feld die E-Mail-Adresse eines vorhandenen Exchange Online-Postfachs ein. Verteilergruppen sind nicht zulässig. Benutzerübermittlungen werden sowohl zur Analyse an Microsoft als auch an das benutzerdefinierte Postfach für Ihr Administrator- oder Sicherheitsteam zur Analyse gesendet.
              - **Nur benutzerdefiniertes** Postfach: Geben Sie in das angezeigte Feld die E-Mail-Adresse eines vorhandenen Exchange Online-Postfachs ein. Verteilergruppen sind nicht zulässig. Verwenden Sie diese Option, wenn die Nachricht zunächst nur an einen Administrator oder das Sicherheitsbetriebsteam zur Analyse gehen soll. Nachrichten werden nur dann an Microsoft gesendet, wenn der Administrator sie selbst weitersent.

        > [!NOTE]
        > Us.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**. Die beiden anderen Optionen sind deaktiviert.

      Klicken Sie nach Abschluss des Abschlusses auf **Bestätigen**.

      > [!CAUTION]
      > Wenn Sie die Junk-E-Mail-Berichterstellung [in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) im Web mithilfe von Outlook im Webpostfachrichtlinien deaktiviert haben, Sie jedoch eine der vorherigen Einstellungen zum Melden von Nachrichten an Microsoft konfigurieren, können Benutzer Nachrichten über das Add-In "Nachricht melden" oder das Phishing-Add-In Melden an Microsoft in Outlook im Web melden.


    1. Deaktivieren des Berichtsnachrichtenfeatures für **Outlook:** Wählen Sie diese Option aus, wenn Sie Berichtstools von Drittanbietern anstelle des Berichtsnachrichten-Add-Ins, des Phishing-Add-Ins "Melden" oder der integrierten Berichterstellung in Outlook im Web verwenden, und konfigurieren Sie dann die folgenden Einstellungen:

          Wählen **Sie Dieses benutzerdefinierte Postfach verwenden, um vom Benutzer gemeldete Übermittlungen zu empfangen.** Geben Sie in das angezeigte Feld die E-Mail-Adresse eines vorhandenen Postfachs ein, das sich bereits in Office 365 befindet. Dies muss ein vorhandenes Postfach in Exchange Online sein, das E-Mails empfangen kann.

          Klicken Sie nach Abschluss des Abschlusses auf **Bestätigen**.

## <a name="message-submission-format"></a>Nachrichtenübermittlungsformat

Nachrichten, die an benutzerdefinierte Postfächer gesendet werden, müssen einem bestimmten Übermittlungs-E-Mail-Format folgen. Der Betreff (Umschlagtitel) der Übermittlung sollte in diesem Format vorliegen:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

Dabei ist SafetyAPIAction einer der folgenden ganzzahligen Werte:

- 1: Junk
- 2: Kein Junk
- 3: Phishing

Im folgenden Beispiel:

- Die Nachricht wird als Phishing gemeldet.
- Die Netzwerknachrichten-ID lautet 49871234-6dc6-43e8-abcd-08d797f20abe.
- Die Absender-IP ist 167.220.232.101.
- Die Von-Adresse ist test@contoso.com.
- Die Betreffzeile der Nachricht lautet "Phishing-Testübermittlung"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

Nachrichten, die diesem Format nicht folgen, werden nicht ordnungsgemäß im Übermittlungsportal angezeigt.
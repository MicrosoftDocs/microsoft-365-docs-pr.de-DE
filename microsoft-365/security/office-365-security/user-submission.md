---
title: Benutzerübermittlungsrichtlinie
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
description: Administratoren können erfahren, wie Sie ein Postfach so konfigurieren, dass Spam- und Phishing-E-Mails gesammelt werden, die von Benutzern gemeldet werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6022d2ca0e4357b422a20490fee7486affefa09c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287269"
---
# <a name="user-submissions-policy"></a>Benutzerübermittlungsrichtlinie

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Exchange Online-Postfächern können Sie ein Postfach angeben, um Nachrichten zu empfangen, die Benutzer als bösartig oder nicht schädlich melden. Wenn Benutzer Nachrichten mithilfe der verschiedenen Berichtsoptionen übermitteln, können Sie dieses Postfach verwenden, um Nachrichten abzufangen (nur an das benutzerdefinierte Postfach senden) oder Kopien von Nachrichten zu empfangen (an das benutzerdefinierte Postfach und Microsoft senden). Dieses Feature funktioniert mit den folgenden Nachrichtenberichtsoptionen:

- [Das Berichtsnachrichten-Add-In](enable-the-report-message-add-in.md)

- [Das Phishing-Add-In "Melden"](enable-the-report-phish-add-in.md)

- [Integrierte Berichterstellung in Outlook im Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (früher als Outlook Web App bekannt)

- [Integrierte Berichterstellung in Outlook für iOS und Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Wenn die Berichterstellung [in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)im Web deaktiviert wurde, setzt das Aktivieren von Benutzerübermittlungen hier diese Einstellung außer Kraft und ermöglicht Es Benutzern, Nachrichten in Outlook im Web erneut zu melden.

Sie können auch Tools für die Nachrichtenberichterstattung von Drittanbietern konfigurieren, um Nachrichten an das von Ihnen festgelegte Postfach weiter zu senden.

Das Senden von vom Benutzer gemeldeten Nachrichten an ein benutzerdefiniertes Postfach anstatt direkt an Microsoft ermöglicht Es Ihren Administratoren, Nachrichten mithilfe der Administratorübermittlung selektiv und manuell an Microsoft [zu melden.](admin-submission.md)

## <a name="custom-mailbox-prerequisites"></a>Voraussetzungen für benutzerdefinierte Postfächer

Verwenden Sie die folgenden Artikel, um die erforderlichen Komponenten zu konfigurieren, damit vom Benutzer gemeldete Nachrichten an Ihr benutzerdefiniertes Postfach gesendet werden:

- Überspringen Sie die Spamfilterung für das benutzerdefinierte Postfach, indem Sie eine Exchange-Nachrichtenflussregel erstellen, um die Spamsicherheitsstufe zu festlegen. Weitere Informationen finden Sie unter Verwenden [der EAC zum](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) Erstellen einer Nachrichtenflussregel, mit der der SCL einer Nachricht so festgelegt wird, dass der SCL auf **-1 festgelegt wird.**

- Deaktivieren Sie das Scannen von Anlagen auf Schadsoftware im benutzerdefinierten Postfach. Verwenden Sie Richtlinien zum Einrichten sicherer Anlagen [in Defender für Office 365,](set-up-atp-safe-attachments-policies.md) um eine Richtlinie für sichere Anlagen mit der Einstellung **"Für** sichere Anlagen unbekannte Schadsoftwareantwort" **zu erstellen.**

- Deaktivieren Sie die URL-Überprüfung für Nachrichten im benutzerdefinierten Postfach. Verwenden Sie "Richtlinien für sichere [Links einrichten" in Defender für Office 365,](set-up-atp-safe-links-policies.md) um eine Richtlinie für sichere Links mit der Einstellung "Aus" für "Aktion für unbekannte potenziell schädliche URLs in Nachrichten auswählen" **zu erstellen.** 

- Erstellen Sie eine Ansoftwarerichtlinie, um die automatische Bereinigung der Schadsoftware zur Nullstunde zu deaktivieren. Weitere [Informationen finden Sie unter "Verwenden des Security & Compliance Center](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) zum Erstellen von An malware-Richtlinien, um die automatische Bereinigung der Schadsoftware zur Nullstunde **auf** "Aus" **zu setzen.**

- Erstellen Sie eine Spamfilterrichtlinie, um die automatische Bereinigung zur Nullstunde (ZAP) für Spam und Phishing im benutzerdefinierten Postfach zu deaktivieren. Verwenden Sie das Security & Compliance Center, um [Antispamrichtlinien](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) zu erstellen und die Kontrollkästchen **"Ein"** für **Spam ZAP** und **Phish ZAP zu löschen.**

- Deaktivieren Sie die Junk-E-Mail-Regel im benutzerdefinierten Postfach. Verwenden [Sie "Junk-E-Mail-Einstellungen für Exchange Online-Postfächer konfigurieren",](configure-junk-email-settings-on-exo-mailboxes.md) um die Junk-E-Mail-Regel zu deaktivieren. Nach der Deaktivierung kann EOP Nachrichten nicht mehr in den  Junk-E-Mail-Ordner verschieben, basierend auf der Spamfilterungsaktion "Nachricht in Junk-E-Mail-Ordner oder die Sammlung von Listen sicherer Adressen für das Postfach verschieben".

Nachdem Sie überprüft haben, ob Ihr Postfach alle zutreffenden Voraussetzungen erfüllt, konfigurieren Sie das Benutzerübermittlungspostfach mithilfe des [Security & Compliance Centers](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in diesem Artikel).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **"Benutzerübermittlungen" zu** wechseln, verwenden Sie <https://protection.office.com/userSubmissionsReportMessage> .

- Zum Ändern der Konfiguration für Benutzerübermittlungen müssen Sie Mitglied einer der folgenden Rollengruppen sein:

  - **Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
  - **Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Sie benötigen Zugriff auf Exchange Online PowerShell. Wenn das Konto, das Sie verwenden möchten, keinen Zugriff auf Exchange Online PowerShell hat, erhalten Sie eine Fehlermeldung, die beim Angeben des Übermittlungspostfachs wie dies aussieht:

  > Angeben einer E-Mail-Adresse in Ihrer Domäne

  Weitere Informationen zum Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell finden Sie in den folgenden Themen:

  - [Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Clientzugriffsregeln in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Konfigurieren des Benutzerübermittlungspostfachs mithilfe des Security & Compliance Center

1. Wechseln Sie im Security & Compliance  Center zu Benutzerübermittlungen der \> **Bedrohungsverwaltungsrichtlinie.** \> 

2. Wählen Sie **auf der angezeigten** Seite "Benutzerübermittlungen" eine der folgenden Optionen aus:

   1. Aktivieren Sie das Feature "Nachricht melden" für **Outlook (empfohlen):** Wählen Sie diese Option aus, wenn Sie das Add-In "Nachricht melden", das Phishing-Add-In "Melden" oder die integrierte Berichterstellung in Outlook im Web verwenden und dann die folgenden Einstellungen konfigurieren:

      - **Passen Sie die Bestätigungsmeldung des Endbenutzers an:** Klicken Sie auf diesen Link. Konfigurieren Sie **im angezeigten** Flyout "Bestätigungsnachricht anpassen" die folgenden Einstellungen:

      - **Vor der** Übermittlung:  Geben Sie in die Meldungsfelder "Titel" und "Bestätigung" den beschreibenden Text ein, der Benutzern angezeigt wird, bevor sie eine Nachricht mithilfe des Add-Ins "Nachricht melden" oder des "Phishing-Add-Ins melden" melden.  Sie können die Variable %type% verwenden, um den Übermittlungstyp (Junk, kein Junk, Phishing usw.) zu verwenden.

        Wie bereits erwähnt, wird der Benachrichtigung auch der folgende Text hinzugefügt, wenn Sie eine Option auswählen, die die gemeldeten Nachrichten an Microsoft sendet:

        > Ihre E-Mails werden wie bess an Microsoft zur Analyse übermittelt. Einige E-Mails enthalten möglicherweise persönliche oder vertrauliche Informationen.

      - **After submission**: Click ![ Expand icon ](../../media/scc-expand-icon.png) . Geben **Sie**  in die Meldungsfelder "Titel" und "Bestätigung" den beschreibenden Text ein, der Benutzern angezeigt wird, nachdem sie eine Nachricht mithilfe des Add-Ins "Nachricht melden" oder des Phishing-Add-Ins "Melden" gemeldet haben. Sie können die Variable "%type%" verwenden, um den Übermittlungstyp mit ein-/ zu verwenden.

      Klicken Sie nach Abschluss des Vorgangs auf **Speichern**. Klicken Sie auf der Seite "Benutzerübermittlungen" auf "Wiederherstellen", um **diese Werte zu** löschen. 

      - **Senden Sie die gemeldeten Nachrichten an:** Treffen Sie eine der folgenden Optionen:

        - **Microsoft (empfohlen):** Das Benutzerübermittlungspostfach wird nicht verwendet (alle gemeldeten Nachrichten gehen an Microsoft).

        - **Microsoft und ein benutzerdefiniertes** Postfach: Geben Sie in das angezeigte Feld die E-Mail-Adresse eines vorhandenen Exchange Online-Postfachs ein. Verteilergruppen sind nicht zulässig. Benutzerübermittlungen werden sowohl zur Analyse an Microsoft als auch an das benutzerdefinierte Postfach gesendet, das Ihr Administrator- oder Sicherheitsteam analysieren kann.

        - **Benutzerdefiniertes** Postfach: Geben Sie in das angezeigte Feld die E-Mail-Adresse eines vorhandenen Exchange Online-Postfachs ein. Verteilergruppen sind nicht zulässig. Verwenden Sie diese Option, wenn die Nachricht nur an einen Administrator oder das Sicherheitsteam zur Analyse gesendet werden soll. Nachrichten werden nicht an Microsoft gesendet, es sei denn, der Administrator gibt sie selbst weiter.

        > [!NOTE]
        > Us-Government-Organisationen (GCC, GCC-H und DoD) können nur benutzerdefinierte **Postfächer konfigurieren.** Die beiden anderen Optionen sind deaktiviert.

      Klicken Sie nach Abschluss des Abschlusses auf **"Bestätigen".**

      > [!CAUTION]
      > Wenn Sie die Junk-E-Mail-Berichterstellung [in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) im Web mithilfe von Outlook im Web-Postfachrichtlinien deaktiviert haben, aber eine der vorherigen Einstellungen so konfigurieren, dass Nachrichten an Microsoft gemeldet werden, können Benutzer Nachrichten mithilfe des Add-Ins "Nachricht melden" oder "Phishing melden" an Microsoft in Outlook im Web melden.

   - Deaktivieren Sie das Feature "Nachricht melden" für **Outlook:** Wählen Sie diese Option aus, wenn Sie berichtstools von Drittanbietern anstelle des Berichtsnachrichten-Add-Ins, des Phishing-Add-Ins "Melden" oder der integrierten Berichterstellung in Outlook im Web verwenden, und konfigurieren Sie dann die folgenden Einstellungen:

      Wählen **Sie "Dieses benutzerdefinierte Postfach verwenden" aus, um vom Benutzer gemeldete Übermittlungen zu empfangen.** Geben Sie in das angezeigte Feld die E-Mail-Adresse eines vorhandenen Postfachs ein, das sich bereits in Office 365 befindet. Dies muss ein vorhandenes Postfach in Exchange Online sein, das E-Mails empfangen kann.

      Klicken Sie nach Abschluss des Abschlusses auf **"Bestätigen".**

## <a name="message-submission-format"></a>Nachrichtenübermittlungsformat

Nachrichten, die an benutzerdefinierte Postfächer gesendet werden, müssen ein bestimmtes Übermittlungs-E-Mail-Format verwenden. Der Betreff (Umschlagtitel) der Übermittlung sollte in diesem Format vorliegen:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

Dabei ist SafetyAPIAction einer der folgenden ganzzahligen Werte:

- 1: Junk
- 2: Kein Junk
- 3: Phishing

Im folgenden Beispiel:

- Die Nachricht wird als Phishing gemeldet.
- Die Netzwerknachrichten-ID lautet 49871234-6dc6-43e8-abcd-08d797f20abe.
- Die Absender-IP ist 167.220.232.101.
- Die "Von"-Adresse test@contoso.com.
- Die Betreffzeile der Nachricht lautet "Phishing-Testübermittlung".

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

Nachrichten, die nicht diesem Format folgen, werden im Übermittlungsportal nicht ordnungsgemäß angezeigt.

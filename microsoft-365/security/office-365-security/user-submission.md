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
description: Administratoren können erfahren, wie Sie ein Postfach konfigurieren, um Spam- und Phishing-E-Mails zu sammeln, die von Benutzern gemeldet werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4827ce149632d0e37dbe9c3dc5fc8325dbfa8afa
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929875"
---
# <a name="user-submissions-policy"></a>Richtlinie für Benutzerübermittlungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Exchange Online Postfächern können Sie ein Postfach angeben, um Nachrichten zu empfangen, die Benutzer als bösartig oder nicht bösartig melden. Wenn Benutzer Nachrichten mit den verschiedenen Berichtsoptionen übermitteln, können Sie dieses Postfach verwenden, um Nachrichten abzufangen (nur an das benutzerdefinierte Postfach senden) oder Kopien von Nachrichten zu empfangen (an das benutzerdefinierte Postfach und Microsoft senden). Dieses Feature funktioniert mit den folgenden Optionen für die Meldungsberichterstellung:

- [Das Add-In "Nachricht melden"](enable-the-report-message-add-in.md)

- [Das Add-In "Phishing melden"](enable-the-report-phish-add-in.md)

- [Berichterstellungstools von Drittanbietern](#third-party-reporting-tools)

Wenn Benutzer gemeldete Nachrichten an ein benutzerdefiniertes Postfach statt direkt an Microsoft übermitteln, können Ihre Administratoren Nachrichten mithilfe der Administratorübermittlung selektiv und manuell an Microsoft [melden.](admin-submission.md)

  > [!NOTE]
  > Wenn die Berichterstellung [in Outlook im Web deaktiviert](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)wurde, setzt das Aktivieren von Benutzerübermittlungen hier diese Einstellung außer Kraft und ermöglicht Es Benutzern, Nachrichten in Outlook im Web erneut zu melden.

## <a name="custom-mailbox-prerequisites"></a>Voraussetzungen für benutzerdefinierte Postfächer

Verwenden Sie die folgenden Artikel, um die erforderlichen Komponenten zu konfigurieren, damit vom Benutzer gemeldete Nachrichten an Ihr benutzerdefiniertes Postfach gesendet werden:

- Überspringen Sie die Spamfilterung für das benutzerdefinierte Postfach, indem Sie eine Exchange-Nachrichtenflussregel erstellen, um die Spamzustimmungsstufe festzulegen. Weitere Informationen finden Sie unter [Verwenden des EAC zum Erstellen einer Nachrichtenflussregel, die die SCL einer Nachricht so festlegt, dass](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) die SCL auf **Spamfilterung umgeht.**

- Deaktivieren Sie das Scannen von Anlagen auf Schadsoftware im benutzerdefinierten Postfach. Verwenden Sie ["Einrichten von Richtlinien für sichere Anlagen" in Defender für Office 365,](set-up-safe-attachments-policies.md) um eine Richtlinie für sichere Anlagen mit der Einstellung **"Aus"** für **unbekannte Schadsoftwareantworten** für sichere Anlagen zu erstellen.

- Deaktivieren Sie die URL-Überprüfung für Nachrichten im benutzerdefinierten Postfach. Verwenden Sie ["Einrichten von Richtlinien für sichere Links" in Defender für Office 365,](set-up-safe-links-policies.md) um eine Richtlinie für sichere Links mit der Einstellung **"Aus"** für **"Auswählen der Aktion für unbekannte potenziell schädliche URLs in Nachrichten"** zu erstellen.

- Erstellen Sie eine Antischadsoftwarerichtlinie, um die automatische Bereinigung von Schadsoftware zur Nullstunde zu deaktivieren. Weitere Informationen finden Sie [unter Verwenden des Microsoft 365 Defender-Portals, um Antispamrichtlinien](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) zu erstellen, um die automatische Bereinigung von **Schadsoftware zur Nullstunde** auf **"Aus"** festzulegen.

- Erstellen Sie eine Spamfilterrichtlinie, um die automatische Bereinigung von Nullstunden (ZAP) für Spam und Phishing im benutzerdefinierten Postfach zu deaktivieren. Weitere Informationen finden [Sie unter Verwenden des Microsoft 365 Defender-Portals, um Antispamrichtlinien zu erstellen](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) und die **Ein-Kontrollkästchen** für Spam **ZAP** und Phishing **ZAP** zu deaktivieren.

- Deaktivieren Sie die Junk-E-Mail-Regel im benutzerdefinierten Postfach. Verwenden Sie ["Junk-E-Mail-Einstellungen für Exchange Online Postfächer](configure-junk-email-settings-on-exo-mailboxes.md) konfigurieren", um die Junk-E-Mail-Regel zu deaktivieren. Nach der Deaktivierung kann EOP Nachrichten nicht mehr in den Junk-E-Mail-Ordner verschieben, basierend auf der Spamfilter-Bewertungsaktion **"Nachricht in Junk-E-Mail-Ordner** verschieben" oder in die Sammlung von Listen im Postfach verschieben.

Nachdem Sie überprüft haben, ob Ihr Postfach alle anwendbaren Voraussetzungen erfüllt, implementieren Sie das unter [Verwenden des Microsoft 365 Defender-Portals angegebene Verfahren, um das Postfach für Benutzerübermittlungen zu konfigurieren.](#use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/>. Um direkt zur Seite **"Übermittlungen"** zu wechseln, verwenden Sie <https://security.microsoft.com/reportsubmission> .

- Um die Konfiguration für Benutzerübermittlungen zu ändern, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

  - **Organisationsverwaltung** oder **Sicherheitsadministrator** im [Microsoft 365 Defender-Portal.](permissions-in-the-security-and-compliance-center.md)
  - **Organisationsverwaltung** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- Sie benötigen Zugriff auf Exchange Online PowerShell. Wenn das Konto, das Sie verwenden möchten, keinen Zugriff auf Exchange Online PowerShell hat, erhalten Sie einen Fehler, der beim Angeben des Übermittlungspostfachs wie folgt aussieht:

  > Angeben einer E-Mail-Adresse in Ihrer Domäne

  Weitere Informationen zum Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell finden Sie in den folgenden Themen:

  - [Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Clientzugriffsregeln in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>Verwenden des Microsoft 365 Defender-Portals zum Konfigurieren des Postfachs für Benutzerübermittlungen

1. Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien & Regeln** \> **Bedrohungsrichtlinien** Benutzer \> **gemeldete Nachrichteneinstellungen** \> **Benutzerübermittlungen.**

2. Wählen Sie auf der angezeigten Seite **"Benutzerübermittlungen"** eine der folgenden Optionen aus:

      1. **Aktivieren Sie das Feature "Nachricht melden" für Outlook (empfohlen):** Wählen Sie diese Option aus, wenn Sie das Add-In "Nachricht melden", das Add-In "Berichtphishing" oder die integrierte Berichterstellung in Outlook im Web verwenden, und konfigurieren Sie dann die folgenden Einstellungen:

    - **Passen Sie die Bestätigungsmeldung des Endbenutzers** an: Klicken Sie auf diesen Link. Konfigurieren Sie im angezeigten Flyout **"Bestätigungsnachricht anpassen"** die folgenden Einstellungen:

        - **Vor der Übermittlung:** Geben Sie in die Meldungsfelder **"Titel"** und **"Bestätigung"** den beschreibenden Text ein, den Benutzer sehen, bevor sie eine Nachricht mithilfe des Add-Ins "Nachricht melden" oder des Add-Ins "Phishing melden" melden. Sie können die Variable %type% verwenden, um den Übermittlungstyp (Junk, nicht Junk, Phishing usw.) einzuschließen.

          Wie bereits erwähnt, wird der Benachrichtigung auch der folgende Text hinzugefügt, wenn Sie eine Option auswählen, die die gemeldeten Nachrichten an Microsoft sendet:

          > Ihre E-Mail wird zur Analyse wie besehen an Microsoft übermittelt. Einige E-Mails können persönliche oder vertrauliche Informationen enthalten.

        - **Nach der Übermittlung:** Klicken Sie auf ![ das Symbol "Erweitern". ](../../media/scc-expand-icon.png) Geben Sie in die Meldungsfelder **"Titel"** und **"Bestätigung"** den beschreibenden Text ein, den Benutzer sehen, nachdem sie eine Nachricht mithilfe des Add-Ins "Nachricht melden" oder des Add-Ins "Phishing melden" gemeldet haben. Sie können die Variable %type% verwenden, um den Übermittlungstyp einzuschließen.

      Klicken Sie nach Abschluss des Vorgangs auf **Speichern**. Um diese Werte zu löschen, klicken Sie auf der Seite **"Benutzerübermittlungen"** auf **"Wiederherstellen".**
    
    - Passen Sie die Optionen für **die Endbenutzerberichterstellung** an: Klicken Sie auf diesen Link. Geben Sie im angezeigten Flyout **"Berichterstattungsoptionen für Endbenutzer anpassen"** den beschreibenden Text für Junk-E-Mail-Berichterstellungsoptionen ein. 
    
      Wählen Sie unter **"Optionen", um anzuzeigen, wann Nachrichten gemeldet werden,** mindestens eine der folgenden Optionen aus:
        - **Fragen Sie mich vor dem Senden eines Berichts**
        - **Automatisches Senden von Berichten**
        - **Niemals Berichte senden**
       
      Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

        - **Senden Sie die gemeldeten Nachrichten an:** Treffen Sie eine der folgenden Auswahlen:

        - **Microsoft (Empfohlen):** Das Postfach für Benutzerübermittlungen wird nicht verwendet (alle gemeldeten Nachrichten gehen an Microsoft).

        - **Sowohl Microsoft als auch ein benutzerdefiniertes Postfach:** Geben Sie in das angezeigte Feld die E-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein. Verteilergruppen sind nicht zulässig. Benutzerübermittlungen werden sowohl an Microsoft zur Analyse als auch an das benutzerdefinierte Postfach gesendet, das Ihr Administrator- oder Sicherheitsteam analysieren kann.

        - **Nur benutzerdefiniertes Postfach:** Geben Sie in das angezeigte Feld die E-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein. Verteilergruppen sind nicht zulässig. Verwenden Sie diese Option, wenn die Nachricht nur zur Analyse an einen Administrator oder das Sicherheitsteam gesendet werden soll. Nachrichten werden nicht an Microsoft weitergeleitet, es sei denn, der Administrator leitet sie selbst weiter.

          > [!NOTE]
          > U.S. Government-Organisationen (GCC, GCC-H und DoD) können nur **benutzerdefinierte Postfächer** konfigurieren. Die beiden anderen Optionen sind deaktiviert.

          > [!NOTE]
          > Wenn Organisationen so konfiguriert sind, dass sie nur an ein benutzerdefiniertes Postfach senden, werden gemeldete Nachrichten nicht zur erneuten Überprüfung gesendet, und die Ergebnisse im Portal für vom Benutzer gemeldete Nachrichten sind immer leer.

      Wenn Sie fertig sind, klicken Sie auf **Bestätigen.**

      > [!CAUTION]
      > Wenn Sie die [Junk-E-Mail-Berichterstellung in Outlook im Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) mithilfe von Outlook im Web-Postfachrichtlinien deaktiviert haben, Sie jedoch eine der vorherigen Einstellungen zum Melden von Nachrichten an Microsoft konfigurieren, können Benutzer Nachrichten mithilfe des Add-Ins "Nachricht melden" oder des Add-Ins "Phishing melden" in Outlook im Web an Microsoft melden.


    2. **Deaktivieren Sie das Feature "Meldung melden" für Outlook:** Wählen Sie diese Option aus, wenn Sie Berichtstools von Drittanbietern anstelle des Add-Ins "Nachricht melden", des Add-Ins "Berichtsphishing" oder der integrierten Berichterstellung in Outlook im Web verwenden, und konfigurieren Sie dann die folgenden Einstellungen:

       Wählen Sie **dieses benutzerdefinierte Postfach verwenden, um vom Benutzer gemeldete Übermittlungen zu empfangen.** Geben Sie in das angezeigte Feld die E-Mail-Adresse eines vorhandenen Postfachs ein, das sich bereits in Office 365 befindet. Dies muss ein vorhandenes Postfach in Exchange Online sein, das E-Mails empfangen kann.

       Wenn Sie fertig sind, klicken Sie auf **Bestätigen.**

## <a name="third-party-reporting-tools"></a>Berichterstellungstools von Drittanbietern

Sie können Tools für die Berichterstellung von Drittanbietern konfigurieren, um gemeldete Nachrichten an das benutzerdefinierte Postfach zu senden. Die einzige Anforderung besteht darin, dass die ursprüngliche Nachricht als Anlage in der Nachricht enthalten ist, die an das benutzerdefinierte Postfach gesendet wird (leiten Sie nicht nur die ursprüngliche Nachricht an das benutzerdefinierte Postfach weiter).

Die Anforderungen an die Nachrichtenformatierung werden im nächsten Abschnitt beschrieben. Die Formatierung ist optional, aber wenn sie nicht dem vorgeschriebenen Format entspricht, werden die Berichte immer als Phishing übermittelt.

## <a name="message-submission-format"></a>Nachrichtenübermittlungsformat

Um die ursprünglichen angefügten Nachrichten korrekt zu identifizieren, erfordern Nachrichten, die an das benutzerdefinierte Postfach gesendet werden, eine bestimmte Formatierung. Wenn die Nachrichten dieses Format nicht verwenden, werden die ursprünglichen angefügten Nachrichten immer als Phishing-Übermittlungen identifiziert.

Zur korrekten Identifizierung der ursprünglichen angefügten Nachrichten müssen Nachrichten, die an das benutzerdefinierte Postfach gesendet werden, die folgende Syntax für den Betreff (Briefumschlagtitel) verwenden:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

dabei ist SafetyAPIAction einer der folgenden ganzzahligen Werte:

- 1: Junk
- 2: Kein Junk
- 3: Phishing

In diesem Beispiel werden die folgenden Werte verwendet:

- Die Nachricht wird als Phishing gemeldet.
- Die Netzwerknachrichten-ID lautet 49871234-6dc6-43e8-abcd-08d797f20abe.
- Die Absender-IP lautet 167.220.232.101.
- Die Absenderadresse ist test@contoso.com.
- Die Betreffzeile der Nachricht lautet "Phishing-Testübermittlung".

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

Nachrichten, die diesem Format nicht folgen, werden im Übermittlungsportal nicht ordnungsgemäß angezeigt.

---
title: Melden von Junk-und Phishing-e-Mails in Outlook im Internet
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratoren können Informationen zu den integrierten Junk-, nicht Junk-und Phishing-e-Mail-Berichtoptionen in Outlook im Internet (Outlook Web App) in Exchange Online und zum Deaktivieren dieser Berichtsoptionen für Benutzer erhalten.
ms.openlocfilehash: 75be22d6ec38ca3c8d11836ea28c7af74b93f14c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201243"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Melden von Junk-und Phishing-e-Mails in Outlook im Internet in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Postfächern in Exchange Online können Sie die integrierten Berichtsoptionen in Outlook im Internet (früher bekannt als Outlook Web App) verwenden, um falsch positive Ergebnisse (gute e-Mail-Nachrichten als Spam gekennzeichnet), falsche Negative (ungültige e-Mail-Nachricht) und Phishing-Nachrichten an Exchange Online Protection (EoP) zu senden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Wenn Sie ein Administrator in einer Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungen-Portal im Security & Compliance Center zu verwenden. Weitere Informationen finden Sie unter [Verwenden der Administrator Übermittlung zum Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft](admin-submission.md).

- Administratoren können Benutzern das Melden von Nachrichten an Microsoft in Outlook im Internet deaktivieren oder aktivieren. Ausführliche Informationen finden Sie im Abschnitt [deaktivieren oder Aktivieren von Junk-e-Mail-Berichten in Outlook im Internet](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) weiter unten in diesem Thema.

- Sie können gemeldete Nachrichten so konfigurieren, dass Sie kopiert oder an ein von Ihnen angegebenes Postfach umgeleitet werden. Weitere Informationen finden Sie unter [Angeben eines Postfachs für Benutzer Übermittlungen von Spam-und Phishing-Nachrichten in Exchange Online](user-submission.md).

- Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>Melden von Spam-und Phishing-Nachrichten in Outlook im Internet

1. Verwenden Sie für Nachrichten im Posteingang oder in einem anderen e-Mail-Ordner außer Junk-e-Mails eine der folgenden Methoden, um Spam-und Phishing-Nachrichten zu melden:

   - Wählen Sie die Nachricht aus, klicken Sie auf der Symbolleiste auf **Junk** , und wählen Sie dann **Junk** oder **Phishing**aus.

     ![Melden von Junk-oder Phishing-e-Mails über das Menüband](../../media/owa-report-junk.png)

   - Wählen Sie eine oder mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **als Junk markieren**aus.

2. Klicken Sie im angezeigten Dialogfeld auf **Bericht**. Wenn Sie Ihre Meinung ändern, klicken Sie auf **nicht melden**.

   |Junk-E-Mail|Phishing-E-Mail|
   |:---:|:---:|
   |![Dialogfeld "Bericht als Junk"](../../media/owa-report-as-junk-dialog.png)|![Dialogfeld "als Phishing melden"](../../media/owa-report-as-phishing-dialog.png)|

3. Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet. Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>Melden von nicht-Spam-und Phishing-Nachrichten aus dem Junk-e-Mail-Ordner in Outlook im Internet

1. Verwenden Sie im Junk-e-Mail-Ordner eine der folgenden Methoden, um Spam-falsch positive Ergebnisse oder Phishing-Nachrichten zu melden:

   - Wählen Sie die Nachricht aus, klicken Sie auf der Symbolleiste auf **kein Junk-e** -Mail, und wählen Sie dann **nicht Junk** -oder **Phishing**aus.

     ![Melden von Junk-oder Phishing-e-Mails über das Menüband](../../media/owa-report-not-junk.png)

   - Wählen Sie eine oder mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **als nicht Junk markieren**aus.

2. Lesen Sie im daraufhin angezeigten Dialogfeld die Informationen, und klicken Sie auf **Bericht**. Wenn Sie Ihre Meinung ändern, klicken Sie auf **nicht melden**.

   |Keine Junk-E-Mail|Phishing|
   |:---:|:---:|
   |![Dialogfeld "Bericht als nicht-Junk"](../../media/owa-report-as-not-junk-dialog.png)|![Dialogfeld "als Phishing melden"](../../media/owa-report-as-phishing-dialog.png)|

3. Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet. Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Deaktivieren oder Aktivieren von Junk-e-Mail-Berichten in Outlook im Internet

Standardmäßig können Benutzer Spam-falsch positive Ergebnisse, falsch negative Werte und Phishing-Nachrichten an Microsoft zur Analyse in Outlook im Internet melden. Administratoren können Outlook im webpostfach-Richtlinien in Exchange Online PowerShell konfigurieren, um zu verhindern, dass Benutzer Spam-falsch positive Ergebnisse und Spam-falsch negative an Microsoft melden. Sie können die Möglichkeit für Benutzer nicht deaktivieren, Phishing-Nachrichten an Microsoft zu melden.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Rollen **Empfängerrichtlinien** oder **e-Mail-Empfänger** in Exchange Online, die standardmäßig der Rollengruppe **Organisationsverwaltung** und **Empfänger Verwaltungsdienste** zugewiesen sind. Weitere Informationen zu Rollengruppen in Exchange Online finden Sie unter [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).

- Jede Organisation verfügt über eine Standardrichtlinie mit dem Namen OwaMailboxPolicy-Default, aber Sie können benutzerdefinierte Richtlinien erstellen. Benutzerdefinierte Richtlinien werden vor der Standardrichtlinie auf Bereichs Benutzer angewendet. Weitere Informationen zu Outlook im WebPost Fach Richtlinien finden Sie unter [Outlook im webpostfach-Richtlinien in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).

- Durch Deaktivieren der Junk-e-Mail-Berichterstellung wird die Möglichkeit, eine Nachricht nicht als Junk oder Junk in Outlook im Internet zu markieren, nicht entfernt. Wenn Sie eine Nachricht im Ordner Junk-e-Mail auswählen und auf **nicht Junk** -und-Junk klicken, wird \> **Not junk** die Nachricht weiterhin in den Posteingang verschoben. Wenn Sie eine Nachricht in einem anderen e-Mail-Ordner auswählen und auf **Junk** \> - **Junk** klicken, wird die Nachricht weiterhin in den Ordner Junk-e-Mail verschoben. Nicht mehr verfügbar ist die Option, die Nachricht an Microsoft zu melden.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Verwenden Exchange Online PowerShell zum Deaktivieren oder Aktivieren von Junk-e-Mail-Berichten in Outlook im Internet

1. Führen Sie den folgenden Befehl aus, um Ihre vorhandenen Outlook im Internet-Postfachrichtlinien und den Status der Junk-e-Mail-Berichterstellung zu finden:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Verwenden Sie die folgende Syntax, um die Junk-e-Mail-Berichterstellung in Outlook im Internet zu deaktivieren oder zu aktivieren:

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   In diesem Beispiel wird die Junk-e-Mail-Berichterstellung in der Standardrichtlinie deaktiviert.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   In diesem Beispiel wird die Junk-e-Mail-Berichterstellung in der benutzerdefinierten Richtlinie Contoso Managers aktiviert.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) und [Sets-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Um zu überprüfen, ob Sie die Junk-e-Mail-Berichterstellung in Outlook im Internet erfolgreich aktiviert oder deaktiviert haben, führen Sie einen der folgenden Schritte aus:

- Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, und überprüfen Sie den Wert der **ReportJunkEmailEnabled** -Eigenschaft:

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Internet, wählen Sie eine Nachricht im Posteingang aus, klicken Sie auf **Junk** \> - **e** -Mail, und überprüfen Sie, ob die Aufforderung zum Melden der Nachricht an Microsoft angezeigt wird oder nicht.<sup>\*</sup>

- Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Internet, wählen Sie eine Nachricht im Ordner Junk-e-Mail aus, klicken Sie auf **Junk** - \> **Junk** , und überprüfen Sie, ob die Aufforderung zum Melden der Nachricht an Microsoft angezeigt wird oder nicht.<sup>\*</sup>

<sup>\*</sup> Benutzer können die Eingabeaufforderung ausblenden, um die Nachricht zu melden, während Sie die Nachricht weiterhin meldet. So überprüfen Sie diese Einstellung in Outlook im Internet:

1. Klicken Sie auf **Einstellungen** ![ Outlook im Webeinstellungen-Symbol ](../../media/owa-settings-icon.png) \> **alle Outlook** \> **-Einstellungen Junk-e-Mail**anzeigen.
2. Überprüfen Sie im Abschnitt **Berichterstellung** den Wert: **Fragen Sie mich vor dem Senden eines Berichts**.

   ![Outlook im Interneteinstellungen für Junk-e-Mail-Berichte](../../media/owa-junk-email-reporting-options.png)

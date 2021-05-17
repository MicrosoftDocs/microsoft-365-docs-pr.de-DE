---
title: Melden von Junk- und Phishing-E-Mails in Outlook im Web
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratoren können sich über die integrierten Junk-, nicht Junk- und Phishing-E-Mail-Berichtsoptionen in Outlook im Web (Outlook Web App) in Exchange Online informieren und erfahren, wie sie diese Berichterstellungsoptionen für Benutzer deaktivieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 933387dd32a6c1ca1e27ee11e4a9384615e8fdec
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615211"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Melden von Junk- und Phishing-E-Mails in Outlook im Web in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder lokalen Postfächern [](../../enterprise/hybrid-modern-auth-overview.md)mit moderner Hybridauthentifizierung können Sie falsch positive Nachrichten (gute E-Mails, die als Spam gekennzeichnet sind), falsch negative Nachrichten (ungültige E-Mails zulässig) und Phishingnachrichten an Exchange Online Protection (EOP) senden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Für eine optimale Benutzerübermittlung empfehlen wir die Verwendung der Berichtsnachricht und der Phishing-Add-Ins melden. Weitere [Informationen finden Sie unter Enable the Report Message add-in](./enable-the-report-message-add-in.md) und Enable the Report Phishing [add-in.](./enable-the-report-phish-add-in.md)

- Wenn Sie ein Administrator in einer Organisation mit Exchange Online sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden. Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

- Administratoren können die Möglichkeit für Benutzer deaktivieren oder aktivieren, Nachrichten an Microsoft Outlook im Web zu melden. Weitere Informationen finden Sie im Abschnitt Deaktivieren oder Aktivieren von Junk-E-Mail-Outlook im [Web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) weiter weiter später in diesem Artikel.

- Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen festgelegtes Postfach kopiert oder umgeleitet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien](user-submission.md).

- Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Deaktivieren oder Aktivieren der Junk-E-Mail-Outlook im Web

Standardmäßig können Benutzer Spam falsch positive, falsch negative und Phishingnachrichten an Microsoft zur Analyse in Outlook im Web melden. Administratoren können Outlook in Exchange Online PowerShell konfigurieren, um zu verhindern, dass Benutzer Spam falsch positive und Spam-falsch negative Nachrichten an Microsoft melden. Sie können die Möglichkeit für Benutzer, Phishingnachrichten an Microsoft zu melden, nicht deaktivieren.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Wie Sie eine Verbindung mit Exchange Online-PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel Exchange Online, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Rollen **Empfängerrichtlinien** oder **E-Mail-Empfänger,** die standardmäßig den Rollengruppen Organisationsverwaltung und Empfängerverwaltung zugewiesen sind.   Weitere Informationen zu Rollengruppen in Exchange Online finden Sie unter [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) und Modify role groups in [Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).

- Jede Organisation verfügt über eine Standardrichtlinie mit dem Namen OwaMailboxPolicy-Default, Sie können jedoch benutzerdefinierte Richtlinien erstellen. Benutzerdefinierte Richtlinien werden auf Bereichsbenutzer vor der Standardrichtlinie angewendet. Weitere Informationen zu Outlook in den Webpostfachrichtlinien finden Sie unter Outlook in den [Webpostfachrichtlinien in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).

- Durch das Deaktivieren der Junk-E-Mail-Berichterstellung wird nicht die Möglichkeit zum Markieren einer Nachricht als Junk oder nicht als Junk in Outlook im Web entfernt. Wenn Sie eine Nachricht im Ordner Junk-E-Mail auswählen und auf **Nicht** Junk Nicht Junk klicken, wird die Nachricht trotzdem wieder \>  in den Posteingang verschoben. Wenn Sie eine Nachricht in einem  anderen E-Mail-Ordner auswählen und auf Junk-Junk klicken, wird die Nachricht weiterhin \>  in den Junk-E-Mail-Ordner verschoben. Was nicht mehr verfügbar ist, ist die Option, die Nachricht an Microsoft zu melden.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Verwenden Exchange Online PowerShell zum Deaktivieren oder Aktivieren von Junk-E-Mail-Outlook im Web

1. Führen Sie den folgenden Befehl aus, Outlook sie in den Webpostfachrichtlinien und den Status der Junk-E-Mail-Berichterstellung finden möchten:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Verwenden Sie die folgende Syntax, um die Junk-E-Mail-Outlook im Web zu deaktivieren oder zu aktivieren:

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   In diesem Beispiel wird die Junk-E-Mail-Berichterstellung in der Standardrichtlinie deaktiviert.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   In diesem Beispiel wird die Junk-E-Mail-Berichterstellung in der benutzerdefinierten Richtlinie namens Contoso Managers aktiviert.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) und [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Verwenden Sie einen der folgenden Schritte, um zu überprüfen, ob die Junk-E-Mail-Berichterstellung in Outlook im Web erfolgreich aktiviert oder deaktiviert wurde:

- Führen Exchange Online in powerShell den folgenden Befehl aus, und überprüfen Sie den Wert der **ReportJunkEmailEnabled-Eigenschaft:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Web, wählen  Sie eine Nachricht im Posteingang aus, klicken Sie auf Junk-Junk, und überprüfen Sie, ob die Meldung an Microsoft angezeigt wird oder nicht \>  angezeigt wird.<sup>\*</sup>

- Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Web, wählen Sie  eine Nachricht im Ordner Junk-E-Mail aus, klicken Sie auf Junk-Junk, und überprüfen Sie, ob die Meldung an Microsoft angezeigt wird oder nicht \>  angezeigt wird.<sup>\*</sup>

<sup>\*</sup> Benutzer können die Aufforderung zum Melden der Nachricht ausblenden, während sie die Nachricht weiterhin melden. So überprüfen Sie diese Einstellung Outlook im Web:

1. Klicken **Einstellungen** Outlook im Webeinstellungen-Symbol Alle Einstellungen ![ anzeigen Outlook ](../../media/owa-settings-icon.png) \>  \> **Junk-E-Mail anzeigen.**
2. Überprüfen Sie **im Abschnitt** Berichterstellung den Wert: Fragen **Sie mich, bevor Sie einen Bericht senden.**

   ![Outlook im Web Junk-E-Mail-Berichterstellungseinstellungen](../../media/owa-junk-email-reporting-options.png)
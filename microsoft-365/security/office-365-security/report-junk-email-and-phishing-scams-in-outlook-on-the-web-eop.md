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
description: Administratoren können sich über die integrierten Optionen für Junk-, nicht Junk- und Phishing-E-Mail-Berichterstellung in Outlook im Web (Outlook Web App) in Exchange Online informieren und erfahren, wie diese Berichtsoptionen für Benutzer deaktiviert werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788307"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Melden von Junk- und Phishing-E-Mails in Outlook im Web in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder lokalen Postfächern mit [moderner Hybridauthentifizierung](../../enterprise/hybrid-modern-auth-overview.md)können Sie falsch positive Ergebnisse (als Spam markierte gute E-Mails), falsch negative Nachrichten (ungültige E-Mails sind zulässig) und Phishingnachrichten an Exchange Online Protection (EOP) übermitteln.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

> [!IMPORTANT]
> Wir empfehlen das Add-In "Nachricht melden" oder das Add-In "Phishing melden" für Benutzerübermittlungen. Weitere Informationen finden Sie unter [Aktivieren der Berichtsnachricht oder der Phishing-Add-Ins "Bericht".](./enable-the-report-message-add-in.md) Es wird nicht empfohlen, die integrierte Berichterstellung in Outlook zu verwenden, da die [Benutzerübermittlungsrichtlinie](./user-submission.md)nicht verwendet werden kann.

- Wenn Sie ein Administrator in einer Organisation mit Exchange Online Postfächern sind, empfehlen wir, das Übermittlungsportal im Security & Compliance Center zu verwenden. Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)

- Administratoren können die Möglichkeit für Benutzer deaktivieren oder aktivieren, Nachrichten in Outlook im Web an Microsoft zu melden. Ausführliche Informationen finden Sie unter "Deaktivieren oder Aktivieren der [Junk-E-Mail-Berichterstellung in Outlook im Webabschnitt](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) weiter unten in diesem Artikel".

- Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen angegebenes Postfach kopiert oder umgeleitet werden. Weitere Informationen finden Sie unter [Richtlinien für Benutzerübermittlungen.](user-submission.md)

- Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Melden von Nachrichten und Dateien an Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Deaktivieren oder Aktivieren der Junk-E-Mail-Berichterstellung in Outlook im Web

Standardmäßig können Benutzer Falsch positive Spamnachrichten, falsch negative Ergebnisse und Phishingnachrichten zur Analyse in Outlook im Web an Microsoft melden. Administratoren können Outlook in den Postfachrichtlinien im Web in Exchange Online PowerShell konfigurieren, um zu verhindern, dass Benutzer Spam falsch positive ergebnisse und falsch negative Spamnachrichten an Microsoft melden. Sie können die Möglichkeit für Benutzer, Phishingnachrichten an Microsoft zu melden, nicht deaktivieren.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen in Exchange Online Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die **Empfängerrichtlinien** oder **E-Mail-Empfängerrollen,** die standardmäßig den Rollengruppen **"Organisationsverwaltung"** und **"Empfängerverwaltung"** zugewiesen sind. Weitere Informationen zu Rollengruppen in Exchange Online finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo) und Ändern von [Rollengruppen in Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups)

- Jede Organisation verfügt über eine Standardrichtlinie mit dem Namen OwaMailboxPolicy-Default, Sie können jedoch benutzerdefinierte Richtlinien erstellen. Benutzerdefinierte Richtlinien werden vor der Standardrichtlinie auf bereichsbezogene Benutzer angewendet. Weitere Informationen zu Outlook im Web-Postfachrichtlinien finden Sie unter [Outlook in den Webpostfachrichtlinien in Exchange Online.](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)

- Das Deaktivieren der Junk-E-Mail-Berichterstellung entfernt nicht die Möglichkeit, eine Nachricht in Outlook im Web als Junk oder nicht als Junk zu kennzeichnen. Wenn Sie eine Nachricht im Junk-E-Mail-Ordner auswählen und auf **"Keine Junk-Junk-Nachricht"** klicken, \>  wird die Nachricht trotzdem zurück in den Posteingang verschoben. Wenn Sie eine Nachricht in einem  beliebigen anderen E-Mail-Ordner auswählen und auf \> **Junk-Junk** klicken, wird die Nachricht dennoch in den Junk-E-Mail-Ordner verschoben. Was nicht mehr verfügbar ist, ist die Option, die Nachricht an Microsoft zu melden.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Verwenden Exchange Online PowerShell zum Deaktivieren oder Aktivieren der Junk-E-Mail-Berichterstellung in Outlook im Web

1. Führen Sie den folgenden Befehl aus, um Ihre vorhandenen Outlook im Web-Postfachrichtlinien und den Status der Junk-E-Mail-Berichterstellung zu finden:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Verwenden Sie die folgende Syntax, um die Junk-E-Mail-Berichterstellung in Outlook im Web zu deaktivieren oder zu aktivieren:

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-OwaMailboxPolicy"](/powershell/module/exchange/get-owamailboxpolicy) und ["Set-OwaMailboxPolicy".](/powershell/module/exchange/set-owamailboxpolicy)

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Die Junk-E-Mail-Berichterstellung in Outlook im Web erfolgreich aktiviert oder deaktiviert wurde:

- Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, und überprüfen Sie den Wert der **ReportJunkEmailEnabled-Eigenschaft:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Web, wählen Sie eine Nachricht im Posteingang aus, klicken Sie auf **Junk-Junk,** \>  und überprüfen Sie, ob die Aufforderung, die Nachricht an Microsoft zu melden, angezeigt wird oder nicht.<sup>\*</sup>

- Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Web, wählen Sie eine Nachricht im Junk-E-Mail-Ordner aus, klicken Sie auf **Junk-Junk,** \>  und überprüfen Sie, ob die Aufforderung, die Nachricht an Microsoft zu melden, angezeigt wird oder nicht.<sup>\*</sup>

<sup>\*</sup> Benutzer können die Eingabeaufforderung ausblenden, um die Nachricht zu melden, während sie die Nachricht weiterhin melden. So überprüfen Sie diese Einstellung in Outlook im Web:

1. Klicken Sie **auf Einstellungen** Outlook im ![ Symbol "Webeinstellungen ](../../media/owa-settings-icon.png) \> **anzeigen alle Outlook Einstellungen** \> **Junk-E-Mail** anzeigen".
2. Überprüfen Sie im Abschnitt **"Berichterstellung"** den Wert: **Fragen Sie mich vor dem Senden eines Berichts.**

   ![Outlook in den Junk-E-Mail-Berichterstellungseinstellungen im Web](../../media/owa-junk-email-reporting-options.png)

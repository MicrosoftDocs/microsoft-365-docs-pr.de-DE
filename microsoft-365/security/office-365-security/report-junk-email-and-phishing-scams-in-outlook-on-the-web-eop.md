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
description: Administratoren können sich über die integrierten Junk-, nicht Junk- und Phishing-E-Mail-Berichterstellungsoptionen in Outlook im Web (Outlook Web App) in Exchange Online informieren und erfahren, wie Sie diese Berichterstellungsoptionen für Benutzer deaktivieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77a1233b85ad213091ac84ac6f7e8eb93d9145af
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205726"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="ef1bf-103">Melden von Junk- und Phishing-E-Mails in Outlook im Web in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ef1bf-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ef1bf-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="ef1bf-104">**Applies to**</span></span>
- [<span data-ttu-id="ef1bf-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ef1bf-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ef1bf-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="ef1bf-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ef1bf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef1bf-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ef1bf-108">In Microsoft 365-Organisationen mit Postfächern in Exchange Online können Sie die integrierten Berichtsoptionen in Outlook im Web (früher als Outlook Web App bezeichnet) verwenden, um falsch positive Ergebnisse (gute E-Mails, die als Spam gekennzeichnet sind), falsch negative Nachrichten (ungültige E-Mails zulässig) und Phishingnachrichten an Exchange Online Protection (EOP) zu senden.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-108">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ef1bf-109">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="ef1bf-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ef1bf-110">Wenn Sie ein Administrator in einer Organisation mit Exchange Online-Postfächern sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="ef1bf-111">Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="ef1bf-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="ef1bf-112">Administratoren können die Möglichkeit für Benutzer deaktivieren oder aktivieren, Nachrichten an Microsoft in Outlook im Web zu melden.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-112">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="ef1bf-113">Weitere Informationen finden Sie im Abschnitt Deaktivieren oder [Aktivieren der Junk-E-Mail-Berichterstellung in Outlook im Web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) weiter in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-113">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="ef1bf-114">Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen festgelegtes Postfach kopiert oder umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-114">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="ef1bf-115">Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="ef1bf-115">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="ef1bf-116">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ef1bf-116">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="ef1bf-117">Melden von Spam- und Phishingnachrichten in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="ef1bf-117">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="ef1bf-118">Verwenden Sie für Nachrichten im Posteingang oder in einem anderen E-Mail-Ordner mit Ausnahme von Junk-E-Mails eine der folgenden Methoden, um Spam- und Phishingnachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="ef1bf-118">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="ef1bf-119">Wählen Sie die Nachricht aus, klicken Sie **auf der** Symbolleiste auf Junk, und wählen Sie dann **Junk oder** **Phishing aus.**</span><span class="sxs-lookup"><span data-stu-id="ef1bf-119">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Melden von Junk- oder Phishing-E-Mails über das Menüband](../../media/owa-report-junk.png)

   - <span data-ttu-id="ef1bf-121">Wählen Sie eine oder mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie **dann Als Junk markieren aus.**</span><span class="sxs-lookup"><span data-stu-id="ef1bf-121">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="ef1bf-122">Klicken Sie im angezeigten Dialogfeld auf **Bericht**.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-122">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="ef1bf-123">Wenn Sie Ihre Meinung ändern, klicken Sie auf **Nicht melden**.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-123">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="ef1bf-124">Junk-E-Mail</span><span class="sxs-lookup"><span data-stu-id="ef1bf-124">Junk</span></span>|<span data-ttu-id="ef1bf-125">Phishing-E-Mail</span><span class="sxs-lookup"><span data-stu-id="ef1bf-125">Phishing</span></span>|
   |:---:|:---:|
   |![Melden als Junkdialogfeld](../../media/owa-report-as-junk-dialog.png)|![Melden als Phishingdialogfeld](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="ef1bf-128">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-128">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="ef1bf-129">Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-129">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="ef1bf-130">Melden von Nichtspam- und Phishingnachrichten aus dem Junk-E-Mail-Ordner in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="ef1bf-130">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="ef1bf-131">Verwenden Sie im Ordner Junk-E-Mail eine der folgenden Methoden, um Spam falsch positive Nachrichten oder Phishingnachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="ef1bf-131">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="ef1bf-132">Wählen Sie die Nachricht aus, klicken **Sie auf der** Symbolleiste auf Nicht Junk, und wählen Sie dann Nicht Junk **oder** **Phishing aus.**</span><span class="sxs-lookup"><span data-stu-id="ef1bf-132">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Melden sie keine Junk-E-Mails oder keine Phishing-E-Mails vom Menüband](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="ef1bf-134">Wählen Sie eine oder mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie **dann Als Junk markieren aus.**</span><span class="sxs-lookup"><span data-stu-id="ef1bf-134">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="ef1bf-135">Lesen Sie im angezeigten Dialogfeld die Informationen, und klicken Sie auf **Bericht**.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-135">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="ef1bf-136">Wenn Sie Ihre Meinung ändern, klicken Sie auf **Nicht melden**.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-136">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="ef1bf-137">Keine Junk-E-Mail</span><span class="sxs-lookup"><span data-stu-id="ef1bf-137">Not Junk</span></span>|<span data-ttu-id="ef1bf-138">Phishing</span><span class="sxs-lookup"><span data-stu-id="ef1bf-138">Phishing</span></span>|
   |:---:|:---:|
   |![Melden als Nicht-Junk-Dialogfeld](../../media/owa-report-as-not-junk-dialog.png)|![Melden als Phishingdialogfeld](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="ef1bf-141">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-141">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="ef1bf-142">Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-142">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="ef1bf-143">Deaktivieren oder Aktivieren der Junk-E-Mail-Berichterstellung in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="ef1bf-143">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="ef1bf-144">Standardmäßig können Benutzer Spam falsch positive, falsch negative und Phishingnachrichten zur Analyse in Outlook im Web an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-144">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="ef1bf-145">Administratoren können Outlook im Web-Postfachrichtlinien in Exchange Online PowerShell konfigurieren, um zu verhindern, dass Benutzer Spam falsch positive und Spam-falsch negative Nachrichten an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-145">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="ef1bf-146">Sie können die Möglichkeit für Benutzer, Phishingnachrichten an Microsoft zu melden, nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-146">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ef1bf-147">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="ef1bf-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ef1bf-148">Wie Sie eine Verbindung mit Exchange Online-PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ef1bf-148">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ef1bf-149">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-149">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="ef1bf-150">Insbesondere benötigen Sie die Rollen **Empfängerrichtlinien** oder **E-Mail-Empfänger,** die standardmäßig den Rollengruppen Organisationsverwaltung und Empfängerverwaltung zugewiesen sind.  </span><span class="sxs-lookup"><span data-stu-id="ef1bf-150">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="ef1bf-151">Weitere Informationen zu Rollengruppen in Exchange Online finden Sie unter [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) und Modify role groups in Exchange [Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="ef1bf-151">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="ef1bf-152">Jede Organisation verfügt über eine Standardrichtlinie mit dem Namen OwaMailboxPolicy-Default, Sie können jedoch benutzerdefinierte Richtlinien erstellen.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-152">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="ef1bf-153">Benutzerdefinierte Richtlinien werden auf Bereichsbenutzer vor der Standardrichtlinie angewendet.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-153">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="ef1bf-154">Weitere Informationen zu Outlook im Webpostfachrichtlinien finden Sie unter [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="ef1bf-154">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="ef1bf-155">Durch das Deaktivieren der Junk-E-Mail-Berichterstellung kann eine Nachricht nicht als Junk oder nicht als Junk in Outlook im Web markiert werden.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-155">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="ef1bf-156">Wenn Sie eine Nachricht im Ordner Junk-E-Mail auswählen und auf **Nicht** Junk Nicht Junk klicken, wird die Nachricht trotzdem wieder \>  in den Posteingang verschoben.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-156">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="ef1bf-157">Wenn Sie eine Nachricht in einem  anderen E-Mail-Ordner auswählen und auf Junk-Junk klicken, wird die Nachricht weiterhin \>  in den Junk-E-Mail-Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-157">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="ef1bf-158">Was nicht mehr verfügbar ist, ist die Option, die Nachricht an Microsoft zu melden.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-158">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="ef1bf-159">Verwenden von Exchange Online PowerShell zum Deaktivieren oder Aktivieren der Junk-E-Mail-Berichterstellung in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="ef1bf-159">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="ef1bf-160">Führen Sie den folgenden Befehl aus, um ihre vorhandenen Outlook im Webpostfachrichtlinien und den Status der Junk-E-Mail-Berichterstellung zu finden:</span><span class="sxs-lookup"><span data-stu-id="ef1bf-160">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="ef1bf-161">Verwenden Sie die folgende Syntax, um die Junk-E-Mail-Berichterstellung in Outlook im Web zu deaktivieren oder zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="ef1bf-161">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="ef1bf-162">In diesem Beispiel wird die Junk-E-Mail-Berichterstellung in der Standardrichtlinie deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-162">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="ef1bf-163">In diesem Beispiel wird die Junk-E-Mail-Berichterstellung in der benutzerdefinierten Richtlinie namens Contoso Managers aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-163">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="ef1bf-164">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) und [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="ef1bf-164">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ef1bf-165">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="ef1bf-165">How do you know this worked?</span></span>

<span data-ttu-id="ef1bf-166">Um zu überprüfen, ob Sie die Junk-E-Mail-Berichterstellung in Outlook im Web erfolgreich aktiviert oder deaktiviert haben, verwenden Sie einen der folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="ef1bf-166">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="ef1bf-167">Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, und überprüfen Sie den Wert der **ReportJunkEmailEnabled-Eigenschaft:**</span><span class="sxs-lookup"><span data-stu-id="ef1bf-167">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="ef1bf-168">Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Web,  wählen Sie eine Nachricht im Posteingang aus, klicken Sie auf Junk-Junk, und überprüfen Sie, ob die Meldung an Microsoft angezeigt wird oder nicht \>  angezeigt wird.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ef1bf-168">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="ef1bf-169">Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Web,  wählen Sie eine Nachricht im Ordner Junk-E-Mail aus, klicken Sie auf Junk-Junk, und überprüfen Sie, ob die Meldung an Microsoft angezeigt wird oder nicht \>  angezeigt wird.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ef1bf-169">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="ef1bf-170"><sup>\*</sup> Benutzer können die Aufforderung zum Melden der Nachricht ausblenden, während sie die Nachricht weiterhin melden.</span><span class="sxs-lookup"><span data-stu-id="ef1bf-170"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="ef1bf-171">So überprüfen Sie diese Einstellung in Outlook im Web:</span><span class="sxs-lookup"><span data-stu-id="ef1bf-171">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="ef1bf-172">Klicken **Sie auf Einstellungen** Outlook im ![ Webeinstellungen Symbol Alle ](../../media/owa-settings-icon.png) \> **Outlook-Einstellungen** \> **Junk-E-Mail anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="ef1bf-172">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="ef1bf-173">Überprüfen Sie **im Abschnitt** Berichterstellung den Wert: Fragen **Sie mich, bevor Sie einen Bericht senden.**</span><span class="sxs-lookup"><span data-stu-id="ef1bf-173">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Einstellungen für die Junk-E-Mail-Berichterstellung in Outlook im Web](../../media/owa-junk-email-reporting-options.png)
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
description: Administratoren können sich über die integrierten Junk-E-Mail-, nicht Junk- und Phishing-E-Mail-Berichtsoptionen in Outlook im Web (Outlook Web App) in Exchange Online informieren und erfahren, wie Sie diese Berichtsoptionen für Benutzer deaktivieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0af57aceed608ae80e72e3ae18724925c1168e26
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029210"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="00d13-103">Melden von Junk- und Phishing-E-Mails in Outlook im Web in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="00d13-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="00d13-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online können Sie die integrierten Berichtsoptionen in Outlook im Web (früher als Outlook Web App bezeichnet) verwenden, um falsch positive Ergebnisse (gute E-Mails als Spam gekennzeichnet), falsch negative Ergebnisse (ungültige E-Mails sind zulässig) und Phishingnachrichten an Exchange Online Protection (EOP) zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="00d13-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="00d13-105">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="00d13-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="00d13-106">Wenn Sie ein Administrator in einer Organisation mit Exchange Online-Postfächern sind, empfehlen wir die Verwendung des Übermittlungsportals im Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="00d13-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="00d13-107">Weitere Informationen finden Sie unter "Use Admin Submission", um verdächtige [Spam-, Phishing-, URLs-](admin-submission.md)und Dateien an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="00d13-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="00d13-108">Administratoren können die Möglichkeit für Benutzer, Nachrichten an Microsoft in Outlook im Web zu melden, deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="00d13-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="00d13-109">Weitere Informationen finden Sie im Abschnitt "Deaktivieren oder [Aktivieren der Junk-E-Mail-Berichterstellung in Outlook im Web"](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) weiter später in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="00d13-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="00d13-110">Sie können gemeldete Nachrichten so konfigurieren, dass sie kopiert oder an ein von Ihnen festgelegtes Postfach umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="00d13-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="00d13-111">Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="00d13-111">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="00d13-112">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter ["Melden von Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="00d13-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="00d13-113">Melden von Spam- und Phishingnachrichten in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="00d13-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="00d13-114">Verwenden Sie für Nachrichten im Posteingang oder einem anderen E-Mail-Ordner mit Ausnahme von Junk-E-Mails eine der folgenden Methoden, um Spam- und Phishingnachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="00d13-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="00d13-115">Wählen Sie die Nachricht aus, klicken **Sie auf der** Symbolleiste auf "Junk", und wählen Sie dann **"Junk"** oder **"Phishing" aus.**</span><span class="sxs-lookup"><span data-stu-id="00d13-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Melden von Junk- oder Phishing-E-Mails über das Menüband](../../media/owa-report-junk.png)

   - <span data-ttu-id="00d13-117">Wählen Sie eine oder mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie **dann "Als Junk markieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="00d13-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="00d13-118">Klicken Sie im angezeigten Dialogfeld auf **Bericht**.</span><span class="sxs-lookup"><span data-stu-id="00d13-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="00d13-119">Wenn Sie Ihre Meinung ändern, klicken Sie auf **"Nicht melden".**</span><span class="sxs-lookup"><span data-stu-id="00d13-119">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="00d13-120">Junk-E-Mail</span><span class="sxs-lookup"><span data-stu-id="00d13-120">Junk</span></span>|<span data-ttu-id="00d13-121">Phishing-E-Mail</span><span class="sxs-lookup"><span data-stu-id="00d13-121">Phishing</span></span>|
   |:---:|:---:|
   |![Dialogfeld "Als Junk melden"](../../media/owa-report-as-junk-dialog.png)|![Melden als Phishingdialogfeld](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="00d13-124">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="00d13-124">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="00d13-125">Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="00d13-125">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="00d13-126">Melden von Nichtspam- und Phishingnachrichten aus dem Junk-E-Mail-Ordner in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="00d13-126">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="00d13-127">Verwenden Sie im Junk-E-Mail-Ordner eine der folgenden Methoden, um falsch positive Spam- oder Phishingnachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="00d13-127">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="00d13-128">Wählen Sie die Nachricht aus, klicken Sie auf der Symbolleiste auf "Nicht **Junk",** und wählen Sie dann **"Nicht Junk"** oder **"Phishing" aus.**</span><span class="sxs-lookup"><span data-stu-id="00d13-128">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Melden sie keine Junk-E-Mails oder keine Phishing-E-Mails aus dem Menüband.](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="00d13-130">Wählen Sie eine oder mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann "Als Junk **markieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="00d13-130">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="00d13-131">Lesen Sie im angezeigten Dialogfeld die Informationen, und klicken Sie auf **"Bericht".**</span><span class="sxs-lookup"><span data-stu-id="00d13-131">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="00d13-132">Wenn Sie Ihre Meinung ändern, klicken Sie auf **"Nicht melden"**.</span><span class="sxs-lookup"><span data-stu-id="00d13-132">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="00d13-133">Keine Junk-E-Mail</span><span class="sxs-lookup"><span data-stu-id="00d13-133">Not Junk</span></span>|<span data-ttu-id="00d13-134">Phishing</span><span class="sxs-lookup"><span data-stu-id="00d13-134">Phishing</span></span>|
   |:---:|:---:|
   |![Dialogfeld "Kein Junk melden"](../../media/owa-report-as-not-junk-dialog.png)|![Melden als Phishingdialogfeld](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="00d13-137">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="00d13-137">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="00d13-138">Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="00d13-138">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="00d13-139">Deaktivieren oder Aktivieren der Junk-E-Mail-Berichterstellung in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="00d13-139">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="00d13-140">Standardmäßig können Benutzer falsch positive Spamnachrichten, falsch negative Ergebnisse und Phishingnachrichten zur Analyse in Outlook im Web an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="00d13-140">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="00d13-141">Administratoren können Outlook im Web-Postfachrichtlinien in Exchange Online PowerShell konfigurieren, um zu verhindern, dass Benutzer falsch positive Spam- und Spam-Negative an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="00d13-141">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="00d13-142">Sie können die Möglichkeit für Benutzer, Phishingnachrichten an Microsoft zu melden, nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="00d13-142">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="00d13-143">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="00d13-143">What do you need to know before you begin?</span></span>

- <span data-ttu-id="00d13-144">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="00d13-144">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="00d13-145">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="00d13-145">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="00d13-146">Insbesondere benötigen Sie die Rollen **"Empfängerrichtlinien"** oder **"E-Mail-Empfänger",** die standardmäßig den Rollengruppen "Organisationsverwaltung" und "Empfängerverwaltung" zugewiesen sind.  </span><span class="sxs-lookup"><span data-stu-id="00d13-146">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="00d13-147">Weitere Informationen zu Rollengruppen in Exchange Online finden Sie unter Berechtigungen [in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) und Ändern von [Rollengruppen in Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="00d13-147">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="00d13-148">Jede Organisation verfügt über eine Standardrichtlinie mit dem Namen "OwaMailboxPolicy-Default", aber Sie können benutzerdefinierte Richtlinien erstellen.</span><span class="sxs-lookup"><span data-stu-id="00d13-148">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="00d13-149">Benutzerdefinierte Richtlinien werden vor der Standardrichtlinie auf benutzerbereichsspezifische Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="00d13-149">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="00d13-150">Weitere Informationen zu Outlook im Web-Postfachrichtlinien finden Sie unter [Outlook im Web-Postfachrichtlinien in Exchange Online.](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="00d13-150">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="00d13-151">Durch das Deaktivieren der Junk-E-Mail-Berichterstellung wird die Möglichkeit, eine Nachricht in Outlook im Web als Junk- oder Nicht-Junk-E-Mail zu markieren, nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="00d13-151">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="00d13-152">Wenn Sie eine Nachricht im Junk-E-Mail-Ordner auswählen und auf "Nicht  \> **Junk-E-Mail"** klicken, wird die Nachricht wieder in den Posteingang verschoben.</span><span class="sxs-lookup"><span data-stu-id="00d13-152">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="00d13-153">Wenn Sie eine Nachricht in einem anderen E-Mail-Ordner auswählen und auf **"Junk-Junk"** klicken, wird die Nachricht weiterhin \>  in den Junk-E-Mail-Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="00d13-153">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="00d13-154">Nicht mehr verfügbar ist die Option, die Nachricht an Microsoft zu melden.</span><span class="sxs-lookup"><span data-stu-id="00d13-154">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="00d13-155">Verwenden von Exchange Online PowerShell zum Deaktivieren oder Aktivieren der Junk-E-Mail-Berichterstellung in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="00d13-155">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="00d13-156">Führen Sie den folgenden Befehl aus, um ihre vorhandenen Outlook im Web-Postfachrichtlinien und den Status der Junk-E-Mail-Berichterstellung zu finden:</span><span class="sxs-lookup"><span data-stu-id="00d13-156">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="00d13-157">Verwenden Sie die folgende Syntax, um die Junk-E-Mail-Berichterstellung in Outlook im Web zu deaktivieren oder zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="00d13-157">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="00d13-158">In diesem Beispiel wird die Junk-E-Mail-Berichterstellung in der Standardrichtlinie deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="00d13-158">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="00d13-159">In diesem Beispiel wird die Junk-E-Mail-Berichterstellung in der benutzerdefinierten Richtlinie "Contoso Managers" aktiviert.</span><span class="sxs-lookup"><span data-stu-id="00d13-159">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="00d13-160">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-OwaMailboxPolicy"](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) und ["Set-OwaMailboxPolicy".](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="00d13-160">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="00d13-161">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="00d13-161">How do you know this worked?</span></span>

<span data-ttu-id="00d13-162">Um sicherzustellen, dass Sie die Junk-E-Mail-Berichterstellung in Outlook im Web erfolgreich aktiviert oder deaktiviert haben, verwenden Sie einen der folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="00d13-162">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="00d13-163">Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, und überprüfen Sie den Wert der **Eigenschaft "ReportJunkEmailEnabled":**</span><span class="sxs-lookup"><span data-stu-id="00d13-163">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="00d13-164">Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Web,  wählen Sie eine Nachricht im Posteingang aus, klicken Sie auf Junk-E-Mail, und überprüfen Sie, ob die Aufforderung zum Melden der Nachricht an Microsoft angezeigt wird oder nicht \>  angezeigt wird.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="00d13-164">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="00d13-165">Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Web,  wählen Sie eine Nachricht im Junk-E-Mail-Ordner aus, klicken Sie auf Junk-E-Mail, und überprüfen Sie, ob die Aufforderung zum Melden der Nachricht an Microsoft angezeigt wird oder nicht \>  angezeigt wird.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="00d13-165">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="00d13-166"><sup>\*</sup> Benutzer können die Eingabeaufforderung ausblenden, um die Nachricht zu melden, während sie die Nachricht weiterhin meldet.</span><span class="sxs-lookup"><span data-stu-id="00d13-166"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="00d13-167">So überprüfen Sie diese Einstellung in Outlook im Web:</span><span class="sxs-lookup"><span data-stu-id="00d13-167">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="00d13-168">Klicken **Sie auf** ![ "Einstellungen" outlook im Web-Einstellungen symbol ](../../media/owa-settings-icon.png) \> **Anzeigen aller Outlook-Einstellungen** \> **Junk-E-Mail.**</span><span class="sxs-lookup"><span data-stu-id="00d13-168">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="00d13-169">Überprüfen Sie **im Abschnitt** "Berichterstellung" den Wert: Fragen Sie mich vor dem Senden **eines Berichts.**</span><span class="sxs-lookup"><span data-stu-id="00d13-169">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Einstellungen für die Junk-E-Mail-Berichterstellung in Outlook im Web](../../media/owa-junk-email-reporting-options.png)

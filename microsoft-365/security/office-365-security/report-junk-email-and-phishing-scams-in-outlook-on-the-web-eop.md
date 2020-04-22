---
title: 'Melden von Junk-E-Mails und Phishing-Versuchen in Outlook im Web '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Microsoft 365-Benutzer mit Exchange Online Postfächern können Outlook im Internet (Outlook Web App) verwenden, um Spam-, nicht-Spam-und Phishing-Nachrichten zur Analyse an Microsoft zu übermitteln.
ms.openlocfilehash: 858224074ef7258d59318eef0c685a4ea4f9130f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632619"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a><span data-ttu-id="2c11f-103">Melden von Junk-und Phishing-e-Mails in Outlook im Internet in Office 365</span><span class="sxs-lookup"><span data-stu-id="2c11f-103">Report junk and phishing email in Outlook on the web in Office 365</span></span>

<span data-ttu-id="2c11f-104">Wenn Sie ein Microsoft 365-Kunde mit Exchange Online Postfächern sind, können Sie die integrierten Berichtsoptionen in Outlook im Internet (früher als Outlook Web App bezeichnet) verwenden, um falsch positive Ergebnisse (gute e-Mail-Nachrichten als Spam gekennzeichnet), falsche Negative Zeichen (ungültige e-Mail-Nachricht) und Phishing-Nachrichten an Exchange Online Protection (EoP) zu senden.</span><span class="sxs-lookup"><span data-stu-id="2c11f-104">If you're a Microsoft 365 customer with Exchange Online mailboxes, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2c11f-105">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="2c11f-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2c11f-106">Wenn Sie ein Administrator in einer Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungen-Portal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2c11f-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="2c11f-107">Weitere Informationen finden Sie unter [Verwenden der Administrator Übermittlung zum Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="2c11f-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="2c11f-108">Administratoren können Benutzern das Melden von Nachrichten an Microsoft in Outlook im Internet deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2c11f-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="2c11f-109">Ausführliche Informationen finden Sie im Abschnitt [deaktivieren oder Aktivieren von Junk-e-Mail-Berichten in Outlook im Internet](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="2c11f-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="2c11f-110">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Report Messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="2c11f-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="2c11f-111">Melden von Spam-und Phishing-Nachrichten in Outlook im Internet</span><span class="sxs-lookup"><span data-stu-id="2c11f-111">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="2c11f-112">Verwenden Sie für Nachrichten im Posteingang oder in einem anderen e-Mail-Ordner außer Junk-e-Mails eine der folgenden Methoden, um Spam-und Phishing-Nachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="2c11f-112">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="2c11f-113">Wählen Sie die Nachricht aus, klicken Sie auf der Symbolleiste auf **Junk** , und wählen Sie dann **Junk** oder **Phishing**aus.</span><span class="sxs-lookup"><span data-stu-id="2c11f-113">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Melden von Junk-oder Phishing-e-Mails über das Menüband](../../media/owa-report-junk.png)

   - <span data-ttu-id="2c11f-115">Wählen Sie eine oder mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **als Junk markieren**aus.</span><span class="sxs-lookup"><span data-stu-id="2c11f-115">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="2c11f-116">Klicken Sie im angezeigten Dialogfeld auf **Bericht**.</span><span class="sxs-lookup"><span data-stu-id="2c11f-116">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="2c11f-117">Wenn Sie Ihre Meinung ändern, klicken Sie auf **nicht melden**.</span><span class="sxs-lookup"><span data-stu-id="2c11f-117">If you change your mind, click **Don't Report**.</span></span>

   ![Dialogfeld "Bericht als Junk"](../../media/owa-report-as-junk-dialog.png)

   ![Dialogfeld "als Phishing melden"](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="2c11f-120">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="2c11f-120">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="2c11f-121">Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="2c11f-121">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="2c11f-122">Melden von nicht-Spam-und Phishing-Nachrichten aus dem Junk-e-Mail-Ordner in Outlook im Internet</span><span class="sxs-lookup"><span data-stu-id="2c11f-122">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="2c11f-123">Verwenden Sie im Junk-e-Mail-Ordner eine der folgenden Methoden, um Spam-falsch positive Ergebnisse oder Phishing-Nachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="2c11f-123">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="2c11f-124">Wählen Sie die Nachricht aus, klicken Sie auf der Symbolleiste auf **kein Junk-e** -Mail, und wählen Sie dann **nicht Junk** -oder **Phishing**aus.</span><span class="sxs-lookup"><span data-stu-id="2c11f-124">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Melden von Junk-oder Phishing-e-Mails über das Menüband](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="2c11f-126">Wählen Sie eine oder mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **als nicht Junk markieren**aus.</span><span class="sxs-lookup"><span data-stu-id="2c11f-126">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="2c11f-127">Lesen Sie im daraufhin angezeigten Dialogfeld die Informationen, und klicken Sie auf **Bericht**.</span><span class="sxs-lookup"><span data-stu-id="2c11f-127">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="2c11f-128">Wenn Sie Ihre Meinung ändern, klicken Sie auf **nicht melden**.</span><span class="sxs-lookup"><span data-stu-id="2c11f-128">If you change your mind, click **Don't Report**.</span></span>

   ![Dialogfeld "Bericht als nicht-Junk"](../../media/owa-report-as-not-junk-dialog.png)

   ![Dialogfeld "als Phishing melden"](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="2c11f-131">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="2c11f-131">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="2c11f-132">Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="2c11f-132">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="2c11f-133">Deaktivieren oder Aktivieren von Junk-e-Mail-Berichten in Outlook im Internet</span><span class="sxs-lookup"><span data-stu-id="2c11f-133">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="2c11f-134">Standardmäßig können Benutzer Spam-falsch positive Ergebnisse, falsch negative Werte und Phishing-Nachrichten an Microsoft zur Analyse in Outlook im Internet melden.</span><span class="sxs-lookup"><span data-stu-id="2c11f-134">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="2c11f-135">Administratoren können Outlook im webpostfach-Richtlinien in Exchange Online PowerShell konfigurieren, um zu verhindern, dass Benutzer Spam-falsch positive Ergebnisse und Spam-falsch negative an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="2c11f-135">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="2c11f-136">Sie können die Möglichkeit für Benutzer nicht deaktivieren, Phishing-Nachrichten an Microsoft zu melden.</span><span class="sxs-lookup"><span data-stu-id="2c11f-136">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2c11f-137">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="2c11f-137">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2c11f-138">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2c11f-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="2c11f-139">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="2c11f-139">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="2c11f-140">Insbesondere benötigen Sie die Rollen **Empfängerrichtlinien** oder **e-Mail-Empfänger** in Exchange Online, die standardmäßig der Rollengruppe **Organisationsverwaltung** und **Empfänger Verwaltungsdienste** zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="2c11f-140">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="2c11f-141">Weitere Informationen zu Rollengruppen in Exchange Online finden Sie unter [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="2c11f-141">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="2c11f-142">Jede Organisation verfügt über eine Standardrichtlinie mit dem Namen OwaMailboxPolicy-Default, aber Sie können benutzerdefinierte Richtlinien erstellen.</span><span class="sxs-lookup"><span data-stu-id="2c11f-142">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="2c11f-143">Benutzerdefinierte Richtlinien werden vor der Standardrichtlinie auf Bereichs Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="2c11f-143">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="2c11f-144">Weitere Informationen zu Outlook im WebPost Fach Richtlinien finden Sie unter [Outlook im webpostfach-Richtlinien in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="2c11f-144">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="2c11f-145">Durch Deaktivieren der Junk-e-Mail-Berichterstellung wird die Möglichkeit, eine Nachricht nicht als Junk oder Junk in Outlook im Internet zu markieren, nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="2c11f-145">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="2c11f-146">Wenn Sie eine Nachricht im Ordner Junk-e-Mail auswählen und auf **nicht Junk** \> -und-Junk klicken, wird die **Nachricht weiterhin in** den Posteingang verschoben.</span><span class="sxs-lookup"><span data-stu-id="2c11f-146">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="2c11f-147">Wenn Sie eine Nachricht in einem anderen e-Mail-Ordner auswählen und auf **Junk** \> - **Junk** klicken, wird die Nachricht weiterhin in den Ordner Junk-e-Mail verschoben.</span><span class="sxs-lookup"><span data-stu-id="2c11f-147">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="2c11f-148">Nicht mehr verfügbar ist die Option, die Nachricht an Microsoft zu melden.</span><span class="sxs-lookup"><span data-stu-id="2c11f-148">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="2c11f-149">Verwenden Exchange Online PowerShell zum Deaktivieren oder Aktivieren von Junk-e-Mail-Berichten in Outlook im Internet</span><span class="sxs-lookup"><span data-stu-id="2c11f-149">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="2c11f-150">Führen Sie den folgenden Befehl aus, um Ihre vorhandenen Outlook im Internet-Postfachrichtlinien und den Status der Junk-e-Mail-Berichterstellung zu finden:</span><span class="sxs-lookup"><span data-stu-id="2c11f-150">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="2c11f-151">Verwenden Sie die folgende Syntax, um die Junk-e-Mail-Berichterstellung in Outlook im Internet zu deaktivieren oder zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="2c11f-151">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="2c11f-152">In diesem Beispiel wird die Junk-e-Mail-Berichterstellung in der Standardrichtlinie deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2c11f-152">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="2c11f-153">In diesem Beispiel wird die Junk-e-Mail-Berichterstellung in der benutzerdefinierten Richtlinie Contoso Managers aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2c11f-153">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="2c11f-154">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) und [Sets-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="2c11f-154">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2c11f-155">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="2c11f-155">How do you know this worked?</span></span>

<span data-ttu-id="2c11f-156">Um zu überprüfen, ob Sie die Junk-e-Mail-Berichterstellung in Outlook im Internet erfolgreich aktiviert oder deaktiviert haben, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2c11f-156">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="2c11f-157">Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, und überprüfen Sie den Wert der **ReportJunkEmailEnabled** -Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="2c11f-157">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="2c11f-158">Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Internet, wählen Sie eine Nachricht im Posteingang aus, klicken Sie auf **Junk** \> - **e** -Mail, und überprüfen Sie, ob die Aufforderung zum Melden der Nachricht an Microsoft angezeigt wird oder nicht.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2c11f-158">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="2c11f-159">Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Internet, wählen Sie eine Nachricht im Ordner Junk-e-Mail aus, klicken Sie auf **Junk** \> - **Junk** , und überprüfen Sie, ob die Aufforderung zum Melden der Nachricht an Microsoft angezeigt wird oder nicht.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2c11f-159">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="2c11f-160"><sup>\*</sup>Benutzer können die Eingabeaufforderung ausblenden, um die Nachricht zu melden, während Sie die Nachricht weiterhin meldet.</span><span class="sxs-lookup"><span data-stu-id="2c11f-160"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="2c11f-161">So überprüfen Sie diese Einstellung in Outlook im Internet:</span><span class="sxs-lookup"><span data-stu-id="2c11f-161">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="2c11f-162">Klicken Sie auf **Einstellungen** ![Outlook im Webeinstellungen](../../media/owa-settings-icon.png) \> -Symbol **alle Outlook-Einstellungen** \> **Junk-e-Mail**anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2c11f-162">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="2c11f-163">Überprüfen Sie im Abschnitt **Berichterstellung** den Wert: **Fragen Sie mich vor dem Senden eines Berichts**.</span><span class="sxs-lookup"><span data-stu-id="2c11f-163">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook im Interneteinstellungen für Junk-e-Mail-Berichte](../../media/owa-junk-email-reporting-options.png)

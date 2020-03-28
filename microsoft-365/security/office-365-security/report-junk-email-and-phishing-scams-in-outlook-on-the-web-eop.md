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
description: Office 365 Benutzer mit Exchange Online Postfächern können Outlook im Internet (Outlook Web App) verwenden, um Spam-, nicht-Spam-und Phishing-Nachrichten zur Analyse an Microsoft zu übermitteln.
ms.openlocfilehash: c6aba9a701b23be4bbbe508825a55c6438461928
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033684"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a><span data-ttu-id="94dac-103">Melden von Junk-und Phishing-e-Mails in Outlook im Internet in Office 365</span><span class="sxs-lookup"><span data-stu-id="94dac-103">Report junk and phishing email in Outlook on the web in Office 365</span></span>

<span data-ttu-id="94dac-104">Wenn Sie ein Office 365er Kunde mit Exchange Online Postfächern sind, können Sie die integrierten Berichtsoptionen in Outlook im Internet (früher bekannt als Outlook Web App) verwenden, um falsch positive Ergebnisse (gute e-Mail-Nachrichten als Spam gekennzeichnet), falsche Negative (ungültige e-Mail zulässig) und Phishing-Nachrichten an Exchange Online Schutz (EoP).</span><span class="sxs-lookup"><span data-stu-id="94dac-104">If you're an Office 365 customer with Exchange Online mailboxes, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="94dac-105">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="94dac-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="94dac-106">Wenn Sie ein Administrator in einer Office 365 Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungen-Portal im Office 365 Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="94dac-106">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="94dac-107">Weitere Informationen finden Sie unter [Verwenden der Administrator Übermittlung zum Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="94dac-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="94dac-108">Administratoren können Benutzern das Melden von Nachrichten an Microsoft in Outlook im Internet deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="94dac-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="94dac-109">Ausführliche Informationen finden Sie im Abschnitt [deaktivieren oder Aktivieren von Junk-e-Mail-Berichten in Outlook im Internet](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="94dac-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="94dac-110">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Report Messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="94dac-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="94dac-111">Melden von Spam-und Phishing-Nachrichten in Outlook im Internet</span><span class="sxs-lookup"><span data-stu-id="94dac-111">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="94dac-112">Verwenden Sie für Nachrichten im Posteingang oder in einem anderen e-Mail-Ordner außer Junk-e-Mails eine der folgenden Methoden, um Spam-und Phishing-Nachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="94dac-112">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="94dac-113">Wählen Sie die Nachricht aus, klicken Sie auf der Symbolleiste auf **Junk** , und wählen Sie dann **Junk** oder **Phishing**aus.</span><span class="sxs-lookup"><span data-stu-id="94dac-113">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Melden von Junk-oder Phishing-e-Mails über das Menüband](../../media/owa-report-junk.png)

   - <span data-ttu-id="94dac-115">Wählen Sie eine oder mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **als Junk markieren**aus.</span><span class="sxs-lookup"><span data-stu-id="94dac-115">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="94dac-116">Klicken Sie im angezeigten Dialogfeld auf **Bericht**.</span><span class="sxs-lookup"><span data-stu-id="94dac-116">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="94dac-117">Wenn Sie Ihre Meinung ändern, klicken Sie auf **nicht melden**.</span><span class="sxs-lookup"><span data-stu-id="94dac-117">If you change your mind, click **Don't Report**.</span></span>

   ![Dialogfeld "Bericht als Junk"](../../media/owa-report-as-junk-dialog.png)

   ![Dialogfeld "als Phishing melden"](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="94dac-120">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="94dac-120">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="94dac-121">Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="94dac-121">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="94dac-122">Melden von nicht-Spam-und Phishing-Nachrichten aus dem Junk-e-Mail-Ordner in Outlook im Internet</span><span class="sxs-lookup"><span data-stu-id="94dac-122">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="94dac-123">Verwenden Sie im Junk-e-Mail-Ordner eine der folgenden Methoden, um Spam-falsch positive Ergebnisse oder Phishing-Nachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="94dac-123">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="94dac-124">Wählen Sie die Nachricht aus, klicken Sie auf der Symbolleiste auf **kein Junk-e** -Mail, und wählen Sie dann **nicht Junk** -oder **Phishing**aus.</span><span class="sxs-lookup"><span data-stu-id="94dac-124">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Melden von Junk-oder Phishing-e-Mails über das Menüband](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="94dac-126">Wählen Sie eine oder mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **als nicht Junk markieren**aus.</span><span class="sxs-lookup"><span data-stu-id="94dac-126">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="94dac-127">Lesen Sie im daraufhin angezeigten Dialogfeld die Informationen, und klicken Sie auf **Bericht**.</span><span class="sxs-lookup"><span data-stu-id="94dac-127">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="94dac-128">Wenn Sie Ihre Meinung ändern, klicken Sie auf **nicht melden**.</span><span class="sxs-lookup"><span data-stu-id="94dac-128">If you change your mind, click **Don't Report**.</span></span>

   ![Dialogfeld "Bericht als nicht-Junk"](../../media/owa-report-as-not-junk-dialog.png)

   ![Dialogfeld "als Phishing melden"](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="94dac-131">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="94dac-131">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="94dac-132">Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="94dac-132">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="94dac-133">Deaktivieren oder Aktivieren von Junk-e-Mail-Berichten in Outlook im Internet</span><span class="sxs-lookup"><span data-stu-id="94dac-133">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="94dac-134">Standardmäßig können Benutzer Spam-falsch positive Ergebnisse, falsch negative Werte und Phishing-Nachrichten an Microsoft zur Analyse in Outlook im Internet melden.</span><span class="sxs-lookup"><span data-stu-id="94dac-134">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="94dac-135">Administratoren können Outlook im webpostfach-Richtlinien in Exchange Online verwenden, um diese Fähigkeit zu deaktivieren oder zu aktivieren, jedoch nur in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94dac-135">Admins can use Outlook on the web mailbox policies in Exchange Online to disable or enable this ability, but only in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="94dac-136">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="94dac-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="94dac-137">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="94dac-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="94dac-138">Insbesondere benötigen Sie die Rollen **Empfängerrichtlinien** oder **e-Mail-Empfänger** in Exchange Online, die standardmäßig der Rollengruppe **Organisationsverwaltung** und **Empfänger Verwaltungsdienste** zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="94dac-138">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="94dac-139">Weitere Informationen zu Rollengruppen in Exchange Online finden Sie unter [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="94dac-139">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="94dac-140">Jede Organisation verfügt über eine Standardrichtlinie mit dem Namen OwaMailboxPolicy-Default, aber Sie können benutzerdefinierte Richtlinien erstellen.</span><span class="sxs-lookup"><span data-stu-id="94dac-140">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="94dac-141">Benutzerdefinierte Richtlinien werden vor der Standardrichtlinie auf Bereichs Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="94dac-141">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="94dac-142">Weitere Informationen zu Outlook im WebPost Fach Richtlinien finden Sie unter [Outlook im webpostfach-Richtlinien in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="94dac-142">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

1. <span data-ttu-id="94dac-143">Führen Sie den folgenden Befehl aus, um Ihre vorhandenen Outlook im Internet-Postfachrichtlinien und den Status der Junk-e-Mail-Berichterstellung zu finden:</span><span class="sxs-lookup"><span data-stu-id="94dac-143">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="94dac-144">Verwenden Sie die folgende Syntax, um die Junk-e-Mail-Berichterstellung in Outlook im Internet zu deaktivieren oder zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="94dac-144">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="94dac-145">In diesem Beispiel wird die Junk-e-Mail-Berichterstellung in der Standardrichtlinie deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="94dac-145">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="94dac-146">In diesem Beispiel wurde die Junk-e-Mail-Berichterstellung in der benutzerdefinierten Richtlinie Contoso Managers aktiviert.</span><span class="sxs-lookup"><span data-stu-id="94dac-146">This example enabled junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="94dac-147">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) und [Sets-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="94dac-147">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="94dac-148">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="94dac-148">How do you know this worked?</span></span>

<span data-ttu-id="94dac-149">Um zu überprüfen, ob Sie die Junk-e-Mail-Berichterstellung in Outlook im Internet erfolgreich aktiviert oder deaktiviert haben, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="94dac-149">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="94dac-150">Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, und überprüfen Sie den Wert der **ReportJunkEmailEnabled** -Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="94dac-150">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="94dac-151">Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Internet, und überprüfen Sie die Optionen zum Melden von Junk-e-Mails, nicht für Junk-e-Mails und Phishing-Nachrichten, die verfügbar sind oder nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="94dac-151">Open an affected user's mailbox in Outlook on the web, and verify the options to report junk, not junk, and phishing messages are available or not available.</span></span> <span data-ttu-id="94dac-152">Beachten Sie, dass der Benutzer Nachrichten weiterhin als Junk, Phishing und nicht als Junk kennzeichnen kann, aber der Benutzer kann Sie nicht an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="94dac-152">Note that the user can still mark messages as junk, phishing, and not junk, but the user can't report them to Microsoft.</span></span>

---
title: Installieren und Verwenden des Add-Ins für die Junk-e-Mail-Berichterstellung für Microsoft Outlook
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Hier erfahren Sie, wie Sie das Add-in "Microsoft Junk-e-Mail-Berichterstellung" installieren und verwenden, um Spam, nicht-Spam und Phishing-Nachrichten an Microsoft zu melden.
ms.openlocfilehash: 5c0b802bea89a0f0f62952261bf0d2864842024f
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208827"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="33f34-103">Installieren und Verwenden des Add-Ins für die Junk-e-Mail-Berichterstellung für Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="33f34-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

> [!NOTE]
> <span data-ttu-id="33f34-104">Wenn Sie derzeit das Add-in "Junk-e-Mail-Berichterstellung" nicht verwenden, wird stattdessen das [Add-in "Berichtsnachricht](enable-the-report-message-add-in.md) " empfohlen.</span><span class="sxs-lookup"><span data-stu-id="33f34-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span> <span data-ttu-id="33f34-105">Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="33f34-105">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="33f34-106">Mit dem Add-in "Junk-e-Mail-Berichterstellung" für Microsoft Outlook können Benutzer falsch positive Ergebnisse (gute e-Mail-Nachrichten als Spam gekennzeichnet), falsche Negative (ungültige e-Mail-Nachricht) und Phishing-Nachrichten an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="33f34-106">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="33f34-107">Wenn Ihre Organisation keinen Exchange Online Schutz verwendet (beispielsweise lokale Exchange-oder e-Mail-Dienste, die nicht Exchange Online sind), wirkt sich die Übermittlung des Junk-e-Mail-Berichts nicht auf Ihre Spamfilterung aus.</span><span class="sxs-lookup"><span data-stu-id="33f34-107">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="33f34-108">In diesem Thema wird erläutert, wie Sie das Add-in "Junk-e-Mail-Berichterstellung" installieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="33f34-108">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="33f34-109">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="33f34-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="33f34-110">Informationen zum Installieren des Junk-e-Mail-Berichts-Add-Ins finden Sie im Abschnitt [Installieren des Junk-e-Mail-Berichts-Add-ins](#install-the-junk-email-reporting-add-in) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="33f34-110">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="33f34-111">Das Add-in "Junk-e-Mail-Berichterstellung" funktioniert mit den folgenden Versionen von Outlook:</span><span class="sxs-lookup"><span data-stu-id="33f34-111">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="33f34-112">Outlook 2013 oder höher</span><span class="sxs-lookup"><span data-stu-id="33f34-112">Outlook 2013 or later</span></span>
  - <span data-ttu-id="33f34-113">Outlook im Lieferumfang von Microsoft 365-Apps für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="33f34-113">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="33f34-114">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="33f34-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="33f34-115">Verwenden des Add-Ins "Junk-e-Mail-Berichterstellung" zum Melden von Spam-und Phishing-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="33f34-115">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="33f34-116">Verwenden Sie für Nachrichten im Posteingang oder in einem anderen e-Mail-Ordner außer Junk-e-Mails eine der folgenden Methoden, um Spam-und Phishing-Nachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="33f34-116">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="33f34-117">Wählen Sie die Nachricht aus, oder öffnen Sie die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="33f34-117">Select the message or open the message.</span></span> <span data-ttu-id="33f34-118">Klicken Sie auf der Registerkarte **Start** oder **Nachricht** im Menüband auf **Junk**, und wählen Sie dann **als Junk melden** oder **als Phishing melden**aus.</span><span class="sxs-lookup"><span data-stu-id="33f34-118">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Melden von Junk-oder Phishing-e-Mails über das Menüband](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="33f34-120">Klicken Sie mit der rechten Maustaste auf die Nachricht, wählen Sie **Junk**aus, und wählen Sie dann **als Junk melden** oder **als Phishing melden**aus.</span><span class="sxs-lookup"><span data-stu-id="33f34-120">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Melden von Junk-oder Phishing-e-Mails mit der rechten Maustaste](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="33f34-122">Wählen Sie mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **als Junk melden** oder **als Phishing melden**aus.</span><span class="sxs-lookup"><span data-stu-id="33f34-122">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Melden von mehreren Junk-oder Phishing-e-Mails mit der rechten Maustaste](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="33f34-124">Lesen Sie im daraufhin angezeigten Dialogfeld die Informationen, und klicken Sie auf **Bericht**.</span><span class="sxs-lookup"><span data-stu-id="33f34-124">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="33f34-125">Wenn Sie Ihre Meinung ändern, klicken Sie auf **nicht melden**.</span><span class="sxs-lookup"><span data-stu-id="33f34-125">If you change your mind, click **Don't Report**.</span></span>

   ![Dialogfeld "Bericht als Junk"](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Dialogfeld "als Phishing melden"](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="33f34-p105">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet und in den Ordner "Junk-E-Mail" verschoben. Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="33f34-p105">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="33f34-130">Verwenden des Add-Ins "Junk-e-Mail-Berichterstellung" zum Melden von nicht-Spam-und Phishing-Nachrichten aus dem Junk-e-Mail</span><span class="sxs-lookup"><span data-stu-id="33f34-130">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="33f34-131">Verwenden Sie im Ordner Junk-e-Mail eine der folgenden Methoden, um Spam-falsch positive Ergebnisse oder Phishing-Nachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="33f34-131">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="33f34-132">Wählen Sie die Nachricht aus, oder öffnen Sie die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="33f34-132">Select the message or open the message.</span></span> <span data-ttu-id="33f34-133">Klicken Sie auf der Registerkarte **Start** oder **Nachricht** im Menüband auf **kein Junk-e**-Mail, und wählen Sie dann als nicht-Junk-e- **Mail** melden oder **als Phishing melden**aus.</span><span class="sxs-lookup"><span data-stu-id="33f34-133">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Melden von Junk-und Phishing-e-Mails im Menüband im Ordner "Junk-e-Mail"](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="33f34-135">Klicken Sie mit der rechten Maustaste auf die Nachricht, klicken Sie auf **Junk**, und wählen Sie dann als **nicht-Junk-e-Mail** melden oder **als Phishing melden**aus.</span><span class="sxs-lookup"><span data-stu-id="33f34-135">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Melden von Junk-und Phishing-e-Mails per Rechtsklick im Junk-e-Mail-Ordner](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="33f34-137">Wählen Sie mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann als **nicht-Junk-e-Mail** melden oder **als Phishing melden**aus.</span><span class="sxs-lookup"><span data-stu-id="33f34-137">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Melden Sie sich mit der rechten Maustaste in den Junk-e-Mail-Ordner, um mehrere nicht-Junk-oder Phishing-e-Mails](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="33f34-139">Lesen Sie im daraufhin angezeigten Dialogfeld die Informationen, und klicken Sie auf **Bericht**.</span><span class="sxs-lookup"><span data-stu-id="33f34-139">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="33f34-140">Wenn Sie Ihre Meinung ändern, klicken Sie auf **nicht melden**.</span><span class="sxs-lookup"><span data-stu-id="33f34-140">If you change your mind, click **Don't Report**.</span></span>

   ![Dialogfeld "Bericht als nicht-Junk"](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Dialogfeld "als Phishing melden"](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="33f34-p108">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet und in den Ordner "Junk-E-Mail" verschoben. Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="33f34-p108">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="33f34-145">Installieren des Add-Ins für Junk-e-Mail-Berichte</span><span class="sxs-lookup"><span data-stu-id="33f34-145">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="33f34-146">Sie benötigen Administratorrechte auf dem Computer, auf dem Sie das Add-in installieren.</span><span class="sxs-lookup"><span data-stu-id="33f34-146">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="33f34-147">Wechseln Sie zu, <https://www.microsoft.com/download/details.aspx?id=18275> und laden Sie die entsprechende MSI-Datei für Ihre Office-Version an einen Speicherort, der leicht zu finden ist:</span><span class="sxs-lookup"><span data-stu-id="33f34-147">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="33f34-148">**32-Bit**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="33f34-148">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="33f34-149">**64-Bit**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="33f34-149">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="33f34-150">Für Outlook 2013 oder höher ist die einzige Voraussetzung die Microsoft .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="33f34-150">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="33f34-151">In Windows 10 installieren Sie das .NET Framework 2,0 nicht aus einem Download.</span><span class="sxs-lookup"><span data-stu-id="33f34-151">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="33f34-152">Installieren des Junk-e-Mail-Berichts-Add-Ins mithilfe des Setup-Assistenten</span><span class="sxs-lookup"><span data-stu-id="33f34-152">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="33f34-153">Schließen Sie Outlook auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="33f34-153">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="33f34-154">Überprüfen Sie in Windows 10, ob die .NET Framework 2,0 aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="33f34-154">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="33f34-155">Anweisungen finden Sie unter [Aktivieren der Microsoft .NET Framework 3.5 in der System](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)Steuerung.</span><span class="sxs-lookup"><span data-stu-id="33f34-155">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="33f34-156">Suchen Sie die heruntergeladene MSI-Datei, und doppelklicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="33f34-156">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="33f34-157">Klicken Sie auf der Seite **Willkommen beim Setup des Microsoft-Add-Ins "Junk-E-Mail-Berichtsprogramm"** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33f34-157">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="33f34-158">Lesen Sie den Lizenzvertrag, und klicken Sie auf **Ich stimme den Bedingungen des Lizenzvertrags** zu, wenn Sie den Bedingungen zustimmen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="33f34-158">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="33f34-159">Klicken Sie nach Abschluss des Assistenten auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="33f34-159">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="33f34-160">Starten Sie Outlook.</span><span class="sxs-lookup"><span data-stu-id="33f34-160">Start Outlook.</span></span>

<span data-ttu-id="33f34-161">Suchen Sie auf dem Outlook-Menüband nach der Schaltfläche **Junk** .</span><span class="sxs-lookup"><span data-stu-id="33f34-161">Look for the **Junk** button on your Outlook ribbon.</span></span> <span data-ttu-id="33f34-162">Sie können Microsoft nun Junk-E-Mails melden, indem Sie die entsprechenden E-Mails im Posteingang auswählen und dann auf die Schaltfläche **Junk-E-Mails melden** klicken.</span><span class="sxs-lookup"><span data-stu-id="33f34-162">You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="33f34-p112">Wählen Sie den Pfeil nach unten neben **Junk** aus, um weitere Optionen anzuzeigen, z. B. **Als betrügerischen Phishing-Versuch melden**, wenn Sie Phishing-Scam-E-Mails an Microsoft melden möchten. In Ihrem Junk-E-Mailordner können Sie auch **Keine Junk-E-Mail** auswählen, wenn eine E-Mail-Nachricht fälschlicherweise als Junk-E-Mail gekennzeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="33f34-p112">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="33f34-165">Installieren des Add-Ins „Junk-E-Mail-Berichtsprogramm“ im unbeaufsichtigten Modus</span><span class="sxs-lookup"><span data-stu-id="33f34-165">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="33f34-166">Schließen Sie Outlook auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="33f34-166">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="33f34-167">Installieren Sie in Windows 10 die .NET Framework 2,0, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="33f34-167">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="33f34-168">Wenn Sie das Add-in ohne Benutzerinteraktion installieren möchten, öffnen Sie eine Eingabeaufforderung, und verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="33f34-168">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="33f34-169">`MaxMessageSelection`Gibt die maximale Anzahl von Nachrichten an, die Sie für eine einzelne Übermittlung auswählen können.</span><span class="sxs-lookup"><span data-stu-id="33f34-169">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="33f34-170">Gültige Werte sind 1 bis 50.</span><span class="sxs-lookup"><span data-stu-id="33f34-170">Valid values are from 1 to 50.</span></span> <span data-ttu-id="33f34-171">Der Standardwert ist 15.</span><span class="sxs-lookup"><span data-stu-id="33f34-171">The default value is 15.</span></span>

   - <span data-ttu-id="33f34-172">`BccEmailAddress`Gibt zusätzliche Bcc-Empfänger an, die eine Kopie aller Übermittlungen von Benutzern erhalten sollen.</span><span class="sxs-lookup"><span data-stu-id="33f34-172">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="33f34-173">Der Standardwert ist leer (keine zusätzlichen Bcc-Empfänger).</span><span class="sxs-lookup"><span data-stu-id="33f34-173">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="33f34-174">In diesem Beispiel wird die 64-Bit-Version des Add-Ins aus dem angegebenen Pfad mit den Standardeinstellungen installiert.</span><span class="sxs-lookup"><span data-stu-id="33f34-174">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="33f34-175">In diesem Beispiel wird die 32-Bit-Version des Add-Ins aus dem angegebenen Pfad mit den folgenden zusätzlichen Einstellungen installiert:</span><span class="sxs-lookup"><span data-stu-id="33f34-175">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="33f34-176">In einer einzigen Übermittlung können bis zu 20 Nachrichten ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="33f34-176">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="33f34-177">junkreports@contoso.com und hollyd@treyresearch.net erhalten Bcc-Kopien aller Übermittlungen.</span><span class="sxs-lookup"><span data-stu-id="33f34-177">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="33f34-178">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="33f34-178">How do you know this worked?</span></span>

<span data-ttu-id="33f34-179">Führen Sie die folgenden Schritte in Outlook aus, um zu überprüfen, ob Sie das Add-in "Junk-e-Mail-Berichterstellung" erfolgreich installiert haben:</span><span class="sxs-lookup"><span data-stu-id="33f34-179">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="33f34-180">Wählen Sie die Nachricht aus, oder öffnen Sie die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="33f34-180">Select the message or open the message.</span></span> <span data-ttu-id="33f34-181">Klicken Sie auf der Registerkarte **Start** oder **Nachricht** im Menüband auf **Junk**, und vergewissern Sie sich, dass die folgenden Optionen verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="33f34-181">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="33f34-182">**Als Junk melden**</span><span class="sxs-lookup"><span data-stu-id="33f34-182">**Report as Junk**</span></span>
  - <span data-ttu-id="33f34-183">**Als Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="33f34-183">**Report as Phishing**</span></span>
  - <span data-ttu-id="33f34-184">**Optionen für Junk-Berichterstellung**</span><span class="sxs-lookup"><span data-stu-id="33f34-184">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="33f34-185">**Junk Online-Hilfe melden**</span><span class="sxs-lookup"><span data-stu-id="33f34-185">**Report Junk Online Help**</span></span>

  ![Melden von Junk-oder Phishing-e-Mails über das Menüband](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="33f34-187">Klicken Sie mit der rechten Maustaste auf die Nachricht, wählen Sie **Junk**aus, und stellen Sie sicher, dass die folgenden Optionen verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="33f34-187">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="33f34-188">**Als Junk melden**</span><span class="sxs-lookup"><span data-stu-id="33f34-188">**Report as Junk**</span></span>
  - <span data-ttu-id="33f34-189">**Als Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="33f34-189">**Report as Phishing**</span></span>
  - <span data-ttu-id="33f34-190">**Optionen für Junk-Berichterstellung**</span><span class="sxs-lookup"><span data-stu-id="33f34-190">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="33f34-191">**Junk Online-Hilfe melden**</span><span class="sxs-lookup"><span data-stu-id="33f34-191">**Report Junk Online Help**</span></span>

  ![Melden von Junk-oder Phishing-e-Mails mit der rechten Maustaste](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="33f34-193">Wählen Sie mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und stellen Sie sicher, dass die folgenden Optionen verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="33f34-193">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="33f34-194">**Als Junk melden**</span><span class="sxs-lookup"><span data-stu-id="33f34-194">**Report as Junk**</span></span>
  - <span data-ttu-id="33f34-195">**Als Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="33f34-195">**Report as Phishing**</span></span>

  ![Melden von mehreren Junk-oder Phishing-e-Mails mit der rechten Maustaste](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="33f34-197">Führen Sie die vorherigen Aktionen im Ordner **Junk-e-Mail** aus, und vergewissern Sie sich, dass die vorherigen **Junk** -Berichterstellungsoptionen jetzt **nicht Junk**sind.</span><span class="sxs-lookup"><span data-stu-id="33f34-197">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Melden von Junk-und Phishing-e-Mails im Menüband im Ordner "Junk-e-Mail"](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Melden von Junk-und Phishing-e-Mails per Rechtsklick im Junk-e-Mail-Ordner](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Melden Sie sich mit der rechten Maustaste in den Junk-e-Mail-Ordner, um mehrere nicht-Junk-oder Phishing-e-Mails](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="33f34-201">Deinstallieren des Add-Ins "Junk-E-Mail-Berichtsprogramm"</span><span class="sxs-lookup"><span data-stu-id="33f34-201">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="33f34-202">Nachdem Sie Outlook geschlossen haben, verwenden Sie eines der folgenden Verfahren, um das Add-in "Junk-e-Mail-Berichterstellung" zu deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="33f34-202">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="33f34-203">**System**Steuerung: Drücken Sie die Windows-Taste + R. Geben Sie im daraufhin geöffneten Dialogfeld **Ausführen** die EINGABETASTE ein, `control appwiz.cpl` und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="33f34-203">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="33f34-204">Suchen und wählen Sie **Microsoft Junk-e-Mail-Berichts-Add-in** in der Liste aus, und klicken Sie dann auf **deinstallieren**.</span><span class="sxs-lookup"><span data-stu-id="33f34-204">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="33f34-205">**Windows Installer-Paket**: Suchen oder laden Sie die entsprechende MSI-Datei, und doppelklicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="33f34-205">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="33f34-206">**32-Bit**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="33f34-206">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="33f34-207">**64-Bit**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="33f34-207">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="33f34-208">Wählen Sie im daraufhin angezeigten Dialogfeld **Microsoft Junk-e-Mail-Berichts-Add-in für Outlook entfernen** aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="33f34-208">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="33f34-209">**Automatischer Modus**: Suchen oder Herunterladen der entsprechenden MSI-Datei.</span><span class="sxs-lookup"><span data-stu-id="33f34-209">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="33f34-210">Ersetzen Sie in einem Eingabeaufforderungsfenster \< PathToFile \> durch den Speicherort der MSI-Datei, und führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="33f34-210">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="33f34-211">**32-Bit**:</span><span class="sxs-lookup"><span data-stu-id="33f34-211">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="33f34-212">**64-Bit**:</span><span class="sxs-lookup"><span data-stu-id="33f34-212">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="33f34-213">Wenn Sie Outlook nach der Deinstallation öffnen, sollten die Optionen Junk, not Junk und Phishing-Berichterstellung nicht mehr vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="33f34-213">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="33f34-214">Problembehandlung beim Add-in "Junk-e-Mail-Berichte"</span><span class="sxs-lookup"><span data-stu-id="33f34-214">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="33f34-215">Gelegentlich können Probleme mit Outlook auftreten, nachdem Sie das Add-in "Junk-e-Mail-Berichterstellung" hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="33f34-215">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="33f34-216">In diesem Abschnitt werden Probleme beschrieben, die auftreten können, sowie Tipps zum Beheben dieser Probleme.</span><span class="sxs-lookup"><span data-stu-id="33f34-216">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="33f34-217">Problembehandlung für Benutzer</span><span class="sxs-lookup"><span data-stu-id="33f34-217">Troubleshooting for users</span></span>

<span data-ttu-id="33f34-218">Eines oder mehrere der folgenden Probleme können auftreten:</span><span class="sxs-lookup"><span data-stu-id="33f34-218">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="33f34-219">Das Programm reagiert nicht, wenn Sie auf **Junk-E-Mail melden** klicken</span><span class="sxs-lookup"><span data-stu-id="33f34-219">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="33f34-220">Outlook reagiert nicht mehr, wenn Sie eine E-Mail auswählen</span><span class="sxs-lookup"><span data-stu-id="33f34-220">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="33f34-221">Gemeldete Junk-E-Mails können nicht übermittelt werden, und es wird eine Unzustellbarkeitsnachricht angezeigt</span><span class="sxs-lookup"><span data-stu-id="33f34-221">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="33f34-222">Um dieses Problem zu beheben, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="33f34-222">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="33f34-223">Schließen Sie Outlook, und starten Sie es neu.</span><span class="sxs-lookup"><span data-stu-id="33f34-223">Close and restart Outlook.</span></span>
2. <span data-ttu-id="33f34-224">Erstellen und senden Sie eine Testnachricht, und vergewissern Sie sich, dass der Empfänger die Nachricht erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="33f34-224">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="33f34-225">Wenn das Problem fortbesteht, wenden Sie sich an Ihren Administrator.</span><span class="sxs-lookup"><span data-stu-id="33f34-225">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="33f34-226">Weitere Methoden, die Sie zum Übermitteln von Nachrichten an Microsoft verwenden können, finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="33f34-226">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="33f34-227">Problembehandlung für Administratoren</span><span class="sxs-lookup"><span data-stu-id="33f34-227">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="33f34-228">Problem: Es wird ständig eine Fehlermeldung angezeigt, in der die Benutzer aufgefordert werden, Ihren System Administrator zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="33f34-228">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="33f34-229">Überprüfen oder Festlegen des `LoggingLevel` Registrierungsschlüssels auf den Wert "Verbose":</span><span class="sxs-lookup"><span data-stu-id="33f34-229">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="33f34-230">**32-Bit-Outlook unter 32-Bit-Windows**:</span><span class="sxs-lookup"><span data-stu-id="33f34-230">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="33f34-231">**32-Bit-Outlook unter 64-Bit-Windows**:</span><span class="sxs-lookup"><span data-stu-id="33f34-231">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="33f34-232">**64-Bit-Outlook**:</span><span class="sxs-lookup"><span data-stu-id="33f34-232">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="33f34-233">Starten Sie Outlook neu, und fordern Sie die Benutzer auf, zurückgemeldet zu werden, wenn die Fehlermeldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="33f34-233">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="33f34-234">Erfassen Sie die Protokollinformationen am folgenden Speicherort:</span><span class="sxs-lookup"><span data-stu-id="33f34-234">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="33f34-235">Kontaktieren Sie den technischen Support für Exchange Online Protection, und übergeben Sie den Mitarbeitern diese Protokollinformationen.</span><span class="sxs-lookup"><span data-stu-id="33f34-235">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="33f34-236">Problem: Benutzer haben ausgewählt, beim Melden von Nachrichten keine Bestätigungsaufforderung zu erhalten, und möchten nun die Eingabeaufforderung zurück</span><span class="sxs-lookup"><span data-stu-id="33f34-236">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="33f34-237">Erstellen Sie den `ConfirmReportJunk` Registrierungsschlüssel mit dem Wert "true":</span><span class="sxs-lookup"><span data-stu-id="33f34-237">Create the `ConfirmReportJunk`registry key wih the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="33f34-238">Starten Sie Outlook neu.</span><span class="sxs-lookup"><span data-stu-id="33f34-238">Restart Outlook.</span></span>

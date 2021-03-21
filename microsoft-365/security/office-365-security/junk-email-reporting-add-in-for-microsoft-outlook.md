---
title: Installieren und Verwenden des Junk-E-Mail-Berichts-Add-Ins für Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie das Microsoft Junk Email Reporting-Add-In installieren und verwenden, um Spam-, Nichtspam- und Phishingnachrichten an Microsoft zu melden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a6386307b24d879cac9dd2390d9080cd2cb8b5b5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920360"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="adc95-103">Installieren und Verwenden des Junk-E-Mail-Berichts-Add-Ins für Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="adc95-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="adc95-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="adc95-104">**Applies to**</span></span>
- [<span data-ttu-id="adc95-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="adc95-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="adc95-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="adc95-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="adc95-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="adc95-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> <span data-ttu-id="adc95-108">Wenn Sie das Junk-E-Mail-Berichterstellungs-Add-In derzeit nicht verwenden, wird stattdessen das [Add-In](enable-the-report-message-add-in.md) Nachricht melden oder das [Phishing-Add-In](enable-the-report-phish-add-in.md) melden empfohlen.</span><span class="sxs-lookup"><span data-stu-id="adc95-108">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) instead.</span></span> <span data-ttu-id="adc95-109">Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="adc95-109">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="adc95-110">Das Junk-E-Mail-Berichterstellungs-Add-In für Microsoft Outlook ermöglicht Es Benutzern, falsch positive Nachrichten (gute E-Mails, die als Spam gekennzeichnet sind), falsch negative Nachrichten (ungültige E-Mails zulässig) und Phishingnachrichten an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="adc95-110">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="adc95-111">Wenn Ihre Organisation Exchange Online Protection nicht verwendet (z. B. lokale Exchange- oder E-Mail-Dienste, die keine Exchange Online sind), wirkt sich ihre Übermittlung von Junk-E-Mail-Berichten nicht auf Ihre Spamfilterung aus.</span><span class="sxs-lookup"><span data-stu-id="adc95-111">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="adc95-112">In diesem Thema wird erläutert, wie Sie das Junk-E-Mail-Berichterstellungs-Add-In installieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="adc95-112">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="adc95-113">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="adc95-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="adc95-114">Informationen zum Installieren des Junk-E-Mail-Berichts-Add-Ins finden Sie im Abschnitt Installieren des [Junk-E-Mail-Berichts-Add-Ins](#install-the-junk-email-reporting-add-in) weiter später in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="adc95-114">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this article.</span></span>

- <span data-ttu-id="adc95-115">Das Junk-E-Mail-Berichterstellungs-Add-In funktioniert mit den folgenden Versionen von Outlook:</span><span class="sxs-lookup"><span data-stu-id="adc95-115">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="adc95-116">Outlook 2013 oder höher</span><span class="sxs-lookup"><span data-stu-id="adc95-116">Outlook 2013 or later</span></span>
  - <span data-ttu-id="adc95-117">Outlook in Microsoft 365 Apps for Enterprise enthalten</span><span class="sxs-lookup"><span data-stu-id="adc95-117">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="adc95-118">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="adc95-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="adc95-119">Verwenden des Junk-E-Mail-Berichts-Add-Ins zum Melden von Spam- und Phishingnachrichten</span><span class="sxs-lookup"><span data-stu-id="adc95-119">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="adc95-120">Verwenden Sie für Nachrichten im Posteingang oder in einem anderen E-Mail-Ordner mit Ausnahme von Junk-E-Mails eine der folgenden Methoden, um Spam- und Phishingnachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="adc95-120">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="adc95-121">Wählen Sie die Nachricht aus, oder öffnen Sie die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="adc95-121">Select the message or open the message.</span></span> <span data-ttu-id="adc95-122">Klicken Sie  **auf der Registerkarte** Start oder Nachricht im Menüband auf **Junk,** und wählen Sie **dann Als** Junk melden oder Als Phishing **melden aus.**</span><span class="sxs-lookup"><span data-stu-id="adc95-122">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Melden von Junk- oder Phishing-E-Mails über das Menüband](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="adc95-124">Klicken Sie mit der rechten Maustaste auf die Nachricht, wählen Sie **Junk** aus, und wählen Sie **dann Als** Junk melden oder Als Phishing **melden aus.**</span><span class="sxs-lookup"><span data-stu-id="adc95-124">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Melden von Junk- oder Phishing-E-Mails mit der rechten Maustaste](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="adc95-126">Wählen Sie mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie **dann Als Junk melden** oder Als Phishing melden **aus.**</span><span class="sxs-lookup"><span data-stu-id="adc95-126">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Melden mehrerer Junk- oder Phishing-E-Mail-Nachrichten mit der rechten Maustaste](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="adc95-128">Lesen Sie im angezeigten Dialogfeld die Informationen, und klicken Sie auf **Bericht**.</span><span class="sxs-lookup"><span data-stu-id="adc95-128">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="adc95-129">Wenn Sie Ihre Meinung ändern, klicken Sie auf **Nicht melden**.</span><span class="sxs-lookup"><span data-stu-id="adc95-129">If you change your mind, click **Don't Report**.</span></span>

   ![Melden als Junkdialogfeld](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Melden als Phishingdialogfeld](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="adc95-132">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet und:</span><span class="sxs-lookup"><span data-stu-id="adc95-132">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="adc95-133">In den Junk-E-Mail-Ordner verschoben, wenn er als Spam gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="adc95-133">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="adc95-134">Gelöscht, wenn es als Phishing gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="adc95-134">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="adc95-135">Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="adc95-135">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="adc95-136">Verwenden des Junk-E-Mail-Berichts-Add-Ins zum Melden von Nichtspam- und Phishingnachrichten aus dem Junk-E-Mail-Ordner</span><span class="sxs-lookup"><span data-stu-id="adc95-136">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="adc95-137">Verwenden Sie im Ordner Junk-E-Mail eine der folgenden Methoden, um Spam falsch positive Nachrichten oder Phishingnachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="adc95-137">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="adc95-138">Wählen Sie die Nachricht aus, oder öffnen Sie die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="adc95-138">Select the message or open the message.</span></span> <span data-ttu-id="adc95-139">Klicken Sie  **auf der** Registerkarte Start oder Nachricht im Menüband auf **Nicht** Junk, und wählen Sie dann Melden als Nicht **Junk** oder Als Phishing **melden aus.**</span><span class="sxs-lookup"><span data-stu-id="adc95-139">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Melden sie keine Junk- oder Phishing-E-Mails vom Menüband im Ordner Junk-E-Mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="adc95-141">Klicken Sie mit der rechten Maustaste auf die Nachricht, klicken Sie auf **Junk**, und wählen Sie **dann Als** Nicht Junk melden oder Als Phishing **melden aus.**</span><span class="sxs-lookup"><span data-stu-id="adc95-141">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Melden sie keine Junk- oder Phishing-E-Mails von der rechten Maustaste im Ordner Junk-E-Mail](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="adc95-143">Wählen Sie mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann Melden als **Nicht Junk oder** Als Phishing melden **aus.**</span><span class="sxs-lookup"><span data-stu-id="adc95-143">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Melden mehrerer Junk- oder Phishing-E-Mail-Nachrichten mit der rechten Maustaste im Ordner Junk-E-Mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="adc95-145">Lesen Sie im angezeigten Dialogfeld die Informationen, und klicken Sie auf **Bericht**.</span><span class="sxs-lookup"><span data-stu-id="adc95-145">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="adc95-146">Wenn Sie Ihre Meinung ändern, klicken Sie auf **Nicht melden**.</span><span class="sxs-lookup"><span data-stu-id="adc95-146">If you change your mind, click **Don't Report**.</span></span>

   ![Melden als Nicht-Junk-Dialogfeld](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Melden als Phishingdialogfeld](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="adc95-149">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet und:</span><span class="sxs-lookup"><span data-stu-id="adc95-149">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="adc95-150">In den Junk-E-Mail-Ordner verschoben, wenn er als Spam gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="adc95-150">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="adc95-151">Gelöscht, wenn es als Phishing gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="adc95-151">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="adc95-152">Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="adc95-152">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="adc95-153">Installieren des Junk-E-Mail-Berichts-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="adc95-153">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="adc95-154">Sie benötigen Administratorrechte auf dem Computer, auf dem Sie das Add-In installieren.</span><span class="sxs-lookup"><span data-stu-id="adc95-154">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="adc95-155">Wechseln Sie zu und laden Sie die entsprechende MSI-Datei für Ihre Office-Version an einen Speicherort herunter, der <https://www.microsoft.com/download/details.aspx?id=18275> leicht zu finden ist:</span><span class="sxs-lookup"><span data-stu-id="adc95-155">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="adc95-156">**32-Bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="adc95-156">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="adc95-157">**64-Bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="adc95-157">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="adc95-158">Für Outlook 2013 oder höher ist die einzige Voraussetzung das Microsoft .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="adc95-158">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="adc95-159">In Windows 10 installieren Sie die .NET Framework 2.0 nicht aus einem Download.</span><span class="sxs-lookup"><span data-stu-id="adc95-159">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="adc95-160">Installieren des Junk-E-Mail-Berichts-Add-Ins mithilfe des Setup-Assistenten</span><span class="sxs-lookup"><span data-stu-id="adc95-160">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="adc95-161">Schließen Sie Outlook auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="adc95-161">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="adc95-162">Überprüfen Sie in Windows 10, ob .NET Framework 2.0 aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="adc95-162">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="adc95-163">Anweisungen finden Sie unter [Enable the .NET Framework 3.5 in Control Panel](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span><span class="sxs-lookup"><span data-stu-id="adc95-163">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="adc95-164">Suchen Sie die heruntergeladene MSI-Datei, und doppelklicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="adc95-164">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="adc95-165">Klicken Sie auf der Seite **Willkommen beim Setup des Microsoft-Add-Ins "Junk-E-Mail-Berichtsprogramm"** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="adc95-165">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="adc95-166">Überprüfen Sie den Lizenzvertrag, klicken Sie auf Ich stimme den **Bedingungen im** Lizenzvertrag zu, wenn Sie den Bedingungen zustimmen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="adc95-166">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="adc95-167">Klicken Sie nach Abschluss des Assistenten auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="adc95-167">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="adc95-168">Starten Sie Outlook.</span><span class="sxs-lookup"><span data-stu-id="adc95-168">Start Outlook.</span></span>

<span data-ttu-id="adc95-169">Suchen Sie im **Outlook-Menüband** nach der Schaltfläche Junk.</span><span class="sxs-lookup"><span data-stu-id="adc95-169">Look for the **Junk** button on your Outlook ribbon.</span></span> <span data-ttu-id="adc95-170">Sie können Microsoft nun Junk-E-Mails melden, indem Sie die entsprechenden E-Mails im Posteingang auswählen und dann auf die Schaltfläche **Junk-E-Mails melden** klicken.</span><span class="sxs-lookup"><span data-stu-id="adc95-170">You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="adc95-p110">Wählen Sie den Pfeil nach unten neben **Junk** aus, um weitere Optionen anzuzeigen, z. B. **Als betrügerischen Phishing-Versuch melden**, wenn Sie Phishing-Scam-E-Mails an Microsoft melden möchten. In Ihrem Junk-E-Mailordner können Sie auch **Keine Junk-E-Mail** auswählen, wenn eine E-Mail-Nachricht fälschlicherweise als Junk-E-Mail gekennzeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="adc95-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="adc95-173">Installieren des Add-Ins „Junk-E-Mail-Berichtsprogramm“ im unbeaufsichtigten Modus</span><span class="sxs-lookup"><span data-stu-id="adc95-173">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="adc95-174">Schließen Sie Outlook auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="adc95-174">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="adc95-175">Installieren Sie in Windows 10 die .NET Framework 2.0, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="adc95-175">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="adc95-176">Öffnen Sie eine Eingabeaufforderung, und verwenden Sie die folgende Syntax, um das #A0 ohne Benutzerinteraktion zu installieren:</span><span class="sxs-lookup"><span data-stu-id="adc95-176">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="adc95-177">`MaxMessageSelection` gibt die maximale Anzahl von Nachrichten an, die Sie für eine einzelne Übermittlung auswählen können.</span><span class="sxs-lookup"><span data-stu-id="adc95-177">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="adc95-178">Gültige Werte liegen zwischen 1 und 50.</span><span class="sxs-lookup"><span data-stu-id="adc95-178">Valid values are from 1 to 50.</span></span> <span data-ttu-id="adc95-179">Der Standardwert ist 15.</span><span class="sxs-lookup"><span data-stu-id="adc95-179">The default value is 15.</span></span>

   - <span data-ttu-id="adc95-180">`BccEmailAddress` gibt zusätzliche Bcc-Empfänger an, die eine Kopie aller Benutzerübermittlungen erhalten.</span><span class="sxs-lookup"><span data-stu-id="adc95-180">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="adc95-181">Der Standardwert ist leer (keine zusätzlichen Bcc-Empfänger).</span><span class="sxs-lookup"><span data-stu-id="adc95-181">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="adc95-182">In diesem Beispiel wird die 64-Bit-Version des Add-Ins aus dem angegebenen Pfad mit den Standardeinstellungen installiert.</span><span class="sxs-lookup"><span data-stu-id="adc95-182">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="adc95-183">In diesem Beispiel wird die 32-Bit-Version des Add-Ins über den angegebenen Pfad mit den folgenden zusätzlichen Einstellungen installiert:</span><span class="sxs-lookup"><span data-stu-id="adc95-183">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="adc95-184">Bis zu 20 Nachrichten können in einer einzigen Übermittlung ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="adc95-184">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="adc95-185">junkreports@contoso.com und hollyd@treyresearch.net erhalten Bcc-Kopien aller Übermittlungen.</span><span class="sxs-lookup"><span data-stu-id="adc95-185">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="adc95-186">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="adc95-186">How do you know this worked?</span></span>

<span data-ttu-id="adc95-187">Gehen Sie wie folgt vor, um zu überprüfen, ob Sie das Junk-E-Mail-Berichterstellungs-Add-In erfolgreich installiert haben:</span><span class="sxs-lookup"><span data-stu-id="adc95-187">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="adc95-188">Wählen Sie die Nachricht aus, oder öffnen Sie die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="adc95-188">Select the message or open the message.</span></span> <span data-ttu-id="adc95-189">Klicken Sie **auf der** Registerkarte **Start** oder Nachricht im Menüband auf **Junk,** und stellen Sie sicher, dass die folgenden Optionen verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="adc95-189">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="adc95-190">**Melden als Junk**</span><span class="sxs-lookup"><span data-stu-id="adc95-190">**Report as Junk**</span></span>
  - <span data-ttu-id="adc95-191">**Melden als Phishing**</span><span class="sxs-lookup"><span data-stu-id="adc95-191">**Report as Phishing**</span></span>
  - <span data-ttu-id="adc95-192">**Junkberichtsoptionen**</span><span class="sxs-lookup"><span data-stu-id="adc95-192">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="adc95-193">**Junk-Online-Hilfe melden**</span><span class="sxs-lookup"><span data-stu-id="adc95-193">**Report Junk Online Help**</span></span>

  ![Melden von Junk- oder Phishing-E-Mails über das Menüband](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="adc95-195">Klicken Sie mit der rechten Maustaste auf die Nachricht, wählen Sie **Junk** aus, und stellen Sie sicher, dass die folgenden Optionen verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="adc95-195">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="adc95-196">**Melden als Junk**</span><span class="sxs-lookup"><span data-stu-id="adc95-196">**Report as Junk**</span></span>
  - <span data-ttu-id="adc95-197">**Melden als Phishing**</span><span class="sxs-lookup"><span data-stu-id="adc95-197">**Report as Phishing**</span></span>
  - <span data-ttu-id="adc95-198">**Junkberichtsoptionen**</span><span class="sxs-lookup"><span data-stu-id="adc95-198">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="adc95-199">**Junk-Online-Hilfe melden**</span><span class="sxs-lookup"><span data-stu-id="adc95-199">**Report Junk Online Help**</span></span>

  ![Melden von Junk- oder Phishing-E-Mails mit der rechten Maustaste](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="adc95-201">Wählen Sie mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und überprüfen Sie, ob die folgenden Optionen verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="adc95-201">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="adc95-202">**Melden als Junk**</span><span class="sxs-lookup"><span data-stu-id="adc95-202">**Report as Junk**</span></span>
  - <span data-ttu-id="adc95-203">**Melden als Phishing**</span><span class="sxs-lookup"><span data-stu-id="adc95-203">**Report as Phishing**</span></span>

  ![Melden mehrerer Junk- oder Phishing-E-Mail-Nachrichten mit der rechten Maustaste](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="adc95-205">Gehen Sie wie zuvor im Ordner **Junk-E-Mail** vor, und überprüfen Sie, ob die vorherigen **Junkberichtsoptionen** jetzt **Nicht Junk sind.**</span><span class="sxs-lookup"><span data-stu-id="adc95-205">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Melden sie keine Junk- oder Phishing-E-Mails vom Menüband im Ordner Junk-E-Mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Melden sie keine Junk- oder Phishing-E-Mails von der rechten Maustaste im Ordner Junk-E-Mail](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Melden mehrerer Junk- oder Phishing-E-Mail-Nachrichten mit der rechten Maustaste im Ordner Junk-E-Mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="adc95-209">Deinstallieren des Add-Ins "Junk-E-Mail-Berichtsprogramm"</span><span class="sxs-lookup"><span data-stu-id="adc95-209">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="adc95-210">Verwenden Sie nach dem Schließen von Outlook eines der folgenden Verfahren, um das Junk-E-Mail-Berichterstellungs-Add-In zu deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="adc95-210">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="adc95-211">**Systemsteuerung**: Drücken Sie die Windows-TASTE + R. Geben Sie **im** geöffneten Dialogfeld Ausführen die Eingabe `control appwiz.cpl` ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="adc95-211">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="adc95-212">Suchen Sie das **Microsoft Junk-E-Mail-Berichterstellungs-Add-In,** und wählen Sie es in der Liste aus, und klicken Sie dann auf **Deinstallieren.**</span><span class="sxs-lookup"><span data-stu-id="adc95-212">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="adc95-213">**Windows Installer-Paket:** Suchen oder laden Sie die entsprechende MSI-Datei herunter, und doppelklicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="adc95-213">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="adc95-214">**32-Bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="adc95-214">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="adc95-215">**64-Bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="adc95-215">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="adc95-216">Wählen Sie im angezeigten Dialogfeld **Microsoft Junk-E-Mail-Berichterstellungs-Add-In** entfernen für Outlook aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="adc95-216">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="adc95-217">**Silent Mode**: Suchen oder laden Sie die entsprechende MSI-Datei herunter.</span><span class="sxs-lookup"><span data-stu-id="adc95-217">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="adc95-218">Ersetzen Sie in einem Eingabeaufforderungsfenster durch den Speicherort der \<PathToFile\> MSI-Datei, und führen Sie einen der folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="adc95-218">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="adc95-219">**32-Bit:**</span><span class="sxs-lookup"><span data-stu-id="adc95-219">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="adc95-220">**64-Bit:**</span><span class="sxs-lookup"><span data-stu-id="adc95-220">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="adc95-221">Wenn Sie Outlook nach der Deinstallation öffnen, sollten die Junk-, nicht Junk- und Phishingberichtsoptionen weg sein.</span><span class="sxs-lookup"><span data-stu-id="adc95-221">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="adc95-222">Problembehandlung für das Junk-E-Mail-Bericht-Add-In</span><span class="sxs-lookup"><span data-stu-id="adc95-222">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="adc95-223">Gelegentlich können Probleme mit Outlook nach dem Hinzufügen des Junk-E-Mail-Berichts-Add-Ins angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="adc95-223">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="adc95-224">In diesem Abschnitt werden Probleme beschrieben, die auftreten können, sowie Tipps zum Beheben dieser Probleme.</span><span class="sxs-lookup"><span data-stu-id="adc95-224">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="adc95-225">Problembehandlung für Benutzer</span><span class="sxs-lookup"><span data-stu-id="adc95-225">Troubleshooting for users</span></span>

<span data-ttu-id="adc95-226">Es gibt mindestens eines der folgenden Probleme:</span><span class="sxs-lookup"><span data-stu-id="adc95-226">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="adc95-227">Das Programm reagiert nicht, wenn Sie auf **Junk-E-Mail melden** klicken</span><span class="sxs-lookup"><span data-stu-id="adc95-227">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="adc95-228">Outlook reagiert nicht mehr, wenn Sie eine E-Mail auswählen</span><span class="sxs-lookup"><span data-stu-id="adc95-228">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="adc95-229">Gemeldete Junk-E-Mails können nicht übermittelt werden, und es wird eine Unzustellbarkeitsnachricht angezeigt</span><span class="sxs-lookup"><span data-stu-id="adc95-229">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="adc95-230">Gehen Sie wie folgt vor, um dieses Problem zu beheben:</span><span class="sxs-lookup"><span data-stu-id="adc95-230">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="adc95-231">Schließen und starten Sie Outlook neu.</span><span class="sxs-lookup"><span data-stu-id="adc95-231">Close and restart Outlook.</span></span>
2. <span data-ttu-id="adc95-232">Erstellen und senden Sie eine Testnachricht, und vergewissern Sie sich, dass der Empfänger die Nachricht empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="adc95-232">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="adc95-233">Wenn das Problem weiterhin besteht, wenden Sie sich an Ihren Administrator.</span><span class="sxs-lookup"><span data-stu-id="adc95-233">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="adc95-234">Weitere Methoden zum Übermitteln von Nachrichten an Microsoft finden Sie unter Melden von Nachrichten [und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="adc95-234">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="adc95-235">Problembehandlung für Administratoren</span><span class="sxs-lookup"><span data-stu-id="adc95-235">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="adc95-236">Problem: Es wird ständig eine Fehlermeldung angezeigt, in der Benutzer zur Kontaktaufnahme mit ihrem Systemadministrator gefragt werden.</span><span class="sxs-lookup"><span data-stu-id="adc95-236">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="adc95-237">Überprüfen oder festlegen Sie `LoggingLevel` den Registrierungsschlüssel auf den Wert "Verbose":</span><span class="sxs-lookup"><span data-stu-id="adc95-237">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="adc95-238">**32-Bit-Outlook unter 32-Bit-Windows**:</span><span class="sxs-lookup"><span data-stu-id="adc95-238">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="adc95-239">**32-Bit-Outlook unter 64-Bit-Windows**:</span><span class="sxs-lookup"><span data-stu-id="adc95-239">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="adc95-240">**64-Bit-Outlook**:</span><span class="sxs-lookup"><span data-stu-id="adc95-240">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="adc95-241">Starten Sie Outlook neu, und fordern Sie Benutzer auf, sich zu melden, wenn die Fehlermeldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="adc95-241">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="adc95-242">Erfassen Sie die Protokollinformationen am folgenden Speicherort:</span><span class="sxs-lookup"><span data-stu-id="adc95-242">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="adc95-243">Kontaktieren Sie den technischen Support für Exchange Online Protection, und übergeben Sie den Mitarbeitern diese Protokollinformationen.</span><span class="sxs-lookup"><span data-stu-id="adc95-243">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="adc95-244">Problem: Benutzer haben ausgewählt, keine Bestätigungsaufforderung zu erhalten, wenn sie Nachrichten melden, und jetzt möchten sie die Eingabeaufforderung zurück</span><span class="sxs-lookup"><span data-stu-id="adc95-244">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="adc95-245">Erstellen Sie `ConfirmReportJunk` den Registrierungsschlüssel mit dem Wert "True":</span><span class="sxs-lookup"><span data-stu-id="adc95-245">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="adc95-246">Starten Sie Outlook neu.</span><span class="sxs-lookup"><span data-stu-id="adc95-246">Restart Outlook.</span></span>
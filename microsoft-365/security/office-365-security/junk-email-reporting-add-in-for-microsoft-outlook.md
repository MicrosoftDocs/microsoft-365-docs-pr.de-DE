---
title: Installieren und Verwenden des Junk-E-Mail-Berichterstellungs-Add-Ins für Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie das Microsoft-Add-In "Junk-E-Mail-Berichterstellung" installieren und verwenden, um Spam-, Nichtspam- und Phishingnachrichten an Microsoft zu melden.
ms.openlocfilehash: 2b98fb0183cb7164ee90fb6a3a22d949e6edc2bc
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865061"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="9d69e-103">Installieren und Verwenden des Junk-E-Mail-Berichterstellungs-Add-Ins für Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="9d69e-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="9d69e-104">Wenn Sie das Junk-E-Mail-Berichterstellungs-Add-In derzeit nicht verwenden, empfehlen wir stattdessen das [Add-In](enable-the-report-message-add-in.md) "Nachricht melden" oder das ["Phishing-Add-In](enable-the-report-phish-add-in.md) melden".</span><span class="sxs-lookup"><span data-stu-id="9d69e-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) instead.</span></span> <span data-ttu-id="9d69e-105">Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="9d69e-105">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="9d69e-106">Mit dem Junk-E-Mail-Bericht-Add-In für Microsoft Outlook können Benutzer falsch positive Ergebnisse (gute E-Mails als Spam gekennzeichnet), falsch negative Ergebnisse (ungültige E-Mails sind zugelassen) und Phishingnachrichten an Microsoft übermitteln.</span><span class="sxs-lookup"><span data-stu-id="9d69e-106">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="9d69e-107">Wenn Ihre Organisation Exchange Online Protection nicht verwendet (z. B. lokale Exchange- oder andere E-Mail-Dienste als Exchange Online), hat Ihre Übermittlung des Junk-E-Mail-Berichts keine Auswirkungen auf Ihre Spamfilterung.</span><span class="sxs-lookup"><span data-stu-id="9d69e-107">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="9d69e-108">In diesem Thema wird erläutert, wie Sie das Junk-E-Mail-Berichterstellungs-Add-In installieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d69e-108">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9d69e-109">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="9d69e-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9d69e-110">Informationen zum Installieren des Junk-E-Mail-Berichterstellungs-Add-Ins finden Sie im Abschnitt "Installieren des [Junk-E-Mail-Berichterstellungs-Add-Ins"](#install-the-junk-email-reporting-add-in) weiter später in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="9d69e-110">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this article.</span></span>

- <span data-ttu-id="9d69e-111">Das Junk-E-Mail-Bericht-Add-In funktioniert mit den folgenden Versionen von Outlook:</span><span class="sxs-lookup"><span data-stu-id="9d69e-111">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="9d69e-112">Outlook 2013 oder höher</span><span class="sxs-lookup"><span data-stu-id="9d69e-112">Outlook 2013 or later</span></span>
  - <span data-ttu-id="9d69e-113">Outlook im Lieferumfang von Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="9d69e-113">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="9d69e-114">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter ["Melden von Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="9d69e-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="9d69e-115">Verwenden des Junk-E-Mail-Berichterstellungs-Add-Ins zum Melden von Spam- und Phishingnachrichten</span><span class="sxs-lookup"><span data-stu-id="9d69e-115">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="9d69e-116">Verwenden Sie für Nachrichten im Posteingang oder einem anderen E-Mail-Ordner mit Ausnahme von Junk-E-Mails eine der folgenden Methoden, um Spam- und Phishingnachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="9d69e-116">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="9d69e-117">Wählen Sie die Nachricht aus, oder öffnen Sie die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9d69e-117">Select the message or open the message.</span></span> <span data-ttu-id="9d69e-118">Klicken Sie  **auf der Registerkarte "Start"** oder "Nachricht" im Menüband auf **"Junk",** und wählen Sie dann **"Als** Junk melden" oder "Als Phishing **melden" aus.**</span><span class="sxs-lookup"><span data-stu-id="9d69e-118">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Melden von Junk- oder Phishing-E-Mails über das Menüband](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="9d69e-120">Klicken Sie mit der rechten Maustaste auf die Nachricht, wählen **Sie "Junk"** aus, und wählen Sie dann **"Als Junk melden"** oder "Als Phishing **melden" aus.**</span><span class="sxs-lookup"><span data-stu-id="9d69e-120">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Melden von Junk- oder Phishing-E-Mails per Rechtsklick](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="9d69e-122">Wählen Sie mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **"Als Junk melden"** oder "Als Phishing **melden" aus.**</span><span class="sxs-lookup"><span data-stu-id="9d69e-122">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Melden mehrerer Junk- oder Phishing-E-Mail-Nachrichten mit der rechten Maustaste](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="9d69e-124">Lesen Sie im angezeigten Dialogfeld die Informationen, und klicken Sie auf **"Bericht".**</span><span class="sxs-lookup"><span data-stu-id="9d69e-124">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="9d69e-125">Wenn Sie Ihre Meinung ändern, klicken Sie auf **"Nicht melden".**</span><span class="sxs-lookup"><span data-stu-id="9d69e-125">If you change your mind, click **Don't Report**.</span></span>

   ![Dialogfeld "Als Junk melden"](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Melden als Phishingdialogfeld](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="9d69e-128">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet und:</span><span class="sxs-lookup"><span data-stu-id="9d69e-128">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="9d69e-129">In den Junk-E-Mail-Ordner verschoben, wenn er als Spam gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="9d69e-129">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="9d69e-130">Gelöscht, wenn es als Phishing gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="9d69e-130">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="9d69e-131">Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="9d69e-131">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="9d69e-132">Verwenden des Junk-E-Mail-Berichts-Add-Ins zum Melden von Nichtspam- und Phishingnachrichten aus dem Junk-E-Mail-Ordner</span><span class="sxs-lookup"><span data-stu-id="9d69e-132">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="9d69e-133">Verwenden Sie im Junk-E-Mail-Ordner eine der folgenden Methoden, um falsch positive Spam- oder Phishingnachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="9d69e-133">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="9d69e-134">Wählen Sie die Nachricht aus, oder öffnen Sie die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9d69e-134">Select the message or open the message.</span></span> <span data-ttu-id="9d69e-135">Klicken Sie  **auf der Registerkarte "Start"** oder "Nachricht" im Menüband auf "Kein **Junk",** und wählen Sie dann "Als Nicht-Junk-E-Mail melden" oder "Als Phishing **melden" aus.** </span><span class="sxs-lookup"><span data-stu-id="9d69e-135">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Melden sie keine Junk- oder Phishing-E-Mails aus dem Menüband im Junk-E-Mail-Ordner.](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="9d69e-137">Klicken Sie mit der rechten Maustaste auf die Nachricht, klicken Sie auf **"Junk",** und wählen Sie "Als Nicht-Junk-E-Mail **melden"** oder "Als Phishing **melden" aus.**</span><span class="sxs-lookup"><span data-stu-id="9d69e-137">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Melden sie keine Junk- oder Phishing-E-Mails, wenn Sie mit der rechten Maustaste in den Junk-E-Mail-Ordner klicken.](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="9d69e-139">Wählen Sie mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann "Als Nicht-Junk-E-Mail **melden"** oder **"Als Phishing melden" aus.**</span><span class="sxs-lookup"><span data-stu-id="9d69e-139">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Melden mehrerer Junk- oder Phishing-E-Mail-Nachrichten durch Rechtsklick im Junk-E-Mail-Ordner](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="9d69e-141">Lesen Sie im angezeigten Dialogfeld die Informationen, und klicken Sie auf **"Bericht".**</span><span class="sxs-lookup"><span data-stu-id="9d69e-141">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="9d69e-142">Wenn Sie Ihre Meinung ändern, klicken Sie auf **"Nicht melden".**</span><span class="sxs-lookup"><span data-stu-id="9d69e-142">If you change your mind, click **Don't Report**.</span></span>

   ![Dialogfeld "Als nicht junk melden"](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Melden als Phishingdialogfeld](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="9d69e-145">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet und:</span><span class="sxs-lookup"><span data-stu-id="9d69e-145">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="9d69e-146">In den Junk-E-Mail-Ordner verschoben, wenn er als Spam gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="9d69e-146">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="9d69e-147">Gelöscht, wenn es als Phishing gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="9d69e-147">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="9d69e-148">Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="9d69e-148">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="9d69e-149">Installieren des Junk-E-Mail-Berichterstellungs-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="9d69e-149">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="9d69e-150">Sie benötigen Administratorrechte auf dem Computer, auf dem Sie das Add-in installieren.</span><span class="sxs-lookup"><span data-stu-id="9d69e-150">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="9d69e-151">Laden Sie die entsprechende .msi-Datei für Ihre Version von Office an einen leicht zu <https://www.microsoft.com/download/details.aspx?id=18275> findenen Speicherort herunter:</span><span class="sxs-lookup"><span data-stu-id="9d69e-151">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="9d69e-152">**32-Bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="9d69e-152">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="9d69e-153">**64-Bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="9d69e-153">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="9d69e-154">Für Outlook 2013 oder höher ist microsoft .NET Framework 2.0 die einzige Voraussetzung.</span><span class="sxs-lookup"><span data-stu-id="9d69e-154">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="9d69e-155">In Windows 10 installieren Sie .NET Framework 2.0 nicht aus einem Download.</span><span class="sxs-lookup"><span data-stu-id="9d69e-155">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="9d69e-156">Installieren des Junk-E-Mail-Berichterstellungs-Add-Ins mithilfe des Setup-Assistenten</span><span class="sxs-lookup"><span data-stu-id="9d69e-156">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="9d69e-157">Schließen Sie Outlook auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="9d69e-157">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="9d69e-158">Überprüfen Sie in Windows 10, ob .NET Framework 2.0 aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9d69e-158">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="9d69e-159">Anweisungen finden Sie unter [Aktivieren von .NET Framework 3.5 in der Systemsteuerung.](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)</span><span class="sxs-lookup"><span data-stu-id="9d69e-159">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="9d69e-160">Suchen Sie die heruntergeladene MSI-Datei, und doppelklicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="9d69e-160">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="9d69e-161">Klicken Sie auf der Seite **Willkommen beim Setup des Microsoft-Add-Ins "Junk-E-Mail-Berichtsprogramm"** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9d69e-161">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="9d69e-162">Überprüfen Sie den Lizenzvertrag, klicken Sie auf **"Ich** stimme den Bedingungen des Lizenzvertrags zu, wenn Sie den Bedingungen zustimmen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="9d69e-162">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="9d69e-163">Klicken Sie nach Abschluss des Assistenten auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="9d69e-163">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="9d69e-164">Starten Sie Outlook.</span><span class="sxs-lookup"><span data-stu-id="9d69e-164">Start Outlook.</span></span>

<span data-ttu-id="9d69e-165">Suchen Sie im Menüband von Outlook nach der Schaltfläche **"Junk".**</span><span class="sxs-lookup"><span data-stu-id="9d69e-165">Look for the **Junk** button on your Outlook ribbon.</span></span> <span data-ttu-id="9d69e-166">Sie können Microsoft nun Junk-E-Mails melden, indem Sie die entsprechenden E-Mails im Posteingang auswählen und dann auf die Schaltfläche **Junk-E-Mails melden** klicken.</span><span class="sxs-lookup"><span data-stu-id="9d69e-166">You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="9d69e-p110">Wählen Sie den Pfeil nach unten neben **Junk** aus, um weitere Optionen anzuzeigen, z. B. **Als betrügerischen Phishing-Versuch melden**, wenn Sie Phishing-Scam-E-Mails an Microsoft melden möchten. In Ihrem Junk-E-Mailordner können Sie auch **Keine Junk-E-Mail** auswählen, wenn eine E-Mail-Nachricht fälschlicherweise als Junk-E-Mail gekennzeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="9d69e-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="9d69e-169">Installieren des Add-Ins „Junk-E-Mail-Berichtsprogramm“ im unbeaufsichtigten Modus</span><span class="sxs-lookup"><span data-stu-id="9d69e-169">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="9d69e-170">Schließen Sie Outlook auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="9d69e-170">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="9d69e-171">Installieren Sie in Windows 10 .NET Framework 2.0, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="9d69e-171">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="9d69e-172">Öffnen Sie eine Eingabeaufforderung, und verwenden Sie die folgende Syntax, um das #A0 ohne Benutzerinteraktion zu installieren:</span><span class="sxs-lookup"><span data-stu-id="9d69e-172">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="9d69e-173">`MaxMessageSelection` gibt die maximale Anzahl von Nachrichten an, die Sie für eine einzelne Übermittlung auswählen können.</span><span class="sxs-lookup"><span data-stu-id="9d69e-173">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="9d69e-174">Gültige Werte sind 1 bis 50.</span><span class="sxs-lookup"><span data-stu-id="9d69e-174">Valid values are from 1 to 50.</span></span> <span data-ttu-id="9d69e-175">Der Standardwert ist 15.</span><span class="sxs-lookup"><span data-stu-id="9d69e-175">The default value is 15.</span></span>

   - <span data-ttu-id="9d69e-176">`BccEmailAddress` gibt zusätzliche Bcc-Empfänger an, die eine Kopie aller Benutzerübermittlungen erhalten.</span><span class="sxs-lookup"><span data-stu-id="9d69e-176">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="9d69e-177">Der Standardwert ist leer (keine weiteren Bcc-Empfänger).</span><span class="sxs-lookup"><span data-stu-id="9d69e-177">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="9d69e-178">In diesem Beispiel wird die 64-Bit-Version des Add-Ins aus dem angegebenen Pfad mit den Standardeinstellungen installiert.</span><span class="sxs-lookup"><span data-stu-id="9d69e-178">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="9d69e-179">In diesem Beispiel wird die 32-Bit-Version des Add-Ins aus dem angegebenen Pfad mit den folgenden zusätzlichen Einstellungen installiert:</span><span class="sxs-lookup"><span data-stu-id="9d69e-179">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="9d69e-180">Bis zu 20 Nachrichten können in einer einzigen Übermittlung ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="9d69e-180">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="9d69e-181">junkreports@contoso.com und hollyd@treyresearch.net erhalten Bcc-Kopien aller Übermittlungen.</span><span class="sxs-lookup"><span data-stu-id="9d69e-181">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="9d69e-182">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="9d69e-182">How do you know this worked?</span></span>

<span data-ttu-id="9d69e-183">Um zu überprüfen, ob Sie das Junk-E-Mail-Berichterstellungs-Add-In erfolgreich installiert haben, gehen Sie in Outlook wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="9d69e-183">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="9d69e-184">Wählen Sie die Nachricht aus, oder öffnen Sie die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9d69e-184">Select the message or open the message.</span></span> <span data-ttu-id="9d69e-185">Klicken Sie  **auf der Registerkarte "Start"** oder "Nachricht" im Menüband auf **"Junk",** und stellen Sie sicher, dass die folgenden Optionen verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="9d69e-185">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="9d69e-186">**Melden als Junk-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="9d69e-186">**Report as Junk**</span></span>
  - <span data-ttu-id="9d69e-187">**Melden als Phishing**</span><span class="sxs-lookup"><span data-stu-id="9d69e-187">**Report as Phishing**</span></span>
  - <span data-ttu-id="9d69e-188">**Junk-Berichtsoptionen**</span><span class="sxs-lookup"><span data-stu-id="9d69e-188">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="9d69e-189">**Melden der Junk-Online-Hilfe**</span><span class="sxs-lookup"><span data-stu-id="9d69e-189">**Report Junk Online Help**</span></span>

  ![Melden von Junk- oder Phishing-E-Mails über das Menüband](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="9d69e-191">Klicken Sie mit der rechten Maustaste auf die Nachricht, wählen **Sie "Junk"** aus, und stellen Sie sicher, dass die folgenden Optionen verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="9d69e-191">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="9d69e-192">**Melden als Junk-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="9d69e-192">**Report as Junk**</span></span>
  - <span data-ttu-id="9d69e-193">**Melden als Phishing**</span><span class="sxs-lookup"><span data-stu-id="9d69e-193">**Report as Phishing**</span></span>
  - <span data-ttu-id="9d69e-194">**Junk-Berichtsoptionen**</span><span class="sxs-lookup"><span data-stu-id="9d69e-194">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="9d69e-195">**Melden der Junk-Online-Hilfe**</span><span class="sxs-lookup"><span data-stu-id="9d69e-195">**Report Junk Online Help**</span></span>

  ![Melden von Junk- oder Phishing-E-Mails per Rechtsklick](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="9d69e-197">Wählen Sie mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und stellen Sie sicher, dass die folgenden Optionen verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="9d69e-197">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="9d69e-198">**Melden als Junk-E-Mail**</span><span class="sxs-lookup"><span data-stu-id="9d69e-198">**Report as Junk**</span></span>
  - <span data-ttu-id="9d69e-199">**Melden als Phishing**</span><span class="sxs-lookup"><span data-stu-id="9d69e-199">**Report as Phishing**</span></span>

  ![Melden mehrerer Junk- oder Phishing-E-Mail-Nachrichten mit der rechten Maustaste](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="9d69e-201">Gehen Sie wie zuvor im Junk-E-Mail-Ordner vor, und stellen Sie sicher, dass die vorherigen **Junk-E-Mail-Berichtsoptionen** jetzt **"Kein Junk" sind.** </span><span class="sxs-lookup"><span data-stu-id="9d69e-201">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Melden sie keine Junk- oder Phishing-E-Mails aus dem Menüband im Junk-E-Mail-Ordner.](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Melden sie keine Junk- oder Phishing-E-Mails, wenn Sie mit der rechten Maustaste in den Junk-E-Mail-Ordner klicken.](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Melden mehrerer Junk- oder Phishing-E-Mail-Nachrichten durch Rechtsklick im Junk-E-Mail-Ordner](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="9d69e-205">Deinstallieren des Add-Ins "Junk-E-Mail-Berichtsprogramm"</span><span class="sxs-lookup"><span data-stu-id="9d69e-205">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="9d69e-206">Nachdem Sie Outlook geschlossen haben, verwenden Sie eines der folgenden Verfahren, um das Junk-E-Mail-Berichterstellungs-Add-In zu deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="9d69e-206">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="9d69e-207">**Systemsteuerung:** Drücken Sie die Windows-TASTE + R. Geben Sie im dialogfeld **"Ausführen"** ein, das geöffnet wird, `control appwiz.cpl` und klicken Sie dann auf **"OK".**</span><span class="sxs-lookup"><span data-stu-id="9d69e-207">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="9d69e-208">Suchen Sie das **Microsoft-Add-In "Junk-E-Mail-Berichterstellung"** in der Liste, und wählen Sie es aus, und klicken Sie dann auf **"Deinstallieren".**</span><span class="sxs-lookup"><span data-stu-id="9d69e-208">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="9d69e-209">**Windows Installer-Paket:** Suchen oder herunterladen Sie die entsprechende MSI-Datei, und doppelklicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="9d69e-209">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="9d69e-210">**32-Bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="9d69e-210">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="9d69e-211">**64-Bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="9d69e-211">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="9d69e-212">Wählen Sie im angezeigten Dialogfeld **"Microsoft Junk-E-Mail-Berichterstellungs-Add-In für Outlook** entfernen" aus, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="9d69e-212">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="9d69e-213">**Silent Mode**: Suchen oder Herunterladen der entsprechenden MSI-Datei.</span><span class="sxs-lookup"><span data-stu-id="9d69e-213">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="9d69e-214">Ersetzen Sie in einem Eingabeaufforderungsfenster den Speicherort der MSI-Datei, und führen Sie einen der \<PathToFile\> folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="9d69e-214">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="9d69e-215">**32-Bit:**</span><span class="sxs-lookup"><span data-stu-id="9d69e-215">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="9d69e-216">**64-Bit:**</span><span class="sxs-lookup"><span data-stu-id="9d69e-216">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="9d69e-217">Wenn Sie Outlook nach der Deinstallation öffnen, sollten die Junk-, nicht Junk- und Phishingberichtsoptionen weg sein.</span><span class="sxs-lookup"><span data-stu-id="9d69e-217">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="9d69e-218">Problembehandlung für das Junk-E-Mail-Bericht-Add-In</span><span class="sxs-lookup"><span data-stu-id="9d69e-218">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="9d69e-219">Gelegentlich können Probleme mit Outlook nach dem Hinzufügen des Junk-E-Mail-Berichterstellungs-Add-Ins angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9d69e-219">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="9d69e-220">In diesem Abschnitt werden Probleme beschrieben, die auftreten können, sowie Tipps zum Beheben dieser Probleme.</span><span class="sxs-lookup"><span data-stu-id="9d69e-220">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="9d69e-221">Problembehandlung für Benutzer</span><span class="sxs-lookup"><span data-stu-id="9d69e-221">Troubleshooting for users</span></span>

<span data-ttu-id="9d69e-222">Eines oder mehrere der folgenden Probleme werden auftreten:</span><span class="sxs-lookup"><span data-stu-id="9d69e-222">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="9d69e-223">Das Programm reagiert nicht, wenn Sie auf **Junk-E-Mail melden** klicken</span><span class="sxs-lookup"><span data-stu-id="9d69e-223">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="9d69e-224">Outlook reagiert nicht mehr, wenn Sie eine E-Mail auswählen</span><span class="sxs-lookup"><span data-stu-id="9d69e-224">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="9d69e-225">Gemeldete Junk-E-Mails können nicht übermittelt werden, und es wird eine Unzustellbarkeitsnachricht angezeigt</span><span class="sxs-lookup"><span data-stu-id="9d69e-225">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="9d69e-226">Gehen Sie wie folgt vor, um dieses Problem zu beheben:</span><span class="sxs-lookup"><span data-stu-id="9d69e-226">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="9d69e-227">Schließen Sie Outlook, und starten Sie es neu.</span><span class="sxs-lookup"><span data-stu-id="9d69e-227">Close and restart Outlook.</span></span>
2. <span data-ttu-id="9d69e-228">Erstellen und senden Sie eine Testnachricht, und stellen Sie sicher, dass der Empfänger die Nachricht empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="9d69e-228">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="9d69e-229">Wenn das Problem weiterhin besteht, wenden Sie sich an Ihren Administrator.</span><span class="sxs-lookup"><span data-stu-id="9d69e-229">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="9d69e-230">Weitere Methoden, die Sie zum Übermitteln von Nachrichten an Microsoft verwenden können, finden Sie unter "Nachrichten und Dateien an [Microsoft melden".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="9d69e-230">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="9d69e-231">Problembehandlung für Administratoren</span><span class="sxs-lookup"><span data-stu-id="9d69e-231">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="9d69e-232">Problem: Es wird ständig eine Fehlermeldung angezeigt, in der Benutzer zur Kontaktaufnahme mit ihrem Systemadministrator gefragt werden.</span><span class="sxs-lookup"><span data-stu-id="9d69e-232">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="9d69e-233">Überprüfen oder legen Sie `LoggingLevel` den Registrierungsschlüssel auf den Wert "Verbose" (Ausführlich) ein:</span><span class="sxs-lookup"><span data-stu-id="9d69e-233">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="9d69e-234">**32-Bit-Version von Outlook unter 32-Bit-Windows:**</span><span class="sxs-lookup"><span data-stu-id="9d69e-234">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="9d69e-235">**32-Bit-Version von Outlook unter 64-Bit-Windows:**</span><span class="sxs-lookup"><span data-stu-id="9d69e-235">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="9d69e-236">**64-Bit-Version von Outlook:**</span><span class="sxs-lookup"><span data-stu-id="9d69e-236">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="9d69e-237">Starten Sie Outlook neu, und bitten Sie die Benutzer, sich zu melden, wenn die Fehlermeldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9d69e-237">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="9d69e-238">Erfassen Sie die Protokollinformationen am folgenden Speicherort:</span><span class="sxs-lookup"><span data-stu-id="9d69e-238">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="9d69e-239">Kontaktieren Sie den technischen Support für Exchange Online Protection, und übergeben Sie den Mitarbeitern diese Protokollinformationen.</span><span class="sxs-lookup"><span data-stu-id="9d69e-239">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="9d69e-240">Problem: Benutzer haben ausgewählt, dass beim Melden von Nachrichten keine Bestätigungsaufforderung angezeigt werden soll, und möchten nun die Aufforderung zurück</span><span class="sxs-lookup"><span data-stu-id="9d69e-240">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="9d69e-241">Erstellen Sie `ConfirmReportJunk` den Registrierungsschlüssel mit dem Wert "True":</span><span class="sxs-lookup"><span data-stu-id="9d69e-241">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="9d69e-242">Starten Sie Outlook neu.</span><span class="sxs-lookup"><span data-stu-id="9d69e-242">Restart Outlook.</span></span>

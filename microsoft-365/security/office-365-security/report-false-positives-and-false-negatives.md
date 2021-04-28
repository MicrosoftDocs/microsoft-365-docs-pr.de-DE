---
title: Melden falscher und falsch negativer Ergebnisse in Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie falsch positive und falsch negative Ergebnisse in Outlook melden und die Add-Ins "Nachricht melden" und "Phishing melden" aktivieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38f940a98581c5678eef0c57c95f6349cdb41de8
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065176"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="63cb3-103">Melden falscher und falsch negativer Ergebnisse in Outlook</span><span class="sxs-lookup"><span data-stu-id="63cb3-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="63cb3-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="63cb3-104">**Applies to**</span></span>
- [<span data-ttu-id="63cb3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="63cb3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="63cb3-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="63cb3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="63cb3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63cb3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="63cb3-108">Wenn Sie ein Administrator in einer Microsoft 365-Organisation mit Exchange Online-Postfächern sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="63cb3-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="63cb3-109">Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="63cb3-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="63cb3-110">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder lokalen Postfächern mit moderner Hybridauthentifizierung können Sie falsch positive Ergebnisse (gute E-Mails als Spam gekennzeichnet) und falsch negative (ungültige E-Mails und Phishing zulässig) an Exchange Online Protection (EOP) senden.</span><span class="sxs-lookup"><span data-stu-id="63cb3-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email marked as spam) and false negatives (bad email and phish allowed) to Exchange Online Protection (EOP).</span></span>

## <a name="things-to-remember-before-you-use-the-report-message-feature"></a><span data-ttu-id="63cb3-111">Dinge, die Sie vor der Verwendung des Berichtsnachrichtenfeatures beachten sollten</span><span class="sxs-lookup"><span data-stu-id="63cb3-111">Things to remember before you use the Report Message feature</span></span>

- <span data-ttu-id="63cb3-112">Verwenden Sie das Add-In Nachricht melden oder das Phishing-Add-In melden, um eine optimale Benutzerübermittlung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="63cb3-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="63cb3-113">Beachten Sie, dass dieses Add-In für Outlook auf allen Plattformen funktioniert – im Web, iOS, Android und Desktop.</span><span class="sxs-lookup"><span data-stu-id="63cb3-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="63cb3-114">Wenn Sie ein Administrator in einer Organisation mit Exchange Online-Postfächern sind, verwenden Sie das Übermittlungsportal im Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="63cb3-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="63cb3-115">Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="63cb3-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="63cb3-116">Sie können konfigurieren, dass Nachrichten direkt an Microsoft, ein von Ihnen festgelegtes Postfach oder beides gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="63cb3-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="63cb3-117">Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="63cb3-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="63cb3-118">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="63cb3-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="63cb3-119">Verwenden des Berichtsnachrichtenfeatures</span><span class="sxs-lookup"><span data-stu-id="63cb3-119">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="63cb3-120">Melden von Junk- und Phishingnachrichten</span><span class="sxs-lookup"><span data-stu-id="63cb3-120">Report junk and phishing messages</span></span>

<span data-ttu-id="63cb3-121">Verwenden Sie für Nachrichten im Posteingang oder in einem anderen E-Mail-Ordner mit Ausnahme von Junk-E-Mails die folgende Methode, um Spam- und Phishingnachrichten zu melden:</span><span class="sxs-lookup"><span data-stu-id="63cb3-121">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="63cb3-122">Klicken Sie **in der** oberen rechten Ecke der ausgewählten  Nachricht auf die Ellipsen Weitere Aktionen, klicken Sie im Dropdownmenü auf Nachricht melden, und wählen Sie **dann Junk** oder **Phishing aus.**</span><span class="sxs-lookup"><span data-stu-id="63cb3-122">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="63cb3-123">![Berichtsnachricht – Weitere Aktionen](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="63cb3-123">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="63cb3-124">![Berichtsnachricht – Junk und Phishing](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="63cb3-124">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="63cb3-125">Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet und:</span><span class="sxs-lookup"><span data-stu-id="63cb3-125">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="63cb3-126">In den Junk-E-Mail-Ordner verschoben, wenn er als Spam gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="63cb3-126">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="63cb3-127">Gelöscht, wenn es als Phishing gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="63cb3-127">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="63cb3-128">Melden von Nachrichten, die kein Junk sind</span><span class="sxs-lookup"><span data-stu-id="63cb3-128">Report messages that are not junk</span></span>

1. <span data-ttu-id="63cb3-129">Klicken Sie **in der** oberen rechten Ecke der ausgewählten  Nachricht auf die Ellipsen Weitere Aktionen, klicken Sie im Dropdownmenü auf Nachricht melden, und klicken Sie dann auf **Nicht Junk**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-129">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="63cb3-130">![Berichtsnachricht – Weitere Aktionen](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="63cb3-130">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="63cb3-131">![Berichtsnachricht – Kein Junk](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="63cb3-131">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="63cb3-132">Die ausgewählte Nachricht wird zur Analyse an Microsoft gesendet und in den Posteingang oder einen anderen angegebenen Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="63cb3-132">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="enable-the-report-message-and-report-phishing-add-ins"></a><span data-ttu-id="63cb3-133">Aktivieren der Phishing-Add-Ins "Nachricht melden" und "Melden"</span><span class="sxs-lookup"><span data-stu-id="63cb3-133">Enable the Report Message and Report Phishing add-ins</span></span>

<span data-ttu-id="63cb3-134">Die Phishing-Add-Ins für Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) ermöglichen es Benutzern, falsch positive Ergebnisse (gute E-Mails, die als schlecht gekennzeichnet sind) oder falsch negative (ungültige E-Mails sind zulässig) an Microsoft und seine Partner zur Analyse zu melden.</span><span class="sxs-lookup"><span data-stu-id="63cb3-134">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="63cb3-135">Microsoft verwendet diese Übermittlungen, um die Effektivität von E-Mail-Schutztechnologien zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="63cb3-135">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="63cb3-136">Angenommen, die Benutzer melden viele Nachrichten mithilfe des Phishing-Add-Ins Melden.</span><span class="sxs-lookup"><span data-stu-id="63cb3-136">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="63cb3-137">Diese Informationen werden im Sicherheitsdashboard und anderen Berichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63cb3-137">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="63cb3-138">Das Sicherheitsteam Ihrer Organisation kann diese Informationen als Hinweis darauf verwenden, dass Antiphishingrichtlinien möglicherweise aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="63cb3-138">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="63cb3-139">Sie können entweder das Add-In "Nachricht melden" oder "Phishing melden" installieren.</span><span class="sxs-lookup"><span data-stu-id="63cb3-139">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="63cb3-140">Wenn Ihre Benutzer Spam- und Phishingnachrichten melden sollen, stellen Sie das Report Message-Add-In in Ihrer Organisation zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="63cb3-140">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="63cb3-141">Weitere Informationen finden Sie unter Aktivieren des Berichtsnachrichten-Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="63cb3-141">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="63cb3-142">Das Add-In Report Message bietet die Möglichkeit, Sowohl Spam- als auch Phishingnachrichten zu melden.</span><span class="sxs-lookup"><span data-stu-id="63cb3-142">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="63cb3-143">Administratoren können das Report Message-Add-In für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.</span><span class="sxs-lookup"><span data-stu-id="63cb3-143">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="63cb3-144">Das Phishing-Add-In "Phishing melden" bietet die Möglichkeit, nur Phishingnachrichten zu melden.</span><span class="sxs-lookup"><span data-stu-id="63cb3-144">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="63cb3-145">Administratoren können das Phishing-Add-In melden für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.</span><span class="sxs-lookup"><span data-stu-id="63cb3-145">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="63cb3-146">Wenn Sie ein einzelner Benutzer sind, können Sie beide Add-Ins für sich selbst aktivieren.</span><span class="sxs-lookup"><span data-stu-id="63cb3-146">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="63cb3-147">f Sie ein globaler Administrator oder Exchange Online-Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie das Add-In "Nachricht melden" und das Phishing-Add-In melden für Ihre Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="63cb3-147">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="63cb3-148">Beide Add-Ins sind jetzt über die zentrale [Bereitstellung verfügbar.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="63cb3-148">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="63cb3-149">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="63cb3-149">What do you need to know before you begin?</span></span>

- <span data-ttu-id="63cb3-150">Sowohl das Add-In "Nachricht melden" als auch das Phishing-Add-In melden funktioniert mit den meisten Microsoft 365-Abonnements und den folgenden Produkten:</span><span class="sxs-lookup"><span data-stu-id="63cb3-150">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="63cb3-151">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="63cb3-151">Outlook on the web</span></span>
  - <span data-ttu-id="63cb3-152">Outlook 2013 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="63cb3-152">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="63cb3-153">Outlook 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="63cb3-153">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="63cb3-154">Outlook in Microsoft 365-Apps für Unternehmen enthalten</span><span class="sxs-lookup"><span data-stu-id="63cb3-154">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="63cb3-155">Outlook-App für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="63cb3-155">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="63cb3-156">Beide Add-Ins sind für freigegebene Postfächer oder Postfächer in lokalen Exchange-Organisationen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="63cb3-156">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="63cb3-157">Ihr vorhandener Webbrowser sollte sowohl mit den Add-Ins "Nachricht melden" als auch "Phishing melden" funktionieren. Wenn Sie jedoch feststellen, dass das Add-In nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie es mit einem anderen Browser.</span><span class="sxs-lookup"><span data-stu-id="63cb3-157">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="63cb3-158">Für Organisationsinstallationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="63cb3-158">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="63cb3-159">Weitere Informationen finden Sie unter [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="63cb3-159">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="63cb3-160">Administratoren müssen Mitglied der Rollengruppe Globale Administratoren sein.</span><span class="sxs-lookup"><span data-stu-id="63cb3-160">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="63cb3-161">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="63cb3-161">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="63cb3-162">Get the Report Message add-in</span><span class="sxs-lookup"><span data-stu-id="63cb3-162">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="63cb3-163">Das Add-In für sich selbst</span><span class="sxs-lookup"><span data-stu-id="63cb3-163">Get the add-in for yourself</span></span>

1. <span data-ttu-id="63cb3-164">Wechseln Sie zur Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> unter, und suchen Sie nach dem Add-In Nachricht melden.</span><span class="sxs-lookup"><span data-stu-id="63cb3-164">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="63cb3-165">Um direkt zum Add-In "Nachricht melden" zu wechseln, wechseln Sie zu <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="63cb3-165">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="63cb3-166">Klicken Sie **auf JETZT GET IT**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-166">Click **GET IT NOW**.</span></span>

   ![Berichtsnachricht – Jetzt erhalten](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="63cb3-168">Überprüfen Sie im angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-168">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="63cb3-169">Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto (für geschäftliche Nutzung) oder Ihrem Microsoft-Konto (für den persönlichen Gebrauch) an.</span><span class="sxs-lookup"><span data-stu-id="63cb3-169">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="63cb3-170">Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="63cb3-170">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="63cb3-171">In Outlook sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="63cb3-171">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="63cb3-172">![Symbol für Nachrichten-Add-In für Outlook melden](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="63cb3-172">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="63cb3-173">In Outlook im Web sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="63cb3-173">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="63cb3-174">![Symbol für Outlook im WebBericht Nachrichten-Add-In](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="63cb3-174">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="63cb3-175">Das Add-In für Ihre Organisation erhalten</span><span class="sxs-lookup"><span data-stu-id="63cb3-175">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="63cb3-176">Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="63cb3-176">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="63cb3-177">Wechseln Sie im Microsoft 365 Admin Center  zur Seite \> **Einstellungen-Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="63cb3-177">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="63cb3-178">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie oben auf der Seite Integrierte Apps zum Link Integrierte  \>  \> **Apps-Add-Ins.** </span><span class="sxs-lookup"><span data-stu-id="63cb3-178">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="63cb3-179">Wählen **Sie add-in** bereitstellen oben auf der Seite aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="63cb3-179">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="63cb3-181">Überprüfen Sie im angezeigten Flyout Bereitstellen eines neuen **Add-Ins** die Informationen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-181">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="63cb3-182">Klicken Sie auf der nächsten Seite im **Store auf Auswählen.**</span><span class="sxs-lookup"><span data-stu-id="63cb3-182">On the next page, click **Choose from the Store**.</span></span>

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="63cb3-184">Klicken Sie auf der angezeigten Seite  **Add-In** auswählen in das Feld Suchen, geben Sie **Meldung** melden ein, und klicken Sie dann auf **Suchsymbol** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="63cb3-184">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="63cb3-185">Suchen Sie in der Liste der Ergebnisse nach **Berichtnachricht,** und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-185">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Auswählen von Add-In-Suchergebnissen](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="63cb3-187">Überprüfen Sie im angezeigten Dialogfeld die Lizenzierungs- und Datenschutzinformationen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-187">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="63cb3-188">Konfigurieren Sie auf der angezeigten Seite **Add-In** konfigurieren die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="63cb3-188">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="63cb3-189">**Zugewiesene** Benutzer : Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="63cb3-189">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="63cb3-190">**Jeder** (Standard)</span><span class="sxs-lookup"><span data-stu-id="63cb3-190">**Everyone** (default)</span></span>
     - <span data-ttu-id="63cb3-191">**Bestimmte Benutzer/Gruppen**</span><span class="sxs-lookup"><span data-stu-id="63cb3-191">**Specific users / groups**</span></span>
     - <span data-ttu-id="63cb3-192">**Nur ich**</span><span class="sxs-lookup"><span data-stu-id="63cb3-192">**Just me**</span></span>

   - <span data-ttu-id="63cb3-193">**Bereitstellungsmethode**: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="63cb3-193">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="63cb3-194">**Fixed (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="63cb3-194">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="63cb3-195">**Verfügbar:** Benutzer können das Add-In unter **Home** \> **Get add-ins** \> **Admin-managed installieren.**</span><span class="sxs-lookup"><span data-stu-id="63cb3-195">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="63cb3-196">**Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann es jedoch entfernen.</span><span class="sxs-lookup"><span data-stu-id="63cb3-196">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Konfigurieren der Add-In-Seite](../../media/configure-add-in.png)

   <span data-ttu-id="63cb3-198">Klicken Sie nach Abschluss des Abschlusses auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-198">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="63cb3-199">Auf der **angezeigten** Seite Berichtsnachricht bereitstellen wird ein Fortschrittsbericht angezeigt, gefolgt von der Bestätigung, dass das Add-In bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="63cb3-199">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="63cb3-200">Klicken Sie nach dem Lesen der Informationen auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-200">After you read the information, click **Next**.</span></span>

   ![Seite "Berichtsnachricht bereitstellen"](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="63cb3-202">Überprüfen Sie auf der angezeigten Seite **Add-In** ankündigen die Informationen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-202">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Add-In-Seite ankündigen](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="63cb3-204">Überprüfen oder Bearbeiten von Einstellungen für das Report Message-Add-In</span><span class="sxs-lookup"><span data-stu-id="63cb3-204">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="63cb3-205">Wechseln Sie im Microsoft 365 Admin Center  zur Seite \> **Einstellungen-Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="63cb3-205">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="63cb3-206">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie oben auf der Seite Integrierte Apps zum Link Integrierte  \>  \> **Apps-Add-Ins.** </span><span class="sxs-lookup"><span data-stu-id="63cb3-206">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Dienst- und Add-Ins im neuen Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="63cb3-208">Suchen Sie das **Add-In Nachricht** melden, und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="63cb3-208">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="63cb3-209">Überprüfen **und** bearbeiten Sie im angezeigten Flyout Berichtsnachricht bearbeiten die Einstellungen, die für Ihre Organisation geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="63cb3-209">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="63cb3-210">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-210">When you're finished, click **Save**.</span></span>

   ![Einstellungen für das Berichtsnachrichten-Add-In](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="63cb3-212">Das Phishing-Add-In melden</span><span class="sxs-lookup"><span data-stu-id="63cb3-212">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="63cb3-213">Das Add-In für sich selbst</span><span class="sxs-lookup"><span data-stu-id="63cb3-213">Get the add-in for yourself</span></span>

1. <span data-ttu-id="63cb3-214">Wechseln Sie zur Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> unter, und suchen Sie nach dem Phishing-Add-In Melden.</span><span class="sxs-lookup"><span data-stu-id="63cb3-214">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="63cb3-215">Klicken Sie **auf JETZT GET IT**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-215">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="63cb3-216">Überprüfen Sie im angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-216">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="63cb3-217">Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto (für geschäftliche Nutzung) oder Ihrem Microsoft-Konto (für den persönlichen Gebrauch) an.</span><span class="sxs-lookup"><span data-stu-id="63cb3-217">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="63cb3-218">Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="63cb3-218">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="63cb3-219">In Outlook sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="63cb3-219">In Outlook, the icon looks like this:</span></span>

  ![Phishing-Add-In-Symbol für Outlook melden](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="63cb3-221">In Outlook im Web sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="63cb3-221">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="63cb3-222">![Outlook im Web Phishing-Add-In-Symbol melden](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="63cb3-222">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="63cb3-223">Das Add-In für Ihre Organisation erhalten</span><span class="sxs-lookup"><span data-stu-id="63cb3-223">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="63cb3-224">Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="63cb3-224">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="63cb3-225">Wechseln Sie im Microsoft 365 Admin Center  zur Seite \> **Einstellungen-Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="63cb3-225">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="63cb3-226">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie oben auf der Seite Integrierte Apps zum Link Integrierte  \>  \> **Apps-Add-Ins.** </span><span class="sxs-lookup"><span data-stu-id="63cb3-226">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="63cb3-227">Wählen **Sie add-in** bereitstellen oben auf der Seite aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="63cb3-227">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="63cb3-229">Überprüfen Sie im angezeigten Flyout Bereitstellen eines neuen **Add-Ins** die Informationen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-229">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="63cb3-230">Klicken Sie auf der nächsten Seite im **Store auf Auswählen.**</span><span class="sxs-lookup"><span data-stu-id="63cb3-230">On the next page, click **Choose from the Store**.</span></span>

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="63cb3-232">Klicken Sie auf der angezeigten Seite  **Add-In** auswählen in das Feld Suchen, geben Sie **Phishing** melden ein, und klicken Sie dann auf **Suchsymbol** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="63cb3-232">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="63cb3-233">Suchen Sie in der Liste der Ergebnisse nach **Phishing melden,** und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-233">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="63cb3-234">Überprüfen Sie im angezeigten Dialogfeld die Lizenzierungs- und Datenschutzinformationen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-234">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="63cb3-235">Konfigurieren Sie auf der angezeigten Seite **Add-In** konfigurieren die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="63cb3-235">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="63cb3-236">**Zugewiesene** Benutzer : Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="63cb3-236">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="63cb3-237">**Jeder** (Standard)</span><span class="sxs-lookup"><span data-stu-id="63cb3-237">**Everyone** (default)</span></span>
     - <span data-ttu-id="63cb3-238">**Bestimmte Benutzer/Gruppen**</span><span class="sxs-lookup"><span data-stu-id="63cb3-238">**Specific users / groups**</span></span>
     - <span data-ttu-id="63cb3-239">**Nur ich**</span><span class="sxs-lookup"><span data-stu-id="63cb3-239">**Just me**</span></span>

   - <span data-ttu-id="63cb3-240">**Bereitstellungsmethode**: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="63cb3-240">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="63cb3-241">**Fixed (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="63cb3-241">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="63cb3-242">**Verfügbar:** Benutzer können das Add-In unter **Home** \> **Get add-ins** \> **Admin-managed installieren.**</span><span class="sxs-lookup"><span data-stu-id="63cb3-242">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="63cb3-243">**Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann es jedoch entfernen.</span><span class="sxs-lookup"><span data-stu-id="63cb3-243">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="63cb3-244">Klicken Sie nach Abschluss des Abschlusses auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-244">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="63cb3-245">Auf der **angezeigten Seite Phishingbericht** bereitstellen sehen Sie einen Fortschrittsbericht, gefolgt von einer Bestätigung, dass das Add-In bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="63cb3-245">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="63cb3-246">Klicken Sie nach dem Lesen der Informationen auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-246">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="63cb3-247">Überprüfen Sie auf der angezeigten Seite **Add-In** ankündigen die Informationen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-247">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="63cb3-248">Überprüfen oder Bearbeiten von Einstellungen für das Phishing-Add-In melden</span><span class="sxs-lookup"><span data-stu-id="63cb3-248">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="63cb3-249">Wechseln Sie im Microsoft 365 Admin Center  zur Seite \> **Einstellungen-Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="63cb3-249">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="63cb3-250">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie oben auf der Seite Integrierte Apps zum Link Integrierte  \>  \> **Apps-Add-Ins.** </span><span class="sxs-lookup"><span data-stu-id="63cb3-250">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="63cb3-251">Suchen Sie das **Phishing-Add-In melden,** und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="63cb3-251">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="63cb3-252">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span><span class="sxs-lookup"><span data-stu-id="63cb3-252">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="63cb3-253">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="63cb3-253">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="63cb3-254">Anzeigen und Überprüfen von gemeldeten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="63cb3-254">View and review reported messages</span></span>

<span data-ttu-id="63cb3-255">Zum Überprüfen von Nachrichten, die Benutzer an Microsoft melden, haben Sie die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="63cb3-255">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="63cb3-256">Verwenden Sie das Administrator-Übermittlungsportal.</span><span class="sxs-lookup"><span data-stu-id="63cb3-256">Use the Admin Submissions portal.</span></span> <span data-ttu-id="63cb3-257">Weitere Informationen finden Sie unter [Anzeigen von Benutzerübermittlungen an Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="63cb3-257">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="63cb3-258">Erstellen Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet), um Kopien von gemeldeten Nachrichten zu senden.</span><span class="sxs-lookup"><span data-stu-id="63cb3-258">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="63cb3-259">Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, was Ihre Benutzer an Microsoft melden.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="63cb3-259">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
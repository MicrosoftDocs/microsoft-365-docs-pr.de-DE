---
title: Aktivieren des Add-Ins „Nachrichten melden“
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie das Report Message-Add-In für Outlook und Outlook im Web für einzelne Benutzer oder Ihre gesamte Organisation aktivieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4e85af902eaaa41eb82acf8d4b4baedc538e7888
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204042"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="7cf03-103">Aktivieren des Add-Ins „Nachrichten melden“</span><span class="sxs-lookup"><span data-stu-id="7cf03-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7cf03-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="7cf03-104">**Applies to**</span></span>
- [<span data-ttu-id="7cf03-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7cf03-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7cf03-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="7cf03-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7cf03-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7cf03-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="7cf03-108">Wenn Sie ein Administrator in einer Microsoft 365-Organisation mit Exchange Online-Postfächern sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7cf03-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="7cf03-109">Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="7cf03-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="7cf03-110">Mit den Phishing-Add-Ins für Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) können Benutzer falsch positive Ergebnisse (gute E-Mails, die als schlecht gekennzeichnet sind) oder falsch negative (ungültige E-Mails sind zulässig) für die Analyse an Microsoft und seine Partner melden.</span><span class="sxs-lookup"><span data-stu-id="7cf03-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="7cf03-111">Microsoft verwendet diese Übermittlungen, um die Effektivität von E-Mail-Schutztechnologien zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="7cf03-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="7cf03-112">Wenn z. B. viele Nachrichten gemeldet werden, die mithilfe des Berichtsnachrichten-Add-Ins als Junk-E-Mail gekennzeichnet wurden, muss das Sicherheitsteam Ihrer Organisation möglicherweise [Antispamrichtlinien anpassen.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7cf03-112">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="7cf03-113">Sie können entweder das Add-In "Nachricht melden" oder "Phishing melden" installieren.</span><span class="sxs-lookup"><span data-stu-id="7cf03-113">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="7cf03-114">Wenn Ihre Benutzer nur Phishingnachrichten melden sollen, stellen Sie das Phishing-Add-In Melden in Ihrer Organisation zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7cf03-114">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="7cf03-115">Weitere Informationen finden Sie unter [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="7cf03-115">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="7cf03-116">Das Add-In Report Message bietet die Möglichkeit, Sowohl Spam- als auch Phishingnachrichten zu melden.</span><span class="sxs-lookup"><span data-stu-id="7cf03-116">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="7cf03-117">Administratoren können das Report Message-Add-In für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.</span><span class="sxs-lookup"><span data-stu-id="7cf03-117">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="7cf03-118">Wenn Sie ein einzelner Benutzer sind, können Sie das [Add-In](#get-the-report-message-add-in-for-yourself)Nachricht melden für sich selbst aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7cf03-118">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="7cf03-119">Wenn Sie ein globaler Administrator oder Exchange Online-Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie das [Add-In](#get-and-enable-the-report-message-add-in-for-your-organization)Nachricht melden für Ihre Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7cf03-119">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="7cf03-120">Die Berichtsnachricht Add-In ist jetzt über die zentrale [Bereitstellung verfügbar.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="7cf03-120">The Report Message Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7cf03-121">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="7cf03-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7cf03-122">Das Berichtsnachrichten-Add-In funktioniert mit den meisten Microsoft 365-Abonnements und den folgenden Produkten:</span><span class="sxs-lookup"><span data-stu-id="7cf03-122">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="7cf03-123">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="7cf03-123">Outlook on the web</span></span>
  - <span data-ttu-id="7cf03-124">Outlook 2013 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="7cf03-124">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="7cf03-125">Outlook 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="7cf03-125">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="7cf03-126">Outlook in Microsoft 365-Apps für Unternehmen enthalten</span><span class="sxs-lookup"><span data-stu-id="7cf03-126">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="7cf03-127">Outlook-App für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="7cf03-127">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="7cf03-128">Das Berichtsnachrichten-Add-In ist für freigegebene Postfächer oder Postfächer in lokalen Exchange-Organisationen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7cf03-128">The Report Message add-in is not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="7cf03-129">Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen festgelegtes Postfach kopiert oder umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="7cf03-129">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="7cf03-130">Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="7cf03-130">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="7cf03-131">Ihr vorhandener Webbrowser sollte mit dem Report Message-Add-In funktionieren.</span><span class="sxs-lookup"><span data-stu-id="7cf03-131">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="7cf03-132">Wenn Sie jedoch feststellen, dass das Add-In nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie es mit einem anderen Browser.</span><span class="sxs-lookup"><span data-stu-id="7cf03-132">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="7cf03-133">Für Organisationsinstallationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="7cf03-133">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="7cf03-134">Weitere Informationen finden Sie unter [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="7cf03-134">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="7cf03-135">Administratoren müssen Mitglied der Rollengruppe Globale Administratoren sein.</span><span class="sxs-lookup"><span data-stu-id="7cf03-135">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="7cf03-136">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7cf03-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="7cf03-137">Erstellen des Berichtsnachrichten-Add-Ins für sich selbst</span><span class="sxs-lookup"><span data-stu-id="7cf03-137">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="7cf03-138">Wechseln Sie zur Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> unter, und suchen Sie nach dem Add-In Nachricht melden.</span><span class="sxs-lookup"><span data-stu-id="7cf03-138">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="7cf03-139">Um direkt zum Add-In "Nachricht melden" zu wechseln, wechseln Sie zu <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="7cf03-139">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="7cf03-140">Klicken Sie **auf JETZT GET IT**.</span><span class="sxs-lookup"><span data-stu-id="7cf03-140">Click **GET IT NOW**.</span></span>

   ![Berichtsnachricht – Jetzt erhalten](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="7cf03-142">Überprüfen Sie im angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7cf03-142">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="7cf03-143">Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto (für geschäftliche Nutzung) oder Ihrem Microsoft-Konto (für den persönlichen Gebrauch) an.</span><span class="sxs-lookup"><span data-stu-id="7cf03-143">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="7cf03-144">Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7cf03-144">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="7cf03-145">In Outlook sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="7cf03-145">In Outlook, the icon looks like this:</span></span>

  ![Symbol für Nachrichten-Add-In für Outlook melden](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="7cf03-147">In Outlook im Web sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="7cf03-147">In Outlook on the web, the icon looks like this:</span></span>

  ![Symbol für Outlook im WebBericht Nachrichten-Add-In](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="7cf03-149">Informationen zur Verwendung des Add-Ins finden Sie unter [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="7cf03-149">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="7cf03-150">Get and enable the Report Message add-in for your organization</span><span class="sxs-lookup"><span data-stu-id="7cf03-150">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="7cf03-151">Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7cf03-151">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="7cf03-152">Wechseln Sie im Microsoft 365 Admin Center  zur Seite Einstellungen-Add-Ins unter , Wenn die \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **Add-In-Seite**  nicht angezeigt wird, wechseln Sie zum Link Integrierte \>  \> **Apps-Add-Ins**  einstellungen oben auf der Seite Integrierte Apps.</span><span class="sxs-lookup"><span data-stu-id="7cf03-152">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="7cf03-153">Wählen **Sie add-in** bereitstellen oben auf der Seite aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7cf03-153">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="7cf03-155">Überprüfen Sie im angezeigten Flyout Bereitstellen eines neuen **Add-Ins** die Informationen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7cf03-155">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="7cf03-156">Klicken Sie auf der nächsten Seite im **Store auf Auswählen.**</span><span class="sxs-lookup"><span data-stu-id="7cf03-156">On the next page, click **Choose from the Store**.</span></span>

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="7cf03-158">Klicken Sie auf der angezeigten Seite  **Add-In** auswählen in das Feld Suchen, geben Sie **Meldung** melden ein, und klicken Sie dann auf **Suchsymbol** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="7cf03-158">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="7cf03-159">Suchen Sie in der Liste der Ergebnisse nach **Berichtnachricht,** und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7cf03-159">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Auswählen von Add-In-Suchergebnissen](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="7cf03-161">Überprüfen Sie im angezeigten Dialogfeld die Lizenzierungs- und Datenschutzinformationen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7cf03-161">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="7cf03-162">Konfigurieren Sie auf der angezeigten Seite **Add-In** konfigurieren die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="7cf03-162">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="7cf03-163">**Zugewiesene** Benutzer : Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="7cf03-163">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="7cf03-164">**Jeder** (Standard)</span><span class="sxs-lookup"><span data-stu-id="7cf03-164">**Everyone** (default)</span></span>
     - <span data-ttu-id="7cf03-165">**Bestimmte Benutzer/Gruppen**</span><span class="sxs-lookup"><span data-stu-id="7cf03-165">**Specific users / groups**</span></span>
     - <span data-ttu-id="7cf03-166">**Nur ich**</span><span class="sxs-lookup"><span data-stu-id="7cf03-166">**Just me**</span></span>

   - <span data-ttu-id="7cf03-167">**Bereitstellungsmethode**: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="7cf03-167">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="7cf03-168">**Fixed (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="7cf03-168">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="7cf03-169">**Verfügbar:** Benutzer können das Add-In unter **Home** \> **Get add-ins** \> **Admin-managed installieren.**</span><span class="sxs-lookup"><span data-stu-id="7cf03-169">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="7cf03-170">**Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann es jedoch entfernen.</span><span class="sxs-lookup"><span data-stu-id="7cf03-170">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Konfigurieren der Add-In-Seite](../../media/configure-add-in.png)

   <span data-ttu-id="7cf03-172">Klicken Sie nach Abschluss des Abschlusses auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="7cf03-172">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="7cf03-173">Auf der **angezeigten** Seite Berichtsnachricht bereitstellen wird ein Fortschrittsbericht angezeigt, gefolgt von der Bestätigung, dass das Add-In bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7cf03-173">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="7cf03-174">Klicken Sie nach dem Lesen der Informationen auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7cf03-174">After you read the information, click **Next**.</span></span>

   ![Seite "Berichtsnachricht bereitstellen"](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="7cf03-176">Überprüfen Sie auf der angezeigten Seite **Add-In** ankündigen die Informationen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="7cf03-176">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Add-In-Seite ankündigen](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="7cf03-178">Informationen zur Verwendung des Berichtsnachrichten-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="7cf03-178">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="7cf03-179">Personen, denen das Add-In zugewiesen ist, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7cf03-179">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="7cf03-180">In Outlook sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="7cf03-180">In Outlook, the icon looks like this:</span></span>

  ![Symbol für Nachrichten-Add-In für Outlook melden](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="7cf03-182">In Outlook im Web sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="7cf03-182">In Outlook on the web, the icon looks like this:</span></span>

  ![Symbol für Outlook im Webbericht Nachrichten-Add-In](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="7cf03-184">Wenn Sie Benutzer über das Add-In "Nachricht melden" benachrichtigen, fügen Sie einen Link zum Verwenden des [Berichtsnachricht-Add-Ins hinzu.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="7cf03-184">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="7cf03-185">Überprüfen oder Bearbeiten von Einstellungen für das Report Message-Add-In</span><span class="sxs-lookup"><span data-stu-id="7cf03-185">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="7cf03-186">Wechseln Sie im Microsoft 365 Admin Center  zur Seite Einstellungen-Add-Ins unter , Wenn die \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **Add-In-Seite**  nicht angezeigt wird, wechseln Sie zum Link Integrierte \>  \> **Apps-Add-Ins**  einstellungen oben auf der Seite Integrierte Apps.</span><span class="sxs-lookup"><span data-stu-id="7cf03-186">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Dienst- und Add-Ins im neuen Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="7cf03-188">Suchen Sie das **Add-In Nachricht** melden, und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="7cf03-188">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="7cf03-189">Überprüfen **und** bearbeiten Sie im angezeigten Flyout Berichtsnachricht bearbeiten die Einstellungen, die für Ihre Organisation geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="7cf03-189">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="7cf03-190">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7cf03-190">When you're finished, click **Save**.</span></span>

   ![Einstellungen für das Berichtsnachrichten-Add-In](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="7cf03-192">Anzeigen und Überprüfen von gemeldeten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="7cf03-192">View and review reported messages</span></span>

<span data-ttu-id="7cf03-193">Zum Überprüfen von Nachrichten, die Benutzer an Microsoft melden, haben Sie die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="7cf03-193">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="7cf03-194">Verwenden Sie das Administrator-Übermittlungsportal.</span><span class="sxs-lookup"><span data-stu-id="7cf03-194">Use the Admin Submissions portal.</span></span> <span data-ttu-id="7cf03-195">Weitere Informationen finden Sie unter [Anzeigen von Benutzerübermittlungen an Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="7cf03-195">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="7cf03-196">Erstellen Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet), um Kopien von gemeldeten Nachrichten zu senden.</span><span class="sxs-lookup"><span data-stu-id="7cf03-196">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="7cf03-197">Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, was Ihre Benutzer an Microsoft melden.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="7cf03-197">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>

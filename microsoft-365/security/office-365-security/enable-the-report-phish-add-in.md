---
title: Aktivieren des Berichts-Phish-Add-Ins
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie das Phishing-Add-In "Phishing melden" für Outlook und Outlook im Web für einzelne Benutzer oder Ihre gesamte Organisation aktivieren.
ms.openlocfilehash: 12543364943321689d0efa2c2942351b3d3ec6f9
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453765"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="712d4-103">Aktivieren des Add-Ins „Phishing melden“</span><span class="sxs-lookup"><span data-stu-id="712d4-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="712d4-104">Wenn Sie ein Administrator in einer Microsoft 365-Organisation mit Exchange Online-Postfächern sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="712d4-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="712d4-105">Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="712d4-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="712d4-106">Die Phishing-Add-Ins für Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) ermöglichen es Benutzern, falsch positive Ergebnisse (gute E-Mails, die als schlecht gekennzeichnet sind) oder falsch negative (ungültige E-Mails sind zulässig) an Microsoft und seine Partner zur Analyse zu melden.</span><span class="sxs-lookup"><span data-stu-id="712d4-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="712d4-107">Microsoft verwendet diese Übermittlungen, um die Effektivität von E-Mail-Schutztechnologien zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="712d4-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="712d4-108">Angenommen, die Benutzer melden viele Nachrichten mithilfe des Phishing-Add-Ins Melden.</span><span class="sxs-lookup"><span data-stu-id="712d4-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="712d4-109">Diese Informationen werden im [Sicherheitsdashboard und](security-dashboard.md) anderen Berichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="712d4-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="712d4-110">Das Sicherheitsteam Ihrer Organisation kann diese Informationen als Hinweis darauf verwenden, dass Antiphishingrichtlinien möglicherweise aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="712d4-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="712d4-111">Sie können entweder das Add-In "Nachricht melden" oder "Phishing melden" installieren.</span><span class="sxs-lookup"><span data-stu-id="712d4-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="712d4-112">Wenn Ihre Benutzer Spam- und Phishingnachrichten melden sollen, stellen Sie das Report Message-Add-In in Ihrer Organisation zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="712d4-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="712d4-113">Weitere Informationen finden Sie unter [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="712d4-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="712d4-114">Das Phishing-Add-In "Phishing melden" bietet die Möglichkeit, nur Phishingnachrichten zu melden.</span><span class="sxs-lookup"><span data-stu-id="712d4-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="712d4-115">Administratoren können das Phishing-Add-In melden für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.</span><span class="sxs-lookup"><span data-stu-id="712d4-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="712d4-116">Wenn Sie ein einzelner Benutzer sind, können Sie das [Phishing-Add-In](#get-the-report-phishing-add-in-for-yourself)melden für sich selbst aktivieren.</span><span class="sxs-lookup"><span data-stu-id="712d4-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="712d4-117">Wenn Sie ein globaler Administrator oder Exchange Online-Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie das [Phishing-Add-In](#get-and-enable-the-report-phishing-add-in-for-your-organization)melden für Ihre Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="712d4-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="712d4-118">Der Phishingbericht Add-In jetzt über die zentrale [Bereitstellung verfügbar.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="712d4-118">The Report Phishing Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="712d4-119">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="712d4-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="712d4-120">Das Phishing-Add-In "Phishing melden" funktioniert mit den meisten Microsoft 365-Abonnements und den folgenden Produkten:</span><span class="sxs-lookup"><span data-stu-id="712d4-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="712d4-121">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="712d4-121">Outlook on the web</span></span>
  - <span data-ttu-id="712d4-122">Outlook 2013 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="712d4-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="712d4-123">Outlook 2016 für Mac oder höher</span><span class="sxs-lookup"><span data-stu-id="712d4-123">Outlook 2016 for Mac or later</span></span>
  - <span data-ttu-id="712d4-124">Outlook in Microsoft 365-Apps für Unternehmen enthalten</span><span class="sxs-lookup"><span data-stu-id="712d4-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="712d4-125">Outlook-App für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="712d4-125">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="712d4-126">Das Phishing-Add-In melden ist für freigegebene Postfächer oder Postfächer in lokalen Exchange-Organisationen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="712d4-126">The Report Phishing add-in is not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="712d4-127">Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen festgelegtes Postfach kopiert oder umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="712d4-127">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="712d4-128">Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="712d4-128">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="712d4-129">Ihr vorhandener Webbrowser sollte mit dem Phishing-Add-In Melden funktionieren.</span><span class="sxs-lookup"><span data-stu-id="712d4-129">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="712d4-130">Wenn Sie jedoch feststellen, dass das Add-In nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie es mit einem anderen Browser.</span><span class="sxs-lookup"><span data-stu-id="712d4-130">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="712d4-131">Für Organisationsinstallationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="712d4-131">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="712d4-132">Weitere Informationen finden Sie unter [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="712d4-132">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="712d4-133">Administratoren müssen Mitglied der Rollengruppe Globale Administratoren sein.</span><span class="sxs-lookup"><span data-stu-id="712d4-133">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="712d4-134">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="712d4-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="712d4-135">Melden Des Phishing-Add-Ins für sich selbst</span><span class="sxs-lookup"><span data-stu-id="712d4-135">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="712d4-136">Wechseln Sie zur Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> unter, und suchen Sie nach dem Phishing-Add-In Melden.</span><span class="sxs-lookup"><span data-stu-id="712d4-136">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="712d4-137">Klicken Sie **auf JETZT GET IT**.</span><span class="sxs-lookup"><span data-stu-id="712d4-137">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="712d4-138">Überprüfen Sie im angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="712d4-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="712d4-139">Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto (für geschäftliche Nutzung) oder Ihrem Microsoft-Konto (für den persönlichen Gebrauch) an.</span><span class="sxs-lookup"><span data-stu-id="712d4-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="712d4-140">Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="712d4-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="712d4-141">In Outlook sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="712d4-141">In Outlook, the icon looks like this:</span></span>

  ![Phishing-Add-In-Symbol für Outlook melden](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="712d4-143">In Outlook im Web sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="712d4-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook im Web Phishing-Add-In-Symbol melden](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="712d4-145">Erhalten und Aktivieren des Phishing-Add-Ins "Phishing melden" für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="712d4-145">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="712d4-146">Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="712d4-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="712d4-147">Wechseln Sie im Microsoft 365 Admin Center  zur Seite Einstellungen-Add-Ins unter , Wenn die \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **Add-In-Seite**  nicht angezeigt wird, wechseln Sie zum Link Integrierte \>  \> **Apps-Add-Ins**  einstellungen oben auf der Seite Integrierte Apps.</span><span class="sxs-lookup"><span data-stu-id="712d4-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="712d4-148">Wählen **Sie add-in** bereitstellen oben auf der Seite aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="712d4-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="712d4-150">Überprüfen Sie im angezeigten Flyout Bereitstellen eines neuen **Add-Ins** die Informationen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="712d4-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="712d4-151">Klicken Sie auf der nächsten Seite im **Store auf Auswählen.**</span><span class="sxs-lookup"><span data-stu-id="712d4-151">On the next page, click **Choose from the Store**.</span></span>

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="712d4-153">Klicken Sie auf der angezeigten Seite  **Add-In** auswählen in das Feld Suchen, geben Sie **Phishing** melden ein, und klicken Sie dann auf **Suchsymbol** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="712d4-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="712d4-154">Suchen Sie in der Liste der Ergebnisse nach **Phishing melden,** und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="712d4-154">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="712d4-155">Überprüfen Sie im angezeigten Dialogfeld die Lizenzierungs- und Datenschutzinformationen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="712d4-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="712d4-156">Konfigurieren Sie auf der angezeigten Seite **Add-In** konfigurieren die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="712d4-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="712d4-157">**Zugewiesene** Benutzer : Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="712d4-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="712d4-158">**Jeder** (Standard)</span><span class="sxs-lookup"><span data-stu-id="712d4-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="712d4-159">**Bestimmte Benutzer/Gruppen**</span><span class="sxs-lookup"><span data-stu-id="712d4-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="712d4-160">**Nur ich**</span><span class="sxs-lookup"><span data-stu-id="712d4-160">**Just me**</span></span>

   - <span data-ttu-id="712d4-161">**Bereitstellungsmethode**: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="712d4-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="712d4-162">**Fixed (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="712d4-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="712d4-163">**Verfügbar:** Benutzer können das Add-In unter **Home** \> **Get add-ins** \> **Admin-managed installieren.**</span><span class="sxs-lookup"><span data-stu-id="712d4-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="712d4-164">**Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann es jedoch entfernen.</span><span class="sxs-lookup"><span data-stu-id="712d4-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="712d4-165">Klicken Sie nach Abschluss des Abschlusses auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="712d4-165">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="712d4-166">Auf der **angezeigten Seite Phishingbericht** bereitstellen sehen Sie einen Fortschrittsbericht, gefolgt von einer Bestätigung, dass das Add-In bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="712d4-166">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="712d4-167">Klicken Sie nach dem Lesen der Informationen auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="712d4-167">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="712d4-168">Überprüfen Sie auf der angezeigten Seite **Add-In** ankündigen die Informationen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="712d4-168">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="712d4-169">Erfahren Sie, wie Sie das Phishing-Add-In "Phishing melden" verwenden</span><span class="sxs-lookup"><span data-stu-id="712d4-169">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="712d4-170">Personen, denen das Add-In zugewiesen ist, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="712d4-170">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="712d4-171">In Outlook sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="712d4-171">In Outlook, the icon looks like this:</span></span>

  ![Phishing-Add-In-Symbol für Outlook melden](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="712d4-173">In Outlook im Web sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="712d4-173">In Outlook on the web, the icon looks like this:</span></span>

  ![Symbol für Phishing-Add-Ins für Outlook im Webbericht](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="712d4-175">Überprüfen oder Bearbeiten von Einstellungen für das Phishing-Add-In melden</span><span class="sxs-lookup"><span data-stu-id="712d4-175">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="712d4-176">Wechseln Sie im Microsoft 365 Admin Center  zur Seite Einstellungen-Add-Ins unter , Wenn die \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **Add-In-Seite**  nicht angezeigt wird, wechseln Sie zum Link Integrierte \>  \> **Apps-Add-Ins**  einstellungen oben auf der Seite Integrierte Apps.</span><span class="sxs-lookup"><span data-stu-id="712d4-176">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="712d4-177">Suchen Sie das **Phishing-Add-In melden,** und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="712d4-177">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="712d4-178">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span><span class="sxs-lookup"><span data-stu-id="712d4-178">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="712d4-179">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="712d4-179">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="712d4-180">Anzeigen und Überprüfen von gemeldeten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="712d4-180">View and review reported messages</span></span>

<span data-ttu-id="712d4-181">Zum Überprüfen von Nachrichten, die Benutzer an Microsoft melden, haben Sie die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="712d4-181">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="712d4-182">Verwenden Sie das Administrator-Übermittlungsportal.</span><span class="sxs-lookup"><span data-stu-id="712d4-182">Use the Admin Submissions portal.</span></span> <span data-ttu-id="712d4-183">Weitere Informationen finden Sie unter [Anzeigen von Benutzerübermittlungen an Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="712d4-183">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="712d4-184">Erstellen Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet), um Kopien von gemeldeten Nachrichten zu senden.</span><span class="sxs-lookup"><span data-stu-id="712d4-184">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="712d4-185">Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, was Ihre Benutzer an Microsoft melden.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="712d4-185">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>

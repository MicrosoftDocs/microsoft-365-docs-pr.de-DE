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
description: Erfahren Sie, wie Sie das Phishing-Add-In "Melden" für Outlook und Outlook im Web, für einzelne Benutzer oder ihre gesamte Organisation aktivieren.
ms.openlocfilehash: 6d86fdc710539bc3c74eb94f8931ca48a0c992c1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029138"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="f1afe-103">Aktivieren des Add-Ins „Phishing melden“</span><span class="sxs-lookup"><span data-stu-id="f1afe-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="f1afe-104">Wenn Sie ein Administrator in einer Microsoft 365-Organisation mit Exchange Online-Postfächern sind, empfehlen wir die Verwendung des Übermittlungsportals im Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="f1afe-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f1afe-105">Weitere Informationen finden Sie unter "Use Admin Submission", um verdächtige [Spam-, Phishing-, URLs-](admin-submission.md)und Dateien an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="f1afe-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f1afe-106">Die "Nachricht melden" und "Phishing melden"-Add-Ins für Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) ermöglichen Es Benutzern, falsch positive Ergebnisse (eine gute E-Mail als schlecht markiert) oder falsch negative Ergebnisse (ungültige E-Mails sind zulässig) zur Analyse an Microsoft und seine Partner zu melden.</span><span class="sxs-lookup"><span data-stu-id="f1afe-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="f1afe-107">Microsoft verwendet diese Übermittlungen, um die Effektivität von E-Mail-Schutztechnologien zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="f1afe-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="f1afe-108">Nehmen wir beispielsweise an, dass Benutzer viele Nachrichten mit dem Phishing-Add-In "Melden" melden.</span><span class="sxs-lookup"><span data-stu-id="f1afe-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="f1afe-109">Diese Informationen werden im [Sicherheitsdashboard und](security-dashboard.md) anderen Berichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1afe-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="f1afe-110">Das Sicherheitsteam Ihrer Organisation kann diese Informationen als Hinweis darauf verwenden, dass Antiphishingrichtlinien möglicherweise aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f1afe-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="f1afe-111">Sie können entweder das Add-In "Nachricht melden" oder "Phishing melden" installieren.</span><span class="sxs-lookup"><span data-stu-id="f1afe-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="f1afe-112">Wenn Ihre Benutzer Sowohl Spam- als auch Phishingnachrichten melden sollen, stellen Sie das Report Message-Add-In in Ihrer Organisation zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f1afe-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="f1afe-113">Weitere Informationen finden Sie unter [Aktivieren des Berichtsnachrichten-Add-Ins.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="f1afe-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="f1afe-114">Das Phishing-Add-In "Melden" bietet die Möglichkeit, nur Phishingnachrichten zu melden.</span><span class="sxs-lookup"><span data-stu-id="f1afe-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="f1afe-115">Administratoren können das Phishing-Add-In "Melden" für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.</span><span class="sxs-lookup"><span data-stu-id="f1afe-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="f1afe-116">Wenn Sie ein einzelner Benutzer sind, können Sie das [Phishing-Add-In "Melden" für sich selbst aktivieren.](#get-the-report-phishing-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="f1afe-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="f1afe-117">Wenn Sie ein globaler Administrator oder Exchange Online-Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie das [Phishing-Add-In](#get-and-enable-the-report-phishing-add-in-for-your-organization)"Melden" für Ihre Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f1afe-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="f1afe-118">Der Phishingbericht Add-In ist jetzt über die [zentrale Bereitstellung verfügbar.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="f1afe-118">The Report Phishing Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f1afe-119">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="f1afe-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f1afe-120">Das Phishing-Add-In "Melden" funktioniert mit den meisten Microsoft 365-Abonnements und den folgenden Produkten:</span><span class="sxs-lookup"><span data-stu-id="f1afe-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="f1afe-121">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="f1afe-121">Outlook on the web</span></span>
  - <span data-ttu-id="f1afe-122">Outlook 2013 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="f1afe-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="f1afe-123">Outlook 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="f1afe-123">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="f1afe-124">Outlook im Lieferumfang von Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="f1afe-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="f1afe-125">Das Phishing-Add-In "Melden" ist für Postfächer in lokalen Exchange-Organisationen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f1afe-125">The Report Phishing add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="f1afe-126">Sie können gemeldete Nachrichten so konfigurieren, dass sie kopiert oder an ein von Ihnen festgelegtes Postfach umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="f1afe-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="f1afe-127">Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f1afe-127">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="f1afe-128">Ihr vorhandener Webbrowser sollte mit dem Phishing-Add-In "Melden" funktionieren.</span><span class="sxs-lookup"><span data-stu-id="f1afe-128">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="f1afe-129">Wenn Sie jedoch feststellen, dass das Add-in nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie es in einem anderen Browser.</span><span class="sxs-lookup"><span data-stu-id="f1afe-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="f1afe-130">Für Organisationsinstallationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f1afe-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="f1afe-131">Weitere Informationen finden Sie unter Ermitteln, ob die zentrale Bereitstellung von [Add-Ins für Ihre Organisation funktioniert.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="f1afe-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="f1afe-132">Administratoren müssen Mitglied der Rollengruppe "Globale Administratoren" sein.</span><span class="sxs-lookup"><span data-stu-id="f1afe-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="f1afe-133">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f1afe-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="f1afe-134">Das Phishing-Add-In "Melden" für sich selbst erhalten</span><span class="sxs-lookup"><span data-stu-id="f1afe-134">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="f1afe-135">Wechseln Sie zu Microsoft AppSource, <https://appsource.microsoft.com/marketplace/apps> und suchen Sie nach dem Phishing-Add-In "Melden".</span><span class="sxs-lookup"><span data-stu-id="f1afe-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="f1afe-136">Klicken **Sie auf "JETZT GET IT".**</span><span class="sxs-lookup"><span data-stu-id="f1afe-136">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="f1afe-137">Überprüfen Sie im angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="f1afe-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="f1afe-138">Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Firmenkonto (zur geschäftlichen Nutzung) oder Ihrem Microsoft-Konto (zur persönlichen Verwendung) an.</span><span class="sxs-lookup"><span data-stu-id="f1afe-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="f1afe-139">Nachdem das Add-in installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f1afe-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="f1afe-140">In Outlook sieht das Symbol wie hier dargestellt aus:</span><span class="sxs-lookup"><span data-stu-id="f1afe-140">In Outlook, the icon looks like this:</span></span>

  ![Melden eines Phishing-Add-In-Symbols für Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="f1afe-142">In Outlook im Web sieht das Symbol wie hier dargestellt aus:</span><span class="sxs-lookup"><span data-stu-id="f1afe-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook im Web – Symbol für Phishing-Add-In-Bericht](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="f1afe-144">Erhalten und Aktivieren des Phishing-Add-Ins "Melden" für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="f1afe-144">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="f1afe-145">Es kann bis zu 12 Stunden dauern, bis das Add-in in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f1afe-145">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="f1afe-146">Wechseln Sie im Microsoft 365 Admin Center  zur Seite \> **"Einstellungen-Add-Ins".** Wenn die <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **Add-In-Seite**  nicht angezeigt wird, wechseln \>  \>   Sie oben auf der Seite "Integrierte Apps" zum Link "Integrierte Apps".</span><span class="sxs-lookup"><span data-stu-id="f1afe-146">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="f1afe-147">Wählen Sie oben auf der Seite **"Add-In** bereitstellen" und dann **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="f1afe-147">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="f1afe-149">Überprüfen Sie **im angezeigten Flyout** "Neues Add-In bereitstellen" die Informationen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="f1afe-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="f1afe-150">Klicken Sie auf der nächsten Seite auf **"Aus Store auswählen".**</span><span class="sxs-lookup"><span data-stu-id="f1afe-150">On the next page, click **Choose from the Store**.</span></span>

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="f1afe-152">Klicken Sie auf **der angezeigten Seite "Add-In** auswählen" in das  Suchfeld, geben **Sie "Phishing** melden" ein, und klicken Sie dann auf das Suchsymbol  ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="f1afe-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="f1afe-153">Suchen Sie in der Ergebnisliste nach **"Phishing melden",** und klicken Sie dann auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="f1afe-153">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="f1afe-154">Überprüfen Sie im angezeigten Dialogfeld die Lizenzierungs- und Datenschutzinformationen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="f1afe-154">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="f1afe-155">Konfigurieren Sie auf der angezeigten Seite **"Add-In** konfigurieren" die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f1afe-155">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f1afe-156">**Zugewiesene Benutzer:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="f1afe-156">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="f1afe-157">**Jeder** (Standard)</span><span class="sxs-lookup"><span data-stu-id="f1afe-157">**Everyone** (default)</span></span>
     - <span data-ttu-id="f1afe-158">**Bestimmte Benutzer/Gruppen**</span><span class="sxs-lookup"><span data-stu-id="f1afe-158">**Specific users / groups**</span></span>
     - <span data-ttu-id="f1afe-159">**Nur ich**</span><span class="sxs-lookup"><span data-stu-id="f1afe-159">**Just me**</span></span>

   - <span data-ttu-id="f1afe-160">**Bereitstellungsmethode:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="f1afe-160">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="f1afe-161">**Fixed (Standard):** Das Add-in wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="f1afe-161">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="f1afe-162">**Verfügbar:** Benutzer können das Add-in unter **"Home** \> **Get add-ins** \> **Admin-managed" installieren.**</span><span class="sxs-lookup"><span data-stu-id="f1afe-162">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="f1afe-163">**Optional:** Das Add-in wird automatisch für die angegebenen Benutzer bereitgestellt, kann aber entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="f1afe-163">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="f1afe-164">Klicken Sie nach Abschluss des Abschlusses auf **"Bereitstellen".**</span><span class="sxs-lookup"><span data-stu-id="f1afe-164">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="f1afe-165">Auf der **angezeigten Seite "Phishingbericht** bereitstellen" wird ein Fortschrittsbericht angezeigt, gefolgt von einer Bestätigung, dass das Add-in bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f1afe-165">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="f1afe-166">Klicken Sie nach dem Lesen der Informationen auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="f1afe-166">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="f1afe-167">Überprüfen Sie **auf der angezeigten** Seite "Add-In ankündigen" die Informationen, und klicken Sie dann auf **"Schließen".**</span><span class="sxs-lookup"><span data-stu-id="f1afe-167">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="f1afe-168">Informationen zur Verwendung des Phishing-Add-Ins "Melden"</span><span class="sxs-lookup"><span data-stu-id="f1afe-168">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="f1afe-169">Personen, denen das Add-In zugewiesen ist, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f1afe-169">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="f1afe-170">In Outlook sieht das Symbol wie hier dargestellt aus:</span><span class="sxs-lookup"><span data-stu-id="f1afe-170">In Outlook, the icon looks like this:</span></span>

  ![Melden eines Phishing-Add-In-Symbols für Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="f1afe-172">In Outlook im Web sieht das Symbol wie hier dargestellt aus:</span><span class="sxs-lookup"><span data-stu-id="f1afe-172">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook im Web Report Phishing-Add-In-Symbol](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="f1afe-174">Überprüfen oder Bearbeiten von Einstellungen für das Phishing-Add-In "Melden"</span><span class="sxs-lookup"><span data-stu-id="f1afe-174">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="f1afe-175">Wechseln Sie im Microsoft 365 Admin Center  zur Seite \> **"Einstellungen-Add-Ins".** Wenn die <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **Add-In-Seite**  nicht angezeigt wird, wechseln \>  \>   Sie oben auf der Seite "Integrierte Apps" zum Link "Integrierte Apps".</span><span class="sxs-lookup"><span data-stu-id="f1afe-175">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="f1afe-176">Suchen Sie das **Phishing-Add-In "Melden",** und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="f1afe-176">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="f1afe-177">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span><span class="sxs-lookup"><span data-stu-id="f1afe-177">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="f1afe-178">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f1afe-178">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="f1afe-179">Anzeigen und Überprüfen von gemeldeten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="f1afe-179">View and review reported messages</span></span>

<span data-ttu-id="f1afe-180">Zum Überprüfen von Nachrichten, die Benutzer an Microsoft melden, haben Sie die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="f1afe-180">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="f1afe-181">Verwenden Sie das Verwaltungsübermittlungsportal.</span><span class="sxs-lookup"><span data-stu-id="f1afe-181">Use the Admin Submissions portal.</span></span> <span data-ttu-id="f1afe-182">Weitere Informationen finden Sie unter [Anzeigen von Benutzerübermittlungen an Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="f1afe-182">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="f1afe-183">Erstellen Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet), um Kopien der gemeldeten Nachrichten zu senden.</span><span class="sxs-lookup"><span data-stu-id="f1afe-183">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="f1afe-184">Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, was Ihre Benutzer an Microsoft melden.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="f1afe-184">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
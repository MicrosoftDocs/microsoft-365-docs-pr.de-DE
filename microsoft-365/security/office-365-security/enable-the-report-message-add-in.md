---
title: Aktivieren des Add-Ins „Nachrichten melden“
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie das Add-in "Berichtsnachricht" für Outlook und Outlook im Internet für einzelne Benutzer oder die gesamte Organisation aktivieren.
ms.openlocfilehash: 0024e8c87ef6326c1df4547349631c4f1fd4cab8
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921576"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="6e9f3-103">Aktivieren des Add-Ins „Nachrichten melden“</span><span class="sxs-lookup"><span data-stu-id="6e9f3-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="6e9f3-104">Wenn Sie ein Administrator in einer Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungen-Portal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="6e9f3-105">Weitere Informationen finden Sie unter [Verwenden der Administrator Übermittlung zum Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="6e9f3-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="6e9f3-106">Das Berichtsnachrichten-Add-in für Outlook und Outlook im Internet (früher bekannt als Outlook Web App) ermöglicht Benutzern das einfache Melden von falsch positiven Ergebnissen (gute e-Mail-Nachrichten als "schlecht" gekennzeichnet) oder von falschen negativen (ungültige e-Mail-Nachrichten) an Microsoft und seine Partner zur Analyse.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="6e9f3-107">Microsoft verwendet diese Übermittlungen, um die Effektivität von e-Mail-Schutztechnologien zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="6e9f3-108">Nehmen wir beispielsweise an, dass Personen viele Nachrichten als Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="6e9f3-109">Diese Informationen werden im [Sicherheits Dashboard](security-dashboard.md) und in anderen Berichten unter Oberflächen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="6e9f3-110">Das Sicherheitsteam Ihrer Organisation kann diese Informationen als Anhaltspunkt dafür verwenden, dass Anti-Phishing-Richtlinien möglicherweise aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="6e9f3-111">Oder wenn Personen viele Nachrichten melden, die als Junk-e-Mail als nicht-Junk mithilfe des Berichtsnachrichten-Add-ins gekennzeichnet wurden, muss das Sicherheitsteam Ihrer Organisation möglicherweise [Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md)anpassen.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="6e9f3-112">Wenn Ihre Organisation [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) oder [Plan 2](office-365-ti.md)verwendet, bietet das Add-in "Berichtsnachricht" außerdem nützliche Informationen zum Überprüfen und Aktualisieren von Sicherheitsrichtlinien, die dem Sicherheitsteam Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="6e9f3-113">Administratoren können das Add-in "Berichtsnachricht" für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="6e9f3-114">Wenn Sie ein einzelner Benutzer sind, können Sie [das Add-in "Berichtsnachricht" für sich selbst aktivieren](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="6e9f3-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="6e9f3-115">Wenn Sie globaler Administrator oder Exchange Online Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie [das Add-in "Berichtsnachricht" für Ihre Organisation aktivieren](#get-and-enable-the-report-message-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="6e9f3-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="6e9f3-116">Das Add-in "Berichtsnachricht" ist jetzt über eine [zentralisierte Bereitstellung](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6e9f3-117">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="6e9f3-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6e9f3-118">Das Add-in "Berichtsnachricht" funktioniert mit den meisten Microsoft 365-Abonnements und den folgenden Produkten:</span><span class="sxs-lookup"><span data-stu-id="6e9f3-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="6e9f3-119">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="6e9f3-119">Outlook on the web</span></span>
  - <span data-ttu-id="6e9f3-120">Outlook 2013 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="6e9f3-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="6e9f3-121">Outlook 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="6e9f3-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="6e9f3-122">Outlook im Lieferumfang von Microsoft 365-Apps für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="6e9f3-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="6e9f3-123">Das Add-in "Berichtsnachricht" steht derzeit nicht zur Verfügung für:</span><span class="sxs-lookup"><span data-stu-id="6e9f3-123">The Report Message add-in is currently not available for:</span></span>

  - <span data-ttu-id="6e9f3-124">Postfächer in lokalen Exchange-Organisationen</span><span class="sxs-lookup"><span data-stu-id="6e9f3-124">Mailboxes in on-premises Exchange organizations</span></span>
  - <span data-ttu-id="6e9f3-125">Gcc-, gcc-High-oder DoD-Abonnements</span><span class="sxs-lookup"><span data-stu-id="6e9f3-125">GCC, GCC HIGH, or DoD subscriptions</span></span>

- <span data-ttu-id="6e9f3-126">Sie können gemeldete Nachrichten so konfigurieren, dass Sie kopiert oder an ein von Ihnen angegebenes Postfach umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="6e9f3-127">Weitere Informationen finden Sie unter [Angeben eines Postfachs für Benutzer Übermittlungen von Spam-und Phishing-Nachrichten in Office 365](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="6e9f3-127">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Office 365](user-submission.md).</span></span>

- <span data-ttu-id="6e9f3-128">Ihr vorhandener Webbrowser sollte mit dem Add-in "Berichtsnachricht" funktionieren.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-128">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="6e9f3-129">Wenn Sie jedoch feststellen, dass das Add-in nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie es mit einem anderen Browser.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="6e9f3-130">Für organisatorische Installationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="6e9f3-131">Weitere Informationen finden Sie unter [bestimmen, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="6e9f3-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="6e9f3-132">Administratoren müssen Mitglied der Rollengruppe "globale Administratoren" sein.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="6e9f3-133">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6e9f3-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="6e9f3-134">Abrufen des Berichtsnachrichten-Add-Ins für sich selbst</span><span class="sxs-lookup"><span data-stu-id="6e9f3-134">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="6e9f3-135">Wechseln Sie zum Microsoft-AppSource <https://appsource.microsoft.com/marketplace/apps> , und suchen Sie nach dem Add-in "Berichtsnachricht".</span><span class="sxs-lookup"><span data-stu-id="6e9f3-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="6e9f3-136">Wechseln Sie zu, um direkt zum Add-in "Berichtsnachricht <https://appsource.microsoft.com/product/office/wa104381180>" zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-136">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="6e9f3-137">Klicken Sie auf **Jetzt abrufen**.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-137">Click **GET IT NOW**.</span></span>

   ![Berichtsnachricht – jetzt abrufen](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="6e9f3-139">Lesen Sie im daraufhin angezeigten Dialogfeld Nutzungsbedingungen und Datenschutzrichtlinie, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-139">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="6e9f3-140">Melden Sie sich mit Ihrem Geschäfts-oder Schulkonto (für geschäftliche Zwecke) oder Ihrem Microsoft-Konto (zur persönlichen Verwendung) an.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-140">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="6e9f3-141">Nachdem das Add-in installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="6e9f3-141">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="6e9f3-142">In Outlook sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="6e9f3-142">In Outlook, the icon looks like this:</span></span>

  ![Add-in-Symbol für Berichtsnachricht für Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="6e9f3-144">In Outlook im Internet sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="6e9f3-144">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook im Add-in-Symbol für den Webbericht-Nachrichtendienst](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="6e9f3-146">Informationen zur Verwendung des Add-Ins finden Sie unter [Verwenden des Berichtsnachrichten-Add-ins](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="6e9f3-146">To learn how to use the add-in, see [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="6e9f3-147">Abrufen und Aktivieren des Berichtsnachrichten-Add-Ins für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="6e9f3-147">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="6e9f3-148">Es kann bis zu 12 Stunden dauern, bis das Add-in in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-148">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="6e9f3-149">Wechseln Sie im Microsoft 365 Admin Center zur Seite **Dienste &-Add-ins** <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, und klicken Sie dann auf **Add-in bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-149">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="6e9f3-151">Überprüfen Sie im angezeigten **neuen Add-in-** Flyout, das angezeigt wird, die Informationen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-151">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="6e9f3-152">Klicken Sie auf der nächsten Seite im **Store auf auswählen**.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-152">On the next page, click **Choose from the Store**.</span></span>

   ![Bereitstelleneiner neuen Add-in-Seite](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="6e9f3-154">Klicken Sie auf der Seite **Add-in auswählen** , die angezeigt wird, auf das **Suchfeld** , geben Sie **Berichtsnachricht**ein, und klicken](../../media/search-icon.png)Sie dann auf Suchsymbol **Suchen** ![.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-154">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="6e9f3-155">Suchen Sie in der Ergebnisliste nach **Berichtnachricht** , und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-155">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Auswählen von Add-in-Suchergebnissen](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="6e9f3-157">Überprüfen Sie im angezeigten Dialogfeld die Informationen zu Lizenzierung und Datenschutz, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-157">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="6e9f3-158">Konfigurieren Sie auf der Seite **Add-in konfigurieren** , die angezeigt wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="6e9f3-158">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="6e9f3-159">**Zugewiesene Benutzer**: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="6e9f3-159">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="6e9f3-160">**Jeder** (Standard)</span><span class="sxs-lookup"><span data-stu-id="6e9f3-160">**Everyone** (default)</span></span>
     - <span data-ttu-id="6e9f3-161">**Bestimmte Benutzer/Gruppen**</span><span class="sxs-lookup"><span data-stu-id="6e9f3-161">**Specific users / groups**</span></span>
     - <span data-ttu-id="6e9f3-162">**Nur ich**</span><span class="sxs-lookup"><span data-stu-id="6e9f3-162">**Just me**</span></span>

   - <span data-ttu-id="6e9f3-163">**Bereitstellungsmethode**: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="6e9f3-163">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="6e9f3-164">**Fixed (Standard)**: das Add-in wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-164">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="6e9f3-165">**Verfügbar**: Benutzer können das Add-in zu **Hause** \> installieren **Get Add-ins** \> **Administrator verwaltet**.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-165">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="6e9f3-166">**Optional**: das Add-in wird automatisch für die angegebenen Benutzer bereitgestellt, aber es kann ausgewählt werden, es zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-166">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Konfigurieren der Add-in-Seite](../../media/configure-add-in.png)

   <span data-ttu-id="6e9f3-168">Wenn Sie fertig sind, klicken Sie auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-168">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="6e9f3-169">Auf der angezeigten Seite **Berichtnachricht bereitstellen** sehen Sie einen Fortschrittsbericht, gefolgt von einer Bestätigung, dass das Add-in bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-169">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="6e9f3-170">Nachdem Sie die Informationen gelesen haben, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-170">After you read the information, click **Next**.</span></span>

   ![Seite "Berichtsnachricht bereitstellen"](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="6e9f3-172">Überprüfen Sie auf der Seite **Add-in kündigen** , die angezeigt wird, die Informationen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-172">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Add-in-Seite ankündigen](../../media/announce-add-in-page.png)

### <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="6e9f3-174">Informationen zur Verwendung des Berichtsnachrichten-Add-ins</span><span class="sxs-lookup"><span data-stu-id="6e9f3-174">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="6e9f3-175">Personen, denen das Add-in zugewiesen ist, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="6e9f3-175">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="6e9f3-176">In Outlook sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="6e9f3-176">In Outlook, the icon looks like this:</span></span>

  ![Add-in-Symbol für Berichtsnachricht für Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="6e9f3-178">In Outlook im Internet sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="6e9f3-178">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook im Add-in-Symbol für den Webbericht-Nachrichtendienst](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="6e9f3-180">Wenn Sie Benutzer über das Add-in "Berichtsnachricht" informieren, fügen Sie einen Link zur [Verwendung des Berichtsnachrichten-Add-ins](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)hinzu.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-180">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

### <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="6e9f3-181">Überprüfen oder Bearbeiten der Einstellungen für das Add-in "Berichtsnachricht"</span><span class="sxs-lookup"><span data-stu-id="6e9f3-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="6e9f3-182">Wechseln Sie im Microsoft 365 Admin Center zur Seite **Dienste &-Add-ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-182">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![Seite "Dienste und Add-Ins" im neuen Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="6e9f3-184">Suchen Sie das Add-in **Berichtsnachricht** , und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-184">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="6e9f3-185">Überprüfen und bearbeiten Sie in der angezeigten Dropdown- **Meldung zum Bearbeiten des Berichtsnachrichten** die Einstellungen entsprechend Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-185">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="6e9f3-186">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6e9f3-186">When you're finished, click **Save**.</span></span>

   ![Einstellungen für das Add-in "Berichtsnachricht"](../../media/EditReportMessageAddIn.png)

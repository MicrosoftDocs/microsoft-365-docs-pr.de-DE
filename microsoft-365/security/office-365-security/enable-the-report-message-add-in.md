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
description: Erfahren Sie, wie Sie das Report Message-Add-In für Outlook und Outlook im Web, für einzelne Benutzer oder die gesamte Organisation aktivieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9b21472736cff2fd0eed7da5495ab6aae597032f
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094855"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="ea4e9-103">Aktivieren des Add-Ins „Nachrichten melden“</span><span class="sxs-lookup"><span data-stu-id="ea4e9-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="ea4e9-104">Wenn Sie ein Administrator in einer Microsoft 365-Organisation mit Exchange Online-Postfächern sind, empfehlen wir die Verwendung des Übermittlungsportals im Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="ea4e9-105">Weitere Informationen finden Sie unter ["Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft ".](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="ea4e9-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="ea4e9-106">Die "Nachricht melden" und "Phishing melden"-Add-Ins für Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) ermöglichen Es Benutzern, falsch positive Ergebnisse (eine gute E-Mail als schlecht markiert) oder falsch negative Ergebnisse (ungültige E-Mails sind zulässig) zur Analyse an Microsoft und seine Partner zu melden.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="ea4e9-107">Microsoft verwendet diese Übermittlungen, um die Effektivität von E-Mail-Schutztechnologien zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="ea4e9-108">Wenn Benutzer beispielsweise viele Nachrichten melden, die mithilfe des Add-Ins "Nachricht melden" als Junk-E-Mail gekennzeichnet wurden, muss das Sicherheitsteam Ihrer Organisation möglicherweise [Antispamrichtlinien anpassen.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ea4e9-108">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="ea4e9-109">Sie können entweder das Add-In "Nachricht melden" oder "Phishing melden" installieren.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-109">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="ea4e9-110">Wenn Ihre Benutzer nur Phishingnachrichten melden sollen, stellen Sie das Phishing-Add-In "Melden" in Ihrer Organisation zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-110">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="ea4e9-111">Weitere Informationen finden Sie unter [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="ea4e9-111">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="ea4e9-112">Das Report Message-Add-In bietet die Möglichkeit, Sowohl Spam- als auch Phishingnachrichten zu melden.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-112">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="ea4e9-113">Administratoren können das Report Message-Add-In für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="ea4e9-114">Wenn Sie ein einzelner Benutzer sind, können Sie das Add-In "Nachricht [melden" für sich selbst aktivieren.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="ea4e9-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="ea4e9-115">Wenn Sie ein globaler Administrator oder Exchange Online-Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie das [Berichtsnachrichten-Add-In für Ihre Organisation aktivieren.](#get-and-enable-the-report-message-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="ea4e9-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="ea4e9-116">Die Berichtsnachricht Add-In jetzt über die zentrale [Bereitstellung verfügbar.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="ea4e9-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ea4e9-117">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="ea4e9-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ea4e9-118">Das Report Message-Add-In funktioniert mit den meisten Microsoft 365-Abonnements und den folgenden Produkten:</span><span class="sxs-lookup"><span data-stu-id="ea4e9-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="ea4e9-119">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="ea4e9-119">Outlook on the web</span></span>
  - <span data-ttu-id="ea4e9-120">Outlook 2013 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="ea4e9-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="ea4e9-121">Outlook 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="ea4e9-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="ea4e9-122">Outlook im Lieferumfang von Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="ea4e9-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="ea4e9-123">Outlook-App für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="ea4e9-123">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="ea4e9-124">Das Report Message-Add-In ist für Postfächer in lokalen Exchange-Organisationen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-124">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="ea4e9-125">Sie können gemeldete Nachrichten so konfigurieren, dass sie kopiert oder an ein von Ihnen festgelegtes Postfach umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-125">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="ea4e9-126">Weitere Informationen finden Sie unter [Richtlinien für Benutzerübermittlungen.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="ea4e9-126">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="ea4e9-127">Ihr vorhandener Webbrowser sollte mit dem Add-In "Nachricht melden" funktionieren.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-127">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="ea4e9-128">Wenn Sie jedoch feststellen, dass das Add-in nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie es in einem anderen Browser.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-128">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="ea4e9-129">Für Organisationsinstallationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-129">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="ea4e9-130">Weitere Informationen finden Sie unter Ermitteln, ob die zentrale Bereitstellung von [Add-Ins für Ihre Organisation funktioniert.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="ea4e9-130">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="ea4e9-131">Administratoren müssen Mitglied der Rollengruppe "Globale Administratoren" sein.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-131">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="ea4e9-132">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ea4e9-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="ea4e9-133">Das Berichtnachrichten-Add-In für sich selbst erhalten</span><span class="sxs-lookup"><span data-stu-id="ea4e9-133">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="ea4e9-134">Wechseln Sie zu Microsoft AppSource, <https://appsource.microsoft.com/marketplace/apps> und suchen Sie nach dem Add-In "Nachricht melden".</span><span class="sxs-lookup"><span data-stu-id="ea4e9-134">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="ea4e9-135">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="ea4e9-135">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="ea4e9-136">Klicken **Sie auf "JETZT GET IT".**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-136">Click **GET IT NOW**.</span></span>

   ![Berichtnachricht – Jetzt erhalten](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="ea4e9-138">Überprüfen Sie im angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="ea4e9-139">Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Firmenkonto (zur geschäftlichen Nutzung) oder Ihrem Microsoft-Konto (zur persönlichen Nutzung) an.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="ea4e9-140">Nachdem das Add-in installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ea4e9-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="ea4e9-141">In Outlook sieht das Symbol wie hier dargestellt aus:</span><span class="sxs-lookup"><span data-stu-id="ea4e9-141">In Outlook, the icon looks like this:</span></span>

  ![Symbol für Das Add-In"-Symbol "Nachricht melden" für Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="ea4e9-143">In Outlook im Web sieht das Symbol wie hier dargestellt aus:</span><span class="sxs-lookup"><span data-stu-id="ea4e9-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook im Web - Add-In-Symbol "Nachricht melden"](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="ea4e9-145">Informationen zur Verwendung des Add-Ins finden Sie unter [Verwenden des Add-Ins](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)"Nachricht melden".</span><span class="sxs-lookup"><span data-stu-id="ea4e9-145">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="ea4e9-146">Get and enable the Report Message add-in for your organization</span><span class="sxs-lookup"><span data-stu-id="ea4e9-146">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="ea4e9-147">Es kann bis zu 12 Stunden dauern, bis das Add-in in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-147">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="ea4e9-148">Wechseln Sie im Microsoft 365 Admin Center  zur Seite \> **"Einstellungen-Add-Ins".** Wenn die <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **Add-In-Seite**  nicht angezeigt wird, wechseln \>  \>   Sie oben auf der Seite "Integrierte Apps" zum Link "Integrierte Apps".</span><span class="sxs-lookup"><span data-stu-id="ea4e9-148">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="ea4e9-149">Wählen Sie oben auf der Seite **"Add-In** bereitstellen" und dann **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-149">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="ea4e9-151">Überprüfen Sie **im angezeigten Flyout** "Neues Add-In bereitstellen" die Informationen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-151">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="ea4e9-152">Klicken Sie auf der nächsten Seite auf **"Aus Store auswählen".**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-152">On the next page, click **Choose from the Store**.</span></span>

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="ea4e9-154">Klicken Sie auf **der angezeigten Seite "Add-In** auswählen" auf das  Suchfeld, **geben** Sie "Nachricht melden" ein, und klicken Sie dann auf das Suchsymbol  ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="ea4e9-154">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="ea4e9-155">Suchen Sie in der Ergebnisliste nach **"Nachricht melden",** und klicken Sie dann auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-155">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Auswählen von Add-In-Suchergebnissen](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="ea4e9-157">Überprüfen Sie im angezeigten Dialogfeld die Lizenzierungs- und Datenschutzinformationen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-157">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="ea4e9-158">Konfigurieren Sie auf der angezeigten Seite **"Add-In** konfigurieren" die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ea4e9-158">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ea4e9-159">**Zugewiesene Benutzer:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="ea4e9-159">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="ea4e9-160">**Jeder** (Standard)</span><span class="sxs-lookup"><span data-stu-id="ea4e9-160">**Everyone** (default)</span></span>
     - <span data-ttu-id="ea4e9-161">**Bestimmte Benutzer/Gruppen**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-161">**Specific users / groups**</span></span>
     - <span data-ttu-id="ea4e9-162">**Nur ich**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-162">**Just me**</span></span>

   - <span data-ttu-id="ea4e9-163">**Bereitstellungsmethode:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="ea4e9-163">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="ea4e9-164">**Fixed (Standard):** Das Add-in wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-164">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="ea4e9-165">**Verfügbar:** Benutzer können das Add-in unter **"Home** \> **Get add-ins** \> **Admin-managed" installieren.**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-165">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="ea4e9-166">**Optional:** Das Add-in wird automatisch für die angegebenen Benutzer bereitgestellt, kann aber entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-166">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Konfigurieren der Add-In-Seite](../../media/configure-add-in.png)

   <span data-ttu-id="ea4e9-168">Klicken Sie nach Abschluss des Abschlusses auf **"Bereitstellen".**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-168">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="ea4e9-169">Auf der **Seite "Nachricht bereitstellen"** wird ein Fortschrittsbericht angezeigt, gefolgt von einer Bestätigung, dass das Add-in bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-169">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="ea4e9-170">Klicken Sie nach dem Lesen der Informationen auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-170">After you read the information, click **Next**.</span></span>

   ![Seite "Berichtnachricht bereitstellen"](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="ea4e9-172">Überprüfen Sie **auf der angezeigten** Seite "Add-In ankündigen" die Informationen, und klicken Sie dann auf **"Schließen".**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-172">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Add-In-Seite ankündigen](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="ea4e9-174">Informationen zur Verwendung des Berichtsnachrichten-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="ea4e9-174">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="ea4e9-175">Personen, denen das Add-In zugewiesen ist, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ea4e9-175">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="ea4e9-176">In Outlook sieht das Symbol wie hier dargestellt aus:</span><span class="sxs-lookup"><span data-stu-id="ea4e9-176">In Outlook, the icon looks like this:</span></span>

  ![Symbol "Nachrichten-Add-In melden" für Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="ea4e9-178">In Outlook im Web sieht das Symbol wie hier dargestellt aus:</span><span class="sxs-lookup"><span data-stu-id="ea4e9-178">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook im Web Report Message Add-in icon](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="ea4e9-180">Wenn Sie Benutzer über das Add-In "Nachricht melden" benachrichtigen, fügen Sie einen Link zum Verwenden des Add-Ins "Nachricht [melden" hinzu.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="ea4e9-180">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="ea4e9-181">Überprüfen oder Bearbeiten von Einstellungen für das Berichtsnachrichten-Add-In</span><span class="sxs-lookup"><span data-stu-id="ea4e9-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="ea4e9-182">Wechseln Sie im Microsoft 365 Admin Center  zur Seite \> **"Einstellungen-Add-Ins".** Wenn die <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **Add-In-Seite**  nicht angezeigt wird, wechseln \>  \>   Sie oben auf der Seite "Integrierte Apps" zum Link "Integrierte Apps".</span><span class="sxs-lookup"><span data-stu-id="ea4e9-182">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Seite Add-Ins Dienste und Dienste im neuen Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="ea4e9-184">Suchen Sie das Add-In **"Nachricht melden",** und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-184">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="ea4e9-185">Überprüfen und **bearbeiten Sie im** angezeigten Flyout "Berichtnachricht bearbeiten" die Einstellungen, die für Ihre Organisation geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-185">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="ea4e9-186">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-186">When you're finished, click **Save**.</span></span>

   ![Einstellungen für das Berichtsnachrichten-Add-In](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="ea4e9-188">Anzeigen und Überprüfen von gemeldeten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="ea4e9-188">View and review reported messages</span></span>

<span data-ttu-id="ea4e9-189">Zum Überprüfen von Nachrichten, die Benutzer an Microsoft melden, haben Sie die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="ea4e9-189">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="ea4e9-190">Verwenden Sie das Verwaltungsübermittlungsportal.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-190">Use the Admin Submissions portal.</span></span> <span data-ttu-id="ea4e9-191">Weitere Informationen finden Sie unter [Anzeigen von Benutzerübermittlungen an Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="ea4e9-191">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="ea4e9-192">Erstellen Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet), um Kopien der gemeldeten Nachrichten zu senden.</span><span class="sxs-lookup"><span data-stu-id="ea4e9-192">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="ea4e9-193">Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, was Ihre Benutzer an Microsoft melden.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="ea4e9-193">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>

---
title: Aktivieren des Add-Ins "Phishingbericht"
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
description: Erfahren Sie, wie Sie das Add-In "Phishing melden" für Outlook und Outlook im Web, für einzelne Benutzer oder ihre gesamte Organisation aktivieren.
ms.openlocfilehash: 44113237274d37aabeda954354182fe4da5aa970
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083416"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="c40c8-103">Aktivieren des Add-Ins „Phishing melden“</span><span class="sxs-lookup"><span data-stu-id="c40c8-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="c40c8-104">Wenn Sie ein Administrator in einer Microsoft 365 Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungsportal im Microsoft 365 Defender-Portal zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c40c8-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="c40c8-105">Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c40c8-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="c40c8-106">Mit den Add-Ins "Nachricht melden" und "Phishing melden" für Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) können Benutzer einfach falsch positive Ergebnisse (als falsch markierte gute E-Mails) oder falsch negative (ungültige E-Mails sind zulässig) an Microsoft und seine Partner zur Analyse melden.</span><span class="sxs-lookup"><span data-stu-id="c40c8-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="c40c8-107">Microsoft verwendet diese Übermittlungen, um die Effektivität von E-Mail-Schutztechnologien zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="c40c8-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="c40c8-108">Nehmen wir beispielsweise an, dass Viele Nachrichten mithilfe des Add-Ins "Phishing melden" gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="c40c8-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="c40c8-109">Diese Informationen werden im [Sicherheitsdashboard](security-dashboard.md) und anderen Berichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c40c8-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="c40c8-110">Das Sicherheitsteam Ihrer Organisation kann diese Informationen als Hinweis darauf verwenden, dass Antiphishingrichtlinien möglicherweise aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c40c8-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="c40c8-111">Sie können entweder das Add-In "Nachricht melden" oder "Phishing melden" installieren.</span><span class="sxs-lookup"><span data-stu-id="c40c8-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="c40c8-112">Wenn Ihre Benutzer sowohl Spam- als auch Phishingnachrichten melden sollen, stellen Sie das Add-In "Nachricht melden" in Ihrer Organisation bereit.</span><span class="sxs-lookup"><span data-stu-id="c40c8-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="c40c8-113">Weitere Informationen finden Sie unter [Aktivieren des Add-Ins "Nachricht melden".](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="c40c8-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="c40c8-114">Das Add-In "Phishing melden" bietet die Möglichkeit, nur Phishingnachrichten zu melden.</span><span class="sxs-lookup"><span data-stu-id="c40c8-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="c40c8-115">Administratoren können das Add-In "Phishing melden" für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.</span><span class="sxs-lookup"><span data-stu-id="c40c8-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="c40c8-116">Wenn Sie ein einzelner Benutzer sind, können Sie [das Add-In "Phishing melden" für sich selbst aktivieren.](#get-the-report-phishing-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="c40c8-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="c40c8-117">Wenn Sie ein globaler Administrator oder ein Exchange Online-Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie [das Add-In "Phishing melden" für Ihre Organisation aktivieren.](#get-and-enable-the-report-phishing-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="c40c8-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="c40c8-118">Der Bericht-Phishing-Add-In ist jetzt über [die zentrale Bereitstellung](../../admin/manage/centralized-deployment-of-add-ins.md)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c40c8-118">The Report Phishing Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c40c8-119">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="c40c8-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c40c8-120">Das Berichtsphishing-Add-In funktioniert mit den meisten Microsoft 365 Abonnements und den folgenden Produkten:</span><span class="sxs-lookup"><span data-stu-id="c40c8-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="c40c8-121">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="c40c8-121">Outlook on the web</span></span>
  - <span data-ttu-id="c40c8-122">Outlook 2013 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="c40c8-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="c40c8-123">Outlook 2016 für Mac oder höher</span><span class="sxs-lookup"><span data-stu-id="c40c8-123">Outlook 2016 for Mac or later</span></span>
  - <span data-ttu-id="c40c8-124">Outlook in Microsoft 365 Apps für Enterprise enthalten</span><span class="sxs-lookup"><span data-stu-id="c40c8-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="c40c8-125">Outlook-App für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="c40c8-125">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="c40c8-126">Das Berichtsphishing-Add-In ist für freigegebene Postfächer oder Postfächer in lokalen Exchange Organisationen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c40c8-126">The Report Phishing add-in is not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="c40c8-127">Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen angegebenes Postfach kopiert oder umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c40c8-127">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="c40c8-128">Weitere Informationen finden Sie unter [Richtlinien für Benutzerübermittlungen.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c40c8-128">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="c40c8-129">Ihr vorhandener Webbrowser sollte mit dem Add-In "Phishing melden" funktionieren.</span><span class="sxs-lookup"><span data-stu-id="c40c8-129">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="c40c8-130">Wenn Sie jedoch feststellen, dass das Add-In nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie einen anderen Browser.</span><span class="sxs-lookup"><span data-stu-id="c40c8-130">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="c40c8-131">Für Organisationsinstallationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c40c8-131">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="c40c8-132">Weitere Informationen finden Sie unter [Ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="c40c8-132">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="c40c8-133">Administratoren müssen Mitglied der Rollengruppe "Globale Administratoren" sein.</span><span class="sxs-lookup"><span data-stu-id="c40c8-133">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="c40c8-134">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="c40c8-134">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="c40c8-135">Abrufen des Berichtsphishing-Add-Ins für sich selbst</span><span class="sxs-lookup"><span data-stu-id="c40c8-135">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="c40c8-136">Wechseln Sie zu Microsoft AppSource, <https://appsource.microsoft.com/marketplace/apps> und suchen Sie nach dem Add-In "Phishing melden".</span><span class="sxs-lookup"><span data-stu-id="c40c8-136">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="c40c8-137">Klicken Sie **auf "JETZT ABRUFEN".**</span><span class="sxs-lookup"><span data-stu-id="c40c8-137">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="c40c8-138">Überprüfen Sie im daraufhin angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="c40c8-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="c40c8-139">Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto (für geschäftliche Zwecke) oder Ihrem Microsoft-Konto (zur persönlichen Verwendung) an.</span><span class="sxs-lookup"><span data-stu-id="c40c8-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="c40c8-140">Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c40c8-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="c40c8-141">In Outlook sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="c40c8-141">In Outlook, the icon looks like this:</span></span>

  ![Add-In-Symbol "Phishing melden" für Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="c40c8-143">In Outlook im Web sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="c40c8-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook im Web Symbol "Phishing-Add-In melden"](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="c40c8-145">Abrufen und Aktivieren des Add-Ins "Phishing melden" für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="c40c8-145">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="c40c8-146">Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c40c8-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="c40c8-147">Wechseln Sie im Microsoft 365 Admin Center zur **Seite Einstellungen** \> **Add-Ins** unter , <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**</span><span class="sxs-lookup"><span data-stu-id="c40c8-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="c40c8-148">Wählen Sie **"Add-In bereitstellen"** oben auf der Seite und dann **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="c40c8-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="c40c8-150">Überprüfen Sie im angezeigten **Flyout "Neues Add-In bereitstellen"** die Informationen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="c40c8-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="c40c8-151">Klicken Sie auf der nächsten Seite auf **"Aus dem Store auswählen".**</span><span class="sxs-lookup"><span data-stu-id="c40c8-151">On the next page, click **Choose from the Store**.</span></span>

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="c40c8-153">Klicken Sie auf der angezeigten **Add-In-Seite "Add-In auswählen"** in das **Suchfeld,** geben **Sie "Phishing melden"** ein, und **klicken** Sie dann auf das ![ ](../../media/search-icon.png) Suchsymbol.</span><span class="sxs-lookup"><span data-stu-id="c40c8-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="c40c8-154">Suchen Sie in der Liste der Ergebnisse **nach "Phishing melden",** und klicken Sie dann auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="c40c8-154">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="c40c8-155">Überprüfen Sie im daraufhin angezeigten Dialogfeld die Lizenz- und Datenschutzinformationen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="c40c8-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="c40c8-156">Konfigurieren Sie auf der angezeigten Seite **"Add-In konfigurieren"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="c40c8-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c40c8-157">**Zugewiesene Benutzer:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="c40c8-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="c40c8-158">**Jeder** (Standard)</span><span class="sxs-lookup"><span data-stu-id="c40c8-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="c40c8-159">**Bestimmte Benutzer/Gruppen**</span><span class="sxs-lookup"><span data-stu-id="c40c8-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="c40c8-160">**Nur ich**</span><span class="sxs-lookup"><span data-stu-id="c40c8-160">**Just me**</span></span>

   - <span data-ttu-id="c40c8-161">**Bereitstellungsmethode:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="c40c8-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="c40c8-162">**Behoben (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="c40c8-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="c40c8-163">**Verfügbar:** Benutzer können das Add-In zu **Hause** \> **installieren. Add-Ins** werden \> **vom Administrator verwaltet.**</span><span class="sxs-lookup"><span data-stu-id="c40c8-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="c40c8-164">**Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann jedoch entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="c40c8-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="c40c8-165">Wenn Sie fertig sind, klicken Sie auf **"Bereitstellen".**</span><span class="sxs-lookup"><span data-stu-id="c40c8-165">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="c40c8-166">Auf der angezeigten Seite **"Bericht Phishing bereitstellen"** wird ein Statusbericht mit anschließender Bestätigung angezeigt, dass das Add-In bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c40c8-166">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="c40c8-167">Klicken Sie nach dem Lesen der Informationen auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="c40c8-167">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="c40c8-168">Überprüfen Sie auf der angezeigten **Add-In-Seite "Ankündigen"** die Informationen, und klicken Sie dann auf **"Schließen".**</span><span class="sxs-lookup"><span data-stu-id="c40c8-168">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="c40c8-169">Erfahren Sie, wie Sie das Add-In "Phishing melden" verwenden</span><span class="sxs-lookup"><span data-stu-id="c40c8-169">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="c40c8-170">Personen, denen das Add-In zugewiesen wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c40c8-170">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="c40c8-171">In Outlook sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="c40c8-171">In Outlook, the icon looks like this:</span></span>

  ![Add-In-Symbol "Phishing melden" für Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="c40c8-173">In Outlook im Web sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="c40c8-173">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook im Webbericht-Phishing-Add-In-Symbol](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="c40c8-175">Überprüfen oder Bearbeiten von Einstellungen für das Add-In "Phishing melden"</span><span class="sxs-lookup"><span data-stu-id="c40c8-175">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="c40c8-176">Wechseln Sie im Microsoft 365 Admin Center zur **Seite Einstellungen** \> **Add-Ins** unter , <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**</span><span class="sxs-lookup"><span data-stu-id="c40c8-176">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="c40c8-177">Suchen Sie das **Add-In "Phishing melden",** und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="c40c8-177">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="c40c8-178">Überprüfen und bearbeiten Sie im angezeigten **Flyout "Bericht Phishing bearbeiten"** einstellungen entsprechend Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="c40c8-178">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="c40c8-179">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c40c8-179">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="c40c8-180">Anzeigen und Überprüfen gemeldeter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="c40c8-180">View and review reported messages</span></span>

<span data-ttu-id="c40c8-181">Zum Überprüfen von Nachrichten, die Benutzer an Microsoft melden, haben Sie die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="c40c8-181">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="c40c8-182">Verwenden Sie das Portal für Administratorübermittlungen.</span><span class="sxs-lookup"><span data-stu-id="c40c8-182">Use the Admin Submissions portal.</span></span> <span data-ttu-id="c40c8-183">Weitere Informationen finden Sie unter [Anzeigen von Benutzerübermittlungen an Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="c40c8-183">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="c40c8-184">Erstellen Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet), um Kopien von gemeldeten Nachrichten zu senden.</span><span class="sxs-lookup"><span data-stu-id="c40c8-184">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="c40c8-185">Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, welche Benutzer An Microsoft melden.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="c40c8-185">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>

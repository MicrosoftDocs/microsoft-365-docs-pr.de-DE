---
title: Aktivieren der Add-Ins "Berichtnachricht" oder "Phishing melden"
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
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
description: Erfahren Sie, wie Sie die Add-Ins "Nachricht melden" oder "Phishing melden" für Outlook und Outlook im Web, für einzelne Benutzer oder für Ihre gesamte Organisation aktivieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7e5136e6d1a118df2e0e91f09a79a9a63e88052
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028583"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="94358-103">Aktivieren der Add-Ins "Berichtnachricht" oder "Phishing melden"</span><span class="sxs-lookup"><span data-stu-id="94358-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="94358-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="94358-104">**Applies to**</span></span>
- [<span data-ttu-id="94358-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="94358-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="94358-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="94358-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="94358-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94358-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="94358-108">Wenn Sie ein Administrator in einer Microsoft 365 Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungsportal in Microsoft 365 Defender zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="94358-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in Microsoft 365 Defender.</span></span> <span data-ttu-id="94358-109">Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="94358-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="94358-110">Mit den Add-Ins "Nachricht melden" und "Phishing melden" für Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) können Benutzer einfach falsch positive Ergebnisse (als falsch markierte gute E-Mails) oder falsch negative (ungültige E-Mails sind zulässig) an Microsoft und seine Partner zur Analyse melden.</span><span class="sxs-lookup"><span data-stu-id="94358-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="94358-111">Microsoft verwendet diese Übermittlungen, um die Effektivität von E-Mail-Schutztechnologien zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="94358-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="94358-112">Nehmen wir beispielsweise an, dass Viele Nachrichten mithilfe des Add-Ins "Phishing melden" gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="94358-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="94358-113">Diese Informationen werden im Sicherheitsdashboard und anderen Berichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="94358-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="94358-114">Das Sicherheitsteam Ihrer Organisation kann diese Informationen als Hinweis darauf verwenden, dass Antiphishingrichtlinien möglicherweise aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="94358-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="94358-115">Sie können entweder das Add-In "Nachricht melden" oder "Phishing melden" installieren.</span><span class="sxs-lookup"><span data-stu-id="94358-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="94358-116">Wenn Ihre Benutzer sowohl Spam- als auch Phishingnachrichten melden sollen, stellen Sie das Add-In "Nachricht melden" in Ihrer Organisation bereit.</span><span class="sxs-lookup"><span data-stu-id="94358-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="94358-117">Weitere Informationen finden Sie unter Aktivieren des Add-Ins "Nachricht melden".</span><span class="sxs-lookup"><span data-stu-id="94358-117">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="94358-118">Das Add-In "Nachricht melden" bietet die Möglichkeit, Sowohl Spam- als auch Phishingnachrichten zu melden.</span><span class="sxs-lookup"><span data-stu-id="94358-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="94358-119">Administratoren können das Add-In "Nachricht melden" für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.</span><span class="sxs-lookup"><span data-stu-id="94358-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="94358-120">Das Add-In "Phishing melden" bietet die Möglichkeit, nur Phishingnachrichten zu melden.</span><span class="sxs-lookup"><span data-stu-id="94358-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="94358-121">Administratoren können das Add-In "Phishing melden" für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.</span><span class="sxs-lookup"><span data-stu-id="94358-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="94358-122">Wenn Sie ein einzelner Benutzer sind, können Sie beide Add-Ins für sich selbst aktivieren.</span><span class="sxs-lookup"><span data-stu-id="94358-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="94358-123">Wenn Sie ein globaler Administrator oder ein Exchange Online-Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie das Add-In "Nachricht melden" und das Add-In "Phishing melden" für Ihre Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="94358-123">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="94358-124">Beide Add-Ins sind jetzt über [die zentrale Bereitstellung](../../admin/manage/centralized-deployment-of-add-ins.md)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="94358-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="94358-125">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="94358-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="94358-126">Sowohl das Add-In "Nachricht melden" als auch das Add-In "Phishing melden" funktionieren mit den meisten Microsoft 365 Abonnements und den folgenden Produkten:</span><span class="sxs-lookup"><span data-stu-id="94358-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>
  - <span data-ttu-id="94358-127">Outlook im Web </span><span class="sxs-lookup"><span data-stu-id="94358-127">Outlook on the web</span></span>
  - <span data-ttu-id="94358-128">Outlook 2013 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="94358-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="94358-129">Outlook 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="94358-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="94358-130">Outlook in Microsoft 365 Apps für Enterprise enthalten</span><span class="sxs-lookup"><span data-stu-id="94358-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="94358-131">Outlook-App für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="94358-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="94358-132">Beide Add-Ins sind nicht für freigegebene Postfächer oder Postfächer in lokalen Exchange Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="94358-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="94358-133">Ihr vorhandener Webbrowser sollte sowohl mit den Add-Ins "Nachricht melden" als auch mit "Phishing melden" funktionieren. Wenn Sie jedoch feststellen, dass das Add-In nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie einen anderen Browser.</span><span class="sxs-lookup"><span data-stu-id="94358-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="94358-134">Für Organisationsinstallationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="94358-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="94358-135">Weitere Informationen finden Sie unter [Ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="94358-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="94358-136">Administratoren müssen Mitglied der Rollengruppe "Globale Administratoren" sein.</span><span class="sxs-lookup"><span data-stu-id="94358-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="94358-137">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="94358-137">For more information, see [Permissions in the Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="94358-138">Weitere Informationen zum Melden einer Nachricht mithilfe des Berichtsnachrichtenfeatures finden Sie unter [Bericht falsch positive und falsch negative Ergebnisse in Outlook](report-false-positives-and-false-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="94358-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94358-139">Es wird nicht empfohlen, die integrierte Berichterstellung in Outlook zu verwenden, da die [Benutzerübermittlungsrichtlinie](./user-submission.md)nicht verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="94358-139">We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="94358-140">Es wird empfohlen, stattdessen das Add-In "Nachricht melden" oder das Add-In "Phishing melden" zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="94358-140">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="94358-141">Abrufen des Add-Ins "Berichtnachricht"</span><span class="sxs-lookup"><span data-stu-id="94358-141">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="94358-142">Abrufen des Add-Ins für sich selbst</span><span class="sxs-lookup"><span data-stu-id="94358-142">Get the add-in for yourself</span></span>

1. <span data-ttu-id="94358-143">Wechseln Sie zu Microsoft AppSource, <https://appsource.microsoft.com/marketplace/apps> und suchen Sie nach dem Add-In "Nachricht melden".</span><span class="sxs-lookup"><span data-stu-id="94358-143">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="94358-144">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="94358-144">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="94358-145">Klicken Sie **auf "JETZT ABRUFEN".**</span><span class="sxs-lookup"><span data-stu-id="94358-145">Click **GET IT NOW**.</span></span>

   ![Nachricht melden – Jetzt abrufen](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="94358-147">Überprüfen Sie im daraufhin angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="94358-147">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="94358-148">Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto (für geschäftliche Zwecke) oder Ihrem Microsoft-Konto (zur persönlichen Verwendung) an.</span><span class="sxs-lookup"><span data-stu-id="94358-148">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="94358-149">Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="94358-149">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="94358-150">In Outlook sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="94358-150">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="94358-151">![Add-In-Symbol "Nachricht melden" für Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="94358-151">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="94358-152">In Outlook im Web sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="94358-152">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="94358-153">![Outlook im Web Add-In-Symbol "Nachricht melden"](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="94358-153">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="94358-154">Abrufen des Add-Ins für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="94358-154">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="94358-155">Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="94358-155">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="94358-156">Wechseln Sie im Microsoft 365 Admin Center zur **Seite Einstellungen** \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="94358-156">In the Microsoft 365 admin center, go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="94358-157">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**</span><span class="sxs-lookup"><span data-stu-id="94358-157">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="94358-158">Wählen Sie **"Add-In bereitstellen"** oben auf der Seite und dann **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="94358-158">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="94358-160">Überprüfen Sie im angezeigten **Flyout "Neues Add-In bereitstellen"** die Informationen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="94358-160">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="94358-161">Klicken Sie auf der nächsten Seite auf **"Aus dem Store auswählen".**</span><span class="sxs-lookup"><span data-stu-id="94358-161">On the next page, click **Choose from the Store**.</span></span>

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="94358-163">Klicken Sie auf der angezeigten **Add-In-Seite "Add-In auswählen"** in das **Suchfeld,** geben Sie **"Meldung melden"** ein, und **klicken** Sie dann auf das ![ ](../../media/search-icon.png) Suchsymbol.</span><span class="sxs-lookup"><span data-stu-id="94358-163">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="94358-164">Suchen Sie in der Liste der Ergebnisse nach **"Berichtnachricht",** und klicken Sie dann auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="94358-164">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Auswählen von Add-In-Suchergebnissen](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="94358-166">Überprüfen Sie im daraufhin angezeigten Dialogfeld die Lizenz- und Datenschutzinformationen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="94358-166">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="94358-167">Konfigurieren Sie auf der angezeigten Seite **"Add-In konfigurieren"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="94358-167">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="94358-168">**Zugewiesene Benutzer:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="94358-168">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="94358-169">**Jeder** (Standard)</span><span class="sxs-lookup"><span data-stu-id="94358-169">**Everyone** (default)</span></span>
     - <span data-ttu-id="94358-170">**Bestimmte Benutzer/Gruppen**</span><span class="sxs-lookup"><span data-stu-id="94358-170">**Specific users / groups**</span></span>
     - <span data-ttu-id="94358-171">**Nur ich**</span><span class="sxs-lookup"><span data-stu-id="94358-171">**Just me**</span></span>

   - <span data-ttu-id="94358-172">**Bereitstellungsmethode:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="94358-172">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="94358-173">**Behoben (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="94358-173">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="94358-174">**Verfügbar:** Benutzer können das Add-In zu **Hause** \> **installieren. Add-Ins** werden \> **vom Administrator verwaltet.**</span><span class="sxs-lookup"><span data-stu-id="94358-174">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="94358-175">**Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann jedoch entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="94358-175">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Add-In-Seite konfigurieren](../../media/configure-add-in.png)

   <span data-ttu-id="94358-177">Wenn Sie fertig sind, klicken Sie auf **"Bereitstellen".**</span><span class="sxs-lookup"><span data-stu-id="94358-177">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="94358-178">Auf der angezeigten Seite **"Berichtnachricht bereitstellen"** wird ein Statusbericht mit anschließender Bestätigung angezeigt, dass das Add-In bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="94358-178">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="94358-179">Klicken Sie nach dem Lesen der Informationen auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="94358-179">After you read the information, click **Next**.</span></span>

   ![Seite "Berichtnachricht bereitstellen"](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="94358-181">Überprüfen Sie auf der angezeigten **Add-In-Seite "Ankündigen"** die Informationen, und klicken Sie dann auf **"Schließen".**</span><span class="sxs-lookup"><span data-stu-id="94358-181">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Add-In-Seite ankündigen](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="94358-183">Überprüfen oder Bearbeiten von Einstellungen für das Add-In "Nachricht melden"</span><span class="sxs-lookup"><span data-stu-id="94358-183">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="94358-184">Wechseln Sie im Microsoft 365 Admin Center zur Seite **Einstellungen** \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="94358-184">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="94358-185">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**</span><span class="sxs-lookup"><span data-stu-id="94358-185">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Seite "Dienste und Add-Ins" im neuen Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="94358-187">Suchen sie das Add-In **"Nachricht melden",** und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="94358-187">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="94358-188">Überprüfen und bearbeiten Sie im angezeigten Flyout **"Berichtnachricht bearbeiten"** die Einstellungen entsprechend Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="94358-188">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="94358-189">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="94358-189">When you're finished, click **Save**.</span></span>

   ![Einstellungen für das Add-In "Nachricht melden"](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="94358-191">Abrufen des Berichtsphishing-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="94358-191">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="94358-192">Abrufen des Add-Ins für sich selbst</span><span class="sxs-lookup"><span data-stu-id="94358-192">Get the add-in for yourself</span></span>

1. <span data-ttu-id="94358-193">Wechseln Sie zu Microsoft AppSource, <https://appsource.microsoft.com/marketplace/apps> und suchen Sie nach dem Add-In "Phishing melden".</span><span class="sxs-lookup"><span data-stu-id="94358-193">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="94358-194">Klicken Sie **auf "JETZT ABRUFEN".**</span><span class="sxs-lookup"><span data-stu-id="94358-194">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="94358-195">Überprüfen Sie im daraufhin angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="94358-195">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="94358-196">Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto (für geschäftliche Zwecke) oder Ihrem Microsoft-Konto (zur persönlichen Verwendung) an.</span><span class="sxs-lookup"><span data-stu-id="94358-196">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="94358-197">Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="94358-197">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="94358-198">In Outlook sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="94358-198">In Outlook, the icon looks like this:</span></span>

  ![Add-In-Symbol "Phishing melden" für Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="94358-200">In Outlook im Web sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="94358-200">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="94358-201">![Outlook im Web Symbol "Phishing-Add-In melden"](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="94358-201">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="94358-202">Abrufen des Add-Ins für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="94358-202">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="94358-203">Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="94358-203">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="94358-204">Wechseln Sie im Microsoft 365 Admin Center zur **Seite Einstellungen** \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="94358-204">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="94358-205">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**</span><span class="sxs-lookup"><span data-stu-id="94358-205">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="94358-206">Wählen Sie **"Add-In bereitstellen"** oben auf der Seite und dann **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="94358-206">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="94358-208">Überprüfen Sie im angezeigten **Flyout "Neues Add-In bereitstellen"** die Informationen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="94358-208">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="94358-209">Klicken Sie auf der nächsten Seite auf **"Aus dem Store auswählen".**</span><span class="sxs-lookup"><span data-stu-id="94358-209">On the next page, click **Choose from the Store**.</span></span>

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="94358-211">Klicken Sie auf der angezeigten **Add-In-Seite "Add-In auswählen"** in das **Suchfeld,** geben **Sie "Phishing melden"** ein, und **klicken** Sie dann auf das ![ ](../../media/search-icon.png) Suchsymbol.</span><span class="sxs-lookup"><span data-stu-id="94358-211">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="94358-212">Suchen Sie in der Liste der Ergebnisse **nach "Phishing melden",** und klicken Sie dann auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="94358-212">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="94358-213">Überprüfen Sie im daraufhin angezeigten Dialogfeld die Lizenz- und Datenschutzinformationen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="94358-213">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="94358-214">Konfigurieren Sie auf der angezeigten Seite **"Add-In konfigurieren"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="94358-214">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="94358-215">**Zugewiesene Benutzer:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="94358-215">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="94358-216">**Jeder** (Standard)</span><span class="sxs-lookup"><span data-stu-id="94358-216">**Everyone** (default)</span></span>
     - <span data-ttu-id="94358-217">**Bestimmte Benutzer/Gruppen**</span><span class="sxs-lookup"><span data-stu-id="94358-217">**Specific users / groups**</span></span>
     - <span data-ttu-id="94358-218">**Nur ich**</span><span class="sxs-lookup"><span data-stu-id="94358-218">**Just me**</span></span>

   - <span data-ttu-id="94358-219">**Bereitstellungsmethode:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="94358-219">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="94358-220">**Behoben (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="94358-220">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="94358-221">**Verfügbar:** Benutzer können das Add-In zu **Hause** \> **installieren. Add-Ins** werden \> **vom Administrator verwaltet.**</span><span class="sxs-lookup"><span data-stu-id="94358-221">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="94358-222">**Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann jedoch entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="94358-222">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="94358-223">Wenn Sie fertig sind, klicken Sie auf **"Bereitstellen".**</span><span class="sxs-lookup"><span data-stu-id="94358-223">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="94358-224">Auf der angezeigten Seite **"Bericht Phishing bereitstellen"** wird ein Statusbericht mit anschließender Bestätigung angezeigt, dass das Add-In bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="94358-224">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="94358-225">Klicken Sie nach dem Lesen der Informationen auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="94358-225">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="94358-226">Überprüfen Sie auf der angezeigten **Add-In-Seite "Ankündigen"** die Informationen, und klicken Sie dann auf **"Schließen".**</span><span class="sxs-lookup"><span data-stu-id="94358-226">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="94358-227">Überprüfen oder Bearbeiten von Einstellungen für das Add-In "Phishing melden"</span><span class="sxs-lookup"><span data-stu-id="94358-227">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="94358-228">Wechseln Sie im Microsoft 365 Admin Center zur **Seite Einstellungen** \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="94358-228">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="94358-229">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**</span><span class="sxs-lookup"><span data-stu-id="94358-229">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="94358-230">Suchen Sie das **Add-In "Phishing melden",** und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="94358-230">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="94358-231">Überprüfen und bearbeiten Sie im angezeigten **Flyout "Bericht Phishing bearbeiten"** einstellungen entsprechend Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="94358-231">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="94358-232">Wenn Sie die gewünschten Einstellungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="94358-232">When you're finished, click **Save**.</span></span>

---
title: Aktivieren der Berichtsnachricht oder der Phishing-Add-Ins melden
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
description: Erfahren Sie, wie Sie die Berichtsnachricht oder die Phishing-Add-Ins für Outlook und Outlook im Web, für einzelne Benutzer oder für Ihre gesamte Organisation aktivieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dc54c5b74697ac41a1d4ff0818467dba662b31f5
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52295819"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="33ba1-103">Aktivieren der Berichtsnachricht oder der Phishing-Add-Ins melden</span><span class="sxs-lookup"><span data-stu-id="33ba1-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="33ba1-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="33ba1-104">**Applies to**</span></span>
- [<span data-ttu-id="33ba1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="33ba1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="33ba1-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="33ba1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="33ba1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33ba1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="33ba1-108">Wenn Sie ein Administrator in einer Microsoft 365 mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="33ba1-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="33ba1-109">Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="33ba1-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="33ba1-110">Die Phishing-Add-Ins "Nachricht melden" und "Phishing melden" für Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) ermöglichen es Benutzern, falsch positive Ergebnisse (gute E-Mails, die als ungültig gekennzeichnet sind) oder falsch negative (ungültige E-Mails sind zulässig) an Microsoft und seine Partner zur Analyse zu melden.</span><span class="sxs-lookup"><span data-stu-id="33ba1-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="33ba1-111">Microsoft verwendet diese Übermittlungen, um die Effektivität von E-Mail-Schutztechnologien zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="33ba1-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="33ba1-112">Angenommen, die Benutzer melden viele Nachrichten mithilfe des Phishing-Add-Ins Melden.</span><span class="sxs-lookup"><span data-stu-id="33ba1-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="33ba1-113">Diese Informationen werden im Sicherheitsdashboard und anderen Berichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33ba1-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="33ba1-114">Das Sicherheitsteam Ihrer Organisation kann diese Informationen als Hinweis darauf verwenden, dass Antiphishingrichtlinien möglicherweise aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="33ba1-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="33ba1-115">Sie können entweder das Add-In "Nachricht melden" oder "Phishing melden" installieren.</span><span class="sxs-lookup"><span data-stu-id="33ba1-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="33ba1-116">Wenn Ihre Benutzer Spam- und Phishingnachrichten melden sollen, stellen Sie das Report Message-Add-In in Ihrer Organisation zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="33ba1-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="33ba1-117">Weitere Informationen finden Sie unter Aktivieren des Berichtsnachrichten-Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="33ba1-117">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="33ba1-118">Das Add-In Report Message bietet die Möglichkeit, Sowohl Spam- als auch Phishingnachrichten zu melden.</span><span class="sxs-lookup"><span data-stu-id="33ba1-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="33ba1-119">Administratoren können das Report Message-Add-In für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.</span><span class="sxs-lookup"><span data-stu-id="33ba1-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="33ba1-120">Das Phishing-Add-In "Phishing melden" bietet die Möglichkeit, nur Phishingnachrichten zu melden.</span><span class="sxs-lookup"><span data-stu-id="33ba1-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="33ba1-121">Administratoren können das Phishing-Add-In melden für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.</span><span class="sxs-lookup"><span data-stu-id="33ba1-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="33ba1-122">Wenn Sie ein einzelner Benutzer sind, können Sie beide Add-Ins für sich selbst aktivieren.</span><span class="sxs-lookup"><span data-stu-id="33ba1-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="33ba1-123">f Sie ein globaler Administrator oder ein Exchange Online-Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie das Add-In Nachricht melden und das Phishing-Add-In melden für Ihre Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="33ba1-123">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="33ba1-124">Beide Add-Ins sind jetzt über die zentrale [Bereitstellung verfügbar.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="33ba1-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="33ba1-125">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="33ba1-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="33ba1-126">Sowohl das Report Message-Add-In als auch das Phishing-Add-In Report funktioniert mit den meisten Microsoft 365 und den folgenden Produkten:</span><span class="sxs-lookup"><span data-stu-id="33ba1-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="33ba1-127">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="33ba1-127">Outlook on the web</span></span>
  - <span data-ttu-id="33ba1-128">Outlook 2013 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="33ba1-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="33ba1-129">Outlook 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="33ba1-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="33ba1-130">Outlook in Microsoft 365 apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="33ba1-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="33ba1-131">Outlook App für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="33ba1-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="33ba1-132">Beide Add-Ins sind nicht für freigegebene Postfächer oder Postfächer in lokalen Organisationen Exchange verfügbar.</span><span class="sxs-lookup"><span data-stu-id="33ba1-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="33ba1-133">Ihr vorhandener Webbrowser sollte sowohl mit den Add-Ins "Nachricht melden" als auch "Phishing melden" funktionieren. Wenn Sie jedoch feststellen, dass das Add-In nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie es mit einem anderen Browser.</span><span class="sxs-lookup"><span data-stu-id="33ba1-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="33ba1-134">Für Organisationsinstallationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="33ba1-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="33ba1-135">Weitere Informationen finden Sie unter [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="33ba1-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="33ba1-136">Administratoren müssen Mitglied der Rollengruppe Globale Administratoren sein.</span><span class="sxs-lookup"><span data-stu-id="33ba1-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="33ba1-137">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="33ba1-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="33ba1-138">Weitere Informationen zum Melden einer Nachricht mithilfe des Berichtsnachrichtenfeatures finden Sie unter Melden falsch positiver und falsch negativer [Outlook](report-false-positives-and-false-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="33ba1-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="33ba1-139">Get the Report Message add-in</span><span class="sxs-lookup"><span data-stu-id="33ba1-139">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="33ba1-140">Das Add-In für sich selbst</span><span class="sxs-lookup"><span data-stu-id="33ba1-140">Get the add-in for yourself</span></span>

1. <span data-ttu-id="33ba1-141">Wechseln Sie zur Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> unter, und suchen Sie nach dem Add-In Nachricht melden.</span><span class="sxs-lookup"><span data-stu-id="33ba1-141">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="33ba1-142">Um direkt zum Add-In "Nachricht melden" zu wechseln, wechseln Sie zu <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="33ba1-142">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="33ba1-143">Klicken Sie **auf JETZT GET IT**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-143">Click **GET IT NOW**.</span></span>

   ![Berichtsnachricht – Jetzt erhalten](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="33ba1-145">Überprüfen Sie im angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-145">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="33ba1-146">Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto (für geschäftliche Nutzung) oder Ihrem Microsoft-Konto (für den persönlichen Gebrauch) an.</span><span class="sxs-lookup"><span data-stu-id="33ba1-146">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="33ba1-147">Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="33ba1-147">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="33ba1-148">In Outlook sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="33ba1-148">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="33ba1-149">![Symbol zum Melden von Nachrichten-Add-Ins für Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="33ba1-149">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="33ba1-150">In Outlook im Web sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="33ba1-150">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="33ba1-151">![Outlook im Web Nachrichten-Add-In-Symbol melden](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="33ba1-151">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="33ba1-152">Das Add-In für Ihre Organisation erhalten</span><span class="sxs-lookup"><span data-stu-id="33ba1-152">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="33ba1-153">Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="33ba1-153">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="33ba1-154">Wechseln Sie Microsoft 365 Admin Center zur Seite Einstellungen  \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="33ba1-154">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="33ba1-155">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** Integrierte \>  \> **Apps-Add-Ins**  oben auf der Seite Integrierte Apps.</span><span class="sxs-lookup"><span data-stu-id="33ba1-155">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="33ba1-156">Wählen **Sie add-in** bereitstellen oben auf der Seite aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="33ba1-156">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="33ba1-158">Überprüfen Sie im angezeigten Flyout Bereitstellen eines neuen **Add-Ins** die Informationen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-158">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="33ba1-159">Klicken Sie auf der nächsten Seite auf **Auswählen aus Store**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-159">On the next page, click **Choose from the Store**.</span></span>

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="33ba1-161">Klicken Sie auf der angezeigten Seite  **Add-In** auswählen in das Feld Suchen, geben Sie **Meldung** melden ein, und klicken Sie dann auf **Suchsymbol** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="33ba1-161">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="33ba1-162">Suchen Sie in der Liste der Ergebnisse nach **Berichtnachricht,** und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-162">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Auswählen von Add-In-Suchergebnissen](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="33ba1-164">Überprüfen Sie im angezeigten Dialogfeld die Lizenzierungs- und Datenschutzinformationen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-164">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="33ba1-165">Konfigurieren Sie auf der angezeigten Seite **Add-In** konfigurieren die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="33ba1-165">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="33ba1-166">**Zugewiesene** Benutzer : Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="33ba1-166">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="33ba1-167">**Jeder** (Standard)</span><span class="sxs-lookup"><span data-stu-id="33ba1-167">**Everyone** (default)</span></span>
     - <span data-ttu-id="33ba1-168">**Bestimmte Benutzer/Gruppen**</span><span class="sxs-lookup"><span data-stu-id="33ba1-168">**Specific users / groups**</span></span>
     - <span data-ttu-id="33ba1-169">**Nur ich**</span><span class="sxs-lookup"><span data-stu-id="33ba1-169">**Just me**</span></span>

   - <span data-ttu-id="33ba1-170">**Bereitstellungsmethode**: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="33ba1-170">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="33ba1-171">**Fixed (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="33ba1-171">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="33ba1-172">**Verfügbar:** Benutzer können das Add-In unter **Home** \> **Get add-ins** \> **Admin-managed installieren.**</span><span class="sxs-lookup"><span data-stu-id="33ba1-172">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="33ba1-173">**Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann es jedoch entfernen.</span><span class="sxs-lookup"><span data-stu-id="33ba1-173">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Konfigurieren der Add-In-Seite](../../media/configure-add-in.png)

   <span data-ttu-id="33ba1-175">Klicken Sie nach Abschluss des Abschlusses auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-175">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="33ba1-176">Auf der **angezeigten** Seite Berichtsnachricht bereitstellen wird ein Fortschrittsbericht angezeigt, gefolgt von der Bestätigung, dass das Add-In bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="33ba1-176">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="33ba1-177">Klicken Sie nach dem Lesen der Informationen auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-177">After you read the information, click **Next**.</span></span>

   ![Seite "Berichtsnachricht bereitstellen"](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="33ba1-179">Überprüfen Sie auf der angezeigten Seite **Add-In** ankündigen die Informationen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-179">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Add-In-Seite ankündigen](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="33ba1-181">Überprüfen oder Bearbeiten von Einstellungen für das Report Message-Add-In</span><span class="sxs-lookup"><span data-stu-id="33ba1-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="33ba1-182">Wechseln Sie Microsoft 365 Admin Center zur Seite Einstellungen  \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="33ba1-182">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="33ba1-183">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** Integrierte \>  \> **Apps-Add-Ins**  oben auf der Seite Integrierte Apps.</span><span class="sxs-lookup"><span data-stu-id="33ba1-183">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Seite "Dienste Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="33ba1-185">Suchen Sie das **Add-In Nachricht** melden, und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="33ba1-185">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="33ba1-186">Überprüfen **und** bearbeiten Sie im angezeigten Flyout Berichtsnachricht bearbeiten die Einstellungen, die für Ihre Organisation geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="33ba1-186">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="33ba1-187">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-187">When you're finished, click **Save**.</span></span>

   ![Einstellungen für das Berichtsnachrichten-Add-In](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="33ba1-189">Das Phishing-Add-In melden</span><span class="sxs-lookup"><span data-stu-id="33ba1-189">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="33ba1-190">Das Add-In für sich selbst</span><span class="sxs-lookup"><span data-stu-id="33ba1-190">Get the add-in for yourself</span></span>

1. <span data-ttu-id="33ba1-191">Wechseln Sie zur Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> unter, und suchen Sie nach dem Phishing-Add-In Melden.</span><span class="sxs-lookup"><span data-stu-id="33ba1-191">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="33ba1-192">Klicken Sie **auf JETZT GET IT**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-192">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="33ba1-193">Überprüfen Sie im angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-193">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="33ba1-194">Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto (für geschäftliche Nutzung) oder Ihrem Microsoft-Konto (für den persönlichen Gebrauch) an.</span><span class="sxs-lookup"><span data-stu-id="33ba1-194">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="33ba1-195">Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="33ba1-195">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="33ba1-196">In Outlook sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="33ba1-196">In Outlook, the icon looks like this:</span></span>

  ![Melden des Phishing-Add-In-Symbols für Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="33ba1-198">In Outlook im Web sieht das Symbol wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="33ba1-198">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="33ba1-199">![Outlook im Web Phishing-Add-In-Symbol melden](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="33ba1-199">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="33ba1-200">Das Add-In für Ihre Organisation erhalten</span><span class="sxs-lookup"><span data-stu-id="33ba1-200">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="33ba1-201">Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="33ba1-201">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="33ba1-202">Wechseln Sie Microsoft 365 Admin Center zur Seite Einstellungen  \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="33ba1-202">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="33ba1-203">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** Integrierte \>  \> **Apps-Add-Ins**  oben auf der Seite Integrierte Apps.</span><span class="sxs-lookup"><span data-stu-id="33ba1-203">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="33ba1-204">Wählen **Sie add-in** bereitstellen oben auf der Seite aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="33ba1-204">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="33ba1-206">Überprüfen Sie im angezeigten Flyout Bereitstellen eines neuen **Add-Ins** die Informationen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-206">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="33ba1-207">Klicken Sie auf der nächsten Seite auf **Auswählen aus Store**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-207">On the next page, click **Choose from the Store**.</span></span>

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="33ba1-209">Klicken Sie auf der angezeigten Seite  **Add-In** auswählen in das Feld Suchen, geben Sie **Phishing** melden ein, und klicken Sie dann auf **Suchsymbol** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="33ba1-209">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="33ba1-210">Suchen Sie in der Liste der Ergebnisse nach **Phishing melden,** und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-210">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="33ba1-211">Überprüfen Sie im angezeigten Dialogfeld die Lizenzierungs- und Datenschutzinformationen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-211">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="33ba1-212">Konfigurieren Sie auf der angezeigten Seite **Add-In** konfigurieren die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="33ba1-212">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="33ba1-213">**Zugewiesene** Benutzer : Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="33ba1-213">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="33ba1-214">**Jeder** (Standard)</span><span class="sxs-lookup"><span data-stu-id="33ba1-214">**Everyone** (default)</span></span>
     - <span data-ttu-id="33ba1-215">**Bestimmte Benutzer/Gruppen**</span><span class="sxs-lookup"><span data-stu-id="33ba1-215">**Specific users / groups**</span></span>
     - <span data-ttu-id="33ba1-216">**Nur ich**</span><span class="sxs-lookup"><span data-stu-id="33ba1-216">**Just me**</span></span>

   - <span data-ttu-id="33ba1-217">**Bereitstellungsmethode**: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="33ba1-217">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="33ba1-218">**Fixed (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="33ba1-218">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="33ba1-219">**Verfügbar:** Benutzer können das Add-In unter **Home** \> **Get add-ins** \> **Admin-managed installieren.**</span><span class="sxs-lookup"><span data-stu-id="33ba1-219">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="33ba1-220">**Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann es jedoch entfernen.</span><span class="sxs-lookup"><span data-stu-id="33ba1-220">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="33ba1-221">Klicken Sie nach Abschluss des Abschlusses auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-221">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="33ba1-222">Auf der **angezeigten Seite Phishingbericht** bereitstellen sehen Sie einen Fortschrittsbericht, gefolgt von einer Bestätigung, dass das Add-In bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="33ba1-222">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="33ba1-223">Klicken Sie nach dem Lesen der Informationen auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-223">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="33ba1-224">Überprüfen Sie auf der angezeigten Seite **Add-In** ankündigen die Informationen, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-224">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="33ba1-225">Überprüfen oder Bearbeiten von Einstellungen für das Phishing-Add-In melden</span><span class="sxs-lookup"><span data-stu-id="33ba1-225">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="33ba1-226">Wechseln Sie Microsoft 365 Admin Center zur Seite Einstellungen  \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="33ba1-226">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="33ba1-227">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** Integrierte \>  \> **Apps-Add-Ins**  oben auf der Seite Integrierte Apps.</span><span class="sxs-lookup"><span data-stu-id="33ba1-227">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="33ba1-228">Suchen Sie das **Phishing-Add-In melden,** und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="33ba1-228">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="33ba1-229">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span><span class="sxs-lookup"><span data-stu-id="33ba1-229">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="33ba1-230">Wenn Sie die gewünschten Einstellungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-230">When you're finished, click **Save**.</span></span>

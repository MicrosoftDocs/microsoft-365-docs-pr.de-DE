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
ms.openlocfilehash: 25c4f7d67fd4fa876544a17df0f4bc1abfd7b3e7
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782933"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="fb213-103">Aktivieren der Add-Ins "Berichtnachricht" oder "Phishing melden"</span><span class="sxs-lookup"><span data-stu-id="fb213-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fb213-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="fb213-104">**Applies to**</span></span>
- [<span data-ttu-id="fb213-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fb213-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="fb213-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="fb213-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="fb213-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fb213-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="fb213-108">Wenn Sie ein Administrator in einer Microsoft 365 Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb213-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="fb213-109">Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="fb213-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="fb213-110">Die Add-Ins "Nachricht melden" und "Phishing melden" für Outlook und Outlook im Web (früher bekannt als Outlook Web App), ermöglichen Es Personen, falsch positive Ergebnisse (als falsch markierte gute E-Mails) oder falsch negative Nachrichten (ungültige E-Mails sind zulässig) an Microsoft und seine Partner zur Analyse zu melden.</span><span class="sxs-lookup"><span data-stu-id="fb213-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="fb213-111">Microsoft verwendet diese Übermittlungen, um die Effektivität von E-Mail-Schutztechnologien zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="fb213-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="fb213-112">Nehmen wir beispielsweise an, dass Viele Nachrichten mithilfe des Add-Ins "Phishing melden" gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="fb213-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="fb213-113">Diese Informationen werden im Sicherheitsdashboard und anderen Berichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb213-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="fb213-114">Das Sicherheitsteam Ihrer Organisation kann diese Informationen als Hinweis darauf verwenden, dass Antiphishingrichtlinien möglicherweise aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="fb213-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="fb213-115">Sie können entweder das Add-In "Nachricht melden" oder "Phishing melden" installieren.</span><span class="sxs-lookup"><span data-stu-id="fb213-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="fb213-116">Wenn Ihre Benutzer sowohl Spam- als auch Phishingnachrichten melden sollen, stellen Sie das Add-In "Nachricht melden" in Ihrer Organisation bereit.</span><span class="sxs-lookup"><span data-stu-id="fb213-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="fb213-117">Weitere Informationen finden Sie unter Aktivieren des Add-Ins "Nachricht melden".</span><span class="sxs-lookup"><span data-stu-id="fb213-117">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="fb213-118">Das Add-In "Nachricht melden" bietet die Möglichkeit, Sowohl Spam- als auch Phishingnachrichten zu melden.</span><span class="sxs-lookup"><span data-stu-id="fb213-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="fb213-119">Administratoren können das Add-In "Nachricht melden" für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.</span><span class="sxs-lookup"><span data-stu-id="fb213-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="fb213-120">Das Add-In "Phishing melden" bietet die Möglichkeit, nur Phishingnachrichten zu melden.</span><span class="sxs-lookup"><span data-stu-id="fb213-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="fb213-121">Administratoren können das Add-In "Phishing melden" für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.</span><span class="sxs-lookup"><span data-stu-id="fb213-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="fb213-122">Wenn Sie ein einzelner Benutzer sind, können Sie beide Add-Ins für sich selbst aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fb213-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="fb213-123">Wenn Sie ein globaler Administrator oder ein Exchange Online-Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie das Add-In "Nachricht melden" und das Add-In "Phishing melden" für Ihre Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fb213-123">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="fb213-124">Beide Add-Ins sind jetzt über [die zentrale Bereitstellung](../../admin/manage/centralized-deployment-of-add-ins.md)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fb213-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fb213-125">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="fb213-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fb213-126">Sowohl das Add-In "Nachricht melden" als auch das Add-In "Phishing melden" funktionieren mit den meisten Microsoft 365 Abonnements und den folgenden Produkten:</span><span class="sxs-lookup"><span data-stu-id="fb213-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="fb213-127">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="fb213-127">Outlook on the web</span></span>
  - <span data-ttu-id="fb213-128">Outlook 2013 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="fb213-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="fb213-129">Outlook 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="fb213-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="fb213-130">Outlook in Microsoft 365-Apps für Enterprise enthalten</span><span class="sxs-lookup"><span data-stu-id="fb213-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="fb213-131">Outlook-App für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="fb213-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="fb213-132">Beide Add-Ins sind nicht für freigegebene Postfächer oder Postfächer in lokalen Exchange Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fb213-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="fb213-133">Ihr vorhandener Webbrowser sollte sowohl mit den Add-Ins "Nachricht melden" als auch mit "Phishing melden" funktionieren. Wenn Sie jedoch feststellen, dass das Add-In nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie einen anderen Browser.</span><span class="sxs-lookup"><span data-stu-id="fb213-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="fb213-134">Für Organisationsinstallationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="fb213-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="fb213-135">Weitere Informationen finden Sie unter [Ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="fb213-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="fb213-136">Administratoren müssen Mitglied der Rollengruppe "Globale Administratoren" sein.</span><span class="sxs-lookup"><span data-stu-id="fb213-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="fb213-137">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fb213-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="fb213-138">Weitere Informationen zum Melden einer Nachricht mithilfe des Berichtsnachrichtenfeatures finden Sie unter [Bericht falsch positive und falsch negative Ergebnisse in Outlook](report-false-positives-and-false-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="fb213-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="fb213-139">Abrufen des Add-Ins "Berichtnachricht"</span><span class="sxs-lookup"><span data-stu-id="fb213-139">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="fb213-140">Abrufen des Add-Ins für sich selbst</span><span class="sxs-lookup"><span data-stu-id="fb213-140">Get the add-in for yourself</span></span>

1. <span data-ttu-id="fb213-141">Wechseln Sie zu Microsoft AppSource, <https://appsource.microsoft.com/marketplace/apps> und suchen Sie nach dem Add-In "Nachricht melden".</span><span class="sxs-lookup"><span data-stu-id="fb213-141">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="fb213-142">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="fb213-142">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="fb213-143">Klicken Sie **auf "JETZT ABRUFEN".**</span><span class="sxs-lookup"><span data-stu-id="fb213-143">Click **GET IT NOW**.</span></span>

   ![Nachricht melden – Jetzt abrufen](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="fb213-145">Überprüfen Sie im daraufhin angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="fb213-145">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="fb213-146">Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto (für geschäftliche Zwecke) oder Ihrem Microsoft-Konto (zur persönlichen Verwendung) an.</span><span class="sxs-lookup"><span data-stu-id="fb213-146">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="fb213-147">Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fb213-147">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="fb213-148">In Outlook sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="fb213-148">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="fb213-149">![Add-In-Symbol "Nachricht melden" für Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="fb213-149">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="fb213-150">In Outlook im Web sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="fb213-150">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="fb213-151">![Outlook im Web-Add-In-Symbol "Nachricht melden"](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="fb213-151">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="fb213-152">Abrufen des Add-Ins für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="fb213-152">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="fb213-153">Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fb213-153">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="fb213-154">Wechseln Sie im Microsoft 365 Admin Center zur Seite **Einstellungen** \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="fb213-154">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="fb213-155">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**</span><span class="sxs-lookup"><span data-stu-id="fb213-155">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="fb213-156">Wählen Sie **"Add-In bereitstellen"** oben auf der Seite und dann **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="fb213-156">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="fb213-158">Überprüfen Sie im angezeigten **Flyout "Neues Add-In bereitstellen"** die Informationen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="fb213-158">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="fb213-159">Klicken Sie auf der nächsten Seite auf **"Aus dem Store auswählen".**</span><span class="sxs-lookup"><span data-stu-id="fb213-159">On the next page, click **Choose from the Store**.</span></span>

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="fb213-161">Klicken Sie auf der angezeigten **Add-In-Seite "Add-In auswählen"** in das **Suchfeld,** geben Sie **"Meldung melden"** ein, und **klicken** Sie dann auf das ![ ](../../media/search-icon.png) Suchsymbol.</span><span class="sxs-lookup"><span data-stu-id="fb213-161">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="fb213-162">Suchen Sie in der Liste der Ergebnisse nach **"Berichtnachricht",** und klicken Sie dann auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="fb213-162">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Auswählen von Add-In-Suchergebnissen](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="fb213-164">Überprüfen Sie im daraufhin angezeigten Dialogfeld die Lizenz- und Datenschutzinformationen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="fb213-164">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="fb213-165">Konfigurieren Sie auf der angezeigten Seite **"Add-In konfigurieren"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="fb213-165">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="fb213-166">**Zugewiesene Benutzer:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="fb213-166">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="fb213-167">**Jeder** (Standard)</span><span class="sxs-lookup"><span data-stu-id="fb213-167">**Everyone** (default)</span></span>
     - <span data-ttu-id="fb213-168">**Bestimmte Benutzer/Gruppen**</span><span class="sxs-lookup"><span data-stu-id="fb213-168">**Specific users / groups**</span></span>
     - <span data-ttu-id="fb213-169">**Nur ich**</span><span class="sxs-lookup"><span data-stu-id="fb213-169">**Just me**</span></span>

   - <span data-ttu-id="fb213-170">**Bereitstellungsmethode:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="fb213-170">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="fb213-171">**Behoben (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="fb213-171">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="fb213-172">**Verfügbar:** Benutzer können das Add-In zu **Hause** \> **installieren. Add-Ins** werden \> **vom Administrator verwaltet.**</span><span class="sxs-lookup"><span data-stu-id="fb213-172">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="fb213-173">**Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann jedoch entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="fb213-173">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Add-In-Seite konfigurieren](../../media/configure-add-in.png)

   <span data-ttu-id="fb213-175">Wenn Sie fertig sind, klicken Sie auf **"Bereitstellen".**</span><span class="sxs-lookup"><span data-stu-id="fb213-175">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="fb213-176">Auf der angezeigten Seite **"Berichtnachricht bereitstellen"** wird ein Statusbericht mit anschließender Bestätigung angezeigt, dass das Add-In bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb213-176">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="fb213-177">Klicken Sie nach dem Lesen der Informationen auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="fb213-177">After you read the information, click **Next**.</span></span>

   ![Seite "Berichtnachricht bereitstellen"](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="fb213-179">Überprüfen Sie auf der angezeigten **Add-In-Seite "Ankündigen"** die Informationen, und klicken Sie dann auf **"Schließen".**</span><span class="sxs-lookup"><span data-stu-id="fb213-179">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Add-In-Seite ankündigen](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="fb213-181">Überprüfen oder Bearbeiten von Einstellungen für das Add-In "Nachricht melden"</span><span class="sxs-lookup"><span data-stu-id="fb213-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="fb213-182">Wechseln Sie im Microsoft 365 Admin Center zur Seite **Einstellungen** \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="fb213-182">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="fb213-183">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**</span><span class="sxs-lookup"><span data-stu-id="fb213-183">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Seite "Dienste und Add-Ins" im neuen Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="fb213-185">Suchen sie das Add-In **"Nachricht melden",** und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="fb213-185">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="fb213-186">Überprüfen und bearbeiten Sie im angezeigten Flyout **"Berichtnachricht bearbeiten"** die Einstellungen entsprechend Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="fb213-186">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="fb213-187">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb213-187">When you're finished, click **Save**.</span></span>

   ![Einstellungen für das Add-In "Nachricht melden"](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="fb213-189">Abrufen des Berichtsphishing-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="fb213-189">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="fb213-190">Abrufen des Add-Ins für sich selbst</span><span class="sxs-lookup"><span data-stu-id="fb213-190">Get the add-in for yourself</span></span>

1. <span data-ttu-id="fb213-191">Wechseln Sie zu Microsoft AppSource, <https://appsource.microsoft.com/marketplace/apps> und suchen Sie nach dem Add-In "Phishing melden".</span><span class="sxs-lookup"><span data-stu-id="fb213-191">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="fb213-192">Klicken Sie **auf "JETZT ABRUFEN".**</span><span class="sxs-lookup"><span data-stu-id="fb213-192">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="fb213-193">Überprüfen Sie im daraufhin angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="fb213-193">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="fb213-194">Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto (für geschäftliche Zwecke) oder Ihrem Microsoft-Konto (zur persönlichen Verwendung) an.</span><span class="sxs-lookup"><span data-stu-id="fb213-194">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="fb213-195">Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fb213-195">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="fb213-196">In Outlook sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="fb213-196">In Outlook, the icon looks like this:</span></span>

  ![Add-In-Symbol "Phishing melden" für Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="fb213-198">In Outlook im Web sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="fb213-198">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="fb213-199">![Outlook im Web-Add-In-Symbol "Phishing melden"](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="fb213-199">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="fb213-200">Abrufen des Add-Ins für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="fb213-200">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="fb213-201">Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fb213-201">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="fb213-202">Wechseln Sie im Microsoft 365 Admin Center zur **Seite Einstellungen** \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="fb213-202">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="fb213-203">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**</span><span class="sxs-lookup"><span data-stu-id="fb213-203">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="fb213-204">Wählen Sie **"Add-In bereitstellen"** oben auf der Seite und dann **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="fb213-204">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="fb213-206">Überprüfen Sie im angezeigten **Flyout "Neues Add-In bereitstellen"** die Informationen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="fb213-206">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="fb213-207">Klicken Sie auf der nächsten Seite auf **"Aus dem Store auswählen".**</span><span class="sxs-lookup"><span data-stu-id="fb213-207">On the next page, click **Choose from the Store**.</span></span>

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="fb213-209">Klicken Sie auf der angezeigten **Add-In-Seite "Add-In auswählen"** in das **Suchfeld,** geben **Sie "Phishing melden"** ein, und **klicken** Sie dann auf das ![ ](../../media/search-icon.png) Suchsymbol.</span><span class="sxs-lookup"><span data-stu-id="fb213-209">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="fb213-210">Suchen Sie in der Liste der Ergebnisse **nach "Phishing melden",** und klicken Sie dann auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="fb213-210">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="fb213-211">Überprüfen Sie im daraufhin angezeigten Dialogfeld die Lizenz- und Datenschutzinformationen, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="fb213-211">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="fb213-212">Konfigurieren Sie auf der angezeigten Seite **"Add-In konfigurieren"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="fb213-212">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="fb213-213">**Zugewiesene Benutzer:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="fb213-213">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="fb213-214">**Jeder** (Standard)</span><span class="sxs-lookup"><span data-stu-id="fb213-214">**Everyone** (default)</span></span>
     - <span data-ttu-id="fb213-215">**Bestimmte Benutzer/Gruppen**</span><span class="sxs-lookup"><span data-stu-id="fb213-215">**Specific users / groups**</span></span>
     - <span data-ttu-id="fb213-216">**Nur ich**</span><span class="sxs-lookup"><span data-stu-id="fb213-216">**Just me**</span></span>

   - <span data-ttu-id="fb213-217">**Bereitstellungsmethode:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="fb213-217">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="fb213-218">**Behoben (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="fb213-218">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="fb213-219">**Verfügbar:** Benutzer können das Add-In zu **Hause** \> **installieren. Add-Ins** werden \> **vom Administrator verwaltet.**</span><span class="sxs-lookup"><span data-stu-id="fb213-219">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="fb213-220">**Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann jedoch entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="fb213-220">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="fb213-221">Wenn Sie fertig sind, klicken Sie auf **"Bereitstellen".**</span><span class="sxs-lookup"><span data-stu-id="fb213-221">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="fb213-222">Auf der angezeigten Seite **"Bericht Phishing bereitstellen"** wird ein Statusbericht mit anschließender Bestätigung angezeigt, dass das Add-In bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb213-222">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="fb213-223">Klicken Sie nach dem Lesen der Informationen auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="fb213-223">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="fb213-224">Überprüfen Sie auf der angezeigten **Add-In-Seite "Ankündigen"** die Informationen, und klicken Sie dann auf **"Schließen".**</span><span class="sxs-lookup"><span data-stu-id="fb213-224">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="fb213-225">Überprüfen oder Bearbeiten von Einstellungen für das Add-In "Phishing melden"</span><span class="sxs-lookup"><span data-stu-id="fb213-225">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="fb213-226">Wechseln Sie im Microsoft 365 Admin Center zur **Seite Einstellungen** \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="fb213-226">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="fb213-227">Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**</span><span class="sxs-lookup"><span data-stu-id="fb213-227">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="fb213-228">Suchen Sie das **Add-In "Phishing melden",** und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="fb213-228">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="fb213-229">Überprüfen und bearbeiten Sie im angezeigten **Flyout "Bericht Phishing bearbeiten"** einstellungen entsprechend Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="fb213-229">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="fb213-230">Wenn Sie die gewünschten Einstellungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fb213-230">When you're finished, click **Save**.</span></span>

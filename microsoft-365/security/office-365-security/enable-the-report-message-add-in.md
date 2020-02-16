---
title: Aktivieren des Berichtsnachrichts-Add-Ins
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
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
ms.openlocfilehash: 94dbe7d9dcd5cf3dc8bd5874550880d813f879f5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42086359"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="d768d-103">Aktivieren des Berichtsnachrichts-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="d768d-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="d768d-104">Das Berichtsnachrichten-Add-in für Outlook und Outlook im Internet ist nicht genau dasselbe wie der [Outlook-Junk-e-Mail-Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), obwohl beide dazu verwendet werden können, e-Mails als Junk-e-Mail, nicht als Junk-oder als Phishing-Versuch zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="d768d-104">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt.</span></span> <span data-ttu-id="d768d-105">Der Unterschied besteht darin, dass das Add-in "Berichtsnachricht" für Outlook und Outlook im Internet Microsoft über falsch klassifizierte e-Mails benachrichtigt, während der Outlook-Junk-e-Mail-Filter zum Organisieren von e-Mail-Nachrichten im Postfach eines Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d768d-105">The difference is, the Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span>

## <a name="overview"></a><span data-ttu-id="d768d-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d768d-106">Overview</span></span>

<span data-ttu-id="d768d-107">Das Berichtsnachrichten-Add-in für Outlook und Outlook im Internet (ehemals Outlook Web App genannt) ermöglicht Benutzern das einfache Melden von vertraulichen oder böswilligen e-Mail-Nachrichten an Microsoft und seine Partner zur Analyse.</span><span class="sxs-lookup"><span data-stu-id="d768d-107">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="d768d-108">Microsoft verwendet diese Übermittlungen, um die Effektivität von e-Mail-Schutztechnologien zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="d768d-108">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="d768d-109">Wenn Ihre Organisation [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) oder [Plan 2](office-365-ti.md)verwendet, bietet das Add-in "Berichtsnachricht" außerdem nützliche Informationen zum Überprüfen und Aktualisieren von Sicherheitsrichtlinien, die dem Sicherheitsteam Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="d768d-109">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="d768d-110">Nehmen wir beispielsweise an, dass Personen viele Nachrichten als Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="d768d-110">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="d768d-111">Diese Informationen werden im [Sicherheits Dashboard](security-dashboard.md) und in anderen Berichten unter Oberflächen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d768d-111">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="d768d-112">Das Sicherheitsteam Ihrer Organisation kann diese Informationen als Anhaltspunkt dafür verwenden, dass Anti-Phishing-Richtlinien möglicherweise aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d768d-112">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="d768d-113">Oder wenn Personen viele Nachrichten melden, die als Junk-e-Mail als nicht-Junk mithilfe des Berichtsnachrichten-Add-ins gekennzeichnet wurden, muss das Sicherheitsteam Ihrer Organisation möglicherweise [Anti-Spam-Richtlinien](configure-the-anti-spam-policies.md)anpassen.</span><span class="sxs-lookup"><span data-stu-id="d768d-113">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

<span data-ttu-id="d768d-114">Das Add-in "Berichtsnachricht" funktioniert mit den meisten Office 365-Abonnements und den folgenden Produkten:</span><span class="sxs-lookup"><span data-stu-id="d768d-114">The Report Message add-in works with most Office 365 subscriptions and the following products:</span></span>

 - <span data-ttu-id="d768d-115">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="d768d-115">Outlook on the web</span></span>
 - <span data-ttu-id="d768d-116">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="d768d-116">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="d768d-117">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d768d-117">Outlook 2016</span></span>
 - <span data-ttu-id="d768d-118">Outlook 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="d768d-118">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="d768d-119">Outlook im Lieferumfang von Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="d768d-119">Outlook included with Office 365 ProPlus</span></span>

<span data-ttu-id="d768d-120">Das Add-in "Berichtsnachricht" steht derzeit nicht zur Verfügung für:</span><span class="sxs-lookup"><span data-stu-id="d768d-120">The Report Message add-in is currently not available for:</span></span>

 - <span data-ttu-id="d768d-121">Postfächer in lokalen Exchange-Organisationen</span><span class="sxs-lookup"><span data-stu-id="d768d-121">Mailboxes in on-premises Exchange organizations</span></span>
 - <span data-ttu-id="d768d-122">Gcc-, gcc-High-oder DoD-Abonnements</span><span class="sxs-lookup"><span data-stu-id="d768d-122">GCC, GCC HIGH, or DoD subscriptions</span></span>

<span data-ttu-id="d768d-123">Ihr vorhandener Webbrowser sollte ausreichen, damit das Add-in "Berichtsnachricht" funktioniert. Wenn Sie jedoch feststellen, dass das Add-in nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie es mit einem anderen Browser.</span><span class="sxs-lookup"><span data-stu-id="d768d-123">Your existing web browser should suffice for the Report Message add-in to work; however, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

<span data-ttu-id="d768d-124">Wenn Sie ein einzelner Benutzer sind, können Sie [das Add-in "Berichtsnachricht" für sich selbst aktivieren](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="d768d-124">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="d768d-125">Wenn Sie ein Office 365 globaler Administrator oder ein Exchange Online Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie [das Add-in "Berichtsnachricht" für Ihre Organisation aktivieren](#get-and-enable-the-report-message-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="d768d-125">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="d768d-126">Das Add-in "Berichtsnachricht" ist jetzt über eine [zentralisierte Bereitstellung](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d768d-126">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="d768d-127">Abrufen des Berichtsnachrichten-Add-Ins für sich selbst</span><span class="sxs-lookup"><span data-stu-id="d768d-127">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="d768d-128">Suchen Sie in [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)nach dem [Add-in "Berichtsnachricht](https://appsource.microsoft.com/product/office/wa104381180)".</span><span class="sxs-lookup"><span data-stu-id="d768d-128">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>

2. <span data-ttu-id="d768d-129">Wählen Sie **get it now**aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-129">Choose **GET IT NOW**.</span></span>

   ![Berichtsnachricht – jetzt abrufen](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="d768d-131">Lesen Sie die Nutzungsbedingungen und Datenschutzrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="d768d-131">Review the terms of use and privacy policy.</span></span> <span data-ttu-id="d768d-132">Wählen Sie dann **Continue** aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-132">Then choose **Continue**.</span></span>

4. <span data-ttu-id="d768d-133">Melden Sie sich bei Office 365 mit Ihrem Geschäfts-oder Schulkonto (für geschäftliche Zwecke) oder Ihrem Microsoft-Konto (zur persönlichen Verwendung) an.</span><span class="sxs-lookup"><span data-stu-id="d768d-133">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="d768d-134">Nachdem das Add-in installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d768d-134">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="d768d-135">In Outlook sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d768d-135">In Outlook, the icon looks like this:</span></span>

  ![Add-in-Symbol für Berichtsnachricht für Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="d768d-137">In Outlook im Internet (früher bekannt als Outlook Web App) sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d768d-137">In Outlook on the web (formerly known as Outlook Web App), the icon looks like this:</span></span>

  ![Outlook im Add-in-Symbol für den Webbericht-Nachrichtendienst](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> <span data-ttu-id="d768d-139">Im nächsten Schritt erfahren Sie, wie Sie [das Add-in "Berichtsnachricht" verwenden](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="d768d-139">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="d768d-140">Abrufen und Aktivieren des Berichtsnachrichten-Add-Ins für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="d768d-140">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d768d-141">Sie müssen ein Office 365 globaler Administrator oder ein Exchange Online Administrator sein, um diese Aufgabe ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="d768d-141">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span> <span data-ttu-id="d768d-142">Darüber hinaus muss Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert sein, um weitere Informationen zu erhalten, siehe [Exchange-Anforderungen (zentralisierte Bereitstellung von Add-Ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="d768d-142">In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

1. <span data-ttu-id="d768d-143">Wechseln Sie zur [Seite Dienste &-Add-ins](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="d768d-143">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span>

   ![Seite "Dienste und Add-Ins" im neuen Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="d768d-145">Wählen Sie **+ Deploy Add-in aus**.</span><span class="sxs-lookup"><span data-stu-id="d768d-145">Choose **+ Deploy Add-in**.</span></span>

   ![Auswählen von "Add-in bereitstellen"](../../media/ServicesAddIns-ChooseDeployAddIn.png)

3. <span data-ttu-id="d768d-147">Überprüfen Sie im **neuen Add-in-** Bildschirm die Informationen, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-147">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span>

   ![Neue Add-in-Details](../../media/NewAddInScreen1.png)

4. <span data-ttu-id="d768d-149">Wählen Sie **Ich möchte ein Add-in aus dem Office Store hinzufügen aus**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="d768d-149">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span>

   ![Ich möchte ein neues Add-in hinzufügen](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="d768d-151">Suchen Sie nach **Berichtsnachricht**, und wählen Sie in der Ergebnisliste neben dem **Add-in "Berichtsnachricht**" die Option **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-151">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span>

   ![Suchen Sie nach Berichtsnachricht, und wählen Sie dann hinzufügen](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="d768d-153">Überprüfen Sie auf dem Bildschirm **Bericht Meldung** die Informationen, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-153">On the **Report Message** screen, review the information, and then choose **Next**.</span></span>

   ![Berichtsnachrichten Details](../../media/ReportMessageAdd-InNewScreen4.png)

7. <span data-ttu-id="d768d-155">Geben Sie die Standardeinstellungen des Benutzers für Outlook an, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="d768d-155">Specify the user default settings for Outlook, and  then choose **Next**.</span></span>

   ![Berichtsnachrichten Standardeinstellungen für Outlook](../../media/ReportMessageOptionsScreen5.png)

8. <span data-ttu-id="d768d-157">Geben Sie an, wer das Add-in "Berichtsnachricht" abruft, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-157">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span>

   ![Wer ruft das Add-in "Berichtsnachricht" ab](../../media/ReportMessageOptionsScreen6.png)

> [!TIP]
> <span data-ttu-id="d768d-159">Es [wird empfohlen, eine Regel einzurichten, um eine Kopie der von Ihren Benutzern gemeldeten e-Mail-Nachrichten zu erhalten](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span><span class="sxs-lookup"><span data-stu-id="d768d-159">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="d768d-160">Je nachdem, was Sie beim Einrichten des Add-Ins (Schritte 7-8 oben) ausgewählt haben, ist das [Add-in "Berichtsnachricht](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) " für Personen in Ihrer Organisation verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d768d-160">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available.</span></span> <span data-ttu-id="d768d-161">Personen in Ihrer Organisation werden die folgenden Symbole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d768d-161">People in your organization will see the following icons:</span></span>

- <span data-ttu-id="d768d-162">In Outlook sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d768d-162">In Outlook, the icon looks like this:</span></span>

  ![Add-in-Symbol für Berichtsnachricht für Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="d768d-164">In Outlook im Internet sieht das Symbol wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d768d-164">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook im Add-in-Symbol für den Webbericht-Nachrichtendienst](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> <span data-ttu-id="d768d-166">Wenn Sie Benutzer über das Add-in "Berichtsnachricht" informieren, fügen Sie einen Link zur [Verwendung des Berichtsnachrichten-Add-ins](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)hinzu.</span><span class="sxs-lookup"><span data-stu-id="d768d-166">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="d768d-167">Einrichten einer Regel zum Abrufen einer Kopie von von Ihren Benutzern gemeldeten e-Mail-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="d768d-167">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d768d-168">Sie müssen ein Exchange Online Administrator sein, um diese Aufgabe ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="d768d-168">You must be an Exchange Online Administrator to perform this task.</span></span>

<span data-ttu-id="d768d-169">Sie können eine Regel einrichten, um eine Kopie der von Benutzern in Ihrer Organisation gemeldeten e-Mail-Nachrichten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d768d-169">You can set up a rule to get a copy of email messages reported by users in your organization.</span></span> <span data-ttu-id="d768d-170">Dies tun Sie, nachdem Sie das Add-in "Berichtsnachricht" für Ihre Organisation heruntergeladen und aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="d768d-170">You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>

1. <span data-ttu-id="d768d-171">Wählen Sie in der Exchange-Verwaltungskonsole **Nachrichtenfluss** \> **Regeln**aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-171">In the Exchange admin center, choose **mail flow** \> **rules**.</span></span>

2. <span data-ttu-id="d768d-172">Wählen **+** \> Sie **neue Regel erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-172">Choose **+** \> **Create a new rule**.</span></span>

3. <span data-ttu-id="d768d-173">Geben Sie im Feld **Name** einen Namen ein, beispielsweise Übermittlungen.</span><span class="sxs-lookup"><span data-stu-id="d768d-173">In the **Name** box, type a name, such as Submissions.</span></span>

4. <span data-ttu-id="d768d-174">Wählen Sie in der Liste **diese Regel anwenden, wenn** **die Option Empfängeradresse enthält...** aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-174">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span>

5. <span data-ttu-id="d768d-175">Klicken Sie im Bildschirm **Wörter oder Ausdrücke angeben** auf Hinzufügen `junk@office365.microsoft.com` , und `phish@office365.microsoft.com`wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-175">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span>

   ![Angeben der Junk-und Phishing-e-Mail-Adressen für die Regel](../../media/018c1833-f336-4333-a45c-f2e8b75cd698.png)

6. <span data-ttu-id="d768d-177">Wählen Sie in der Liste **ausführen die folgende...** die Option **Bcc die Nachricht an...** aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-177">In the **Do the following...** list, choose **Bcc the message to...**.</span></span>

7. <span data-ttu-id="d768d-178">Fügen Sie einen globalen Administrator, Sicherheitsadministrator und/oder Sicherheits Leser hinzu, der eine Kopie jeder e-Mail-Nachricht erhalten soll, die Personen an Microsoft melden, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-178">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span>

   ![Hinzufügen eines globalen oder Sicherheitsadministrators zum Empfangen einer Kopie jeder gemeldeten Nachricht](../../media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)

8. <span data-ttu-id="d768d-180">Wählen Sie **diese Regel mit Schweregrad überwachen**aus, und wählen Sie **Medium**aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-180">Select **Audit this rule with severity level**, and choose **Medium**.</span></span>

9. <span data-ttu-id="d768d-181">Wählen Sie unter **Modus für diese Regel auswählen die**Option **erzwingen**aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-181">Under **Choose a mode for this rule**, choose **Enforce**.</span></span>

   ![Einrichten einer Regel zum Abrufen einer Kopie jeder gemeldeten Nachricht](../../media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)

10. <span data-ttu-id="d768d-183">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-183">Choose **Save**.</span></span>

<span data-ttu-id="d768d-184">Wenn diese Regel erfüllt ist, erhält Ihr globaler Administrator, Sicherheitsadministrator und/oder Sicherheits Leser eine Kopie dieser Nachricht, wenn jemand in Ihrer Organisation eine e-Mail-Nachricht mithilfe des Berichtsnachrichten-Add-ins meldet.</span><span class="sxs-lookup"><span data-stu-id="d768d-184">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message.</span></span> <span data-ttu-id="d768d-185">Diese Informationen können Ihnen das Einrichten oder Anpassen von Richtlinien ermöglichen, beispielsweise Office 365 Richtlinien für [ATP-sichere Links](atp-safe-links.md) oder Ihre [Anti-Spam-](anti-spam-protection.md) Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="d768d-185">This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span>

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="d768d-186">Informationen zur Verwendung des Berichtsnachrichten-Add-ins</span><span class="sxs-lookup"><span data-stu-id="d768d-186">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="d768d-187">Siehe [Verwenden des Berichtsnachrichten-Add-ins](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="d768d-187">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="d768d-188">Überprüfen oder Bearbeiten der Einstellungen für das Add-in "Berichtsnachricht"</span><span class="sxs-lookup"><span data-stu-id="d768d-188">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="d768d-189">Sie können die Standardeinstellungen für das Add-in "Berichtsnachricht" auf der [Seite Dienste &-Add-ins](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)überprüfen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d768d-189">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d768d-190">Sie müssen ein Office 365 globaler Administrator oder ein Exchange Online Administrator sein, um diese Aufgabe ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="d768d-190">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>

1. <span data-ttu-id="d768d-191">Wechseln Sie zur [Seite Dienste &-Add-ins](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="d768d-191">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span>

   ![Seite "Dienste und Add-Ins" im neuen Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="d768d-193">Suchen Sie das Add-in Berichtsnachricht, und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="d768d-193">Find and select the Report Message add-in.</span></span>

   ![Suchen und auswählen des Add-Ins "Berichtsnachricht"](../../media/FindReportMessageAddIn.png)

3. <span data-ttu-id="d768d-195">Überprüfen und bearbeiten Sie auf dem Bildschirm Bericht Meldung die Einstellungen entsprechend Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="d768d-195">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span>

   ![Einstellungen für das Add-in "Berichtsnachricht"](../../media/EditReportMessageAddIn.png)

## <a name="related-topics"></a><span data-ttu-id="d768d-197">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d768d-197">Related topics</span></span>

[<span data-ttu-id="d768d-198">Verwenden des Add-Ins "Berichtsnachricht"</span><span class="sxs-lookup"><span data-stu-id="d768d-198">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

[<span data-ttu-id="d768d-199">Anzeigen von e-Mail-Sicherheits &amp; Berichten im Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d768d-199">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="d768d-200">Anzeigen von Berichten für Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d768d-200">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="d768d-201">Verwenden des Explorers im Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d768d-201">Use Explorer in the Security &amp; Compliance Center</span></span>](threat-explorer.md)

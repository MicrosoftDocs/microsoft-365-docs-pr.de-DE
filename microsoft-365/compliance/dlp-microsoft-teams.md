---
title: Verhinderung von Datenverlust (DLP) und Microsoft Teams.
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Sie können jetzt DLP-Richtlinien auf Microsoft Teams Chats und Kanäle anwenden. Lesen Sie diesen Artikel, um mehr darüber zu erfahren, wie es funktioniert.
ms.openlocfilehash: 9fdce86473dcfbb7ec75b9d371b8782d4141ef57
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572465"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="bba66-104">Verhinderung von Datenverlust (DLP) und Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bba66-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="bba66-105">Vor kurzem wurden Microsoft Teams Chat- und Channel-Nachrichten für Benutzer, die für Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Informationsschutz und -steuerung oder Office 365 Advanced Compliance lizenziert sind, hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bba66-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="bba66-106">Office 365 und Microsoft 365 E3 enthalten DLP-Schutz für SharePoint Online, OneDrive und Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bba66-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="bba66-107">Dies schließt auch Dateien ein, die über Teams freigegeben werden, da Teams SharePoint Online und OneDrive verwendet, um Dateien freizugeben.</span><span class="sxs-lookup"><span data-stu-id="bba66-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="bba66-108">Die Unterstützung für den DLP-Schutz in Teams Chat erfordert E5.</span><span class="sxs-lookup"><span data-stu-id="bba66-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="bba66-109">Weitere Informationen zu den Lizenzierungsanforderungen finden Sie unter [Microsoft 365-Dienste auf Mandantenebene – Leitfaden zur Lizenzierung](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="bba66-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="bba66-110">Übersicht über DLP für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bba66-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="bba66-111">Kürzlich wurden die Funktionen zur Verhinderung von [Datenverlust](dlp-learn-about-dlp.md) um Microsoft Teams Chat- und Kanalnachrichten, **einschließlich Nachrichten über den privaten Kanal**, erweitert.</span><span class="sxs-lookup"><span data-stu-id="bba66-111">Recently, [data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="bba66-112">DLP gilt derzeit nur für die eigentlichen Nachrichten im Chat oder Kanalthread.</span><span class="sxs-lookup"><span data-stu-id="bba66-112">DLP currently applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="bba66-113">Aktivitätsbenachrichtigungen - die eine kurze Nachrichtenvorschau enthalten und basierend auf den Benachrichtigungseinstellungen eines Benutzers angezeigt werden -- sind derzeit **nicht** in Teams DLP enthalten.</span><span class="sxs-lookup"><span data-stu-id="bba66-113">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP at this time.</span></span> <span data-ttu-id="bba66-114">Alle vertraulichen Informationen in dem Teil der Nachricht, der in der Vorschau angezeigt wird, bleiben in der Benachrichtigung sichtbar, auch nachdem die DLP-Richtlinie angewendet und vertrauliche Informationen entfernt wurden, die die Nachricht selbst.</span><span class="sxs-lookup"><span data-stu-id="bba66-114">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

<span data-ttu-id="bba66-115">Wenn Ihre Organisation über DLP verfügt, können Sie jetzt Richtlinien definieren, die verhindern, dass Personen vertrauliche Informationen in einem Microsoft Teams Kanal oder einer Chatsitzung freigeben.</span><span class="sxs-lookup"><span data-stu-id="bba66-115">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="bba66-116">Hier sind einige Beispiele, wie dieser Schutz funktioniert:</span><span class="sxs-lookup"><span data-stu-id="bba66-116">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="bba66-117">**Beispiel 1: Schutz vertraulicher Informationen in Nachrichten**.</span><span class="sxs-lookup"><span data-stu-id="bba66-117">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="bba66-118">Angenommen, jemand versucht, vertrauliche Informationen in einem Teams Chat oder Kanal mit Gästen (externen Benutzern) zu teilen.</span><span class="sxs-lookup"><span data-stu-id="bba66-118">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="bba66-119">Wenn Sie eine DLP-Richtlinie definiert haben, um dies zu verhindern, werden Nachrichten mit vertraulichen Informationen, die an externe Benutzer gesendet werden, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="bba66-119">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="bba66-120">Dies geschieht automatisch und innerhalb von Sekunden, je nachdem, wie Ihre DLP-Richtlinie konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="bba66-120">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bba66-121">DLP für Microsoft Teams blockiert vertrauliche Inhalte, wenn sie für Microsoft Teams Benutzer freigegeben werden, die über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="bba66-121">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="bba66-122">- [Gastzugang](/MicrosoftTeams/guest-access) in Teams und Kanälen; Oder</span><span class="sxs-lookup"><span data-stu-id="bba66-122">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="bba66-123">- [externer Zugriff](/MicrosoftTeams/manage-external-access) in Meetings und Chat-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="bba66-123">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="bba66-124">DLP für externe Chatsitzungen funktioniert nur, wenn sich sowohl der Absender als auch der Empfänger im Teams Nur-Modus befinden und [Microsoft Teams systemeigene Verbund](/microsoftteams/manage-external-access)verwendet.</span><span class="sxs-lookup"><span data-stu-id="bba66-124">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="bba66-125">DLP für Teams blockiert keine Nachrichten im [Interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) mit Skype for Business oder nicht nativen Verbundchatsitzungen.</span><span class="sxs-lookup"><span data-stu-id="bba66-125">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="bba66-126">**Beispiel 2: Schutz vertraulicher Informationen in Dokumenten**.</span><span class="sxs-lookup"><span data-stu-id="bba66-126">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="bba66-127">Angenommen, jemand versucht, ein Dokument für Gäste in einem Microsoft Teams Kanal oder Chat freizugeben, und das Dokument enthält vertrauliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="bba66-127">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="bba66-128">Wenn Sie eine DLP-Richtlinie definiert haben, um dies zu verhindern, wird das Dokument für diese Benutzer nicht geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bba66-128">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="bba66-129">Beachten Sie, dass Ihre DLP-Richtlinie in diesem Fall SharePoint und OneDrive enthalten muss, damit der Schutz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bba66-129">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="bba66-130">(Dies ist ein Beispiel für DLP für SharePoint, das in Microsoft Teams angezeigt wird und daher erfordert, dass Benutzer für Office 365 DLP lizenziert sind (in Office 365 E3 enthalten), benutzermüssen jedoch nicht für Office 365 Advanced Compliance lizenziert werden.)</span><span class="sxs-lookup"><span data-stu-id="bba66-130">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="bba66-131">Richtlinientipps helfen Benutzern bei der Schulung</span><span class="sxs-lookup"><span data-stu-id="bba66-131">Policy tips help educate users</span></span>

<span data-ttu-id="bba66-132">Ähnlich wie DLP in [Exchange, Outlook, Outlook im Web,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web) [SharePoint Online, OneDrive for Business Websites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)und Office [Desktopclients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)funktioniert, werden Richtlinientipps angezeigt, wenn eine Aktion mit einer DLP-Richtlinie in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="bba66-132">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="bba66-133">Hier ist ein Beispiel für einen Richtlinientipp:</span><span class="sxs-lookup"><span data-stu-id="bba66-133">Here's an example of a policy tip:</span></span>

![Blockierte Nachrichtenbenachrichtigung in Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="bba66-135">In diesem Fall hat der Absender versucht, eine Sozialversicherungsnummer in einem Microsoft Teams Kanal zu teilen.</span><span class="sxs-lookup"><span data-stu-id="bba66-135">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="bba66-136">Der Link **Was kann ich tun?** öffnet ein Dialogfeld, das Optionen für den Absender bereitstellt, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="bba66-136">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="bba66-137">Beachten Sie, dass der Absender in diesem Fall die Richtlinie überschreiben oder einen Administrator benachrichtigen kann, sie zu überprüfen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="bba66-137">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Optionen zum Auflösen blockierter Nachrichten](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="bba66-139">In Ihrer Organisation können Sie festlegen, dass Benutzer eine DLP-Richtlinie überschreiben können.</span><span class="sxs-lookup"><span data-stu-id="bba66-139">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="bba66-140">Wenn Sie Ihre DLP-Richtlinien konfigurieren, können Sie die Standardrichtlinientipps verwenden oder Richtlinientipps für Ihre Organisation [anpassen.](#to-customize-policy-tips)</span><span class="sxs-lookup"><span data-stu-id="bba66-140">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="bba66-141">Zurück zu unserem Beispiel, in dem ein Absender eine Sozialversicherungsnummer in einem Teams Kanal geteilt hat, sehen Sie hier Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bba66-141">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bba66-142">![Nachricht blockiert](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="bba66-142">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="bba66-143">Anpassen von Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="bba66-143">To customize policy tips</span></span>

<span data-ttu-id="bba66-144">Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt.</span><span class="sxs-lookup"><span data-stu-id="bba66-144">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="bba66-145">Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="bba66-145">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="bba66-146">Wechseln Sie zum Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="bba66-146">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="bba66-147">Wählen Sie **Data Loss Prevention**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="bba66-147">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="bba66-148">Wählen Sie eine Richtlinie aus, und **wählen** Sie neben **Richtlinieneinstellungen** bearbeiten aus.</span><span class="sxs-lookup"><span data-stu-id="bba66-148">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="bba66-149">Erstellen Sie entweder eine neue Regel, oder bearbeiten Sie eine vorhandene Regel für die Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="bba66-149">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bba66-150">![Bearbeiten einer Regel für eine Richtlinie](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="bba66-150">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="bba66-151">Wählen Sie auf der Registerkarte **Benutzerbenachrichtigungen** die Option **E-Mail-Text anpassen** und/oder **die Textoptionen für Richtlinientipps anpassen** aus.</span><span class="sxs-lookup"><span data-stu-id="bba66-151">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bba66-152">![Anpassen von Benutzerbenachrichtigungen und Richtlinientipps](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="bba66-152">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="bba66-153">Geben Sie den Text an, den Sie für E-Mail-Benachrichtigungen und/oder Richtlinientipps verwenden möchten, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="bba66-153">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="bba66-154">Wählen Sie auf der Registerkarte **Richtlinieneinstellungen** die Option **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="bba66-154">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="bba66-155">Erlauben Sie etwa einer Stunde, bis Ihre Änderungen ihren Weg durch Ihr Rechenzentrum finden und mit Benutzerkonten synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="bba66-155">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="bba66-156">Hinzufügen von Microsoft Teams als Speicherort zu bestehenden DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="bba66-156">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="bba66-157">Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt.</span><span class="sxs-lookup"><span data-stu-id="bba66-157">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="bba66-158">Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="bba66-158">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="bba66-159">Wechseln Sie zum Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="bba66-159">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="bba66-160">Wählen Sie **Data Loss Prevention**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="bba66-160">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="bba66-161">Wählen Sie eine Richtlinie aus, und sehen Sie sich die Werte unter **Standorte** an.</span><span class="sxs-lookup"><span data-stu-id="bba66-161">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="bba66-162">Wenn **Sie Teams Chat- und Kanalnachrichten** sehen, sind Sie alle gesetzt.</span><span class="sxs-lookup"><span data-stu-id="bba66-162">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="bba66-163">Wenn Sie dies nicht tun, klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bba66-163">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bba66-164">![Standorte für vorhandene Richtlinien](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="bba66-164">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="bba66-165">Aktivieren Sie in der Spalte **Status** die Richtlinie für **Teams Chat- und Kanalnachrichten**.</span><span class="sxs-lookup"><span data-stu-id="bba66-165">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bba66-166">![DLP für Teams Chats und Kanäle](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="bba66-166">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="bba66-167">Behalten Sie auf der Registerkarte **Standorte auswählen** die Standardeinstellung aller Konten bei, oder wählen Sie Lassen Sie mich bestimmte **Standorte auswählen.**</span><span class="sxs-lookup"><span data-stu-id="bba66-167">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="bba66-168">Sie können Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="bba66-168">You can specify:</span></span>

    1. <span data-ttu-id="bba66-169">bis zu 1000 Einzelkonten zum Ein- oder Ausschließen</span><span class="sxs-lookup"><span data-stu-id="bba66-169">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="bba66-170">Verteilerlisten und Sicherheitsgruppen einzuschließen oder auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="bba66-170">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="bba66-171">Wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="bba66-171">Then choose **Next**.</span></span>

7. <span data-ttu-id="bba66-172">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bba66-172">Click **Save**.</span></span>

<span data-ttu-id="bba66-173">Erlauben Sie etwa einer Stunde, bis Ihre Änderungen ihren Weg durch Ihr Rechenzentrum finden und mit Benutzerkonten synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="bba66-173">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="bba66-174">Definieren einer neuen DLP-Richtlinie für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bba66-174">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="bba66-175">Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt.</span><span class="sxs-lookup"><span data-stu-id="bba66-175">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="bba66-176">Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="bba66-176">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="bba66-177">Wechseln Sie zum Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="bba66-177">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="bba66-178">Wählen Sie Richtlinie zur Verhinderung von **Datenverlust**  >    >  **+ Erstellen einer Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="bba66-178">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="bba66-179">Wählen Sie eine [Vorlage](data-loss-prevention-policies.md#dlp-policy-templates)aus, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="bba66-179">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="bba66-180">In unserem Beispiel haben wir die Vorlage für personenbezogene Daten daten in den USA ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="bba66-180">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bba66-181">![Datenschutzvorlage für DLP-Richtlinie](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="bba66-181">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="bba66-182">Geben Sie auf der Registerkarte **"Name Ihrer Richtlinie"** einen Namen und eine Beschreibung für die Richtlinie an, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="bba66-182">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="bba66-183">Behalten Sie auf der Registerkarte **Standorte auswählen** die Standardeinstellung aller Konten bei, oder wählen Sie Lassen Sie mich bestimmte **Standorte auswählen.**</span><span class="sxs-lookup"><span data-stu-id="bba66-183">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="bba66-184">Sie können Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="bba66-184">You can specify:</span></span>

    1. <span data-ttu-id="bba66-185">bis zu 1000 Einzelkonten zum Ein- oder Ausschließen</span><span class="sxs-lookup"><span data-stu-id="bba66-185">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="bba66-186">Verteilerlisten und Sicherheitsgruppen einzuschließen oder auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="bba66-186">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="bba66-187">**Dies ist eine öffentliche Vorschaufunktion.**</span><span class="sxs-lookup"><span data-stu-id="bba66-187">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP-Richtlinienspeicherorte](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="bba66-189">Wenn Sie sicherstellen möchten, dass Dokumente, die vertrauliche Informationen enthalten, nicht in Teams unangemessen freigegeben werden, stellen Sie sicher, dass **SharePoint Websites** und **OneDrive Konten** aktiviert sind, zusammen mit **Teams Chat- und Kanalnachrichten**.</span><span class="sxs-lookup"><span data-stu-id="bba66-189">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="bba66-190">Auf der Registerkarte **Richtlinieneinstellungen** unter **Anpassen des Inhaltstyps,** den Sie schützen möchten, behalten Sie die einfachen Standardeinstellungen bei, oder wählen Sie Erweiterte Einstellungen **verwenden** aus, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="bba66-190">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="bba66-191">Wenn Sie erweiterte Einstellungen auswählen, können Sie Regeln für Ihre Richtlinie erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="bba66-191">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="bba66-192">(Um Hilfe hierzu zu erhalten, finden Sie unter [Einfache Einstellungen im Vergleich zu erweiterten Einstellungen](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span><span class="sxs-lookup"><span data-stu-id="bba66-192">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="bba66-193">Überprüfen Sie auf der Registerkarte **Richtlinieneinstellungen** unter **Was möchten Sie tun, wenn wir vertrauliche Informationen erkennen?,** die Einstellungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="bba66-193">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="bba66-194">(Hier können Sie [Standardrichtlinientipps und E-Mail-Benachrichtigungen](use-notifications-and-policy-tips.md)beibehalten oder anpassen.)</span><span class="sxs-lookup"><span data-stu-id="bba66-194">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bba66-195">![DLP-Richtlinieneinstellungen mit Tipps und Benachrichtigungen](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="bba66-195">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="bba66-196">Wenn Sie mit der Überprüfung oder Bearbeitung der Einstellungen fertig sind, wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="bba66-196">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="bba66-197">Wählen Sie auf der Registerkarte **Richtlinieneinstellungen** unter Aktivieren **der Richtlinie oder zuerst testen?**, wählen Sie aus, ob die Richtlinie aktiviert werden soll, testen Sie sie [zuerst](dlp-overview-plan-for-dlp.md#policy-deployment), oder halten Sie sie für den Moment deaktiviert, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="bba66-197">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bba66-198">![Geben Sie an, ob die Richtlinie](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="bba66-198">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="bba66-199">Überprüfen Sie auf der Registerkarte **Überprüfen Ihrer Einstellungen** die Einstellungen für Ihre neue Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="bba66-199">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="bba66-200">Wählen Sie **Bearbeiten** aus, um Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="bba66-200">Choose **Edit** to make changes.</span></span> <span data-ttu-id="bba66-201">Wenn Sie fertig sind, wählen Sie **Erstellen** aus .</span><span class="sxs-lookup"><span data-stu-id="bba66-201">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="bba66-202">Lassen Sie sich etwa eine Stunde Zeit, damit ihre neue Richtlinie ihren Weg durch Ihr Rechenzentrum durchläuft und mit Benutzerkonten synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="bba66-202">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="bba66-203">Verhindern des externen Zugriffs auf vertrauliche Dokumente</span><span class="sxs-lookup"><span data-stu-id="bba66-203">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="bba66-204">Um sicherzustellen, dass SharePoint Dokumente, die vertrauliche Informationen enthalten, von externen Gästen aus SharePoint oder Teams standardmäßig nicht abgerufen werden können, wählen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="bba66-204">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="bba66-205">Sie können sicherstellen, dass Dokumente geschützt sind, bis DLP sie scannt und als sicher zu teilen markiert, indem [Sie neue Dateien standardmäßig als vertraulich markieren.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="bba66-205">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="bba66-206">Empfohlene DLP-Richtlinienstruktur</span><span class="sxs-lookup"><span data-stu-id="bba66-206">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="bba66-207">**Bedingungen:**</span><span class="sxs-lookup"><span data-stu-id="bba66-207">**Conditions**</span></span>
        - <span data-ttu-id="bba66-208">Der Inhalt enthält einen dieser vertraulichen Informationstypen: [Wählen Sie alle, die angewendet wird]</span><span class="sxs-lookup"><span data-stu-id="bba66-208">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        
        - <span data-ttu-id="bba66-209">Inhalte werden von Microsoft 365 mit Personen außerhalb meiner Organisation geteilt</span><span class="sxs-lookup"><span data-stu-id="bba66-209">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="bba66-210">![DLP-Bedingungen zum Erkennen der externen Freigabe sensibler Inhalte](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="bba66-210">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="bba66-211">**Aktionen**</span><span class="sxs-lookup"><span data-stu-id="bba66-211">**Actions**</span></span>
        - <span data-ttu-id="bba66-212">Zugriff auf den Inhalt für externe Benutzer einschränken</span><span class="sxs-lookup"><span data-stu-id="bba66-212">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="bba66-213">Benutzer per E-Mail und mit Richtlinientipps benachrichtigen</span><span class="sxs-lookup"><span data-stu-id="bba66-213">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="bba66-214">Vorfallberichte an den Administrator senden</span><span class="sxs-lookup"><span data-stu-id="bba66-214">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="bba66-215">![DLP-Aktion zum Blockieren der externen Freigabe vertraulicher Inhalte](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="bba66-215">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="bba66-216">DLP-Richtlinie in Aktion, wenn versucht wird, ein Dokument in SharePoint freizugeben, das vertrauliche Informationen für einen externen Gast enthält:</span><span class="sxs-lookup"><span data-stu-id="bba66-216">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bba66-217">![Externe Freigabe blockiert](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="bba66-217">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="bba66-218">DLP-Richtlinie in Aktion, wenn Gast versucht, ein Dokument in Teams mit block external zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="bba66-218">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bba66-219">![Externer Zugriff gesperrt](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="bba66-219">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="bba66-220">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="bba66-220">Related articles</span></span>

[<span data-ttu-id="bba66-221">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="bba66-221">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="bba66-222">Senden von E-Mail-Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="bba66-222">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)

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
description: Sie können jetzt DLP-Richtlinien auf Microsoft Teams-Chats und -Kanäle anwenden. Lesen Sie diesen Artikel, um mehr über die Funktionsweise zu erfahren.
ms.openlocfilehash: 40c55ed486efc75619b514a60b707ac75554953b
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445663"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="ca5ea-104">Verhinderung von Datenverlust (DLP) und Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="ca5ea-105">Funktionen zur Verhinderung von Datenverlust wurden kürzlich zu Microsoft Teams-Chat- und Kanalnachrichten für Benutzer hinzugefügt, die für Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance oder Office 365 Advanced Compliance lizenziert sind.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="ca5ea-106">Office 365 und Microsoft 365 E3 enthalten DLP-Schutz für SharePoint Online, OneDrive und Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="ca5ea-107">Dies umfasst auch Dateien, die über Teams freigegeben werden, da Teams SharePoint Online und OneDrive zum Freigeben von Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="ca5ea-108">Für die Unterstützung des DLP-Schutzes im Teams-Chat ist E5 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="ca5ea-109">Weitere Informationen zu den Lizenzierungsanforderungen finden Sie unter [Microsoft 365-Dienste auf Mandantenebene – Leitfaden zur Lizenzierung](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="ca5ea-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="ca5ea-110">Übersicht über DLP für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca5ea-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="ca5ea-111">Vor kurzem wurden die Funktionen zur Verhinderung von Datenverlust (Data [Loss Prevention,](data-loss-prevention-policies.md) DLP) um Chat- und Kanalnachrichten von Microsoft Teams erweitert, einschließlich **Nachrichten im privaten Kanal.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-111">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ca5ea-112">DLP gilt derzeit nur für die tatsächlichen Nachrichten im Chat- oder Kanalthread.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-112">DLP currently applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="ca5ea-113">Aktivitätsbenachrichtigungen – die eine kurze Nachrichtenvorschau enthalten und basierend  auf den Benachrichtigungseinstellungen eines Benutzers angezeigt werden – sind derzeit nicht in Teams DLP enthalten.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-113">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP at this time.</span></span> <span data-ttu-id="ca5ea-114">Alle vertraulichen Informationen im Teil der Nachricht, der in der Vorschau angezeigt wird, bleiben in der Benachrichtigung sichtbar, auch nachdem die DLP-Richtlinie angewendet und die vertrauliche Inforamtion der Nachricht selbst entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-114">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive inforamtion the message itself.</span></span>

<span data-ttu-id="ca5ea-115">Wenn Ihre Organisation über DLP verfügt, können Sie jetzt Richtlinien definieren, die verhindern, dass Personen vertrauliche Informationen in einem Microsoft Teams-Kanal oder einer Chatsitzung freigeben.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-115">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="ca5ea-116">Hier sind einige Beispiele für die Funktionsweise dieses Schutzes:</span><span class="sxs-lookup"><span data-stu-id="ca5ea-116">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="ca5ea-117">**Beispiel 1: Schützen vertraulicher Informationen in Nachrichten**.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-117">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="ca5ea-118">Angenommen, jemand versucht, vertrauliche Informationen in einem Teams-Chat oder -Kanal mit Gästen (externen Benutzern) zu teilen.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-118">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="ca5ea-119">Wenn Sie eine DLP-Richtlinie definiert haben, um dies zu verhindern, werden Nachrichten mit vertraulichen Informationen, die an externe Benutzer gesendet werden, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-119">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="ca5ea-120">Dies geschieht automatisch und innerhalb von Sekunden, je nach Konfiguration Ihrer DLP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-120">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca5ea-121">DLP für Microsoft Teams blockiert vertrauliche Inhalte, wenn sie für Microsoft Teams-Benutzer freigegeben werden, die über:</span><span class="sxs-lookup"><span data-stu-id="ca5ea-121">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="ca5ea-122">- [Gastzugriff](/MicrosoftTeams/guest-access) in Teams und Kanälen; oder</span><span class="sxs-lookup"><span data-stu-id="ca5ea-122">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="ca5ea-123">- [externer Zugriff](/MicrosoftTeams/manage-external-access) in Besprechungen und Chatsitzungen.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-123">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="ca5ea-124">DLP für externe Chatsitzungen funktioniert nur, wenn sich sowohl der Absender als auch der Empfänger im Modus "Nur Teams" befinden und den systemeigenen [Microsoft Teams-Verbund verwenden.](/microsoftteams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-124">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="ca5ea-125">DLP für Teams blockiert keine Nachrichten [in](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) Interop mit Skype for Business oder nicht nativen Verbundchatsitzungen.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-125">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="ca5ea-126">**Beispiel 2: Schützen vertraulicher Informationen in Dokumenten**.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-126">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="ca5ea-127">Angenommen, jemand versucht, ein Dokument für Gäste in einem Microsoft Teams-Kanal oder -Chat zu teilen, und das Dokument enthält vertrauliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-127">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="ca5ea-128">Wenn Sie eine DLP-Richtlinie definiert haben, um dies zu verhindern, wird das Dokument für diese Benutzer nicht geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-128">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="ca5ea-129">Beachten Sie, dass ihre #A0 in diesem Fall SharePoint und OneDrive enthalten muss, damit der Schutz möglich ist.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-129">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="ca5ea-130">(Dies ist ein Beispiel für DLP für SharePoint, das in Microsoft Teams gezeigt wird und daher erfordert, dass Benutzer für Office 365 DLP (in Office 365 E3 enthalten) lizenziert sind, aber keine Lizenz für Office 365 Advanced Compliance benötigen.)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-130">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="ca5ea-131">Richtlinientipps helfen Bei der Schulung von Benutzern</span><span class="sxs-lookup"><span data-stu-id="ca5ea-131">Policy tips help educate users</span></span>

<span data-ttu-id="ca5ea-132">Ähnlich wie DLP in [Exchange, Outlook, Outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)im Web, [SharePoint Online, OneDrive for #A0](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)und Office-Desktopclients funktioniert, werden Richtlinientipps angezeigt, wenn eine Aktion mit einer #A1 in Konflikt steht. [](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-132">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="ca5ea-133">Hier ist ein Beispiel für einen Richtlinientipp:</span><span class="sxs-lookup"><span data-stu-id="ca5ea-133">Here's an example of a policy tip:</span></span>

![Benachrichtigung über blockierte Nachrichten in Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="ca5ea-135">In diesem Fall hat der Absender versucht, eine Sozialversicherungsnummer in einem Microsoft Teams-Kanal zu teilen.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-135">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="ca5ea-136">Der **Link Was kann ich tun?** öffnet ein Dialogfeld, das Optionen zum Beheben des Problems für den Absender bietet.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-136">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="ca5ea-137">Beachten Sie, dass der Absender in diesem Fall die Richtlinie außer Kraft setzen oder einen Administrator benachrichtigen kann, um die Richtlinie zu überprüfen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-137">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Optionen zum Auflösen blockierter Nachrichten](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="ca5ea-139">In Ihrer Organisation können Sie festlegen, dass Benutzer eine DLP-Richtlinie außer Kraft setzen können.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-139">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="ca5ea-140">Und wenn Sie Ihre DLP-Richtlinien konfigurieren, können Sie die Standardrichtlinientipps verwenden oder [Richtlinientipps](#to-customize-policy-tips) für Ihre Organisation anpassen.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-140">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="ca5ea-141">Kehren Sie zu unserem Beispiel zurück, in dem ein Absender eine Sozialversicherungsnummer in einem Teams-Kanal freigegeben hat, was der Empfänger gesehen hat:</span><span class="sxs-lookup"><span data-stu-id="ca5ea-141">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca5ea-142">![Nachricht blockiert](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-142">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

<span data-ttu-id="ca5ea-143">Der **Link What's this?** öffnet einen [Artikel](data-loss-prevention-policies.md) über DLP-Richtlinien, in dem erläutert wird, warum die Nachricht blockiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-143">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="ca5ea-144">Anpassen von Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="ca5ea-144">To customize policy tips</span></span>

<span data-ttu-id="ca5ea-145">Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-145">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="ca5ea-146">Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="ca5ea-146">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="ca5ea-147">Wechseln Sie zum Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-147">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="ca5ea-148">Wählen **Sie Richtlinie zur Verhinderung von Datenverlust**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-148">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="ca5ea-149">Wählen Sie eine Richtlinie aus, und wählen Sie **neben Richtlinieneinstellungen** bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-149">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="ca5ea-150">Erstellen Sie entweder eine neue Regel, oder bearbeiten Sie eine vorhandene Regel für die Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-150">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca5ea-151">![Bearbeiten einer Regel für eine Richtlinie](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-151">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="ca5ea-152">Wählen Sie **auf der Registerkarte** Benutzerbenachrichtigungen die Option E-Mail-Text **anpassen** und/oder **Richtlinientipptextoptionen** anpassen aus.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-152">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca5ea-153">![Anpassen von Benutzerbenachrichtigungen und Richtlinientipps](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-153">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="ca5ea-154">Geben Sie den Text an, den Sie für E-Mail-Benachrichtigungen und/oder Richtlinientipps verwenden möchten, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-154">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="ca5ea-155">Wählen Sie **auf der** Registerkarte Richtlinieneinstellungen die Option **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-155">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="ca5ea-156">Lassen Sie ungefähr eine Stunde, bis Ihre Änderungen ihren Weg durch Ihr Rechenzentrum und die Synchronisierung mit Benutzerkonten finden.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-156">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="ca5ea-157">Hinzufügen von Microsoft Teams als Speicherort zu bestehenden DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="ca5ea-157">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="ca5ea-158">Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-158">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="ca5ea-159">Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="ca5ea-159">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="ca5ea-160">Wechseln Sie zum Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-160">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="ca5ea-161">Wählen **Sie Richtlinie zur Verhinderung von Datenverlust**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-161">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="ca5ea-162">Wählen Sie eine Richtlinie aus, und sehen Sie sich die Werte unter **Locations an.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-162">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="ca5ea-163">Wenn **Teams-Chat- und Kanalnachrichten angezeigt werden,** sind sie alle festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-163">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="ca5ea-164">Klicken Sie auf Bearbeiten, falls **nicht.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-164">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca5ea-165">![Speicherorte für vorhandene Richtlinien](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-165">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="ca5ea-166">Aktivieren Sie **in der** Spalte Status die Richtlinie für **Teams-Chat- und Kanalnachrichten.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-166">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca5ea-167">![DLP für Teams-Chats und -Kanäle](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-167">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="ca5ea-168">Behalten Sie **auf der** Registerkarte Speicherorte auswählen die Standardeinstellung aller Konten bei, oder wählen Sie Let me choose **specific locations** aus.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-168">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="ca5ea-169">Sie können Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="ca5ea-169">You can specify:</span></span>

    1. <span data-ttu-id="ca5ea-170">Bis zu 1.000 einzelne Konten zum Ein- oder Ausschließen</span><span class="sxs-lookup"><span data-stu-id="ca5ea-170">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="ca5ea-171">Verteilerlisten und Sicherheitsgruppen, die ein- oder ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-171">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="ca5ea-172">**Dies ist ein öffentliches Vorschaufeature.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-172">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="ca5ea-173">Wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-173">Then choose **Next**.</span></span>

7. <span data-ttu-id="ca5ea-174">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-174">Click **Save**.</span></span>

<span data-ttu-id="ca5ea-175">Lassen Sie ungefähr eine Stunde, bis Ihre Änderungen ihren Weg durch Ihr Rechenzentrum und die Synchronisierung mit Benutzerkonten finden.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-175">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="ca5ea-176">Definieren einer neuen DLP-Richtlinie für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca5ea-176">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="ca5ea-177">Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-177">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="ca5ea-178">Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="ca5ea-178">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="ca5ea-179">Wechseln Sie zum Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-179">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="ca5ea-180">Wählen **Sie Richtlinie zur Verhinderung von**  >  **Datenverlust**  >  **+ Erstellen einer Richtlinie aus.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-180">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="ca5ea-181">Wählen Sie [eine Vorlage](data-loss-prevention-policies.md#dlp-policy-templates)aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-181">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="ca5ea-182">In unserem Beispiel haben wir die Vorlage für personenbezogene Daten in den USA ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-182">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca5ea-183">![Datenschutzvorlage für die DLP-Richtlinie](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-183">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="ca5ea-184">Geben Sie **auf der Registerkarte** Name Ihrer Richtlinie einen Namen und eine Beschreibung für die Richtlinie an, und wählen Sie dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-184">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="ca5ea-185">Behalten Sie **auf der** Registerkarte Speicherorte auswählen die Standardeinstellung aller Konten bei, oder wählen Sie Let me choose **specific locations** aus.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-185">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="ca5ea-186">Sie können Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="ca5ea-186">You can specify:</span></span>

    1. <span data-ttu-id="ca5ea-187">Bis zu 1.000 einzelne Konten zum Ein- oder Ausschließen</span><span class="sxs-lookup"><span data-stu-id="ca5ea-187">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="ca5ea-188">Verteilerlisten und Sicherheitsgruppen, die ein- oder ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-188">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="ca5ea-189">**Dies ist ein öffentliches Vorschaufeature.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-189">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Speicherorte von DLP-Richtlinien](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="ca5ea-191">Wenn Sie sicherstellen möchten, dass Dokumente, die vertrauliche Informationen enthalten, nicht unangemessen in Teams freigegeben werden, stellen Sie sicher, dass **#A0** und **#A1** sowie Chat- und Kanalnachrichten von Teams aktiviert **sind.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-191">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="ca5ea-192">Behalten Sie **auf** der Registerkarte Richtlinieneinstellungen unter Anpassen des Zu schützende Inhaltstyps die Standardeinstellungen für einfache Einstellungen bei, oder wählen Sie **Erweiterte** Einstellungen verwenden aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-192">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="ca5ea-193">Wenn Sie erweiterte Einstellungen auswählen, können Sie Regeln für Ihre Richtlinie erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-193">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="ca5ea-194">(Informationen dazu finden Sie unter [Einfache Einstellungen im Vergleich zu erweiterten Einstellungen](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-194">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="ca5ea-195">Überprüfen Sie **auf der** Registerkarte Richtlinieneinstellungen unter Was möchten Sie tun, wenn vertrauliche Informationen erkannt **werden?** die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-195">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="ca5ea-196">(Hier können Sie standardrichtlinientipps [](use-notifications-and-policy-tips.md)und E-Mail-Benachrichtigungen behalten oder anpassen.)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-196">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca5ea-197">![DLP-Richtlinieneinstellungen mit Tipps und Benachrichtigungen](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-197">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="ca5ea-198">Wenn Sie die Einstellungen überprüft oder bearbeitet haben, wählen Sie **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-198">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="ca5ea-199">Wählen  Sie auf der Registerkarte Richtlinieneinstellungen unter Möchten Sie die Richtlinie aktivieren oder dinge zuerst **testen?** [aus,](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)ob die Richtlinie aktiviert werden soll, testen Sie sie zuerst, oder lassen Sie sie vorerst deaktiviert, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-199">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca5ea-200">![Angeben, ob die Richtlinie aktivieren soll](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-200">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="ca5ea-201">Überprüfen Sie **auf der Registerkarte** Einstellungen überprüfen die Einstellungen für Ihre neue Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-201">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="ca5ea-202">Wählen **Sie Bearbeiten** aus, um Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-202">Choose **Edit** to make changes.</span></span> <span data-ttu-id="ca5ea-203">Wenn Sie fertig sind, wählen Sie **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-203">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="ca5ea-204">Lassen Sie ungefähr eine Stunde zu, bis Ihre neue Richtlinie ihren Weg durch Ihr Rechenzentrum durcharbeiten und mit Benutzerkonten synchronisieren kann.</span><span class="sxs-lookup"><span data-stu-id="ca5ea-204">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="ca5ea-205">Verhindern des externen Zugriffs auf vertrauliche Dokumente</span><span class="sxs-lookup"><span data-stu-id="ca5ea-205">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="ca5ea-206">Wählen Sie Folgendes aus, um sicherzustellen, dass auf SharePoint- oder Teams-Dokumente, die vertrauliche Informationen enthalten, standardmäßig nicht von externen Gästen zugegriffen werden kann:</span><span class="sxs-lookup"><span data-stu-id="ca5ea-206">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="ca5ea-207">Sie können sicherstellen, dass Dokumente geschützt sind, bis DLP sie überprüft und als sicher für die Freigabe markiert, indem Sie neue Dateien standardmäßig als [vertraulich kennzeichnen.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-207">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="ca5ea-208">Empfohlene DLP-Richtlinienstruktur</span><span class="sxs-lookup"><span data-stu-id="ca5ea-208">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="ca5ea-209">**Bedingungen:**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-209">**Conditions**</span></span>
        - <span data-ttu-id="ca5ea-210">Inhalt enthält einen der folgenden Typen vertraulicher Informationen: [Alle gilt auswählen]</span><span class="sxs-lookup"><span data-stu-id="ca5ea-210">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        
        - <span data-ttu-id="ca5ea-211">Inhalte werden von Microsoft 365 für Personen außerhalb meiner Organisation freigegeben</span><span class="sxs-lookup"><span data-stu-id="ca5ea-211">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="ca5ea-212">![DLP-Bedingungen zum Erkennen der externen Freigabe vertraulicher Inhalte](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-212">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="ca5ea-213">**Aktionen**</span><span class="sxs-lookup"><span data-stu-id="ca5ea-213">**Actions**</span></span>
        - <span data-ttu-id="ca5ea-214">Zugriff auf den Inhalt für externe Benutzer einschränken</span><span class="sxs-lookup"><span data-stu-id="ca5ea-214">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="ca5ea-215">Benutzer per E-Mail und mit Richtlinientipps benachrichtigen</span><span class="sxs-lookup"><span data-stu-id="ca5ea-215">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="ca5ea-216">Vorfallberichte an den Administrator senden</span><span class="sxs-lookup"><span data-stu-id="ca5ea-216">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="ca5ea-217">![DLP-Aktion zum Blockieren der externen Freigabe vertraulicher Inhalte](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-217">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="ca5ea-218">DLP-Richtlinie in Aktion beim Versuch, ein Dokument in SharePoint zu teilen, das vertrauliche Informationen für einen externen Gast enthält:</span><span class="sxs-lookup"><span data-stu-id="ca5ea-218">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca5ea-219">![Externe Freigabe blockiert](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-219">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="ca5ea-220">DLP-Richtlinie in Aktion, wenn Gast versucht, ein Dokument in Teams mit externem Block zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="ca5ea-220">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca5ea-221">![Externer Zugriff blockiert](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="ca5ea-221">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="ca5ea-222">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="ca5ea-222">Related articles</span></span>

[<span data-ttu-id="ca5ea-223">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="ca5ea-223">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="ca5ea-224">Senden von E-Mail-Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="ca5ea-224">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)

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
description: Microsoft Teams chats and channels supports Data Loss Prevention (DLP) policies.
ms.openlocfilehash: e55bfa34b2495465f573bcede3ebda2308dbbbbc
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583388"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="77bd8-103">Verhinderung von Datenverlust (DLP) und Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77bd8-103">Data loss prevention and Microsoft Teams</span></span>

<span data-ttu-id="77bd8-104">Wenn Ihre Organisation über Verhinderung von Datenverlust (Data Loss Prevention, DLP) verfügt, können Sie Richtlinien definieren, die verhindern, dass Personen vertrauliche Informationen in einem Microsoft Teams oder einer Chatsitzung freigeben.</span><span class="sxs-lookup"><span data-stu-id="77bd8-104">If your organization has data loss prevention (DLP), you can define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="77bd8-105">Hier sind einige Beispiele für die Funktionsweise dieses Schutzes:</span><span class="sxs-lookup"><span data-stu-id="77bd8-105">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="77bd8-106">**Beispiel 1: Schützen vertraulicher Informationen in Nachrichten**.</span><span class="sxs-lookup"><span data-stu-id="77bd8-106">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="77bd8-107">Angenommen, jemand versucht, vertrauliche Informationen in einem Teams oder Kanal mit Gästen (externen Benutzern) zu teilen.</span><span class="sxs-lookup"><span data-stu-id="77bd8-107">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="77bd8-108">Wenn Sie eine DLP-Richtlinie definiert haben, um dies zu verhindern, werden Nachrichten mit vertraulichen Informationen, die an externe Benutzer gesendet werden, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="77bd8-108">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="77bd8-109">Dies geschieht automatisch und innerhalb von Sekunden, je nach Konfiguration Ihrer DLP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="77bd8-109">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="77bd8-110">DLP für Microsoft Teams blockiert vertrauliche Inhalte, wenn sie für Microsoft Teams freigegeben werden, die über:</span><span class="sxs-lookup"><span data-stu-id="77bd8-110">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="77bd8-111">- [Gastzugriff](/MicrosoftTeams/guest-access) in Teams und Kanälen; oder</span><span class="sxs-lookup"><span data-stu-id="77bd8-111">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="77bd8-112">- [externer Zugriff](/MicrosoftTeams/manage-external-access) in Besprechungen und Chatsitzungen.</span><span class="sxs-lookup"><span data-stu-id="77bd8-112">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="77bd8-113">DLP für externe Chatsitzungen funktioniert nur, wenn sich sowohl der Absender als auch der Empfänger im Teams Nur-Modus befinden und Microsoft Teams [systemeigenen Verbund verwenden.](/microsoftteams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="77bd8-113">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="77bd8-114">DLP für Teams blockiert nachrichten nicht in [Interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) mit Skype for Business oder nicht nativen Verbundchatsitzungen.</span><span class="sxs-lookup"><span data-stu-id="77bd8-114">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="77bd8-115">**Beispiel 2: Schützen vertraulicher Informationen in Dokumenten**.</span><span class="sxs-lookup"><span data-stu-id="77bd8-115">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="77bd8-116">Angenommen, jemand versucht, ein Dokument für Gäste in einem Microsoft Teams oder Chat zu teilen, und das Dokument enthält vertrauliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="77bd8-116">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="77bd8-117">Wenn Sie eine DLP-Richtlinie definiert haben, um dies zu verhindern, wird das Dokument für diese Benutzer nicht geöffnet.</span><span class="sxs-lookup"><span data-stu-id="77bd8-117">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="77bd8-118">Ihre DLP-Richtlinie muss SharePoint und OneDrive einschließen, damit ein Schutz besteht.</span><span class="sxs-lookup"><span data-stu-id="77bd8-118">Your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="77bd8-119">Dies ist ein Beispiel für DLP für SharePoint, das in Microsoft Teams gezeigt wird und daher erfordert, dass Benutzer für Office 365 DLP (in Office 365 E3 enthalten) lizenziert sind, jedoch keine Lizenz für Office 365 Advanced Compliance.)</span><span class="sxs-lookup"><span data-stu-id="77bd8-119">This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="dlp-licensing-for-microsoft-teams"></a><span data-ttu-id="77bd8-120">DLP-Lizenzierung für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77bd8-120">DLP Licensing for Microsoft Teams</span></span>

<span data-ttu-id="77bd8-121">[Die Funktionen zur Verhinderung von](dlp-learn-about-dlp.md) Datenverlust wurden um Microsoft Teams Chat- und Kanalnachrichten erweitert, einschließlich nachrichten für private **Kanäle** für:</span><span class="sxs-lookup"><span data-stu-id="77bd8-121">[Data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages** for:</span></span>

- <span data-ttu-id="77bd8-122">Office 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="77bd8-122">Office 365 E5/A5</span></span>
- <span data-ttu-id="77bd8-123">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="77bd8-123">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="77bd8-124">Microsoft 365 A5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="77bd8-124">Microsoft 365 Information Protection and Governance</span></span>
- <span data-ttu-id="77bd8-125">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="77bd8-125">Office 365 Advanced Compliance</span></span>

<span data-ttu-id="77bd8-126">Office 365 und Microsoft 365 E3 enthalten DLP-Schutz für SharePoint Online, OneDrive und Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="77bd8-126">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="77bd8-127">Dies umfasst auch Dateien, die über Teams freigegeben werden, Teams SharePoint Online und OneDrive zum Freigeben von Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="77bd8-127">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>

<span data-ttu-id="77bd8-128">Für die Unterstützung des DLP-Schutzes in Teams Chat ist E5 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77bd8-128">Support for DLP protection in Teams Chat requires E5.</span></span>

<span data-ttu-id="77bd8-129">Weitere Informationen zu den Lizenzierungsanforderungen finden Sie unter [Microsoft 365-Dienste auf Mandantenebene – Leitfaden zur Lizenzierung](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="77bd8-129">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77bd8-130">DLP gilt nur für die tatsächlichen Nachrichten im Chat- oder Kanalthread.</span><span class="sxs-lookup"><span data-stu-id="77bd8-130">DLP applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="77bd8-131">Aktivitätsbenachrichtigungen – die eine kurze Nachrichtenvorschau enthalten und basierend  auf den Benachrichtigungseinstellungen eines Benutzers angezeigt werden – sind nicht in Teams DLP enthalten.</span><span class="sxs-lookup"><span data-stu-id="77bd8-131">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP.</span></span> <span data-ttu-id="77bd8-132">Alle vertraulichen Informationen im Teil der Nachricht, der in der Vorschau angezeigt wird, bleiben in der Benachrichtigung sichtbar, auch nachdem die DLP-Richtlinie angewendet und vertrauliche Informationen entfernt wurde, die die Nachricht selbst enthält.</span><span class="sxs-lookup"><span data-stu-id="77bd8-132">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

## <a name="scope-of-dlp-protection"></a><span data-ttu-id="77bd8-133">Umfang des DLP-Schutzes</span><span class="sxs-lookup"><span data-stu-id="77bd8-133">Scope of DLP protection</span></span>

<span data-ttu-id="77bd8-134">Der DLP-Schutz wird unterschiedlich auf Teams angewendet.</span><span class="sxs-lookup"><span data-stu-id="77bd8-134">DLP protection are applied differently to Teams entities.</span></span>

|<span data-ttu-id="77bd8-135">Benutzerkonten/Gruppen/Liste</span><span class="sxs-lookup"><span data-stu-id="77bd8-135">User Accounts/Groups/List</span></span>  |<span data-ttu-id="77bd8-136">Teams Entität</span><span class="sxs-lookup"><span data-stu-id="77bd8-136">Teams Entity</span></span> |<span data-ttu-id="77bd8-137">Verfügbarer DLP-Schutz</span><span class="sxs-lookup"><span data-stu-id="77bd8-137">DLP protection available</span></span>|
|---------|---------|---------|
|<span data-ttu-id="77bd8-138">einzelne Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="77bd8-138">individual user accounts</span></span>     |<span data-ttu-id="77bd8-139">1:1/n-Chats</span><span class="sxs-lookup"><span data-stu-id="77bd8-139">1:1/n chats</span></span>         |<span data-ttu-id="77bd8-140">ja</span><span class="sxs-lookup"><span data-stu-id="77bd8-140">yes</span></span>         |
|     |<span data-ttu-id="77bd8-141">Allgemeine Chats</span><span class="sxs-lookup"><span data-stu-id="77bd8-141">general chats</span></span>         |<span data-ttu-id="77bd8-142">nein</span><span class="sxs-lookup"><span data-stu-id="77bd8-142">no</span></span>         |
|     |<span data-ttu-id="77bd8-143">Freigegebene Kanäle</span><span class="sxs-lookup"><span data-stu-id="77bd8-143">shared channels</span></span>         |<span data-ttu-id="77bd8-144">nein</span><span class="sxs-lookup"><span data-stu-id="77bd8-144">no</span></span>         |
|     |<span data-ttu-id="77bd8-145">Private Kanäle</span><span class="sxs-lookup"><span data-stu-id="77bd8-145">private channels</span></span>         |<span data-ttu-id="77bd8-146">ja</span><span class="sxs-lookup"><span data-stu-id="77bd8-146">yes</span></span>         |
|<span data-ttu-id="77bd8-147">Sicherheitsgruppen/Verteilerlisten</span><span class="sxs-lookup"><span data-stu-id="77bd8-147">security groups/distribution lists</span></span>  | <span data-ttu-id="77bd8-148">1:1/n-Chats</span><span class="sxs-lookup"><span data-stu-id="77bd8-148">1:1/n chats</span></span>         |<span data-ttu-id="77bd8-149">ja</span><span class="sxs-lookup"><span data-stu-id="77bd8-149">yes</span></span>         |
|     |<span data-ttu-id="77bd8-150">Allgemeine Chats</span><span class="sxs-lookup"><span data-stu-id="77bd8-150">general chats</span></span>         |<span data-ttu-id="77bd8-151">nein</span><span class="sxs-lookup"><span data-stu-id="77bd8-151">no</span></span>         |
|     |<span data-ttu-id="77bd8-152">Freigegebene Kanäle</span><span class="sxs-lookup"><span data-stu-id="77bd8-152">shared channels</span></span>         |<span data-ttu-id="77bd8-153">nein</span><span class="sxs-lookup"><span data-stu-id="77bd8-153">no</span></span>      |
|     |<span data-ttu-id="77bd8-154">Private Kanäle</span><span class="sxs-lookup"><span data-stu-id="77bd8-154">private channels</span></span>         |<span data-ttu-id="77bd8-155">ja</span><span class="sxs-lookup"><span data-stu-id="77bd8-155">yes</span></span>        |
|<span data-ttu-id="77bd8-156">Microsoft 365 Gruppe</span><span class="sxs-lookup"><span data-stu-id="77bd8-156">Microsoft 365 group</span></span>    |<span data-ttu-id="77bd8-157">1:1/n-Chats</span><span class="sxs-lookup"><span data-stu-id="77bd8-157">1:1/n chats</span></span>          |<span data-ttu-id="77bd8-158">nein</span><span class="sxs-lookup"><span data-stu-id="77bd8-158">no</span></span>         |
|     |<span data-ttu-id="77bd8-159">Allgemeine Chats</span><span class="sxs-lookup"><span data-stu-id="77bd8-159">general chats</span></span>          |<span data-ttu-id="77bd8-160">ja</span><span class="sxs-lookup"><span data-stu-id="77bd8-160">yes</span></span>        |
|     |<span data-ttu-id="77bd8-161">Freigegebene Kanäle</span><span class="sxs-lookup"><span data-stu-id="77bd8-161">shared channels</span></span>|<span data-ttu-id="77bd8-162">ja</span><span class="sxs-lookup"><span data-stu-id="77bd8-162">yes</span></span> |
|     |<span data-ttu-id="77bd8-163">Private Kanäle</span><span class="sxs-lookup"><span data-stu-id="77bd8-163">private channels</span></span>|<span data-ttu-id="77bd8-164">nein</span><span class="sxs-lookup"><span data-stu-id="77bd8-164">no</span></span>| 


## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="77bd8-165">Richtlinientipps helfen Bei der Schulung von Benutzern</span><span class="sxs-lookup"><span data-stu-id="77bd8-165">Policy tips help educate users</span></span>

<span data-ttu-id="77bd8-166">Ähnlich wie DLP in [Exchange,Outlook, Outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)im Web, [SharePoint Online, OneDrive for Business-Websites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)und Office-Desktopclients [](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)funktioniert, werden Richtlinientipps angezeigt, wenn eine Aktion mit einer DLP-Richtlinie ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="77bd8-166">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action triggers with a DLP policy.</span></span> <span data-ttu-id="77bd8-167">Hier ist ein Beispiel für einen Richtlinientipp:</span><span class="sxs-lookup"><span data-stu-id="77bd8-167">Here's an example of a policy tip:</span></span>

![Benachrichtigung über blockierte Nachrichten in Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="77bd8-169">Hier hat der Absender versucht, eine Sozialversicherungsnummer in einem Microsoft Teams teilen.</span><span class="sxs-lookup"><span data-stu-id="77bd8-169">Here, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="77bd8-170">Der **Link Was kann ich tun?** öffnet ein Dialogfeld, das Optionen zum Beheben des Problems für den Absender bietet.</span><span class="sxs-lookup"><span data-stu-id="77bd8-170">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="77bd8-171">Beachten Sie, dass der Absender die Richtlinie außer Kraft setzen oder einen Administrator benachrichtigen kann, um sie zu überprüfen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="77bd8-171">Notice that, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Optionen zum Auflösen blockierter Nachrichten](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="77bd8-173">In Ihrer Organisation können Sie festlegen, dass Benutzer eine DLP-Richtlinie außer Kraft setzen können.</span><span class="sxs-lookup"><span data-stu-id="77bd8-173">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="77bd8-174">Wenn Sie Ihre DLP-Richtlinien konfigurieren, können Sie die Standardrichtlinientipps verwenden oder [Richtlinientipps](#to-customize-policy-tips) für Ihre Organisation anpassen.</span><span class="sxs-lookup"><span data-stu-id="77bd8-174">When you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="77bd8-175">Kehren Sie zu unserem Beispiel zurück, in dem ein Absender eine Sozialversicherungsnummer in einem Teams freigegeben hat. Hier sehen Sie, was der Empfänger gesehen hat:</span><span class="sxs-lookup"><span data-stu-id="77bd8-175">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77bd8-176">![Nachricht blockiert](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="77bd8-176">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="77bd8-177">Anpassen von Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="77bd8-177">To customize policy tips</span></span>

<span data-ttu-id="77bd8-178">Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt.</span><span class="sxs-lookup"><span data-stu-id="77bd8-178">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="77bd8-179">Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="77bd8-179">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="77bd8-180">Wechseln Sie zum Compliance Center ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="77bd8-180">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="77bd8-181">Wählen **Sie Richtlinie zur Verhinderung von Datenverlust**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-181">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="77bd8-182">Wählen Sie eine Richtlinie aus, und wählen Sie **neben Richtlinieneinstellungen** bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-182">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="77bd8-183">Erstellen Sie entweder eine neue Regel, oder bearbeiten Sie eine vorhandene Regel für die Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="77bd8-183">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77bd8-184">![Bearbeiten einer Regel für eine Richtlinie](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="77bd8-184">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="77bd8-185">Wählen Sie **auf der Registerkarte** Benutzerbenachrichtigungen die Option E-Mail-Text **anpassen** und/oder **Richtlinientipptextoptionen** anpassen aus.</span><span class="sxs-lookup"><span data-stu-id="77bd8-185">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77bd8-186">![Anpassen von Benutzerbenachrichtigungen und Richtlinientipps](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="77bd8-186">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="77bd8-187">Geben Sie den Text an, den Sie für E-Mail-Benachrichtigungen und/oder Richtlinientipps verwenden möchten, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-187">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="77bd8-188">Wählen Sie **auf der** Registerkarte Richtlinieneinstellungen die Option **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-188">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="77bd8-189">Lassen Sie ungefähr eine Stunde, bis Ihre Änderungen ihren Weg durch Ihr Rechenzentrum und die Synchronisierung mit Benutzerkonten finden.</span><span class="sxs-lookup"><span data-stu-id="77bd8-189">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="77bd8-190">Hinzufügen von Microsoft Teams als Speicherort zu bestehenden DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="77bd8-190">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="77bd8-191">Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt.</span><span class="sxs-lookup"><span data-stu-id="77bd8-191">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="77bd8-192">Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="77bd8-192">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="77bd8-193">Wechseln Sie zum Compliance Center ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="77bd8-193">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="77bd8-194">Wählen **Sie Richtlinie zur Verhinderung von Datenverlust**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-194">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="77bd8-195">Wählen Sie eine Richtlinie aus, und sehen Sie sich die Werte unter **Locations an.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-195">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="77bd8-196">Wenn sie Teams **und Kanalnachrichten sehen,** sind Sie alle festgelegt.</span><span class="sxs-lookup"><span data-stu-id="77bd8-196">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="77bd8-197">Klicken Sie auf Bearbeiten, falls **nicht.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-197">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77bd8-198">![Speicherorte für vorhandene Richtlinien](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="77bd8-198">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="77bd8-199">Aktivieren Sie **in** der Spalte Status die Richtlinie für Teams **Chat- und Kanalnachrichten**.</span><span class="sxs-lookup"><span data-stu-id="77bd8-199">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77bd8-200">![DLP für Teams und Kanäle](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="77bd8-200">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="77bd8-201">Behalten Sie **auf der** Registerkarte Speicherorte auswählen die Standardeinstellung aller Konten bei, oder wählen Sie Let me choose **specific locations** aus.</span><span class="sxs-lookup"><span data-stu-id="77bd8-201">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="77bd8-202">Sie können Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="77bd8-202">You can specify:</span></span>

    1. <span data-ttu-id="77bd8-203">Bis zu 1.000 einzelne Konten zum Ein- oder Ausschließen</span><span class="sxs-lookup"><span data-stu-id="77bd8-203">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="77bd8-204">Verteilerlisten und Sicherheitsgruppen, die ein- oder ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="77bd8-204">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="77bd8-205">Wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="77bd8-205">Then choose **Next**.</span></span>

7. <span data-ttu-id="77bd8-206">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="77bd8-206">Click **Save**.</span></span>

<span data-ttu-id="77bd8-207">Lassen Sie ungefähr eine Stunde, bis Ihre Änderungen ihren Weg durch Ihr Rechenzentrum und die Synchronisierung mit Benutzerkonten finden.</span><span class="sxs-lookup"><span data-stu-id="77bd8-207">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="77bd8-208">Definieren einer neuen DLP-Richtlinie für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77bd8-208">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="77bd8-209">Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt.</span><span class="sxs-lookup"><span data-stu-id="77bd8-209">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="77bd8-210">Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="77bd8-210">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="77bd8-211">Wechseln Sie zum Compliance Center ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="77bd8-211">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="77bd8-212">Wählen **Sie Richtlinie zur Verhinderung von**  >  **Datenverlust**  >  **+ Erstellen einer Richtlinie aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-212">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="77bd8-213">Wählen Sie [eine Vorlage](data-loss-prevention-policies.md#dlp-policy-templates)aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-213">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="77bd8-214">In unserem Beispiel haben wir die Vorlage für personenbezogene Daten in den USA ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="77bd8-214">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77bd8-215">![Datenschutzvorlage für die DLP-Richtlinie](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="77bd8-215">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="77bd8-216">Geben Sie **auf der Registerkarte** Name Ihrer Richtlinie einen Namen und eine Beschreibung für die Richtlinie an, und wählen Sie dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-216">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="77bd8-217">Behalten Sie **auf der** Registerkarte Speicherorte auswählen die Standardeinstellung aller Konten bei, oder wählen Sie Let me choose **specific locations** aus.</span><span class="sxs-lookup"><span data-stu-id="77bd8-217">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="77bd8-218">Sie können Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="77bd8-218">You can specify:</span></span>

    1. <span data-ttu-id="77bd8-219">Bis zu 1.000 einzelne Konten zum Ein- oder Ausschließen</span><span class="sxs-lookup"><span data-stu-id="77bd8-219">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="77bd8-220">Verteilerlisten und Sicherheitsgruppen, die ein- oder ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="77bd8-220">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="77bd8-221">**Dies ist ein öffentliches Vorschaufeature.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-221">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Speicherorte von DLP-Richtlinien](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="77bd8-223">Wenn Sie sicherstellen möchten, dass Dokumente, die vertrauliche Informationen enthalten, in Teams nicht unangemessen freigegeben werden, stellen Sie sicher, dass **SharePoint-Websites** und **OneDrive-Konten** sowie Teams Chat- und Kanalnachrichten aktiviert **sind.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-223">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="77bd8-224">Behalten Sie **auf** der Registerkarte Richtlinieneinstellungen unter Anpassen des Zu schützende Inhaltstyps die Standardeinstellungen für einfache Einstellungen bei, oder wählen Sie **Erweiterte** Einstellungen verwenden aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-224">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="77bd8-225">Wenn Sie erweiterte Einstellungen auswählen, können Sie Regeln für Ihre Richtlinie erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="77bd8-225">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="77bd8-226">Hilfe zu diesem Thema finden Sie unter [Einfache Einstellungen im Vergleich zu erweiterten Einstellungen](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span><span class="sxs-lookup"><span data-stu-id="77bd8-226">To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span></span>

7.  <span data-ttu-id="77bd8-227">Überprüfen Sie **auf der** Registerkarte Richtlinieneinstellungen unter Was möchten Sie tun, wenn vertrauliche Informationen erkannt **werden?** die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="77bd8-227">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="77bd8-228">Hier können Sie standardrichtlinientipps und E-Mail-Benachrichtigungen behalten [oder](use-notifications-and-policy-tips.md)anpassen.</span><span class="sxs-lookup"><span data-stu-id="77bd8-228">Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77bd8-229">![DLP-Richtlinieneinstellungen mit Tipps und Benachrichtigungen](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="77bd8-229">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="77bd8-230">Wenn Sie die Einstellungen überprüft oder bearbeitet haben, wählen Sie **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-230">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="77bd8-231">Wählen  Sie auf der Registerkarte Richtlinieneinstellungen unter Möchten Sie die Richtlinie aktivieren oder dinge zuerst **testen?** [aus,](dlp-overview-plan-for-dlp.md#policy-deployment)ob die Richtlinie aktiviert werden soll, testen Sie sie zuerst, oder lassen Sie sie vorerst deaktiviert, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="77bd8-231">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77bd8-232">![Angeben, ob die Richtlinie aktivieren soll](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="77bd8-232">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="77bd8-233">Überprüfen Sie **auf der Registerkarte** Einstellungen überprüfen die Einstellungen für Ihre neue Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="77bd8-233">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="77bd8-234">Wählen **Sie Bearbeiten** aus, um Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="77bd8-234">Choose **Edit** to make changes.</span></span> <span data-ttu-id="77bd8-235">Wenn Sie fertig sind, wählen Sie **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd8-235">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="77bd8-236">Lassen Sie ungefähr eine Stunde zu, bis Ihre neue Richtlinie ihren Weg durch Ihr Rechenzentrum durcharbeiten und mit Benutzerkonten synchronisieren kann.</span><span class="sxs-lookup"><span data-stu-id="77bd8-236">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="77bd8-237">Verhindern des externen Zugriffs auf vertrauliche Dokumente</span><span class="sxs-lookup"><span data-stu-id="77bd8-237">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="77bd8-238">Wählen Sie Folgendes aus, um sicherzustellen, dass SharePoint, die vertrauliche Informationen enthalten, nicht von externen Gästen entweder von SharePoint oder Teams zugegriffen werden kann:</span><span class="sxs-lookup"><span data-stu-id="77bd8-238">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="77bd8-239">Sie können sicherstellen, dass Dokumente geschützt sind, bis DLP sie überprüft und als sicher für die Freigabe markiert, indem Sie neue Dateien standardmäßig als [vertraulich kennzeichnen.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="77bd8-239">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="77bd8-240">Empfohlene DLP-Richtlinienstruktur</span><span class="sxs-lookup"><span data-stu-id="77bd8-240">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="77bd8-241">**Bedingungen:**</span><span class="sxs-lookup"><span data-stu-id="77bd8-241">**Conditions**</span></span>
        - <span data-ttu-id="77bd8-242">Inhalt enthält einen der folgenden Typen vertraulicher Informationen: [Alle anwendbaren Auswählen]</span><span class="sxs-lookup"><span data-stu-id="77bd8-242">Content contains any of these sensitive information types: [Select all that apply]</span></span>
        
        - <span data-ttu-id="77bd8-243">Inhalte werden von Microsoft 365 für Personen außerhalb meiner Organisation freigegeben</span><span class="sxs-lookup"><span data-stu-id="77bd8-243">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="77bd8-244">![DLP-Bedingungen zum Erkennen der externen Freigabe vertraulicher Inhalte](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="77bd8-244">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="77bd8-245">**Aktionen**</span><span class="sxs-lookup"><span data-stu-id="77bd8-245">**Actions**</span></span>
        - <span data-ttu-id="77bd8-246">Zugriff auf den Inhalt für externe Benutzer einschränken</span><span class="sxs-lookup"><span data-stu-id="77bd8-246">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="77bd8-247">Benutzer per E-Mail und mit Richtlinientipps benachrichtigen</span><span class="sxs-lookup"><span data-stu-id="77bd8-247">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="77bd8-248">Vorfallberichte an den Administrator senden</span><span class="sxs-lookup"><span data-stu-id="77bd8-248">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="77bd8-249">![DLP-Aktion zum Blockieren der externen Freigabe vertraulicher Inhalte](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="77bd8-249">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="77bd8-250">DLP-Richtlinie in Aktion beim Versuch, ein Dokument in SharePoint, das vertrauliche Informationen für einen externen Gast enthält:</span><span class="sxs-lookup"><span data-stu-id="77bd8-250">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77bd8-251">![Externe Freigabe blockiert](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="77bd8-251">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="77bd8-252">DLP-Richtlinie in Aktion, wenn Gast versucht, ein Dokument in einem Teams mit externem Block zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="77bd8-252">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77bd8-253">![Externer Zugriff blockiert](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="77bd8-253">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="77bd8-254">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="77bd8-254">Related articles</span></span>

- [<span data-ttu-id="77bd8-255">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="77bd8-255">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="77bd8-256">Senden von E-Mail-Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="77bd8-256">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)

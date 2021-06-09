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
description: Microsoft Teams Chats und Kanäle unterstützen DLP-Richtlinien (Data Loss Prevention).
ms.openlocfilehash: fa7e0967e24d8fa5e64b84fbccf54ff8cf45d1d6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843542"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="44ef2-103">Verhinderung von Datenverlust (DLP) und Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="44ef2-103">Data loss prevention and Microsoft Teams</span></span>

<span data-ttu-id="44ef2-104">Wenn Ihre Organisation über Verhinderung von Datenverlust (Data Loss Prevention, DLP) verfügt, können Sie Richtlinien definieren, die verhindern, dass Personen vertrauliche Informationen in einer Microsoft Teams Kanal- oder Chatsitzung freigeben.</span><span class="sxs-lookup"><span data-stu-id="44ef2-104">If your organization has data loss prevention (DLP), you can define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="44ef2-105">Hier sind einige Beispiele für die Funktionsweise dieses Schutzes:</span><span class="sxs-lookup"><span data-stu-id="44ef2-105">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="44ef2-106">**Beispiel 1: Schützen vertraulicher Informationen in Nachrichten.**</span><span class="sxs-lookup"><span data-stu-id="44ef2-106">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="44ef2-107">Angenommen, jemand versucht, vertrauliche Informationen in einem Teams Chat oder Kanal für Gäste (externe Benutzer) freizugeben.</span><span class="sxs-lookup"><span data-stu-id="44ef2-107">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="44ef2-108">Wenn Sie eine DLP-Richtlinie definiert haben, um dies zu verhindern, werden Nachrichten mit vertraulichen Informationen, die an externe Benutzer gesendet werden, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="44ef2-108">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="44ef2-109">Dies geschieht automatisch und innerhalb von Sekunden entsprechend der Konfiguration Ihrer DLP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="44ef2-109">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="44ef2-110">DLP für Microsoft Teams blockiert vertrauliche Inhalte, wenn sie für Microsoft Teams Benutzer freigegeben werden, die Folgendes haben:</span><span class="sxs-lookup"><span data-stu-id="44ef2-110">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="44ef2-111">- [Gastzugriff](/MicrosoftTeams/guest-access) in Teams und Kanälen; Oder</span><span class="sxs-lookup"><span data-stu-id="44ef2-111">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="44ef2-112">- [Externer Zugriff](/MicrosoftTeams/manage-external-access) in Besprechungen und Chatsitzungen.</span><span class="sxs-lookup"><span data-stu-id="44ef2-112">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="44ef2-113">DLP für externe Chatsitzungen funktioniert nur, wenn sich sowohl der Absender als auch der Empfänger im modus "Nur" Teams befinden und [Microsoft Teams systemeigenen Partnerverbund](/microsoftteams/manage-external-access)verwenden.</span><span class="sxs-lookup"><span data-stu-id="44ef2-113">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="44ef2-114">DLP für Teams blockiert keine Nachrichten in [der Interoperabilität](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) mit Skype for Business oder nicht systemeigenen Verbundchatsitzungen.</span><span class="sxs-lookup"><span data-stu-id="44ef2-114">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="44ef2-115">**Beispiel 2: Schützen vertraulicher Informationen in Dokumenten.**</span><span class="sxs-lookup"><span data-stu-id="44ef2-115">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="44ef2-116">Angenommen, jemand versucht, ein Dokument für Gäste in einem Microsoft Teams Kanal oder Chat freizugeben, und das Dokument enthält vertrauliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="44ef2-116">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="44ef2-117">Wenn Sie eine DLP-Richtlinie definiert haben, um dies zu verhindern, wird das Dokument für diese Benutzer nicht geöffnet.</span><span class="sxs-lookup"><span data-stu-id="44ef2-117">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="44ef2-118">Ihre DLP-Richtlinie muss SharePoint und OneDrive einschließen, damit ein Schutz besteht.</span><span class="sxs-lookup"><span data-stu-id="44ef2-118">Your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="44ef2-119">Dies ist ein Beispiel für DLP für SharePoint, das in Microsoft Teams angezeigt wird und daher erfordert, dass Benutzer für Office 365 DLP lizenziert sind (in Office 365 E3 enthalten), aber keine Benutzer für Office 365 Advanced Compliance lizenziert werden müssen.)</span><span class="sxs-lookup"><span data-stu-id="44ef2-119">This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="dlp-licensing-for-microsoft-teams"></a><span data-ttu-id="44ef2-120">DLP-Lizenzierung für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="44ef2-120">DLP Licensing for Microsoft Teams</span></span>

<span data-ttu-id="44ef2-121">Die Funktionen [zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md) wurden erweitert, um Microsoft Teams Chat- und Kanalnachrichten **einzuschließen, einschließlich Nachrichten aus privaten Kanälen** für:</span><span class="sxs-lookup"><span data-stu-id="44ef2-121">[Data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages** for:</span></span>

- <span data-ttu-id="44ef2-122">Office 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="44ef2-122">Office 365 E5/A5</span></span>
- <span data-ttu-id="44ef2-123">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="44ef2-123">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="44ef2-124">Microsoft 365 A5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="44ef2-124">Microsoft 365 Information Protection and Governance</span></span>
- <span data-ttu-id="44ef2-125">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="44ef2-125">Office 365 Advanced Compliance</span></span>

<span data-ttu-id="44ef2-126">Office 365 und Microsoft 365 E3 DLP-Schutz für SharePoint Online, OneDrive und Exchange Online enthalten.</span><span class="sxs-lookup"><span data-stu-id="44ef2-126">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="44ef2-127">Dies umfasst auch Dateien, die über Teams freigegeben werden, da Teams SharePoint Online und OneDrive zum Freigeben von Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="44ef2-127">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>

<span data-ttu-id="44ef2-128">Die Unterstützung des DLP-Schutzes in Teams Chat erfordert E5.</span><span class="sxs-lookup"><span data-stu-id="44ef2-128">Support for DLP protection in Teams Chat requires E5.</span></span>

<span data-ttu-id="44ef2-129">Weitere Informationen zu den Lizenzierungsanforderungen finden Sie unter [Microsoft 365-Dienste auf Mandantenebene – Leitfaden zur Lizenzierung](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="44ef2-129">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44ef2-130">DLP gilt nur für die tatsächlichen Nachrichten im Chat- oder Kanalthread.</span><span class="sxs-lookup"><span data-stu-id="44ef2-130">DLP applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="44ef2-131">Aktivitätsbenachrichtigungen – die eine kurze Nachrichtenvorschau enthalten und basierend auf den Benachrichtigungseinstellungen eines Benutzers angezeigt werden – sind **nicht** in Teams DLP enthalten.</span><span class="sxs-lookup"><span data-stu-id="44ef2-131">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP.</span></span> <span data-ttu-id="44ef2-132">Alle vertraulichen Informationen, die in dem Teil der Nachricht vorhanden sind, der in der Vorschau angezeigt wird, bleiben in der Benachrichtigung sichtbar, auch nachdem die DLP-Richtlinie angewendet und vertrauliche Informationen entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="44ef2-132">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

## <a name="scope-of-dlp-protection"></a><span data-ttu-id="44ef2-133">Umfang des DLP-Schutzes</span><span class="sxs-lookup"><span data-stu-id="44ef2-133">Scope of DLP protection</span></span>

<span data-ttu-id="44ef2-134">DLP-Schutz wird auf Teams Entitäten unterschiedlich angewendet.</span><span class="sxs-lookup"><span data-stu-id="44ef2-134">DLP protection are applied differently to Teams entities.</span></span>

|<span data-ttu-id="44ef2-135">Benutzerkonten/Gruppen/Liste</span><span class="sxs-lookup"><span data-stu-id="44ef2-135">User Accounts/Groups/List</span></span>  |<span data-ttu-id="44ef2-136">Teams Entität</span><span class="sxs-lookup"><span data-stu-id="44ef2-136">Teams Entity</span></span> |<span data-ttu-id="44ef2-137">DLP-Schutz verfügbar</span><span class="sxs-lookup"><span data-stu-id="44ef2-137">DLP protection available</span></span>|
|---------|---------|---------|
|<span data-ttu-id="44ef2-138">Einzelne Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="44ef2-138">individual user accounts</span></span>     |<span data-ttu-id="44ef2-139">1:1/n-Chats</span><span class="sxs-lookup"><span data-stu-id="44ef2-139">1:1/n chats</span></span>         |<span data-ttu-id="44ef2-140">ja</span><span class="sxs-lookup"><span data-stu-id="44ef2-140">yes</span></span>         |
|     |<span data-ttu-id="44ef2-141">Allgemeine Chats</span><span class="sxs-lookup"><span data-stu-id="44ef2-141">general chats</span></span>         |<span data-ttu-id="44ef2-142">nein</span><span class="sxs-lookup"><span data-stu-id="44ef2-142">no</span></span>         |
|     |<span data-ttu-id="44ef2-143">Private Kanäle</span><span class="sxs-lookup"><span data-stu-id="44ef2-143">private channels</span></span>         |<span data-ttu-id="44ef2-144">ja</span><span class="sxs-lookup"><span data-stu-id="44ef2-144">yes</span></span>         |
|<span data-ttu-id="44ef2-145">Sicherheitsgruppen/Verteilerlisten</span><span class="sxs-lookup"><span data-stu-id="44ef2-145">security groups/distribution lists</span></span>  | <span data-ttu-id="44ef2-146">1:1/n-Chats</span><span class="sxs-lookup"><span data-stu-id="44ef2-146">1:1/n chats</span></span>         |<span data-ttu-id="44ef2-147">ja</span><span class="sxs-lookup"><span data-stu-id="44ef2-147">yes</span></span>         |
|     |<span data-ttu-id="44ef2-148">Allgemeine Chats</span><span class="sxs-lookup"><span data-stu-id="44ef2-148">general chats</span></span>         |<span data-ttu-id="44ef2-149">nein</span><span class="sxs-lookup"><span data-stu-id="44ef2-149">no</span></span>         |
|     |<span data-ttu-id="44ef2-150">Private Kanäle</span><span class="sxs-lookup"><span data-stu-id="44ef2-150">private channels</span></span>         |<span data-ttu-id="44ef2-151">ja</span><span class="sxs-lookup"><span data-stu-id="44ef2-151">yes</span></span>        |
|<span data-ttu-id="44ef2-152">Microsoft 365 Gruppe</span><span class="sxs-lookup"><span data-stu-id="44ef2-152">Microsoft 365 group</span></span>    |<span data-ttu-id="44ef2-153">1:1/n-Chats</span><span class="sxs-lookup"><span data-stu-id="44ef2-153">1:1/n chats</span></span>          |<span data-ttu-id="44ef2-154">nein</span><span class="sxs-lookup"><span data-stu-id="44ef2-154">no</span></span>         |
|     |<span data-ttu-id="44ef2-155">Allgemeine Chats</span><span class="sxs-lookup"><span data-stu-id="44ef2-155">general chats</span></span>          |<span data-ttu-id="44ef2-156">ja</span><span class="sxs-lookup"><span data-stu-id="44ef2-156">yes</span></span>        |
|     |<span data-ttu-id="44ef2-157">Private Kanäle</span><span class="sxs-lookup"><span data-stu-id="44ef2-157">private channels</span></span>|<span data-ttu-id="44ef2-158">nein</span><span class="sxs-lookup"><span data-stu-id="44ef2-158">no</span></span>| 


## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="44ef2-159">Richtlinientipps helfen bei der Schulung von Benutzern</span><span class="sxs-lookup"><span data-stu-id="44ef2-159">Policy tips help educate users</span></span>

<span data-ttu-id="44ef2-160">Ähnlich wie DLP in [Exchange, Outlook, Outlook im Web,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web) [SharePoint Online, OneDrive for Business Websites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)und Office [Desktopclients,](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)werden Richtlinientipps angezeigt, wenn eine Aktion mit einer DLP-Richtlinie ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="44ef2-160">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action triggers with a DLP policy.</span></span> <span data-ttu-id="44ef2-161">Hier ist ein Beispiel für einen Richtlinientipp:</span><span class="sxs-lookup"><span data-stu-id="44ef2-161">Here's an example of a policy tip:</span></span>

![Benachrichtigung über blockierte Nachrichten in Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="44ef2-163">Hier hat der Absender versucht, eine Sozialversicherungsnummer in einem Microsoft Teams Kanal freizugeben.</span><span class="sxs-lookup"><span data-stu-id="44ef2-163">Here, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="44ef2-164">Über den Link **"Was kann ich tun?"** wird ein Dialogfeld geöffnet, das Optionen für den Absender zur Behebung des Problems bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="44ef2-164">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="44ef2-165">Beachten Sie, dass der Absender die Richtlinie außer Kraft setzen oder einen Administrator benachrichtigen kann, die Richtlinie zu überprüfen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="44ef2-165">Notice that, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Optionen zum Auflösen blockierter Nachrichten](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="44ef2-167">In Ihrer Organisation können Sie festlegen, dass Benutzer eine DLP-Richtlinie außer Kraft setzen können.</span><span class="sxs-lookup"><span data-stu-id="44ef2-167">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="44ef2-168">Wenn Sie Ihre DLP-Richtlinien konfigurieren, können Sie die Standardrichtlinientipps verwenden oder [Richtlinientipps](#to-customize-policy-tips) für Ihre Organisation anpassen.</span><span class="sxs-lookup"><span data-stu-id="44ef2-168">When you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="44ef2-169">Wenn Sie zu unserem Beispiel zurückkehren, bei dem ein Absender eine Sozialversicherungsnummer in einem Teams Kanal freigegeben hat, sieht der Empfänger Folgendes:</span><span class="sxs-lookup"><span data-stu-id="44ef2-169">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44ef2-170">![Nachricht blockiert](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="44ef2-170">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="44ef2-171">Anpassen von Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="44ef2-171">To customize policy tips</span></span>

<span data-ttu-id="44ef2-172">Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt.</span><span class="sxs-lookup"><span data-stu-id="44ef2-172">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="44ef2-173">Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="44ef2-173">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="44ef2-174">Wechseln Sie zum Compliance Center ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="44ef2-174">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="44ef2-175">Klicken Sie auf die **Verhinderung von Datenverlust-** > **Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="44ef2-175">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="44ef2-176">Wählen Sie eine Richtlinie aus, und wählen Sie neben **den Richtlinieneinstellungen** **"Bearbeiten"** aus.</span><span class="sxs-lookup"><span data-stu-id="44ef2-176">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="44ef2-177">Erstellen Sie entweder eine neue Regel, oder bearbeiten Sie eine vorhandene Regel für die Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="44ef2-177">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="44ef2-178">![Bearbeiten einer Regel für eine Richtlinie](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="44ef2-178">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="44ef2-179">Wählen Sie auf der Registerkarte **"Benutzerbenachrichtigungen"** die Option **"E-Mail-Text anpassen"** und/oder **"Richtlinientipp-Textoptionen anpassen"** aus.</span><span class="sxs-lookup"><span data-stu-id="44ef2-179">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="44ef2-180">![Anpassen von Benutzerbenachrichtigungen und Richtlinientipps](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="44ef2-180">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="44ef2-181">Geben Sie den Text an, den Sie für E-Mail-Benachrichtigungen und/oder Richtlinientipps verwenden möchten, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="44ef2-181">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="44ef2-182">Wählen Sie auf der Registerkarte **"Richtlinieneinstellungen"** die Option **"Speichern"** aus.</span><span class="sxs-lookup"><span data-stu-id="44ef2-182">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="44ef2-183">Lassen Sie ungefähr eine Stunde zu, bis Ihre Änderungen sich in Ihrem Rechenzentrum befinden und mit Benutzerkonten synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="44ef2-183">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="44ef2-184">Hinzufügen von Microsoft Teams als Speicherort zu bestehenden DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="44ef2-184">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="44ef2-185">Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt.</span><span class="sxs-lookup"><span data-stu-id="44ef2-185">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="44ef2-186">Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="44ef2-186">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="44ef2-187">Wechseln Sie zum Compliance Center ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="44ef2-187">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="44ef2-188">Klicken Sie auf die **Verhinderung von Datenverlust-** > **Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="44ef2-188">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="44ef2-189">Wählen Sie eine Richtlinie aus, und sehen Sie sich die Werte unter **Speicherorte an.**</span><span class="sxs-lookup"><span data-stu-id="44ef2-189">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="44ef2-190">Wenn **Teams Chat- und Kanalnachrichten** angezeigt werden, sind Sie alle festgelegt.</span><span class="sxs-lookup"><span data-stu-id="44ef2-190">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="44ef2-191">Wenn Dies nicht der Fall ist, klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="44ef2-191">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="44ef2-192">![Speicherorte für vorhandene Richtlinien](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="44ef2-192">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="44ef2-193">Aktivieren Sie in der Spalte **"Status"** die Richtlinie für **Teams Chat- und Kanalnachrichten.**</span><span class="sxs-lookup"><span data-stu-id="44ef2-193">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="44ef2-194">![DLP für Teams Chats und Kanäle](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="44ef2-194">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="44ef2-195">Behalten Sie auf der Registerkarte **"Speicherorte auswählen"** die Standardeinstellung aller Konten bei, oder wählen Sie **"Bestimmte Speicherorte auswählen"** aus.</span><span class="sxs-lookup"><span data-stu-id="44ef2-195">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="44ef2-196">Sie können Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="44ef2-196">You can specify:</span></span>

    1. <span data-ttu-id="44ef2-197">bis zu 1.000 einzelne Konten, die ein- oder ausgeschlossen werden sollen</span><span class="sxs-lookup"><span data-stu-id="44ef2-197">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="44ef2-198">Verteilerlisten und Sicherheitsgruppen, die eingeschlossen oder ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="44ef2-198">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="44ef2-199">Wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="44ef2-199">Then choose **Next**.</span></span>

7. <span data-ttu-id="44ef2-200">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="44ef2-200">Click **Save**.</span></span>

<span data-ttu-id="44ef2-201">Lassen Sie ungefähr eine Stunde zu, bis Ihre Änderungen sich in Ihrem Rechenzentrum befinden und mit Benutzerkonten synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="44ef2-201">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="44ef2-202">Definieren einer neuen DLP-Richtlinie für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="44ef2-202">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="44ef2-203">Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt.</span><span class="sxs-lookup"><span data-stu-id="44ef2-203">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="44ef2-204">Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="44ef2-204">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="44ef2-205">Wechseln Sie zum Compliance Center ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="44ef2-205">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="44ef2-206">Klicken Sie auf **Verhinderung von Datenverlust** > **Richtlinie** > **+ Erstellen einer Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="44ef2-206">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="44ef2-207">Wählen Sie eine [Vorlage](data-loss-prevention-policies.md#dlp-policy-templates)aus, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="44ef2-207">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="44ef2-208">In unserem Beispiel haben wir die Vorlage für personenbezogene Informationen in den USA ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="44ef2-208">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="44ef2-209">![Datenschutzvorlage für DLP-Richtlinie](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="44ef2-209">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="44ef2-210">Geben Sie auf der Registerkarte **"Name Ihrer Richtlinie"** einen Namen und eine Beschreibung für die Richtlinie an, und wählen Sie dann **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="44ef2-210">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="44ef2-211">Behalten Sie auf der Registerkarte **"Speicherorte auswählen"** die Standardeinstellung aller Konten bei, oder wählen Sie **"Bestimmte Speicherorte auswählen"** aus.</span><span class="sxs-lookup"><span data-stu-id="44ef2-211">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="44ef2-212">Sie können Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="44ef2-212">You can specify:</span></span>

    1. <span data-ttu-id="44ef2-213">bis zu 1.000 einzelne Konten, die ein- oder ausgeschlossen werden sollen</span><span class="sxs-lookup"><span data-stu-id="44ef2-213">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="44ef2-214">Verteilerlisten und Sicherheitsgruppen, die eingeschlossen oder ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="44ef2-214">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="44ef2-215">**Dies ist eine öffentliche Vorschaufunktion.**</span><span class="sxs-lookup"><span data-stu-id="44ef2-215">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP-Richtlinienspeicherorte](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="44ef2-217">Wenn Sie sicherstellen möchten, dass Dokumente, die vertrauliche Informationen enthalten, nicht unangemessen in Teams freigegeben werden, stellen Sie sicher, dass **SharePoint Websites** und **OneDrive Konten** sowie **Teams Chat- und Kanalnachrichten** aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="44ef2-217">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="44ef2-218">On the **Policy settings** tab, under Customize the type of content you want **to protect,** keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span><span class="sxs-lookup"><span data-stu-id="44ef2-218">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="44ef2-219">Wenn Sie erweiterte Einstellungen auswählen, können Sie Regeln für Ihre Richtlinie erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="44ef2-219">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="44ef2-220">Hilfe hierzu finden Sie unter ["Einfache Einstellungen" im Vergleich zu erweiterten Einstellungen.](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)</span><span class="sxs-lookup"><span data-stu-id="44ef2-220">To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span></span>

7.  <span data-ttu-id="44ef2-221">Überprüfen Sie auf der Registerkarte **"Richtlinieneinstellungen"** unter **"Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?"** die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="44ef2-221">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="44ef2-222">Hier können Sie auswählen, ob Sie standardmäßige [Richtlinientipps und E-Mail-Benachrichtigungen](use-notifications-and-policy-tips.md)beibehalten oder anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="44ef2-222">Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="44ef2-223">![DLP-Richtlinieneinstellungen mit Tipps und Benachrichtigungen](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="44ef2-223">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="44ef2-224">Wenn Sie die Überprüfung oder Bearbeitung der Einstellungen abgeschlossen haben, wählen Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="44ef2-224">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="44ef2-225">Wählen Sie auf der Registerkarte **"Richtlinieneinstellungen"** unter **Möchten Sie die Richtlinie aktivieren oder zuerst testen?** aus, ob Sie die Richtlinie aktivieren, [zuerst testen](dlp-overview-plan-for-dlp.md#policy-deployment)oder vorerst deaktiviert lassen möchten, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="44ef2-225">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="44ef2-226">![Angeben, ob die Richtlinie aktiviert werden soll](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="44ef2-226">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="44ef2-227">Überprüfen Sie auf der Registerkarte **"Einstellungen überprüfen"** die Einstellungen für Ihre neue Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="44ef2-227">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="44ef2-228">Wählen Sie **"Bearbeiten"** aus, um Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="44ef2-228">Choose **Edit** to make changes.</span></span> <span data-ttu-id="44ef2-229">Wenn Sie fertig sind, wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="44ef2-229">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="44ef2-230">Lassen Sie ungefähr eine Stunde zu, bis ihre neue Richtlinie sich in Ihrem Rechenzentrum durcharbeiten und mit Benutzerkonten synchronisieren kann.</span><span class="sxs-lookup"><span data-stu-id="44ef2-230">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="44ef2-231">Verhindern des externen Zugriffs auf vertrauliche Dokumente</span><span class="sxs-lookup"><span data-stu-id="44ef2-231">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="44ef2-232">Um sicherzustellen, dass SharePoint Dokumente, die vertrauliche Informationen enthalten, nicht standardmäßig von externen Gästen über SharePoint oder Teams aufgerufen werden können, wählen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="44ef2-232">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="44ef2-233">Sie können sicherstellen, dass Dokumente geschützt sind, bis DLP-Scans ausgeführt werden, und sie als sicher für die Freigabe kennzeichnen, indem Sie [neue Dateien standardmäßig als vertraulich markieren.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="44ef2-233">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="44ef2-234">Empfohlene DLP-Richtlinienstruktur</span><span class="sxs-lookup"><span data-stu-id="44ef2-234">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="44ef2-235">**Bedingungen:**</span><span class="sxs-lookup"><span data-stu-id="44ef2-235">**Conditions**</span></span>
        - <span data-ttu-id="44ef2-236">Der Inhalt enthält einen der folgenden vertraulichen Informationstypen: [Alle zutreffenden Auswählen]</span><span class="sxs-lookup"><span data-stu-id="44ef2-236">Content contains any of these sensitive information types: [Select all that apply]</span></span>
        
        - <span data-ttu-id="44ef2-237">Inhalte werden von Microsoft 365 für Personen außerhalb meiner Organisation freigegeben.</span><span class="sxs-lookup"><span data-stu-id="44ef2-237">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="44ef2-238">![DLP-Bedingungen zum Erkennen der externen Freigabe vertraulicher Inhalte](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="44ef2-238">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="44ef2-239">**Aktionen**</span><span class="sxs-lookup"><span data-stu-id="44ef2-239">**Actions**</span></span>
        - <span data-ttu-id="44ef2-240">Zugriff auf den Inhalt für externe Benutzer einschränken</span><span class="sxs-lookup"><span data-stu-id="44ef2-240">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="44ef2-241">Benutzer per E-Mail und mit Richtlinientipps benachrichtigen</span><span class="sxs-lookup"><span data-stu-id="44ef2-241">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="44ef2-242">Vorfallberichte an den Administrator senden</span><span class="sxs-lookup"><span data-stu-id="44ef2-242">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="44ef2-243">![DLP-Aktion zum Blockieren der externen Freigabe vertraulicher Inhalte](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="44ef2-243">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="44ef2-244">DLP-Richtlinie in Aktion beim Versuch, ein Dokument in SharePoint freizugeben, das vertrauliche Informationen für einen externen Gast enthält:</span><span class="sxs-lookup"><span data-stu-id="44ef2-244">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44ef2-245">![Externe Freigabe blockiert](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="44ef2-245">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="44ef2-246">DLP-Richtlinie in Aktion, wenn Gast versucht, ein Dokument in Teams mit externen Blockierung zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="44ef2-246">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44ef2-247">![Externer Zugriff blockiert](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="44ef2-247">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="44ef2-248">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="44ef2-248">Related articles</span></span>

- [<span data-ttu-id="44ef2-249">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="44ef2-249">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="44ef2-250">Senden von E-Mail-Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="44ef2-250">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)

---
title: Verwalten von Nachrichten und Dateien in Quarantäne als Administrator
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie isolierte Nachrichten für alle Benutzer in Exchange Online Protection (EOP) anzeigen und verwalten. Administratoren in Organisationen mit Microsoft Defender für Office 365 können auch isolierte Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams verwalten.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3dee441a3442454c5f2978422d18a2084f8377f3
ms.sourcegitcommit: 3d2261af22bebbbf7efa8a0d3135225a15bd6ba8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51215537"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="091cf-104">Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP</span><span class="sxs-lookup"><span data-stu-id="091cf-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="091cf-105">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="091cf-105">**Applies to**</span></span>
- [<span data-ttu-id="091cf-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="091cf-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="091cf-107">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="091cf-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="091cf-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="091cf-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="091cf-109">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="091cf-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="091cf-110">Weitere Informationen finden Sie unter [Quarantined email messages in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="091cf-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="091cf-111">Administratoren können alle Arten von isolierten Nachrichten für alle Benutzer anzeigen, veröffentlichen und löschen.</span><span class="sxs-lookup"><span data-stu-id="091cf-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="091cf-112">Nur Administratoren können Nachrichten verwalten, die als Schadsoftware, Phishing mit hoher Sicherheit oder als Ergebnis von Nachrichtenflussregeln (auch als Transportregeln bekannt) isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="091cf-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="091cf-113">Administratoren können auch falsch positive Ergebnisse an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="091cf-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="091cf-114">Administratoren in Organisationen mit Microsoft Defender für Office 365 können auch isolierte Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams anzeigen, herunterladen und löschen.</span><span class="sxs-lookup"><span data-stu-id="091cf-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="091cf-115">Sie können isolierte Nachrichten im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange &) anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="091cf-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="091cf-116">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="091cf-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="091cf-117">Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="091cf-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="091cf-118">Um die Quarantäne-Seite direkt zu öffnen, wechseln Sie zu <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="091cf-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="091cf-119">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="091cf-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="091cf-120">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="091cf-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="091cf-121">Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:</span><span class="sxs-lookup"><span data-stu-id="091cf-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="091cf-122">Um Maßnahmen für isolierte Nachrichten für alle Benutzer zu ergreifen, müssen Sie Mitglied der Rollengruppen Organisationsverwaltung, Sicherheitsadministrator oder **Quarantäneadministrator** <sup>\*</sup> sein.</span><span class="sxs-lookup"><span data-stu-id="091cf-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="091cf-123">Für den schreibgeschützten Zugriff auf isolierte Nachrichten für alle Benutzer müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.</span><span class="sxs-lookup"><span data-stu-id="091cf-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="091cf-124">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="091cf-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="091cf-125">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="091cf-125">**Notes**:</span></span>

  - <span data-ttu-id="091cf-126">Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="091cf-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="091cf-127">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="091cf-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="091cf-128">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="091cf-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="091cf-129"><sup>\*</sup> Mitglieder der **Rollengruppe Quarantäneadministrator** müssen auch Mitglieder der Rollengruppe **"Hygieneverwaltung"** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) sein, um Quarantäneverfahren in Exchange Online PowerShell ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="091cf-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="091cf-130">Isolierte Nachrichten werden für einen Standardzeitraum aufbewahrt, bevor sie automatisch gelöscht werden:</span><span class="sxs-lookup"><span data-stu-id="091cf-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="091cf-131">30 Tage für Nachrichten, die von Antispamrichtlinien isoliert werden (Spam, Phishing und Massen-E-Mails).</span><span class="sxs-lookup"><span data-stu-id="091cf-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="091cf-132">Dies ist der Standardwert und der Höchstwert.</span><span class="sxs-lookup"><span data-stu-id="091cf-132">This is the default and maximum value.</span></span> <span data-ttu-id="091cf-133">Informationen zum Konfigurieren (niedriger) dieses Werts finden Sie unter [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="091cf-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="091cf-134">15 Tage für Nachrichten, die Schadsoftware enthalten.</span><span class="sxs-lookup"><span data-stu-id="091cf-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="091cf-135">15 Tage für Dateien, die von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams in Defender für Office 365 isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="091cf-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="091cf-136">Wenn eine Nachricht aus der Quarantäne abläuft, können Sie sie nicht wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="091cf-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="091cf-137">Verwenden des Security & Compliance Center zum Verwalten isolierter E-Mail-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="091cf-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="091cf-138">Anzeigen isolierter E-Mails</span><span class="sxs-lookup"><span data-stu-id="091cf-138">View quarantined email</span></span>

1. <span data-ttu-id="091cf-139">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="091cf-139">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="091cf-140">Stellen Sie sicher, dass **Quarantäne anzeigen** auf den Standardwert **E-Mail** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="091cf-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="091cf-141">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="091cf-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="091cf-142">Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="091cf-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="091cf-143">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="091cf-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="091cf-144">**Empfangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="091cf-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="091cf-145">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="091cf-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="091cf-146">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="091cf-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="091cf-147">**Quarantänegrund**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="091cf-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="091cf-148">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="091cf-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="091cf-149">**Richtlinientyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="091cf-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="091cf-150">**Expires**</span><span class="sxs-lookup"><span data-stu-id="091cf-150">**Expires**</span></span>
   - <span data-ttu-id="091cf-151">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="091cf-151">**Recipient**</span></span>
   - <span data-ttu-id="091cf-152">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="091cf-152">**Message ID**</span></span>
   - <span data-ttu-id="091cf-153">**Name der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="091cf-153">**Policy name**</span></span>
   - <span data-ttu-id="091cf-154">**Größe**</span><span class="sxs-lookup"><span data-stu-id="091cf-154">**Size**</span></span>
   - <span data-ttu-id="091cf-155">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="091cf-155">**Direction**</span></span>

   <span data-ttu-id="091cf-156">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**, oder klicken Sie auf **Als Standard festlegen**.</span><span class="sxs-lookup"><span data-stu-id="091cf-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="091cf-157">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="091cf-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="091cf-158">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="091cf-158">The available filters are:</span></span>

   - <span data-ttu-id="091cf-159">**Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="091cf-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="091cf-160">**Heute**</span><span class="sxs-lookup"><span data-stu-id="091cf-160">**Today**</span></span>
     - <span data-ttu-id="091cf-161">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="091cf-161">**Next 2 days**</span></span>
     - <span data-ttu-id="091cf-162">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="091cf-162">**Next 7 days**</span></span>
     - <span data-ttu-id="091cf-163">**Benutzerdefiniert**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="091cf-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="091cf-164">**Empfangszeit**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="091cf-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="091cf-165">**Quarantänegrund**:</span><span class="sxs-lookup"><span data-stu-id="091cf-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="091cf-166">**Richtlinie**: Die Nachricht hat den Bedingungen einer Nachrichtenflussregel (auch als Transportregel bekannt) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="091cf-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="091cf-167">**Bulk**</span><span class="sxs-lookup"><span data-stu-id="091cf-167">**Bulk**</span></span>
     - <span data-ttu-id="091cf-168">**Phish**: Das Spamfilter-Urteil **lautete Phishing-E-Mail** oder Antiphishingschutz, der die Nachricht isolierte ([Spoofeinstellungen](set-up-anti-phishing-policies.md#spoof-settings) oder [Identitätswechselschutz](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="091cf-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="091cf-169">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="091cf-169">**Malware**</span></span>
     - <span data-ttu-id="091cf-170">**Spam**</span><span class="sxs-lookup"><span data-stu-id="091cf-170">**Spam**</span></span>
     - <span data-ttu-id="091cf-171">**Phish mit hoher Konfidenz**</span><span class="sxs-lookup"><span data-stu-id="091cf-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="091cf-172">**Richtlinientyp**: Filtern von Nachrichten nach Richtlinientyp:</span><span class="sxs-lookup"><span data-stu-id="091cf-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="091cf-173">**Richtlinie für Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="091cf-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="091cf-174">**Richtlinie für sichere Anlagen**</span><span class="sxs-lookup"><span data-stu-id="091cf-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="091cf-175">**Antiphishing-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="091cf-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="091cf-176">**Richtlinie für gehostete Inhaltsfilter** (Antispamrichtlinie)</span><span class="sxs-lookup"><span data-stu-id="091cf-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="091cf-177">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="091cf-177">**Transport rule**</span></span>

   - <span data-ttu-id="091cf-178">**E-Mail-Empfänger:** Alle Benutzer oder nur an Sie gesendete Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="091cf-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="091cf-179">Endbenutzer können nur nachrichten in Quarantäne verwalten, die an sie gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="091cf-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="091cf-180">Klicken Sie auf **Löschen**, um den Filter zu löschen.</span><span class="sxs-lookup"><span data-stu-id="091cf-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="091cf-181">Um das Filter-Flyout auszublenden, klicken Sie erneut auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="091cf-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="091cf-182">Verwenden Sie **Ergebnisse sortieren nach** (standardmäßig die Schaltfläche **Nachrichten-ID**) und einen entsprechenden Wert, um bestimmte Nachrichten zu finden.</span><span class="sxs-lookup"><span data-stu-id="091cf-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="091cf-183">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="091cf-183">Wildcards aren't supported.</span></span> <span data-ttu-id="091cf-184">Sie können nach den folgenden Werten suchen:</span><span class="sxs-lookup"><span data-stu-id="091cf-184">You can search by the following values:</span></span>

   - <span data-ttu-id="091cf-185">**Nachrichten-ID**: Die globale eindeutige ID der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="091cf-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="091cf-186">Beispielsweise haben Sie [](message-trace-scc.md) die Nachrichtenverfolgung verwendet, um nach einer Nachricht zu suchen, die an einen Benutzer in Ihrer Organisation gesendet wurde, und Sie bestimmen, dass die Nachricht isoliert und nicht zugestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="091cf-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="091cf-187">Achten Sie darauf, den vollständigen Nachrichten-ID-Wert zu verwenden, der eckige Klammern ( ) enthalten \<\> kann.</span><span class="sxs-lookup"><span data-stu-id="091cf-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="091cf-188">Beispiel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="091cf-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="091cf-189">**E-Mail-Adresse des Absenders**: Die E-Mail-Adresse eines einzelnen Absenders.</span><span class="sxs-lookup"><span data-stu-id="091cf-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="091cf-190">**Richtlinienname**: Verwenden Sie den vollständigen Namen der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="091cf-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="091cf-191">Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="091cf-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="091cf-192">**E-Mail-Adresse des Empfängers**: Die E-Mail-Adresse eines einzelnen Empfängers.</span><span class="sxs-lookup"><span data-stu-id="091cf-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="091cf-193">**Betreff**: Verwenden Sie den gesamten Betreff der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="091cf-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="091cf-194">Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="091cf-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="091cf-195">**Richtlinienname**: Der Name der Richtlinie, die für die Quarantinierung der Nachricht verantwortlich war.</span><span class="sxs-lookup"><span data-stu-id="091cf-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="091cf-196">Nachdem Sie die Suchkriterien eingegeben haben, klicken Sie auf die ![Schaltfläche Aktualisieren](../../media/scc-quarantine-refresh.png) **Aktualisieren**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="091cf-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="091cf-197">Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Maßnahmen zu ergreifen (z. B. die Nachricht anzeigen, freigeben, herunterladen oder löschen).</span><span class="sxs-lookup"><span data-stu-id="091cf-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="091cf-198">Anzeigen von Details der isolierten Nachricht</span><span class="sxs-lookup"><span data-stu-id="091cf-198">View quarantined message details</span></span>

<span data-ttu-id="091cf-199">Wenn Sie eine E-Mail-Nachricht in der Liste auswählen, werden die folgenden Nachrichtendetails im Flyout-Fenster **Details** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="091cf-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="091cf-200">**Nachrichten-ID**: Die globale eindeutige ID für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="091cf-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="091cf-201">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="091cf-201">**Sender address**</span></span>

- <span data-ttu-id="091cf-202">**Empfangen**: Das Datum/die Uhrzeit des Nachrichtenempfangs.</span><span class="sxs-lookup"><span data-stu-id="091cf-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="091cf-203">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="091cf-203">**Subject**</span></span>

- <span data-ttu-id="091cf-204">**Quarantänegrund**: Zeigt an, ob eine Nachricht als **Spam**, **Bulk**, **Phish**, einer Nachrichtenflussregel (**Transportregel**) oder als Schadsoftware identifiziert **wurde.**</span><span class="sxs-lookup"><span data-stu-id="091cf-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="091cf-205">**Anzahl der Empfänger**</span><span class="sxs-lookup"><span data-stu-id="091cf-205">**Recipient count**</span></span>

- <span data-ttu-id="091cf-206">**Empfänger**: Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Vorschau der Nachricht anzeigen** oder **Nachrichten** Kopfzeile anzeigen klicken, um die gesamte Liste der Empfänger anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="091cf-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="091cf-207">**Läuft ab**. Das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="091cf-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="091cf-208">**Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="091cf-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="091cf-209">**Noch nicht freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht noch nicht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="091cf-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="091cf-210">Maßnahmen für isolierte E-Mails ergreifen</span><span class="sxs-lookup"><span data-stu-id="091cf-210">Take action on quarantined email</span></span>

<span data-ttu-id="091cf-211">Nachdem Sie eine Nachricht ausgewählt haben, stehen Ihnen im  Flyoutbereich Details mehrere Optionen zur Verfügung, um die Nachrichten zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="091cf-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="091cf-212">**Veröffentlichungsnachricht**: Wählen Sie im angezeigten Flyoutbereich die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="091cf-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="091cf-213">Nachrichten zur Analyse an **Microsoft melden:** Dies ist standardmäßig ausgewählt und meldet die fälschlicherweise isolierte Nachricht an Microsoft als falsch positiv.</span><span class="sxs-lookup"><span data-stu-id="091cf-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="091cf-214">Wenn die Nachricht als Spam, Massenware, Phishing oder Schadsoftware isoliert wurde, wird die Nachricht auch an das Microsoft Spam Analysis Team gemeldet.</span><span class="sxs-lookup"><span data-stu-id="091cf-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="091cf-215">Je nach Analyse können die dienstweiten Spamfilterregeln angepasst werden, um die Nachricht durch zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="091cf-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="091cf-216">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="091cf-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="091cf-217">**Veröffentlichen von Nachrichten an alle Empfänger**</span><span class="sxs-lookup"><span data-stu-id="091cf-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="091cf-218">**Veröffentlichung von Nachrichten an bestimmte Empfänger**</span><span class="sxs-lookup"><span data-stu-id="091cf-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="091cf-219">**Nachrichten an andere Personen freigeben:** Beachten Sie, dass die Freigabe von Schadsoftwarenachrichten an andere Personen als die ursprünglichen Empfänger nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="091cf-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="091cf-220">Klicken Sie nach Abschluss des Vorgangs auf **Nachrichten freigeben**.</span><span class="sxs-lookup"><span data-stu-id="091cf-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="091cf-221">Hinweise zum Freigeben von Nachrichten:</span><span class="sxs-lookup"><span data-stu-id="091cf-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="091cf-222">Sie können eine Nachricht nicht mehr als einmal an denselben Empfänger los.</span><span class="sxs-lookup"><span data-stu-id="091cf-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="091cf-223">Nur Empfänger, die die Nachricht nicht erhalten haben, werden in der Liste der potenziellen Empfänger angezeigt.</span><span class="sxs-lookup"><span data-stu-id="091cf-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="091cf-224">**Nachrichtenkopf anzeigen**: Wählen Sie diesen Link aus, um den Nachrichtenkopftext anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="091cf-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="091cf-225">Um den Nachrichtenkopf im Detail zu analysieren, kopieren Sie den Nachrichtenkopftext in die Zwischenablage, und wählen Sie dann **Microsoft-Nachrichtenkopfanalyse** aus, um zur Remoteverbindungsuntersuchung zu wechseln (klicken Sie mit der rechten Maustaste, und wählen Sie **In neuer Registerkarte öffnen** aus, wenn Sie Microsoft 365 nicht verlassen möchten, um die Aufgabe auszuführen).</span><span class="sxs-lookup"><span data-stu-id="091cf-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="091cf-226">Fügen Sie den Nachrichtenkopf auf der Seite in den Abschnitt "Nachrichtenkopfanalyse" ein, und wählen Sie dann **Kopfzeilen analysieren** aus:</span><span class="sxs-lookup"><span data-stu-id="091cf-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="091cf-227">**Vorschau der Nachricht anzeigen**: Wählen Sie im angezeigten Flyout-Fenster eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="091cf-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="091cf-228">**Quellansicht**: Zeigt die HTML-Version des Nachrichtentextes an, wobei alle Links deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="091cf-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="091cf-229">**Textansicht**: Zeigt den Nachrichtentext im Klartext an.</span><span class="sxs-lookup"><span data-stu-id="091cf-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="091cf-230">**Aus Quarantäne entfernen:** Nachdem Sie **in** der angezeigten Warnung auf Ja geklickt haben, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="091cf-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="091cf-231">**Nachricht herunterladen**: Wählen Sie im daraufhin angezeigten Flyout-Fenster **Ich verstehe die Risiken beim Herunterladen dieser Nachricht** aus, um eine lokale Kopie der Nachricht im eml-Format zu speichern.</span><span class="sxs-lookup"><span data-stu-id="091cf-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="091cf-232">**Absender blockieren:** Dadurch wird verhindert, dass der Absender E-Mails an das Postfach des Administratorempfängers sendet.</span><span class="sxs-lookup"><span data-stu-id="091cf-232">**Block Sender**: This blocks the sender from sending emails to the admin recipient mailbox.</span></span>

- <span data-ttu-id="091cf-233">**Nachricht senden**: Wählen Sie im angezeigten Flyoutbereich die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="091cf-233">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="091cf-234">**Objekttyp:** **E-Mail** (Standard), **URL** oder **Attachment**.</span><span class="sxs-lookup"><span data-stu-id="091cf-234">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="091cf-235">**Übermittlungsformat:** **Netzwerknachrichten-ID** (Standard, mit dem entsprechenden Wert im Feld **Netzwerknachrichten-ID)** oder **Datei** (navigieren Sie zu einer lokalen EML- oder MSG-Datei).</span><span class="sxs-lookup"><span data-stu-id="091cf-235">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="091cf-236">Beachten Sie, dass der Ursprüngliche Wert weg ist, wenn Sie **Datei** und dann **Netzwerknachrichten-ID** auswählen.</span><span class="sxs-lookup"><span data-stu-id="091cf-236">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="091cf-237">**Empfänger:** Geben Sie beim Leasen einen ursprünglichen Empfänger der Nachricht ein, oder klicken Sie auf **Alle** auswählen, um alle Empfänger zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="091cf-237">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="091cf-238">Sie können auch auf **Alle auswählen** und dann einzelne Empfänger selektiv entfernen.</span><span class="sxs-lookup"><span data-stu-id="091cf-238">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="091cf-239">**Übermittlungsgrund:** **Sollte nicht blockiert** worden sein (Standardeinstellung) oder Sollte blockiert worden **sein.**</span><span class="sxs-lookup"><span data-stu-id="091cf-239">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="091cf-240">Klicken Sie nach Abschluss des Abschlusses auf **Absenden**.</span><span class="sxs-lookup"><span data-stu-id="091cf-240">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="091cf-241">Wenn Sie die Nachricht nicht freigeben oder entfernen, wird sie nach Ablauf der Standard-Quarantäneaufbewahrungszeit gelöscht.</span><span class="sxs-lookup"><span data-stu-id="091cf-241">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="091cf-242">Maßnahmen für mehrere isolierte E-Mail-Nachrichten ergreifen</span><span class="sxs-lookup"><span data-stu-id="091cf-242">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="091cf-243">Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), erscheint das Flyout-Fenster **Massenaktionen**, in dem Sie die folgenden Aktionen durchführen können:</span><span class="sxs-lookup"><span data-stu-id="091cf-243">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="091cf-244">**Nachrichten freigeben**: Die Optionen sind die gleichen wie bei der Freigabe einer einzelnen Nachricht, außer dass Sie nicht **Nachrichten an bestimmte Empfänger freigeben** auswählen können; Sie können nur **Nachricht an alle Empfänger freigeben** oder **Nachrichten an andere Personen freigeben** auswählen.</span><span class="sxs-lookup"><span data-stu-id="091cf-244">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="091cf-245">Berücksichtigen Sie das folgende Szenario: john@gmail.com sendet eine Nachricht an faith@contoso.com und john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="091cf-245">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="091cf-246">Gmail bifurcas diese Nachricht in zwei Kopien, die beide als Phishing in Microsoft in Quarantäne geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="091cf-246">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="091cf-247">Ein Administrator gibt beide dieser Nachrichten an admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="091cf-247">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="091cf-248">Die erste veröffentlichte Nachricht, die das Administratorpostfach erreicht, wird zugestellt.</span><span class="sxs-lookup"><span data-stu-id="091cf-248">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="091cf-249">Die zweite freigegebene Nachricht wird als doppelte Zustellung identifiziert und übersprungen.</span><span class="sxs-lookup"><span data-stu-id="091cf-249">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="091cf-250">Nachrichten werden als Duplikate identifiziert, wenn sie die gleiche Nachrichten-ID und die gleiche Empfangenszeit haben.</span><span class="sxs-lookup"><span data-stu-id="091cf-250">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="091cf-251">**Nachrichten löschen:** Nachdem Sie **in** der angezeigten Warnung auf Ja geklickt haben, werden die Nachrichten sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="091cf-251">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="091cf-252">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="091cf-252">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="091cf-253">Nur Microsoft Defender für Office 365: Verwenden des Security & Compliance Center zum Verwalten isolierter Dateien</span><span class="sxs-lookup"><span data-stu-id="091cf-253">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="091cf-254">Die Verfahren für isolierte Dateien in diesem Abschnitt sind nur für Microsoft Defender für Office 365 Plan 1- und Plan 2-Abonnenten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="091cf-254">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="091cf-255">In Organisationen mit Defender for Office 365 können Administratoren isolierte Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams verwalten.</span><span class="sxs-lookup"><span data-stu-id="091cf-255">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="091cf-256">Informationen zum Aktivieren des Schutzes für diese Dateien finden Sie [unter Aktivieren sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="091cf-256">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="091cf-257">Anzeigen von isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="091cf-257">View quarantined files</span></span>

1. <span data-ttu-id="091cf-258">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="091cf-258">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="091cf-259">Ändern **der In Quarantäne isolierten** Ansicht in die **Wertdateien**.</span><span class="sxs-lookup"><span data-stu-id="091cf-259">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="091cf-260">Sie können nach einem Feld sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="091cf-260">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="091cf-261">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="091cf-261">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="091cf-262">Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="091cf-262">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="091cf-263">Die Standardspalten sind mit einem Sternchen ( <sup>\*</sup> ) gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="091cf-263">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="091cf-264">**Benutzer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="091cf-264">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="091cf-265">**Speicherort**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="091cf-265">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="091cf-266">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="091cf-266">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="091cf-267">**Datei-URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="091cf-267">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="091cf-268">**Dateigröße**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="091cf-268">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="091cf-269">**Läuft ab**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="091cf-269">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="091cf-270">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="091cf-270">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="091cf-271">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="091cf-271">**Detected by**</span></span>
   - <span data-ttu-id="091cf-272">**Nach Zeit geändert**</span><span class="sxs-lookup"><span data-stu-id="091cf-272">**Modified by time**</span></span>

4. <span data-ttu-id="091cf-273">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="091cf-273">To filter the results, click **Filter**.</span></span> <span data-ttu-id="091cf-274">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="091cf-274">The available filters are:</span></span>

   - <span data-ttu-id="091cf-275">**Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="091cf-275">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="091cf-276">**Heute**</span><span class="sxs-lookup"><span data-stu-id="091cf-276">**Today**</span></span>
     - <span data-ttu-id="091cf-277">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="091cf-277">**Next 2 days**</span></span>
     - <span data-ttu-id="091cf-278">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="091cf-278">**Next 7 days**</span></span>
     - <span data-ttu-id="091cf-279">Ein benutzerdefinierter Datums-/Uhrzeitbereich.</span><span class="sxs-lookup"><span data-stu-id="091cf-279">A custom date/time range.</span></span>
   - <span data-ttu-id="091cf-280">**Empfangene Zeit**</span><span class="sxs-lookup"><span data-stu-id="091cf-280">**Received time**</span></span>
   - <span data-ttu-id="091cf-281">**Quarantänegrund**: Der einzige verfügbare Wert ist **Schadsoftware**.</span><span class="sxs-lookup"><span data-stu-id="091cf-281">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="091cf-282">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="091cf-282">**Policy type**</span></span>

<span data-ttu-id="091cf-283">Nachdem Sie eine bestimmte isolierte Datei finden, wählen Sie die Datei aus, um Details dazu anzuzeigen und Maßnahmen zu ergreifen (z. B. Anzeigen, Veröffentlichen, Herunterladen oder Löschen der Nachricht).</span><span class="sxs-lookup"><span data-stu-id="091cf-283">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="091cf-284">Anzeigen von Details zu isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="091cf-284">View quarantined file details</span></span>

<span data-ttu-id="091cf-285">Wenn Sie eine Datei in der Liste auswählen, werden die folgenden Dateidetails im **Flyoutbereich Details** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="091cf-285">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="091cf-286">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="091cf-286">**File Name**</span></span>
- <span data-ttu-id="091cf-287">**Datei-URL**: URL, die den Speicherort der Datei definiert (z. B. in SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="091cf-287">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="091cf-288">**Schädliche Inhalte, die auf erkannt werden** Datum/Uhrzeit der Quarantäne der Datei.</span><span class="sxs-lookup"><span data-stu-id="091cf-288">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="091cf-289">**Läuft ab:** Das Datum, an dem die Datei aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="091cf-289">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="091cf-290">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span><span class="sxs-lookup"><span data-stu-id="091cf-290">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="091cf-291">**Veröffentlicht?**</span><span class="sxs-lookup"><span data-stu-id="091cf-291">**Released?**</span></span>
- <span data-ttu-id="091cf-292">**Schadsoftwarename**</span><span class="sxs-lookup"><span data-stu-id="091cf-292">**Malware Name**</span></span>
- <span data-ttu-id="091cf-293">**Dokument-ID**: Ein eindeutiger Bezeichner für das Dokument.</span><span class="sxs-lookup"><span data-stu-id="091cf-293">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="091cf-294">**Dateigröße**: In Kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="091cf-294">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="091cf-295">**Organisation** Die eindeutige ID Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="091cf-295">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="091cf-296">**Zuletzt geändert**</span><span class="sxs-lookup"><span data-stu-id="091cf-296">**Last modified**</span></span>
- <span data-ttu-id="091cf-297">**Geändert von**: Der Benutzer, der die Datei zuletzt geändert hat.</span><span class="sxs-lookup"><span data-stu-id="091cf-297">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="091cf-298">**Secure Hash Algorithm 256-bit (SHA-256)-Wert:** Sie können diesen Hashwert verwenden, um die Datei in anderen Reputationsspeichern oder an anderen Speicherorten in Ihrer Umgebung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="091cf-298">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="091cf-299">Ergreifen von Maßnahmen für isolierte Dateien</span><span class="sxs-lookup"><span data-stu-id="091cf-299">Take action on quarantined files</span></span>

<span data-ttu-id="091cf-300">Wenn Sie eine Datei in der Liste auswählen, können Sie die folgenden Aktionen für die Datei im **Flyoutbereich Details** ausführen:</span><span class="sxs-lookup"><span data-stu-id="091cf-300">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="091cf-301">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click Release **files**.</span><span class="sxs-lookup"><span data-stu-id="091cf-301">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="091cf-302">**Datei herunterladen**</span><span class="sxs-lookup"><span data-stu-id="091cf-302">**Download file**</span></span>
- <span data-ttu-id="091cf-303">**Entfernen der Datei aus der Quarantäne**</span><span class="sxs-lookup"><span data-stu-id="091cf-303">**Remove file from quarantine**</span></span>

<span data-ttu-id="091cf-304">Wenn Sie die Dateien nicht veröffentlichen oder entfernen, werden sie nach Ablauf des Standardaufbewahrungszeitraums für Quarantäne gelöscht.</span><span class="sxs-lookup"><span data-stu-id="091cf-304">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="091cf-305">Aktionen für mehrere isolierte Dateien</span><span class="sxs-lookup"><span data-stu-id="091cf-305">Actions on multiple quarantined files</span></span>

<span data-ttu-id="091cf-306">Wenn Sie mehrere isolierte Dateien in der Liste auswählen  (bis zu 100), wird der Flyoutbereich Massenaktionen angezeigt, in dem Sie die folgenden Aktionen ausführen können:</span><span class="sxs-lookup"><span data-stu-id="091cf-306">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="091cf-307">**Freigabedateien**</span><span class="sxs-lookup"><span data-stu-id="091cf-307">**Release files**</span></span>
- <span data-ttu-id="091cf-308">**Dateien löschen:** Nachdem Sie **in** der angezeigten Warnung auf Ja geklickt haben, werden die Dateien sofort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="091cf-308">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="091cf-309">Verwenden von Exchange Online PowerShell oder eigenständiger EOP PowerShell zum Anzeigen und Verwalten isolierter Nachrichten und Dateien</span><span class="sxs-lookup"><span data-stu-id="091cf-309">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="091cf-310">Die cmdlets, die Sie zum Anzeigen und Verwalten von Nachrichten und Dateien in Quarantäne verwenden, sind:</span><span class="sxs-lookup"><span data-stu-id="091cf-310">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="091cf-311">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="091cf-311">Delete-QuarantineMessage</span></span>](/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="091cf-312">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="091cf-312">Export-QuarantineMessage</span></span>](/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="091cf-313">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="091cf-313">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="091cf-314">[Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): Beachten Sie, dass dieses Cmdlet nur für Nachrichten und nicht für Isolierte Dateien aus sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="091cf-314">[Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not quarantined files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="091cf-315">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="091cf-315">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)

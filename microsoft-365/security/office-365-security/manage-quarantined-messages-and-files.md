---
title: Verwalten von Nachrichten und Dateien in Quarantäne als Administrator
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
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
description: Administratoren erfahren, wie Sie isolierte Nachrichten für alle Benutzer in Exchange Online Protection (EoP) anzeigen und verwalten können. Administratoren in Organisationen mit Microsoft Defender für Office 365 können auch unter Quarantäne gestellte Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams verwalten.
ms.openlocfilehash: 94dfc8503d61c16aadc8e9d0ccfd295e2684fbba
ms.sourcegitcommit: 1db81b85d327fe423695ce675ad325e538417211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49349280"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="62d5e-104">Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP</span><span class="sxs-lookup"><span data-stu-id="62d5e-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="62d5e-105">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="62d5e-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="62d5e-106">Weitere Informationen finden Sie unter [Quarantäne-e-Mail-Nachrichten in EoP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="62d5e-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="62d5e-107">Administratoren können alle Arten von isolierten Nachrichten für alle Benutzer anzeigen, freigeben und löschen.</span><span class="sxs-lookup"><span data-stu-id="62d5e-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="62d5e-108">Nur Administratoren können Nachrichten verwalten, die als Schadsoftware, als hochgradig vertrauenswürdiges Phishing oder als Ergebnis von Nachrichtenfluss Regeln (auch bekannt als Transportregeln) isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="62d5e-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="62d5e-109">Administratoren können auch falsch positive Ergebnisse an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="62d5e-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="62d5e-110">Administratoren in Organisationen mit Microsoft Defender für Office 365 können auch unter Quarantäne gestellte Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams anzeigen, herunterladen und löschen.</span><span class="sxs-lookup"><span data-stu-id="62d5e-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="62d5e-111">Sie können isolierte Nachrichten im Security & Compliance Center oder in PowerShell anzeigen und verwalten (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer).</span><span class="sxs-lookup"><span data-stu-id="62d5e-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="62d5e-112">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="62d5e-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="62d5e-113">Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="62d5e-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="62d5e-114">Um die Quarantäne-Seite direkt zu öffnen, wechseln Sie zu <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="62d5e-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="62d5e-115">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="62d5e-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="62d5e-116">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="62d5e-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="62d5e-117">Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Quarantäne als Administrator verwalten können. Die Berechtigungen werden durch die **Quarantäne** Rolle im Security & Compliance Center gesteuert.</span><span class="sxs-lookup"><span data-stu-id="62d5e-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="62d5e-118">Diese Rolle wird standardmäßig der Rollengruppe **Organisationsverwaltung** (Global Admins), **Quarantine Administrator** und **Sicherheitsadministrator** im Security & Compliance Center zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="62d5e-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="62d5e-119">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="62d5e-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="62d5e-120">Isolierte Nachrichten werden für einen Standardzeitraum aufbewahrt, bevor Sie automatisch gelöscht werden:</span><span class="sxs-lookup"><span data-stu-id="62d5e-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="62d5e-121">30 Tage für Nachrichten, die durch Anti-Spam-Richtlinien (Spam, Phishing und Massen-e-Mails) unter Quarantäne gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="62d5e-121">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="62d5e-122">Dies ist der Standard-und Höchstwert.</span><span class="sxs-lookup"><span data-stu-id="62d5e-122">This is the default and maximum value.</span></span> <span data-ttu-id="62d5e-123">Informationen zum Konfigurieren (senken) dieses Werts finden Sie unter [configure Anti-Spam Policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="62d5e-123">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="62d5e-124">15 Tage für Nachrichten, die Schadsoftware enthalten.</span><span class="sxs-lookup"><span data-stu-id="62d5e-124">15 days for messages that contain malware.</span></span>

  - <span data-ttu-id="62d5e-125">15 Tage für Dateien, die von ATP für SharePoint, OneDrive und Microsoft Teams in Defender für Office 365 unter Quarantäne gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="62d5e-125">15 days for files quarantined by ATP for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="62d5e-126">Wenn eine Nachricht aus der Quarantäne abläuft, können Sie Sie nicht wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="62d5e-126">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="62d5e-127">Verwenden des Security & Compliance Center zum Verwalten von e-Mail-Nachrichten in Quarantäne</span><span class="sxs-lookup"><span data-stu-id="62d5e-127">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="62d5e-128">Anzeigen von e-Mails in Quarantäne</span><span class="sxs-lookup"><span data-stu-id="62d5e-128">View quarantined email</span></span>

1. <span data-ttu-id="62d5e-129">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="62d5e-129">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="62d5e-130">Stellen Sie sicher, dass **Quarantäne anzeigen** auf den Standardwert **E-Mail** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="62d5e-130">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="62d5e-131">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="62d5e-131">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="62d5e-132">Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="62d5e-132">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="62d5e-133">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="62d5e-133">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="62d5e-134">**Empfangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62d5e-134">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="62d5e-135">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62d5e-135">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="62d5e-136">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62d5e-136">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="62d5e-137">**Quarantänegrund**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62d5e-137">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="62d5e-138">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62d5e-138">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="62d5e-139">**Richtlinientyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62d5e-139">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="62d5e-140">**Expires**</span><span class="sxs-lookup"><span data-stu-id="62d5e-140">**Expires**</span></span>
   - <span data-ttu-id="62d5e-141">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="62d5e-141">**Recipient**</span></span>
   - <span data-ttu-id="62d5e-142">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="62d5e-142">**Message ID**</span></span>
   - <span data-ttu-id="62d5e-143">**Name der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="62d5e-143">**Policy name**</span></span>
   - <span data-ttu-id="62d5e-144">**Größe**</span><span class="sxs-lookup"><span data-stu-id="62d5e-144">**Size**</span></span>
   - <span data-ttu-id="62d5e-145">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="62d5e-145">**Direction**</span></span>

   <span data-ttu-id="62d5e-146">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**, oder klicken Sie auf **Als Standard festlegen**.</span><span class="sxs-lookup"><span data-stu-id="62d5e-146">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="62d5e-147">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="62d5e-147">To filter the results, click **Filter**.</span></span> <span data-ttu-id="62d5e-148">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="62d5e-148">The available filters are:</span></span>

   - <span data-ttu-id="62d5e-149">**Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="62d5e-149">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="62d5e-150">**Heute**</span><span class="sxs-lookup"><span data-stu-id="62d5e-150">**Today**</span></span>
     - <span data-ttu-id="62d5e-151">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="62d5e-151">**Next 2 days**</span></span>
     - <span data-ttu-id="62d5e-152">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="62d5e-152">**Next 7 days**</span></span>
     - <span data-ttu-id="62d5e-153">**Benutzerdefiniert**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="62d5e-153">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="62d5e-154">**Empfangszeit**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="62d5e-154">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="62d5e-155">**Quarantänegrund**:</span><span class="sxs-lookup"><span data-stu-id="62d5e-155">**Quarantine reason**:</span></span>
     - <span data-ttu-id="62d5e-156">**Richtlinie**: die Nachricht stimmte mit den Bedingungen einer Nachrichtenfluss Regel überein (auch als Transportregel bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="62d5e-156">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="62d5e-157">**Massensendung**</span><span class="sxs-lookup"><span data-stu-id="62d5e-157">**Bulk**</span></span>
     - <span data-ttu-id="62d5e-158">**Phishing**: das Spamfilter Urteil lautete, dass die Nachricht durch **Phishing-e-Mails** oder Anti-Phishing-schutzisoliert wurde ([Spoof-Einstellungen](set-up-anti-phishing-policies.md#spoof-settings) oder [Identitätswechsel Schutz](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="62d5e-158">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="62d5e-159">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="62d5e-159">**Malware**</span></span>
     - <span data-ttu-id="62d5e-160">**Spam**</span><span class="sxs-lookup"><span data-stu-id="62d5e-160">**Spam**</span></span>
     - <span data-ttu-id="62d5e-161">**Phishing mit hoher Zuverlässigkeit**</span><span class="sxs-lookup"><span data-stu-id="62d5e-161">**High Confidence Phish**</span></span>

   - <span data-ttu-id="62d5e-162">**Richtlinientyp**: Filtern von Nachrichten nach Richtlinientyp:</span><span class="sxs-lookup"><span data-stu-id="62d5e-162">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="62d5e-163">**Anti-Malware-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="62d5e-163">**Anti-malware policy**</span></span>
     - <span data-ttu-id="62d5e-164">**Richtlinie für sichere Anlagen**</span><span class="sxs-lookup"><span data-stu-id="62d5e-164">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="62d5e-165">**Antiphishing-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="62d5e-165">**Anti-phish policy**</span></span>
     - <span data-ttu-id="62d5e-166">**Richtlinie für gehostete Inhaltsfilter** (Anti-Spam-Richtlinie)</span><span class="sxs-lookup"><span data-stu-id="62d5e-166">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="62d5e-167">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="62d5e-167">**Transport rule**</span></span>

   - <span data-ttu-id="62d5e-168">**E-Mail-Empfänger**: alle Benutzer oder nur an Sie gesendete Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="62d5e-168">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="62d5e-169">Endbenutzer können nur isolierte Nachrichten verwalten, die an Sie gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="62d5e-169">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="62d5e-170">Klicken Sie auf **Löschen**, um den Filter zu löschen.</span><span class="sxs-lookup"><span data-stu-id="62d5e-170">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="62d5e-171">Um das Filter-Flyout auszublenden, klicken Sie erneut auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="62d5e-171">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="62d5e-172">Verwenden Sie **Ergebnisse sortieren nach** (standardmäßig die Schaltfläche **Nachrichten-ID**) und einen entsprechenden Wert, um bestimmte Nachrichten zu finden.</span><span class="sxs-lookup"><span data-stu-id="62d5e-172">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="62d5e-173">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="62d5e-173">Wildcards aren't supported.</span></span> <span data-ttu-id="62d5e-174">Sie können nach den folgenden Werten suchen:</span><span class="sxs-lookup"><span data-stu-id="62d5e-174">You can search by the following values:</span></span>

   - <span data-ttu-id="62d5e-175">**Nachrichten-ID**: Die globale eindeutige ID der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="62d5e-175">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="62d5e-176">Beispielsweise haben Sie die [Nachrichtenablaufverfolgung](message-trace-scc.md) verwendet, um nach einer Nachricht zu suchen, die an einen Benutzer in Ihrer Organisation gesendet wurde, und Sie bestimmen, dass die Nachricht in Quarantäne statt übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="62d5e-176">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="62d5e-177">Achten Sie darauf, den vollständigen Meldungs-ID-Wert einzuschließen, der möglicherweise spitzen Klammern ( \<\> ) enthält.</span><span class="sxs-lookup"><span data-stu-id="62d5e-177">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="62d5e-178">Zum Beispiel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="62d5e-178">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="62d5e-179">**E-Mail-Adresse des Absenders**: Die E-Mail-Adresse eines einzelnen Absenders.</span><span class="sxs-lookup"><span data-stu-id="62d5e-179">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="62d5e-180">**Richtlinienname**: Verwenden Sie den vollständigen Namen der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="62d5e-180">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="62d5e-181">Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="62d5e-181">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="62d5e-182">**E-Mail-Adresse des Empfängers**: Die E-Mail-Adresse eines einzelnen Empfängers.</span><span class="sxs-lookup"><span data-stu-id="62d5e-182">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="62d5e-183">**Betreff**: Verwenden Sie den gesamten Betreff der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="62d5e-183">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="62d5e-184">Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="62d5e-184">The search is not case-sensitive.</span></span>
  
   - <span data-ttu-id="62d5e-185">**Richtlinienname**: der Name der Richtlinie, die für die Quarantäne der Nachricht verantwortlich war.</span><span class="sxs-lookup"><span data-stu-id="62d5e-185">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="62d5e-186">Nachdem Sie die Suchkriterien eingegeben haben, klicken Sie auf die ![Schaltfläche Aktualisieren](../../media/scc-quarantine-refresh.png) **Aktualisieren**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="62d5e-186">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="62d5e-187">Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Maßnahmen zu ergreifen (z. B. die Nachricht anzeigen, freigeben, herunterladen oder löschen).</span><span class="sxs-lookup"><span data-stu-id="62d5e-187">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="62d5e-188">Anzeigen von Details der isolierten Nachricht</span><span class="sxs-lookup"><span data-stu-id="62d5e-188">View quarantined message details</span></span>

<span data-ttu-id="62d5e-189">Wenn Sie eine E-Mail-Nachricht in der Liste auswählen, werden die folgenden Nachrichtendetails im Flyout-Fenster **Details** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="62d5e-189">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="62d5e-190">**Nachrichten-ID**: Die globale eindeutige ID für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="62d5e-190">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="62d5e-191">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="62d5e-191">**Sender address**</span></span>

- <span data-ttu-id="62d5e-192">**Empfangen**: Das Datum/die Uhrzeit des Nachrichtenempfangs.</span><span class="sxs-lookup"><span data-stu-id="62d5e-192">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="62d5e-193">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="62d5e-193">**Subject**</span></span>

- <span data-ttu-id="62d5e-194">**Quarantäne Grund**: zeigt an, ob eine Nachricht als **Spam**, **Massen**, **Phishing**, Übereinstimmung mit einer Nachrichtenfluss Regel (**Transport Regel**) identifiziert wurde oder als enthaltender **Schadsoftware** erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="62d5e-194">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="62d5e-195">**Empfängeranzahl**</span><span class="sxs-lookup"><span data-stu-id="62d5e-195">**Recipient count**</span></span>

- <span data-ttu-id="62d5e-196">**Empfänger**: Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Vorschau der Nachricht anzeigen** oder **Nachrichten** Kopfzeile anzeigen klicken, um die gesamte Liste der Empfänger anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="62d5e-196">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="62d5e-197">**Läuft ab**. Das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="62d5e-197">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="62d5e-198">**Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="62d5e-198">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="62d5e-199">**Noch nicht freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht noch nicht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="62d5e-199">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="62d5e-200">Maßnahmen für isolierte E-Mails ergreifen</span><span class="sxs-lookup"><span data-stu-id="62d5e-200">Take action on quarantined email</span></span>

<span data-ttu-id="62d5e-201">Nachdem Sie eine Nachricht ausgewählt haben, haben Sie mehrere Möglichkeiten, mit den Nachrichten im **Detail** -Flyout-Bereich zu tun:</span><span class="sxs-lookup"><span data-stu-id="62d5e-201">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="62d5e-202">**Nachricht freigeben**: Wählen Sie im eingeblendeten Flyout-Bereich die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="62d5e-202">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="62d5e-203">**Melden von Nachrichten an Microsoft zur Analyse**: diese Option ist standardmäßig aktiviert und meldet die irrtümlich unter Quarantäne gestellte Nachricht an Microsoft als falsch positiv.</span><span class="sxs-lookup"><span data-stu-id="62d5e-203">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="62d5e-204">Wenn die Nachricht als Spam, Massen, Phishing oder mit Schadsoftware isoliert wurde, wird die Nachricht auch an das Microsoft-Spam Analyse Team gemeldet.</span><span class="sxs-lookup"><span data-stu-id="62d5e-204">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="62d5e-205">Je nach Analyse werden die Dienst weiten spamfilterregeln möglicherweise angepasst, um die Nachricht durch zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="62d5e-205">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="62d5e-206">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="62d5e-206">Choose one of the following options:</span></span>
    - <span data-ttu-id="62d5e-207">**Freigeben von Nachrichten für alle Empfänger**</span><span class="sxs-lookup"><span data-stu-id="62d5e-207">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="62d5e-208">**Freigeben von Nachrichten an bestimmte Empfänger**</span><span class="sxs-lookup"><span data-stu-id="62d5e-208">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="62d5e-209">**Freigeben von Nachrichten für andere Personen**</span><span class="sxs-lookup"><span data-stu-id="62d5e-209">**Release messages to other people**</span></span>

  <span data-ttu-id="62d5e-210">Klicken Sie nach Abschluss des Vorgangs auf **Nachrichten freigeben**.</span><span class="sxs-lookup"><span data-stu-id="62d5e-210">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="62d5e-211">Hinweise zum Freigeben von Nachrichten:</span><span class="sxs-lookup"><span data-stu-id="62d5e-211">Notes about releasing messages:</span></span>

  - <span data-ttu-id="62d5e-212">Sie können eine Nachricht nur einmal an denselben Empfänger freigeben.</span><span class="sxs-lookup"><span data-stu-id="62d5e-212">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="62d5e-213">Nur Empfänger, die die Nachricht nicht erhalten haben, werden in der Liste der potenziellen Empfänger angezeigt.</span><span class="sxs-lookup"><span data-stu-id="62d5e-213">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="62d5e-214">**Nachrichtenkopf anzeigen**: Wählen Sie diesen Link aus, um den Nachrichtenkopftext anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="62d5e-214">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="62d5e-215">Um den Nachrichtenkopf im Detail zu analysieren, kopieren Sie den Nachrichtenkopftext in die Zwischenablage, und wählen Sie dann **Microsoft-Nachrichtenkopfanalyse** aus, um zur Remoteverbindungsuntersuchung zu wechseln (klicken Sie mit der rechten Maustaste, und wählen Sie **In neuer Registerkarte öffnen** aus, wenn Sie Microsoft 365 nicht verlassen möchten, um die Aufgabe auszuführen).</span><span class="sxs-lookup"><span data-stu-id="62d5e-215">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="62d5e-216">Fügen Sie den Nachrichtenkopf auf der Seite in den Abschnitt "Nachrichtenkopfanalyse" ein, und wählen Sie dann **Kopfzeilen analysieren** aus:</span><span class="sxs-lookup"><span data-stu-id="62d5e-216">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="62d5e-217">**Vorschau der Nachricht anzeigen**: Wählen Sie im angezeigten Flyout-Fenster eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="62d5e-217">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="62d5e-218">**Quellansicht**: Zeigt die HTML-Version des Nachrichtentextes an, wobei alle Links deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="62d5e-218">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="62d5e-219">**Textansicht**: Zeigt den Nachrichtentext im Klartext an.</span><span class="sxs-lookup"><span data-stu-id="62d5e-219">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="62d5e-220">**Aus Quarantäne entfernen**: Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="62d5e-220">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="62d5e-221">**Nachricht herunterladen**: Wählen Sie im daraufhin angezeigten Flyout-Fenster **Ich verstehe die Risiken beim Herunterladen dieser Nachricht** aus, um eine lokale Kopie der Nachricht im eml-Format zu speichern.</span><span class="sxs-lookup"><span data-stu-id="62d5e-221">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="62d5e-222">**Nachricht übermitteln**: Wählen Sie im eingeblendeten Flyout-Bereich die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="62d5e-222">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="62d5e-223">**Objekttyp**: **e-Mail** (Standard), **URL** oder **Anlage**.</span><span class="sxs-lookup"><span data-stu-id="62d5e-223">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="62d5e-224">**Übermittlungs Format**: **Netzwerknachrichten-ID** (Standard, mit dem entsprechenden Wert im Feld **Netzwerknachrichten-ID** ) oder **Datei** (wechseln Sie zu einer lokalen eml-oder msg-Datei).</span><span class="sxs-lookup"><span data-stu-id="62d5e-224">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="62d5e-225">Beachten Sie Folgendes: Wenn Sie **Datei** auswählen und dann **Netzwerknachrichten-ID** auswählen, ist der anfängliche Wert nicht mehr vorhanden.</span><span class="sxs-lookup"><span data-stu-id="62d5e-225">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="62d5e-226">**Recipients**: Geben Sie bei Lease einen ursprünglichen Empfänger der Nachricht ein, oder klicken Sie auf **Alles auswählen** , um alle Empfänger zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="62d5e-226">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="62d5e-227">Sie können auch auf **Alle auswählen** klicken und dann einzelne Empfänger selektiv entfernen.</span><span class="sxs-lookup"><span data-stu-id="62d5e-227">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="62d5e-228">**Grund für die Übermittlung**: **sollte nicht blockiert worden sein** (Standard) oder hätte **blockiert werden** müssen.</span><span class="sxs-lookup"><span data-stu-id="62d5e-228">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="62d5e-229">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="62d5e-229">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="62d5e-230">Wenn Sie die Nachricht nicht freigeben oder entfernen, wird sie nach Ablauf der Standard-Quarantäneaufbewahrungszeit gelöscht.</span><span class="sxs-lookup"><span data-stu-id="62d5e-230">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="62d5e-231">Maßnahmen für mehrere isolierte E-Mail-Nachrichten ergreifen</span><span class="sxs-lookup"><span data-stu-id="62d5e-231">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="62d5e-232">Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), erscheint das Flyout-Fenster **Massenaktionen**, in dem Sie die folgenden Aktionen durchführen können:</span><span class="sxs-lookup"><span data-stu-id="62d5e-232">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="62d5e-233">**Nachrichten freigeben**: Die Optionen sind die gleichen wie bei der Freigabe einer einzelnen Nachricht, außer dass Sie nicht **Nachrichten an bestimmte Empfänger freigeben** auswählen können; Sie können nur **Nachricht an alle Empfänger freigeben** oder **Nachrichten an andere Personen freigeben** auswählen.</span><span class="sxs-lookup"><span data-stu-id="62d5e-233">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="62d5e-234">Nehmen Sie das folgende Szenario in Frage: John@gmail.com sendet eine Nachricht an Faith@contoso.com und John@Subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="62d5e-234">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="62d5e-235">Gmail verzweigt diese Nachricht in zwei Kopien, die an die Quarantäne als Phishing in Microsoft weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="62d5e-235">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="62d5e-236">Ein Administrator gibt beide Nachrichten an admin@contoso.com frei.</span><span class="sxs-lookup"><span data-stu-id="62d5e-236">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="62d5e-237">Die erste freigegebene Nachricht, die das Administratorpostfach erreicht, wird übermittelt.</span><span class="sxs-lookup"><span data-stu-id="62d5e-237">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="62d5e-238">Die zweite freigegebene Nachricht wird als doppelte Zustellung identifiziert und übersprungen.</span><span class="sxs-lookup"><span data-stu-id="62d5e-238">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="62d5e-239">Nachricht werden als Duplikate identifiziert, wenn Sie dieselbe Nachrichten-ID und dieselbe Empfangszeit haben.</span><span class="sxs-lookup"><span data-stu-id="62d5e-239">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="62d5e-240">**Nachrichten löschen**: Nachdem Sie in der angezeigten Warnung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="62d5e-240">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="62d5e-241">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="62d5e-241">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="62d5e-242">Microsoft Defender nur für Office 365: Verwenden des Security & Compliance Center zum Verwalten von isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="62d5e-242">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="62d5e-243">Die Verfahren für in Quarantäne befindliche Dateien in diesem Abschnitt stehen nur für Microsoft Defender für Office 365 Plan 1 und Plan 2 Subscriber zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="62d5e-243">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="62d5e-244">In Organisationen mit Defender für Office 365 können Administratoren isolierte Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams verwalten.</span><span class="sxs-lookup"><span data-stu-id="62d5e-244">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="62d5e-245">Informationen zum Aktivieren des Schutzes für diese Dateien finden Sie unter [Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="62d5e-245">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="62d5e-246">Anzeigen von isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="62d5e-246">View quarantined files</span></span>

1. <span data-ttu-id="62d5e-247">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="62d5e-247">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="62d5e-248">Ändern Sie die Ansicht in den Wert **Dateien** in **Quarantäne** .</span><span class="sxs-lookup"><span data-stu-id="62d5e-248">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="62d5e-249">Sie können nach einem Feld sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="62d5e-249">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="62d5e-250">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="62d5e-250">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="62d5e-251">Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="62d5e-251">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="62d5e-252">Die Standardspalten sind mit einem Sternchen ( <sup>\*</sup> ) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="62d5e-252">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="62d5e-253">**Benutzer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62d5e-253">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="62d5e-254">**Speicherort**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62d5e-254">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="62d5e-255">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62d5e-255">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="62d5e-256">**Datei-URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62d5e-256">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="62d5e-257">**Dateigröße**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62d5e-257">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="62d5e-258">**Läuft ab**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62d5e-258">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="62d5e-259">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="62d5e-259">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="62d5e-260">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="62d5e-260">**Detected by**</span></span>
   - <span data-ttu-id="62d5e-261">**Geändert von Zeit**</span><span class="sxs-lookup"><span data-stu-id="62d5e-261">**Modified by time**</span></span>

4. <span data-ttu-id="62d5e-262">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="62d5e-262">To filter the results, click **Filter**.</span></span> <span data-ttu-id="62d5e-263">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="62d5e-263">The available filters are:</span></span>

   - <span data-ttu-id="62d5e-264">**Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="62d5e-264">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="62d5e-265">**Heute**</span><span class="sxs-lookup"><span data-stu-id="62d5e-265">**Today**</span></span>
     - <span data-ttu-id="62d5e-266">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="62d5e-266">**Next 2 days**</span></span>
     - <span data-ttu-id="62d5e-267">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="62d5e-267">**Next 7 days**</span></span>
     - <span data-ttu-id="62d5e-268">Ein benutzerdefiniertes Datum/Zeitintervall.</span><span class="sxs-lookup"><span data-stu-id="62d5e-268">A custom date/time range.</span></span>
   - <span data-ttu-id="62d5e-269">**Empfangszeit**</span><span class="sxs-lookup"><span data-stu-id="62d5e-269">**Received time**</span></span>
   - <span data-ttu-id="62d5e-270">**Quarantäne Grund**: der einzige verfügbare Wert ist **Schadsoftware**.</span><span class="sxs-lookup"><span data-stu-id="62d5e-270">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="62d5e-271">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="62d5e-271">**Policy type**</span></span>

<span data-ttu-id="62d5e-272">Nachdem Sie eine bestimmte isolierte Datei gefunden haben, wählen Sie die Datei aus, um Details dazu anzuzeigen, und nehmen Sie Aktionen vor (beispielsweise anzeigen, freigeben, herunterladen oder Löschen der Nachricht).</span><span class="sxs-lookup"><span data-stu-id="62d5e-272">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="62d5e-273">Anzeigen von Details in isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="62d5e-273">View quarantined file details</span></span>

<span data-ttu-id="62d5e-274">Wenn Sie eine Datei in der Liste auswählen, werden im **Detail** -Flyout-Bereich die folgenden Dateidetails angezeigt:</span><span class="sxs-lookup"><span data-stu-id="62d5e-274">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="62d5e-275">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="62d5e-275">**File Name**</span></span>
- <span data-ttu-id="62d5e-276">**Datei-URL**: URL, die den Speicherort der Datei definiert (beispielsweise in SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="62d5e-276">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="62d5e-277">**Böswilliger Inhalt erkannt in** Das Datum/die Uhrzeit, zu dem die Datei isoliert wurde.</span><span class="sxs-lookup"><span data-stu-id="62d5e-277">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="62d5e-278">**Expires**: das Datum, an dem die Datei aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="62d5e-278">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="62d5e-279">**Erkannt von**: Defender für Office 365 oder Microsofts Anti-Malware Engine.</span><span class="sxs-lookup"><span data-stu-id="62d5e-279">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="62d5e-280">**Veröffentlicht?**</span><span class="sxs-lookup"><span data-stu-id="62d5e-280">**Released?**</span></span>
- <span data-ttu-id="62d5e-281">**Name der Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="62d5e-281">**Malware Name**</span></span>
- <span data-ttu-id="62d5e-282">**Dokument-ID**: ein eindeutiger Bezeichner für das Dokument.</span><span class="sxs-lookup"><span data-stu-id="62d5e-282">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="62d5e-283">**Dateigröße**: in Kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="62d5e-283">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="62d5e-284">**Organisation** Die eindeutige ID Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="62d5e-284">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="62d5e-285">**Zuletzt geändert**</span><span class="sxs-lookup"><span data-stu-id="62d5e-285">**Last modified**</span></span>
- <span data-ttu-id="62d5e-286">**Geändert von**: der Benutzer, der die Datei zuletzt geändert hat.</span><span class="sxs-lookup"><span data-stu-id="62d5e-286">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="62d5e-287">**Secure Hash Algorithm 256-Bit (SHA-256)-Wert**: Sie können diesen Hashwert verwenden, um die Datei in anderen Reputation Stores oder an anderen Speicherorten in Ihrer Umgebung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="62d5e-287">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="62d5e-288">Ausführen von Aktionen für isolierte Dateien</span><span class="sxs-lookup"><span data-stu-id="62d5e-288">Take action on quarantined files</span></span>

<span data-ttu-id="62d5e-289">Wenn Sie eine Datei in der Liste auswählen, können Sie die folgenden Aktionen für die Datei im **Detail** -Flyout-Bereich ausführen:</span><span class="sxs-lookup"><span data-stu-id="62d5e-289">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="62d5e-290">**Dateien freigeben**: Wählen Sie (Standard) aus, oder heben Sie **die Auswahl von Berichtsdateien für Microsoft für die Analyse auf**, und klicken Sie dann auf **Dateien freigeben**.</span><span class="sxs-lookup"><span data-stu-id="62d5e-290">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="62d5e-291">**Datei herunterladen**</span><span class="sxs-lookup"><span data-stu-id="62d5e-291">**Download file**</span></span>
- <span data-ttu-id="62d5e-292">**Datei aus Quarantäne entfernen**</span><span class="sxs-lookup"><span data-stu-id="62d5e-292">**Remove file from quarantine**</span></span>

<span data-ttu-id="62d5e-293">Wenn Sie die Dateien nicht freigeben oder entfernen, werden Sie nach Ablauf der standardmäßigen Aufbewahrungszeit für Quarantäne gelöscht.</span><span class="sxs-lookup"><span data-stu-id="62d5e-293">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="62d5e-294">Aktionen für mehrere isolierte Dateien</span><span class="sxs-lookup"><span data-stu-id="62d5e-294">Actions on multiple quarantined files</span></span>

<span data-ttu-id="62d5e-295">Wenn Sie mehrere isolierte Dateien in der Liste auswählen (bis zu 100), wird der Flyout-Bereich **Massenaktionen** angezeigt, in dem Sie die folgenden Aktionen ausführen können:</span><span class="sxs-lookup"><span data-stu-id="62d5e-295">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="62d5e-296">**Veröffentlichungsdateien**</span><span class="sxs-lookup"><span data-stu-id="62d5e-296">**Release files**</span></span>
- <span data-ttu-id="62d5e-297">**Dateien löschen**: Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, werden die Dateien sofort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="62d5e-297">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="62d5e-298">Verwenden Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Anzeigen und Verwalten von isolierten Nachrichten und Dateien</span><span class="sxs-lookup"><span data-stu-id="62d5e-298">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="62d5e-299">Folgende Cmdlets werden zum Anzeigen und Verwalten von Nachrichten und Dateien in der Quarantäne verwendet:</span><span class="sxs-lookup"><span data-stu-id="62d5e-299">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="62d5e-300">DELETE-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="62d5e-300">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="62d5e-301">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="62d5e-301">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="62d5e-302">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="62d5e-302">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="62d5e-303">[Vorschau-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Beachten Sie, dass dieses Cmdlet nur für Nachrichten gilt, nicht für Malware Dateien von ATP für SharePoint Online, OneDrive für Unternehmen oder Teams.</span><span class="sxs-lookup"><span data-stu-id="62d5e-303">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="62d5e-304">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="62d5e-304">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)

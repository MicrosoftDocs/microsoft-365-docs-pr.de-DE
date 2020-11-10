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
ms.openlocfilehash: 9d58f8c08d994e5e9736c8223239b54e52c4edab
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48951047"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="b252a-104">Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP</span><span class="sxs-lookup"><span data-stu-id="b252a-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b252a-105">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b252a-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="b252a-106">Weitere Informationen finden Sie unter [Quarantäne-e-Mail-Nachrichten in EoP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="b252a-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="b252a-107">Administratoren können alle Arten von isolierten Nachrichten für alle Benutzer anzeigen, freigeben und löschen.</span><span class="sxs-lookup"><span data-stu-id="b252a-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="b252a-108">Nur Administratoren können Nachrichten verwalten, die als Schadsoftware, als hochgradig vertrauenswürdiges Phishing oder als Ergebnis von Nachrichtenfluss Regeln (auch bekannt als Transportregeln) isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="b252a-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="b252a-109">Administratoren können auch falsch positive Ergebnisse an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="b252a-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="b252a-110">Administratoren in Organisationen mit Microsoft Defender für Office 365 können auch unter Quarantäne gestellte Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams anzeigen, herunterladen und löschen.</span><span class="sxs-lookup"><span data-stu-id="b252a-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="b252a-111">Sie können isolierte Nachrichten im Security & Compliance Center oder in PowerShell anzeigen und verwalten (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer).</span><span class="sxs-lookup"><span data-stu-id="b252a-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b252a-112">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="b252a-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b252a-113">Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="b252a-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="b252a-114">Um die Quarantäne-Seite direkt zu öffnen, wechseln Sie zu <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="b252a-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="b252a-115">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b252a-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b252a-116">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b252a-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b252a-117">Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Quarantäne als Administrator verwalten können. Die Berechtigungen werden durch die **Quarantäne** Rolle im Security & Compliance Center gesteuert.</span><span class="sxs-lookup"><span data-stu-id="b252a-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="b252a-118">Diese Rolle wird standardmäßig der Rollengruppe **Organisationsverwaltung** (Global Admins), **Quarantine Administrator** und **Sicherheitsadministrator** im Security & Compliance Center zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b252a-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator** , and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="b252a-119">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b252a-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="b252a-120">Isolierte Nachrichten werden für einen Standardzeitraum aufbewahrt, bevor Sie automatisch gelöscht werden:</span><span class="sxs-lookup"><span data-stu-id="b252a-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="b252a-121">Nachrichten, die von antispamregeln (Spam, Phishing und Massen-e-Mails) unter Quarantäne gestellt werden: 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="b252a-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="b252a-122">Dies ist der Standard-und Höchstwert.</span><span class="sxs-lookup"><span data-stu-id="b252a-122">This is the default and maximum value.</span></span> <span data-ttu-id="b252a-123">Informationen zum Konfigurieren dieses Werts finden Sie unter [configure Anti-Spam Policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b252a-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="b252a-124">Nachrichten, die Schadsoftware enthalten: 15 Tage.</span><span class="sxs-lookup"><span data-stu-id="b252a-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="b252a-125">Wenn eine Nachricht aus der Quarantäne abläuft, können Sie Sie nicht wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="b252a-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="b252a-126">Verwenden des Security & Compliance Center zum Verwalten von e-Mail-Nachrichten in Quarantäne</span><span class="sxs-lookup"><span data-stu-id="b252a-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="b252a-127">Anzeigen von e-Mails in Quarantäne</span><span class="sxs-lookup"><span data-stu-id="b252a-127">View quarantined email</span></span>

1. <span data-ttu-id="b252a-128">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="b252a-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="b252a-129">Stellen Sie sicher, dass **Quarantäne anzeigen** auf den Standardwert **E-Mail** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b252a-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="b252a-130">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="b252a-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="b252a-131">Klicken Sie auf **Spalten ändern** , um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b252a-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="b252a-132">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="b252a-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="b252a-133">**Empfangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b252a-133">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="b252a-134">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b252a-134">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="b252a-135">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b252a-135">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="b252a-136">**Quarantänegrund**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b252a-136">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="b252a-137">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b252a-137">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="b252a-138">**Richtlinientyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b252a-138">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="b252a-139">**Expires**</span><span class="sxs-lookup"><span data-stu-id="b252a-139">**Expires**</span></span>
   - <span data-ttu-id="b252a-140">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="b252a-140">**Recipient**</span></span>
   - <span data-ttu-id="b252a-141">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="b252a-141">**Message ID**</span></span>
   - <span data-ttu-id="b252a-142">**Name der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="b252a-142">**Policy name**</span></span>
   - <span data-ttu-id="b252a-143">**Größe**</span><span class="sxs-lookup"><span data-stu-id="b252a-143">**Size**</span></span>
   - <span data-ttu-id="b252a-144">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="b252a-144">**Direction**</span></span>

   <span data-ttu-id="b252a-145">Klicken Sie nach Abschluss des Vorgangs auf **Speichern** , oder klicken Sie auf **Als Standard festlegen**.</span><span class="sxs-lookup"><span data-stu-id="b252a-145">When you're finished, click **Save** , or click **Set to default**.</span></span>

4. <span data-ttu-id="b252a-146">Klicken Sie auf **Filter** , um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="b252a-146">To filter the results, click **Filter**.</span></span> <span data-ttu-id="b252a-147">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="b252a-147">The available filters are:</span></span>

   - <span data-ttu-id="b252a-148">**Ablaufzeit** : Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="b252a-148">**Expires time** : Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="b252a-149">**Heute**</span><span class="sxs-lookup"><span data-stu-id="b252a-149">**Today**</span></span>
     - <span data-ttu-id="b252a-150">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="b252a-150">**Next 2 days**</span></span>
     - <span data-ttu-id="b252a-151">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="b252a-151">**Next 7 days**</span></span>
     - <span data-ttu-id="b252a-152">**Benutzerdefiniert** : Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="b252a-152">**Custom** : Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="b252a-153">**Empfangszeit** : Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="b252a-153">**Received time** : Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="b252a-154">**Quarantänegrund** :</span><span class="sxs-lookup"><span data-stu-id="b252a-154">**Quarantine reason** :</span></span>
     - <span data-ttu-id="b252a-155">**Richtlinie** : die Nachricht stimmte mit den Bedingungen einer Nachrichtenfluss Regel überein (auch als Transportregel bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="b252a-155">**Policy** : The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="b252a-156">**Massensendung**</span><span class="sxs-lookup"><span data-stu-id="b252a-156">**Bulk**</span></span>
     - <span data-ttu-id="b252a-157">**Phishing** : das Spamfilter Urteil lautete, dass die Nachricht durch **Phishing-e-Mails** oder Anti-Phishing-schutzisoliert wurde ( [Spoof-Einstellungen](set-up-anti-phishing-policies.md#spoof-settings) oder [Identitätswechsel Schutz](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="b252a-157">**Phish** : The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="b252a-158">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="b252a-158">**Malware**</span></span>
     - <span data-ttu-id="b252a-159">**Spam**</span><span class="sxs-lookup"><span data-stu-id="b252a-159">**Spam**</span></span>
     - <span data-ttu-id="b252a-160">**Phishing mit hoher Zuverlässigkeit**</span><span class="sxs-lookup"><span data-stu-id="b252a-160">**High Confidence Phish**</span></span>

   - <span data-ttu-id="b252a-161">**Richtlinientyp** : Filtern von Nachrichten nach Richtlinientyp:</span><span class="sxs-lookup"><span data-stu-id="b252a-161">**Policy Type** : Filter messages by policy type:</span></span>
     - <span data-ttu-id="b252a-162">**Anti-Malware-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="b252a-162">**Anti-malware policy**</span></span>
     - <span data-ttu-id="b252a-163">**Richtlinie für sichere Anlagen**</span><span class="sxs-lookup"><span data-stu-id="b252a-163">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="b252a-164">**Antiphishing-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="b252a-164">**Anti-phish policy**</span></span>
     - <span data-ttu-id="b252a-165">**Richtlinie für gehostete Inhaltsfilter** (Anti-Spam-Richtlinie)</span><span class="sxs-lookup"><span data-stu-id="b252a-165">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="b252a-166">**Transport Regel**</span><span class="sxs-lookup"><span data-stu-id="b252a-166">**Transport rule**</span></span>

   - <span data-ttu-id="b252a-167">**E-Mail-Empfänger** : alle Benutzer oder nur an Sie gesendete Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b252a-167">**Email recipient** : All users or only messages sent to you.</span></span> <span data-ttu-id="b252a-168">Endbenutzer können nur isolierte Nachrichten verwalten, die an Sie gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b252a-168">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="b252a-169">Klicken Sie auf **Löschen** , um den Filter zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b252a-169">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="b252a-170">Um das Filter-Flyout auszublenden, klicken Sie erneut auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="b252a-170">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="b252a-171">Verwenden Sie **Ergebnisse sortieren nach** (standardmäßig die Schaltfläche **Nachrichten-ID** ) und einen entsprechenden Wert, um bestimmte Nachrichten zu finden.</span><span class="sxs-lookup"><span data-stu-id="b252a-171">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="b252a-172">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b252a-172">Wildcards aren't supported.</span></span> <span data-ttu-id="b252a-173">Sie können nach den folgenden Werten suchen:</span><span class="sxs-lookup"><span data-stu-id="b252a-173">You can search by the following values:</span></span>

   - <span data-ttu-id="b252a-174">**Nachrichten-ID** : Die globale eindeutige ID der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="b252a-174">**Message ID** : The globally unique identifier of the message.</span></span>

     <span data-ttu-id="b252a-175">Beispielsweise haben Sie die [Nachrichtenablaufverfolgung](message-trace-scc.md) verwendet, um nach einer Nachricht zu suchen, die an einen Benutzer in Ihrer Organisation gesendet wurde, und Sie bestimmen, dass die Nachricht in Quarantäne statt übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="b252a-175">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="b252a-176">Achten Sie darauf, den vollständigen Meldungs-ID-Wert einzuschließen, der möglicherweise spitzen Klammern ( \<\> ) enthält.</span><span class="sxs-lookup"><span data-stu-id="b252a-176">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="b252a-177">Zum Beispiel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="b252a-177">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="b252a-178">**E-Mail-Adresse des Absenders** : Die E-Mail-Adresse eines einzelnen Absenders.</span><span class="sxs-lookup"><span data-stu-id="b252a-178">**Sender email address** : A single sender's email address.</span></span>

   - <span data-ttu-id="b252a-179">**Richtlinienname** : Verwenden Sie den vollständigen Namen der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="b252a-179">**Policy name** : Use the entire policy name of the message.</span></span> <span data-ttu-id="b252a-180">Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="b252a-180">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="b252a-181">**E-Mail-Adresse des Empfängers** : Die E-Mail-Adresse eines einzelnen Empfängers.</span><span class="sxs-lookup"><span data-stu-id="b252a-181">**Recipient email address** : A single recipient's email address.</span></span>

   - <span data-ttu-id="b252a-182">**Betreff** : Verwenden Sie den gesamten Betreff der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="b252a-182">**Subject** : Use the entire subject of the message.</span></span> <span data-ttu-id="b252a-183">Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="b252a-183">The search is not case-sensitive.</span></span>
  
   - <span data-ttu-id="b252a-184">**Richtlinienname** : der Name der Richtlinie, die für die Quarantäne der Nachricht verantwortlich war.</span><span class="sxs-lookup"><span data-stu-id="b252a-184">**Policy name** : The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="b252a-185">Nachdem Sie die Suchkriterien eingegeben haben, klicken Sie auf die ![Schaltfläche Aktualisieren](../../media/scc-quarantine-refresh.png) **Aktualisieren** , um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="b252a-185">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="b252a-186">Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Maßnahmen zu ergreifen (z. B. die Nachricht anzeigen, freigeben, herunterladen oder löschen).</span><span class="sxs-lookup"><span data-stu-id="b252a-186">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="b252a-187">Anzeigen von Details der isolierten Nachricht</span><span class="sxs-lookup"><span data-stu-id="b252a-187">View quarantined message details</span></span>

<span data-ttu-id="b252a-188">Wenn Sie eine E-Mail-Nachricht in der Liste auswählen, werden die folgenden Nachrichtendetails im Flyout-Fenster **Details** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b252a-188">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="b252a-189">**Nachrichten-ID** : Die globale eindeutige ID für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="b252a-189">**Message ID** : The globally unique identifier for the message.</span></span>

- <span data-ttu-id="b252a-190">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="b252a-190">**Sender address**</span></span>

- <span data-ttu-id="b252a-191">**Empfangen** : Das Datum/die Uhrzeit des Nachrichtenempfangs.</span><span class="sxs-lookup"><span data-stu-id="b252a-191">**Received** : The date/time when the message was received.</span></span>

- <span data-ttu-id="b252a-192">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="b252a-192">**Subject**</span></span>

- <span data-ttu-id="b252a-193">**Quarantäne Grund** : zeigt an, ob eine Nachricht als **Spam** , **Massen** , **Phishing** , Übereinstimmung mit einer Nachrichtenfluss Regel ( **Transport Regel** ) identifiziert wurde oder als enthaltender **Schadsoftware** erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="b252a-193">**Quarantine reason** : Shows if a message has been identified as **Spam** , **Bulk** , **Phish** , matched a mail flow rule ( **Transport rule** ), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="b252a-194">**Empfängeranzahl**</span><span class="sxs-lookup"><span data-stu-id="b252a-194">**Recipient count**</span></span>

- <span data-ttu-id="b252a-195">**Empfänger** : Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Vorschau der Nachricht anzeigen** oder **Nachrichten** Kopfzeile anzeigen klicken, um die gesamte Liste der Empfänger anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b252a-195">**Recipients** : If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="b252a-196">**Läuft ab**. Das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="b252a-196">**Expires** : The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="b252a-197">**Freigegeben für** : Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b252a-197">**Released to** : All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="b252a-198">**Noch nicht freigegeben für** : Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht noch nicht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b252a-198">**Not yet released to** : All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="b252a-199">Maßnahmen für isolierte E-Mails ergreifen</span><span class="sxs-lookup"><span data-stu-id="b252a-199">Take action on quarantined email</span></span>

<span data-ttu-id="b252a-200">Nachdem Sie eine Nachricht ausgewählt haben, haben Sie mehrere Möglichkeiten, mit den Nachrichten im **Detail** -Flyout-Bereich zu tun:</span><span class="sxs-lookup"><span data-stu-id="b252a-200">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="b252a-201">**Nachricht freigeben** : Wählen Sie im eingeblendeten Flyout-Bereich die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b252a-201">**Release message** : In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="b252a-202">**Melden von Nachrichten an Microsoft zur Analyse** : diese Option ist standardmäßig aktiviert und meldet die irrtümlich unter Quarantäne gestellte Nachricht an Microsoft als falsch positiv.</span><span class="sxs-lookup"><span data-stu-id="b252a-202">**Report messages to Microsoft for analysis** : This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="b252a-203">Wenn die Nachricht als Spam, Massen, Phishing oder mit Schadsoftware isoliert wurde, wird die Nachricht auch an das Microsoft-Spam Analyse Team gemeldet.</span><span class="sxs-lookup"><span data-stu-id="b252a-203">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="b252a-204">Je nach Analyse werden die Dienst weiten spamfilterregeln möglicherweise angepasst, um die Nachricht durch zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="b252a-204">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="b252a-205">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b252a-205">Choose one of the following options:</span></span>
    - <span data-ttu-id="b252a-206">**Freigeben von Nachrichten für alle Empfänger**</span><span class="sxs-lookup"><span data-stu-id="b252a-206">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="b252a-207">**Freigeben von Nachrichten an bestimmte Empfänger**</span><span class="sxs-lookup"><span data-stu-id="b252a-207">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="b252a-208">**Freigeben von Nachrichten für andere Personen**</span><span class="sxs-lookup"><span data-stu-id="b252a-208">**Release messages to other people**</span></span>

  <span data-ttu-id="b252a-209">Klicken Sie nach Abschluss des Vorgangs auf **Nachrichten freigeben**.</span><span class="sxs-lookup"><span data-stu-id="b252a-209">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="b252a-210">Hinweise zum Freigeben von Nachrichten:</span><span class="sxs-lookup"><span data-stu-id="b252a-210">Notes about releasing messages:</span></span>

  - <span data-ttu-id="b252a-211">Sie können eine Nachricht nur einmal an denselben Empfänger freigeben.</span><span class="sxs-lookup"><span data-stu-id="b252a-211">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="b252a-212">Nur Empfänger, die die Nachricht nicht erhalten haben, werden in der Liste der potenziellen Empfänger angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b252a-212">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="b252a-213">**Nachrichtenkopf anzeigen** : Wählen Sie diesen Link aus, um den Nachrichtenkopftext anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b252a-213">**View message header** : Choose this link to see the message header text.</span></span> <span data-ttu-id="b252a-214">Um den Nachrichtenkopf im Detail zu analysieren, kopieren Sie den Nachrichtenkopftext in die Zwischenablage, und wählen Sie dann **Microsoft-Nachrichtenkopfanalyse** aus, um zur Remoteverbindungsuntersuchung zu wechseln (klicken Sie mit der rechten Maustaste, und wählen Sie **In neuer Registerkarte öffnen** aus, wenn Sie Microsoft 365 nicht verlassen möchten, um die Aufgabe auszuführen).</span><span class="sxs-lookup"><span data-stu-id="b252a-214">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="b252a-215">Fügen Sie den Nachrichtenkopf auf der Seite in den Abschnitt "Nachrichtenkopfanalyse" ein, und wählen Sie dann **Kopfzeilen analysieren** aus:</span><span class="sxs-lookup"><span data-stu-id="b252a-215">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers** :</span></span>

- <span data-ttu-id="b252a-216">**Vorschau der Nachricht anzeigen** : Wählen Sie im angezeigten Flyout-Fenster eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="b252a-216">**Preview message** : In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="b252a-217">**Quellansicht** : Zeigt die HTML-Version des Nachrichtentextes an, wobei alle Links deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="b252a-217">**Source view** : Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="b252a-218">**Textansicht** : Zeigt den Nachrichtentext im Klartext an.</span><span class="sxs-lookup"><span data-stu-id="b252a-218">**Text view** : Shows the message body in plain text.</span></span>

- <span data-ttu-id="b252a-219">**Aus Quarantäne entfernen** : Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="b252a-219">**Remove from quarantine** : After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="b252a-220">**Nachricht herunterladen** : Wählen Sie im daraufhin angezeigten Flyout-Fenster **Ich verstehe die Risiken beim Herunterladen dieser Nachricht** aus, um eine lokale Kopie der Nachricht im eml-Format zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b252a-220">**Download message** : In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="b252a-221">**Nachricht übermitteln** : Wählen Sie im eingeblendeten Flyout-Bereich die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b252a-221">**Submit message** : In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="b252a-222">**Objekttyp** : **e-Mail** (Standard), **URL** oder **Anlage**.</span><span class="sxs-lookup"><span data-stu-id="b252a-222">**Object type** : **Email** (default), **URL** , or **Attachment**.</span></span>

  - <span data-ttu-id="b252a-223">**Übermittlungs Format** : **Netzwerknachrichten-ID** (Standard, mit dem entsprechenden Wert im Feld **Netzwerknachrichten-ID** ) oder **Datei** (wechseln Sie zu einer lokalen eml-oder msg-Datei).</span><span class="sxs-lookup"><span data-stu-id="b252a-223">**Submission format** : **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="b252a-224">Beachten Sie Folgendes: Wenn Sie **Datei** auswählen und dann **Netzwerknachrichten-ID** auswählen, ist der anfängliche Wert nicht mehr vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b252a-224">Note that if you select **File** and then select **Network Message ID** , the initially value is gone.</span></span>

  - <span data-ttu-id="b252a-225">**Recipients** : Geben Sie bei Lease einen ursprünglichen Empfänger der Nachricht ein, oder klicken Sie auf **Alles auswählen** , um alle Empfänger zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b252a-225">**Recipients** : Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="b252a-226">Sie können auch auf **Alle auswählen** klicken und dann einzelne Empfänger selektiv entfernen.</span><span class="sxs-lookup"><span data-stu-id="b252a-226">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="b252a-227">**Grund für die Übermittlung** : **sollte nicht blockiert worden sein** (Standard) oder hätte **blockiert werden** müssen.</span><span class="sxs-lookup"><span data-stu-id="b252a-227">**Reason for submission** : **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="b252a-228">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="b252a-228">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="b252a-229">Wenn Sie die Nachricht nicht freigeben oder entfernen, wird sie nach Ablauf der Standard-Quarantäneaufbewahrungszeit gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b252a-229">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="b252a-230">Maßnahmen für mehrere isolierte E-Mail-Nachrichten ergreifen</span><span class="sxs-lookup"><span data-stu-id="b252a-230">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="b252a-231">Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), erscheint das Flyout-Fenster **Massenaktionen** , in dem Sie die folgenden Aktionen durchführen können:</span><span class="sxs-lookup"><span data-stu-id="b252a-231">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="b252a-232">**Nachrichten freigeben** : Die Optionen sind die gleichen wie bei der Freigabe einer einzelnen Nachricht, außer dass Sie nicht **Nachrichten an bestimmte Empfänger freigeben** auswählen können; Sie können nur **Nachricht an alle Empfänger freigeben** oder **Nachrichten an andere Personen freigeben** auswählen.</span><span class="sxs-lookup"><span data-stu-id="b252a-232">**Release messages** : The options are the same as when you release a single message, except you can't select **Release messages to specific recipients** ; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b252a-233">Nehmen Sie das folgende Szenario in Frage: John@gmail.com sendet eine Nachricht an Faith@contoso.com und John@Subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b252a-233">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="b252a-234">Gmail verzweigt diese Nachricht in zwei Kopien, die an die Quarantäne als Phishing in Microsoft weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b252a-234">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="b252a-235">Ein Administrator gibt beide Nachrichten an admin@contoso.com frei.</span><span class="sxs-lookup"><span data-stu-id="b252a-235">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="b252a-236">Die erste freigegebene Nachricht, die das Administratorpostfach erreicht, wird übermittelt.</span><span class="sxs-lookup"><span data-stu-id="b252a-236">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="b252a-237">Die zweite freigegebene Nachricht wird als doppelte Zustellung identifiziert und übersprungen.</span><span class="sxs-lookup"><span data-stu-id="b252a-237">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="b252a-238">Nachricht werden als Duplikate identifiziert, wenn Sie dieselbe Nachrichten-ID und dieselbe Empfangszeit haben.</span><span class="sxs-lookup"><span data-stu-id="b252a-238">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="b252a-239">**Nachrichten löschen** : Nachdem Sie in der angezeigten Warnung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="b252a-239">**Delete messages** :  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="b252a-240">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="b252a-240">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="b252a-241">Microsoft Defender nur für Office 365: Verwenden des Security & Compliance Center zum Verwalten von isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="b252a-241">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="b252a-242">Die Verfahren für in Quarantäne befindliche Dateien in diesem Abschnitt stehen nur für Microsoft Defender für Office 365 Plan 1 und Plan 2 Subscriber zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b252a-242">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="b252a-243">In Organisationen mit Defender für Office 365 können Administratoren isolierte Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams verwalten.</span><span class="sxs-lookup"><span data-stu-id="b252a-243">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="b252a-244">Informationen zum Aktivieren des Schutzes für diese Dateien finden Sie unter [Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b252a-244">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="b252a-245">Anzeigen von isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="b252a-245">View quarantined files</span></span>

1. <span data-ttu-id="b252a-246">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="b252a-246">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="b252a-247">Ändern Sie die Ansicht in den Wert **Dateien** in **Quarantäne** .</span><span class="sxs-lookup"><span data-stu-id="b252a-247">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="b252a-248">Sie können nach einem Feld sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="b252a-248">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="b252a-249">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="b252a-249">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="b252a-250">Klicken Sie auf **Spalten ändern** , um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b252a-250">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="b252a-251">Die Standardspalten sind mit einem Sternchen ( <sup>\*</sup> ) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="b252a-251">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="b252a-252">**Benutzer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b252a-252">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="b252a-253">**Speicherort**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b252a-253">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="b252a-254">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b252a-254">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="b252a-255">**Datei-URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b252a-255">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="b252a-256">**Dateigröße**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b252a-256">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="b252a-257">**Läuft ab**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b252a-257">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="b252a-258">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b252a-258">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="b252a-259">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="b252a-259">**Detected by**</span></span>
   - <span data-ttu-id="b252a-260">**Geändert von Zeit**</span><span class="sxs-lookup"><span data-stu-id="b252a-260">**Modified by time**</span></span>

4. <span data-ttu-id="b252a-261">Klicken Sie auf **Filter** , um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="b252a-261">To filter the results, click **Filter**.</span></span> <span data-ttu-id="b252a-262">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="b252a-262">The available filters are:</span></span>

   - <span data-ttu-id="b252a-263">**Ablaufzeit** : Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="b252a-263">**Expires time** : Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="b252a-264">**Heute**</span><span class="sxs-lookup"><span data-stu-id="b252a-264">**Today**</span></span>
     - <span data-ttu-id="b252a-265">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="b252a-265">**Next 2 days**</span></span>
     - <span data-ttu-id="b252a-266">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="b252a-266">**Next 7 days**</span></span>
     - <span data-ttu-id="b252a-267">Ein benutzerdefiniertes Datum/Zeitintervall.</span><span class="sxs-lookup"><span data-stu-id="b252a-267">A custom date/time range.</span></span>
   - <span data-ttu-id="b252a-268">**Empfangszeit**</span><span class="sxs-lookup"><span data-stu-id="b252a-268">**Received time**</span></span>
   - <span data-ttu-id="b252a-269">**Quarantäne Grund** : der einzige verfügbare Wert ist **Schadsoftware**.</span><span class="sxs-lookup"><span data-stu-id="b252a-269">**Quarantine reason** : The only available value is **Malware**.</span></span>
   - <span data-ttu-id="b252a-270">**Richtlinientyp**</span><span class="sxs-lookup"><span data-stu-id="b252a-270">**Policy type**</span></span>

<span data-ttu-id="b252a-271">Nachdem Sie eine bestimmte isolierte Datei gefunden haben, wählen Sie die Datei aus, um Details dazu anzuzeigen, und nehmen Sie Aktionen vor (beispielsweise anzeigen, freigeben, herunterladen oder Löschen der Nachricht).</span><span class="sxs-lookup"><span data-stu-id="b252a-271">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="b252a-272">Anzeigen von Details in isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="b252a-272">View quarantined file details</span></span>

<span data-ttu-id="b252a-273">Wenn Sie eine Datei in der Liste auswählen, werden im **Detail** -Flyout-Bereich die folgenden Dateidetails angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b252a-273">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="b252a-274">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="b252a-274">**File Name**</span></span>
- <span data-ttu-id="b252a-275">**Datei-URL** : URL, die den Speicherort der Datei definiert (beispielsweise in SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="b252a-275">**File URL** : URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="b252a-276">**Böswilliger Inhalt erkannt in** Das Datum/die Uhrzeit, zu dem die Datei isoliert wurde.</span><span class="sxs-lookup"><span data-stu-id="b252a-276">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="b252a-277">**Expires** : das Datum, an dem die Datei aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="b252a-277">**Expires** : The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="b252a-278">**Erkannt von** : Defender für Office 365 oder Microsofts Anti-Malware Engine.</span><span class="sxs-lookup"><span data-stu-id="b252a-278">**Detected By** : Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="b252a-279">**Veröffentlicht?**</span><span class="sxs-lookup"><span data-stu-id="b252a-279">**Released?**</span></span>
- <span data-ttu-id="b252a-280">**Name der Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="b252a-280">**Malware Name**</span></span>
- <span data-ttu-id="b252a-281">**Dokument-ID** : ein eindeutiger Bezeichner für das Dokument.</span><span class="sxs-lookup"><span data-stu-id="b252a-281">**Document ID** : A unique identifier for the document.</span></span>
- <span data-ttu-id="b252a-282">**Dateigröße** : in Kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="b252a-282">**File Size** : In kilobytes (KB).</span></span>
- <span data-ttu-id="b252a-283">**Organisation** Die eindeutige ID Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="b252a-283">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="b252a-284">**Zuletzt geändert**</span><span class="sxs-lookup"><span data-stu-id="b252a-284">**Last modified**</span></span>
- <span data-ttu-id="b252a-285">**Geändert von** : der Benutzer, der die Datei zuletzt geändert hat.</span><span class="sxs-lookup"><span data-stu-id="b252a-285">**Modified By** : The user who last modified the file.</span></span>
- <span data-ttu-id="b252a-286">**Secure Hash Algorithm 256-Bit (SHA-256)-Wert** : Sie können diesen Hashwert verwenden, um die Datei in anderen Reputation Stores oder an anderen Speicherorten in Ihrer Umgebung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b252a-286">**Secure Hash Algorithm 256-bit (SHA-256) value** : You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="b252a-287">Ausführen von Aktionen für isolierte Dateien</span><span class="sxs-lookup"><span data-stu-id="b252a-287">Take action on quarantined files</span></span>

<span data-ttu-id="b252a-288">Wenn Sie eine Datei in der Liste auswählen, können Sie die folgenden Aktionen für die Datei im **Detail** -Flyout-Bereich ausführen:</span><span class="sxs-lookup"><span data-stu-id="b252a-288">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="b252a-289">**Dateien freigeben** : Wählen Sie (Standard) aus, oder heben Sie **die Auswahl von Berichtsdateien für Microsoft für die Analyse auf** , und klicken Sie dann auf **Dateien freigeben**.</span><span class="sxs-lookup"><span data-stu-id="b252a-289">**Release files** : Select (default) or unselect **Report files to Microsoft for analysis** , and then click **Release files**.</span></span>
- <span data-ttu-id="b252a-290">**Datei herunterladen**</span><span class="sxs-lookup"><span data-stu-id="b252a-290">**Download file**</span></span>
- <span data-ttu-id="b252a-291">**Datei aus Quarantäne entfernen**</span><span class="sxs-lookup"><span data-stu-id="b252a-291">**Remove file from quarantine**</span></span>

<span data-ttu-id="b252a-292">Wenn Sie die Dateien nicht freigeben oder entfernen, werden Sie nach Ablauf der standardmäßigen Aufbewahrungszeit für Quarantäne gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b252a-292">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="b252a-293">Aktionen für mehrere isolierte Dateien</span><span class="sxs-lookup"><span data-stu-id="b252a-293">Actions on multiple quarantined files</span></span>

<span data-ttu-id="b252a-294">Wenn Sie mehrere isolierte Dateien in der Liste auswählen (bis zu 100), wird der Flyout-Bereich **Massenaktionen** angezeigt, in dem Sie die folgenden Aktionen ausführen können:</span><span class="sxs-lookup"><span data-stu-id="b252a-294">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="b252a-295">**Veröffentlichungsdateien**</span><span class="sxs-lookup"><span data-stu-id="b252a-295">**Release files**</span></span>
- <span data-ttu-id="b252a-296">**Dateien löschen** : Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, werden die Dateien sofort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b252a-296">**Delete files** :  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="b252a-297">Verwenden Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Anzeigen und Verwalten von isolierten Nachrichten und Dateien</span><span class="sxs-lookup"><span data-stu-id="b252a-297">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="b252a-298">Folgende Cmdlets werden zum Anzeigen und Verwalten von Nachrichten und Dateien in der Quarantäne verwendet:</span><span class="sxs-lookup"><span data-stu-id="b252a-298">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="b252a-299">DELETE-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="b252a-299">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="b252a-300">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="b252a-300">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="b252a-301">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="b252a-301">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="b252a-302">[Vorschau-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Beachten Sie, dass dieses Cmdlet nur für Nachrichten gilt, nicht für Malware Dateien von ATP für SharePoint Online, OneDrive für Unternehmen oder Teams.</span><span class="sxs-lookup"><span data-stu-id="b252a-302">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="b252a-303">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="b252a-303">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)

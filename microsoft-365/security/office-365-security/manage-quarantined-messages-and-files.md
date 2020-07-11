---
title: Verwalten von Nachrichten und Dateien in Quarantäne als Administrator
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
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
description: Administratoren erfahren, wie Sie isolierte Nachrichten für alle Benutzer in Exchange Online Protection (EoP) anzeigen und verwalten können. Administratoren in Organisationen mit Office 365 Advanced Threat Protection (Office 365 ATP) können auch unter Quarantäne gestellte Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams verwalten.
ms.openlocfilehash: 5e7c594669cf910404badd85c35671c284d4d91e
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101681"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="de2b1-104">Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP</span><span class="sxs-lookup"><span data-stu-id="de2b1-104">Manage quarantined messages and files as an admin in EOP</span></span>

<span data-ttu-id="de2b1-105">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="de2b1-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="de2b1-106">Weitere Informationen finden Sie unter [Quarantäne-e-Mail-Nachrichten in EoP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="de2b1-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="de2b1-107">Administratoren können alle Arten von isolierten Nachrichten für alle Benutzer anzeigen, freigeben und löschen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="de2b1-108">Nur Administratoren können Nachrichten verwalten, die als Schadsoftware, als hochgradig vertrauenswürdiges Phishing oder als Ergebnis von Nachrichtenfluss Regeln (auch bekannt als Transportregeln) isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="de2b1-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="de2b1-109">Administratoren können auch falsch positive Ergebnisse an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="de2b1-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="de2b1-110">Administratoren in Organisationen mit Office 365 Advance Threat Protection (Office 365 ATP) können unter Quarantäne gestellte Dateien auch in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams anzeigen, herunterladen und löschen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-110">Admins in organizations with Office 365 Advance Threat Protection (Office 365 ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="de2b1-111">Sie können isolierte Nachrichten im Security & Compliance Center oder in PowerShell anzeigen und verwalten (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer).</span><span class="sxs-lookup"><span data-stu-id="de2b1-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="de2b1-112">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="de2b1-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="de2b1-113">Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="de2b1-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="de2b1-114">Um die Quarantäne-Seite direkt zu öffnen, wechseln Sie zu <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="de2b1-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="de2b1-115">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="de2b1-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="de2b1-116">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="de2b1-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="de2b1-117">Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Quarantäne als Administrator verwalten können. Die Berechtigungen werden durch die **Quarantäne** Rolle im Security & Compliance Center gesteuert.</span><span class="sxs-lookup"><span data-stu-id="de2b1-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="de2b1-118">Diese Rolle wird standardmäßig der Rollengruppe **Organisationsverwaltung** (Global Admins), **Quarantine Administrator**und **Sicherheitsadministrator** im Security & Compliance Center zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="de2b1-119">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="de2b1-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="de2b1-120">Isolierte Nachrichten werden für einen Standardzeitraum aufbewahrt, bevor Sie automatisch gelöscht werden:</span><span class="sxs-lookup"><span data-stu-id="de2b1-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="de2b1-121">Nachrichten, die von antispamregeln (Spam, Phishing und Massen-e-Mails) unter Quarantäne gestellt werden: 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="de2b1-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="de2b1-122">Dies ist der Standard-und Höchstwert.</span><span class="sxs-lookup"><span data-stu-id="de2b1-122">This is the default and maximum value.</span></span> <span data-ttu-id="de2b1-123">Informationen zum Konfigurieren dieses Werts finden Sie unter [configure Anti-Spam Policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="de2b1-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="de2b1-124">Nachrichten, die Schadsoftware enthalten: 15 Tage.</span><span class="sxs-lookup"><span data-stu-id="de2b1-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="de2b1-125">Wenn eine Nachricht aus der Quarantäne abläuft, können Sie Sie nicht wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="de2b1-126">Verwenden des Security & Compliance Center zum Verwalten von e-Mail-Nachrichten in Quarantäne</span><span class="sxs-lookup"><span data-stu-id="de2b1-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="de2b1-127">Anzeigen von e-Mails in Quarantäne</span><span class="sxs-lookup"><span data-stu-id="de2b1-127">View quarantined email</span></span>

1. <span data-ttu-id="de2b1-128">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="de2b1-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="de2b1-129">Stellen Sie sicher, dass **Quarantäne anzeigen** auf den Standardwert **E-Mail** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="de2b1-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="de2b1-130">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="de2b1-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="de2b1-131">Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="de2b1-132">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="de2b1-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="de2b1-133">**Empfangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="de2b1-133">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="de2b1-134">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="de2b1-134">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="de2b1-135">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="de2b1-135">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="de2b1-136">**Quarantänegrund**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="de2b1-136">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="de2b1-137">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="de2b1-137">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="de2b1-138">**Richtlinientyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="de2b1-138">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="de2b1-139">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="de2b1-139">**Recipient**</span></span>

   - <span data-ttu-id="de2b1-140">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="de2b1-140">**Message ID**</span></span>

   - <span data-ttu-id="de2b1-141">**Name der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="de2b1-141">**Policy name**</span></span>

   - <span data-ttu-id="de2b1-142">**Größe**</span><span class="sxs-lookup"><span data-stu-id="de2b1-142">**Size**</span></span>

   - <span data-ttu-id="de2b1-143">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="de2b1-143">**Direction**</span></span>

   <span data-ttu-id="de2b1-144">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**, oder klicken Sie auf **Als Standard festlegen**.</span><span class="sxs-lookup"><span data-stu-id="de2b1-144">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="de2b1-145">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="de2b1-145">To filter the results, click **Filter**.</span></span> <span data-ttu-id="de2b1-146">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="de2b1-146">The available filters are:</span></span>

   - <span data-ttu-id="de2b1-147">**Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="de2b1-147">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="de2b1-148">**Heute**</span><span class="sxs-lookup"><span data-stu-id="de2b1-148">**Today**</span></span>

     - <span data-ttu-id="de2b1-149">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="de2b1-149">**Next 2 days**</span></span>

     - <span data-ttu-id="de2b1-150">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="de2b1-150">**Next 7 days**</span></span>

     - <span data-ttu-id="de2b1-151">**Benutzerdefiniert**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="de2b1-151">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="de2b1-152">**Empfangszeit**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="de2b1-152">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="de2b1-153">**Quarantänegrund**:</span><span class="sxs-lookup"><span data-stu-id="de2b1-153">**Quarantine reason**:</span></span>

     - <span data-ttu-id="de2b1-154">**Richtlinie**: die Nachricht stimmte mit den Bedingungen einer Nachrichtenfluss Regel überein (auch als Transportregel bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="de2b1-154">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="de2b1-155">**Massensendung**</span><span class="sxs-lookup"><span data-stu-id="de2b1-155">**Bulk**</span></span>

     - <span data-ttu-id="de2b1-156">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="de2b1-156">**Phish**</span></span>

     - <span data-ttu-id="de2b1-157">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="de2b1-157">**Malware**</span></span>

     - <span data-ttu-id="de2b1-158">**Spam**</span><span class="sxs-lookup"><span data-stu-id="de2b1-158">**Spam**</span></span>

     - <span data-ttu-id="de2b1-159">**Phishing mit hoher Zuverlässigkeit**</span><span class="sxs-lookup"><span data-stu-id="de2b1-159">**High Confidence Phish**</span></span>

   - <span data-ttu-id="de2b1-160">**E-Mail-Empfänger**: alle Benutzer oder nur an Sie gesendete Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="de2b1-160">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="de2b1-161">Endbenutzer können nur isolierte Nachrichten verwalten, die an Sie gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="de2b1-161">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="de2b1-162">Klicken Sie auf **Löschen**, um den Filter zu löschen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-162">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="de2b1-163">Um das Filter-Flyout auszublenden, klicken Sie erneut auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="de2b1-163">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="de2b1-164">Verwenden Sie **Ergebnisse sortieren nach** (standardmäßig die Schaltfläche **Nachrichten-ID**) und einen entsprechenden Wert, um bestimmte Nachrichten zu finden.</span><span class="sxs-lookup"><span data-stu-id="de2b1-164">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="de2b1-165">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="de2b1-165">Wildcards aren't supported.</span></span> <span data-ttu-id="de2b1-166">Sie können nach den folgenden Werten suchen:</span><span class="sxs-lookup"><span data-stu-id="de2b1-166">You can search by the following values:</span></span>

   - <span data-ttu-id="de2b1-167">**Nachrichten-ID**: Die globale eindeutige ID der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="de2b1-167">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="de2b1-168">Beispielsweise haben Sie die [Nachrichtenablaufverfolgung](message-trace-scc.md) verwendet, um nach einer Nachricht zu suchen, die an einen Benutzer in Ihrer Organisation gesendet wurde, und Sie bestimmen, dass die Nachricht in Quarantäne statt übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="de2b1-168">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="de2b1-169">Achten Sie darauf, den vollständigen Meldungs-ID-Wert einzuschließen, der möglicherweise spitzen Klammern ( \<\> ) enthält.</span><span class="sxs-lookup"><span data-stu-id="de2b1-169">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="de2b1-170">Zum Beispiel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="de2b1-170">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="de2b1-171">**E-Mail-Adresse des Absenders**: Die E-Mail-Adresse eines einzelnen Absenders.</span><span class="sxs-lookup"><span data-stu-id="de2b1-171">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="de2b1-172">**E-Mail-Adresse des Empfängers**: Die E-Mail-Adresse eines einzelnen Empfängers.</span><span class="sxs-lookup"><span data-stu-id="de2b1-172">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="de2b1-173">**Betreff**: Verwenden Sie den gesamten Betreff der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="de2b1-173">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="de2b1-174">Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="de2b1-174">The search is not case-sensitive.</span></span>

   <span data-ttu-id="de2b1-175">Nachdem Sie die Suchkriterien eingegeben haben, klicken Sie auf die ![Schaltfläche Aktualisieren](../../media/scc-quarantine-refresh.png) **Aktualisieren**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="de2b1-175">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="de2b1-176">Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Maßnahmen zu ergreifen (z. B. die Nachricht anzeigen, freigeben, herunterladen oder löschen).</span><span class="sxs-lookup"><span data-stu-id="de2b1-176">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="de2b1-177">Nachrichtenergebnisse exportieren</span><span class="sxs-lookup"><span data-stu-id="de2b1-177">Export message results</span></span>

1. <span data-ttu-id="de2b1-178">Wählen Sie die gewünschten Nachrichten aus, und klicken Sie auf **Ergebnisse exportieren**.</span><span class="sxs-lookup"><span data-stu-id="de2b1-178">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="de2b1-179">Klicken Sie auf **Ja** in der Bestätigungsnachricht, die Sie warnt, das Browserfenster geöffnet zu lassen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-179">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="de2b1-180">Wenn Ihr Export fertig ist, können Sie den Speicherort für die .csv-Datei benennen und auswählen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-180">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="de2b1-181">Anzeigen von Details der isolierten Nachricht</span><span class="sxs-lookup"><span data-stu-id="de2b1-181">View quarantined message details</span></span>

<span data-ttu-id="de2b1-182">Wenn Sie eine E-Mail-Nachricht in der Liste auswählen, werden die folgenden Nachrichtendetails im Flyout-Fenster **Details** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="de2b1-182">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="de2b1-183">**Nachrichten-ID**: Die globale eindeutige ID für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="de2b1-183">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="de2b1-184">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="de2b1-184">**Sender address**</span></span>

- <span data-ttu-id="de2b1-185">**Empfangen**: Das Datum/die Uhrzeit des Nachrichtenempfangs.</span><span class="sxs-lookup"><span data-stu-id="de2b1-185">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="de2b1-186">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="de2b1-186">**Subject**</span></span>

- <span data-ttu-id="de2b1-187">**Quarantäne Grund**: zeigt an, ob eine Nachricht als **Spam**, **Massen**, **Phishing**, Übereinstimmung mit einer Nachrichtenfluss Regel (**Transport Regel**) identifiziert wurde oder als enthaltender **Schadsoftware**erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="de2b1-187">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="de2b1-188">**Empfänger**: Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Vorschau der Nachricht anzeigen** oder **Nachrichten** Kopfzeile anzeigen klicken, um die gesamte Liste der Empfänger anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-188">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="de2b1-189">**Läuft ab**. Das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="de2b1-189">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="de2b1-190">**Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="de2b1-190">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="de2b1-191">**Noch nicht freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht noch nicht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="de2b1-191">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="de2b1-192">Maßnahmen für isolierte E-Mails ergreifen</span><span class="sxs-lookup"><span data-stu-id="de2b1-192">Take action on quarantined email</span></span>

<span data-ttu-id="de2b1-193">Nachdem Sie eine Nachricht ausgewählt haben, haben Sie mehrere Möglichkeiten, mit den Nachrichten im **Detail** -Flyout-Bereich zu tun:</span><span class="sxs-lookup"><span data-stu-id="de2b1-193">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="de2b1-194">**Nachricht freigeben**: Wählen Sie im eingeblendeten Flyout-Bereich die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="de2b1-194">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="de2b1-195">**Melden von Nachrichten an Microsoft zur Analyse**: diese Option ist standardmäßig aktiviert und meldet die irrtümlich unter Quarantäne gestellte Nachricht an Microsoft als falsch positiv.</span><span class="sxs-lookup"><span data-stu-id="de2b1-195">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="de2b1-196">Wenn die Nachricht als Spam, Massen, Phishing oder mit Schadsoftware isoliert wurde, wird die Nachricht auch an das Microsoft-Spam Analyse Team gemeldet.</span><span class="sxs-lookup"><span data-stu-id="de2b1-196">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="de2b1-197">Je nach Analyse können die Dienst weiten spamfilterregeln so angepasst werden, dass die Nachricht durchlassen wird.</span><span class="sxs-lookup"><span data-stu-id="de2b1-197">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="de2b1-198">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="de2b1-198">Choose one of the following options:</span></span>

    - <span data-ttu-id="de2b1-199">**Freigeben von Nachrichten für alle Empfänger**</span><span class="sxs-lookup"><span data-stu-id="de2b1-199">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="de2b1-200">**Freigeben von Nachrichten an bestimmte Empfänger**</span><span class="sxs-lookup"><span data-stu-id="de2b1-200">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="de2b1-201">**Freigeben von Nachrichten für andere Personen**</span><span class="sxs-lookup"><span data-stu-id="de2b1-201">**Release messages to other people**</span></span>

  <span data-ttu-id="de2b1-202">Klicken Sie nach Abschluss des Vorgangs auf **Nachrichten freigeben**.</span><span class="sxs-lookup"><span data-stu-id="de2b1-202">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="de2b1-203">Hinweise zum Freigeben von Nachrichten:</span><span class="sxs-lookup"><span data-stu-id="de2b1-203">Notes about releasing messages:</span></span>

  - <span data-ttu-id="de2b1-204">Sie können eine Nachricht nur einmal an denselben Empfänger freigeben.</span><span class="sxs-lookup"><span data-stu-id="de2b1-204">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="de2b1-205">Nur Empfänger, die die Nachricht nicht erhalten haben, werden in der Liste der potenziellen Empfänger angezeigt.</span><span class="sxs-lookup"><span data-stu-id="de2b1-205">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="de2b1-206">**Nachrichtenkopf anzeigen**: Wählen Sie diesen Link aus, um den Nachrichtenkopftext anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-206">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="de2b1-207">Um den Nachrichtenkopf im Detail zu analysieren, kopieren Sie den Nachrichtenkopftext in die Zwischenablage, und wählen Sie dann **Microsoft-Nachrichtenkopfanalyse** aus, um zur Remoteverbindungsuntersuchung zu wechseln (klicken Sie mit der rechten Maustaste, und wählen Sie **In neuer Registerkarte öffnen** aus, wenn Sie Microsoft 365 nicht verlassen möchten, um die Aufgabe auszuführen).</span><span class="sxs-lookup"><span data-stu-id="de2b1-207">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="de2b1-208">Fügen Sie den Nachrichtenkopf auf der Seite in den Abschnitt "Nachrichtenkopfanalyse" ein, und wählen Sie dann **Kopfzeilen analysieren** aus:</span><span class="sxs-lookup"><span data-stu-id="de2b1-208">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="de2b1-209">**Vorschau der Nachricht anzeigen**: Wählen Sie im angezeigten Flyout-Fenster eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="de2b1-209">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="de2b1-210">**Quellansicht**: Zeigt die HTML-Version des Nachrichtentextes an, wobei alle Links deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="de2b1-210">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="de2b1-211">**Textansicht**: Zeigt den Nachrichtentext im Klartext an.</span><span class="sxs-lookup"><span data-stu-id="de2b1-211">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="de2b1-212">**Aus Quarantäne entfernen**: Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="de2b1-212">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="de2b1-213">**Nachricht herunterladen**: Wählen Sie im daraufhin angezeigten Flyout-Fenster **Ich verstehe die Risiken beim Herunterladen dieser Nachricht** aus, um eine lokale Kopie der Nachricht im eml-Format zu speichern.</span><span class="sxs-lookup"><span data-stu-id="de2b1-213">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="de2b1-214">**Nachricht übermitteln**: Wählen Sie im eingeblendeten Flyout-Bereich die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="de2b1-214">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="de2b1-215">**Objekttyp**: **e-Mail** (Standard), **URL**oder **Anlage**.</span><span class="sxs-lookup"><span data-stu-id="de2b1-215">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="de2b1-216">**Übermittlungs Format**: **Netzwerknachrichten-ID** (Standard, mit dem entsprechenden Wert im Feld **Netzwerknachrichten-ID** ) oder **Datei** (wechseln Sie zu einer lokalen eml-oder msg-Datei).</span><span class="sxs-lookup"><span data-stu-id="de2b1-216">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="de2b1-217">Beachten Sie Folgendes: Wenn Sie **Datei** auswählen und dann **Netzwerknachrichten-ID**auswählen, ist der anfängliche Wert nicht mehr vorhanden.</span><span class="sxs-lookup"><span data-stu-id="de2b1-217">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="de2b1-218">**Recipients**: Geben Sie bei Lease einen ursprünglichen Empfänger der Nachricht ein, oder klicken Sie auf **Alles auswählen** , um alle Empfänger zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="de2b1-218">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="de2b1-219">Sie können auch auf **Alle auswählen** klicken und dann einzelne Empfänger selektiv entfernen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-219">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="de2b1-220">**Grund für die Übermittlung**: **sollte nicht blockiert worden sein** (Standard) oder hätte **blockiert werden**müssen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-220">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="de2b1-221">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="de2b1-221">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="de2b1-222">Wenn Sie die Nachricht nicht freigeben oder entfernen, wird sie nach Ablauf der Standard-Quarantäneaufbewahrungszeit gelöscht.</span><span class="sxs-lookup"><span data-stu-id="de2b1-222">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="de2b1-223">Maßnahmen für mehrere isolierte E-Mail-Nachrichten ergreifen</span><span class="sxs-lookup"><span data-stu-id="de2b1-223">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="de2b1-224">Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), erscheint das Flyout-Fenster **Massenaktionen**, in dem Sie die folgenden Aktionen durchführen können:</span><span class="sxs-lookup"><span data-stu-id="de2b1-224">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="de2b1-225">**Nachrichten freigeben**: Die Optionen sind die gleichen wie bei der Freigabe einer einzelnen Nachricht, außer dass Sie nicht **Nachrichten an bestimmte Empfänger freigeben** auswählen können; Sie können nur **Nachricht an alle Empfänger freigeben** oder **Nachrichten an andere Personen freigeben** auswählen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-225">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="de2b1-226">Nehmen Sie das folgende Szenario in Frage: John@gmail.com sendet eine Nachricht an Faith@contoso.com und John@Subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="de2b1-226">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="de2b1-227">Gmail verzweigt diese Nachricht in zwei Kopien, die an die Quarantäne als Phishing in Microsoft weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="de2b1-227">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="de2b1-228">Ein Administrator gibt beide Nachrichten an admin@contoso.com frei.</span><span class="sxs-lookup"><span data-stu-id="de2b1-228">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="de2b1-229">Die erste freigegebene Nachricht, die das Administratorpostfach erreicht, wird übermittelt.</span><span class="sxs-lookup"><span data-stu-id="de2b1-229">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="de2b1-230">Die zweite freigegebene Nachricht wird als doppelte Zustellung identifiziert und übersprungen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-230">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="de2b1-231">Nachricht werden als Duplikate identifiziert, wenn Sie dieselbe Nachrichten-ID und dieselbe Empfangszeit haben.</span><span class="sxs-lookup"><span data-stu-id="de2b1-231">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="de2b1-232">**Nachrichten löschen**: Nachdem Sie in der angezeigten Warnung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="de2b1-232">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="de2b1-233">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="de2b1-233">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="de2b1-234">Nur ATP: Verwenden Sie das Security & Compliance Center, um isolierte Dateien zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="de2b1-234">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="de2b1-235">Die Verfahren für in Quarantäne befindliche Dateien in diesem Abschnitt stehen nur für ATP-Plan 1-und Plan 2-Abonnenten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="de2b1-235">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="de2b1-236">In Organisationen mit ATP können Administratoren isolierte Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams verwalten.</span><span class="sxs-lookup"><span data-stu-id="de2b1-236">In organizations with ATP, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="de2b1-237">Anzeigen von isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="de2b1-237">View quarantined files</span></span>

1. <span data-ttu-id="de2b1-238">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="de2b1-238">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="de2b1-239">Ändern Sie die Ansicht in den Standardwert **Dateien**unter **Quarantäne** .</span><span class="sxs-lookup"><span data-stu-id="de2b1-239">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="de2b1-240">Sie können nach einem Feld sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="de2b1-240">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="de2b1-241">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="de2b1-241">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="de2b1-242">Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-242">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="de2b1-243">Die Standardspalten sind mit einem Sternchen ( <sup>\*</sup> ) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="de2b1-243">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="de2b1-244">**Benutzer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="de2b1-244">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="de2b1-245">**Speicherort**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="de2b1-245">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="de2b1-246">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="de2b1-246">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="de2b1-247">**Datei-URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="de2b1-247">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="de2b1-248">**Dateigröße**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="de2b1-248">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="de2b1-249">**Läuft ab**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="de2b1-249">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="de2b1-250">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="de2b1-250">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="de2b1-251">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="de2b1-251">**Detected by**</span></span>

   - <span data-ttu-id="de2b1-252">**Geändert von Zeit**</span><span class="sxs-lookup"><span data-stu-id="de2b1-252">**Modified by time**</span></span>

4. <span data-ttu-id="de2b1-253">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="de2b1-253">To filter the results, click **Filter**.</span></span> <span data-ttu-id="de2b1-254">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="de2b1-254">The available filters are:</span></span>

   - <span data-ttu-id="de2b1-255">**Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="de2b1-255">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="de2b1-256">**Heute**</span><span class="sxs-lookup"><span data-stu-id="de2b1-256">**Today**</span></span>

     - <span data-ttu-id="de2b1-257">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="de2b1-257">**Next 2 days**</span></span>

     - <span data-ttu-id="de2b1-258">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="de2b1-258">**Next 7 days**</span></span>

     - <span data-ttu-id="de2b1-259">Ein benutzerdefiniertes Datum/Zeitintervall.</span><span class="sxs-lookup"><span data-stu-id="de2b1-259">A custom date/time range.</span></span>

   - <span data-ttu-id="de2b1-260">**Empfangszeit**</span><span class="sxs-lookup"><span data-stu-id="de2b1-260">**Received time**</span></span>

   - <span data-ttu-id="de2b1-261">**Quarantäne Grund**: der einzige verfügbare Wert ist **Schadsoftware**.</span><span class="sxs-lookup"><span data-stu-id="de2b1-261">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="de2b1-262">Nachdem Sie eine bestimmte isolierte Datei gefunden haben, wählen Sie die Datei aus, um Details dazu anzuzeigen, und nehmen Sie Aktionen vor (beispielsweise anzeigen, freigeben, herunterladen oder Löschen der Nachricht).</span><span class="sxs-lookup"><span data-stu-id="de2b1-262">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="de2b1-263">Exportieren von Datei Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="de2b1-263">Export file results</span></span>

1. <span data-ttu-id="de2b1-264">Wählen Sie die Dateien aus, für die Sie sich interessieren, und klicken Sie auf **Ergebnisse exportieren**.</span><span class="sxs-lookup"><span data-stu-id="de2b1-264">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="de2b1-265">Klicken Sie auf **Ja** in der Bestätigungsnachricht, die Sie warnt, das Browserfenster geöffnet zu lassen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-265">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="de2b1-266">Wenn Ihr Export fertig ist, können Sie den Speicherort für die .csv-Datei benennen und auswählen.</span><span class="sxs-lookup"><span data-stu-id="de2b1-266">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="de2b1-267">Anzeigen von Details in isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="de2b1-267">View quarantined file details</span></span>

<span data-ttu-id="de2b1-268">Wenn Sie eine Datei in der Liste auswählen, werden im **Detail** -Flyout-Bereich die folgenden Dateidetails angezeigt:</span><span class="sxs-lookup"><span data-stu-id="de2b1-268">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="de2b1-269">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="de2b1-269">**File Name**</span></span>

- <span data-ttu-id="de2b1-270">**Datei-URL**: URL, die den Speicherort der Datei definiert (beispielsweise in SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="de2b1-270">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="de2b1-271">**Böswilliger Inhalt erkannt in** Das Datum/die Uhrzeit, zu dem die Datei isoliert wurde.</span><span class="sxs-lookup"><span data-stu-id="de2b1-271">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="de2b1-272">**Expires**: das Datum, an dem die Datei aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="de2b1-272">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="de2b1-273">**Erkannt von**: ATP (Advanced Threat Protection) oder Microsofts Anti-Malware Engine.</span><span class="sxs-lookup"><span data-stu-id="de2b1-273">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="de2b1-274">**Veröffentlicht?**</span><span class="sxs-lookup"><span data-stu-id="de2b1-274">**Released?**</span></span>

- <span data-ttu-id="de2b1-275">**Name der Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="de2b1-275">**Malware Name**</span></span>

- <span data-ttu-id="de2b1-276">**Dokument-ID**: ein eindeutiger Bezeichner für das Dokument.</span><span class="sxs-lookup"><span data-stu-id="de2b1-276">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="de2b1-277">**Dateigröße**: in Kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="de2b1-277">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="de2b1-278">**Organisation** Die eindeutige ID Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="de2b1-278">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="de2b1-279">**Zuletzt geändert**</span><span class="sxs-lookup"><span data-stu-id="de2b1-279">**Last modified**</span></span>

- <span data-ttu-id="de2b1-280">**Geändert von**: der Benutzer, der die Datei zuletzt geändert hat.</span><span class="sxs-lookup"><span data-stu-id="de2b1-280">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="de2b1-281">**Secure Hash Algorithm 256-Bit (SHA-256)-Wert**: Sie können diesen Hashwert verwenden, um die Datei in anderen Reputation Stores oder an anderen Speicherorten in Ihrer Umgebung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="de2b1-281">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="de2b1-282">Ausführen von Aktionen für isolierte Dateien</span><span class="sxs-lookup"><span data-stu-id="de2b1-282">Take action on quarantined files</span></span>

<span data-ttu-id="de2b1-283">Wenn Sie eine Datei in der Liste auswählen, können Sie die folgenden Aktionen für die Datei im **Detail** -Flyout-Bereich ausführen:</span><span class="sxs-lookup"><span data-stu-id="de2b1-283">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="de2b1-284">**Dateien freigeben**: Wählen Sie (Standard) aus, oder heben Sie **die Auswahl von Berichtsdateien für Microsoft für die Analyse auf**, und klicken Sie dann auf **Dateien freigeben**.</span><span class="sxs-lookup"><span data-stu-id="de2b1-284">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="de2b1-285">**Datei herunterladen**</span><span class="sxs-lookup"><span data-stu-id="de2b1-285">**Download file**</span></span>

- <span data-ttu-id="de2b1-286">**Datei aus Quarantäne entfernen**</span><span class="sxs-lookup"><span data-stu-id="de2b1-286">**Remove file from quarantine**</span></span>

<span data-ttu-id="de2b1-287">Wenn Sie die Dateien nicht freigeben oder entfernen, werden Sie nach Ablauf der standardmäßigen Aufbewahrungszeit für Quarantäne gelöscht.</span><span class="sxs-lookup"><span data-stu-id="de2b1-287">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="de2b1-288">Aktionen für mehrere isolierte Dateien</span><span class="sxs-lookup"><span data-stu-id="de2b1-288">Actions on multiple quarantined files</span></span>

<span data-ttu-id="de2b1-289">Wenn Sie mehrere isolierte Dateien in der Liste auswählen (bis zu 100), wird der Flyout-Bereich **Massenaktionen** angezeigt, in dem Sie die folgenden Aktionen ausführen können:</span><span class="sxs-lookup"><span data-stu-id="de2b1-289">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="de2b1-290">**Veröffentlichungsdateien**</span><span class="sxs-lookup"><span data-stu-id="de2b1-290">**Release files**</span></span>

- <span data-ttu-id="de2b1-291">**Dateien löschen**: Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, werden die Dateien sofort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="de2b1-291">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="de2b1-292">Melden Sie sich mit einem Arbeits-oder Schulkonto mit globalen Administratorrechten (oder geeigneten Sicherheits & Compliance Center-Rollen) in Ihrer Organisation an, und [wechseln Sie zum Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="de2b1-292">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="de2b1-293">Verwenden Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Anzeigen und Verwalten von isolierten Nachrichten und Dateien</span><span class="sxs-lookup"><span data-stu-id="de2b1-293">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="de2b1-294">Folgende Cmdlets werden zum Anzeigen und Verwalten von Nachrichten und Dateien in der Quarantäne verwendet:</span><span class="sxs-lookup"><span data-stu-id="de2b1-294">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="de2b1-295">DELETE-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="de2b1-295">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="de2b1-296">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="de2b1-296">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="de2b1-297">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="de2b1-297">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="de2b1-298">[Vorschau-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Beachten Sie, dass dieses Cmdlet nur für Nachrichten gilt, nicht für Malware Dateien von ATP für SharePoint Online, OneDrive für Unternehmen oder Teams.</span><span class="sxs-lookup"><span data-stu-id="de2b1-298">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="de2b1-299">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="de2b1-299">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)

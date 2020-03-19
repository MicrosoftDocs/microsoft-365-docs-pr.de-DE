---
title: Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365
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
description: Administratoren können alle Arten von isolierten Nachrichten für alle Benutzer anzeigen, freigeben und löschen. Nur Administratoren können Nachrichten verwalten, die als Schadsoftware, als hochgradig vertrauenswürdiges Phishing oder als Ergebnis von Nachrichtenfluss Regeln (Transportregeln) isoliert wurden.
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857073"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a><span data-ttu-id="01b1b-104">Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365</span><span class="sxs-lookup"><span data-stu-id="01b1b-104">Manage quarantined messages and files as an admin in Office 365</span></span>

<span data-ttu-id="01b1b-105">In Quarantäne werden potenziell gefährliche oder unerwünschte Nachrichten in Office 365 Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="01b1b-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="01b1b-106">Weitere Informationen finden Sie unter [Quarantine in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="01b1b-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="01b1b-107">Administratoren können alle Arten von isolierten Nachrichten für alle Benutzer anzeigen, freigeben und löschen.</span><span class="sxs-lookup"><span data-stu-id="01b1b-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="01b1b-108">Nur Administratoren können Nachrichten verwalten, die als Schadsoftware, als hochgradig vertrauenswürdiges Phishing oder als Ergebnis von Nachrichtenfluss Regeln (auch bekannt als Transportregeln) isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="01b1b-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="01b1b-109">Administratoren können auch falsch positive Ergebnisse an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="01b1b-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="01b1b-110">Administratoren in Organisationen mit Office 365 Advance Threat Protection (ATP) können auch in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams isolierte Dateien anzeigen, herunterladen und löschen.</span><span class="sxs-lookup"><span data-stu-id="01b1b-110">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="01b1b-111">Sie können isolierte Nachrichten im Security & Compliance Center oder in PowerShell anzeigen und verwalten (Exchange Online PowerShell für Office 365 Kunden; Exchange Online Protection PowerShell für eigenständige EoP-Kunden).</span><span class="sxs-lookup"><span data-stu-id="01b1b-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="01b1b-112">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="01b1b-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="01b1b-113">Um das Office 365 Security & Compliance Center zu öffnen, gehen <https://protection.office.com>Sie zu.</span><span class="sxs-lookup"><span data-stu-id="01b1b-113">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="01b1b-114">Um die Quarantäne Seite direkt zu öffnen, wechseln Sie <https://protection.office.com/quarantine>zu.</span><span class="sxs-lookup"><span data-stu-id="01b1b-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="01b1b-115">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="01b1b-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="01b1b-116">Informationen zum Herstellen einer Verbindung mit Exchange Online Protection PowerShell finden Sie unter [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="01b1b-116">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="01b1b-117">Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Quarantäne als Administrator verwalten können. Die Berechtigungen werden durch die **Quarantäne** Rolle im Security & Compliance Center gesteuert.</span><span class="sxs-lookup"><span data-stu-id="01b1b-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="01b1b-118">Diese Rolle wird standardmäßig der Rollengruppe **Organisationsverwaltung** (Global Admins), **Quarantine Administrator**und **Sicherheitsadministrator** im Security & Compliance Center zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="01b1b-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="01b1b-119">Weitere Informationen finden Sie unter [Berechtigungen im Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="01b1b-119">For more information, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="01b1b-120">Isolierte Nachrichten werden für einen Standardzeitraum aufbewahrt, bevor Sie automatisch gelöscht werden:</span><span class="sxs-lookup"><span data-stu-id="01b1b-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="01b1b-121">Nachrichten, die von antispamregeln (Spam, Phishing und Massen-e-Mails) unter Quarantäne gestellt werden: 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="01b1b-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="01b1b-122">Dies ist der Standard-und Höchstwert.</span><span class="sxs-lookup"><span data-stu-id="01b1b-122">This is the default and maximum value.</span></span> <span data-ttu-id="01b1b-123">Informationen zum Konfigurieren dieses Werts finden Sie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="01b1b-123">To configure this value, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="01b1b-124">Nachrichten, die nach Nachrichtenfluss Regeln unter Quarantäne gestellt werden (die Regelaktion ist **die Nachricht an die gehostete Quarantäne zuzustellen**): 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="01b1b-124">Messages quarantined by mail flow rules (the rule action is **Deliver the message to the hosted quarantine**): 30 days.</span></span> <span data-ttu-id="01b1b-125">Dieser Wert kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="01b1b-125">You can't change this value.</span></span>

  - <span data-ttu-id="01b1b-126">Nachrichten, die Schadsoftware enthalten: 15 Tage.</span><span class="sxs-lookup"><span data-stu-id="01b1b-126">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="01b1b-127">Wenn eine Nachricht aus der Quarantäne abläuft, können Sie Sie nicht wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="01b1b-127">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="01b1b-128">Verwenden des Security & Compliance Center zum Verwalten von e-Mail-Nachrichten in Quarantäne</span><span class="sxs-lookup"><span data-stu-id="01b1b-128">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="01b1b-129">Anzeigen von e-Mails in Quarantäne</span><span class="sxs-lookup"><span data-stu-id="01b1b-129">View quarantined email</span></span>

1. <span data-ttu-id="01b1b-130">Wechseln Sie im Security and Compliance Center zu **Threat Management** \> **Review** \> **Quarantine**.</span><span class="sxs-lookup"><span data-stu-id="01b1b-130">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="01b1b-131">Stellen Sie sicher, dass die **Ansicht isoliert** auf den Standardwert **e-Mail**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="01b1b-131">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="01b1b-132">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="01b1b-132">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="01b1b-133">Klicken Sie auf **Spalten ändern** , um maximal sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="01b1b-133">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="01b1b-134">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="01b1b-134">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="01b1b-135">**Empfangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="01b1b-135">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="01b1b-136">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="01b1b-136">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="01b1b-137">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="01b1b-137">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="01b1b-138">**Quarantäne Grund**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="01b1b-138">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="01b1b-139">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="01b1b-139">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="01b1b-140">**Richtlinientyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="01b1b-140">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="01b1b-141">**Abläuft**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="01b1b-141">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="01b1b-142">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="01b1b-142">**Recipient**</span></span>

   - <span data-ttu-id="01b1b-143">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="01b1b-143">**Message ID**</span></span>

   - <span data-ttu-id="01b1b-144">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="01b1b-144">**Policy name**</span></span>

   - <span data-ttu-id="01b1b-145">**Size**</span><span class="sxs-lookup"><span data-stu-id="01b1b-145">**Size**</span></span>

   - <span data-ttu-id="01b1b-146">**Direction**</span><span class="sxs-lookup"><span data-stu-id="01b1b-146">**Direction**</span></span>

   <span data-ttu-id="01b1b-147">Wenn Sie fertig sind, klicken Sie auf **Speichern**, oder klicken Sie auf **auf Standard festlegen**.</span><span class="sxs-lookup"><span data-stu-id="01b1b-147">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="01b1b-148">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="01b1b-148">To filter the results, click **Filter**.</span></span> <span data-ttu-id="01b1b-149">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="01b1b-149">The available filters are:</span></span>

   - <span data-ttu-id="01b1b-150">**Expires Time**: Filtern von Nachrichten nach Ablauf der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="01b1b-150">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="01b1b-151">**Heute**</span><span class="sxs-lookup"><span data-stu-id="01b1b-151">**Today**</span></span>

     - <span data-ttu-id="01b1b-152">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="01b1b-152">**Next 2 days**</span></span>

     - <span data-ttu-id="01b1b-153">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="01b1b-153">**Next 7 days**</span></span>

     - <span data-ttu-id="01b1b-154">**Benutzerdefiniert**: Geben Sie ein **Start** -und **Enddatum**ein.</span><span class="sxs-lookup"><span data-stu-id="01b1b-154">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="01b1b-155">**Empfangszeit**: Geben Sie ein **Start** -und **Enddatum**ein.</span><span class="sxs-lookup"><span data-stu-id="01b1b-155">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="01b1b-156">**Quarantäne Grund**:</span><span class="sxs-lookup"><span data-stu-id="01b1b-156">**Quarantine reason**:</span></span>

     - <span data-ttu-id="01b1b-157">**Richtlinie**: die Nachricht stimmte mit den Bedingungen einer Nachrichtenfluss Regel überein (auch als Transportregel bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="01b1b-157">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="01b1b-158">**Bulk**</span><span class="sxs-lookup"><span data-stu-id="01b1b-158">**Bulk**</span></span>

     - <span data-ttu-id="01b1b-159">**Phishingfilterrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="01b1b-159">**Phish**</span></span>

     - <span data-ttu-id="01b1b-160">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="01b1b-160">**Malware**</span></span>

     - <span data-ttu-id="01b1b-161">**Spam**</span><span class="sxs-lookup"><span data-stu-id="01b1b-161">**Spam**</span></span>

     - <span data-ttu-id="01b1b-162">**Phishing mit hoher Zuverlässigkeit**</span><span class="sxs-lookup"><span data-stu-id="01b1b-162">**High Confidence Phish**</span></span>

   - <span data-ttu-id="01b1b-163">**E-Mail-Empfänger**: alle Benutzer oder nur an Sie gesendete Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="01b1b-163">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="01b1b-164">Endbenutzer können nur isolierte Nachrichten verwalten, die an Sie gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="01b1b-164">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="01b1b-165">Klicken Sie auf **Löschen**, um den Filter zu löschen.</span><span class="sxs-lookup"><span data-stu-id="01b1b-165">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="01b1b-166">Zum Ausblenden des Filter Flyouts klicken Sie erneut auf **Filtern** .</span><span class="sxs-lookup"><span data-stu-id="01b1b-166">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="01b1b-167">Verwenden Sie **Sortierergebnisse nach** (die Schaltfläche **Nachrichten-ID** standardmäßig) und einen entsprechenden Wert, um nach bestimmten Nachrichten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="01b1b-167">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="01b1b-168">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="01b1b-168">Wildcards aren't supported.</span></span> <span data-ttu-id="01b1b-169">Sie können anhand der folgenden Werte suchen:</span><span class="sxs-lookup"><span data-stu-id="01b1b-169">You can search by the following values:</span></span>

   - <span data-ttu-id="01b1b-170">Nach **richten-ID**: die global eindeutige ID der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="01b1b-170">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="01b1b-171">Beispielsweise haben Sie die [Nachrichtenablaufverfolgung](message-trace-scc.md) verwendet, um nach einer Nachricht zu suchen, die an einen Benutzer in Ihrer Organisation gesendet wurde, und Sie bestimmen, dass die Nachricht in Quarantäne statt übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="01b1b-171">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="01b1b-172">Achten Sie darauf, den vollständigen Meldungs-ID-Wert einzuschließen, der\<\>möglicherweise spitzen Klammern () enthält.</span><span class="sxs-lookup"><span data-stu-id="01b1b-172">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="01b1b-173">Zum Beispiel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="01b1b-173">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="01b1b-174">**Absender-e-Mail-Adresse**: e-Mail-Adresse eines einzelnen Absenders.</span><span class="sxs-lookup"><span data-stu-id="01b1b-174">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="01b1b-175">**Empfänger-e-Mail-Adresse**: die e-Mail-Adresse eines einzelnen Empfängers.</span><span class="sxs-lookup"><span data-stu-id="01b1b-175">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="01b1b-176">**Betreff**: Verwenden Sie den gesamten Betreff der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="01b1b-176">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="01b1b-177">Bei der Suche wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="01b1b-177">The search is not case-sensitive.</span></span>

   <span data-ttu-id="01b1b-178">Nachdem Sie die Suchkriterien eingegeben haben, klicken ![Sie auf](../media/scc-quarantine-refresh.png) Aktualisieren Schaltfläche **Aktualisieren** , um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="01b1b-178">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="01b1b-179">Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Aktionen dafür durchführen zu lassen (beispielsweise anzeigen, freigeben, herunterladen oder Löschen der Nachricht).</span><span class="sxs-lookup"><span data-stu-id="01b1b-179">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="01b1b-180">Exportieren von Nachrichten Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="01b1b-180">Export message results</span></span>

1. <span data-ttu-id="01b1b-181">Wählen Sie die Nachrichten aus, für die Sie sich interessieren, und klicken Sie auf **Ergebnisse exportieren**.</span><span class="sxs-lookup"><span data-stu-id="01b1b-181">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="01b1b-182">Klicken Sie in der Bestätigungsmeldung auf **Ja** , um zu warnen, dass das Browserfenster geöffnet bleibt.</span><span class="sxs-lookup"><span data-stu-id="01b1b-182">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="01b1b-183">Wenn der Export abgeschlossen ist, können Sie den Downloadspeicherort für die CSV-Datei benennen und auswählen.</span><span class="sxs-lookup"><span data-stu-id="01b1b-183">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="01b1b-184">Anzeigen von Details für isolierte Nachrichten</span><span class="sxs-lookup"><span data-stu-id="01b1b-184">View quarantined message details</span></span>

<span data-ttu-id="01b1b-185">Wenn Sie eine e-Mail-Nachricht in der Liste auswählen, werden im **Detail** -Flyout-Bereich die folgenden Nachrichtendetails angezeigt:</span><span class="sxs-lookup"><span data-stu-id="01b1b-185">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="01b1b-186">Nach **richten-ID**: der Global eindeutige Bezeichner für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="01b1b-186">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="01b1b-187">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="01b1b-187">**Sender address**</span></span>

- <span data-ttu-id="01b1b-188">**Received**: das Datum/die Uhrzeit, zu der die Nachricht empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="01b1b-188">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="01b1b-189">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="01b1b-189">**Subject**</span></span>

- <span data-ttu-id="01b1b-190">**Quarantäne Grund**: zeigt an, ob eine Nachricht als **Spam**, **Massen**, **Phishing**, Übereinstimmung mit einer Nachrichtenfluss Regel (**Transport Regel**) identifiziert wurde oder als enthaltender **Schadsoftware**erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="01b1b-190">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="01b1b-191">**Empfänger**: Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Nachricht** anzeigen oder **Nachrichtenkopfzeile anzeigen** klicken, um die vollständige Liste der Empfänger anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="01b1b-191">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="01b1b-192">**Expires**: das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="01b1b-192">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="01b1b-193">**Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="01b1b-193">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="01b1b-194">**Noch nicht freigegeben an**: alle e-Mail-Adressen (falls vorhanden), für die die Nachricht noch nicht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="01b1b-194">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="01b1b-195">Aktion für in Quarantäne versehene e-Mails ausführen</span><span class="sxs-lookup"><span data-stu-id="01b1b-195">Take action on quarantined email</span></span>

<span data-ttu-id="01b1b-196">Nachdem Sie eine Nachricht ausgewählt haben, haben Sie mehrere Möglichkeiten, mit den Nachrichten im **Detail** -Flyout-Bereich zu tun:</span><span class="sxs-lookup"><span data-stu-id="01b1b-196">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="01b1b-197">**Nachricht freigeben**: Wählen Sie im eingeblendeten Flyout-Bereich die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="01b1b-197">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="01b1b-198">**Melden von Nachrichten an Microsoft zur Analyse**: diese Option ist standardmäßig aktiviert und meldet die irrtümlich unter Quarantäne gestellte Nachricht an Microsoft als falsch positiv.</span><span class="sxs-lookup"><span data-stu-id="01b1b-198">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="01b1b-199">Wenn die Nachricht als Spam, Massen, Phishing oder mit Schadsoftware isoliert wurde, wird die Nachricht auch an das Microsoft-Spam Analyse Team gemeldet.</span><span class="sxs-lookup"><span data-stu-id="01b1b-199">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="01b1b-200">Je nach Analyse können die Dienst weiten spamfilterregeln so angepasst werden, dass die Nachricht durchlassen wird.</span><span class="sxs-lookup"><span data-stu-id="01b1b-200">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="01b1b-201">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="01b1b-201">Choose one of the following options:</span></span>

    - <span data-ttu-id="01b1b-202">**Freigeben von Nachrichten für alle Empfänger**</span><span class="sxs-lookup"><span data-stu-id="01b1b-202">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="01b1b-203">**Freigeben von Nachrichten an bestimmte Empfänger**</span><span class="sxs-lookup"><span data-stu-id="01b1b-203">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="01b1b-204">**Freigeben von Nachrichten für andere Personen**</span><span class="sxs-lookup"><span data-stu-id="01b1b-204">**Release messages to other people**</span></span>

  <span data-ttu-id="01b1b-205">Wenn Sie fertig sind, klicken Sie auf **Nachrichten freigeben**.</span><span class="sxs-lookup"><span data-stu-id="01b1b-205">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="01b1b-206">Hinweise zum Freigeben von Nachrichten:</span><span class="sxs-lookup"><span data-stu-id="01b1b-206">Notes about releasing messages:</span></span>

  - <span data-ttu-id="01b1b-207">Sie können eine Nachricht nur einmal an denselben Empfänger freigeben.</span><span class="sxs-lookup"><span data-stu-id="01b1b-207">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="01b1b-208">Nur Empfänger, die die Nachricht nicht erhalten haben, werden in der Liste der potenziellen Empfänger angezeigt.</span><span class="sxs-lookup"><span data-stu-id="01b1b-208">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="01b1b-209">**Nachrichtenkopfzeile anzeigen**: Wählen Sie diesen Link aus, um den Text der Nachrichtenkopfzeile anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="01b1b-209">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="01b1b-210">Um die Kopfzeilenfelder und-Werte eingehend zu analysieren, kopieren Sie den Text der Nachrichtenkopfzeile in die Zwischenablage, und wählen Sie dann **Microsoft Message Header Analyzer** aus, um zur Remote Verbindungs Untersuchung zu wechseln (Klicken Sie mit der rechten Maustaste, und wählen Sie **in einer neuen Registerkarte öffnen** aus, wenn Sie Office 365 nicht verlassen möchten).</span><span class="sxs-lookup"><span data-stu-id="01b1b-210">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="01b1b-211">Fügen Sie die Kopfzeile der Nachricht auf der Seite im Abschnitt Nachrichtenkopf Analyse ein, und wählen Sie **Kopfzeilen analysieren**aus:</span><span class="sxs-lookup"><span data-stu-id="01b1b-211">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="01b1b-212">**Vorschau Nachricht**: Wählen Sie im eingeblendeten Flyout-Bereich eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="01b1b-212">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="01b1b-213">**Quellansicht**: zeigt die HTML-Version des Nachrichtentexts an, für den alle Links deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="01b1b-213">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="01b1b-214">**Text Ansicht**: zeigt den Nachrichtentext im nur-Text-Format an.</span><span class="sxs-lookup"><span data-stu-id="01b1b-214">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="01b1b-215">**Aus Quarantäne entfernen**: Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="01b1b-215">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="01b1b-216">**Nachricht herunterladen**: Wählen Sie im Flyout-Bereich, der angezeigt wird, **die Risiken vom Herunterladen dieser Nachricht aus** , um eine lokale Kopie der Nachricht im eml-Format zu speichern.</span><span class="sxs-lookup"><span data-stu-id="01b1b-216">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="01b1b-217">**Nachricht übermitteln**: Wählen Sie im eingeblendeten Flyout-Bereich die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="01b1b-217">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="01b1b-218">**Objekttyp**: **e-Mail** (Standard), **URL**oder **Anlage**.</span><span class="sxs-lookup"><span data-stu-id="01b1b-218">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="01b1b-219">**Übermittlungs Format**: **Netzwerknachrichten-ID** (Standard, mit dem entsprechenden Wert im Feld **Netzwerknachrichten-ID** ) oder **Datei** (wechseln Sie zu einer lokalen eml-oder msg-Datei).</span><span class="sxs-lookup"><span data-stu-id="01b1b-219">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="01b1b-220">Beachten Sie Folgendes: Wenn Sie **Datei** auswählen und dann **Netzwerknachrichten-ID**auswählen, ist der anfängliche Wert nicht mehr vorhanden.</span><span class="sxs-lookup"><span data-stu-id="01b1b-220">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="01b1b-221">**Recipients**: Geben Sie bei Lease einen ursprünglichen Empfänger der Nachricht ein, oder klicken Sie auf **Alles auswählen** , um alle Empfänger zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="01b1b-221">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="01b1b-222">Sie können auch auf **Alle auswählen** klicken und dann einzelne Empfänger selektiv entfernen.</span><span class="sxs-lookup"><span data-stu-id="01b1b-222">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="01b1b-223">**Grund für die Übermittlung**: **sollte nicht blockiert worden sein** (Standard) oder hätte **blockiert werden**müssen.</span><span class="sxs-lookup"><span data-stu-id="01b1b-223">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="01b1b-224">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="01b1b-224">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="01b1b-225">Wenn Sie die Nachricht nicht freigeben oder entfernen, wird Sie nach Ablauf der standardmäßigen Aufbewahrungszeit für Quarantäne gelöscht.</span><span class="sxs-lookup"><span data-stu-id="01b1b-225">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="01b1b-226">Ausführen von Aktionen in mehreren isolierten e-Mail-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="01b1b-226">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="01b1b-227">Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), wird der Flyout-Bereich **Massenaktionen** angezeigt, in dem Sie die folgenden Aktionen ausführen können:</span><span class="sxs-lookup"><span data-stu-id="01b1b-227">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="01b1b-228">**Release-Nachrichten**: die Optionen sind identisch mit denen, wenn Sie eine einzelne Nachricht freigeben, es sei denn, Sie können keine **Nachrichten für bestimmte Empfänger**auswählen. Sie können nur **Release-Nachricht für alle Empfänger** auswählen oder **Nachrichten an andere Personen freigeben**.</span><span class="sxs-lookup"><span data-stu-id="01b1b-228">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="01b1b-229">**Löschen von Nachrichten**: Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="01b1b-229">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="01b1b-230">Wenn Sie fertig sind, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="01b1b-230">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="01b1b-231">Nur ATP: Verwenden Sie das Security & Compliance Center, um isolierte Dateien zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="01b1b-231">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="01b1b-232">Die Verfahren für in Quarantäne befindliche Dateien in diesem Abschnitt stehen nur für ATP-Plan 1-und Plan 2-Abonnenten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="01b1b-232">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="01b1b-233">In Organisationen mit ATP können Administratoren isolierte Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams verwalten.</span><span class="sxs-lookup"><span data-stu-id="01b1b-233">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="01b1b-234">Anzeigen von isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="01b1b-234">View quarantined files</span></span>

1. <span data-ttu-id="01b1b-235">Wechseln Sie im Security and Compliance Center zu **Threat Management** \> **Review** \> **Quarantine**.</span><span class="sxs-lookup"><span data-stu-id="01b1b-235">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="01b1b-236">Ändern Sie die Ansicht in den Standardwert **Dateien**unter **Quarantäne** .</span><span class="sxs-lookup"><span data-stu-id="01b1b-236">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="01b1b-237">Sie können nach einem Feld sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="01b1b-237">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="01b1b-238">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="01b1b-238">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="01b1b-239">Klicken Sie auf **Spalten ändern** , um maximal sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="01b1b-239">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="01b1b-240">Die Standardspalten sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="01b1b-240">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="01b1b-241">**Benutzer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="01b1b-241">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="01b1b-242">**Speicherort**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="01b1b-242">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="01b1b-243">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="01b1b-243">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="01b1b-244">**Datei-URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="01b1b-244">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="01b1b-245">**Dateigröße**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="01b1b-245">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="01b1b-246">**Abläuft**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="01b1b-246">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="01b1b-247">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="01b1b-247">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="01b1b-248">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="01b1b-248">**Detected by**</span></span>

   - <span data-ttu-id="01b1b-249">**Geändert von Zeit**</span><span class="sxs-lookup"><span data-stu-id="01b1b-249">**Modified by time**</span></span>

4. <span data-ttu-id="01b1b-250">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="01b1b-250">To filter the results, click **Filter**.</span></span> <span data-ttu-id="01b1b-251">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="01b1b-251">The available filters are:</span></span>

   - <span data-ttu-id="01b1b-252">**Expires Time**: Filtern von Nachrichten nach Ablauf der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="01b1b-252">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="01b1b-253">**Heute**</span><span class="sxs-lookup"><span data-stu-id="01b1b-253">**Today**</span></span>

     - <span data-ttu-id="01b1b-254">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="01b1b-254">**Next 2 days**</span></span>

     - <span data-ttu-id="01b1b-255">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="01b1b-255">**Next 7 days**</span></span>

     - <span data-ttu-id="01b1b-256">Ein benutzerdefiniertes Datum/Zeitintervall.</span><span class="sxs-lookup"><span data-stu-id="01b1b-256">A custom date/time range.</span></span>

   - <span data-ttu-id="01b1b-257">**Empfangszeit**</span><span class="sxs-lookup"><span data-stu-id="01b1b-257">**Received time**</span></span>

   - <span data-ttu-id="01b1b-258">**Quarantäne Grund**: der einzige verfügbare Wert ist **Schadsoftware**.</span><span class="sxs-lookup"><span data-stu-id="01b1b-258">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="01b1b-259">Nachdem Sie eine bestimmte isolierte Datei gefunden haben, wählen Sie die Datei aus, um Details dazu anzuzeigen, und nehmen Sie Aktionen vor (beispielsweise anzeigen, freigeben, herunterladen oder Löschen der Nachricht).</span><span class="sxs-lookup"><span data-stu-id="01b1b-259">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="01b1b-260">Exportieren von Datei Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="01b1b-260">Export file results</span></span>

1. <span data-ttu-id="01b1b-261">Wählen Sie die Dateien aus, für die Sie sich interessieren, und klicken Sie auf **Ergebnisse exportieren**.</span><span class="sxs-lookup"><span data-stu-id="01b1b-261">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="01b1b-262">Klicken Sie in der Bestätigungsmeldung auf **Ja** , um zu warnen, dass das Browserfenster geöffnet bleibt.</span><span class="sxs-lookup"><span data-stu-id="01b1b-262">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="01b1b-263">Wenn der Export abgeschlossen ist, können Sie den Downloadspeicherort für die CSV-Datei benennen und auswählen.</span><span class="sxs-lookup"><span data-stu-id="01b1b-263">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="01b1b-264">Anzeigen von Details in isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="01b1b-264">View quarantined file details</span></span>

<span data-ttu-id="01b1b-265">Wenn Sie eine Datei in der Liste auswählen, werden im **Detail** -Flyout-Bereich die folgenden Dateidetails angezeigt:</span><span class="sxs-lookup"><span data-stu-id="01b1b-265">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="01b1b-266">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="01b1b-266">**File Name**</span></span>

- <span data-ttu-id="01b1b-267">**Datei-URL**: URL, die den Speicherort der Datei definiert (beispielsweise in SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="01b1b-267">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="01b1b-268">**Böswilliger Inhalt erkannt in** Das Datum/die Uhrzeit, zu dem die Datei isoliert wurde.</span><span class="sxs-lookup"><span data-stu-id="01b1b-268">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="01b1b-269">**Expires**: das Datum, an dem die Datei aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="01b1b-269">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="01b1b-270">**Erkannt von**: ATP (Advanced Threat Protection) oder Microsofts Anti-Malware Engine.</span><span class="sxs-lookup"><span data-stu-id="01b1b-270">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="01b1b-271">**Veröffentlicht?**</span><span class="sxs-lookup"><span data-stu-id="01b1b-271">**Released?**</span></span>

- <span data-ttu-id="01b1b-272">**Name der Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="01b1b-272">**Malware Name**</span></span>

- <span data-ttu-id="01b1b-273">**Dokument-ID**: ein eindeutiger Bezeichner für das Dokument.</span><span class="sxs-lookup"><span data-stu-id="01b1b-273">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="01b1b-274">**Dateigröße**: in Kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="01b1b-274">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="01b1b-275">**Organisation** Die eindeutige ID Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="01b1b-275">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="01b1b-276">**Zuletzt geändert**</span><span class="sxs-lookup"><span data-stu-id="01b1b-276">**Last modified**</span></span>

- <span data-ttu-id="01b1b-277">**Geändert von**: der Benutzer, der die Datei zuletzt geändert hat.</span><span class="sxs-lookup"><span data-stu-id="01b1b-277">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="01b1b-278">**Secure Hash Algorithm 256-Bit (SHA-256)-Wert**: Sie können diesen Hashwert verwenden, um die Datei in anderen Reputation Stores oder an anderen Speicherorten in Ihrer Umgebung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="01b1b-278">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="01b1b-279">Ausführen von Aktionen für isolierte Dateien</span><span class="sxs-lookup"><span data-stu-id="01b1b-279">Take action on quarantined files</span></span>

<span data-ttu-id="01b1b-280">Wenn Sie eine Datei in der Liste auswählen, können Sie die folgenden Aktionen für die Datei im **Detail** -Flyout-Bereich ausführen:</span><span class="sxs-lookup"><span data-stu-id="01b1b-280">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="01b1b-281">**Dateien freigeben**: Wählen Sie (Standard) aus, oder heben Sie **die Auswahl von Berichtsdateien für Microsoft für die Analyse auf**, und klicken Sie dann auf **Dateien freigeben**.</span><span class="sxs-lookup"><span data-stu-id="01b1b-281">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="01b1b-282">**Datei herunterladen**</span><span class="sxs-lookup"><span data-stu-id="01b1b-282">**Download file**</span></span>

- <span data-ttu-id="01b1b-283">**Datei aus Quarantäne entfernen**</span><span class="sxs-lookup"><span data-stu-id="01b1b-283">**Remove file from quarantine**</span></span>

<span data-ttu-id="01b1b-284">Wenn Sie die Dateien nicht freigeben oder entfernen, werden Sie nach Ablauf der standardmäßigen Aufbewahrungszeit für Quarantäne gelöscht.</span><span class="sxs-lookup"><span data-stu-id="01b1b-284">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="01b1b-285">Aktionen für mehrere isolierte Dateien</span><span class="sxs-lookup"><span data-stu-id="01b1b-285">Actions on multiple quarantined files</span></span>

<span data-ttu-id="01b1b-286">Wenn Sie mehrere isolierte Dateien in der Liste auswählen (bis zu 100), wird der Flyout-Bereich **Massenaktionen** angezeigt, in dem Sie die folgenden Aktionen ausführen können:</span><span class="sxs-lookup"><span data-stu-id="01b1b-286">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="01b1b-287">**Veröffentlichungsdateien**</span><span class="sxs-lookup"><span data-stu-id="01b1b-287">**Release files**</span></span>

- <span data-ttu-id="01b1b-288">**Dateien löschen**: Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, werden die Dateien sofort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="01b1b-288">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

<span data-ttu-id="01b1b-289">Wenn Sie fertig sind, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="01b1b-289">When you're finished, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="01b1b-290">Verwenden Exchange Online PowerShell oder eigenständiger Exchange Online Protection PowerShell zum Anzeigen und Verwalten von isolierten Nachrichten und Dateien</span><span class="sxs-lookup"><span data-stu-id="01b1b-290">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="01b1b-291">Folgende Cmdlets werden zum Anzeigen und Verwalten von Nachrichten und Dateien in der Quarantäne verwendet:</span><span class="sxs-lookup"><span data-stu-id="01b1b-291">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="01b1b-292">DELETE-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="01b1b-292">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="01b1b-293">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="01b1b-293">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="01b1b-294">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="01b1b-294">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="01b1b-295">[Vorschau-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Beachten Sie, dass dieses Cmdlet nur für Nachrichten gilt, nicht für Malware Dateien von ATP für SharePoint Online, OneDrive für Unternehmen oder Teams.</span><span class="sxs-lookup"><span data-stu-id="01b1b-295">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="01b1b-296">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="01b1b-296">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)

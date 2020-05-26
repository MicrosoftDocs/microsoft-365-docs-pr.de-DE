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
ms.openlocfilehash: 521268d291c73cc94e8be87f1f2896a17c623678
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352420"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="a7b43-104">Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP</span><span class="sxs-lookup"><span data-stu-id="a7b43-104">Manage quarantined messages and files as an admin in EOP</span></span>

<span data-ttu-id="a7b43-105">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a7b43-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="a7b43-106">Weitere Informationen finden Sie unter [Quarantäne-e-Mail-Nachrichten in EoP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a7b43-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="a7b43-107">Administratoren können alle Arten von isolierten Nachrichten für alle Benutzer anzeigen, freigeben und löschen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="a7b43-108">Nur Administratoren können Nachrichten verwalten, die als Schadsoftware, als hochgradig vertrauenswürdiges Phishing oder als Ergebnis von Nachrichtenfluss Regeln (auch bekannt als Transportregeln) isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="a7b43-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a7b43-109">Administratoren können auch falsch positive Ergebnisse an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="a7b43-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="a7b43-110">Administratoren in Organisationen mit Office 365 Advance Threat Protection (Office 365 ATP) können unter Quarantäne gestellte Dateien auch in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams anzeigen, herunterladen und löschen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-110">Admins in organizations with Office 365 Advance Threat Protection (Office 365 ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="a7b43-111">Sie können isolierte Nachrichten im Security & Compliance Center oder in PowerShell anzeigen und verwalten (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer).</span><span class="sxs-lookup"><span data-stu-id="a7b43-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a7b43-112">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="a7b43-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a7b43-113">Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="a7b43-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="a7b43-114">Um die Quarantäne-Seite direkt zu öffnen, wechseln Sie zu <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="a7b43-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="a7b43-115">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a7b43-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a7b43-116">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a7b43-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a7b43-117">Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Quarantäne als Administrator verwalten können. Die Berechtigungen werden durch die **Quarantäne** Rolle im Security & Compliance Center gesteuert.</span><span class="sxs-lookup"><span data-stu-id="a7b43-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="a7b43-118">Diese Rolle wird standardmäßig der Rollengruppe **Organisationsverwaltung** (Global Admins), **Quarantine Administrator**und **Sicherheitsadministrator** im Security & Compliance Center zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="a7b43-119">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a7b43-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="a7b43-120">Isolierte Nachrichten werden für einen Standardzeitraum aufbewahrt, bevor Sie automatisch gelöscht werden:</span><span class="sxs-lookup"><span data-stu-id="a7b43-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="a7b43-121">Nachrichten, die von antispamregeln (Spam, Phishing und Massen-e-Mails) unter Quarantäne gestellt werden: 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="a7b43-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="a7b43-122">Dies ist der Standard-und Höchstwert.</span><span class="sxs-lookup"><span data-stu-id="a7b43-122">This is the default and maximum value.</span></span> <span data-ttu-id="a7b43-123">Informationen zum Konfigurieren dieses Werts finden Sie unter [configure Anti-Spam Policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a7b43-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="a7b43-124">Nachrichten, die Schadsoftware enthalten: 15 Tage.</span><span class="sxs-lookup"><span data-stu-id="a7b43-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="a7b43-125">Wenn eine Nachricht aus der Quarantäne abläuft, können Sie Sie nicht wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="a7b43-126">Verwenden des Security & Compliance Center zum Verwalten von e-Mail-Nachrichten in Quarantäne</span><span class="sxs-lookup"><span data-stu-id="a7b43-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="a7b43-127">Anzeigen von e-Mails in Quarantäne</span><span class="sxs-lookup"><span data-stu-id="a7b43-127">View quarantined email</span></span>

1. <span data-ttu-id="a7b43-128">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="a7b43-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="a7b43-129">Stellen Sie sicher, dass die **Ansicht isoliert** auf den Standardwert **e-Mail**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a7b43-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="a7b43-130">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="a7b43-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="a7b43-131">Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="a7b43-132">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="a7b43-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="a7b43-133">**Empfangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a7b43-133">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="a7b43-134">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a7b43-134">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="a7b43-135">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a7b43-135">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="a7b43-136">**Quarantänegrund**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a7b43-136">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="a7b43-137">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a7b43-137">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="a7b43-138">**Richtlinientyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a7b43-138">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="a7b43-139">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="a7b43-139">**Recipient**</span></span>

   - <span data-ttu-id="a7b43-140">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="a7b43-140">**Message ID**</span></span>

   - <span data-ttu-id="a7b43-141">**Name der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="a7b43-141">**Policy name**</span></span>

   - <span data-ttu-id="a7b43-142">**Größe**</span><span class="sxs-lookup"><span data-stu-id="a7b43-142">**Size**</span></span>

   - <span data-ttu-id="a7b43-143">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="a7b43-143">**Direction**</span></span>

   <span data-ttu-id="a7b43-144">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**, oder klicken Sie auf **Als Standard festlegen**.</span><span class="sxs-lookup"><span data-stu-id="a7b43-144">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="a7b43-145">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="a7b43-145">To filter the results, click **Filter**.</span></span> <span data-ttu-id="a7b43-146">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="a7b43-146">The available filters are:</span></span>

   - <span data-ttu-id="a7b43-147">**Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="a7b43-147">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="a7b43-148">**Heute**</span><span class="sxs-lookup"><span data-stu-id="a7b43-148">**Today**</span></span>

     - <span data-ttu-id="a7b43-149">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="a7b43-149">**Next 2 days**</span></span>

     - <span data-ttu-id="a7b43-150">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="a7b43-150">**Next 7 days**</span></span>

     - <span data-ttu-id="a7b43-151">**Benutzerdefiniert**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="a7b43-151">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="a7b43-152">**Empfangszeit**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="a7b43-152">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="a7b43-153">**Quarantänegrund**:</span><span class="sxs-lookup"><span data-stu-id="a7b43-153">**Quarantine reason**:</span></span>

     - <span data-ttu-id="a7b43-154">**Richtlinie**: die Nachricht stimmte mit den Bedingungen einer Nachrichtenfluss Regel überein (auch als Transportregel bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="a7b43-154">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="a7b43-155">**Massensendung**</span><span class="sxs-lookup"><span data-stu-id="a7b43-155">**Bulk**</span></span>

     - <span data-ttu-id="a7b43-156">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="a7b43-156">**Phish**</span></span>

     - <span data-ttu-id="a7b43-157">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="a7b43-157">**Malware**</span></span>

     - <span data-ttu-id="a7b43-158">**Spam**</span><span class="sxs-lookup"><span data-stu-id="a7b43-158">**Spam**</span></span>

     - <span data-ttu-id="a7b43-159">**Phishing mit hoher Zuverlässigkeit**</span><span class="sxs-lookup"><span data-stu-id="a7b43-159">**High Confidence Phish**</span></span>

   - <span data-ttu-id="a7b43-160">**E-Mail-Empfänger**: alle Benutzer oder nur an Sie gesendete Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a7b43-160">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="a7b43-161">Endbenutzer können nur isolierte Nachrichten verwalten, die an Sie gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="a7b43-161">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="a7b43-162">Klicken Sie auf **Löschen**, um den Filter zu löschen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-162">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="a7b43-163">Um das Filter-Flyout auszublenden, klicken Sie erneut auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="a7b43-163">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="a7b43-164">Verwenden Sie **Ergebnisse sortieren nach** (standardmäßig die Schaltfläche **Nachrichten-ID**) und einen entsprechenden Wert, um bestimmte Nachrichten zu finden.</span><span class="sxs-lookup"><span data-stu-id="a7b43-164">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="a7b43-165">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a7b43-165">Wildcards aren't supported.</span></span> <span data-ttu-id="a7b43-166">Sie können nach den folgenden Werten suchen:</span><span class="sxs-lookup"><span data-stu-id="a7b43-166">You can search by the following values:</span></span>

   - <span data-ttu-id="a7b43-167">**Nachrichten-ID**: Die globale eindeutige ID der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a7b43-167">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="a7b43-168">Beispielsweise haben Sie die [Nachrichtenablaufverfolgung](message-trace-scc.md) verwendet, um nach einer Nachricht zu suchen, die an einen Benutzer in Ihrer Organisation gesendet wurde, und Sie bestimmen, dass die Nachricht in Quarantäne statt übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="a7b43-168">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="a7b43-169">Achten Sie darauf, den vollständigen Meldungs-ID-Wert einzuschließen, der möglicherweise spitzen Klammern ( \< \> ) enthält.</span><span class="sxs-lookup"><span data-stu-id="a7b43-169">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="a7b43-170">Zum Beispiel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="a7b43-170">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="a7b43-171">**E-Mail-Adresse des Absenders**: Die E-Mail-Adresse eines einzelnen Absenders.</span><span class="sxs-lookup"><span data-stu-id="a7b43-171">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="a7b43-172">**E-Mail-Adresse des Empfängers**: Die E-Mail-Adresse eines einzelnen Empfängers.</span><span class="sxs-lookup"><span data-stu-id="a7b43-172">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="a7b43-173">**Betreff**: Verwenden Sie den gesamten Betreff der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a7b43-173">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="a7b43-174">Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="a7b43-174">The search is not case-sensitive.</span></span>

   <span data-ttu-id="a7b43-175">Nachdem Sie die Suchkriterien eingegeben haben, klicken Sie auf die ![Schaltfläche Aktualisieren](../../media/scc-quarantine-refresh.png) **Aktualisieren**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="a7b43-175">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="a7b43-176">Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Maßnahmen zu ergreifen (z. B. die Nachricht anzeigen, freigeben, herunterladen oder löschen).</span><span class="sxs-lookup"><span data-stu-id="a7b43-176">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="a7b43-177">Nachrichtenergebnisse exportieren</span><span class="sxs-lookup"><span data-stu-id="a7b43-177">Export message results</span></span>

1. <span data-ttu-id="a7b43-178">Wählen Sie die gewünschten Nachrichten aus, und klicken Sie auf **Ergebnisse exportieren**.</span><span class="sxs-lookup"><span data-stu-id="a7b43-178">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="a7b43-179">Klicken Sie auf **Ja** in der Bestätigungsnachricht, die Sie warnt, das Browserfenster geöffnet zu lassen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-179">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="a7b43-180">Wenn Ihr Export fertig ist, können Sie den Speicherort für die .csv-Datei benennen und auswählen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-180">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="a7b43-181">Anzeigen von Details der isolierten Nachricht</span><span class="sxs-lookup"><span data-stu-id="a7b43-181">View quarantined message details</span></span>

<span data-ttu-id="a7b43-182">Wenn Sie eine E-Mail-Nachricht in der Liste auswählen, werden die folgenden Nachrichtendetails im Flyout-Fenster **Details** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a7b43-182">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a7b43-183">**Nachrichten-ID**: Die globale eindeutige ID für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a7b43-183">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="a7b43-184">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="a7b43-184">**Sender address**</span></span>

- <span data-ttu-id="a7b43-185">**Empfangen**: Das Datum/die Uhrzeit des Nachrichtenempfangs.</span><span class="sxs-lookup"><span data-stu-id="a7b43-185">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="a7b43-186">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="a7b43-186">**Subject**</span></span>

- <span data-ttu-id="a7b43-187">**Quarantäne Grund**: zeigt an, ob eine Nachricht als **Spam**, **Massen**, **Phishing**, Übereinstimmung mit einer Nachrichtenfluss Regel (**Transport Regel**) identifiziert wurde oder als enthaltender **Schadsoftware**erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="a7b43-187">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="a7b43-188">**Empfänger**: Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Vorschau der Nachricht anzeigen** oder **Nachrichten** Kopfzeile anzeigen klicken, um die gesamte Liste der Empfänger anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-188">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="a7b43-189">**Läuft ab**. Das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="a7b43-189">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="a7b43-190">**Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a7b43-190">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="a7b43-191">**Noch nicht freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht noch nicht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a7b43-191">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="a7b43-192">Maßnahmen für isolierte E-Mails ergreifen</span><span class="sxs-lookup"><span data-stu-id="a7b43-192">Take action on quarantined email</span></span>

<span data-ttu-id="a7b43-193">Nachdem Sie eine Nachricht ausgewählt haben, haben Sie mehrere Möglichkeiten, mit den Nachrichten im **Detail** -Flyout-Bereich zu tun:</span><span class="sxs-lookup"><span data-stu-id="a7b43-193">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a7b43-194">**Nachricht freigeben**: Wählen Sie im eingeblendeten Flyout-Bereich die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a7b43-194">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="a7b43-195">**Melden von Nachrichten an Microsoft zur Analyse**: diese Option ist standardmäßig aktiviert und meldet die irrtümlich unter Quarantäne gestellte Nachricht an Microsoft als falsch positiv.</span><span class="sxs-lookup"><span data-stu-id="a7b43-195">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="a7b43-196">Wenn die Nachricht als Spam, Massen, Phishing oder mit Schadsoftware isoliert wurde, wird die Nachricht auch an das Microsoft-Spam Analyse Team gemeldet.</span><span class="sxs-lookup"><span data-stu-id="a7b43-196">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="a7b43-197">Je nach Analyse können die Dienst weiten spamfilterregeln so angepasst werden, dass die Nachricht durchlassen wird.</span><span class="sxs-lookup"><span data-stu-id="a7b43-197">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="a7b43-198">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a7b43-198">Choose one of the following options:</span></span>

    - <span data-ttu-id="a7b43-199">**Freigeben von Nachrichten für alle Empfänger**</span><span class="sxs-lookup"><span data-stu-id="a7b43-199">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="a7b43-200">**Freigeben von Nachrichten an bestimmte Empfänger**</span><span class="sxs-lookup"><span data-stu-id="a7b43-200">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="a7b43-201">**Freigeben von Nachrichten für andere Personen**</span><span class="sxs-lookup"><span data-stu-id="a7b43-201">**Release messages to other people**</span></span>

  <span data-ttu-id="a7b43-202">Klicken Sie nach Abschluss des Vorgangs auf **Nachrichten freigeben**.</span><span class="sxs-lookup"><span data-stu-id="a7b43-202">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="a7b43-203">Hinweise zum Freigeben von Nachrichten:</span><span class="sxs-lookup"><span data-stu-id="a7b43-203">Notes about releasing messages:</span></span>

  - <span data-ttu-id="a7b43-204">Sie können eine Nachricht nur einmal an denselben Empfänger freigeben.</span><span class="sxs-lookup"><span data-stu-id="a7b43-204">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="a7b43-205">Nur Empfänger, die die Nachricht nicht erhalten haben, werden in der Liste der potenziellen Empfänger angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a7b43-205">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="a7b43-206">**Nachrichtenkopf anzeigen**: Wählen Sie diesen Link aus, um den Nachrichtenkopftext anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-206">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="a7b43-207">Um den Nachrichtenkopf im Detail zu analysieren, kopieren Sie den Nachrichtenkopftext in die Zwischenablage, und wählen Sie dann **Microsoft-Nachrichtenkopfanalyse** aus, um zur Remoteverbindungsuntersuchung zu wechseln (klicken Sie mit der rechten Maustaste, und wählen Sie **In neuer Registerkarte öffnen** aus, wenn Sie Microsoft 365 nicht verlassen möchten, um die Aufgabe auszuführen).</span><span class="sxs-lookup"><span data-stu-id="a7b43-207">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="a7b43-208">Fügen Sie den Nachrichtenkopf auf der Seite in den Abschnitt "Nachrichtenkopfanalyse" ein, und wählen Sie dann **Kopfzeilen analysieren** aus:</span><span class="sxs-lookup"><span data-stu-id="a7b43-208">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="a7b43-209">**Vorschau der Nachricht anzeigen**: Wählen Sie im angezeigten Flyout-Fenster eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="a7b43-209">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="a7b43-210">**Quellansicht**: Zeigt die HTML-Version des Nachrichtentextes an, wobei alle Links deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="a7b43-210">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="a7b43-211">**Textansicht**: Zeigt den Nachrichtentext im Klartext an.</span><span class="sxs-lookup"><span data-stu-id="a7b43-211">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="a7b43-212">**Aus Quarantäne entfernen**: Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="a7b43-212">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="a7b43-213">**Nachricht herunterladen**: Wählen Sie im daraufhin angezeigten Flyout-Fenster **Ich verstehe die Risiken beim Herunterladen dieser Nachricht** aus, um eine lokale Kopie der Nachricht im eml-Format zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a7b43-213">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="a7b43-214">**Nachricht übermitteln**: Wählen Sie im eingeblendeten Flyout-Bereich die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a7b43-214">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="a7b43-215">**Objekttyp**: **e-Mail** (Standard), **URL**oder **Anlage**.</span><span class="sxs-lookup"><span data-stu-id="a7b43-215">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="a7b43-216">**Übermittlungs Format**: **Netzwerknachrichten-ID** (Standard, mit dem entsprechenden Wert im Feld **Netzwerknachrichten-ID** ) oder **Datei** (wechseln Sie zu einer lokalen eml-oder msg-Datei).</span><span class="sxs-lookup"><span data-stu-id="a7b43-216">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="a7b43-217">Beachten Sie Folgendes: Wenn Sie **Datei** auswählen und dann **Netzwerknachrichten-ID**auswählen, ist der anfängliche Wert nicht mehr vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a7b43-217">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="a7b43-218">**Recipients**: Geben Sie bei Lease einen ursprünglichen Empfänger der Nachricht ein, oder klicken Sie auf **Alles auswählen** , um alle Empfänger zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a7b43-218">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="a7b43-219">Sie können auch auf **Alle auswählen** klicken und dann einzelne Empfänger selektiv entfernen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-219">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="a7b43-220">**Grund für die Übermittlung**: **sollte nicht blockiert worden sein** (Standard) oder hätte **blockiert werden**müssen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-220">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="a7b43-221">Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="a7b43-221">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="a7b43-222">Wenn Sie die Nachricht nicht freigeben oder entfernen, wird sie nach Ablauf der Standard-Quarantäneaufbewahrungszeit gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a7b43-222">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="a7b43-223">Maßnahmen für mehrere isolierte E-Mail-Nachrichten ergreifen</span><span class="sxs-lookup"><span data-stu-id="a7b43-223">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="a7b43-224">Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), erscheint das Flyout-Fenster **Massenaktionen**, in dem Sie die folgenden Aktionen durchführen können:</span><span class="sxs-lookup"><span data-stu-id="a7b43-224">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="a7b43-225">**Nachrichten freigeben**: Die Optionen sind die gleichen wie bei der Freigabe einer einzelnen Nachricht, außer dass Sie nicht **Nachrichten an bestimmte Empfänger freigeben** auswählen können; Sie können nur **Nachricht an alle Empfänger freigeben** oder **Nachrichten an andere Personen freigeben** auswählen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-225">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="a7b43-226">**Nachrichten löschen**: Nachdem Sie in der angezeigten Warnung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="a7b43-226">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="a7b43-227">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="a7b43-227">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="a7b43-228">Nur ATP: Verwenden Sie das Security & Compliance Center, um isolierte Dateien zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="a7b43-228">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="a7b43-229">Die Verfahren für in Quarantäne befindliche Dateien in diesem Abschnitt stehen nur für ATP-Plan 1-und Plan 2-Abonnenten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a7b43-229">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="a7b43-230">In Organisationen mit ATP können Administratoren isolierte Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams verwalten.</span><span class="sxs-lookup"><span data-stu-id="a7b43-230">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="a7b43-231">Anzeigen von isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="a7b43-231">View quarantined files</span></span>

1. <span data-ttu-id="a7b43-232">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="a7b43-232">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="a7b43-233">Ändern Sie die Ansicht in den Standardwert **Dateien**unter **Quarantäne** .</span><span class="sxs-lookup"><span data-stu-id="a7b43-233">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="a7b43-234">Sie können nach einem Feld sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="a7b43-234">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="a7b43-235">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="a7b43-235">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="a7b43-236">Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-236">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="a7b43-237">Die Standardspalten sind mit einem Sternchen ( <sup>\*</sup> ) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="a7b43-237">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="a7b43-238">**Benutzer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a7b43-238">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="a7b43-239">**Speicherort**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a7b43-239">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="a7b43-240">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a7b43-240">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="a7b43-241">**Datei-URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a7b43-241">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="a7b43-242">**Dateigröße**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a7b43-242">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="a7b43-243">**Läuft ab**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a7b43-243">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="a7b43-244">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a7b43-244">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="a7b43-245">**Erkannt von**</span><span class="sxs-lookup"><span data-stu-id="a7b43-245">**Detected by**</span></span>

   - <span data-ttu-id="a7b43-246">**Geändert von Zeit**</span><span class="sxs-lookup"><span data-stu-id="a7b43-246">**Modified by time**</span></span>

4. <span data-ttu-id="a7b43-247">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="a7b43-247">To filter the results, click **Filter**.</span></span> <span data-ttu-id="a7b43-248">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="a7b43-248">The available filters are:</span></span>

   - <span data-ttu-id="a7b43-249">**Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="a7b43-249">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="a7b43-250">**Heute**</span><span class="sxs-lookup"><span data-stu-id="a7b43-250">**Today**</span></span>

     - <span data-ttu-id="a7b43-251">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="a7b43-251">**Next 2 days**</span></span>

     - <span data-ttu-id="a7b43-252">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="a7b43-252">**Next 7 days**</span></span>

     - <span data-ttu-id="a7b43-253">Ein benutzerdefiniertes Datum/Zeitintervall.</span><span class="sxs-lookup"><span data-stu-id="a7b43-253">A custom date/time range.</span></span>

   - <span data-ttu-id="a7b43-254">**Empfangszeit**</span><span class="sxs-lookup"><span data-stu-id="a7b43-254">**Received time**</span></span>

   - <span data-ttu-id="a7b43-255">**Quarantäne Grund**: der einzige verfügbare Wert ist **Schadsoftware**.</span><span class="sxs-lookup"><span data-stu-id="a7b43-255">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="a7b43-256">Nachdem Sie eine bestimmte isolierte Datei gefunden haben, wählen Sie die Datei aus, um Details dazu anzuzeigen, und nehmen Sie Aktionen vor (beispielsweise anzeigen, freigeben, herunterladen oder Löschen der Nachricht).</span><span class="sxs-lookup"><span data-stu-id="a7b43-256">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="a7b43-257">Exportieren von Datei Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a7b43-257">Export file results</span></span>

1. <span data-ttu-id="a7b43-258">Wählen Sie die Dateien aus, für die Sie sich interessieren, und klicken Sie auf **Ergebnisse exportieren**.</span><span class="sxs-lookup"><span data-stu-id="a7b43-258">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="a7b43-259">Klicken Sie auf **Ja** in der Bestätigungsnachricht, die Sie warnt, das Browserfenster geöffnet zu lassen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-259">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="a7b43-260">Wenn Ihr Export fertig ist, können Sie den Speicherort für die .csv-Datei benennen und auswählen.</span><span class="sxs-lookup"><span data-stu-id="a7b43-260">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="a7b43-261">Anzeigen von Details in isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="a7b43-261">View quarantined file details</span></span>

<span data-ttu-id="a7b43-262">Wenn Sie eine Datei in der Liste auswählen, werden im **Detail** -Flyout-Bereich die folgenden Dateidetails angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a7b43-262">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a7b43-263">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="a7b43-263">**File Name**</span></span>

- <span data-ttu-id="a7b43-264">**Datei-URL**: URL, die den Speicherort der Datei definiert (beispielsweise in SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="a7b43-264">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="a7b43-265">**Böswilliger Inhalt erkannt in** Das Datum/die Uhrzeit, zu dem die Datei isoliert wurde.</span><span class="sxs-lookup"><span data-stu-id="a7b43-265">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="a7b43-266">**Expires**: das Datum, an dem die Datei aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="a7b43-266">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="a7b43-267">**Erkannt von**: ATP (Advanced Threat Protection) oder Microsofts Anti-Malware Engine.</span><span class="sxs-lookup"><span data-stu-id="a7b43-267">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="a7b43-268">**Veröffentlicht?**</span><span class="sxs-lookup"><span data-stu-id="a7b43-268">**Released?**</span></span>

- <span data-ttu-id="a7b43-269">**Name der Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="a7b43-269">**Malware Name**</span></span>

- <span data-ttu-id="a7b43-270">**Dokument-ID**: ein eindeutiger Bezeichner für das Dokument.</span><span class="sxs-lookup"><span data-stu-id="a7b43-270">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="a7b43-271">**Dateigröße**: in Kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="a7b43-271">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="a7b43-272">**Organisation** Die eindeutige ID Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="a7b43-272">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="a7b43-273">**Zuletzt geändert**</span><span class="sxs-lookup"><span data-stu-id="a7b43-273">**Last modified**</span></span>

- <span data-ttu-id="a7b43-274">**Geändert von**: der Benutzer, der die Datei zuletzt geändert hat.</span><span class="sxs-lookup"><span data-stu-id="a7b43-274">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="a7b43-275">**Secure Hash Algorithm 256-Bit (SHA-256)-Wert**: Sie können diesen Hashwert verwenden, um die Datei in anderen Reputation Stores oder an anderen Speicherorten in Ihrer Umgebung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a7b43-275">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="a7b43-276">Ausführen von Aktionen für isolierte Dateien</span><span class="sxs-lookup"><span data-stu-id="a7b43-276">Take action on quarantined files</span></span>

<span data-ttu-id="a7b43-277">Wenn Sie eine Datei in der Liste auswählen, können Sie die folgenden Aktionen für die Datei im **Detail** -Flyout-Bereich ausführen:</span><span class="sxs-lookup"><span data-stu-id="a7b43-277">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a7b43-278">**Dateien freigeben**: Wählen Sie (Standard) aus, oder heben Sie **die Auswahl von Berichtsdateien für Microsoft für die Analyse auf**, und klicken Sie dann auf **Dateien freigeben**.</span><span class="sxs-lookup"><span data-stu-id="a7b43-278">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="a7b43-279">**Datei herunterladen**</span><span class="sxs-lookup"><span data-stu-id="a7b43-279">**Download file**</span></span>

- <span data-ttu-id="a7b43-280">**Datei aus Quarantäne entfernen**</span><span class="sxs-lookup"><span data-stu-id="a7b43-280">**Remove file from quarantine**</span></span>

<span data-ttu-id="a7b43-281">Wenn Sie die Dateien nicht freigeben oder entfernen, werden Sie nach Ablauf der standardmäßigen Aufbewahrungszeit für Quarantäne gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a7b43-281">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="a7b43-282">Aktionen für mehrere isolierte Dateien</span><span class="sxs-lookup"><span data-stu-id="a7b43-282">Actions on multiple quarantined files</span></span>

<span data-ttu-id="a7b43-283">Wenn Sie mehrere isolierte Dateien in der Liste auswählen (bis zu 100), wird der Flyout-Bereich **Massenaktionen** angezeigt, in dem Sie die folgenden Aktionen ausführen können:</span><span class="sxs-lookup"><span data-stu-id="a7b43-283">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="a7b43-284">**Veröffentlichungsdateien**</span><span class="sxs-lookup"><span data-stu-id="a7b43-284">**Release files**</span></span>

- <span data-ttu-id="a7b43-285">**Dateien löschen**: Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, werden die Dateien sofort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a7b43-285">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="a7b43-286">Melden Sie sich mit einem Arbeits-oder Schulkonto mit globalen Administratorrechten (oder geeigneten Sicherheits & Compliance Center-Rollen) in Ihrer Organisation an, und [wechseln Sie zum Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a7b43-286">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="a7b43-287">Verwenden Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Anzeigen und Verwalten von isolierten Nachrichten und Dateien</span><span class="sxs-lookup"><span data-stu-id="a7b43-287">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="a7b43-288">Folgende Cmdlets werden zum Anzeigen und Verwalten von Nachrichten und Dateien in der Quarantäne verwendet:</span><span class="sxs-lookup"><span data-stu-id="a7b43-288">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="a7b43-289">DELETE-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="a7b43-289">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="a7b43-290">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="a7b43-290">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="a7b43-291">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="a7b43-291">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="a7b43-292">[Vorschau-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Beachten Sie, dass dieses Cmdlet nur für Nachrichten gilt, nicht für Malware Dateien von ATP für SharePoint Online, OneDrive für Unternehmen oder Teams.</span><span class="sxs-lookup"><span data-stu-id="a7b43-292">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="a7b43-293">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="a7b43-293">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)

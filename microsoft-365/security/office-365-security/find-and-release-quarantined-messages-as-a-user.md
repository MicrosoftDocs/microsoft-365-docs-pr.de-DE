---
title: Finden und Freigeben von Nachrichten unter Quarantäne als Benutzer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: Als Microsoft 365-Benutzer können Sie Ihre unter Quarantäne gestellten Nachrichten anzeigen, freigeben und löschen (Nachrichten, bei denen Sie ein Empfänger sind und der Spam-Filter die Nachricht als Spam oder Massen-E-Mail unter Quarantäne gestellt hat). Sie können Ihre isolierten Nachrichten im Security & Compliance Center anzeigen und verwalten.
ms.openlocfilehash: b8ab5835a29ccf0c58d27f56fe84d29745419b1a
ms.sourcegitcommit: 481fb95d8b80cf2102a9c73b21e7effa79e594e7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "43809009"
---
# <a name="find-and-release-quarantined-messages-as-a-user"></a><span data-ttu-id="dd211-104">Finden und Freigeben von Nachrichten unter Quarantäne als Benutzer</span><span class="sxs-lookup"><span data-stu-id="dd211-104">Find and release quarantined messages as a user</span></span>

<span data-ttu-id="dd211-105">Die Quarantäne enthält potenziell gefährliche oder unerwünschte Nachrichten in Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="dd211-105">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="dd211-106">Weitere Informationen finden Sie unter [Quarantäne in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="dd211-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="dd211-107">Als Benutzer können Sie unter Quarantäne gestellte Nachrichten anzeigen, freigeben und löschen, wenn Sie ein Empfänger sind und die Nachricht als Spam, Massen-E-Mail oder (ab April 2020) als Phishing unter Quarantäne gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="dd211-107">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="dd211-108">Sie können die in Quarantäne befindlichen Nachrichten im Security & Compliance Center oder (wenn ein Administrator dies eingerichtet hat) in [Spambenachrichtigungen für Endbenutzer](use-spam-notifications-to-release-and-report-quarantined-messages.md) anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="dd211-108">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dd211-109">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="dd211-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="dd211-110">Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="dd211-110">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="dd211-111">Um die Quarantäne-Seite direkt zu öffnen, wechseln Sie zu <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="dd211-111">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="dd211-112">Administratoren können konfigurieren, wie lange Nachrichten isoliert werden, bevor sie endgültig gelöscht werden (Anti-Spam-Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="dd211-112">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="dd211-113">Nachrichten, die aus der Quarantäne abgelaufen sind, können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="dd211-113">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="dd211-114">Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dd211-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="dd211-115">Administratoren können auch [Spam-Benachrichtigungen für Endbenutzer](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in Anti-Spam-Richtlinien aktivieren.</span><span class="sxs-lookup"><span data-stu-id="dd211-115">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="dd211-116">Benutzer können in Quarantäne gestellte Spamnachrichten, aber nicht in Quarantäne gestellte Phishingnachrichten, direkt aus diesen Benachrichtigungen heraus freigeben.</span><span class="sxs-lookup"><span data-stu-id="dd211-116">Users can release spam quarantined messages but not phish quarantined messages directly from these notifications.</span></span> <span data-ttu-id="dd211-117">Weitere Informationen finden Sie unter [Spam-Benachrichtigungen für Endbenutzer in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="dd211-117">For more information, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="dd211-118">Nachrichten, die wegen hoher Phishingwahrscheinlichkeit, Schadsoftware oder durch Nachrichtenflussregeln (auch als Transportregeln bekannt) unter Quarantäne gestellt wurden, sind nur für Administratoren verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dd211-118">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="dd211-119">Phishing-Nachrichten können von Benutzern überprüft, aber nur von Administratoren freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="dd211-119">Phish messages can be reviewed by users but only released by admins.</span></span> <span data-ttu-id="dd211-120">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="dd211-120">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="dd211-121">Sie können eine Nachricht nur einmal freigeben und als falsch positiv markiert (keine Junk-E-Mail) melden.</span><span class="sxs-lookup"><span data-stu-id="dd211-121">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="dd211-122">Anzeigen Ihrer isolierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="dd211-122">View your quarantined messages</span></span>

1. <span data-ttu-id="dd211-123">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="dd211-123">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="dd211-124">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="dd211-124">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="dd211-125">Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd211-125">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="dd211-126">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="dd211-126">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="dd211-127">**Empfangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dd211-127">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="dd211-128">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dd211-128">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="dd211-129">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dd211-129">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="dd211-130">**Quarantänegrund**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dd211-130">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="dd211-131">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dd211-131">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="dd211-132">**Richtlinientyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dd211-132">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="dd211-133">**Läuft ab**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dd211-133">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="dd211-134">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="dd211-134">**Recipient**</span></span>

   - <span data-ttu-id="dd211-135">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="dd211-135">**Message ID**</span></span>

   - <span data-ttu-id="dd211-136">**Name der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="dd211-136">**Policy name**</span></span>

   - <span data-ttu-id="dd211-137">**Größe**</span><span class="sxs-lookup"><span data-stu-id="dd211-137">**Size**</span></span>

   - <span data-ttu-id="dd211-138">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="dd211-138">**Direction**</span></span>

   <span data-ttu-id="dd211-139">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**, oder klicken Sie auf **Als Standard festlegen**.</span><span class="sxs-lookup"><span data-stu-id="dd211-139">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="dd211-140">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="dd211-140">To filter the results, click **Filter**.</span></span> <span data-ttu-id="dd211-141">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="dd211-141">The available filters are:</span></span>

   - <span data-ttu-id="dd211-142">**Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="dd211-142">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="dd211-143">**Heute**</span><span class="sxs-lookup"><span data-stu-id="dd211-143">**Today**</span></span>

     - <span data-ttu-id="dd211-144">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="dd211-144">**Next 2 days**</span></span>

     - <span data-ttu-id="dd211-145">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="dd211-145">**Next 7 days**</span></span>

     - <span data-ttu-id="dd211-146">**Benutzerdefiniert**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="dd211-146">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="dd211-147">**Empfangszeit**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="dd211-147">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="dd211-148">**Quarantänegrund**:</span><span class="sxs-lookup"><span data-stu-id="dd211-148">**Quarantine reason**:</span></span>

     - <span data-ttu-id="dd211-149">**Massensendung**</span><span class="sxs-lookup"><span data-stu-id="dd211-149">**Bulk**</span></span>

     - <span data-ttu-id="dd211-150">**Spam**</span><span class="sxs-lookup"><span data-stu-id="dd211-150">**Spam**</span></span>

     - <span data-ttu-id="dd211-151">**Phishing** (ab April 2020)</span><span class="sxs-lookup"><span data-stu-id="dd211-151">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="dd211-152">Klicken Sie auf **Löschen**, um den Filter zu löschen.</span><span class="sxs-lookup"><span data-stu-id="dd211-152">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="dd211-153">Um das Filter-Flyout auszublenden, klicken Sie erneut auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="dd211-153">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="dd211-154">Verwenden Sie **Ergebnisse sortieren nach** (standardmäßig die Schaltfläche **Nachrichten-ID**) und einen entsprechenden Wert, um bestimmte Nachrichten zu finden.</span><span class="sxs-lookup"><span data-stu-id="dd211-154">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="dd211-155">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dd211-155">Wildcards aren't supported.</span></span> <span data-ttu-id="dd211-156">Sie können nach den folgenden Werten suchen:</span><span class="sxs-lookup"><span data-stu-id="dd211-156">You can search by the following values:</span></span>

   - <span data-ttu-id="dd211-157">**Nachrichten-ID**: Die globale eindeutige ID der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="dd211-157">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="dd211-158">Wenn Sie eine Nachricht in der Liste auswählen, wird der Wert **Nachrichten-ID** im Flyout-Fenster **Details** angezeigt, der angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dd211-158">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="dd211-159">Administratoren können [Nachrichtenverfolgung](message-trace-scc.md) verwenden, um Nachrichten und die entsprechenden Nachrichten-ID-Werte zu suchen.</span><span class="sxs-lookup"><span data-stu-id="dd211-159">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="dd211-160">**E-Mail-Adresse des Absenders**: Die E-Mail-Adresse eines einzelnen Absenders.</span><span class="sxs-lookup"><span data-stu-id="dd211-160">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="dd211-161">**E-Mail-Adresse des Empfängers**: Die E-Mail-Adresse eines einzelnen Empfängers.</span><span class="sxs-lookup"><span data-stu-id="dd211-161">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="dd211-162">**Betreff**: Verwenden Sie den gesamten Betreff der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="dd211-162">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="dd211-163">Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="dd211-163">The search is not case-sensitive.</span></span>

   <span data-ttu-id="dd211-164">Nachdem Sie die Suchkriterien eingegeben haben, klicken Sie auf die ![Schaltfläche Aktualisieren](../../media/scc-quarantine-refresh.png) **Aktualisieren**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="dd211-164">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="dd211-165">Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Maßnahmen zu ergreifen (z. B. die Nachricht anzeigen, freigeben, herunterladen oder löschen).</span><span class="sxs-lookup"><span data-stu-id="dd211-165">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="dd211-166">Nachrichtenergebnisse exportieren</span><span class="sxs-lookup"><span data-stu-id="dd211-166">Export message results</span></span>

1. <span data-ttu-id="dd211-167">Wählen Sie die gewünschten Nachrichten aus, und klicken Sie auf **Ergebnisse exportieren**.</span><span class="sxs-lookup"><span data-stu-id="dd211-167">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="dd211-168">Klicken Sie auf **Ja** in der Bestätigungsnachricht, die Sie warnt, das Browserfenster geöffnet zu lassen.</span><span class="sxs-lookup"><span data-stu-id="dd211-168">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="dd211-169">Wenn Ihr Export fertig ist, können Sie den Speicherort für die .csv-Datei benennen und auswählen.</span><span class="sxs-lookup"><span data-stu-id="dd211-169">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="dd211-170">Anzeigen von Details der isolierten Nachricht</span><span class="sxs-lookup"><span data-stu-id="dd211-170">View quarantined message details</span></span>

<span data-ttu-id="dd211-171">Wenn Sie eine E-Mail-Nachricht in der Liste auswählen, werden die folgenden Nachrichtendetails im Flyout-Fenster **Details** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="dd211-171">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="dd211-172">**Nachrichten-ID**: Die globale eindeutige ID für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="dd211-172">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="dd211-173">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="dd211-173">**Sender address**</span></span>

- <span data-ttu-id="dd211-174">**Empfangen**: Das Datum/die Uhrzeit des Nachrichtenempfangs.</span><span class="sxs-lookup"><span data-stu-id="dd211-174">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="dd211-175">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="dd211-175">**Subject**</span></span>

- <span data-ttu-id="dd211-176">**Quarantänegrund**: Zeigt an, ob eine Nachricht als **Spam**, **Massensendung** oder (ab April 2020) **Phishing** erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="dd211-176">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="dd211-177">**Empfänger**: Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Vorschau der Nachricht anzeigen** oder **Nachrichten** Kopfzeile anzeigen klicken, um die gesamte Liste der Empfänger anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd211-177">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="dd211-178">**Läuft ab**. Das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="dd211-178">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="dd211-179">**Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="dd211-179">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="dd211-180">**Noch nicht freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht noch nicht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="dd211-180">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="dd211-181">Maßnahmen für isolierte E-Mails ergreifen</span><span class="sxs-lookup"><span data-stu-id="dd211-181">Take action on quarantined email</span></span>

<span data-ttu-id="dd211-182">Nachdem Sie eine Nachricht ausgewählt haben, haben Sie Optionen, was mit den Nachrichten im Flyout-Fenster **Details** geschehen soll:</span><span class="sxs-lookup"><span data-stu-id="dd211-182">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="dd211-183">**Nachricht freigeben**: Wählen Sie im angezeigten Flyout-Fenster, ob Sie **Meldungen zur Analyse an Microsoft melden** möchten.</span><span class="sxs-lookup"><span data-stu-id="dd211-183">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="dd211-184">Diese ist standardmäßig ausgewählt und meldet die irrtümlich isolierte Nachricht an Microsoft als falsches positives Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="dd211-184">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="dd211-185">Klicken Sie nach Abschluss des Vorgangs auf **Nachrichten freigeben**.</span><span class="sxs-lookup"><span data-stu-id="dd211-185">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="dd211-186">**Nachrichtenkopf anzeigen**: Wählen Sie diesen Link aus, um den Nachrichtenkopftext anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd211-186">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="dd211-187">Um den Nachrichtenkopf im Detail zu analysieren, kopieren Sie den Nachrichtenkopftext in die Zwischenablage, und wählen Sie dann **Microsoft-Nachrichtenkopfanalyse** aus, um zur Remoteverbindungsuntersuchung zu wechseln (klicken Sie mit der rechten Maustaste, und wählen Sie **In neuer Registerkarte öffnen** aus, wenn Sie Microsoft 365 nicht verlassen möchten, um die Aufgabe auszuführen).</span><span class="sxs-lookup"><span data-stu-id="dd211-187">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="dd211-188">Fügen Sie den Nachrichtenkopf auf der Seite in den Abschnitt "Nachrichtenkopfanalyse" ein, und wählen Sie dann **Kopfzeilen analysieren** aus:</span><span class="sxs-lookup"><span data-stu-id="dd211-188">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="dd211-189">**Vorschau der Nachricht anzeigen**: Wählen Sie im angezeigten Flyout-Fenster eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="dd211-189">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="dd211-190">**Quellansicht**: Zeigt die HTML-Version des Nachrichtentextes an, wobei alle Links deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="dd211-190">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="dd211-191">**Textansicht**: Zeigt den Nachrichtentext im Klartext an.</span><span class="sxs-lookup"><span data-stu-id="dd211-191">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="dd211-192">**Nachricht herunterladen**: Wählen Sie im daraufhin angezeigten Flyout-Fenster **Ich verstehe die Risiken beim Herunterladen dieser Nachricht** aus, um eine lokale Kopie der Nachricht im eml-Format zu speichern.</span><span class="sxs-lookup"><span data-stu-id="dd211-192">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="dd211-193">**Aus Quarantäne entfernen**: Nachdem Sie in der angezeigten Warnung auf **Ja** geklickt haben, wird die Nachricht sofort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="dd211-193">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="dd211-194">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="dd211-194">When you're finished, click **Close**.</span></span>

<span data-ttu-id="dd211-195">Wenn Sie die Nachricht nicht freigeben oder entfernen, wird sie nach Ablauf der Standard-Quarantäneaufbewahrungszeit gelöscht.</span><span class="sxs-lookup"><span data-stu-id="dd211-195">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="dd211-196">Maßnahmen für mehrere isolierte E-Mail-Nachrichten ergreifen</span><span class="sxs-lookup"><span data-stu-id="dd211-196">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="dd211-197">Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), erscheint das Flyout-Fenster **Massenaktionen**, in dem Sie die folgenden Aktionen durchführen können:</span><span class="sxs-lookup"><span data-stu-id="dd211-197">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="dd211-198">**Nachrichten freigeben**: Die Optionen sind die gleichen wie bei der Freigabe einer einzelnen Nachricht, außer dass Sie nicht **Nachrichten an bestimmte Empfänger freigeben** auswählen können; Sie können nur **Nachricht an alle Empfänger freigeben** oder **Nachrichten an andere Personen freigeben** auswählen.</span><span class="sxs-lookup"><span data-stu-id="dd211-198">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="dd211-199">**Nachrichten löschen**: Nachdem Sie in der angezeigten Warnung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="dd211-199">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="dd211-200">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="dd211-200">When you're finished, click **Close**.</span></span>

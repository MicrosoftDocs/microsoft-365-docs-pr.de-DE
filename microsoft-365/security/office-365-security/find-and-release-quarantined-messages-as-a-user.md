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
ms.openlocfilehash: 215cbc23aca3b7d10eca8c53d816892d0ca042cb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638106"
---
# <a name="find-and-release-quarantined-messages-as-a-user"></a><span data-ttu-id="19e23-104">Finden und Freigeben von Nachrichten unter Quarantäne als Benutzer</span><span class="sxs-lookup"><span data-stu-id="19e23-104">Find and release quarantined messages as a user</span></span>

<span data-ttu-id="19e23-105">Die Quarantäne enthält potenziell gefährliche oder unerwünschte Nachrichten in Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="19e23-105">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="19e23-106">Weitere Informationen finden Sie unter [Quarantäne in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="19e23-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="19e23-107">Als Benutzer können Sie unter Quarantäne gestellte Nachrichten anzeigen, freigeben und löschen, wenn Sie ein Empfänger sind und die Nachricht als Spam, Massen-E-Mail oder (ab April 2020) als Phishing unter Quarantäne gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="19e23-107">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="19e23-108">Sie können die in Quarantäne befindlichen Nachrichten im Security & Compliance Center oder (wenn ein Administrator dies eingerichtet hat) in [Spambenachrichtigungen für Endbenutzer](use-spam-notifications-to-release-and-report-quarantined-messages.md) anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="19e23-108">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="19e23-109">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="19e23-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="19e23-110">Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="19e23-110">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="19e23-111">Um die Quarantäne-Seite direkt zu öffnen, wechseln Sie zu <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="19e23-111">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="19e23-112">Administratoren können konfigurieren, wie lange Nachrichten isoliert werden, bevor sie endgültig gelöscht werden (Anti-Spam-Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="19e23-112">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="19e23-113">Nachrichten, die aus der Quarantäne abgelaufen sind, können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="19e23-113">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="19e23-114">Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="19e23-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="19e23-115">Administratoren können auch [Spam-Benachrichtigungen für Endbenutzer](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in Anti-Spam-Richtlinien aktivieren.</span><span class="sxs-lookup"><span data-stu-id="19e23-115">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="19e23-116">Benutzer können in Quarantäne gestellte Spamnachrichten, aber nicht in Quarantäne gestellte Phishingnachrichten, direkt aus diesen Benachrichtigungen heraus freigeben.</span><span class="sxs-lookup"><span data-stu-id="19e23-116">Users can release spam quarantined messages but not phish quarantined messages directly from these notifications.</span></span> <span data-ttu-id="19e23-117">Weitere Informationen finden Sie unter [Spam-Benachrichtigungen für Endbenutzer in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="19e23-117">For more information, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="19e23-118">Nachrichten, die wegen hoher Phishingwahrscheinlichkeit, Schadsoftware oder durch Nachrichtenflussregeln (auch als Transportregeln bekannt) unter Quarantäne gestellt wurden, sind nur für Administratoren verfügbar.</span><span class="sxs-lookup"><span data-stu-id="19e23-118">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="19e23-119">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="19e23-119">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="19e23-120">Sie können eine Nachricht nur einmal freigeben und als falsch positiv markiert (keine Junk-E-Mail) melden.</span><span class="sxs-lookup"><span data-stu-id="19e23-120">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="19e23-121">Anzeigen Ihrer isolierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="19e23-121">View your quarantined messages</span></span>

1. <span data-ttu-id="19e23-122">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="19e23-122">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="19e23-123">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="19e23-123">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="19e23-124">Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="19e23-124">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="19e23-125">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="19e23-125">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="19e23-126">**Empfangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19e23-126">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="19e23-127">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19e23-127">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="19e23-128">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19e23-128">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="19e23-129">**Quarantänegrund**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19e23-129">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="19e23-130">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19e23-130">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="19e23-131">**Richtlinientyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19e23-131">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="19e23-132">**Läuft ab**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19e23-132">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="19e23-133">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="19e23-133">**Recipient**</span></span>

   - <span data-ttu-id="19e23-134">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="19e23-134">**Message ID**</span></span>

   - <span data-ttu-id="19e23-135">**Name der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="19e23-135">**Policy name**</span></span>

   - <span data-ttu-id="19e23-136">**Größe**</span><span class="sxs-lookup"><span data-stu-id="19e23-136">**Size**</span></span>

   - <span data-ttu-id="19e23-137">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="19e23-137">**Direction**</span></span>

   <span data-ttu-id="19e23-138">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**, oder klicken Sie auf **Als Standard festlegen**.</span><span class="sxs-lookup"><span data-stu-id="19e23-138">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="19e23-139">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="19e23-139">To filter the results, click **Filter**.</span></span> <span data-ttu-id="19e23-140">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="19e23-140">The available filters are:</span></span>

   - <span data-ttu-id="19e23-141">**Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="19e23-141">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="19e23-142">**Heute**</span><span class="sxs-lookup"><span data-stu-id="19e23-142">**Today**</span></span>

     - <span data-ttu-id="19e23-143">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="19e23-143">**Next 2 days**</span></span>

     - <span data-ttu-id="19e23-144">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="19e23-144">**Next 7 days**</span></span>

     - <span data-ttu-id="19e23-145">**Benutzerdefiniert**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="19e23-145">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="19e23-146">**Empfangszeit**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="19e23-146">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="19e23-147">**Quarantänegrund**:</span><span class="sxs-lookup"><span data-stu-id="19e23-147">**Quarantine reason**:</span></span>

     - <span data-ttu-id="19e23-148">**Massensendung**</span><span class="sxs-lookup"><span data-stu-id="19e23-148">**Bulk**</span></span>

     - <span data-ttu-id="19e23-149">**Spam**</span><span class="sxs-lookup"><span data-stu-id="19e23-149">**Spam**</span></span>

     - <span data-ttu-id="19e23-150">**Phishing** (ab April 2020)</span><span class="sxs-lookup"><span data-stu-id="19e23-150">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="19e23-151">Klicken Sie auf **Löschen**, um den Filter zu löschen.</span><span class="sxs-lookup"><span data-stu-id="19e23-151">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="19e23-152">Um das Filter-Flyout auszublenden, klicken Sie erneut auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="19e23-152">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="19e23-153">Verwenden Sie **Ergebnisse sortieren nach** (standardmäßig die Schaltfläche **Nachrichten-ID**) und einen entsprechenden Wert, um bestimmte Nachrichten zu finden.</span><span class="sxs-lookup"><span data-stu-id="19e23-153">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="19e23-154">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="19e23-154">Wildcards aren't supported.</span></span> <span data-ttu-id="19e23-155">Sie können nach den folgenden Werten suchen:</span><span class="sxs-lookup"><span data-stu-id="19e23-155">You can search by the following values:</span></span>

   - <span data-ttu-id="19e23-156">**Nachrichten-ID**: Die globale eindeutige ID der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="19e23-156">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="19e23-157">Wenn Sie eine Nachricht in der Liste auswählen, wird der Wert **Nachrichten-ID** im Flyout-Fenster **Details** angezeigt, der angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="19e23-157">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="19e23-158">Administratoren können [Nachrichtenverfolgung](message-trace-scc.md) verwenden, um Nachrichten und die entsprechenden Nachrichten-ID-Werte zu suchen.</span><span class="sxs-lookup"><span data-stu-id="19e23-158">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="19e23-159">**E-Mail-Adresse des Absenders**: Die E-Mail-Adresse eines einzelnen Absenders.</span><span class="sxs-lookup"><span data-stu-id="19e23-159">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="19e23-160">**E-Mail-Adresse des Empfängers**: Die E-Mail-Adresse eines einzelnen Empfängers.</span><span class="sxs-lookup"><span data-stu-id="19e23-160">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="19e23-161">**Betreff**: Verwenden Sie den gesamten Betreff der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="19e23-161">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="19e23-162">Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="19e23-162">The search is not case-sensitive.</span></span>

   <span data-ttu-id="19e23-163">Nachdem Sie die Suchkriterien eingegeben haben, klicken Sie auf die ![Schaltfläche Aktualisieren](../../media/scc-quarantine-refresh.png) **Aktualisieren**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="19e23-163">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="19e23-164">Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Maßnahmen zu ergreifen (z. B. die Nachricht anzeigen, freigeben, herunterladen oder löschen).</span><span class="sxs-lookup"><span data-stu-id="19e23-164">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="19e23-165">Nachrichtenergebnisse exportieren</span><span class="sxs-lookup"><span data-stu-id="19e23-165">Export message results</span></span>

1. <span data-ttu-id="19e23-166">Wählen Sie die gewünschten Nachrichten aus, und klicken Sie auf **Ergebnisse exportieren**.</span><span class="sxs-lookup"><span data-stu-id="19e23-166">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="19e23-167">Klicken Sie auf **Ja** in der Bestätigungsnachricht, die Sie warnt, das Browserfenster geöffnet zu lassen.</span><span class="sxs-lookup"><span data-stu-id="19e23-167">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="19e23-168">Wenn Ihr Export fertig ist, können Sie den Speicherort für die .csv-Datei benennen und auswählen.</span><span class="sxs-lookup"><span data-stu-id="19e23-168">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="19e23-169">Anzeigen von Details der isolierten Nachricht</span><span class="sxs-lookup"><span data-stu-id="19e23-169">View quarantined message details</span></span>

<span data-ttu-id="19e23-170">Wenn Sie eine E-Mail-Nachricht in der Liste auswählen, werden die folgenden Nachrichtendetails im Flyout-Fenster **Details** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="19e23-170">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="19e23-171">**Nachrichten-ID**: Die globale eindeutige ID für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="19e23-171">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="19e23-172">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="19e23-172">**Sender address**</span></span>

- <span data-ttu-id="19e23-173">**Empfangen**: Das Datum/die Uhrzeit des Nachrichtenempfangs.</span><span class="sxs-lookup"><span data-stu-id="19e23-173">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="19e23-174">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="19e23-174">**Subject**</span></span>

- <span data-ttu-id="19e23-175">**Quarantänegrund**: Zeigt an, ob eine Nachricht als **Spam**, **Massensendung** oder (ab April 2020) **Phishing** erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="19e23-175">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="19e23-176">**Empfänger**: Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Vorschau der Nachricht anzeigen** oder **Nachrichten** Kopfzeile anzeigen klicken, um die gesamte Liste der Empfänger anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="19e23-176">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="19e23-177">**Läuft ab**. Das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="19e23-177">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="19e23-178">**Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="19e23-178">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="19e23-179">**Noch nicht freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht noch nicht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="19e23-179">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="19e23-180">Maßnahmen für isolierte E-Mails ergreifen</span><span class="sxs-lookup"><span data-stu-id="19e23-180">Take action on quarantined email</span></span>

<span data-ttu-id="19e23-181">Nachdem Sie eine Nachricht ausgewählt haben, haben Sie Optionen, was mit den Nachrichten im Flyout-Fenster **Details** geschehen soll:</span><span class="sxs-lookup"><span data-stu-id="19e23-181">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="19e23-182">**Nachricht freigeben**: Wählen Sie im angezeigten Flyout-Fenster, ob Sie **Meldungen zur Analyse an Microsoft melden** möchten.</span><span class="sxs-lookup"><span data-stu-id="19e23-182">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="19e23-183">Diese ist standardmäßig ausgewählt und meldet die irrtümlich isolierte Nachricht an Microsoft als falsches positives Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="19e23-183">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="19e23-184">Klicken Sie nach Abschluss des Vorgangs auf **Nachrichten freigeben**.</span><span class="sxs-lookup"><span data-stu-id="19e23-184">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="19e23-185">**Nachrichtenkopf anzeigen**: Wählen Sie diesen Link aus, um den Nachrichtenkopftext anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="19e23-185">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="19e23-186">Um den Nachrichtenkopf im Detail zu analysieren, kopieren Sie den Nachrichtenkopftext in die Zwischenablage, und wählen Sie dann **Microsoft-Nachrichtenkopfanalyse** aus, um zur Remoteverbindungsuntersuchung zu wechseln (klicken Sie mit der rechten Maustaste, und wählen Sie **In neuer Registerkarte öffnen** aus, wenn Sie Microsoft 365 nicht verlassen möchten, um die Aufgabe auszuführen).</span><span class="sxs-lookup"><span data-stu-id="19e23-186">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="19e23-187">Fügen Sie den Nachrichtenkopf auf der Seite in den Abschnitt "Nachrichtenkopfanalyse" ein, und wählen Sie dann **Kopfzeilen analysieren** aus:</span><span class="sxs-lookup"><span data-stu-id="19e23-187">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="19e23-188">**Vorschau der Nachricht anzeigen**: Wählen Sie im angezeigten Flyout-Fenster eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="19e23-188">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="19e23-189">**Quellansicht**: Zeigt die HTML-Version des Nachrichtentextes an, wobei alle Links deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="19e23-189">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="19e23-190">**Textansicht**: Zeigt den Nachrichtentext im Klartext an.</span><span class="sxs-lookup"><span data-stu-id="19e23-190">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="19e23-191">**Nachricht herunterladen**: Wählen Sie im daraufhin angezeigten Flyout-Fenster **Ich verstehe die Risiken beim Herunterladen dieser Nachricht** aus, um eine lokale Kopie der Nachricht im eml-Format zu speichern.</span><span class="sxs-lookup"><span data-stu-id="19e23-191">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="19e23-192">**Aus Quarantäne entfernen**: Nachdem Sie in der angezeigten Warnung auf **Ja** geklickt haben, wird die Nachricht sofort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="19e23-192">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="19e23-193">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="19e23-193">When you're finished, click **Close**.</span></span>

<span data-ttu-id="19e23-194">Wenn Sie die Nachricht nicht freigeben oder entfernen, wird sie nach Ablauf der Standard-Quarantäneaufbewahrungszeit gelöscht.</span><span class="sxs-lookup"><span data-stu-id="19e23-194">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="19e23-195">Maßnahmen für mehrere isolierte E-Mail-Nachrichten ergreifen</span><span class="sxs-lookup"><span data-stu-id="19e23-195">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="19e23-196">Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), erscheint das Flyout-Fenster **Massenaktionen**, in dem Sie die folgenden Aktionen durchführen können:</span><span class="sxs-lookup"><span data-stu-id="19e23-196">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="19e23-197">**Nachrichten freigeben**: Die Optionen sind die gleichen wie bei der Freigabe einer einzelnen Nachricht, außer dass Sie nicht **Nachrichten an bestimmte Empfänger freigeben** auswählen können; Sie können nur **Nachricht an alle Empfänger freigeben** oder **Nachrichten an andere Personen freigeben** auswählen.</span><span class="sxs-lookup"><span data-stu-id="19e23-197">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="19e23-198">**Nachrichten löschen**: Nachdem Sie in der angezeigten Warnung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="19e23-198">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="19e23-199">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="19e23-199">When you're finished, click **Close**.</span></span>

---
title: Suchen und Freigeben von isolierten Nachrichten als Benutzer in Office 365
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
description: Als Office 365-Benutzer können Sie Ihre isolierten Nachrichten anzeigen, freigeben und löschen (Nachrichten, bei denen Sie ein Empfänger sind und der Spam-Filter die Nachricht als Spam oder Massen-E-Mail unter Quarantäne gestellt hat). Sie können Ihre isolierten Nachrichten im Security & Compliance Center anzeigen und verwalten.
ms.openlocfilehash: 04f04cfddb123bf176f3c71568789c77d225a601
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893670"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a><span data-ttu-id="9d6c1-104">Suchen und Freigeben von isolierten Nachrichten als Benutzer in Office 365</span><span class="sxs-lookup"><span data-stu-id="9d6c1-104">Find and release quarantined messages as a user in Office 365</span></span>

<span data-ttu-id="9d6c1-105">Die Quarantäne enthält potenziell gefährliche oder unerwünschte Nachrichten in Office 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="9d6c1-106">Weitere Informationen finden Sie unter [Quarantäne in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="9d6c1-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="9d6c1-107">Als Benutzer können Sie unter Quarantäne gestellte Nachrichten anzeigen, freigeben und löschen, wenn Sie ein Empfänger sind und die Nachricht als Spam, Massen-E-Mail oder (ab April 2020) als Phishing unter Quarantäne gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-107">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="9d6c1-108">Sie können Microsoft auch falsch positive Ergebnisse melden.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-108">You can also report false positives to Microsoft.</span></span>

<span data-ttu-id="9d6c1-109">Sie können Ihre isolierten Nachrichten im Security & Compliance Center anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-109">You view and manage your quarantined messages in the Security & Compliance Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9d6c1-110">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="9d6c1-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9d6c1-111">Um das Office 365 Security & Compliance Center zu öffnen wechseln Sie zu <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-111">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="9d6c1-112">Um die Quarantäne-Seite direkt zu öffnen, wechseln Sie zu <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-112">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="9d6c1-113">Administratoren können konfigurieren, wie lange Nachrichten isoliert werden, bevor sie endgültig gelöscht werden (Anti-Spam-Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="9d6c1-113">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="9d6c1-114">Nachrichten, die aus der Quarantäne abgelaufen sind, können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-114">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="9d6c1-115">Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9d6c1-115">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="9d6c1-116">Administratoren können auch [Spam-Benachrichtigungen für Endbenutzer](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in Anti-Spam-Richtlinien aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-116">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="9d6c1-117">Ab Oktober 2019 können Sie ihre isolierten Nachrichten nicht mehr direkt über diese Benachrichtigungen freigeben.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-117">As of October 2019, you can no longer release quarantined messages directly from these notifications.</span></span> <span data-ttu-id="9d6c1-118">Sie können in der Benachrichtigung auf **Überprüfen** klicken, was Sie zur Quarantäne im Security & Compliance Center führt.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-118">You can click **Review** in the notification, which will take you to Quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="9d6c1-119">Weitere Informationen zu Benachrichtigungen finden Sie unter [Spambenachrichtigungen für Endbenutzer in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="9d6c1-119">For more information about the notifications, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="9d6c1-120">Nachrichten, die wegen hoher Phishingwahrscheinlichkeit, Schadsoftware oder durch Nachrichtenflussregeln (auch als Transportregeln bekannt) unter Quarantäne gestellt wurden, sind nur für Administratoren verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-120">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="9d6c1-121">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="9d6c1-121">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="9d6c1-122">Sie können eine Nachricht nur einmal freigeben und als falsch positiv markiert (keine Junk-E-Mail) melden.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-122">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="9d6c1-123">Anzeigen Ihrer isolierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="9d6c1-123">View your quarantined messages</span></span>

1. <span data-ttu-id="9d6c1-124">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-124">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="9d6c1-125">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-125">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="9d6c1-126">Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-126">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="9d6c1-127">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="9d6c1-127">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="9d6c1-128">**Empfangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9d6c1-128">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="9d6c1-129">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9d6c1-129">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="9d6c1-130">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9d6c1-130">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="9d6c1-131">**Quarantänegrund**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9d6c1-131">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="9d6c1-132">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9d6c1-132">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="9d6c1-133">**Richtlinientyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9d6c1-133">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="9d6c1-134">**Läuft ab**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9d6c1-134">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="9d6c1-135">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-135">**Recipient**</span></span>

   - <span data-ttu-id="9d6c1-136">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-136">**Message ID**</span></span>

   - <span data-ttu-id="9d6c1-137">**Name der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-137">**Policy name**</span></span>

   - <span data-ttu-id="9d6c1-138">**Größe**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-138">**Size**</span></span>

   - <span data-ttu-id="9d6c1-139">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-139">**Direction**</span></span>

   <span data-ttu-id="9d6c1-140">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**, oder klicken Sie auf **Als Standard festlegen**.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-140">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="9d6c1-141">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-141">To filter the results, click **Filter**.</span></span> <span data-ttu-id="9d6c1-142">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="9d6c1-142">The available filters are:</span></span>

   - <span data-ttu-id="9d6c1-143">**Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="9d6c1-143">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="9d6c1-144">**Heute**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-144">**Today**</span></span>

     - <span data-ttu-id="9d6c1-145">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-145">**Next 2 days**</span></span>

     - <span data-ttu-id="9d6c1-146">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-146">**Next 7 days**</span></span>

     - <span data-ttu-id="9d6c1-147">**Benutzerdefiniert**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-147">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="9d6c1-148">**Empfangszeit**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-148">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="9d6c1-149">**Quarantänegrund**:</span><span class="sxs-lookup"><span data-stu-id="9d6c1-149">**Quarantine reason**:</span></span>

     - <span data-ttu-id="9d6c1-150">**Massensendung**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-150">**Bulk**</span></span>

     - <span data-ttu-id="9d6c1-151">**Spam**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-151">**Spam**</span></span>

     - <span data-ttu-id="9d6c1-152">**Phishing** (ab April 2020)</span><span class="sxs-lookup"><span data-stu-id="9d6c1-152">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="9d6c1-153">Klicken Sie auf **Löschen**, um den Filter zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-153">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="9d6c1-154">Um das Filter-Flyout auszublenden, klicken Sie erneut auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-154">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="9d6c1-155">Verwenden Sie **Ergebnisse sortieren nach** (standardmäßig die Schaltfläche **Nachrichten-ID**) und einen entsprechenden Wert, um bestimmte Nachrichten zu finden.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-155">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="9d6c1-156">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-156">Wildcards aren't supported.</span></span> <span data-ttu-id="9d6c1-157">Sie können nach den folgenden Werten suchen:</span><span class="sxs-lookup"><span data-stu-id="9d6c1-157">You can search by the following values:</span></span>

   - <span data-ttu-id="9d6c1-158">**Nachrichten-ID**: Die globale eindeutige ID der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-158">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="9d6c1-159">Wenn Sie eine Nachricht in der Liste auswählen, wird der Wert **Nachrichten-ID** im Flyout-Fenster **Details** angezeigt, der angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-159">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="9d6c1-160">Administratoren können [Nachrichtenverfolgung](message-trace-scc.md) verwenden, um Nachrichten und die entsprechenden Nachrichten-ID-Werte zu suchen.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-160">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="9d6c1-161">**E-Mail-Adresse des Absenders**: Die E-Mail-Adresse eines einzelnen Absenders.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-161">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="9d6c1-162">**E-Mail-Adresse des Empfängers**: Die E-Mail-Adresse eines einzelnen Empfängers.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-162">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="9d6c1-163">**Betreff**: Verwenden Sie den gesamten Betreff der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-163">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="9d6c1-164">Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-164">The search is not case-sensitive.</span></span>

   <span data-ttu-id="9d6c1-165">Nachdem Sie die Suchkriterien eingegeben haben, klicken Sie auf die ![Schaltfläche Aktualisieren](../media/scc-quarantine-refresh.png) **Aktualisieren**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-165">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="9d6c1-166">Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Maßnahmen zu ergreifen (z. B. die Nachricht anzeigen, freigeben, herunterladen oder löschen).</span><span class="sxs-lookup"><span data-stu-id="9d6c1-166">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="9d6c1-167">Nachrichtenergebnisse exportieren</span><span class="sxs-lookup"><span data-stu-id="9d6c1-167">Export message results</span></span>

1. <span data-ttu-id="9d6c1-168">Wählen Sie die gewünschten Nachrichten aus, und klicken Sie auf **Ergebnisse exportieren**.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-168">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="9d6c1-169">Klicken Sie auf **Ja** in der Bestätigungsnachricht, die Sie warnt, das Browserfenster geöffnet zu lassen.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-169">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="9d6c1-170">Wenn Ihr Export fertig ist, können Sie den Speicherort für die .csv-Datei benennen und auswählen.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-170">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="9d6c1-171">Anzeigen von Details der isolierten Nachricht</span><span class="sxs-lookup"><span data-stu-id="9d6c1-171">View quarantined message details</span></span>

<span data-ttu-id="9d6c1-172">Wenn Sie eine E-Mail-Nachricht in der Liste auswählen, werden die folgenden Nachrichtendetails im Flyout-Fenster **Details** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9d6c1-172">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="9d6c1-173">**Nachrichten-ID**: Die globale eindeutige ID für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-173">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="9d6c1-174">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-174">**Sender address**</span></span>

- <span data-ttu-id="9d6c1-175">**Empfangen**: Das Datum/die Uhrzeit des Nachrichtenempfangs.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-175">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="9d6c1-176">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-176">**Subject**</span></span>

- <span data-ttu-id="9d6c1-177">**Quarantänegrund**: Zeigt an, ob eine Nachricht als **Spam**, **Massensendung** oder (ab April 2020) **Phishing** erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-177">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="9d6c1-178">**Empfänger**: Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Vorschau der Nachricht anzeigen** oder **Nachrichten** Kopfzeile anzeigen klicken, um die gesamte Liste der Empfänger anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-178">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="9d6c1-179">**Läuft ab**. Das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-179">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="9d6c1-180">**Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-180">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="9d6c1-181">**Noch nicht freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht noch nicht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-181">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="9d6c1-182">Maßnahmen für isolierte E-Mails ergreifen</span><span class="sxs-lookup"><span data-stu-id="9d6c1-182">Take action on quarantined email</span></span>

<span data-ttu-id="9d6c1-183">Nachdem Sie eine Nachricht ausgewählt haben, haben Sie Optionen, was mit den Nachrichten im Flyout-Fenster **Details** geschehen soll:</span><span class="sxs-lookup"><span data-stu-id="9d6c1-183">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="9d6c1-184">**Nachricht freigeben**: Wählen Sie im angezeigten Flyout-Fenster, ob Sie **Meldungen zur Analyse an Microsoft melden** möchten.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-184">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="9d6c1-185">Diese ist standardmäßig ausgewählt und meldet die irrtümlich isolierte Nachricht an Microsoft als falsches positives Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-185">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="9d6c1-186">Klicken Sie nach Abschluss des Vorgangs auf **Nachrichten freigeben**.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-186">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="9d6c1-187">**Nachrichtenkopf anzeigen**: Wählen Sie diesen Link aus, um den Nachrichtenkopftext anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-187">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="9d6c1-188">Um den Nachrichtenkopf im Detail zu analysieren, kopieren Sie den Nachrichtenkopftext in die Zwischenablage, und wählen Sie dann **Microsoft-Nachrichtenkopfanalyse** aus, um zur Remoteverbindungsuntersuchung zu wechseln (klicken Sie mit der rechten Maustaste, und wählen Sie **In neuer Registerkarte öffnen** aus, wenn Sie Office 365 nicht verlassen möchten, um die Aufgabe auszuführen).</span><span class="sxs-lookup"><span data-stu-id="9d6c1-188">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="9d6c1-189">Fügen Sie den Nachrichtenkopf auf der Seite in den Abschnitt "Nachrichtenkopfanalyse" ein, und wählen Sie dann **Kopfzeilen analysieren** aus:</span><span class="sxs-lookup"><span data-stu-id="9d6c1-189">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="9d6c1-190">**Vorschau der Nachricht anzeigen**: Wählen Sie im angezeigten Flyout-Fenster eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="9d6c1-190">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="9d6c1-191">**Quellansicht**: Zeigt die HTML-Version des Nachrichtentextes an, wobei alle Links deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-191">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="9d6c1-192">**Textansicht**: Zeigt den Nachrichtentext im Klartext an.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-192">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="9d6c1-193">**Nachricht herunterladen**: Wählen Sie im daraufhin angezeigten Flyout-Fenster **Ich verstehe die Risiken beim Herunterladen dieser Nachricht** aus, um eine lokale Kopie der Nachricht im eml-Format zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-193">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="9d6c1-194">**Aus Quarantäne entfernen**: Nachdem Sie in der angezeigten Warnung auf **Ja** geklickt haben, wird die Nachricht sofort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-194">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="9d6c1-195">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-195">When you're finished, click **Close**.</span></span>

<span data-ttu-id="9d6c1-196">Wenn Sie die Nachricht nicht freigeben oder entfernen, wird sie nach Ablauf der Standard-Quarantäneaufbewahrungszeit gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-196">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="9d6c1-197">Maßnahmen für mehrere isolierte E-Mail-Nachrichten ergreifen</span><span class="sxs-lookup"><span data-stu-id="9d6c1-197">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="9d6c1-198">Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), erscheint das Flyout-Fenster **Massenaktionen**, in dem Sie die folgenden Aktionen durchführen können:</span><span class="sxs-lookup"><span data-stu-id="9d6c1-198">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="9d6c1-199">**Nachrichten freigeben**: Die Optionen sind die gleichen wie bei der Freigabe einer einzelnen Nachricht, außer dass Sie nicht **Nachrichten an bestimmte Empfänger freigeben** auswählen können; Sie können nur **Nachricht an alle Empfänger freigeben** oder **Nachrichten an andere Personen freigeben** auswählen.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-199">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="9d6c1-200">**Nachrichten löschen**: Nachdem Sie in der angezeigten Warnung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-200">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="9d6c1-201">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-201">When you're finished, click **Close**.</span></span>

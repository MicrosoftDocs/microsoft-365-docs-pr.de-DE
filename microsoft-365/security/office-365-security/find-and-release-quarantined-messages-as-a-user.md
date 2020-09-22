---
title: Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Benutzer können erfahren, wie sie in Exchange Online Protection (EOP) isolierte (unter Quarantäne gestellte) Nachrichten anzeigen und verwalten, die sie hätten empfangen sollen.
ms.openlocfilehash: 03bcb0518b75d9a35aae1b6664b410b521adf940
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202843"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="222b4-103">Suchen und Freigeben von isolierten Nachrichten als Benutzer in EOP</span><span class="sxs-lookup"><span data-stu-id="222b4-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="222b4-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="222b4-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="222b4-105">Weitere Informationen finden Sie unter [Quarantäne in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="222b4-105">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="222b4-106">Als Benutzer können Sie unter Quarantäne gestellte Nachrichten anzeigen, freigeben und löschen, wenn Sie ein Empfänger sind und die Nachricht als Spam oder Massen-E-Mail unter Quarantäne gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="222b4-106">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam or bulk email.</span></span> <span data-ttu-id="222b4-107">Seit April 2020 können Sie unter Quarantäne gestellte Phishing-Nachrichten (nicht mit hoher Phishingwahrscheinlichkeit), für die Sie als Empfänger gelten, anzeigen oder löschen.</span><span class="sxs-lookup"><span data-stu-id="222b4-107">As of April 2020, you can view or delete quarantined phishing (not high confidence phishing) messages where you are a recipient.</span></span> <span data-ttu-id="222b4-108">Sie können die in Quarantäne befindlichen Nachrichten im Security & Compliance Center oder (wenn ein Administrator dies eingerichtet hat) in [Spambenachrichtigungen für Endbenutzer](use-spam-notifications-to-release-and-report-quarantined-messages.md) anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="222b4-108">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="222b4-109">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="222b4-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="222b4-110">Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="222b4-110">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="222b4-111">Um die Quarantäne-Seite direkt zu öffnen, wechseln Sie zu <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="222b4-111">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="222b4-112">Administratoren können konfigurieren, wie lange Nachrichten isoliert werden, bevor sie endgültig gelöscht werden (Anti-Spam-Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="222b4-112">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="222b4-113">Nachrichten, die aus der Quarantäne abgelaufen sind, können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="222b4-113">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="222b4-114">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="222b4-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="222b4-115">Administratoren können auch [Spam-Benachrichtigungen für Endbenutzer](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in Anti-Spam-Richtlinien aktivieren.</span><span class="sxs-lookup"><span data-stu-id="222b4-115">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="222b4-116">Benutzende können in Quarantäne befindliche Spamnachrichten direkt über diese Benachrichtigungen freigeben.</span><span class="sxs-lookup"><span data-stu-id="222b4-116">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="222b4-117">Benutzende können die in Quarantäne befindlichen Phishing-Nachrichten (keine Phishing-Nachrichten mit hohem Sicherheitsrisiko) direkt aus diesen Benachrichtigungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="222b4-117">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="222b4-118">Weitere Informationen finden Sie unter [Spam-Benachrichtigungen für Endbenutzer in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="222b4-118">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="222b4-119">Nachrichten, die wegen Phishing mit hohem Sicherheitsrisiko, Malware oder durch Mail-Flow-Regeln (auch als Transportregeln bekannt) unter Quarantäne gestellt wurden, sind nur für Admins verfügbar und für Benutzende nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="222b4-119">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="222b4-120">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="222b4-120">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="222b4-121">Sie können eine Nachricht nur einmal freigeben und als falsch positiv markiert (keine Junk-E-Mail) melden.</span><span class="sxs-lookup"><span data-stu-id="222b4-121">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="222b4-122">Anzeigen Ihrer isolierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="222b4-122">View your quarantined messages</span></span>

1. <span data-ttu-id="222b4-123">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="222b4-123">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="222b4-124">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="222b4-124">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="222b4-125">Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="222b4-125">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="222b4-126">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="222b4-126">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="222b4-127">**Empfangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="222b4-127">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="222b4-128">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="222b4-128">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="222b4-129">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="222b4-129">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="222b4-130">**Quarantänegrund**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="222b4-130">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="222b4-131">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="222b4-131">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="222b4-132">**Richtlinientyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="222b4-132">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="222b4-133">**Läuft ab**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="222b4-133">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="222b4-134">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="222b4-134">**Recipient**</span></span>

   - <span data-ttu-id="222b4-135">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="222b4-135">**Message ID**</span></span>

   - <span data-ttu-id="222b4-136">**Name der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="222b4-136">**Policy name**</span></span>

   - <span data-ttu-id="222b4-137">**Größe**</span><span class="sxs-lookup"><span data-stu-id="222b4-137">**Size**</span></span>

   - <span data-ttu-id="222b4-138">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="222b4-138">**Direction**</span></span>

   <span data-ttu-id="222b4-139">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**, oder klicken Sie auf **Als Standard festlegen**.</span><span class="sxs-lookup"><span data-stu-id="222b4-139">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="222b4-140">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="222b4-140">To filter the results, click **Filter**.</span></span> <span data-ttu-id="222b4-141">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="222b4-141">The available filters are:</span></span>

   - <span data-ttu-id="222b4-142">**Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="222b4-142">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="222b4-143">**Heute**</span><span class="sxs-lookup"><span data-stu-id="222b4-143">**Today**</span></span>

     - <span data-ttu-id="222b4-144">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="222b4-144">**Next 2 days**</span></span>

     - <span data-ttu-id="222b4-145">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="222b4-145">**Next 7 days**</span></span>

     - <span data-ttu-id="222b4-146">**Benutzerdefiniert**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="222b4-146">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="222b4-147">**Empfangszeit**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="222b4-147">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="222b4-148">**Quarantänegrund**:</span><span class="sxs-lookup"><span data-stu-id="222b4-148">**Quarantine reason**:</span></span>

     - <span data-ttu-id="222b4-149">**Massensendung**</span><span class="sxs-lookup"><span data-stu-id="222b4-149">**Bulk**</span></span>

     - <span data-ttu-id="222b4-150">**Spam**</span><span class="sxs-lookup"><span data-stu-id="222b4-150">**Spam**</span></span>

     - <span data-ttu-id="222b4-151">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="222b4-151">**Phish**</span></span>

   <span data-ttu-id="222b4-152">Klicken Sie auf **Löschen**, um den Filter zu löschen.</span><span class="sxs-lookup"><span data-stu-id="222b4-152">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="222b4-153">Um das Filter-Flyout auszublenden, klicken Sie erneut auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="222b4-153">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="222b4-154">Verwenden Sie **Ergebnisse sortieren nach** (standardmäßig die Schaltfläche **Nachrichten-ID**) und einen entsprechenden Wert, um bestimmte Nachrichten zu finden.</span><span class="sxs-lookup"><span data-stu-id="222b4-154">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="222b4-155">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="222b4-155">Wildcards aren't supported.</span></span> <span data-ttu-id="222b4-156">Sie können nach den folgenden Werten suchen:</span><span class="sxs-lookup"><span data-stu-id="222b4-156">You can search by the following values:</span></span>

   - <span data-ttu-id="222b4-157">**Nachrichten-ID**: Die globale eindeutige ID der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="222b4-157">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="222b4-158">Wenn Sie eine Nachricht in der Liste auswählen, wird der Wert **Nachrichten-ID** im Flyout-Fenster **Details** angezeigt, der angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="222b4-158">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="222b4-159">Administratoren können [Nachrichtenverfolgung](message-trace-scc.md) verwenden, um Nachrichten und die entsprechenden Nachrichten-ID-Werte zu suchen.</span><span class="sxs-lookup"><span data-stu-id="222b4-159">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="222b4-160">**E-Mail-Adresse des Absenders**: Die E-Mail-Adresse eines einzelnen Absenders.</span><span class="sxs-lookup"><span data-stu-id="222b4-160">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="222b4-161">**E-Mail-Adresse des Empfängers**: Die E-Mail-Adresse eines einzelnen Empfängers.</span><span class="sxs-lookup"><span data-stu-id="222b4-161">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="222b4-162">**Betreff**: Verwenden Sie den gesamten Betreff der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="222b4-162">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="222b4-163">Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="222b4-163">The search is not case-sensitive.</span></span>

   <span data-ttu-id="222b4-164">Nachdem Sie die Suchkriterien eingegeben haben, klicken Sie auf die ![Schaltfläche Aktualisieren](../../media/scc-quarantine-refresh.png) **Aktualisieren**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="222b4-164">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="222b4-165">Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Maßnahmen zu ergreifen (z. B. die Nachricht anzeigen, freigeben, herunterladen oder löschen).</span><span class="sxs-lookup"><span data-stu-id="222b4-165">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="222b4-166">Nachrichtenergebnisse exportieren</span><span class="sxs-lookup"><span data-stu-id="222b4-166">Export message results</span></span>

1. <span data-ttu-id="222b4-167">Wählen Sie die gewünschten Nachrichten aus, und klicken Sie auf **Ergebnisse exportieren**.</span><span class="sxs-lookup"><span data-stu-id="222b4-167">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="222b4-168">Klicken Sie auf **Ja** in der Bestätigungsnachricht, die Sie warnt, das Browserfenster geöffnet zu lassen.</span><span class="sxs-lookup"><span data-stu-id="222b4-168">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="222b4-169">Wenn Ihr Export fertig ist, können Sie den Speicherort für die .csv-Datei benennen und auswählen.</span><span class="sxs-lookup"><span data-stu-id="222b4-169">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="222b4-170">Anzeigen von Details der isolierten Nachricht</span><span class="sxs-lookup"><span data-stu-id="222b4-170">View quarantined message details</span></span>

<span data-ttu-id="222b4-171">Wenn Sie eine E-Mail-Nachricht in der Liste auswählen, werden die folgenden Nachrichtendetails im Flyout-Fenster **Details** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="222b4-171">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="222b4-172">**Nachrichten-ID**: Die globale eindeutige ID für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="222b4-172">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="222b4-173">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="222b4-173">**Sender address**</span></span>

- <span data-ttu-id="222b4-174">**Empfangen**: Das Datum/die Uhrzeit des Nachrichtenempfangs.</span><span class="sxs-lookup"><span data-stu-id="222b4-174">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="222b4-175">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="222b4-175">**Subject**</span></span>

- <span data-ttu-id="222b4-176">**Quarantänegrund**: Zeigt an, ob eine Nachricht als **Spam**, **Massensendung** oder **Phishing** erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="222b4-176">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>

- <span data-ttu-id="222b4-177">**Empfänger**: Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Vorschau der Nachricht anzeigen** oder **Nachrichten** Kopfzeile anzeigen klicken, um die gesamte Liste der Empfänger anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="222b4-177">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="222b4-178">**Läuft ab**. Das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="222b4-178">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="222b4-179">**Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="222b4-179">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="222b4-180">**Noch nicht freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht noch nicht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="222b4-180">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="222b4-181">Maßnahmen für isolierte E-Mails ergreifen</span><span class="sxs-lookup"><span data-stu-id="222b4-181">Take action on quarantined email</span></span>

<span data-ttu-id="222b4-182">Nachdem Sie eine Nachricht ausgewählt haben, haben Sie Optionen, was mit den Nachrichten im Flyout-Fenster **Details** geschehen soll:</span><span class="sxs-lookup"><span data-stu-id="222b4-182">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="222b4-183">**Nachricht freigeben**: Wählen Sie im angezeigten Flyout-Fenster, ob Sie **Meldungen zur Analyse an Microsoft melden** möchten.</span><span class="sxs-lookup"><span data-stu-id="222b4-183">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="222b4-184">Diese ist standardmäßig ausgewählt und meldet die irrtümlich isolierte Nachricht an Microsoft als falsches positives Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="222b4-184">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="222b4-185">Klicken Sie nach Abschluss des Vorgangs auf **Nachrichten freigeben**.</span><span class="sxs-lookup"><span data-stu-id="222b4-185">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="222b4-186">**Nachrichtenkopf anzeigen**: Wählen Sie diesen Link aus, um den Nachrichtenkopftext anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="222b4-186">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="222b4-187">Um den Nachrichtenkopf im Detail zu analysieren, kopieren Sie den Nachrichtenkopftext in die Zwischenablage, und wählen Sie dann **Microsoft-Nachrichtenkopfanalyse** aus, um zur Remoteverbindungsuntersuchung zu wechseln (klicken Sie mit der rechten Maustaste, und wählen Sie **In neuer Registerkarte öffnen** aus, wenn Sie Microsoft 365 nicht verlassen möchten, um die Aufgabe auszuführen).</span><span class="sxs-lookup"><span data-stu-id="222b4-187">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="222b4-188">Fügen Sie den Nachrichtenkopf auf der Seite in den Abschnitt "Nachrichtenkopfanalyse" ein, und wählen Sie dann **Kopfzeilen analysieren** aus:</span><span class="sxs-lookup"><span data-stu-id="222b4-188">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="222b4-189">**Vorschau der Nachricht anzeigen**: Wählen Sie im angezeigten Flyout-Fenster eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="222b4-189">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="222b4-190">**Quellansicht**: Zeigt die HTML-Version des Nachrichtentextes an, wobei alle Links deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="222b4-190">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="222b4-191">**Textansicht**: Zeigt den Nachrichtentext im Klartext an.</span><span class="sxs-lookup"><span data-stu-id="222b4-191">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="222b4-192">**Nachricht herunterladen**: Wählen Sie im daraufhin angezeigten Flyout-Fenster **Ich verstehe die Risiken beim Herunterladen dieser Nachricht** aus, um eine lokale Kopie der Nachricht im eml-Format zu speichern.</span><span class="sxs-lookup"><span data-stu-id="222b4-192">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="222b4-193">**Aus Quarantäne entfernen**: Nachdem Sie in der angezeigten Warnung auf **Ja** geklickt haben, wird die Nachricht sofort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="222b4-193">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="222b4-194">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="222b4-194">When you're finished, click **Close**.</span></span>

<span data-ttu-id="222b4-195">Wenn Sie die Nachricht nicht freigeben oder entfernen, wird sie nach Ablauf der Standard-Quarantäneaufbewahrungszeit gelöscht.</span><span class="sxs-lookup"><span data-stu-id="222b4-195">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="222b4-196">Maßnahmen für mehrere isolierte E-Mail-Nachrichten ergreifen</span><span class="sxs-lookup"><span data-stu-id="222b4-196">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="222b4-197">Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), erscheint das Flyout-Fenster **Massenaktionen**, in dem Sie die folgenden Aktionen durchführen können:</span><span class="sxs-lookup"><span data-stu-id="222b4-197">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="222b4-198">**Nachrichten freigeben**: Die Optionen sind die gleichen wie bei der Freigabe einer einzelnen Nachricht, außer dass Sie nicht **Nachrichten an bestimmte Empfänger freigeben** auswählen können; Sie können nur **Nachricht an alle Empfänger freigeben** oder **Nachrichten an andere Personen freigeben** auswählen.</span><span class="sxs-lookup"><span data-stu-id="222b4-198">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="222b4-199">**Nachrichten löschen**: Nachdem Sie in der angezeigten Warnung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="222b4-199">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="222b4-200">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="222b4-200">When you're finished, click **Close**.</span></span>

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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 036aa164b8b77efd2365d56c07d26870eac243f5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274448"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="84e64-103">Suchen und Freigeben von isolierten Nachrichten als Benutzer in EOP</span><span class="sxs-lookup"><span data-stu-id="84e64-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="84e64-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="84e64-104">**Applies to**</span></span>
- [<span data-ttu-id="84e64-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="84e64-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="84e64-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="84e64-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="84e64-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84e64-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="84e64-108">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="84e64-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="84e64-109">Weitere Informationen finden Sie unter [Quarantäne in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="84e64-109">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="84e64-110">Als Benutzer können Sie unter Quarantäne gestellte Nachrichten anzeigen, freigeben und löschen, wenn Sie ein Empfänger sind und die Nachricht als Spam oder Massen-E-Mail unter Quarantäne gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="84e64-110">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam or bulk email.</span></span> <span data-ttu-id="84e64-111">Seit April 2020 können Sie unter Quarantäne gestellte Phishing-Nachrichten (nicht mit hoher Phishingwahrscheinlichkeit), für die Sie als Empfänger gelten, anzeigen oder löschen.</span><span class="sxs-lookup"><span data-stu-id="84e64-111">As of April 2020, you can view or delete quarantined phishing (not high confidence phishing) messages where you are a recipient.</span></span> <span data-ttu-id="84e64-112">Sie können die in Quarantäne befindlichen Nachrichten im Security & Compliance Center oder (wenn ein Administrator dies eingerichtet hat) in [Spambenachrichtigungen für Endbenutzer](use-spam-notifications-to-release-and-report-quarantined-messages.md) anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="84e64-112">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="84e64-113">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="84e64-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="84e64-114">Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="84e64-114">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="84e64-115">Um die Quarantäne-Seite direkt zu öffnen, wechseln Sie zu <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="84e64-115">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="84e64-116">Administratoren können konfigurieren, wie lange Nachrichten isoliert werden, bevor sie endgültig gelöscht werden (Anti-Spam-Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="84e64-116">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="84e64-117">Nachrichten, die aus der Quarantäne abgelaufen sind, können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="84e64-117">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="84e64-118">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="84e64-118">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="84e64-119">Administratoren können auch [Spam-Benachrichtigungen für Endbenutzer](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in Anti-Spam-Richtlinien aktivieren.</span><span class="sxs-lookup"><span data-stu-id="84e64-119">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="84e64-120">Benutzende können in Quarantäne befindliche Spamnachrichten direkt über diese Benachrichtigungen freigeben.</span><span class="sxs-lookup"><span data-stu-id="84e64-120">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="84e64-121">Benutzende können die in Quarantäne befindlichen Phishing-Nachrichten (keine Phishing-Nachrichten mit hohem Sicherheitsrisiko) direkt aus diesen Benachrichtigungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="84e64-121">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="84e64-122">Weitere Informationen finden Sie unter [Spam-Benachrichtigungen für Endbenutzer in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="84e64-122">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="84e64-123">Nachrichten, die wegen Phishing mit hohem Sicherheitsrisiko, Malware oder durch Mail-Flow-Regeln (auch als Transportregeln bekannt) unter Quarantäne gestellt wurden, sind nur für Admins verfügbar und für Benutzende nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="84e64-123">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="84e64-124">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="84e64-124">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="84e64-125">Sie können eine Nachricht nur einmal freigeben und als falsch positiv markiert (keine Junk-E-Mail) melden.</span><span class="sxs-lookup"><span data-stu-id="84e64-125">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="84e64-126">Anzeigen Ihrer isolierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="84e64-126">View your quarantined messages</span></span>

1. <span data-ttu-id="84e64-127">Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.</span><span class="sxs-lookup"><span data-stu-id="84e64-127">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="84e64-128">Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="84e64-128">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="84e64-129">Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="84e64-129">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="84e64-130">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="84e64-130">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="84e64-131">**Empfangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84e64-131">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="84e64-132">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84e64-132">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="84e64-133">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84e64-133">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="84e64-134">**Quarantänegrund**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84e64-134">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="84e64-135">**Veröffentlicht?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84e64-135">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="84e64-136">**Richtlinientyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84e64-136">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="84e64-137">**Läuft ab**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84e64-137">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="84e64-138">**Empfänger**</span><span class="sxs-lookup"><span data-stu-id="84e64-138">**Recipient**</span></span>
   - <span data-ttu-id="84e64-139">**Nachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="84e64-139">**Message ID**</span></span>
   - <span data-ttu-id="84e64-140">**Name der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="84e64-140">**Policy name**</span></span>
   - <span data-ttu-id="84e64-141">**Größe**</span><span class="sxs-lookup"><span data-stu-id="84e64-141">**Size**</span></span>
   - <span data-ttu-id="84e64-142">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="84e64-142">**Direction**</span></span>

   <span data-ttu-id="84e64-143">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**, oder klicken Sie auf **Als Standard festlegen**.</span><span class="sxs-lookup"><span data-stu-id="84e64-143">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="84e64-144">Klicken Sie auf **Filter**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="84e64-144">To filter the results, click **Filter**.</span></span> <span data-ttu-id="84e64-145">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="84e64-145">The available filters are:</span></span>

   - <span data-ttu-id="84e64-146">**Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:</span><span class="sxs-lookup"><span data-stu-id="84e64-146">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="84e64-147">**Heute**</span><span class="sxs-lookup"><span data-stu-id="84e64-147">**Today**</span></span>
     - <span data-ttu-id="84e64-148">**Nächste 2 Tage**</span><span class="sxs-lookup"><span data-stu-id="84e64-148">**Next 2 days**</span></span>
     - <span data-ttu-id="84e64-149">**Nächste 7 Tage**</span><span class="sxs-lookup"><span data-stu-id="84e64-149">**Next 7 days**</span></span>
     - <span data-ttu-id="84e64-150">**Benutzerdefiniert**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="84e64-150">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="84e64-151">**Empfangszeit**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="84e64-151">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="84e64-152">**Quarantänegrund**:</span><span class="sxs-lookup"><span data-stu-id="84e64-152">**Quarantine reason**:</span></span>
     - <span data-ttu-id="84e64-153">**Massensendung**</span><span class="sxs-lookup"><span data-stu-id="84e64-153">**Bulk**</span></span>
     - <span data-ttu-id="84e64-154">**Spam**</span><span class="sxs-lookup"><span data-stu-id="84e64-154">**Spam**</span></span>
     - <span data-ttu-id="84e64-155">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="84e64-155">**Phish**</span></span>

   - <span data-ttu-id="84e64-156">**Richtlinientyp**: Filtern von Nachrichten nach Richtlinientyp:</span><span class="sxs-lookup"><span data-stu-id="84e64-156">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="84e64-157">**Antiphishing-Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="84e64-157">**Anti-phish policy**</span></span>
     - <span data-ttu-id="84e64-158">**Richtlinie für gehostete Inhaltsfilter** (Antispamrichtlinie)</span><span class="sxs-lookup"><span data-stu-id="84e64-158">**Hosted content filter policy** (anti-spam policy)</span></span>

   <span data-ttu-id="84e64-159">Klicken Sie auf **Löschen**, um den Filter zu löschen.</span><span class="sxs-lookup"><span data-stu-id="84e64-159">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="84e64-160">Um das Filter-Flyout auszublenden, klicken Sie erneut auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="84e64-160">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="84e64-161">Verwenden Sie **Ergebnisse sortieren nach** (standardmäßig die Schaltfläche **Nachrichten-ID**) und einen entsprechenden Wert, um bestimmte Nachrichten zu finden.</span><span class="sxs-lookup"><span data-stu-id="84e64-161">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="84e64-162">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="84e64-162">Wildcards aren't supported.</span></span> <span data-ttu-id="84e64-163">Sie können nach den folgenden Werten suchen:</span><span class="sxs-lookup"><span data-stu-id="84e64-163">You can search by the following values:</span></span>

   - <span data-ttu-id="84e64-164">**Nachrichten-ID**: Die globale eindeutige ID der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="84e64-164">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="84e64-165">Wenn Sie eine Nachricht in der Liste auswählen, wird der Wert **Nachrichten-ID** im Flyout-Fenster **Details** angezeigt, der angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="84e64-165">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="84e64-166">Administratoren können [Nachrichtenverfolgung](message-trace-scc.md) verwenden, um Nachrichten und die entsprechenden Nachrichten-ID-Werte zu suchen.</span><span class="sxs-lookup"><span data-stu-id="84e64-166">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="84e64-167">**E-Mail-Adresse des Absenders**: Die E-Mail-Adresse eines einzelnen Absenders.</span><span class="sxs-lookup"><span data-stu-id="84e64-167">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="84e64-168">**Richtlinienname**: Verwenden Sie den vollständigen Namen der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="84e64-168">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="84e64-169">Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="84e64-169">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="84e64-170">**E-Mail-Adresse des Empfängers**: Die E-Mail-Adresse eines einzelnen Empfängers.</span><span class="sxs-lookup"><span data-stu-id="84e64-170">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="84e64-171">**Betreff**: Verwenden Sie den gesamten Betreff der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="84e64-171">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="84e64-172">Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="84e64-172">The search is not case-sensitive.</span></span>

   <span data-ttu-id="84e64-173">Nachdem Sie die Suchkriterien eingegeben haben, klicken Sie auf die ![Schaltfläche Aktualisieren](../../media/scc-quarantine-refresh.png) **Aktualisieren**, um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="84e64-173">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="84e64-174">Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Maßnahmen zu ergreifen (z. B. die Nachricht anzeigen, freigeben, herunterladen oder löschen).</span><span class="sxs-lookup"><span data-stu-id="84e64-174">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="84e64-175">Nachrichtenergebnisse exportieren</span><span class="sxs-lookup"><span data-stu-id="84e64-175">Export message results</span></span>

1. <span data-ttu-id="84e64-176">Wählen Sie die gewünschten Nachrichten aus, und klicken Sie auf **Ergebnisse exportieren**.</span><span class="sxs-lookup"><span data-stu-id="84e64-176">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="84e64-177">Klicken Sie auf **Ja** in der Bestätigungsnachricht, die Sie warnt, das Browserfenster geöffnet zu lassen.</span><span class="sxs-lookup"><span data-stu-id="84e64-177">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="84e64-178">Wenn Ihr Export fertig ist, können Sie den Speicherort für die .csv-Datei benennen und auswählen.</span><span class="sxs-lookup"><span data-stu-id="84e64-178">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="84e64-179">Anzeigen von Details der isolierten Nachricht</span><span class="sxs-lookup"><span data-stu-id="84e64-179">View quarantined message details</span></span>

<span data-ttu-id="84e64-180">Wenn Sie eine E-Mail-Nachricht in der Liste auswählen, werden die folgenden Nachrichtendetails im Flyout-Fenster **Details** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="84e64-180">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="84e64-181">**Nachrichten-ID**: Die globale eindeutige ID für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="84e64-181">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="84e64-182">**Absenderadresse**</span><span class="sxs-lookup"><span data-stu-id="84e64-182">**Sender address**</span></span>

- <span data-ttu-id="84e64-183">**Empfangen**: Das Datum/die Uhrzeit des Nachrichtenempfangs.</span><span class="sxs-lookup"><span data-stu-id="84e64-183">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="84e64-184">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="84e64-184">**Subject**</span></span>

- <span data-ttu-id="84e64-185">**Quarantänegrund**: Zeigt an, ob eine Nachricht als **Spam**, **Massensendung** oder **Phishing** erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="84e64-185">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>

- <span data-ttu-id="84e64-186">**Empfänger**: Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Vorschau der Nachricht anzeigen** oder **Nachrichten** Kopfzeile anzeigen klicken, um die gesamte Liste der Empfänger anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="84e64-186">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="84e64-187">**Läuft ab**. Das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="84e64-187">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="84e64-188">**Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="84e64-188">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="84e64-189">**Noch nicht freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht noch nicht freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="84e64-189">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="84e64-190">Maßnahmen für isolierte E-Mails ergreifen</span><span class="sxs-lookup"><span data-stu-id="84e64-190">Take action on quarantined email</span></span>

<span data-ttu-id="84e64-191">Nachdem Sie eine Nachricht ausgewählt haben, haben Sie Optionen, was mit den Nachrichten im Flyout-Fenster **Details** geschehen soll:</span><span class="sxs-lookup"><span data-stu-id="84e64-191">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="84e64-192">**Nachricht freigeben**: Wählen Sie im angezeigten Flyout-Fenster, ob Sie **Meldungen zur Analyse an Microsoft melden** möchten.</span><span class="sxs-lookup"><span data-stu-id="84e64-192">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="84e64-193">Diese ist standardmäßig ausgewählt und meldet die irrtümlich isolierte Nachricht an Microsoft als falsches positives Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="84e64-193">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="84e64-194">Klicken Sie nach Abschluss des Vorgangs auf **Nachrichten freigeben**.</span><span class="sxs-lookup"><span data-stu-id="84e64-194">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="84e64-195">**Nachrichtenkopf anzeigen**: Wählen Sie diesen Link aus, um den Nachrichtenkopftext anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="84e64-195">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="84e64-196">Um den Nachrichtenkopf im Detail zu analysieren, kopieren Sie den Nachrichtenkopftext in die Zwischenablage, und wählen Sie dann **Microsoft-Nachrichtenkopfanalyse** aus, um zur Remoteverbindungsuntersuchung zu wechseln (klicken Sie mit der rechten Maustaste, und wählen Sie **In neuer Registerkarte öffnen** aus, wenn Sie Microsoft 365 nicht verlassen möchten, um die Aufgabe auszuführen).</span><span class="sxs-lookup"><span data-stu-id="84e64-196">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="84e64-197">Fügen Sie den Nachrichtenkopf auf der Seite in den Abschnitt "Nachrichtenkopfanalyse" ein, und wählen Sie dann **Kopfzeilen analysieren** aus:</span><span class="sxs-lookup"><span data-stu-id="84e64-197">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="84e64-198">**Vorschau der Nachricht anzeigen**: Wählen Sie im angezeigten Flyout-Fenster eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="84e64-198">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="84e64-199">**Quellansicht**: Zeigt die HTML-Version des Nachrichtentextes an, wobei alle Links deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="84e64-199">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="84e64-200">**Textansicht**: Zeigt den Nachrichtentext im Klartext an.</span><span class="sxs-lookup"><span data-stu-id="84e64-200">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="84e64-201">**Aus Quarantäne entfernen**: Nachdem Sie in der angezeigten Warnung auf **Ja** geklickt haben, wird die Nachricht sofort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="84e64-201">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

- <span data-ttu-id="84e64-202">**Absender blockieren**: Fügen Sie den Absender zur Liste blockierter Absender für Ihr Postfach hinzu.</span><span class="sxs-lookup"><span data-stu-id="84e64-202">**Block Sender**: Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="84e64-203">Weitere Informationen finden Sie unter [E-Mail-Absender blockieren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="84e64-203">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="84e64-204">Fügen Sie den Absender zur Liste blockierter Absender für Ihr Postfach hinzu.</span><span class="sxs-lookup"><span data-stu-id="84e64-204">Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="84e64-205">Weitere Informationen finden Sie unter [E-Mail-Absender blockieren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="84e64-205">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="84e64-206">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="84e64-206">When you're finished, click **Close**.</span></span>

<span data-ttu-id="84e64-207">Wenn Sie die Nachricht nicht freigeben oder entfernen, wird sie nach Ablauf der Standard-Quarantäneaufbewahrungszeit gelöscht.</span><span class="sxs-lookup"><span data-stu-id="84e64-207">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="84e64-208">Maßnahmen für mehrere isolierte E-Mail-Nachrichten ergreifen</span><span class="sxs-lookup"><span data-stu-id="84e64-208">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="84e64-209">Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), erscheint das Flyout-Fenster **Massenaktionen**, in dem Sie die folgenden Aktionen durchführen können:</span><span class="sxs-lookup"><span data-stu-id="84e64-209">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="84e64-210">**Nachrichten freigeben**: Die Optionen sind die gleichen wie bei der Freigabe einer einzelnen Nachricht, außer dass Sie nicht **Nachrichten an bestimmte Empfänger freigeben** auswählen können; Sie können nur **Nachricht an alle Empfänger freigeben** oder **Nachrichten an andere Personen freigeben** auswählen.</span><span class="sxs-lookup"><span data-stu-id="84e64-210">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="84e64-211">**Nachrichten löschen**: Nachdem Sie in der angezeigten Warnung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="84e64-211">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="84e64-212">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="84e64-212">When you're finished, click **Close**.</span></span>

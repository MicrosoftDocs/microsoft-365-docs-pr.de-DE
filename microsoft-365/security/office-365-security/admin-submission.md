---
title: Administratorübermittlungen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie das Übermittlungsportal im Security & Compliance Center verwenden, um verdächtige E-Mails, verdächtige Phishing-E-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und Dateien zur Überprüfung an Microsoft zu übermitteln.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed417db93bc2f3efa6b85b0ef97c10b5941cd8eb
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029514"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="86914-103">Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="86914-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="86914-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online können Administratoren das Übermittlungsportal im Security & Compliance Center verwenden, um E-Mail-Nachrichten, URLs und Anlagen zur Überprüfung an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="86914-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="86914-105">Wenn Sie eine E-Mail-Nachricht übermitteln, erhalten Sie:</span><span class="sxs-lookup"><span data-stu-id="86914-105">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="86914-106">**E-Mail-Authentifizierungsprüfung:** Details dazu, ob die E-Mail-Authentifizierung erfolgreich war oder nicht, als sie zugestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="86914-106">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="86914-107">**Richtlinientreffer:** Informationen zu allen Richtlinien, die möglicherweise eingehende E-Mails in Ihrem Mandanten zugelassen oder blockiert haben, und überschreiben unsere Dienstfilter-Verdingungen.</span><span class="sxs-lookup"><span data-stu-id="86914-107">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="86914-108">**Nutzlast-Reputation/-Detonation:** Untersuchung aller URLs und Anlagen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="86914-108">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="86914-109">**Analyse der** Benotung: Überprüfen Sie, ob Nachrichten bösartig sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="86914-109">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86914-110">Die Nutzlast-Reputations-/Detonation- und Bewertungsanalyse wird nicht in allen Mandanten durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="86914-110">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="86914-111">Informationen werden am Verlassen der Organisation blockiert, wenn Daten aus Compliancegründen nicht die Mandantengrenze verlassen sollen.</span><span class="sxs-lookup"><span data-stu-id="86914-111">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="86914-112">Weitere Möglichkeiten zum Senden von E-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter "Nachrichten und Dateien an [Microsoft melden".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="86914-112">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="86914-113">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="86914-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="86914-114">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="86914-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="86914-115">Um direkt zur **Übermittlungsseite zu** wechseln, verwenden Sie <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="86914-115">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="86914-116">Um Nachrichten und Dateien an Microsoft zu übermitteln, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="86914-116">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="86914-117">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="86914-117">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="86914-118">**Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="86914-118">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="86914-119">Beachten Sie, dass die Mitgliedschaft [](#view-user-submissions-to-the-custom-mailbox) in dieser Rollengruppe erforderlich ist, um Benutzerübermittlungen an das benutzerdefinierte Postfach wie weiter unten in diesem Artikel beschrieben anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="86914-119">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="86914-120">Weitere Informationen dazu, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter "Nachrichten und Dateien an [Microsoft melden".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="86914-120">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="86914-121">Verdächtige Inhalte an Microsoft melden</span><span class="sxs-lookup"><span data-stu-id="86914-121">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="86914-122">Wechseln Sie im Security & Compliance  Center zu "Übermittlungen zur \> **Bedrohungsverwaltung",** vergewissern Sie sich, dass Sie auf der Registerkarte **"Administratorübermittlungen"** sind, und klicken Sie dann auf **"Neue Übermittlung".**</span><span class="sxs-lookup"><span data-stu-id="86914-122">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="86914-123">Verwenden **Sie das Flyout "Neue** Übermittlung", das wie in den folgenden Abschnitten beschrieben angezeigt wird, um die Nachricht, URL oder Anlage zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="86914-123">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="86914-124">Senden einer fragwürdigen E-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="86914-124">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="86914-125">Wählen Sie **im Abschnitt "Objekttyp"** die Option **"E-Mail" aus.**</span><span class="sxs-lookup"><span data-stu-id="86914-125">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="86914-126">Verwenden Sie **im Abschnitt** "Übermittlungsformat" eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="86914-126">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="86914-127">**Netzwerknachrichten-ID:** Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-Id-Header** in der Nachricht oder im **X-MS-Office365-Filtering-Correlation-Id-Header** in isolierten Nachrichten verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="86914-127">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="86914-128">**Datei**: Klicken Sie **auf Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="86914-128">**File**: Click **Choose file**.</span></span> <span data-ttu-id="86914-129">Suchen Sie im dialogfeld, das geöffnet wird, die EML- oder MSG-Datei, und wählen Sie sie aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="86914-129">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="86914-130">Administratoren mit Defender für Office 365 Plan 1 oder Plan 2 können Nachrichten übermitteln, die 30 Tage alt sind.</span><span class="sxs-lookup"><span data-stu-id="86914-130">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="86914-131">Andere Administratoren können nur 7 Tage zurück gehen.</span><span class="sxs-lookup"><span data-stu-id="86914-131">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="86914-132">Geben Sie **im** Abschnitt "Empfänger" einen oder mehrere Empfänger an, für die Sie eine Richtlinienüberprüfung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="86914-132">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="86914-133">Die Richtlinienüberprüfung bestimmt, ob die Überprüfung per E-Mail aufgrund von Benutzer- oder Organisationsrichtlinien umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="86914-133">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="86914-134">Wählen Sie **im Abschnitt "Gründe für die** Übermittlung" eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="86914-134">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="86914-135">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="86914-135">**Should not have been blocked**</span></span>

   - <span data-ttu-id="86914-136">**Sollte blockiert worden sein:** Wählen **Sie Spam,** **Phishing** oder **Schadsoftware aus.**</span><span class="sxs-lookup"><span data-stu-id="86914-136">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="86914-137">Wenn Sie nicht sicher sind, verwenden Sie Ihre beste Einschätzung.</span><span class="sxs-lookup"><span data-stu-id="86914-137">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="86914-138">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="86914-138">When you're finished, click the **Submit** button.</span></span>

   ![Beispiel für die URL-Übermittlung](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="86914-140">Senden einer verdächtigen URL an Microsoft</span><span class="sxs-lookup"><span data-stu-id="86914-140">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="86914-141">Wählen Sie **im Abschnitt "Objekttyp"** die **URL aus.**</span><span class="sxs-lookup"><span data-stu-id="86914-141">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="86914-142">Geben Sie in das angezeigte Feld die vollständige URL ein (z. B. `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="86914-142">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="86914-143">Wählen Sie **im Abschnitt "Gründe für die** Übermittlung" eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="86914-143">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="86914-144">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="86914-144">**Should not have been blocked**</span></span>

   - <span data-ttu-id="86914-145">**Sollte blockiert worden sein:** Wählen Sie **Phishing oder** **Schadsoftware aus.**</span><span class="sxs-lookup"><span data-stu-id="86914-145">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="86914-146">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="86914-146">When you're finished, click the **Submit** button.</span></span>

   ![Beispiel für die E-Mail-Übermittlung](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="86914-148">Übermitteln einer verdächtigen Datei an Microsoft</span><span class="sxs-lookup"><span data-stu-id="86914-148">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="86914-149">Wählen Sie **im Abschnitt "Objekttyp"** die Option **"Anlage" aus.**</span><span class="sxs-lookup"><span data-stu-id="86914-149">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="86914-150">Klicken Sie **auf Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="86914-150">Click **Choose File**.</span></span> <span data-ttu-id="86914-151">Suchen Sie im dialogfeld, das geöffnet wird, die Datei, und wählen Sie sie aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="86914-151">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="86914-152">Wählen Sie **im Abschnitt "Gründe für die** Übermittlung" eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="86914-152">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="86914-153">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="86914-153">**Should not have been blocked**</span></span>

   - <span data-ttu-id="86914-154">**Sollte blockiert worden sein:** **Schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="86914-154">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="86914-155">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="86914-155">When you're finished, click the **Submit** button.</span></span>

   ![Beispiel für Anlagenübermittlung](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="86914-157">Anzeigen von Administratorübermittlungen</span><span class="sxs-lookup"><span data-stu-id="86914-157">View admin submissions</span></span>

<span data-ttu-id="86914-158">Wechseln Sie im Security & Compliance  Center zu "Übermittlungen zur \> **Bedrohungsverwaltung",** vergewissern Sie sich, dass Sie auf der Registerkarte **"Administratorübermittlungen"** sind, und klicken Sie dann auf **"Neue Übermittlung".**</span><span class="sxs-lookup"><span data-stu-id="86914-158">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="86914-159">Im oberen Seitenanfang können Sie ein Startdatum, ein Enddatum und (standardmäßig)  einen Filter nach Übermittlungs-ID (einem GUID-Wert, der jeder Übermittlung zugewiesen ist) eingeben, indem Sie einen Wert in das Feld eingeben und auf die Schaltfläche "Aktualisieren" ![ ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="86914-159">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="86914-160">Update</span><span class="sxs-lookup"><span data-stu-id="86914-160">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="86914-161">Um die Filterkriterien zu ändern, klicken Sie auf die Schaltfläche **"Übermittlungs-ID",** und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="86914-161">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="86914-162">**Sender**</span><span class="sxs-lookup"><span data-stu-id="86914-162">**Sender**</span></span>
- <span data-ttu-id="86914-163">**Betreff/URL/Dateiname**</span><span class="sxs-lookup"><span data-stu-id="86914-163">**Subject/URL/File name**</span></span>
- <span data-ttu-id="86914-164">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="86914-164">**Submitted by**</span></span>
- <span data-ttu-id="86914-165">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="86914-165">**Submission type**</span></span>
- <span data-ttu-id="86914-166">**Status**</span><span class="sxs-lookup"><span data-stu-id="86914-166">**Status**</span></span>

![Filteroptionen für Administratorübermittlungen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="86914-168">Zum Exportieren der Ergebnisse klicken **Sie** oben auf der Seite auf "Exportieren", und wählen Sie **Diagrammdaten** oder **Tabelle aus.**</span><span class="sxs-lookup"><span data-stu-id="86914-168">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="86914-169">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="86914-169">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="86914-170">Unterhalb des Diagramms gibt es drei Registerkarten: **E-Mail** (Standard), **URL** und **Anlage**.</span><span class="sxs-lookup"><span data-stu-id="86914-170">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="86914-171">Anzeigen von Administrator-E-Mail-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="86914-171">View admin email submissions</span></span>

<span data-ttu-id="86914-172">Klicken Sie auf die **Registerkarte "E-Mail".**</span><span class="sxs-lookup"><span data-stu-id="86914-172">Click the **Email** tab.</span></span>

<span data-ttu-id="86914-173">Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten in der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="86914-173">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="86914-174">**Date**</span><span class="sxs-lookup"><span data-stu-id="86914-174">**Date**</span></span>
- <span data-ttu-id="86914-175">**Übermittlungs-ID:** Ein GUID-Wert, der jeder Übermittlung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="86914-175">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="86914-176">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-176">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="86914-177">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-177">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="86914-178">**Sender**</span><span class="sxs-lookup"><span data-stu-id="86914-178">**Sender**</span></span>
- <span data-ttu-id="86914-179">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-179">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="86914-180">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="86914-180">**Submission type**</span></span>
- <span data-ttu-id="86914-181">**Zustellungsgrund**</span><span class="sxs-lookup"><span data-stu-id="86914-181">**Delivery reason**</span></span>
- <span data-ttu-id="86914-182">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-182">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="86914-183"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86914-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="86914-184">Details zur erneuten Eingabe der Administratorübermittlung</span><span class="sxs-lookup"><span data-stu-id="86914-184">Admin submission rescan details</span></span>

<span data-ttu-id="86914-185">Nachrichten, die in Administratorübermittlungen übermittelt werden, werden erneut überprüft, und die Ergebnisse werden im Detailf flyout angezeigt:</span><span class="sxs-lookup"><span data-stu-id="86914-185">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="86914-186">Wenn bei der E-Mail-Authentifizierung des Absenders zum Zeitpunkt der Zustellung ein Fehler aufting.</span><span class="sxs-lookup"><span data-stu-id="86914-186">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="86914-187">Informationen zu allen Richtlinientreffern, die die Entscheidung einer Nachricht beeinflusst oder außer Kraft gesetzt haben könnten.</span><span class="sxs-lookup"><span data-stu-id="86914-187">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="86914-188">Aktuelle Ergebnisse der Detonation, um zu sehen, ob die URLs oder Dateien in der Nachricht bösartig waren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="86914-188">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="86914-189">Feedback von Benotungsgebern.</span><span class="sxs-lookup"><span data-stu-id="86914-189">Feedback from graders.</span></span>

<span data-ttu-id="86914-190">Wenn eine Außerkraftsetzung gefunden wurde, sollte die Erneutes Scannen in einigen Minuten abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="86914-190">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="86914-191">Wenn kein Problem bei der E-Mail-Authentifizierung oder Zustellung von einer Außerkraftsetzung betroffen war, kann das Feedback der Benotungsbesteller bis zu einem Tag dauern.</span><span class="sxs-lookup"><span data-stu-id="86914-191">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="86914-192">Anzeigen von Admin-URL-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="86914-192">View admin URL submissions</span></span>

<span data-ttu-id="86914-193">Klicken Sie auf **die Registerkarte "URL".**</span><span class="sxs-lookup"><span data-stu-id="86914-193">Click the **URL** tab.</span></span>

<span data-ttu-id="86914-194">Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="86914-194">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="86914-195">**Date**</span><span class="sxs-lookup"><span data-stu-id="86914-195">**Date**</span></span>
- <span data-ttu-id="86914-196">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="86914-196">**Submission ID**</span></span>
- <span data-ttu-id="86914-197">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-197">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="86914-198">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-198">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="86914-199">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="86914-199">**Submission type**</span></span>
- <span data-ttu-id="86914-200">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-200">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="86914-201"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86914-201"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="86914-202">Anzeigen von Administrator-Anlagenübermittlungen</span><span class="sxs-lookup"><span data-stu-id="86914-202">View admin attachment submissions</span></span>

<span data-ttu-id="86914-203">Klicken Sie auf die **Registerkarte "Anlagen".**</span><span class="sxs-lookup"><span data-stu-id="86914-203">Click the **Attachments** tab.</span></span>

<span data-ttu-id="86914-204">Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="86914-204">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="86914-205">**Date**</span><span class="sxs-lookup"><span data-stu-id="86914-205">**Date**</span></span>
- <span data-ttu-id="86914-206">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="86914-206">**Submission ID**</span></span>
- <span data-ttu-id="86914-207">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-207">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="86914-208">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-208">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="86914-209">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="86914-209">**Submission type**</span></span>
- <span data-ttu-id="86914-210">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-210">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="86914-211"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86914-211"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="86914-212">Anzeigen von Benutzerübermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="86914-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="86914-213">Wenn Sie das Report [Message-Add-In,](enable-the-report-message-add-in.md)das [Phishing-Add-In](enable-the-report-phish-add-in.md)"Melden" oder Personen, die die integrierte Berichterstellung in  [Outlook im Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)verwenden, bereitgestellt haben, können Sie auf der Registerkarte "Benutzerübermittlungen" anzeigen, welche Benutzer berichte.</span><span class="sxs-lookup"><span data-stu-id="86914-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="86914-214">Wechseln Sie im Security & Compliance Center zu **"Übermittlungen zur** \> **Bedrohungsverwaltung".**</span><span class="sxs-lookup"><span data-stu-id="86914-214">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="86914-215">Wählen Sie **die Registerkarte "Benutzerübermittlungen"** aus, und klicken Sie dann auf **"Neue Übermittlung".**</span><span class="sxs-lookup"><span data-stu-id="86914-215">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="86914-216">Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="86914-216">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="86914-217">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="86914-217">**Submitted on**</span></span>
- <span data-ttu-id="86914-218">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-218">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="86914-219">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-219">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="86914-220">**Sender**</span><span class="sxs-lookup"><span data-stu-id="86914-220">**Sender**</span></span>
- <span data-ttu-id="86914-221">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-221">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="86914-222">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="86914-222">**Submission type**</span></span>

<span data-ttu-id="86914-223"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86914-223"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="86914-224">Im oberen Seitenanfang können Sie ein Startdatum, ein Enddatum und (standardmäßig) einen Filter nach **Absender** eingeben, indem Sie einen Wert in das Feld eingeben und auf die Schaltfläche Aktualisieren ![ ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="86914-224">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="86914-225">Update</span><span class="sxs-lookup"><span data-stu-id="86914-225">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="86914-226">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **"Absender",** und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="86914-226">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="86914-227">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="86914-227">**Sender domain**</span></span>
- <span data-ttu-id="86914-228">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="86914-228">**Subject**</span></span>
- <span data-ttu-id="86914-229">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="86914-229">**Submitted by**</span></span>
- <span data-ttu-id="86914-230">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="86914-230">**Submission type**</span></span>
- <span data-ttu-id="86914-231">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="86914-231">**Sender IP**</span></span>

![Filteroptionen für Benutzerübermittlungen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="86914-233">Zum Exportieren der Ergebnisse klicken **Sie** oben auf der Seite auf "Exportieren", und wählen Sie **Diagrammdaten** oder **Tabelle aus.**</span><span class="sxs-lookup"><span data-stu-id="86914-233">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="86914-234">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="86914-234">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="86914-235">Anzeigen von Benutzerübermittlungen an das benutzerdefinierte Postfach</span><span class="sxs-lookup"><span data-stu-id="86914-235">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="86914-236">**Wenn** Sie ein [benutzerdefiniertes](user-submission.md) Postfach für den Empfang von vom Benutzer gemeldeten Nachrichten konfiguriert haben, können Sie auch Nachrichten anzeigen und übermitteln, die an das Berichtspostfach zugestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="86914-236">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="86914-237">Wechseln Sie im Security & Compliance Center zu **"Übermittlungen zur** \> **Bedrohungsverwaltung".**</span><span class="sxs-lookup"><span data-stu-id="86914-237">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="86914-238">Wählen Sie die **Registerkarte "Benutzerdefiniertes Postfach"** aus.</span><span class="sxs-lookup"><span data-stu-id="86914-238">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="86914-239">Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="86914-239">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="86914-240">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="86914-240">**Submitted on**</span></span>
- <span data-ttu-id="86914-241">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-241">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="86914-242">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-242">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="86914-243">**Sender**</span><span class="sxs-lookup"><span data-stu-id="86914-243">**Sender**</span></span>
- <span data-ttu-id="86914-244">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86914-244">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="86914-245">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="86914-245">**Submission type**</span></span>

<span data-ttu-id="86914-246">Im oberen Seitenanfang können Sie ein Startdatum, ein Enddatum eingeben  und nach "Übermittelt" filtern, indem Sie einen Wert in das Feld eingeben und auf die Schaltfläche ![ "Aktualisieren" ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="86914-246">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="86914-247">Update</span><span class="sxs-lookup"><span data-stu-id="86914-247">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="86914-248">Zum Exportieren der Ergebnisse klicken **Sie** oben auf der Seite auf "Exportieren", und wählen Sie **Diagrammdaten** oder **Tabelle aus.**</span><span class="sxs-lookup"><span data-stu-id="86914-248">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="86914-249">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="86914-249">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="86914-250">Rückgängig machen von Benutzerübermittlungen</span><span class="sxs-lookup"><span data-stu-id="86914-250">Undo user submissions</span></span>

<span data-ttu-id="86914-251">Sobald ein Benutzer eine verdächtige E-Mail an das benutzerdefinierte Postfach übermittelt hat, haben der Benutzer und der Administrator keine Möglichkeit, die Übermittlung rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="86914-251">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="86914-252">Wenn der Benutzer die E-Mail wiederherstellen möchte, steht sie für die Wiederherstellung in den Ordnern "Gelöschte Elemente" oder "Junk-E-Mail" zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="86914-252">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="86914-253">Senden von Nachrichten aus dem benutzerdefinierten Postfach an Microsoft</span><span class="sxs-lookup"><span data-stu-id="86914-253">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="86914-254">Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass von Benutzern gemeldete Nachrichten abgefangen werden, ohne die Nachrichten an Microsoft zu senden, können Sie bestimmte Nachrichten zur Analyse finden und an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="86914-254">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="86914-255">Dadurch wird eine Benutzerübermittlung effektiv in eine Administratorübermittlung verlagert.</span><span class="sxs-lookup"><span data-stu-id="86914-255">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="86914-256">Wählen Sie auf der Registerkarte **"Benutzerdefiniertes**  Postfach" eine Nachricht in der Liste aus, klicken Sie auf die Schaltfläche "Aktion", und treffen Sie eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="86914-256">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="86914-257">**Bereinigen des Berichts**</span><span class="sxs-lookup"><span data-stu-id="86914-257">**Report clean**</span></span>
- <span data-ttu-id="86914-258">**Melden von Phishing**</span><span class="sxs-lookup"><span data-stu-id="86914-258">**Report phishing**</span></span>
- <span data-ttu-id="86914-259">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="86914-259">**Report malware**</span></span>
- <span data-ttu-id="86914-260">**Melden von Spam**</span><span class="sxs-lookup"><span data-stu-id="86914-260">**Report spam**</span></span>

![Optionen auf der Schaltfläche "Aktion"](../../media/user-submission-custom-mailbox-action-button.png)

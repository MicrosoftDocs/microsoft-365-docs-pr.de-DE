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
ms.openlocfilehash: 7a822909c318cb336c179b299aa64cd71dcca4d8
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175871"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="38a27-103">Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="38a27-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="38a27-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="38a27-104">**Applies to**</span></span>
- [<span data-ttu-id="38a27-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="38a27-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="38a27-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="38a27-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)


<span data-ttu-id="38a27-107">In Microsoft 365-Organisationen mit Postfächern in Exchange Online können Administratoren das Übermittlungsportal im Security & Compliance Center verwenden, um E-Mail-Nachrichten, URLs und Anlagen zur Überprüfung an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="38a27-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="38a27-108">Wenn Sie eine E-Mail-Nachricht übermitteln, erhalten Sie:</span><span class="sxs-lookup"><span data-stu-id="38a27-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="38a27-109">**E-Mail-Authentifizierungsprüfung:** Details dazu, ob die E-Mail-Authentifizierung erfolgreich war oder nicht, als sie zugestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="38a27-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="38a27-110">**Richtlinientreffer:** Informationen zu allen Richtlinien, die möglicherweise eingehende E-Mails in Ihrem Mandanten zugelassen oder blockiert haben, und überschreiben unsere Dienstfilter-Verdingungen.</span><span class="sxs-lookup"><span data-stu-id="38a27-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="38a27-111">**Nutzlast-Reputation/-Detonation:** Untersuchung aller URLs und Anlagen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="38a27-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="38a27-112">**Analyse der** Benotung: Überprüfen Sie, ob Nachrichten bösartig sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="38a27-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38a27-113">Die Nutzlast-Reputations-/Detonation- und Bewertungsanalyse wird nicht in allen Mandanten durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="38a27-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="38a27-114">Informationen werden am Verlassen der Organisation blockiert, wenn Daten aus Compliancegründen nicht die Mandantengrenze verlassen sollen.</span><span class="sxs-lookup"><span data-stu-id="38a27-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="38a27-115">Weitere Möglichkeiten zum Senden von E-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter "Nachrichten und Dateien an [Microsoft melden".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="38a27-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="38a27-116">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="38a27-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="38a27-117">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="38a27-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="38a27-118">Um direkt zur **Übermittlungsseite zu** wechseln, verwenden Sie <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="38a27-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="38a27-119">Um Nachrichten und Dateien an Microsoft zu übermitteln, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="38a27-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="38a27-120">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="38a27-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="38a27-121">**Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="38a27-121">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="38a27-122">Beachten Sie, dass die Mitgliedschaft [](#view-user-submissions-to-the-custom-mailbox) in dieser Rollengruppe erforderlich ist, um Benutzerübermittlungen an das benutzerdefinierte Postfach wie weiter unten in diesem Artikel beschrieben anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="38a27-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="38a27-123">Weitere Informationen dazu, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter "Nachrichten und Dateien an [Microsoft melden".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="38a27-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="38a27-124">Melden verdächtiger Inhalte an Microsoft</span><span class="sxs-lookup"><span data-stu-id="38a27-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="38a27-125">Wechseln Sie im Security & Compliance  Center zu "Übermittlungen zur \> **Bedrohungsverwaltung",** vergewissern Sie sich, dass Sie auf der Registerkarte **"Administratorübermittlungen"** sind, und klicken Sie dann auf **"Neue Übermittlung".**</span><span class="sxs-lookup"><span data-stu-id="38a27-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="38a27-126">Verwenden **Sie das Flyout "Neue** Übermittlung", das wie in den folgenden Abschnitten beschrieben angezeigt wird, um die Nachricht, URL oder Anlage zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="38a27-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="38a27-127">Senden einer fragwürdigen E-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="38a27-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="38a27-128">Wählen Sie **im Abschnitt "Objekttyp"** die Option **"E-Mail" aus.**</span><span class="sxs-lookup"><span data-stu-id="38a27-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="38a27-129">Verwenden Sie **im Abschnitt** "Übermittlungsformat" eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="38a27-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="38a27-130">**Netzwerknachrichten-ID:** Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-Id-Header** in der Nachricht oder im **X-MS-Office365-Filtering-Correlation-Id-Header** in isolierten Nachrichten verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="38a27-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="38a27-131">**Datei**: Klicken Sie **auf Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="38a27-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="38a27-132">Suchen Sie im dialogfeld, das geöffnet wird, die EML- oder MSG-Datei, und wählen Sie sie aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="38a27-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="38a27-133">Administratoren mit Defender für Office 365 Plan 1 oder Plan 2 können Nachrichten übermitteln, die 30 Tage alt sind.</span><span class="sxs-lookup"><span data-stu-id="38a27-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="38a27-134">Andere Administratoren können nur 7 Tage zurück gehen.</span><span class="sxs-lookup"><span data-stu-id="38a27-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="38a27-135">Geben Sie **im** Abschnitt "Empfänger" einen oder mehrere Empfänger an, für die Sie eine Richtlinienüberprüfung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="38a27-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="38a27-136">Die Richtlinienprüfung bestimmt, ob die Überprüfung per E-Mail aufgrund von Benutzer- oder Organisationsrichtlinien umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="38a27-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="38a27-137">Wählen Sie **im Abschnitt "Gründe für die** Übermittlung" eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="38a27-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="38a27-138">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="38a27-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="38a27-139">**Sollte blockiert worden sein:** Wählen **Sie Spam,** **Phishing** oder **Schadsoftware aus.**</span><span class="sxs-lookup"><span data-stu-id="38a27-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="38a27-140">Wenn Sie nicht sicher sind, verwenden Sie Ihre beste Einschätzung.</span><span class="sxs-lookup"><span data-stu-id="38a27-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="38a27-141">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="38a27-141">When you're finished, click the **Submit** button.</span></span>

   ![Beispiel für die URL-Übermittlung](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="38a27-143">Senden einer verdächtigen URL an Microsoft</span><span class="sxs-lookup"><span data-stu-id="38a27-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="38a27-144">Wählen Sie **im Abschnitt "Objekttyp"** die **URL aus.**</span><span class="sxs-lookup"><span data-stu-id="38a27-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="38a27-145">Geben Sie in das angezeigte Feld die vollständige URL ein (z. B. `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="38a27-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="38a27-146">Wählen Sie **im Abschnitt "Gründe für die** Übermittlung" eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="38a27-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="38a27-147">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="38a27-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="38a27-148">**Sollte blockiert worden sein:** Wählen Sie **Phishing oder** **Schadsoftware aus.**</span><span class="sxs-lookup"><span data-stu-id="38a27-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="38a27-149">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="38a27-149">When you're finished, click the **Submit** button.</span></span>

   ![Beispiel für die E-Mail-Übermittlung](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="38a27-151">Übermitteln einer verdächtigen Datei an Microsoft</span><span class="sxs-lookup"><span data-stu-id="38a27-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="38a27-152">Wählen Sie **im Abschnitt "Objekttyp"** die Option **"Anlage" aus.**</span><span class="sxs-lookup"><span data-stu-id="38a27-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="38a27-153">Klicken Sie **auf Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="38a27-153">Click **Choose File**.</span></span> <span data-ttu-id="38a27-154">Suchen Sie im dialogfeld, das geöffnet wird, die Datei, und wählen Sie sie aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="38a27-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="38a27-155">Wählen Sie **im Abschnitt "Gründe für die** Übermittlung" eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="38a27-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="38a27-156">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="38a27-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="38a27-157">**Sollte blockiert worden sein:** **Schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="38a27-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="38a27-158">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="38a27-158">When you're finished, click the **Submit** button.</span></span>

   ![Beispiel für Anlagenübermittlung](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="38a27-160">Anzeigen von Administratorübermittlungen</span><span class="sxs-lookup"><span data-stu-id="38a27-160">View admin submissions</span></span>

<span data-ttu-id="38a27-161">Wechseln Sie im Security & Compliance  Center zu "Übermittlungen zur \> **Bedrohungsverwaltung",** vergewissern Sie sich, dass Sie auf der Registerkarte **"Administratorübermittlungen"** sind, und klicken Sie dann auf **"Neue Übermittlung".**</span><span class="sxs-lookup"><span data-stu-id="38a27-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="38a27-162">Im oberen Seitenanfang können Sie ein Startdatum, ein Enddatum und (standardmäßig)  einen Filter nach Übermittlungs-ID (einem GUID-Wert, der jeder Übermittlung zugewiesen ist) eingeben, indem Sie einen Wert in das Feld eingeben und auf die Schaltfläche Aktualisieren ![ ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="38a27-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="38a27-163">Update</span><span class="sxs-lookup"><span data-stu-id="38a27-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="38a27-164">Um die Filterkriterien zu ändern, klicken Sie auf die Schaltfläche **"Übermittlungs-ID",** und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="38a27-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="38a27-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="38a27-165">**Sender**</span></span>
- <span data-ttu-id="38a27-166">**Betreff/URL/Dateiname**</span><span class="sxs-lookup"><span data-stu-id="38a27-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="38a27-167">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="38a27-167">**Submitted by**</span></span>
- <span data-ttu-id="38a27-168">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="38a27-168">**Submission type**</span></span>
- <span data-ttu-id="38a27-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="38a27-169">**Status**</span></span>

![Filteroptionen für Administratorübermittlungen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="38a27-171">Zum Exportieren der Ergebnisse klicken **Sie** oben auf der Seite auf "Exportieren", und wählen Sie **Diagrammdaten** oder **Tabelle aus.**</span><span class="sxs-lookup"><span data-stu-id="38a27-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="38a27-172">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="38a27-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="38a27-173">Unterhalb des Diagramms gibt es drei Registerkarten: **E-Mail** (Standard), **URL** und **Anlage**.</span><span class="sxs-lookup"><span data-stu-id="38a27-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="38a27-174">Anzeigen von Administrator-E-Mail-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="38a27-174">View admin email submissions</span></span>

<span data-ttu-id="38a27-175">Klicken Sie auf die **Registerkarte "E-Mail".**</span><span class="sxs-lookup"><span data-stu-id="38a27-175">Click the **Email** tab.</span></span>

<span data-ttu-id="38a27-176">Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="38a27-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="38a27-177">**Date**</span><span class="sxs-lookup"><span data-stu-id="38a27-177">**Date**</span></span>
- <span data-ttu-id="38a27-178">**Übermittlungs-ID:** Ein GUID-Wert, der jeder Übermittlung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="38a27-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="38a27-179">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="38a27-180">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="38a27-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="38a27-181">**Sender**</span></span>
- <span data-ttu-id="38a27-182">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="38a27-183">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="38a27-183">**Submission type**</span></span>
- <span data-ttu-id="38a27-184">**Zustellungsgrund**</span><span class="sxs-lookup"><span data-stu-id="38a27-184">**Delivery reason**</span></span>
- <span data-ttu-id="38a27-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="38a27-186"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="38a27-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="38a27-187">Details zur erneuten Eingabe der Administratorübermittlung</span><span class="sxs-lookup"><span data-stu-id="38a27-187">Admin submission rescan details</span></span>

<span data-ttu-id="38a27-188">Nachrichten, die in Administratorübermittlungen übermittelt werden, werden erneut überprüft, und die Ergebnisse werden im Detailf flyout angezeigt:</span><span class="sxs-lookup"><span data-stu-id="38a27-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="38a27-189">Wenn bei der E-Mail-Authentifizierung des Absenders zum Zeitpunkt der Zustellung ein Fehler aufting.</span><span class="sxs-lookup"><span data-stu-id="38a27-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="38a27-190">Informationen zu allen Richtlinientreffern, die die Entscheidung einer Nachricht beeinflusst oder außer Kraft gesetzt haben könnten.</span><span class="sxs-lookup"><span data-stu-id="38a27-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="38a27-191">Aktuelle Ergebnisse der Detonation, um zu sehen, ob die URLs oder Dateien in der Nachricht bösartig waren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="38a27-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="38a27-192">Feedback von Benotungsgebern.</span><span class="sxs-lookup"><span data-stu-id="38a27-192">Feedback from graders.</span></span>

<span data-ttu-id="38a27-193">Wenn eine Außerkraftsetzung gefunden wurde, sollte die Erneutes Scannen in einigen Minuten abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="38a27-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="38a27-194">Wenn kein Problem bei der E-Mail-Authentifizierung oder Zustellung von einer Außerkraftsetzung betroffen war, kann das Feedback der Benotungsbesteller bis zu einem Tag dauern.</span><span class="sxs-lookup"><span data-stu-id="38a27-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="38a27-195">Anzeigen von Admin-URL-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="38a27-195">View admin URL submissions</span></span>

<span data-ttu-id="38a27-196">Klicken Sie auf **die Registerkarte "URL".**</span><span class="sxs-lookup"><span data-stu-id="38a27-196">Click the **URL** tab.</span></span>

<span data-ttu-id="38a27-197">Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="38a27-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="38a27-198">**Date**</span><span class="sxs-lookup"><span data-stu-id="38a27-198">**Date**</span></span>
- <span data-ttu-id="38a27-199">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="38a27-199">**Submission ID**</span></span>
- <span data-ttu-id="38a27-200">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="38a27-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="38a27-202">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="38a27-202">**Submission type**</span></span>
- <span data-ttu-id="38a27-203">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="38a27-204"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="38a27-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="38a27-205">Anzeigen von Administrator-Anlagenübermittlungen</span><span class="sxs-lookup"><span data-stu-id="38a27-205">View admin attachment submissions</span></span>

<span data-ttu-id="38a27-206">Klicken Sie auf die **Registerkarte "Anlagen".**</span><span class="sxs-lookup"><span data-stu-id="38a27-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="38a27-207">Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="38a27-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="38a27-208">**Date**</span><span class="sxs-lookup"><span data-stu-id="38a27-208">**Date**</span></span>
- <span data-ttu-id="38a27-209">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="38a27-209">**Submission ID**</span></span>
- <span data-ttu-id="38a27-210">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="38a27-211">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="38a27-212">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="38a27-212">**Submission type**</span></span>
- <span data-ttu-id="38a27-213">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="38a27-214"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="38a27-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="38a27-215">Anzeigen von Benutzerübermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="38a27-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="38a27-216">Wenn Sie das Add-in "Nachricht melden", das [Phishing-Add-In](enable-the-report-phish-add-in.md)"Melden" oder Personen, die die integrierte Berichterstellung  [in Outlook im Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)verwenden, bereitgestellt haben, können Sie auf der Registerkarte "Benutzerübermittlungen" anzeigen, welche Benutzer berichte. [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="38a27-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="38a27-217">Wechseln Sie im Security & Compliance Center zu **"Übermittlungen zur** \> **Bedrohungsverwaltung".**</span><span class="sxs-lookup"><span data-stu-id="38a27-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="38a27-218">Wählen Sie **die Registerkarte "Benutzerübermittlungen"** aus, und klicken Sie dann auf **"Neue Übermittlung".**</span><span class="sxs-lookup"><span data-stu-id="38a27-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="38a27-219">Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="38a27-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="38a27-220">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="38a27-220">**Submitted on**</span></span>
- <span data-ttu-id="38a27-221">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="38a27-222">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="38a27-223">**Sender**</span><span class="sxs-lookup"><span data-stu-id="38a27-223">**Sender**</span></span>
- <span data-ttu-id="38a27-224">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="38a27-225">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="38a27-225">**Submission type**</span></span>

<span data-ttu-id="38a27-226"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="38a27-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="38a27-227">Im oberen Seitenanfang können Sie ein Startdatum, ein Enddatum und (standardmäßig) einen Filter nach **Absender** eingeben, indem Sie einen Wert in das Feld eingeben und auf die Schaltfläche Aktualisieren ![ ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="38a27-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="38a27-228">Update</span><span class="sxs-lookup"><span data-stu-id="38a27-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="38a27-229">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **"Absender",** und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="38a27-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="38a27-230">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="38a27-230">**Sender domain**</span></span>
- <span data-ttu-id="38a27-231">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="38a27-231">**Subject**</span></span>
- <span data-ttu-id="38a27-232">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="38a27-232">**Submitted by**</span></span>
- <span data-ttu-id="38a27-233">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="38a27-233">**Submission type**</span></span>
- <span data-ttu-id="38a27-234">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="38a27-234">**Sender IP**</span></span>

![Filteroptionen für Benutzerübermittlungen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="38a27-236">Zum Exportieren der Ergebnisse klicken **Sie** oben auf der Seite auf "Exportieren", und wählen Sie **Diagrammdaten** oder **Tabelle aus.**</span><span class="sxs-lookup"><span data-stu-id="38a27-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="38a27-237">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="38a27-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="38a27-238">Anzeigen von Benutzerübermittlungen an das benutzerdefinierte Postfach</span><span class="sxs-lookup"><span data-stu-id="38a27-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="38a27-239">**Wenn** Sie ein [benutzerdefiniertes](user-submission.md) Postfach für den Empfang von vom Benutzer gemeldeten Nachrichten konfiguriert haben, können Sie auch Nachrichten anzeigen und übermitteln, die an das Berichtspostfach zugestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="38a27-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="38a27-240">Wechseln Sie im Security & Compliance Center zu **"Übermittlungen zur** \> **Bedrohungsverwaltung".**</span><span class="sxs-lookup"><span data-stu-id="38a27-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="38a27-241">Wählen Sie die **Registerkarte "Benutzerdefiniertes Postfach"** aus.</span><span class="sxs-lookup"><span data-stu-id="38a27-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="38a27-242">Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="38a27-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="38a27-243">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="38a27-243">**Submitted on**</span></span>
- <span data-ttu-id="38a27-244">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="38a27-245">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="38a27-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="38a27-246">**Sender**</span></span>
- <span data-ttu-id="38a27-247">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38a27-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="38a27-248">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="38a27-248">**Submission type**</span></span>

<span data-ttu-id="38a27-249">Im oberen Seitenanfang können Sie ein Startdatum, ein Enddatum eingeben  und nach "Übermittelt" filtern, indem Sie einen Wert in das Feld eingeben und auf die Schaltfläche ![ "Aktualisieren" ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="38a27-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="38a27-250">Update</span><span class="sxs-lookup"><span data-stu-id="38a27-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="38a27-251">Zum Exportieren der Ergebnisse klicken **Sie** oben auf der Seite auf "Exportieren", und wählen Sie **Diagrammdaten** oder **Tabelle aus.**</span><span class="sxs-lookup"><span data-stu-id="38a27-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="38a27-252">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="38a27-252">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="38a27-253">Rückgängig machen von Benutzerübermittlungen</span><span class="sxs-lookup"><span data-stu-id="38a27-253">Undo user submissions</span></span>

<span data-ttu-id="38a27-254">Sobald ein Benutzer eine verdächtige E-Mail an das benutzerdefinierte Postfach übermittelt hat, haben der Benutzer und der Administrator keine Möglichkeit, die Übermittlung rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="38a27-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="38a27-255">Wenn der Benutzer die E-Mail wiederherstellen möchte, steht sie für die Wiederherstellung in den Ordnern "Gelöschte Elemente" oder "Junk-E-Mail" zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="38a27-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="38a27-256">Senden von Nachrichten aus dem benutzerdefinierten Postfach an Microsoft</span><span class="sxs-lookup"><span data-stu-id="38a27-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="38a27-257">Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass von Benutzern gemeldete Nachrichten abgefangen werden, ohne die Nachrichten an Microsoft zu senden, können Sie bestimmte Nachrichten zur Analyse finden und an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="38a27-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="38a27-258">Dadurch wird eine Benutzerübermittlung effektiv in eine Administratorübermittlung verlagert.</span><span class="sxs-lookup"><span data-stu-id="38a27-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="38a27-259">Wählen Sie auf der Registerkarte **"Benutzerdefiniertes**  Postfach" eine Nachricht in der Liste aus, klicken Sie auf die Schaltfläche "Aktion", und treffen Sie eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="38a27-259">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="38a27-260">**Bereinigen des Berichts**</span><span class="sxs-lookup"><span data-stu-id="38a27-260">**Report clean**</span></span>
- <span data-ttu-id="38a27-261">**Melden von Phishing**</span><span class="sxs-lookup"><span data-stu-id="38a27-261">**Report phishing**</span></span>
- <span data-ttu-id="38a27-262">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="38a27-262">**Report malware**</span></span>
- <span data-ttu-id="38a27-263">**Melden von Spam**</span><span class="sxs-lookup"><span data-stu-id="38a27-263">**Report spam**</span></span>

![Optionen auf der Schaltfläche "Aktion"](../../media/user-submission-custom-mailbox-action-button.png)

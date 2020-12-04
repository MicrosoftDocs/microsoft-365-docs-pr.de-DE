---
title: Übermittlungen von Administratoren
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie das Übermittlungen-Portal im Security & Compliance Center verwenden, um verdächtige e-Mails, verdächtige Phishing-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und Dateien für die Überprüfung an Microsoft zu übermitteln.
ms.openlocfilehash: 0c01afff2e9e5a656099192f3867bb3a6f1cee23
ms.sourcegitcommit: 7e003ee0a06f61bfb9f80441c3479fa3148afafe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "49568590"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="91264-103">Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="91264-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="91264-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online können Administratoren das Übermittlungen-Portal im Security & Compliance Center verwenden, um e-Mail-Nachrichten, URLs und Anlagen für die Überprüfung an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="91264-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="91264-105">Wenn Sie eine e-Mail übermitteln, erhalten Sie Informationen zu allen Richtlinien, die möglicherweise die eingehenden e-Mails in ihren Mandanten zugelassen haben, sowie über die Untersuchung von URLs und Anlagen in der e-Mail.</span><span class="sxs-lookup"><span data-stu-id="91264-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="91264-106">Richtlinien, die möglicherweise eine e-Mail erlaubt haben, enthalten die Liste sicherer Absender eines einzelnen Benutzers sowie Richtlinien auf Mandantenebene wie Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln).</span><span class="sxs-lookup"><span data-stu-id="91264-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="91264-107">Weitere Möglichkeiten zum Übermitteln von e-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="91264-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="91264-108">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="91264-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="91264-109">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="91264-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="91264-110">Wenn Sie direkt zur **Übermittlungs** Seite wechseln möchten, verwenden Sie <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="91264-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="91264-111">Um Nachrichten und Dateien an Microsoft zu übermitteln, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="91264-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="91264-112">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="91264-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="91264-113">**Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="91264-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="91264-114">Beachten Sie, dass die Mitgliedschaft in dieser Rollengruppe erforderlich ist, um [Benutzer Übermittlungen an das benutzerdefinierte Postfach anzuzeigen](#view-user-submissions-to-the-custom-mailbox) , wie weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91264-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="91264-115">Weitere Informationen darüber, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="91264-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="91264-116">Verdächtigen Inhalt an Microsoft melden</span><span class="sxs-lookup"><span data-stu-id="91264-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="91264-117">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> -über **mittlungen**, stellen Sie sicher, dass Sie sich auf der Registerkarte Admin-über **mittlungen** befinden, und klicken Sie dann auf **neue Übermittlung**.</span><span class="sxs-lookup"><span data-stu-id="91264-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="91264-118">Verwenden Sie das **neue Übermittlungs** Flyout, das angezeigt wird, um die Nachricht, die URL oder Anlage zu übermitteln, wie in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91264-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="91264-119">Senden einer fragwürdigen e-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="91264-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="91264-120">Wählen Sie im Abschnitt **Objekttyp** die Option **e-Mail** aus.</span><span class="sxs-lookup"><span data-stu-id="91264-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="91264-121">Verwenden Sie im Abschnitt **Übermittlungs Format** eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="91264-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="91264-122">**Netzwerknachrichten-ID**: Dies ist ein GUID-Wert, der im **x-MS-Exchange-Organization-Network-Message-ID** -Header in der Nachricht oder im **x-ms-Office365-Filter-Korrelations-ID** -Header in unter Quarantäne gestellten Nachrichten zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="91264-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="91264-123">**Datei**: Klicken Sie auf **Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="91264-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="91264-124">Suchen Sie in dem Dialogfeld, das geöffnet wird, nach der EML-oder msg-Datei, und wählen Sie Sie aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="91264-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="91264-125">Administratoren mit Defender für Office 365 Plan 1 oder Plan 2 können Nachrichten senden, die älter als 30 Tage sind.</span><span class="sxs-lookup"><span data-stu-id="91264-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="91264-126">Andere Administratoren werden nur 7 Tage zurückkehren können.</span><span class="sxs-lookup"><span data-stu-id="91264-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="91264-127">Geben Sie im Abschnitt **Empfänger** einen oder mehrere Empfänger an, für die Sie eine Richtlinienüberprüfung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="91264-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="91264-128">Durch die Richtlinienüberprüfung wird ermittelt, ob die e-Mail-Überprüfung aufgrund von Benutzer-oder Organisationsrichtlinien umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="91264-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="91264-129">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="91264-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="91264-130">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="91264-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="91264-131">**Sollte blockiert worden sein**: Wählen Sie **Spam**, **Phishing** oder **Schadsoftware** aus.</span><span class="sxs-lookup"><span data-stu-id="91264-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="91264-132">Wenn Sie nicht sicher sind, verwenden Sie Ihr Bestes Urteil.</span><span class="sxs-lookup"><span data-stu-id="91264-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="91264-133">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="91264-133">When you're finished, click the **Submit** button.</span></span>

![URL-Übermittlungs Beispiel](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="91264-135">Senden einer verdächtigen URL an Microsoft</span><span class="sxs-lookup"><span data-stu-id="91264-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="91264-136">Wählen Sie im Abschnitt **Objekttyp** die Option **URL** aus.</span><span class="sxs-lookup"><span data-stu-id="91264-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="91264-137">Geben Sie in das Feld, das angezeigt wird, die vollständige URL ein (beispielsweise `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="91264-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="91264-138">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="91264-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="91264-139">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="91264-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="91264-140">**Sollte blockiert worden sein**: Wählen Sie **Phishing** oder **Schadsoftware** aus.</span><span class="sxs-lookup"><span data-stu-id="91264-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="91264-141">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="91264-141">When you're finished, click the **Submit** button.</span></span>

![Beispiel für eine e-Mail-Übermittlung](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="91264-143">Übermitteln einer vermuteten Datei an Microsoft</span><span class="sxs-lookup"><span data-stu-id="91264-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="91264-144">Wählen Sie im Abschnitt **Objekttyp** die Option **Anlage** aus.</span><span class="sxs-lookup"><span data-stu-id="91264-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="91264-145">Klicken Sie auf **Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="91264-145">Click **Choose File**.</span></span> <span data-ttu-id="91264-146">Suchen und wählen Sie im daraufhin geöffneten Dialogfeld die Datei aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="91264-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="91264-147">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="91264-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="91264-148">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="91264-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="91264-149">**Sollte blockiert worden sein**: **Schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt..</span><span class="sxs-lookup"><span data-stu-id="91264-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="91264-150">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="91264-150">When you're finished, click the **Submit** button.</span></span>

![Beispiel für Anlagen Übermittlung](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="91264-152">Anzeigen von Übermittlungen von Administratoren</span><span class="sxs-lookup"><span data-stu-id="91264-152">View admin submissions</span></span>

<span data-ttu-id="91264-153">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> -über **mittlungen**, stellen Sie sicher, dass Sie sich auf der Registerkarte Admin-über **mittlungen** befinden, und klicken Sie dann auf **neue Übermittlung**.</span><span class="sxs-lookup"><span data-stu-id="91264-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="91264-154">Oben auf der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Übermittlungs-ID** (ein GUID-Wert, der jeder Übermittlung zugewiesen ist) filtern, indem Sie einen Wert in das Feld eingeben und auf Aktualisieren klicken ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="91264-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="91264-155">Update</span><span class="sxs-lookup"><span data-stu-id="91264-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="91264-156">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Übermittlungs-ID** , und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="91264-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="91264-157">**Sender**</span><span class="sxs-lookup"><span data-stu-id="91264-157">**Sender**</span></span>
- <span data-ttu-id="91264-158">**Betreff/URL/Dateiname**</span><span class="sxs-lookup"><span data-stu-id="91264-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="91264-159">**Eingereicht von**</span><span class="sxs-lookup"><span data-stu-id="91264-159">**Submitted by**</span></span>
- <span data-ttu-id="91264-160">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="91264-160">**Submission type**</span></span>
- <span data-ttu-id="91264-161">**Status**</span><span class="sxs-lookup"><span data-stu-id="91264-161">**Status**</span></span>

![Filter Optionen für Übermittlungen von Administratoren](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="91264-163">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle** aus.</span><span class="sxs-lookup"><span data-stu-id="91264-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="91264-164">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="91264-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="91264-165">Unter dem Diagramm befinden sich drei Registerkarten: **e-Mail** (Standard), **URL** und **Anlage**.</span><span class="sxs-lookup"><span data-stu-id="91264-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="91264-166">Anzeigen von Administrator-e-Mail-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="91264-166">View admin email submissions</span></span>

<span data-ttu-id="91264-167">Klicken Sie auf die Registerkarte **e-Mail** .</span><span class="sxs-lookup"><span data-stu-id="91264-167">Click the **Email** tab.</span></span>

<span data-ttu-id="91264-168">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="91264-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="91264-169">**Date**</span><span class="sxs-lookup"><span data-stu-id="91264-169">**Date**</span></span>
- <span data-ttu-id="91264-170">**Übermittlungs-ID**: ein GUID-Wert, der jeder Übermittlung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="91264-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="91264-171">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="91264-172">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="91264-173">**Sender**</span><span class="sxs-lookup"><span data-stu-id="91264-173">**Sender**</span></span>
- <span data-ttu-id="91264-174">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="91264-175">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="91264-175">**Submission type**</span></span>
- <span data-ttu-id="91264-176">**Zustellungs Grund**</span><span class="sxs-lookup"><span data-stu-id="91264-176">**Delivery reason**</span></span>
- <span data-ttu-id="91264-177">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="91264-178"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91264-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="91264-179">Details zur erneuten Überprüfung der Administrator Übermittlung</span><span class="sxs-lookup"><span data-stu-id="91264-179">Admin submission rescan details</span></span>

<span data-ttu-id="91264-180">Nachrichten, die in admin-Übermittlungen übermittelt werden, werden erneut gescannt, und die Ergebnisse werden im Detail-Flyout angezeigt:</span><span class="sxs-lookup"><span data-stu-id="91264-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="91264-181">Wenn ein Fehler bei der e-Mail-Authentifizierung des Absenders zum Zeitpunkt der Zustellung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="91264-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="91264-182">Informationen zu allen Richtlinien Treffern, die das Urteil einer Nachricht beeinträchtigt oder außer Kraft gesetzt haben könnten.</span><span class="sxs-lookup"><span data-stu-id="91264-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="91264-183">Aktuelle detonations Ergebnisse, um zu ermitteln, ob die in der Nachricht enthaltenen URLs oder Dateien bösartig sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="91264-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="91264-184">Feedback von Grader.</span><span class="sxs-lookup"><span data-stu-id="91264-184">Feedback from graders.</span></span>

<span data-ttu-id="91264-185">Wenn eine Außerkraftsetzung gefunden wurde, sollte der erneute Scan in einigen Minuten abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="91264-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="91264-186">Wenn kein Problem in der e-Mail-Authentifizierung vorliegt oder die Zustellung von einer Außerkraftsetzung nicht betroffen war, kann das Feedback von Grader bis zu einem Tag dauern.</span><span class="sxs-lookup"><span data-stu-id="91264-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="91264-187">Anzeigen von Administratoren-URL-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="91264-187">View admin URL submissions</span></span>

<span data-ttu-id="91264-188">Klicken Sie auf die Registerkarte **URL** .</span><span class="sxs-lookup"><span data-stu-id="91264-188">Click the **URL** tab.</span></span>

<span data-ttu-id="91264-189">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="91264-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="91264-190">**Date**</span><span class="sxs-lookup"><span data-stu-id="91264-190">**Date**</span></span>
- <span data-ttu-id="91264-191">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="91264-191">**Submission ID**</span></span>
- <span data-ttu-id="91264-192">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="91264-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="91264-194">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="91264-194">**Submission type**</span></span>
- <span data-ttu-id="91264-195">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="91264-196"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91264-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="91264-197">Anzeigen der Übermittlungen von Administrator Anlagen</span><span class="sxs-lookup"><span data-stu-id="91264-197">View admin attachment submissions</span></span>

<span data-ttu-id="91264-198">Klicken Sie auf die Registerkarte **Anlagen** .</span><span class="sxs-lookup"><span data-stu-id="91264-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="91264-199">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="91264-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="91264-200">**Date**</span><span class="sxs-lookup"><span data-stu-id="91264-200">**Date**</span></span>
- <span data-ttu-id="91264-201">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="91264-201">**Submission ID**</span></span>
- <span data-ttu-id="91264-202">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="91264-203">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="91264-204">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="91264-204">**Submission type**</span></span>
- <span data-ttu-id="91264-205">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="91264-206"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91264-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="91264-207">Anzeigen von Benutzern Übermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="91264-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="91264-208">Wenn Sie das [Add-in "Berichtsnachricht](enable-the-report-message-add-in.md)" bereitgestellt haben oder die [integrierten Berichte in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)verwendet werden, können Sie sehen, welche Benutzer auf der Registerkarte " **Benutzereingaben** " berichten.</span><span class="sxs-lookup"><span data-stu-id="91264-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="91264-209">Wechseln Sie im Security & Compliance Center zu **Threat Management** -über \> **mittlungen**.</span><span class="sxs-lookup"><span data-stu-id="91264-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="91264-210">Wählen Sie die Registerkarte **Benutzer Übermittlungen** aus, und klicken Sie dann auf **neue Übermittlung**.</span><span class="sxs-lookup"><span data-stu-id="91264-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="91264-211">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="91264-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="91264-212">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="91264-212">**Submitted on**</span></span>
- <span data-ttu-id="91264-213">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="91264-214">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="91264-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="91264-215">**Sender**</span></span>
- <span data-ttu-id="91264-216">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="91264-217">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="91264-217">**Submission type**</span></span>

<span data-ttu-id="91264-218"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91264-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="91264-219">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Absender** filtern, indem Sie einen Wert in das Feld eingeben und auf ![ Aktualisieren klicken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="91264-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="91264-220">Update</span><span class="sxs-lookup"><span data-stu-id="91264-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="91264-221">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Absender** , und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="91264-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="91264-222">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="91264-222">**Sender domain**</span></span>
- <span data-ttu-id="91264-223">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="91264-223">**Subject**</span></span>
- <span data-ttu-id="91264-224">**Eingereicht von**</span><span class="sxs-lookup"><span data-stu-id="91264-224">**Submitted by**</span></span>
- <span data-ttu-id="91264-225">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="91264-225">**Submission type**</span></span>
- <span data-ttu-id="91264-226">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="91264-226">**Sender IP**</span></span>

![Filter Optionen für Benutzer Übermittlungen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="91264-228">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle** aus.</span><span class="sxs-lookup"><span data-stu-id="91264-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="91264-229">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="91264-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="91264-230">Anzeigen von Benutzereingaben zum benutzerdefinierten Postfach</span><span class="sxs-lookup"><span data-stu-id="91264-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="91264-231">**Wenn** Sie [ein benutzerdefiniertes Postfach](user-submission.md) für den Empfang von gemeldeten Benutzern konfiguriert haben, können Sie Nachrichten anzeigen und auch senden, die an das Berichts Postfach übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="91264-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="91264-232">Wechseln Sie im Security & Compliance Center zu **Threat Management** -über \> **mittlungen**.</span><span class="sxs-lookup"><span data-stu-id="91264-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="91264-233">Wählen Sie die Registerkarte **benutzerdefiniertes Postfach** aus.</span><span class="sxs-lookup"><span data-stu-id="91264-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="91264-234">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="91264-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="91264-235">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="91264-235">**Submitted on**</span></span>
- <span data-ttu-id="91264-236">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="91264-237">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="91264-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="91264-238">**Sender**</span></span>
- <span data-ttu-id="91264-239">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91264-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="91264-240">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="91264-240">**Submission type**</span></span>

<span data-ttu-id="91264-241">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum eingeben und nach **abgesendet** filtern, indem Sie einen Wert in das Feld eingeben und auf ![ Aktualisieren klicken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="91264-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="91264-242">Update</span><span class="sxs-lookup"><span data-stu-id="91264-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="91264-243">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle** aus.</span><span class="sxs-lookup"><span data-stu-id="91264-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="91264-244">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="91264-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="91264-245">Benutzereingaben rückgängig machen</span><span class="sxs-lookup"><span data-stu-id="91264-245">Undo user submissions</span></span>

<span data-ttu-id="91264-246">Sobald ein Benutzer eine verdächtige e-Mail an das benutzerdefinierte Postfach übermittelt hat, haben der Benutzer und der Administrator keine Option zum Rückgängigmachen der Übermittlung.</span><span class="sxs-lookup"><span data-stu-id="91264-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="91264-247">Wenn der Benutzer die e-Mail wiederherstellen möchte, steht er für die Wiederherstellung in den Ordner "Gelöschte Elemente" oder "Junk-e-Mail" zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="91264-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="91264-248">Übermitteln von Nachrichten an Microsoft aus dem benutzerdefinierten Postfach</span><span class="sxs-lookup"><span data-stu-id="91264-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="91264-249">Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass vom Benutzer gemeldete Nachrichten abgefangen werden, ohne dass die Nachrichten an Microsoft gesendet werden, können Sie bestimmte Nachrichten zur Analyse an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="91264-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="91264-250">Dadurch wird eine Benutzer Übermittlung effektiv in eine Administrator Übermittlung verschoben.</span><span class="sxs-lookup"><span data-stu-id="91264-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="91264-251">Wählen Sie auf der Registerkarte **benutzerdefiniertes Postfach** eine Nachricht in der Liste aus, klicken Sie auf die Schaltfläche **Aktion** , und führen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="91264-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="91264-252">**Bericht säubern**</span><span class="sxs-lookup"><span data-stu-id="91264-252">**Report clean**</span></span>
- <span data-ttu-id="91264-253">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="91264-253">**Report phishing**</span></span>
- <span data-ttu-id="91264-254">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="91264-254">**Report malware**</span></span>
- <span data-ttu-id="91264-255">**Spam melden**</span><span class="sxs-lookup"><span data-stu-id="91264-255">**Report spam**</span></span>

![Optionen für die Schaltfläche "Aktion"](../../media/user-submission-custom-mailbox-action-button.png)

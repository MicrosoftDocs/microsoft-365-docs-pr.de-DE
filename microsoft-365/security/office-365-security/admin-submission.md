---
title: Übermittlungen von Administratoren
f1.keywords:
- NOCSH
ms.author: chrisda
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
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie das Übermittlungen-Portal im Security & Compliance Center verwenden, um verdächtige e-Mails, verdächtige Phishing-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und Dateien für die Überprüfung an Microsoft zu übermitteln.
ms.openlocfilehash: 1b3715e3ed6f0472d9202573ff0cab92f7240ffa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845966"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="6da76-103">Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="6da76-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="6da76-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online können Administratoren das Übermittlungen-Portal im Security & Compliance Center verwenden, um e-Mail-Nachrichten, URLs und Anlagen für die Überprüfung an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="6da76-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="6da76-105">Wenn Sie eine e-Mail übermitteln, erhalten Sie Informationen zu allen Richtlinien, die möglicherweise die eingehenden e-Mails in ihren Mandanten zugelassen haben, sowie über die Untersuchung von URLs und Anlagen in der e-Mail.</span><span class="sxs-lookup"><span data-stu-id="6da76-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="6da76-106">Richtlinien, die möglicherweise eine e-Mail erlaubt haben, enthalten die Liste sicherer Absender eines einzelnen Benutzers sowie Richtlinien auf Mandantenebene wie Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln).</span><span class="sxs-lookup"><span data-stu-id="6da76-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="6da76-107">Weitere Möglichkeiten zum Übermitteln von e-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="6da76-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6da76-108">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="6da76-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6da76-109">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="6da76-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6da76-110">Wenn Sie direkt zur **Übermittlungs** Seite wechseln möchten, verwenden Sie <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="6da76-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="6da76-111">Bevor Sie die in diesem Artikel besprochenen Verfahren ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="6da76-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="6da76-112">Um Nachrichten und Dateien an Microsoft zu übermitteln, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="6da76-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="6da76-113">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6da76-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="6da76-114">**Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="6da76-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="6da76-115">Für den schreibgeschützten Zugriff auf das Übermittlungen-Portal müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="6da76-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="6da76-116">**Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6da76-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="6da76-117">**Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="6da76-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="6da76-118">Weitere Informationen darüber, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="6da76-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="6da76-119">Verdächtigen Inhalt an Microsoft melden</span><span class="sxs-lookup"><span data-stu-id="6da76-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="6da76-120">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> -über **mittlungen**, stellen Sie sicher, dass Sie sich auf der Registerkarte Admin-über **mittlungen** befinden, und klicken Sie dann auf **neue Übermittlung**.</span><span class="sxs-lookup"><span data-stu-id="6da76-120">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="6da76-121">Verwenden Sie das **neue Übermittlungs** Flyout, das angezeigt wird, um die Nachricht, die URL oder Anlage zu übermitteln, wie in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6da76-121">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="6da76-122">Senden einer fragwürdigen e-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="6da76-122">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="6da76-123">Wählen Sie im Abschnitt **Objekttyp** die Option **e-Mail**aus.</span><span class="sxs-lookup"><span data-stu-id="6da76-123">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="6da76-124">Verwenden Sie im Abschnitt **Übermittlungs Format** eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="6da76-124">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="6da76-125">**Netzwerknachrichten-ID**: Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-ID** -Header in der Nachricht zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="6da76-125">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="6da76-126">**Datei**: Klicken Sie auf **Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="6da76-126">**File**: Click **Choose file**.</span></span> <span data-ttu-id="6da76-127">Suchen Sie in dem Dialogfeld, das geöffnet wird, nach der EML-oder msg-Datei, und wählen Sie Sie aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="6da76-127">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="6da76-128">Geben Sie im Abschnitt **Empfänger** einen oder mehrere Empfänger an, für die Sie eine Richtlinienüberprüfung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="6da76-128">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="6da76-129">Durch die Richtlinienüberprüfung wird ermittelt, ob die e-Mail-Überprüfung aufgrund von Benutzer-oder Organisationsrichtlinien umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="6da76-129">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="6da76-130">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="6da76-130">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="6da76-131">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="6da76-131">**Should not have been blocked**</span></span>

   - <span data-ttu-id="6da76-132">**Sollte blockiert worden sein**: Wählen Sie **Spam**, **Phishing**oder **Schadsoftware**aus.</span><span class="sxs-lookup"><span data-stu-id="6da76-132">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="6da76-133">Wenn Sie nicht sicher sind, verwenden Sie Ihr Bestes Urteil.</span><span class="sxs-lookup"><span data-stu-id="6da76-133">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="6da76-134">Wenn der Filter aufgrund von Richtlinien bei der Übermittlung umgangen wurde, werden Informationen zu dieser Richtlinie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6da76-134">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="6da76-135">Wenn der Filter aufgrund einer oder mehrerer Richtlinien nicht umgangen wurde, wird die Überprüfung in einigen Minuten abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6da76-135">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="6da76-136">Sie erhalten zusätzliche Informationen über die Übermittlung, indem Sie auf den Link Status klicken.</span><span class="sxs-lookup"><span data-stu-id="6da76-136">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="6da76-137">Dies beinhaltet die Ergebnisse der Richtlinienüberprüfung und das Ergebnis der erneuten Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="6da76-137">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="6da76-138">Hinweis Dadurch wird die e-Mail-Nachricht nicht über den Office 365 ATP-voll Filter Stapel erneut ausgeführt, es wird jedoch ein partieller erneuter Scan auf der Grundlage bestimmter Attribute der e-Mail, der URL oder der Datei ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6da76-138">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="6da76-139">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="6da76-139">When you're finished, click the **Submit** button.</span></span>

![URL-Übermittlungs Beispiel](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="6da76-141">Senden einer verdächtigen URL an Microsoft</span><span class="sxs-lookup"><span data-stu-id="6da76-141">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="6da76-142">Wählen Sie im Abschnitt **Objekttyp** die Option **URL**aus.</span><span class="sxs-lookup"><span data-stu-id="6da76-142">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="6da76-143">Geben Sie in das Feld, das angezeigt wird, die vollständige URL ein (beispielsweise <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="6da76-143">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="6da76-144">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="6da76-144">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="6da76-145">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="6da76-145">**Should not have been blocked**</span></span>

   - <span data-ttu-id="6da76-146">**Sollte blockiert worden sein**: Wählen Sie **Phishing** oder **Schadsoftware**aus.</span><span class="sxs-lookup"><span data-stu-id="6da76-146">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="6da76-147">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="6da76-147">When you're finished, click the **Submit** button.</span></span>

![Beispiel für eine e-Mail-Übermittlung](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="6da76-149">Übermitteln einer vermuteten Datei an Microsoft</span><span class="sxs-lookup"><span data-stu-id="6da76-149">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="6da76-150">Wählen Sie im Abschnitt **Objekttyp** die Option **Anlage**aus.</span><span class="sxs-lookup"><span data-stu-id="6da76-150">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="6da76-151">Klicken Sie auf **Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="6da76-151">Click **Choose File**.</span></span> <span data-ttu-id="6da76-152">Suchen und wählen Sie im daraufhin geöffneten Dialogfeld die Datei aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="6da76-152">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="6da76-153">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="6da76-153">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="6da76-154">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="6da76-154">**Should not have been blocked**</span></span>

   - <span data-ttu-id="6da76-155">**Sollte blockiert worden sein**: **Schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt..</span><span class="sxs-lookup"><span data-stu-id="6da76-155">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="6da76-156">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="6da76-156">When you're finished, click the **Submit** button.</span></span>

![Beispiel für Anlagen Übermittlung](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="6da76-158">Anzeigen von Übermittlungen von Administratoren</span><span class="sxs-lookup"><span data-stu-id="6da76-158">View admin submissions</span></span>

<span data-ttu-id="6da76-159">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> -über **mittlungen**, stellen Sie sicher, dass Sie sich auf der Registerkarte Admin-über **mittlungen** befinden, und klicken Sie dann auf **neue Übermittlung**.</span><span class="sxs-lookup"><span data-stu-id="6da76-159">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="6da76-160">Oben auf der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Übermittlungs-ID** (ein GUID-Wert, der jeder Übermittlung zugewiesen ist) filtern, indem Sie einen Wert in das Feld eingeben und auf Aktualisieren klicken ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="6da76-160">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="6da76-161">Update</span><span class="sxs-lookup"><span data-stu-id="6da76-161">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="6da76-162">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Übermittlungs-ID** , und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="6da76-162">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="6da76-163">**Sender**</span><span class="sxs-lookup"><span data-stu-id="6da76-163">**Sender**</span></span>
- <span data-ttu-id="6da76-164">**Betreff/URL/Dateiname**</span><span class="sxs-lookup"><span data-stu-id="6da76-164">**Subject/URL/File name**</span></span>
- <span data-ttu-id="6da76-165">**Eingereicht von**</span><span class="sxs-lookup"><span data-stu-id="6da76-165">**Submitted by**</span></span>
- <span data-ttu-id="6da76-166">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="6da76-166">**Submission type**</span></span>
- <span data-ttu-id="6da76-167">**Status**</span><span class="sxs-lookup"><span data-stu-id="6da76-167">**Status**</span></span>

![Filter Optionen für Übermittlungen von Administratoren](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="6da76-169">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle**aus.</span><span class="sxs-lookup"><span data-stu-id="6da76-169">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="6da76-170">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="6da76-170">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="6da76-171">Unter dem Diagramm befinden sich drei Registerkarten: **e-Mail** (Standard), **URL**und **Anlage**.</span><span class="sxs-lookup"><span data-stu-id="6da76-171">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="6da76-172">Anzeigen von Administrator-e-Mail-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="6da76-172">View admin email submissions</span></span>

<span data-ttu-id="6da76-173">Klicken Sie auf die Registerkarte **e-Mail** .</span><span class="sxs-lookup"><span data-stu-id="6da76-173">Click the **Email** tab.</span></span>

<span data-ttu-id="6da76-174">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="6da76-174">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6da76-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="6da76-175">**Date**</span></span>
- <span data-ttu-id="6da76-176">**Übermittlungs-ID**: ein GUID-Wert, der jeder Übermittlung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="6da76-176">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="6da76-177">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-177">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6da76-178">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-178">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="6da76-179">**Sender**</span><span class="sxs-lookup"><span data-stu-id="6da76-179">**Sender**</span></span>
- <span data-ttu-id="6da76-180">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-180">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="6da76-181">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="6da76-181">**Submission type**</span></span>
- <span data-ttu-id="6da76-182">**Zustellungs Grund**</span><span class="sxs-lookup"><span data-stu-id="6da76-182">**Delivery reason**</span></span>
- <span data-ttu-id="6da76-183">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-183">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="6da76-184">**Steuerelementtyp**</span><span class="sxs-lookup"><span data-stu-id="6da76-184">**Control type**</span></span>
- <span data-ttu-id="6da76-185">**Steuerelementquelle**</span><span class="sxs-lookup"><span data-stu-id="6da76-185">**Control source**</span></span>

  <span data-ttu-id="6da76-186"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6da76-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="6da76-187">Anzeigen von Administratoren-URL-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="6da76-187">View admin URL submissions</span></span>

<span data-ttu-id="6da76-188">Klicken Sie auf die Registerkarte **URL** .</span><span class="sxs-lookup"><span data-stu-id="6da76-188">Click the **URL** tab.</span></span>

<span data-ttu-id="6da76-189">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="6da76-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6da76-190">**Date**</span><span class="sxs-lookup"><span data-stu-id="6da76-190">**Date**</span></span>
- <span data-ttu-id="6da76-191">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="6da76-191">**Submission ID**</span></span>
- <span data-ttu-id="6da76-192">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6da76-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="6da76-194">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="6da76-194">**Submission type**</span></span>
- <span data-ttu-id="6da76-195">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="6da76-196"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6da76-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="6da76-197">Anzeigen der Übermittlungen von Administrator Anlagen</span><span class="sxs-lookup"><span data-stu-id="6da76-197">View admin attachment submissions</span></span>

<span data-ttu-id="6da76-198">Klicken Sie auf die Registerkarte **Anlagen** .</span><span class="sxs-lookup"><span data-stu-id="6da76-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="6da76-199">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="6da76-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6da76-200">**Date**</span><span class="sxs-lookup"><span data-stu-id="6da76-200">**Date**</span></span>
- <span data-ttu-id="6da76-201">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="6da76-201">**Submission ID**</span></span>
- <span data-ttu-id="6da76-202">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6da76-203">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="6da76-204">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="6da76-204">**Submission type**</span></span>
- <span data-ttu-id="6da76-205">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="6da76-206"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6da76-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="6da76-207">Anzeigen von Benutzern Übermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="6da76-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="6da76-208">Wenn Sie das [Add-in "Berichtsnachricht](enable-the-report-message-add-in.md)" bereitgestellt haben oder die [integrierten Berichte in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)verwendet werden, können Sie sehen, welche Benutzer auf der Registerkarte " **Benutzereingaben** " berichten.</span><span class="sxs-lookup"><span data-stu-id="6da76-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="6da76-209">Wechseln Sie im Security & Compliance Center zu **Threat Management** -über \> **mittlungen**.</span><span class="sxs-lookup"><span data-stu-id="6da76-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="6da76-210">Wählen Sie die Registerkarte **Benutzer Übermittlungen** aus, und klicken Sie dann auf **neue Übermittlung**.</span><span class="sxs-lookup"><span data-stu-id="6da76-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="6da76-211">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="6da76-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6da76-212">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="6da76-212">**Submitted on**</span></span>
- <span data-ttu-id="6da76-213">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6da76-214">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="6da76-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="6da76-215">**Sender**</span></span>
- <span data-ttu-id="6da76-216">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="6da76-217">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="6da76-217">**Submission type**</span></span>

<span data-ttu-id="6da76-218"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6da76-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="6da76-219">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Absender** filtern, indem Sie einen Wert in das Feld eingeben und auf ![ Aktualisieren klicken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="6da76-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="6da76-220">Update</span><span class="sxs-lookup"><span data-stu-id="6da76-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="6da76-221">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Absender** , und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="6da76-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="6da76-222">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="6da76-222">**Sender domain**</span></span>
- <span data-ttu-id="6da76-223">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="6da76-223">**Subject**</span></span>
- <span data-ttu-id="6da76-224">**Eingereicht von**</span><span class="sxs-lookup"><span data-stu-id="6da76-224">**Submitted by**</span></span>
- <span data-ttu-id="6da76-225">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="6da76-225">**Submission type**</span></span>
- <span data-ttu-id="6da76-226">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="6da76-226">**Sender IP**</span></span>

![Filter Optionen für Benutzer Übermittlungen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="6da76-228">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle**aus.</span><span class="sxs-lookup"><span data-stu-id="6da76-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="6da76-229">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="6da76-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="6da76-230">Anzeigen von Benutzereingaben zum benutzerdefinierten Postfach</span><span class="sxs-lookup"><span data-stu-id="6da76-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="6da76-231">Wenn Sie [ein benutzerdefiniertes Postfach](user-submission.md) für den Empfang von gemeldeten Benutzern konfiguriert haben, können Sie Nachrichten anzeigen und auch senden, die an das Berichts Postfach übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="6da76-231">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="6da76-232">Wechseln Sie im Security & Compliance Center zu **Threat Management** -über \> **mittlungen**.</span><span class="sxs-lookup"><span data-stu-id="6da76-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="6da76-233">Wählen Sie die Registerkarte **benutzerdefiniertes Postfach** aus.</span><span class="sxs-lookup"><span data-stu-id="6da76-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="6da76-234">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="6da76-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6da76-235">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="6da76-235">**Submitted on**</span></span>
- <span data-ttu-id="6da76-236">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6da76-237">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="6da76-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="6da76-238">**Sender**</span></span>
- <span data-ttu-id="6da76-239">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da76-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="6da76-240">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="6da76-240">**Submission type**</span></span>

<span data-ttu-id="6da76-241">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum eingeben und nach **abgesendet** filtern, indem Sie einen Wert in das Feld eingeben und auf ![ Aktualisieren klicken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="6da76-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="6da76-242">Update</span><span class="sxs-lookup"><span data-stu-id="6da76-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="6da76-243">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle**aus.</span><span class="sxs-lookup"><span data-stu-id="6da76-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="6da76-244">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="6da76-244">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="6da76-245">Übermitteln von Nachrichten an Microsoft aus dem benutzerdefinierten Postfach</span><span class="sxs-lookup"><span data-stu-id="6da76-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="6da76-246">Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass vom Benutzer gemeldete Nachrichten abgefangen werden, ohne dass die Nachrichten an Microsoft gesendet werden, können Sie bestimmte Nachrichten zur Analyse an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="6da76-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="6da76-247">Dadurch wird eine Benutzer Übermittlung effektiv in eine Administrator Übermittlung verschoben.</span><span class="sxs-lookup"><span data-stu-id="6da76-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="6da76-248">Wählen Sie auf der Registerkarte **benutzerdefiniertes Postfach** eine Nachricht in der Liste aus, klicken Sie auf die Schaltfläche **Aktion** , und führen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="6da76-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="6da76-249">**Bericht säubern**</span><span class="sxs-lookup"><span data-stu-id="6da76-249">**Report clean**</span></span>
- <span data-ttu-id="6da76-250">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="6da76-250">**Report phishing**</span></span>
- <span data-ttu-id="6da76-251">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="6da76-251">**Report malware**</span></span>
- <span data-ttu-id="6da76-252">**Spam melden**</span><span class="sxs-lookup"><span data-stu-id="6da76-252">**Report spam**</span></span>

![Optionen für die Schaltfläche "Aktion"](../../media/user-submission-custom-mailbox-action-button.png)

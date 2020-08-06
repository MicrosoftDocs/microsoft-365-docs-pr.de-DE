---
title: Übermittlungen von Administratoren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie das Übermittlungen-Portal im Security & Compliance Center verwenden, um verdächtige e-Mails, verdächtige Phishing-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und Dateien für die Überprüfung an Microsoft zu übermitteln.
ms.openlocfilehash: 4d0737d881334db9cc4aeda43037ab89d7444618
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577870"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="8dfd9-103">Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="8dfd9-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="8dfd9-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online können Administratoren das Übermittlungen-Portal im Security & Compliance Center verwenden, um e-Mail-Nachrichten, URLs und Anlagen für die Überprüfung an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="8dfd9-105">Wenn Sie eine e-Mail übermitteln, erhalten Sie Informationen zu allen Richtlinien, die möglicherweise die eingehenden e-Mails in ihren Mandanten zugelassen haben, sowie über die Untersuchung von URLs und Anlagen in der e-Mail.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="8dfd9-106">Richtlinien, die möglicherweise eine e-Mail erlaubt haben, enthalten die Liste sicherer Absender eines einzelnen Benutzers sowie Richtlinien auf Mandantenebene wie Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln).</span><span class="sxs-lookup"><span data-stu-id="8dfd9-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="8dfd9-107">Weitere Möglichkeiten zum Übermitteln von e-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="8dfd9-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8dfd9-108">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="8dfd9-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8dfd9-109">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8dfd9-110">Wenn Sie direkt zur **Übermittlungs** Seite wechseln möchten, verwenden Sie <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="8dfd9-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="8dfd9-111">Bevor Sie die in diesem Artikel besprochenen Verfahren ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="8dfd9-112">Um Nachrichten und Dateien an Microsoft zu übermitteln, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="8dfd9-113">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8dfd9-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="8dfd9-114">**Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="8dfd9-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="8dfd9-115">Für den schreibgeschützten Zugriff auf das Übermittlungen-Portal müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="8dfd9-116">**Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8dfd9-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="8dfd9-117">**Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="8dfd9-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="8dfd9-118">Weitere Informationen darüber, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="8dfd9-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="8dfd9-119">Verdächtigen Inhalt an Microsoft melden</span><span class="sxs-lookup"><span data-stu-id="8dfd9-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="8dfd9-120">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Review** \> **Administrator Submission Messages**.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-120">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="8dfd9-121">Klicken Sie auf der angezeigten Seite über **mittlungen** auf die Schaltfläche **neue Übermittlung** .</span><span class="sxs-lookup"><span data-stu-id="8dfd9-121">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="8dfd9-122">Verwenden Sie das **neue Übermittlungs** Flyout, das angezeigt wird, um die Nachricht, die URL oder Anlage zu übermitteln, wie in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-122">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="8dfd9-123">Senden einer fragwürdigen e-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="8dfd9-123">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="8dfd9-124">Wählen Sie im Abschnitt **Objekttyp** die Option **e-Mail**aus.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-124">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="8dfd9-125">Verwenden Sie im Abschnitt **Übermittlungs Format** eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-125">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="8dfd9-126">**Netzwerknachrichten-ID**: Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-ID** -Header in der Nachricht zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-126">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="8dfd9-127">**Datei**: Klicken Sie auf **Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-127">**File**: Click **Choose file**.</span></span> <span data-ttu-id="8dfd9-128">Suchen Sie in dem Dialogfeld, das geöffnet wird, nach der EML-oder msg-Datei, und wählen Sie Sie aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-128">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="8dfd9-129">Geben Sie im Abschnitt **Empfänger** einen oder mehrere Empfänger an, für die Sie eine Richtlinienüberprüfung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-129">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="8dfd9-130">Durch die Richtlinienüberprüfung wird ermittelt, ob die e-Mail-Überprüfung aufgrund von Benutzer-oder Organisationsrichtlinien umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-130">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="8dfd9-131">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-131">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="8dfd9-132">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-132">**Should not have been blocked**</span></span>

   - <span data-ttu-id="8dfd9-133">**Sollte blockiert worden sein**: Wählen Sie **Spam**, **Phishing**oder **Schadsoftware**aus.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-133">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="8dfd9-134">Wenn Sie nicht sicher sind, verwenden Sie Ihr Bestes Urteil.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-134">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="8dfd9-135">Wenn der Filter aufgrund von Richtlinien bei der Übermittlung umgangen wurde, werden Informationen zu dieser Richtlinie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-135">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="8dfd9-136">Wenn der Filter aufgrund einer oder mehrerer Richtlinien nicht umgangen wurde, wird die Überprüfung in einigen Minuten abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-136">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="8dfd9-137">Sie erhalten zusätzliche Informationen über die Übermittlung, indem Sie auf den Link Status klicken.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-137">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="8dfd9-138">Dies beinhaltet die Ergebnisse der Richtlinienüberprüfung und das Ergebnis der erneuten Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-138">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="8dfd9-139">Hinweis Dadurch wird die e-Mail-Nachricht nicht über den Office 365 ATP-voll Filter Stapel erneut ausgeführt, es wird jedoch ein partieller erneuter Scan auf der Grundlage bestimmter Attribute der e-Mail, der URL oder der Datei ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-139">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="8dfd9-140">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="8dfd9-140">When you're finished, click the **Submit** button.</span></span>

![URL-Übermittlungs Beispiel](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="8dfd9-142">Senden einer verdächtigen URL an Microsoft</span><span class="sxs-lookup"><span data-stu-id="8dfd9-142">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="8dfd9-143">Wählen Sie im Abschnitt **Objekttyp** die Option **URL**aus.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-143">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="8dfd9-144">Geben Sie in das Feld, das angezeigt wird, die vollständige URL ein (beispielsweise <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="8dfd9-144">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="8dfd9-145">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-145">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="8dfd9-146">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-146">**Should not have been blocked**</span></span>

   - <span data-ttu-id="8dfd9-147">**Sollte blockiert worden sein**: Wählen Sie **Phishing** oder **Schadsoftware**aus.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-147">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="8dfd9-148">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="8dfd9-148">When you're finished, click the **Submit** button.</span></span>

![Beispiel für eine e-Mail-Übermittlung](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="8dfd9-150">Übermitteln einer vermuteten Datei an Microsoft</span><span class="sxs-lookup"><span data-stu-id="8dfd9-150">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="8dfd9-151">Wählen Sie im Abschnitt **Objekttyp** die Option **Anlage**aus.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-151">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="8dfd9-152">Klicken Sie auf **Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-152">Click **Choose File**.</span></span> <span data-ttu-id="8dfd9-153">Suchen und wählen Sie im daraufhin geöffneten Dialogfeld die Datei aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-153">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="8dfd9-154">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-154">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="8dfd9-155">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-155">**Should not have been blocked**</span></span>

   - <span data-ttu-id="8dfd9-156">**Sollte blockiert worden sein**: **Schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt..</span><span class="sxs-lookup"><span data-stu-id="8dfd9-156">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="8dfd9-157">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="8dfd9-157">When you're finished, click the **Submit** button.</span></span>

![Beispiel für Anlagen Übermittlung](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="8dfd9-159">Anzeigen von Übermittlungen von Administratoren</span><span class="sxs-lookup"><span data-stu-id="8dfd9-159">View admin submissions</span></span>

1. <span data-ttu-id="8dfd9-160">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Review** \> **Administrator Submission Messages**.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-160">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="8dfd9-161">Überprüfen Sie auf der Seite über **mittlungen** , die angezeigt wird, dass die Registerkarte Admin-über **mittlungen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-161">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="8dfd9-162">Oben auf der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Übermittlungs-ID** (ein GUID-Wert, der jeder Übermittlung zugewiesen ist) filtern, indem Sie einen Wert in das Feld eingeben und auf Aktualisieren klicken ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="8dfd9-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="8dfd9-163">Update</span><span class="sxs-lookup"><span data-stu-id="8dfd9-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="8dfd9-164">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Übermittlungs-ID** , und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="8dfd9-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-165">**Sender**</span></span>
- <span data-ttu-id="8dfd9-166">**Betreff/URL/Dateiname**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="8dfd9-167">**Eingereicht von**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-167">**Submitted by**</span></span>
- <span data-ttu-id="8dfd9-168">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-168">**Submission type**</span></span>
- <span data-ttu-id="8dfd9-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-169">**Status**</span></span>

![Filter Optionen für Übermittlungen von Administratoren](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="8dfd9-171">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle**aus.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="8dfd9-172">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="8dfd9-173">Unter dem Diagramm befinden sich drei Registerkarten: **e-Mail** (Standard), **URL**und **Anlage**.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="8dfd9-174">Anzeigen von Administrator-e-Mail-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="8dfd9-174">View admin email submissions</span></span>

<span data-ttu-id="8dfd9-175">Klicken Sie auf die Registerkarte **e-Mail** .</span><span class="sxs-lookup"><span data-stu-id="8dfd9-175">Click the **Email** tab.</span></span>

<span data-ttu-id="8dfd9-176">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8dfd9-177">**Date**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-177">**Date**</span></span>
- <span data-ttu-id="8dfd9-178">**Übermittlungs-ID**: ein GUID-Wert, der jeder Übermittlung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="8dfd9-179">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8dfd9-180">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="8dfd9-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-181">**Sender**</span></span>
- <span data-ttu-id="8dfd9-182">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="8dfd9-183">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-183">**Submission type**</span></span>
- <span data-ttu-id="8dfd9-184">**Zustellungs Grund**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-184">**Delivery reason**</span></span>
- <span data-ttu-id="8dfd9-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-185">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="8dfd9-186">**Steuerelementtyp**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-186">**Control type**</span></span>
- <span data-ttu-id="8dfd9-187">**Steuerelementquelle**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-187">**Control source**</span></span>

  <span data-ttu-id="8dfd9-188"><sup>\*</sup>Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-188"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="8dfd9-189">Anzeigen von Administratoren-URL-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="8dfd9-189">View admin URL submissions</span></span>

<span data-ttu-id="8dfd9-190">Klicken Sie auf die Registerkarte **URL** .</span><span class="sxs-lookup"><span data-stu-id="8dfd9-190">Click the **URL** tab.</span></span>

<span data-ttu-id="8dfd9-191">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-191">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8dfd9-192">**Date**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-192">**Date**</span></span>
- <span data-ttu-id="8dfd9-193">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-193">**Submission ID**</span></span>
- <span data-ttu-id="8dfd9-194">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-194">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8dfd9-195">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-195">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="8dfd9-196">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-196">**Submission type**</span></span>
- <span data-ttu-id="8dfd9-197">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-197">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="8dfd9-198"><sup>\*</sup>Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-198"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="8dfd9-199">Anzeigen der Übermittlungen von Administrator Anlagen</span><span class="sxs-lookup"><span data-stu-id="8dfd9-199">View admin attachment submissions</span></span>

<span data-ttu-id="8dfd9-200">Klicken Sie auf die Registerkarte **Anlagen** .</span><span class="sxs-lookup"><span data-stu-id="8dfd9-200">Click the **Attachments** tab.</span></span>

<span data-ttu-id="8dfd9-201">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-201">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8dfd9-202">**Date**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-202">**Date**</span></span>
- <span data-ttu-id="8dfd9-203">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-203">**Submission ID**</span></span>
- <span data-ttu-id="8dfd9-204">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-204">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8dfd9-205">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-205">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="8dfd9-206">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-206">**Submission type**</span></span>
- <span data-ttu-id="8dfd9-207">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-207">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="8dfd9-208"><sup>\*</sup>Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-208"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="8dfd9-209">Anzeigen von Benutzern Übermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="8dfd9-209">View user submissions to Microsoft</span></span>

<span data-ttu-id="8dfd9-210">Wenn Sie das [Add-in "Berichtsnachricht](enable-the-report-message-add-in.md)" bereitgestellt haben oder die [integrierten Berichte in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)verwendet werden, können Sie sehen, welche Benutzer auf der Registerkarte " **Benutzereingaben** " berichten.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-210">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="8dfd9-211">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Review** \> **Administrator Submission Messages**.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-211">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="8dfd9-212">Klicken Sie auf der angezeigten Seite über **mittlungen** auf die Registerkarte **Benutzereingaben** .</span><span class="sxs-lookup"><span data-stu-id="8dfd9-212">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="8dfd9-213">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-213">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8dfd9-214">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-214">**Submitted on**</span></span>
- <span data-ttu-id="8dfd9-215">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-215">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8dfd9-216">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-216">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="8dfd9-217">**Sender**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-217">**Sender**</span></span>
- <span data-ttu-id="8dfd9-218">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-218">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="8dfd9-219">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-219">**Submission type**</span></span>

<span data-ttu-id="8dfd9-220"><sup>\*</sup>Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-220"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="8dfd9-221">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Absender** filtern, indem Sie einen Wert in das Feld eingeben und auf ![ Aktualisieren klicken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="8dfd9-221">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="8dfd9-222">Update</span><span class="sxs-lookup"><span data-stu-id="8dfd9-222">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="8dfd9-223">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Absender** , und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-223">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="8dfd9-224">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-224">**Sender domain**</span></span>
- <span data-ttu-id="8dfd9-225">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-225">**Subject**</span></span>
- <span data-ttu-id="8dfd9-226">**Eingereicht von**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-226">**Submitted by**</span></span>
- <span data-ttu-id="8dfd9-227">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-227">**Submission type**</span></span>
- <span data-ttu-id="8dfd9-228">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-228">**Sender IP**</span></span>

![Filter Optionen für Benutzer Übermittlungen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="8dfd9-230">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle**aus.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-230">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="8dfd9-231">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-231">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="8dfd9-232">Anzeigen von Benutzereingaben zum benutzerdefinierten Postfach</span><span class="sxs-lookup"><span data-stu-id="8dfd9-232">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="8dfd9-233">Wenn Sie [ein benutzerdefiniertes Postfach](user-submission.md) für den Empfang von gemeldeten Benutzern konfiguriert haben, können Sie Nachrichten anzeigen und auch senden, die an das Berichts Postfach übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-233">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="8dfd9-234">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Review** \> **Administrator Submission Messages**.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-234">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="8dfd9-235">Klicken Sie auf der angezeigten Seite über **mittlungen** auf die Registerkarte **benutzerdefiniertes Postfach** .</span><span class="sxs-lookup"><span data-stu-id="8dfd9-235">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="8dfd9-236">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-236">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8dfd9-237">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-237">**Submitted on**</span></span>
- <span data-ttu-id="8dfd9-238">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-238">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8dfd9-239">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-239">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="8dfd9-240">**Sender**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-240">**Sender**</span></span>
- <span data-ttu-id="8dfd9-241">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8dfd9-241">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="8dfd9-242">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-242">**Submission type**</span></span>

<span data-ttu-id="8dfd9-243">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum eingeben und nach **abgesendet** filtern, indem Sie einen Wert in das Feld eingeben und auf ![ Aktualisieren klicken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="8dfd9-243">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="8dfd9-244">Update</span><span class="sxs-lookup"><span data-stu-id="8dfd9-244">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="8dfd9-245">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle**aus.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-245">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="8dfd9-246">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-246">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="8dfd9-247">Übermitteln von Nachrichten an Microsoft aus dem benutzerdefinierten Postfach</span><span class="sxs-lookup"><span data-stu-id="8dfd9-247">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="8dfd9-248">Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass vom Benutzer gemeldete Nachrichten abgefangen werden, ohne dass die Nachrichten an Microsoft gesendet werden, können Sie bestimmte Nachrichten zur Analyse an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-248">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="8dfd9-249">Dadurch wird eine Benutzer Übermittlung effektiv in eine Administrator Übermittlung verschoben.</span><span class="sxs-lookup"><span data-stu-id="8dfd9-249">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="8dfd9-250">Wählen Sie auf der Registerkarte **benutzerdefiniertes Postfach** eine Nachricht in der Liste aus, klicken Sie auf die Schaltfläche **Aktion** , und führen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="8dfd9-250">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="8dfd9-251">**Bericht säubern**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-251">**Report clean**</span></span>
- <span data-ttu-id="8dfd9-252">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-252">**Report phishing**</span></span>
- <span data-ttu-id="8dfd9-253">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-253">**Report malware**</span></span>
- <span data-ttu-id="8dfd9-254">**Spam melden**</span><span class="sxs-lookup"><span data-stu-id="8dfd9-254">**Report spam**</span></span>

![Optionen für die Schaltfläche "Aktion"](../../media/user-submission-custom-mailbox-action-button.png)

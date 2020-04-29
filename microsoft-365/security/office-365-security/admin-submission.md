---
title: Admin-Übermittlungen, Übermittlungen, Spam-Problem, falsch negativ, Phishing senden, e-Mail zum Scannen senden, verdächtige e-Mails in Office 365, e-Mails scannen, Microsoft-Scan für Phishing durchführen, Microsoft für Spam überprüfen, e-Mails senden, e-Mails senden, zwielichtige e-Mails, fehlerhafte Darsteller e-Mail, verdächtige, nicht vertrauenswürdige e-Mails, Phishing-e-Mails an Microsoft melden, Phishing-e-Mails an Microsoft melden, böswillige e-Mails , melden Sie Malware in e-Mails an Microsoft, Spam-e-Mails im Posteingang, Virus in e-Mail
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
description: Hier erfahren Sie, wie Sie verdächtige e-Mails, verdächtige Phishing-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und Dateien von Ihrem Unternehmen zur Überprüfung an Microsoft übermitteln.
ms.openlocfilehash: 73c33ba1218a710c33f8b2675bc65c0a7486efda
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921507"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="15e6d-103">Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="15e6d-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="15e6d-104">Wenn Sie ein Administrator in einer Microsoft 365-Organisation mit Postfächern in Exchange Online sind, können Sie das Übermittlungen-Portal im Security & Compliance Center verwenden, um e-Mail-Nachrichten, URLs und Anlagen für die Überprüfung an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="15e6d-104">If you're an admin in a Microsoft 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="15e6d-105">Wenn Sie eine e-Mail übermitteln, erhalten Sie Informationen zu allen Richtlinien, die möglicherweise die eingehenden e-Mails in ihren Mandanten zugelassen haben, sowie über die Untersuchung von URLs und Anlagen in der e-Mail.</span><span class="sxs-lookup"><span data-stu-id="15e6d-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="15e6d-106">Richtlinien, die möglicherweise eine e-Mail erlaubt haben, enthalten die Liste sicherer Absender eines einzelnen Benutzers sowie Richtlinien auf Mandantenebene wie Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln).</span><span class="sxs-lookup"><span data-stu-id="15e6d-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="15e6d-107">Weitere Möglichkeiten zum Übermitteln von e-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="15e6d-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="15e6d-108">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="15e6d-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="15e6d-109">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="15e6d-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="15e6d-110">Wenn Sie direkt zur **Übermittlungs** Seite wechseln möchten <https://protection.office.com/reportsubmission>, verwenden Sie.</span><span class="sxs-lookup"><span data-stu-id="15e6d-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="15e6d-111">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="15e6d-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="15e6d-112">Zum Hinzufügen, ändern und Löschen von Anti-Spam-Richtlinien müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung**", " **Sicherheits Administrator**" oder " **Sicherheits Leser** " sein.</span><span class="sxs-lookup"><span data-stu-id="15e6d-112">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="15e6d-113">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="15e6d-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="15e6d-114">Weitere Informationen darüber, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="15e6d-114">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="15e6d-115">Verdächtigen Inhalt an Microsoft melden</span><span class="sxs-lookup"><span data-stu-id="15e6d-115">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="15e6d-116">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Review** \> **Administrator Submission Messages**.</span><span class="sxs-lookup"><span data-stu-id="15e6d-116">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="15e6d-117">Klicken Sie auf der angezeigten Seite über **mittlungen** auf die Schaltfläche **neue Übermittlung** .</span><span class="sxs-lookup"><span data-stu-id="15e6d-117">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="15e6d-118">Verwenden Sie das **neue Übermittlungs** Flyout, das angezeigt wird, um die Nachricht, die URL oder Anlage zu übermitteln, wie in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="15e6d-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="15e6d-119">Senden einer fragwürdigen e-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="15e6d-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="15e6d-120">Wählen Sie im Abschnitt **Objekttyp** die Option **e-Mail**aus.</span><span class="sxs-lookup"><span data-stu-id="15e6d-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="15e6d-121">Verwenden Sie im Abschnitt **Übermittlungs Format** eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="15e6d-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="15e6d-122">**Netzwerknachrichten-ID**: Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-ID** -Header in der Nachricht zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="15e6d-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="15e6d-123">**Datei**: Klicken Sie auf **Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="15e6d-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="15e6d-124">Suchen Sie in dem Dialogfeld, das geöffnet wird, nach der EML-oder msg-Datei, und wählen Sie Sie aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="15e6d-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="15e6d-125">Geben Sie im Abschnitt **Empfänger** einen oder mehrere Empfänger an, für die Sie eine Richtlinienüberprüfung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="15e6d-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="15e6d-126">Durch die Richtlinienüberprüfung wird ermittelt, ob die e-Mail-Überprüfung aufgrund von Benutzer-oder Organisationsrichtlinien umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="15e6d-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="15e6d-127">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="15e6d-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="15e6d-128">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="15e6d-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="15e6d-129">**Sollte blockiert worden sein**: Wählen Sie **Spam**, **Phishing**oder **Schadsoftware**aus.</span><span class="sxs-lookup"><span data-stu-id="15e6d-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="15e6d-130">Wenn Sie nicht sicher sind, verwenden Sie Ihr Bestes Urteil.</span><span class="sxs-lookup"><span data-stu-id="15e6d-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="15e6d-131">Wenn der Filter aufgrund von Richtlinien bei der Übermittlung umgangen wurde, werden Informationen zu dieser Richtlinie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15e6d-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="15e6d-132">Wenn der Filter aufgrund einer oder mehrerer Richtlinien nicht umgangen wurde, wird die Überprüfung in einigen Minuten abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="15e6d-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="15e6d-133">Sie erhalten zusätzliche Informationen über die Übermittlung, indem Sie auf den Link Status klicken.</span><span class="sxs-lookup"><span data-stu-id="15e6d-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="15e6d-134">Dies beinhaltet die Ergebnisse der Richtlinienüberprüfung und das Ergebnis der erneuten Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="15e6d-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="15e6d-135">Hinweis Dadurch wird die e-Mail-Nachricht nicht über den Office 365 ATP-voll Filter Stapel erneut ausgeführt, es wird jedoch ein partieller erneuter Scan auf der Grundlage bestimmter Attribute der e-Mail, der URL oder der Datei ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="15e6d-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="15e6d-136">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="15e6d-136">When you're finished, click the **Submit** button.</span></span>

![URL-Übermittlungs Beispiel](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="15e6d-138">Senden einer verdächtigen URL an Microsoft</span><span class="sxs-lookup"><span data-stu-id="15e6d-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="15e6d-139">Wählen Sie im Abschnitt **Objekttyp** die Option **URL**aus.</span><span class="sxs-lookup"><span data-stu-id="15e6d-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="15e6d-140">Geben Sie in das Feld, das angezeigt wird, die vollständige URL <https://www.fabrikam.com/marketing.html>ein (beispielsweise).</span><span class="sxs-lookup"><span data-stu-id="15e6d-140">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="15e6d-141">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="15e6d-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="15e6d-142">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="15e6d-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="15e6d-143">**Sollte blockiert worden sein**: Wählen Sie **Phishing** oder **Schadsoftware**aus.</span><span class="sxs-lookup"><span data-stu-id="15e6d-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="15e6d-144">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="15e6d-144">When you're finished, click the **Submit** button.</span></span>

![Beispiel für eine e-Mail-Übermittlung](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="15e6d-146">Übermitteln einer vermuteten Datei an Microsoft</span><span class="sxs-lookup"><span data-stu-id="15e6d-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="15e6d-147">Wählen Sie im Abschnitt **Objekttyp** die Option **Anlage**aus.</span><span class="sxs-lookup"><span data-stu-id="15e6d-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="15e6d-148">Klicken Sie auf **Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="15e6d-148">Click **Choose File**.</span></span> <span data-ttu-id="15e6d-149">Suchen und wählen Sie im daraufhin geöffneten Dialogfeld die Datei aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="15e6d-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="15e6d-150">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="15e6d-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="15e6d-151">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="15e6d-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="15e6d-152">**Sollte blockiert worden sein**: **Schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt..</span><span class="sxs-lookup"><span data-stu-id="15e6d-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="15e6d-153">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="15e6d-153">When you're finished, click the **Submit** button.</span></span>

![Beispiel für Anlagen Übermittlung](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="15e6d-155">Anzeigen von Übermittlungen von Administratoren</span><span class="sxs-lookup"><span data-stu-id="15e6d-155">View admin submissions</span></span>

1. <span data-ttu-id="15e6d-156">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Review** \> **Administrator Submission Messages**.</span><span class="sxs-lookup"><span data-stu-id="15e6d-156">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="15e6d-157">Überprüfen Sie auf der Seite über **mittlungen** , die angezeigt wird, dass die Registerkarte Admin-über **mittlungen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="15e6d-157">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="15e6d-158">Oben auf der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Übermittlungs-ID** filtern, indem Sie einen Wert in das Feld eingeben und auf Aktualisieren klicken ![](../../media/scc-quarantine-refresh.png).</span><span class="sxs-lookup"><span data-stu-id="15e6d-158">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="15e6d-159">Update</span><span class="sxs-lookup"><span data-stu-id="15e6d-159">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="15e6d-160">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Übermittlungs-ID** , und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="15e6d-160">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="15e6d-161">**Sender**</span><span class="sxs-lookup"><span data-stu-id="15e6d-161">**Sender**</span></span>
- <span data-ttu-id="15e6d-162">**Betreff/URL/Dateiname**</span><span class="sxs-lookup"><span data-stu-id="15e6d-162">**Subject/URL/File name**</span></span>
- <span data-ttu-id="15e6d-163">**Eingereicht von**</span><span class="sxs-lookup"><span data-stu-id="15e6d-163">**Submitted by**</span></span>
- <span data-ttu-id="15e6d-164">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="15e6d-164">**Submission type**</span></span>
- <span data-ttu-id="15e6d-165">**Status**</span><span class="sxs-lookup"><span data-stu-id="15e6d-165">**Status**</span></span>

![Filter Optionen für Übermittlungen von Administratoren](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="15e6d-167">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle**aus.</span><span class="sxs-lookup"><span data-stu-id="15e6d-167">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="15e6d-168">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="15e6d-168">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="15e6d-169">Unter dem Diagramm befinden sich drei Registerkarten: **e-Mail** (Standard), **URL**und **Anlage**.</span><span class="sxs-lookup"><span data-stu-id="15e6d-169">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="15e6d-170">Anzeigen von Administrator-e-Mail-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="15e6d-170">View admin email submissions</span></span>

<span data-ttu-id="15e6d-171">Klicken Sie auf die Registerkarte **e-Mail** .</span><span class="sxs-lookup"><span data-stu-id="15e6d-171">Click the **Email** tab.</span></span>

<span data-ttu-id="15e6d-172">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="15e6d-172">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="15e6d-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="15e6d-173">**Date**</span></span>
- <span data-ttu-id="15e6d-174">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="15e6d-174">**Submission ID**</span></span>
- <span data-ttu-id="15e6d-175">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-175">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="15e6d-176">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-176">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="15e6d-177">**Sender**</span><span class="sxs-lookup"><span data-stu-id="15e6d-177">**Sender**</span></span>
- <span data-ttu-id="15e6d-178">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-178">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="15e6d-179">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="15e6d-179">**Submission type**</span></span>
- <span data-ttu-id="15e6d-180">**Zustellungs Grund**</span><span class="sxs-lookup"><span data-stu-id="15e6d-180">**Delivery reason**</span></span>
- <span data-ttu-id="15e6d-181">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-181">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="15e6d-182">**Steuerelementtyp**</span><span class="sxs-lookup"><span data-stu-id="15e6d-182">**Control type**</span></span>
- <span data-ttu-id="15e6d-183">**Steuerelementquelle**</span><span class="sxs-lookup"><span data-stu-id="15e6d-183">**Control source**</span></span>

  <span data-ttu-id="15e6d-184"><sup>\*</sup>Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15e6d-184"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="15e6d-185">Anzeigen von Administratoren-URL-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="15e6d-185">View admin URL submissions</span></span>

<span data-ttu-id="15e6d-186">Klicken Sie auf die Registerkarte **URL** .</span><span class="sxs-lookup"><span data-stu-id="15e6d-186">Click the **URL** tab.</span></span>

<span data-ttu-id="15e6d-187">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="15e6d-187">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="15e6d-188">**Date**</span><span class="sxs-lookup"><span data-stu-id="15e6d-188">**Date**</span></span>
- <span data-ttu-id="15e6d-189">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="15e6d-189">**Submission ID**</span></span>
- <span data-ttu-id="15e6d-190">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-190">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="15e6d-191">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-191">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="15e6d-192">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="15e6d-192">**Submission type**</span></span>
- <span data-ttu-id="15e6d-193">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-193">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="15e6d-194"><sup>\*</sup>Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15e6d-194"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="15e6d-195">Anzeigen der Übermittlungen von Administrator Anlagen</span><span class="sxs-lookup"><span data-stu-id="15e6d-195">View admin attachment submissions</span></span>

<span data-ttu-id="15e6d-196">Klicken Sie auf die Registerkarte **Anlagen** .</span><span class="sxs-lookup"><span data-stu-id="15e6d-196">Click the **Attachments** tab.</span></span>

<span data-ttu-id="15e6d-197">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="15e6d-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="15e6d-198">**Date**</span><span class="sxs-lookup"><span data-stu-id="15e6d-198">**Date**</span></span>
- <span data-ttu-id="15e6d-199">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="15e6d-199">**Submission ID**</span></span>
- <span data-ttu-id="15e6d-200">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="15e6d-201">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-201">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="15e6d-202">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="15e6d-202">**Submission type**</span></span>
- <span data-ttu-id="15e6d-203">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="15e6d-204"><sup>\*</sup>Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15e6d-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="15e6d-205">Anzeigen von Benutzern Übermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="15e6d-205">View user submissions to Microsoft</span></span>

<span data-ttu-id="15e6d-206">Wenn Sie das [Add-in "Berichtsnachricht](enable-the-report-message-add-in.md)" bereitgestellt haben oder die [integrierten Berichte in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)verwendet werden, können Sie sehen, welche Benutzer auf der Registerkarte " **Benutzereingaben** " berichten.</span><span class="sxs-lookup"><span data-stu-id="15e6d-206">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="15e6d-207">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Review** \> **Administrator Submission Messages**.</span><span class="sxs-lookup"><span data-stu-id="15e6d-207">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="15e6d-208">Klicken Sie auf der angezeigten Seite über **mittlungen** auf die Registerkarte **Benutzereingaben** .</span><span class="sxs-lookup"><span data-stu-id="15e6d-208">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="15e6d-209">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="15e6d-209">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="15e6d-210">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="15e6d-210">**Submitted on**</span></span>
- <span data-ttu-id="15e6d-211">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-211">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="15e6d-212">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-212">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="15e6d-213">**Sender**</span><span class="sxs-lookup"><span data-stu-id="15e6d-213">**Sender**</span></span>
- <span data-ttu-id="15e6d-214">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-214">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="15e6d-215">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="15e6d-215">**Submission type**</span></span>

<span data-ttu-id="15e6d-216"><sup>\*</sup>Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15e6d-216"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="15e6d-217">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Absender** filtern, indem Sie einen Wert in das Feld eingeben und auf Aktualisieren klicken ![](../../media/scc-quarantine-refresh.png).</span><span class="sxs-lookup"><span data-stu-id="15e6d-217">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="15e6d-218">Update</span><span class="sxs-lookup"><span data-stu-id="15e6d-218">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="15e6d-219">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Absender** , und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="15e6d-219">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="15e6d-220">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="15e6d-220">**Sender domain**</span></span>
- <span data-ttu-id="15e6d-221">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="15e6d-221">**Subject**</span></span>
- <span data-ttu-id="15e6d-222">**Eingereicht von**</span><span class="sxs-lookup"><span data-stu-id="15e6d-222">**Submitted by**</span></span>
- <span data-ttu-id="15e6d-223">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="15e6d-223">**Submission type**</span></span>
- <span data-ttu-id="15e6d-224">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="15e6d-224">**Sender IP**</span></span>

![Filter Optionen für Benutzer Übermittlungen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="15e6d-226">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle**aus.</span><span class="sxs-lookup"><span data-stu-id="15e6d-226">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="15e6d-227">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="15e6d-227">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="15e6d-228">Anzeigen von Benutzereingaben zum benutzerdefinierten Postfach</span><span class="sxs-lookup"><span data-stu-id="15e6d-228">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="15e6d-229">Wenn Sie [ein benutzerdefiniertes Postfach](user-submission.md) für den Empfang von gemeldeten Benutzern konfiguriert haben, können Sie Nachrichten anzeigen und auch senden, die an das Berichts Postfach übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="15e6d-229">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="15e6d-230">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Review** \> **Administrator Submission Messages**.</span><span class="sxs-lookup"><span data-stu-id="15e6d-230">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="15e6d-231">Klicken Sie auf der angezeigten Seite über **mittlungen** auf die Registerkarte **benutzerdefiniertes Postfach** .</span><span class="sxs-lookup"><span data-stu-id="15e6d-231">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="15e6d-232">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="15e6d-232">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="15e6d-233">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="15e6d-233">**Submitted on**</span></span>
- <span data-ttu-id="15e6d-234">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-234">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="15e6d-235">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-235">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="15e6d-236">**Sender**</span><span class="sxs-lookup"><span data-stu-id="15e6d-236">**Sender**</span></span>
- <span data-ttu-id="15e6d-237">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15e6d-237">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="15e6d-238">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="15e6d-238">**Submission type**</span></span>

<span data-ttu-id="15e6d-239">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum eingeben und nach **abgesendet** filtern, indem Sie einen Wert in das Feld eingeben und auf Aktualisieren klicken ![](../../media/scc-quarantine-refresh.png).</span><span class="sxs-lookup"><span data-stu-id="15e6d-239">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="15e6d-240">Update</span><span class="sxs-lookup"><span data-stu-id="15e6d-240">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="15e6d-241">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle**aus.</span><span class="sxs-lookup"><span data-stu-id="15e6d-241">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="15e6d-242">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="15e6d-242">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="15e6d-243">Übermitteln von Nachrichten an Microsoft aus dem benutzerdefinierten Postfach</span><span class="sxs-lookup"><span data-stu-id="15e6d-243">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="15e6d-244">Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass vom Benutzer gemeldete Nachrichten abgefangen werden, ohne dass die Nachrichten an Microsoft gesendet werden, können Sie bestimmte Nachrichten zur Analyse an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="15e6d-244">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="15e6d-245">Dadurch wird eine Benutzer Übermittlung effektiv in eine Administrator Übermittlung verschoben.</span><span class="sxs-lookup"><span data-stu-id="15e6d-245">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="15e6d-246">Wählen Sie auf der Registerkarte **benutzerdefiniertes Postfach** eine Nachricht in der Liste aus, klicken Sie auf die Schaltfläche **Aktion** , und führen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="15e6d-246">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="15e6d-247">**Bericht säubern**</span><span class="sxs-lookup"><span data-stu-id="15e6d-247">**Report clean**</span></span>
- <span data-ttu-id="15e6d-248">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="15e6d-248">**Report phishing**</span></span>
- <span data-ttu-id="15e6d-249">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="15e6d-249">**Report malware**</span></span>
- <span data-ttu-id="15e6d-250">**Spam melden**</span><span class="sxs-lookup"><span data-stu-id="15e6d-250">**Report spam**</span></span>

![Optionen für die Schaltfläche "Aktion"](../../media/user-submission-custom-mailbox-action-button.png)

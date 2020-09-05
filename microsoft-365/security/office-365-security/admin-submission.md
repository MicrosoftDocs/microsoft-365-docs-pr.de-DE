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
ms.openlocfilehash: 08d1633142bba7348cbc899f9cf9b2a1288c3743
ms.sourcegitcommit: 916fa2dacbc13287b49823176375259d7af03f86
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "47394735"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="b724d-103">Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="b724d-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="b724d-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online können Administratoren das Übermittlungen-Portal im Security & Compliance Center verwenden, um e-Mail-Nachrichten, URLs und Anlagen für die Überprüfung an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="b724d-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="b724d-105">Wenn Sie eine e-Mail übermitteln, erhalten Sie Informationen zu allen Richtlinien, die möglicherweise die eingehenden e-Mails in ihren Mandanten zugelassen haben, sowie über die Untersuchung von URLs und Anlagen in der e-Mail.</span><span class="sxs-lookup"><span data-stu-id="b724d-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="b724d-106">Richtlinien, die möglicherweise eine e-Mail erlaubt haben, enthalten die Liste sicherer Absender eines einzelnen Benutzers sowie Richtlinien auf Mandantenebene wie Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln).</span><span class="sxs-lookup"><span data-stu-id="b724d-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="b724d-107">Weitere Möglichkeiten zum Übermitteln von e-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="b724d-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b724d-108">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="b724d-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b724d-109">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b724d-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b724d-110">Wenn Sie direkt zur **Übermittlungs** Seite wechseln möchten, verwenden Sie <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="b724d-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="b724d-111">Um Nachrichten und Dateien an Microsoft zu übermitteln, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="b724d-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="b724d-112">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b724d-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="b724d-113">**Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="b724d-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="b724d-114">Beachten Sie, dass die Mitgliedschaft in dieser Rollengruppe erforderlich ist, um [Benutzer Übermittlungen an das benutzerdefinierte Postfach anzuzeigen](#view-user-submissions-to-the-custom-mailbox) , wie weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b724d-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="b724d-115">Weitere Informationen darüber, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="b724d-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="b724d-116">Verdächtigen Inhalt an Microsoft melden</span><span class="sxs-lookup"><span data-stu-id="b724d-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="b724d-117">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> -über **mittlungen**, stellen Sie sicher, dass Sie sich auf der Registerkarte Admin-über **mittlungen** befinden, und klicken Sie dann auf **neue Übermittlung**.</span><span class="sxs-lookup"><span data-stu-id="b724d-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="b724d-118">Verwenden Sie das **neue Übermittlungs** Flyout, das angezeigt wird, um die Nachricht, die URL oder Anlage zu übermitteln, wie in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b724d-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="b724d-119">Senden einer fragwürdigen e-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="b724d-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="b724d-120">Wählen Sie im Abschnitt **Objekttyp** die Option **e-Mail**aus.</span><span class="sxs-lookup"><span data-stu-id="b724d-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="b724d-121">Verwenden Sie im Abschnitt **Übermittlungs Format** eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="b724d-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="b724d-122">**Netzwerknachrichten-ID**: Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-ID** -Header in der Nachricht zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="b724d-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="b724d-123">**Datei**: Klicken Sie auf **Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="b724d-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="b724d-124">Suchen Sie in dem Dialogfeld, das geöffnet wird, nach der EML-oder msg-Datei, und wählen Sie Sie aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="b724d-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="b724d-125">Geben Sie im Abschnitt **Empfänger** einen oder mehrere Empfänger an, für die Sie eine Richtlinienüberprüfung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="b724d-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="b724d-126">Durch die Richtlinienüberprüfung wird ermittelt, ob die e-Mail-Überprüfung aufgrund von Benutzer-oder Organisationsrichtlinien umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="b724d-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="b724d-127">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b724d-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="b724d-128">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="b724d-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="b724d-129">**Sollte blockiert worden sein**: Wählen Sie **Spam**, **Phishing**oder **Schadsoftware**aus.</span><span class="sxs-lookup"><span data-stu-id="b724d-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="b724d-130">Wenn Sie nicht sicher sind, verwenden Sie Ihr Bestes Urteil.</span><span class="sxs-lookup"><span data-stu-id="b724d-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="b724d-131">Wenn der Filter aufgrund von Richtlinien bei der Übermittlung umgangen wurde, werden Informationen zu dieser Richtlinie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b724d-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="b724d-132">Wenn der Filter aufgrund einer oder mehrerer Richtlinien nicht umgangen wurde, wird die Überprüfung in einigen Minuten abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b724d-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="b724d-133">Sie erhalten zusätzliche Informationen über die Übermittlung, indem Sie auf den Link Status klicken.</span><span class="sxs-lookup"><span data-stu-id="b724d-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="b724d-134">Dies beinhaltet die Ergebnisse der Richtlinienüberprüfung und das Ergebnis der erneuten Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="b724d-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="b724d-135">Hinweis Dadurch wird die e-Mail-Nachricht nicht über den Office 365 ATP-voll Filter Stapel erneut ausgeführt, es wird jedoch ein partieller erneuter Scan auf der Grundlage bestimmter Attribute der e-Mail, der URL oder der Datei ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b724d-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="b724d-136">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="b724d-136">When you're finished, click the **Submit** button.</span></span>

![URL-Übermittlungs Beispiel](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="b724d-138">Senden einer verdächtigen URL an Microsoft</span><span class="sxs-lookup"><span data-stu-id="b724d-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="b724d-139">Wählen Sie im Abschnitt **Objekttyp** die Option **URL**aus.</span><span class="sxs-lookup"><span data-stu-id="b724d-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="b724d-140">Geben Sie in das Feld, das angezeigt wird, die vollständige URL ein (beispielsweise <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="b724d-140">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="b724d-141">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b724d-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="b724d-142">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="b724d-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="b724d-143">**Sollte blockiert worden sein**: Wählen Sie **Phishing** oder **Schadsoftware**aus.</span><span class="sxs-lookup"><span data-stu-id="b724d-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="b724d-144">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="b724d-144">When you're finished, click the **Submit** button.</span></span>

![Beispiel für eine e-Mail-Übermittlung](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="b724d-146">Übermitteln einer vermuteten Datei an Microsoft</span><span class="sxs-lookup"><span data-stu-id="b724d-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="b724d-147">Wählen Sie im Abschnitt **Objekttyp** die Option **Anlage**aus.</span><span class="sxs-lookup"><span data-stu-id="b724d-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="b724d-148">Klicken Sie auf **Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="b724d-148">Click **Choose File**.</span></span> <span data-ttu-id="b724d-149">Suchen und wählen Sie im daraufhin geöffneten Dialogfeld die Datei aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="b724d-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="b724d-150">Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b724d-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="b724d-151">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="b724d-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="b724d-152">**Sollte blockiert worden sein**: **Schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt..</span><span class="sxs-lookup"><span data-stu-id="b724d-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="b724d-153">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="b724d-153">When you're finished, click the **Submit** button.</span></span>

![Beispiel für Anlagen Übermittlung](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="b724d-155">Anzeigen von Übermittlungen von Administratoren</span><span class="sxs-lookup"><span data-stu-id="b724d-155">View admin submissions</span></span>

<span data-ttu-id="b724d-156">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> -über **mittlungen**, stellen Sie sicher, dass Sie sich auf der Registerkarte Admin-über **mittlungen** befinden, und klicken Sie dann auf **neue Übermittlung**.</span><span class="sxs-lookup"><span data-stu-id="b724d-156">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="b724d-157">Oben auf der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Übermittlungs-ID** (ein GUID-Wert, der jeder Übermittlung zugewiesen ist) filtern, indem Sie einen Wert in das Feld eingeben und auf Aktualisieren klicken ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="b724d-157">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="b724d-158">Update</span><span class="sxs-lookup"><span data-stu-id="b724d-158">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="b724d-159">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Übermittlungs-ID** , und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="b724d-159">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="b724d-160">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b724d-160">**Sender**</span></span>
- <span data-ttu-id="b724d-161">**Betreff/URL/Dateiname**</span><span class="sxs-lookup"><span data-stu-id="b724d-161">**Subject/URL/File name**</span></span>
- <span data-ttu-id="b724d-162">**Eingereicht von**</span><span class="sxs-lookup"><span data-stu-id="b724d-162">**Submitted by**</span></span>
- <span data-ttu-id="b724d-163">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="b724d-163">**Submission type**</span></span>
- <span data-ttu-id="b724d-164">**Status**</span><span class="sxs-lookup"><span data-stu-id="b724d-164">**Status**</span></span>

![Filter Optionen für Übermittlungen von Administratoren](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="b724d-166">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle**aus.</span><span class="sxs-lookup"><span data-stu-id="b724d-166">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="b724d-167">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="b724d-167">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="b724d-168">Unter dem Diagramm befinden sich drei Registerkarten: **e-Mail** (Standard), **URL**und **Anlage**.</span><span class="sxs-lookup"><span data-stu-id="b724d-168">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="b724d-169">Anzeigen von Administrator-e-Mail-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="b724d-169">View admin email submissions</span></span>

<span data-ttu-id="b724d-170">Klicken Sie auf die Registerkarte **e-Mail** .</span><span class="sxs-lookup"><span data-stu-id="b724d-170">Click the **Email** tab.</span></span>

<span data-ttu-id="b724d-171">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="b724d-171">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b724d-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="b724d-172">**Date**</span></span>
- <span data-ttu-id="b724d-173">**Übermittlungs-ID**: ein GUID-Wert, der jeder Übermittlung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="b724d-173">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="b724d-174">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-174">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b724d-175">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-175">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="b724d-176">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b724d-176">**Sender**</span></span>
- <span data-ttu-id="b724d-177">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-177">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="b724d-178">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="b724d-178">**Submission type**</span></span>
- <span data-ttu-id="b724d-179">**Zustellungs Grund**</span><span class="sxs-lookup"><span data-stu-id="b724d-179">**Delivery reason**</span></span>
- <span data-ttu-id="b724d-180">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-180">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="b724d-181">**Steuerelementtyp**</span><span class="sxs-lookup"><span data-stu-id="b724d-181">**Control type**</span></span>
- <span data-ttu-id="b724d-182">**Steuerelementquelle**</span><span class="sxs-lookup"><span data-stu-id="b724d-182">**Control source**</span></span>

  <span data-ttu-id="b724d-183"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b724d-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="b724d-184">Anzeigen von Administratoren-URL-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="b724d-184">View admin URL submissions</span></span>

<span data-ttu-id="b724d-185">Klicken Sie auf die Registerkarte **URL** .</span><span class="sxs-lookup"><span data-stu-id="b724d-185">Click the **URL** tab.</span></span>

<span data-ttu-id="b724d-186">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="b724d-186">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b724d-187">**Date**</span><span class="sxs-lookup"><span data-stu-id="b724d-187">**Date**</span></span>
- <span data-ttu-id="b724d-188">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="b724d-188">**Submission ID**</span></span>
- <span data-ttu-id="b724d-189">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-189">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b724d-190">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-190">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="b724d-191">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="b724d-191">**Submission type**</span></span>
- <span data-ttu-id="b724d-192">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-192">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="b724d-193"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b724d-193"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="b724d-194">Anzeigen der Übermittlungen von Administrator Anlagen</span><span class="sxs-lookup"><span data-stu-id="b724d-194">View admin attachment submissions</span></span>

<span data-ttu-id="b724d-195">Klicken Sie auf die Registerkarte **Anlagen** .</span><span class="sxs-lookup"><span data-stu-id="b724d-195">Click the **Attachments** tab.</span></span>

<span data-ttu-id="b724d-196">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="b724d-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b724d-197">**Date**</span><span class="sxs-lookup"><span data-stu-id="b724d-197">**Date**</span></span>
- <span data-ttu-id="b724d-198">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="b724d-198">**Submission ID**</span></span>
- <span data-ttu-id="b724d-199">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b724d-200">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-200">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="b724d-201">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="b724d-201">**Submission type**</span></span>
- <span data-ttu-id="b724d-202">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="b724d-203"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b724d-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="b724d-204">Anzeigen von Benutzern Übermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="b724d-204">View user submissions to Microsoft</span></span>

<span data-ttu-id="b724d-205">Wenn Sie das [Add-in "Berichtsnachricht](enable-the-report-message-add-in.md)" bereitgestellt haben oder die [integrierten Berichte in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)verwendet werden, können Sie sehen, welche Benutzer auf der Registerkarte " **Benutzereingaben** " berichten.</span><span class="sxs-lookup"><span data-stu-id="b724d-205">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="b724d-206">Wechseln Sie im Security & Compliance Center zu **Threat Management** -über \> **mittlungen**.</span><span class="sxs-lookup"><span data-stu-id="b724d-206">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="b724d-207">Wählen Sie die Registerkarte **Benutzer Übermittlungen** aus, und klicken Sie dann auf **neue Übermittlung**.</span><span class="sxs-lookup"><span data-stu-id="b724d-207">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="b724d-208">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="b724d-208">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b724d-209">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="b724d-209">**Submitted on**</span></span>
- <span data-ttu-id="b724d-210">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b724d-211">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-211">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="b724d-212">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b724d-212">**Sender**</span></span>
- <span data-ttu-id="b724d-213">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-213">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="b724d-214">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="b724d-214">**Submission type**</span></span>

<span data-ttu-id="b724d-215"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b724d-215"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="b724d-216">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Absender** filtern, indem Sie einen Wert in das Feld eingeben und auf ![ Aktualisieren klicken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="b724d-216">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="b724d-217">Update</span><span class="sxs-lookup"><span data-stu-id="b724d-217">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="b724d-218">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Absender** , und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="b724d-218">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="b724d-219">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="b724d-219">**Sender domain**</span></span>
- <span data-ttu-id="b724d-220">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="b724d-220">**Subject**</span></span>
- <span data-ttu-id="b724d-221">**Eingereicht von**</span><span class="sxs-lookup"><span data-stu-id="b724d-221">**Submitted by**</span></span>
- <span data-ttu-id="b724d-222">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="b724d-222">**Submission type**</span></span>
- <span data-ttu-id="b724d-223">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="b724d-223">**Sender IP**</span></span>

![Filter Optionen für Benutzer Übermittlungen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="b724d-225">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle**aus.</span><span class="sxs-lookup"><span data-stu-id="b724d-225">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="b724d-226">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="b724d-226">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="b724d-227">Anzeigen von Benutzereingaben zum benutzerdefinierten Postfach</span><span class="sxs-lookup"><span data-stu-id="b724d-227">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="b724d-228">**Wenn** Sie [ein benutzerdefiniertes Postfach](user-submission.md) für den Empfang von gemeldeten Benutzern konfiguriert haben, können Sie Nachrichten anzeigen und auch senden, die an das Berichts Postfach übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="b724d-228">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="b724d-229">Wechseln Sie im Security & Compliance Center zu **Threat Management** -über \> **mittlungen**.</span><span class="sxs-lookup"><span data-stu-id="b724d-229">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="b724d-230">Wählen Sie die Registerkarte **benutzerdefiniertes Postfach** aus.</span><span class="sxs-lookup"><span data-stu-id="b724d-230">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="b724d-231">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="b724d-231">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b724d-232">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="b724d-232">**Submitted on**</span></span>
- <span data-ttu-id="b724d-233">**Eingereicht von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-233">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b724d-234">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-234">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="b724d-235">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b724d-235">**Sender**</span></span>
- <span data-ttu-id="b724d-236">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b724d-236">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="b724d-237">**Übermittlungs**</span><span class="sxs-lookup"><span data-stu-id="b724d-237">**Submission type**</span></span>

<span data-ttu-id="b724d-238">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum eingeben und nach **abgesendet** filtern, indem Sie einen Wert in das Feld eingeben und auf ![ Aktualisieren klicken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="b724d-238">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="b724d-239">Update</span><span class="sxs-lookup"><span data-stu-id="b724d-239">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="b724d-240">Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle**aus.</span><span class="sxs-lookup"><span data-stu-id="b724d-240">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="b724d-241">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="b724d-241">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="b724d-242">Übermitteln von Nachrichten an Microsoft aus dem benutzerdefinierten Postfach</span><span class="sxs-lookup"><span data-stu-id="b724d-242">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="b724d-243">Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass vom Benutzer gemeldete Nachrichten abgefangen werden, ohne dass die Nachrichten an Microsoft gesendet werden, können Sie bestimmte Nachrichten zur Analyse an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="b724d-243">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="b724d-244">Dadurch wird eine Benutzer Übermittlung effektiv in eine Administrator Übermittlung verschoben.</span><span class="sxs-lookup"><span data-stu-id="b724d-244">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="b724d-245">Wählen Sie auf der Registerkarte **benutzerdefiniertes Postfach** eine Nachricht in der Liste aus, klicken Sie auf die Schaltfläche **Aktion** , und führen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b724d-245">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="b724d-246">**Bericht säubern**</span><span class="sxs-lookup"><span data-stu-id="b724d-246">**Report clean**</span></span>
- <span data-ttu-id="b724d-247">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="b724d-247">**Report phishing**</span></span>
- <span data-ttu-id="b724d-248">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="b724d-248">**Report malware**</span></span>
- <span data-ttu-id="b724d-249">**Spam melden**</span><span class="sxs-lookup"><span data-stu-id="b724d-249">**Report spam**</span></span>

![Optionen für die Schaltfläche "Aktion"](../../media/user-submission-custom-mailbox-action-button.png)

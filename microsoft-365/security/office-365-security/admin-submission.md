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
ms.openlocfilehash: d0b91808aa9008f467f66b8200f2c05a120fbcd9
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107230"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="608dc-103">Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="608dc-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="608dc-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="608dc-104">**Applies to**</span></span>
- [<span data-ttu-id="608dc-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="608dc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="608dc-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="608dc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="608dc-107">In Microsoft 365 Organisationen mit Postfächern in Exchange Online können Administratoren das Übermittlungsportal im Security & Compliance Center verwenden, um E-Mail-Nachrichten, URLs und Anlagen zur Überprüfung an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="608dc-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="608dc-108">Wenn Sie eine E-Mail-Nachricht übermitteln, erhalten Sie:</span><span class="sxs-lookup"><span data-stu-id="608dc-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="608dc-109">**E-Mail-Authentifizierungsprüfung:** Details dazu, ob die E-Mail-Authentifizierung bei der Zugestellten bestanden oder fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="608dc-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="608dc-110">**Richtlinientreffer**: Informationen zu allen Richtlinien, die die eingehenden E-Mails möglicherweise in Ihrem Mandanten zugelassen oder blockiert haben, und überschreiben unsere Dienstfilter-Urteile.</span><span class="sxs-lookup"><span data-stu-id="608dc-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="608dc-111">**Nutzlast reputation/detonation**: Prüfung aller URLs und Anlagen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="608dc-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="608dc-112">**Analyse der** Benotung: Überprüfen Sie, ob Nachrichten bösartig sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="608dc-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="608dc-113">Die Nutzlastre reputation/detonation und grader analysis werden nicht in allen Mandanten durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="608dc-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="608dc-114">Es wird verhindert, dass Informationen außerhalb der Organisation bleiben, wenn Daten die Mandantengrenze nicht aus Compliancegründen verlassen sollen.</span><span class="sxs-lookup"><span data-stu-id="608dc-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="608dc-115">Weitere Möglichkeiten zum Übermitteln von E-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter Melden von Nachrichten [und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="608dc-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="608dc-116">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="608dc-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="608dc-117">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="608dc-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="608dc-118">Um direkt zur Übermittlungsseite **zu** wechseln, verwenden Sie <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="608dc-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="608dc-119">Zum Übermitteln von Nachrichten und Dateien an Microsoft müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="608dc-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="608dc-120">**Organisationsverwaltung** oder **Security Reader** im Security & [Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="608dc-120">**Organization Management** or **Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="608dc-121">**Organisationsverwaltung** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="608dc-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="608dc-122">Beachten Sie, dass die Mitgliedschaft in dieser Rollengruppe erforderlich ist, um Benutzerübermittlungen an [das](#view-user-submissions-to-the-custom-mailbox) benutzerdefinierte Postfach wie weiter unten in diesem Artikel beschrieben anzeigen.</span><span class="sxs-lookup"><span data-stu-id="608dc-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="608dc-123">Weitere Informationen dazu, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter Melden von Nachrichten und Dateien [an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="608dc-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="608dc-124">Melden verdächtiger Inhalte an Microsoft</span><span class="sxs-lookup"><span data-stu-id="608dc-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="608dc-125">Wechseln Sie & Security & Compliance  Center zu Übermittlungen der \> **Bedrohungsverwaltung,** überprüfen Sie, ob Sie sich auf der Registerkarte **Administratorübermittlungen** befindet, und klicken Sie dann auf **Neue Übermittlung**.</span><span class="sxs-lookup"><span data-stu-id="608dc-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="608dc-126">Verwenden **Sie Neues Übermittlungsf** flyout, das die Nachricht, URL oder Anlage wie in den folgenden Abschnitten beschrieben zu übermitteln scheint.</span><span class="sxs-lookup"><span data-stu-id="608dc-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="608dc-127">Senden einer fragwürdigen E-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="608dc-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="608dc-128">Wählen Sie **im Abschnitt Objekttyp** die Option **E-Mail aus.**</span><span class="sxs-lookup"><span data-stu-id="608dc-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="608dc-129">Verwenden Sie **im** Abschnitt Übermittlungsformat eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="608dc-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="608dc-130">**Netzwerknachrichten-ID:** Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-Id-Header** in der Nachricht oder im **X-MS-Office365-Filtering-Correlation-Id-Header** in isolierten Nachrichten verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="608dc-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="608dc-131">**Datei**: Klicken Sie **auf Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="608dc-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="608dc-132">Suchen Und wählen Sie im geöffneten Dialogfeld die Datei EML oder MSG aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="608dc-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="608dc-133">Die Möglichkeit, Nachrichten ab einem Alter von 30 Tagen zu übermitteln, wurde für Defender für Office 365 ausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="608dc-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="608dc-134">Administratoren können nur 7 Tage zurück.</span><span class="sxs-lookup"><span data-stu-id="608dc-134">Admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="608dc-135">Geben Sie **im Abschnitt Empfänger** einen oder mehrere Empfänger an, für die Sie eine Richtlinienüberprüfung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="608dc-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="608dc-136">Die Richtlinienüberprüfung bestimmt, ob die E-Mail-Überprüfung aufgrund von Benutzer- oder Organisationsrichtlinien umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="608dc-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="608dc-137">Wählen Sie **im Abschnitt** Gründe für die Übermittlung eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="608dc-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="608dc-138">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="608dc-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="608dc-139">**Sollte blockiert sein:** Wählen **Sie Spam,** **Phishing** oder **Malware aus.**</span><span class="sxs-lookup"><span data-stu-id="608dc-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="608dc-140">Wenn Sie nicht sicher sind, verwenden Sie Ihr bestes Urteil.</span><span class="sxs-lookup"><span data-stu-id="608dc-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="608dc-141">Wenn Sie fertig sind, klicken Sie auf **die** Schaltfläche Absenden.</span><span class="sxs-lookup"><span data-stu-id="608dc-141">When you're finished, click the **Submit** button.</span></span>

   ![Neues URL-Übermittlungsbeispiel](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="608dc-143">Senden einer verdächtigen URL an Microsoft</span><span class="sxs-lookup"><span data-stu-id="608dc-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="608dc-144">Wählen Sie **im Abschnitt Objekttyp** die **Option URL aus.**</span><span class="sxs-lookup"><span data-stu-id="608dc-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="608dc-145">Geben Sie in das angezeigte Feld die vollständige URL ein (z. B. `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="608dc-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="608dc-146">Wählen Sie **im Abschnitt** Gründe für die Übermittlung eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="608dc-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="608dc-147">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="608dc-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="608dc-148">**Sollte blockiert sein:** Wählen Sie **Phishing oder** **Schadsoftware aus.**</span><span class="sxs-lookup"><span data-stu-id="608dc-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="608dc-149">Wenn Sie fertig sind, klicken Sie auf **die** Schaltfläche Absenden.</span><span class="sxs-lookup"><span data-stu-id="608dc-149">When you're finished, click the **Submit** button.</span></span>

   ![Beispiel für neue E-Mail-Übermittlung](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="608dc-151">Übermitteln einer verdächtigen Datei an Microsoft</span><span class="sxs-lookup"><span data-stu-id="608dc-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="608dc-152">Wählen Sie **im Abschnitt Objekttyp** die Option **Anlage aus.**</span><span class="sxs-lookup"><span data-stu-id="608dc-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="608dc-153">Klicken **Sie auf Datei auswählen.**</span><span class="sxs-lookup"><span data-stu-id="608dc-153">Click **Choose File**.</span></span> <span data-ttu-id="608dc-154">Suchen Und wählen Sie im geöffneten Dialogfeld die Datei aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="608dc-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="608dc-155">Wählen Sie **im Abschnitt** Gründe für die Übermittlung eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="608dc-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="608dc-156">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="608dc-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="608dc-157">**Sollte blockiert worden sein:** **Schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="608dc-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="608dc-158">Wenn Sie fertig sind, klicken Sie auf **die** Schaltfläche Absenden.</span><span class="sxs-lookup"><span data-stu-id="608dc-158">When you're finished, click the **Submit** button.</span></span>

   ![Beispiel für die Übermittlung neuer Anlagen](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="608dc-160">Zur Analyse übermittelte Elemente anzeigen</span><span class="sxs-lookup"><span data-stu-id="608dc-160">View items Submitted for analysis</span></span>

<span data-ttu-id="608dc-161">Wechseln Sie & Security & Compliance  Center zu Übermittlungen zur \> **Bedrohungsverwaltung,** überprüfen Sie, ob Sie auf der Registerkarte Übermittelt für **die Analyse** sind.</span><span class="sxs-lookup"><span data-stu-id="608dc-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="608dc-162">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum und  (standardmäßig) nach Übermittlungs-ID filtern (ein GUID-Wert, der jeder Übermittlung zugewiesen ist), indem Sie einen Wert in das Feld eingeben und auf Aktualisieren ![ ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="608dc-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="608dc-163">Mehrere Werte können durch Kommata getrennt eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="608dc-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="608dc-164">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Übermittlungs-ID,** und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="608dc-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="608dc-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="608dc-165">**Sender**</span></span>
- <span data-ttu-id="608dc-166">**Betreff/URL/Dateiname**</span><span class="sxs-lookup"><span data-stu-id="608dc-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="608dc-167">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="608dc-167">**Submitted by**</span></span>
- <span data-ttu-id="608dc-168">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="608dc-168">**Submission type**</span></span>
- <span data-ttu-id="608dc-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="608dc-169">**Status**</span></span>

![Neue Filteroptionen für Administratorübermittlungen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="608dc-171">Klicken Sie zum Exportieren der Ergebnisse **am** oberen Rand der Seite auf Exportieren, und wählen Sie **Diagrammdaten** oder **Tabelle aus.**</span><span class="sxs-lookup"><span data-stu-id="608dc-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="608dc-172">Speichern Sie im angezeigten Dialogfeld die .csv Datei.</span><span class="sxs-lookup"><span data-stu-id="608dc-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="608dc-173">Unterhalb des Diagramms befinden sich drei Registerkarten: **E-Mail** (Standard), **URL** und **Anlage**.</span><span class="sxs-lookup"><span data-stu-id="608dc-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="608dc-174">Anzeigen von Administrator-E-Mail-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="608dc-174">View admin email submissions</span></span>

<span data-ttu-id="608dc-175">Klicken Sie auf **die Registerkarte E-Mail.**</span><span class="sxs-lookup"><span data-stu-id="608dc-175">Click the **Email** tab.</span></span>

<span data-ttu-id="608dc-176">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="608dc-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="608dc-177">**Date**</span><span class="sxs-lookup"><span data-stu-id="608dc-177">**Date**</span></span>
- <span data-ttu-id="608dc-178">**Übermittlungs-ID:** Ein GUID-Wert, der jeder Übermittlung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="608dc-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="608dc-179">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="608dc-180">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="608dc-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="608dc-181">**Sender**</span></span>
- <span data-ttu-id="608dc-182">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="608dc-183">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="608dc-183">**Submission type**</span></span>
- <span data-ttu-id="608dc-184">**Zustellungsgrund**</span><span class="sxs-lookup"><span data-stu-id="608dc-184">**Delivery reason**</span></span>
- <span data-ttu-id="608dc-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="608dc-186"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="608dc-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="608dc-187">Details zum erneuten Scannen der Administratorübermittlung</span><span class="sxs-lookup"><span data-stu-id="608dc-187">Admin submission rescan details</span></span>

<span data-ttu-id="608dc-188">Nachrichten, die in Administratorübermittlungen übermittelt werden, werden erneut überprüft, und die Ergebnisse werden im Detailf flyout angezeigt:</span><span class="sxs-lookup"><span data-stu-id="608dc-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="608dc-189">Mögliche Fehler in der E-Mail-Authentifizierung des Absenders zum Zeitpunkt der Auslieferung.</span><span class="sxs-lookup"><span data-stu-id="608dc-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="608dc-190">Informationen zu Richtlinientreffern, welche die Bewertung über einer Nachricht beeinflusst oder überschrieben haben könnten.</span><span class="sxs-lookup"><span data-stu-id="608dc-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="608dc-191">Aktuelle Detonationsergebnisse, um festzustellen, ob die in der Nachricht enthaltenen URLs oder Dateien böswillig waren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="608dc-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="608dc-192">Feedback von Gradern.</span><span class="sxs-lookup"><span data-stu-id="608dc-192">Feedback from graders.</span></span>

<span data-ttu-id="608dc-193">Wenn eine Überschreibung gefunden wurde, sollte der erneute Scan in einigen Minuten abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="608dc-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="608dc-194">Wenn kein Problem bei der E-Mail-Authentifizierung oder -Zustellung durch eine Außerkraftsetzung verursacht wurde, kann das Feedback von Gradern bis zu einem Tag dauern.</span><span class="sxs-lookup"><span data-stu-id="608dc-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="608dc-195">Anzeigen von Administrator-URL-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="608dc-195">View admin URL submissions</span></span>

<span data-ttu-id="608dc-196">Klicken Sie auf **die Registerkarte URL.**</span><span class="sxs-lookup"><span data-stu-id="608dc-196">Click the **URL** tab.</span></span>

<span data-ttu-id="608dc-197">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="608dc-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="608dc-198">**Date**</span><span class="sxs-lookup"><span data-stu-id="608dc-198">**Date**</span></span>
- <span data-ttu-id="608dc-199">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="608dc-199">**Submission ID**</span></span>
- <span data-ttu-id="608dc-200">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="608dc-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="608dc-202">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="608dc-202">**Submission type**</span></span>
- <span data-ttu-id="608dc-203">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="608dc-204"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="608dc-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="608dc-205">Anzeigen von Administratoranhangsübermittlungen</span><span class="sxs-lookup"><span data-stu-id="608dc-205">View admin attachment submissions</span></span>

<span data-ttu-id="608dc-206">Klicken Sie auf **die Registerkarte Anlagen.**</span><span class="sxs-lookup"><span data-stu-id="608dc-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="608dc-207">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="608dc-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="608dc-208">**Date**</span><span class="sxs-lookup"><span data-stu-id="608dc-208">**Date**</span></span>
- <span data-ttu-id="608dc-209">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="608dc-209">**Submission ID**</span></span>
- <span data-ttu-id="608dc-210">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="608dc-211">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="608dc-212">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="608dc-212">**Submission type**</span></span>
- <span data-ttu-id="608dc-213">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="608dc-214"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="608dc-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="608dc-215">Anzeigen von Benutzerübermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="608dc-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="608dc-216">Wenn Sie das Berichtsnachrichten-Add-In , das  Phishing-Add-In Melden oder Personen, die die integrierte Berichterstellung in Outlook im Web verwenden, bereitgestellt haben, können Sie auf der Registerkarte Benutzerübermittlungen [anzeigen, welche](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)Benutzer melden. [](enable-the-report-message-add-in.md) [](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="608dc-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="608dc-217">Wechseln Sie im Security & Compliance Center zu Übermittlungen **der** \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="608dc-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="608dc-218">Wählen Sie **die Registerkarte Benutzerübermittlungen** aus, und klicken Sie dann auf **Neue Übermittlung**.</span><span class="sxs-lookup"><span data-stu-id="608dc-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="608dc-219">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="608dc-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="608dc-220">**Gesendet am**</span><span class="sxs-lookup"><span data-stu-id="608dc-220">**Submitted on**</span></span>
- <span data-ttu-id="608dc-221">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="608dc-222">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="608dc-223">**Sender**</span><span class="sxs-lookup"><span data-stu-id="608dc-223">**Sender**</span></span>
- <span data-ttu-id="608dc-224">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="608dc-225">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="608dc-225">**Submission type**</span></span>

<span data-ttu-id="608dc-226"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="608dc-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="608dc-227">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Sender** filtern, indem Sie einen Wert in das Feld eingeben und auf Aktualisieren ![ ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="608dc-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="608dc-228">Mehrere Werte können durch Kommata getrennt eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="608dc-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="608dc-229">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Absender,** und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="608dc-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="608dc-230">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="608dc-230">**Sender domain**</span></span>
- <span data-ttu-id="608dc-231">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="608dc-231">**Subject**</span></span>
- <span data-ttu-id="608dc-232">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="608dc-232">**Submitted by**</span></span>
- <span data-ttu-id="608dc-233">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="608dc-233">**Submission type**</span></span>
- <span data-ttu-id="608dc-234">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="608dc-234">**Sender IP**</span></span>

![Neue Filteroptionen für Benutzerübermittlungen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="608dc-236">Klicken Sie zum Exportieren der Ergebnisse **am** oberen Rand der Seite auf Exportieren, und wählen Sie **Diagrammdaten** oder **Tabelle aus.**</span><span class="sxs-lookup"><span data-stu-id="608dc-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="608dc-237">Speichern Sie im angezeigten Dialogfeld die .csv Datei.</span><span class="sxs-lookup"><span data-stu-id="608dc-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="608dc-238">Anzeigen von Benutzerübermittlungen an das benutzerdefinierte Postfach</span><span class="sxs-lookup"><span data-stu-id="608dc-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="608dc-239">**Wenn** Sie ein [benutzerdefiniertes](user-submission.md) Postfach für den Empfang von vom Benutzer gemeldeten Nachrichten konfiguriert haben, können Sie Nachrichten anzeigen und auch übermitteln, die an das Berichtspostfach übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="608dc-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="608dc-240">Wechseln Sie im Security & Compliance Center zu Übermittlungen **der** \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="608dc-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="608dc-241">Wählen Sie die **Registerkarte Benutzerdefiniertes Postfach** aus.</span><span class="sxs-lookup"><span data-stu-id="608dc-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="608dc-242">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="608dc-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="608dc-243">**Gesendet am**</span><span class="sxs-lookup"><span data-stu-id="608dc-243">**Submitted on**</span></span>
- <span data-ttu-id="608dc-244">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="608dc-245">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="608dc-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="608dc-246">**Sender**</span></span>
- <span data-ttu-id="608dc-247">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="608dc-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="608dc-248">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="608dc-248">**Submission type**</span></span>

<span data-ttu-id="608dc-249">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum eingeben und nach **Übermittelt** filtern, indem Sie in das Feld einen Wert eingeben und auf Aktualisieren ![ ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="608dc-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="608dc-250">Mehrere Werte können durch Kommata getrennt eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="608dc-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="608dc-251">Klicken Sie zum Exportieren der Ergebnisse **am** oberen Rand der Seite auf Exportieren, und wählen Sie **Diagrammdaten** oder **Tabelle aus.**</span><span class="sxs-lookup"><span data-stu-id="608dc-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="608dc-252">Speichern Sie im angezeigten Dialogfeld die .csv Datei.</span><span class="sxs-lookup"><span data-stu-id="608dc-252">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="608dc-253">Wenn Organisationen nur für das Senden an benutzerdefinierte Postfächer konfiguriert sind, werden die gemeldeten Nachrichten nicht zum erneuten Scannen gesendet, und die Ergebnisse im Portal für vom Benutzer gemeldete Nachrichten sind immer leer.</span><span class="sxs-lookup"><span data-stu-id="608dc-253">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="608dc-254">Rückgängig machen von Benutzerübermittlungen</span><span class="sxs-lookup"><span data-stu-id="608dc-254">Undo user submissions</span></span>

<span data-ttu-id="608dc-255">Sobald ein Benutzer eine verdächtige E-Mail an das benutzerdefinierte Postfach übermittelt hat, haben der Benutzer und der Administrator keine Möglichkeit, die Übermittlung rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="608dc-255">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="608dc-256">Wenn der Benutzer die E-Mail wiederherstellen möchte, steht sie für die Wiederherstellung in den Ordnern Gelöschte Elemente oder Junk-E-Mail zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="608dc-256">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="608dc-257">Senden von Nachrichten an Microsoft aus dem benutzerdefinierten Postfach</span><span class="sxs-lookup"><span data-stu-id="608dc-257">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="608dc-258">Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass von Benutzern gemeldete Nachrichten abgefangen werden, ohne die Nachrichten an Microsoft zu senden, können Sie bestimmte Nachrichten zur Analyse finden und an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="608dc-258">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="608dc-259">Dadurch wird eine Benutzerübermittlung effektiv in eine Administratorübermittlung verlagert.</span><span class="sxs-lookup"><span data-stu-id="608dc-259">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="608dc-260">Wählen Sie **auf** der Registerkarte Benutzer gemeldete Nachrichten  eine Nachricht in der Liste aus, klicken Sie auf die Schaltfläche Aktion, und treffen Sie eine der folgenden Auswahlen:</span><span class="sxs-lookup"><span data-stu-id="608dc-260">On the **User reported messages** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="608dc-261">**Bericht bereinigen**</span><span class="sxs-lookup"><span data-stu-id="608dc-261">**Report clean**</span></span>
- <span data-ttu-id="608dc-262">**Melden von Phishing**</span><span class="sxs-lookup"><span data-stu-id="608dc-262">**Report phishing**</span></span>
- <span data-ttu-id="608dc-263">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="608dc-263">**Report malware**</span></span>
- <span data-ttu-id="608dc-264">**Melden von Spam**</span><span class="sxs-lookup"><span data-stu-id="608dc-264">**Report spam**</span></span>

![Neue Optionen auf der Schaltfläche Aktion](../../media/user-submission-custom-mailbox-action-button.png)

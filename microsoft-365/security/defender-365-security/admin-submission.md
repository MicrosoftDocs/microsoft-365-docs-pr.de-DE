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
ms.openlocfilehash: 3dd566de3ba4b4281b19c423b8623f081c378bca
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065648"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="ae509-103">Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="ae509-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ae509-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="ae509-104">**Applies to**</span></span>
- [<span data-ttu-id="ae509-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ae509-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ae509-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="ae509-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="ae509-107">In Microsoft 365-Organisationen mit Postfächern in Exchange Online können Administratoren das Übermittlungsportal im Security & Compliance Center verwenden, um E-Mail-Nachrichten, URLs und Anlagen zur Überprüfung an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="ae509-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="ae509-108">Wenn Sie eine E-Mail-Nachricht übermitteln, erhalten Sie:</span><span class="sxs-lookup"><span data-stu-id="ae509-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="ae509-109">**E-Mail-Authentifizierungsprüfung:** Details dazu, ob die E-Mail-Authentifizierung bei der Zugestellten bestanden oder fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="ae509-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="ae509-110">**Richtlinientreffer**: Informationen zu allen Richtlinien, die die eingehenden E-Mails möglicherweise in Ihrem Mandanten zugelassen oder blockiert haben, und überschreiben unsere Dienstfilter-Urteile.</span><span class="sxs-lookup"><span data-stu-id="ae509-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="ae509-111">**Nutzlast reputation/detonation**: Prüfung aller URLs und Anlagen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="ae509-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="ae509-112">**Analyse der** Benotung: Überprüfen Sie, ob Nachrichten bösartig sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="ae509-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae509-113">Die Nutzlastre reputation/detonation und grader analysis werden nicht in allen Mandanten durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="ae509-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="ae509-114">Es wird verhindert, dass Informationen außerhalb der Organisation bleiben, wenn Daten die Mandantengrenze nicht aus Compliancegründen verlassen sollen.</span><span class="sxs-lookup"><span data-stu-id="ae509-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="ae509-115">Weitere Möglichkeiten zum Übermitteln von E-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter Melden von Nachrichten [und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ae509-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ae509-116">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="ae509-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ae509-117">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ae509-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ae509-118">Um direkt zur Übermittlungsseite **zu** wechseln, verwenden Sie <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="ae509-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="ae509-119">Zum Übermitteln von Nachrichten und Dateien an Microsoft müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="ae509-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="ae509-120">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ae509-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="ae509-121">**Organisationsverwaltung** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="ae509-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="ae509-122">Beachten Sie, dass die Mitgliedschaft in dieser Rollengruppe erforderlich ist, um Benutzerübermittlungen an [das](#view-user-submissions-to-the-custom-mailbox) benutzerdefinierte Postfach wie weiter unten in diesem Artikel beschrieben anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ae509-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="ae509-123">Weitere Informationen dazu, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter Melden von Nachrichten und Dateien [an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ae509-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="ae509-124">Melden verdächtiger Inhalte an Microsoft</span><span class="sxs-lookup"><span data-stu-id="ae509-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="ae509-125">Wechseln Sie & Security & Compliance  Center zu Übermittlungen der \> **Bedrohungsverwaltung,** überprüfen Sie, ob Sie sich auf der Registerkarte **Administratorübermittlungen** befindet, und klicken Sie dann auf **Neue Übermittlung**.</span><span class="sxs-lookup"><span data-stu-id="ae509-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="ae509-126">Verwenden **Sie Neues Übermittlungsf** flyout, das die Nachricht, URL oder Anlage wie in den folgenden Abschnitten beschrieben zu übermitteln scheint.</span><span class="sxs-lookup"><span data-stu-id="ae509-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="ae509-127">Senden einer fragwürdigen E-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="ae509-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="ae509-128">Wählen Sie **im Abschnitt Objekttyp** die Option **E-Mail aus.**</span><span class="sxs-lookup"><span data-stu-id="ae509-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="ae509-129">Verwenden Sie **im** Abschnitt Übermittlungsformat eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="ae509-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="ae509-130">**Netzwerknachrichten-ID:** Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-Id-Header** in der Nachricht oder im **X-MS-Office365-Filtering-Correlation-Id-Header** in isolierten Nachrichten verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ae509-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="ae509-131">**Datei**: Klicken Sie **auf Datei auswählen**.</span><span class="sxs-lookup"><span data-stu-id="ae509-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="ae509-132">Suchen Und wählen Sie im geöffneten Dialogfeld die Datei EML oder MSG aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="ae509-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ae509-133">Administratoren mit Defender für Office 365 Plan 1 oder Plan 2 können Nachrichten so alt wie 30 Tage übermitteln.</span><span class="sxs-lookup"><span data-stu-id="ae509-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="ae509-134">Andere Administratoren können nur 7 Tage zurück.</span><span class="sxs-lookup"><span data-stu-id="ae509-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="ae509-135">Geben Sie **im Abschnitt Empfänger** einen oder mehrere Empfänger an, für die Sie eine Richtlinienüberprüfung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="ae509-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="ae509-136">Die Richtlinienüberprüfung bestimmt, ob die E-Mail-Überprüfung aufgrund von Benutzer- oder Organisationsrichtlinien umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="ae509-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="ae509-137">Wählen Sie **im Abschnitt** Gründe für die Übermittlung eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="ae509-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ae509-138">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="ae509-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ae509-139">**Sollte blockiert sein:** Wählen **Sie Spam,** **Phishing** oder **Malware aus.**</span><span class="sxs-lookup"><span data-stu-id="ae509-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="ae509-140">Wenn Sie nicht sicher sind, verwenden Sie Ihr bestes Urteil.</span><span class="sxs-lookup"><span data-stu-id="ae509-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="ae509-141">Wenn Sie fertig sind, klicken Sie auf **die** Schaltfläche Absenden.</span><span class="sxs-lookup"><span data-stu-id="ae509-141">When you're finished, click the **Submit** button.</span></span>

   ![Beispiel für die URL-Übermittlung](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="ae509-143">Senden einer verdächtigen URL an Microsoft</span><span class="sxs-lookup"><span data-stu-id="ae509-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="ae509-144">Wählen Sie **im Abschnitt Objekttyp** die **Option URL aus.**</span><span class="sxs-lookup"><span data-stu-id="ae509-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="ae509-145">Geben Sie in das angezeigte Feld die vollständige URL ein (z. B. `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="ae509-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="ae509-146">Wählen Sie **im Abschnitt** Gründe für die Übermittlung eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="ae509-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ae509-147">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="ae509-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ae509-148">**Sollte blockiert sein:** Wählen Sie **Phishing oder** **Schadsoftware aus.**</span><span class="sxs-lookup"><span data-stu-id="ae509-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="ae509-149">Wenn Sie fertig sind, klicken Sie auf **die** Schaltfläche Absenden.</span><span class="sxs-lookup"><span data-stu-id="ae509-149">When you're finished, click the **Submit** button.</span></span>

   ![Beispiel für die E-Mail-Übermittlung](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="ae509-151">Übermitteln einer verdächtigen Datei an Microsoft</span><span class="sxs-lookup"><span data-stu-id="ae509-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="ae509-152">Wählen Sie **im Abschnitt Objekttyp** die Option **Anlage aus.**</span><span class="sxs-lookup"><span data-stu-id="ae509-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="ae509-153">Klicken **Sie auf Datei auswählen.**</span><span class="sxs-lookup"><span data-stu-id="ae509-153">Click **Choose File**.</span></span> <span data-ttu-id="ae509-154">Suchen Und wählen Sie im geöffneten Dialogfeld die Datei aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="ae509-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="ae509-155">Wählen Sie **im Abschnitt** Gründe für die Übermittlung eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="ae509-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ae509-156">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="ae509-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ae509-157">**Sollte blockiert worden sein:** **Schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ae509-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="ae509-158">Wenn Sie fertig sind, klicken Sie auf **die** Schaltfläche Absenden.</span><span class="sxs-lookup"><span data-stu-id="ae509-158">When you're finished, click the **Submit** button.</span></span>

   ![Beispiel für anlagenübermittlung](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="ae509-160">Anzeigen von Administratorübermittlungen</span><span class="sxs-lookup"><span data-stu-id="ae509-160">View admin submissions</span></span>

<span data-ttu-id="ae509-161">Wechseln Sie & Security & Compliance  Center zu Übermittlungen der \> **Bedrohungsverwaltung,** überprüfen Sie, ob Sie sich auf der Registerkarte **Administratorübermittlungen** befindet, und klicken Sie dann auf **Neue Übermittlung**.</span><span class="sxs-lookup"><span data-stu-id="ae509-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="ae509-162">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum und  (standardmäßig) nach Übermittlungs-ID filtern (ein GUID-Wert, der jeder Übermittlung zugewiesen ist), indem Sie einen Wert in das Feld eingeben und auf Aktualisieren ![ ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="ae509-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ae509-163">Mehrere Werte können durch Kommata getrennt eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ae509-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ae509-164">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Übermittlungs-ID,** und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="ae509-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="ae509-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="ae509-165">**Sender**</span></span>
- <span data-ttu-id="ae509-166">**Betreff/URL/Dateiname**</span><span class="sxs-lookup"><span data-stu-id="ae509-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="ae509-167">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="ae509-167">**Submitted by**</span></span>
- <span data-ttu-id="ae509-168">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="ae509-168">**Submission type**</span></span>
- <span data-ttu-id="ae509-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="ae509-169">**Status**</span></span>

![Filteroptionen für Administratorübermittlungen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="ae509-171">Klicken Sie zum Exportieren der Ergebnisse **am** oberen Rand der Seite auf Exportieren, und wählen Sie **Diagrammdaten** oder **Tabelle aus.**</span><span class="sxs-lookup"><span data-stu-id="ae509-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ae509-172">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="ae509-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="ae509-173">Unterhalb des Diagramms befinden sich drei Registerkarten: **E-Mail** (Standard), **URL** und **Anlage**.</span><span class="sxs-lookup"><span data-stu-id="ae509-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="ae509-174">Anzeigen von Administrator-E-Mail-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="ae509-174">View admin email submissions</span></span>

<span data-ttu-id="ae509-175">Klicken Sie auf **die Registerkarte E-Mail.**</span><span class="sxs-lookup"><span data-stu-id="ae509-175">Click the **Email** tab.</span></span>

<span data-ttu-id="ae509-176">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="ae509-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ae509-177">**Date**</span><span class="sxs-lookup"><span data-stu-id="ae509-177">**Date**</span></span>
- <span data-ttu-id="ae509-178">**Übermittlungs-ID:** Ein GUID-Wert, der jeder Übermittlung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ae509-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="ae509-179">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ae509-180">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ae509-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="ae509-181">**Sender**</span></span>
- <span data-ttu-id="ae509-182">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ae509-183">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="ae509-183">**Submission type**</span></span>
- <span data-ttu-id="ae509-184">**Zustellungsgrund**</span><span class="sxs-lookup"><span data-stu-id="ae509-184">**Delivery reason**</span></span>
- <span data-ttu-id="ae509-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="ae509-186"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae509-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="ae509-187">Details zum erneuten Scannen der Administratorübermittlung</span><span class="sxs-lookup"><span data-stu-id="ae509-187">Admin submission rescan details</span></span>

<span data-ttu-id="ae509-188">Nachrichten, die in Administratorübermittlungen übermittelt werden, werden erneut überprüft, und die Ergebnisse werden im Detailf flyout angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ae509-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="ae509-189">Mögliche Fehler in der E-Mail-Authentifizierung des Absenders zum Zeitpunkt der Auslieferung.</span><span class="sxs-lookup"><span data-stu-id="ae509-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="ae509-190">Informationen zu Richtlinientreffern, welche die Bewertung über einer Nachricht beeinflusst oder überschrieben haben könnten.</span><span class="sxs-lookup"><span data-stu-id="ae509-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="ae509-191">Aktuelle Detonationsergebnisse, um festzustellen, ob die in der Nachricht enthaltenen URLs oder Dateien böswillig waren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="ae509-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="ae509-192">Feedback von Gradern.</span><span class="sxs-lookup"><span data-stu-id="ae509-192">Feedback from graders.</span></span>

<span data-ttu-id="ae509-193">Wenn eine Überschreibung gefunden wurde, sollte der erneute Scan in einigen Minuten abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="ae509-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="ae509-194">Wenn kein Problem bei der E-Mail-Authentifizierung oder -Zustellung durch eine Außerkraftsetzung verursacht wurde, kann das Feedback von Gradern bis zu einem Tag dauern.</span><span class="sxs-lookup"><span data-stu-id="ae509-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="ae509-195">Anzeigen von Administrator-URL-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="ae509-195">View admin URL submissions</span></span>

<span data-ttu-id="ae509-196">Klicken Sie auf **die Registerkarte URL.**</span><span class="sxs-lookup"><span data-stu-id="ae509-196">Click the **URL** tab.</span></span>

<span data-ttu-id="ae509-197">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="ae509-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ae509-198">**Date**</span><span class="sxs-lookup"><span data-stu-id="ae509-198">**Date**</span></span>
- <span data-ttu-id="ae509-199">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="ae509-199">**Submission ID**</span></span>
- <span data-ttu-id="ae509-200">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ae509-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="ae509-202">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="ae509-202">**Submission type**</span></span>
- <span data-ttu-id="ae509-203">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="ae509-204"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae509-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="ae509-205">Anzeigen von Administratoranhangsübermittlungen</span><span class="sxs-lookup"><span data-stu-id="ae509-205">View admin attachment submissions</span></span>

<span data-ttu-id="ae509-206">Klicken Sie auf **die Registerkarte Anlagen.**</span><span class="sxs-lookup"><span data-stu-id="ae509-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="ae509-207">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="ae509-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ae509-208">**Date**</span><span class="sxs-lookup"><span data-stu-id="ae509-208">**Date**</span></span>
- <span data-ttu-id="ae509-209">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="ae509-209">**Submission ID**</span></span>
- <span data-ttu-id="ae509-210">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ae509-211">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="ae509-212">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="ae509-212">**Submission type**</span></span>
- <span data-ttu-id="ae509-213">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="ae509-214"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae509-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="ae509-215">Anzeigen von Benutzerübermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="ae509-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="ae509-216">Wenn Sie das Berichtsnachrichten-Add-In , das  [Phishing-Add-In](enable-the-report-phish-add-in.md)Melden oder Personen, die die integrierte Berichterstellung [in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)im Web verwenden, bereitgestellt haben, können Sie auf der Registerkarte Benutzerübermittlungen anzeigen, welche Benutzer melden. [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="ae509-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="ae509-217">Wechseln Sie im Security & Compliance Center zu Übermittlungen **der** \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="ae509-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="ae509-218">Wählen Sie **die Registerkarte Benutzerübermittlungen** aus, und klicken Sie dann auf **Neue Übermittlung**.</span><span class="sxs-lookup"><span data-stu-id="ae509-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="ae509-219">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="ae509-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ae509-220">**Gesendet am**</span><span class="sxs-lookup"><span data-stu-id="ae509-220">**Submitted on**</span></span>
- <span data-ttu-id="ae509-221">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ae509-222">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ae509-223">**Sender**</span><span class="sxs-lookup"><span data-stu-id="ae509-223">**Sender**</span></span>
- <span data-ttu-id="ae509-224">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ae509-225">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="ae509-225">**Submission type**</span></span>

<span data-ttu-id="ae509-226"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae509-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="ae509-227">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Sender** filtern, indem Sie einen Wert in das Feld eingeben und auf Aktualisieren ![ ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="ae509-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ae509-228">Mehrere Werte können durch Kommata getrennt eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ae509-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ae509-229">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Absender,** und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="ae509-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="ae509-230">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="ae509-230">**Sender domain**</span></span>
- <span data-ttu-id="ae509-231">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="ae509-231">**Subject**</span></span>
- <span data-ttu-id="ae509-232">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="ae509-232">**Submitted by**</span></span>
- <span data-ttu-id="ae509-233">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="ae509-233">**Submission type**</span></span>
- <span data-ttu-id="ae509-234">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="ae509-234">**Sender IP**</span></span>

![Filteroptionen für Benutzerübermittlungen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="ae509-236">Klicken Sie zum Exportieren der Ergebnisse **am** oberen Rand der Seite auf Exportieren, und wählen Sie **Diagrammdaten** oder **Tabelle aus.**</span><span class="sxs-lookup"><span data-stu-id="ae509-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ae509-237">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="ae509-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="ae509-238">Anzeigen von Benutzerübermittlungen an das benutzerdefinierte Postfach</span><span class="sxs-lookup"><span data-stu-id="ae509-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="ae509-239">**Wenn** Sie ein [benutzerdefiniertes](user-submission.md) Postfach für den Empfang von vom Benutzer gemeldeten Nachrichten konfiguriert haben, können Sie Nachrichten anzeigen und auch übermitteln, die an das Berichtspostfach übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="ae509-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="ae509-240">Wechseln Sie im Security & Compliance Center zu Übermittlungen **der** \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="ae509-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="ae509-241">Wählen Sie die **Registerkarte Benutzerdefiniertes Postfach** aus.</span><span class="sxs-lookup"><span data-stu-id="ae509-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="ae509-242">Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="ae509-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ae509-243">**Gesendet am**</span><span class="sxs-lookup"><span data-stu-id="ae509-243">**Submitted on**</span></span>
- <span data-ttu-id="ae509-244">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ae509-245">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ae509-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="ae509-246">**Sender**</span></span>
- <span data-ttu-id="ae509-247">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ae509-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ae509-248">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="ae509-248">**Submission type**</span></span>

<span data-ttu-id="ae509-249">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum eingeben und nach **Übermittelt** filtern, indem Sie in das Feld einen Wert eingeben und auf Aktualisieren ![ ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="ae509-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ae509-250">Mehrere Werte können durch Kommata getrennt eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ae509-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ae509-251">Klicken Sie zum Exportieren der Ergebnisse **am** oberen Rand der Seite auf Exportieren, und wählen Sie **Diagrammdaten** oder **Tabelle aus.**</span><span class="sxs-lookup"><span data-stu-id="ae509-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ae509-252">Speichern Sie im angezeigten Dialogfeld die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="ae509-252">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="ae509-253">Rückgängig machen von Benutzerübermittlungen</span><span class="sxs-lookup"><span data-stu-id="ae509-253">Undo user submissions</span></span>

<span data-ttu-id="ae509-254">Sobald ein Benutzer eine verdächtige E-Mail an das benutzerdefinierte Postfach übermittelt hat, haben der Benutzer und der Administrator keine Möglichkeit, die Übermittlung rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="ae509-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="ae509-255">Wenn der Benutzer die E-Mail wiederherstellen möchte, steht sie für die Wiederherstellung in den Ordnern Gelöschte Elemente oder Junk-E-Mail zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ae509-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="ae509-256">Senden von Nachrichten an Microsoft aus dem benutzerdefinierten Postfach</span><span class="sxs-lookup"><span data-stu-id="ae509-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="ae509-257">Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass von Benutzern gemeldete Nachrichten abgefangen werden, ohne die Nachrichten an Microsoft zu senden, können Sie bestimmte Nachrichten zur Analyse finden und an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="ae509-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="ae509-258">Dadurch wird eine Benutzerübermittlung effektiv in eine Administratorübermittlung verlagert.</span><span class="sxs-lookup"><span data-stu-id="ae509-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="ae509-259">Wählen Sie **auf der** Registerkarte Benutzerdefiniertes Postfach  eine Nachricht in der Liste aus, klicken Sie auf die Schaltfläche Aktion, und treffen Sie eine der folgenden Auswahlen:</span><span class="sxs-lookup"><span data-stu-id="ae509-259">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="ae509-260">**Bericht bereinigen**</span><span class="sxs-lookup"><span data-stu-id="ae509-260">**Report clean**</span></span>
- <span data-ttu-id="ae509-261">**Melden von Phishing**</span><span class="sxs-lookup"><span data-stu-id="ae509-261">**Report phishing**</span></span>
- <span data-ttu-id="ae509-262">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="ae509-262">**Report malware**</span></span>
- <span data-ttu-id="ae509-263">**Melden von Spam**</span><span class="sxs-lookup"><span data-stu-id="ae509-263">**Report spam**</span></span>

![Optionen auf der Schaltfläche Aktion](../../media/user-submission-custom-mailbox-action-button.png)
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
description: Administratoren können erfahren, wie Sie das Übermittlungsportal im Microsoft 365 Security Center verwenden, um verdächtige E-Mails, verdächtige Phishing-E-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und E-Mail-Anlagen zur erneuten Überprüfung an Microsoft zu senden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6de6a018a96407a5690249bea15e90c2f5a0d1ed
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878688"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="018d4-103">Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="018d4-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="018d4-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="018d4-104">**Applies to**</span></span>
- [<span data-ttu-id="018d4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="018d4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="018d4-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="018d4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="018d4-107">In Microsoft 365 Organisationen mit Postfächern in Exchange Online können Administratoren das Übermittlungsportal im Security & Compliance Center verwenden, um E-Mail-Nachrichten, URLs und Anlagen zur Überprüfung an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="018d4-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="018d4-108">Wenn Sie eine E-Mail-Nachricht übermitteln, erhalten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="018d4-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="018d4-109">**E-Mail-Authentifizierungsprüfung:** Details dazu, ob die E-Mail-Authentifizierung bei der Zustellung erfolgreich war oder fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="018d4-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="018d4-110">**Richtlinientreffer:** Informationen zu allen Richtlinien, die eingehende E-Mails in Ihrem Mandanten möglicherweise zugelassen oder blockiert haben, und überschreiben unsere Dienstfilterbewertungen.</span><span class="sxs-lookup"><span data-stu-id="018d4-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="018d4-111">**Nutzlastreputation/-detonation:** Untersuchung aller URLs und Anlagen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="018d4-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="018d4-112">**Benotungsanalyse:** Überprüfung durch Benotungsprüfer, um zu überprüfen, ob Nachrichten bösartig sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="018d4-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="018d4-113">Nutzlastreputation/-detonation und Bewertungsanalyse werden nicht in allen Mandanten durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="018d4-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="018d4-114">Informationen werden daran gehindert, sich außerhalb der Organisation zu befinden, wenn Daten die Mandantengrenze nicht zu Compliancezwecken verlassen sollen.</span><span class="sxs-lookup"><span data-stu-id="018d4-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="018d4-115">Weitere Möglichkeiten zum Übermitteln von E-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter "Melden von [Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="018d4-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="018d4-116">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="018d4-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="018d4-117">Sie öffnen das Microsoft 365 Security Center unter <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="018d4-117">You open the Microsoft 365 security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="018d4-118">Um direkt zur Seite **"Übermittlungen"** zu wechseln, verwenden Sie <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="018d4-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="018d4-119">Um Nachrichten und Dateien an Microsoft zu übermitteln, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="018d4-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="018d4-120">**Organisationsverwaltung** oder **Sicherheitsleseberechtigter** im [Microsoft 365 Security Center.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="018d4-120">**Organization Management** or **Security Reader** in the [Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>

  - <span data-ttu-id="018d4-121">**Organisationsverwaltung** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="018d4-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="018d4-122">Beachten Sie, dass die Mitgliedschaft in dieser Rollengruppe erforderlich ist, um [Benutzerübermittlungen an das benutzerdefinierte Postfach anzuzeigen,](#view-user-submissions-to-the-custom-mailbox) wie weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="018d4-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="018d4-123">Weitere Informationen dazu, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter ["Melden von Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="018d4-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="018d4-124">Melden verdächtiger Inhalte an Microsoft</span><span class="sxs-lookup"><span data-stu-id="018d4-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="018d4-125">Wechseln Sie im [Microsoft 365 Security Center](../defender/overview-security-center.md)zu **"Übermittlungen",** und überprüfen Sie, ob Sie sich auf der Registerkarte **"Zur Analyse übermittelt"** befinden, und klicken Sie dann zur Überprüfung auf **"An Microsoft übermitteln".**</span><span class="sxs-lookup"><span data-stu-id="018d4-125">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Submissions** and verify that you're on the **Submitted for analysis** tab, and then click **Submit to Microsoft for review**.</span></span>

2. <span data-ttu-id="018d4-126">Verwenden Sie das Flyout **"An Microsoft übermitteln" zum Überprüfen** des Flyouts, das die Nachricht, URL oder E-Mail-Anlage wie in den folgenden Abschnitten beschrieben zu übermitteln scheint.</span><span class="sxs-lookup"><span data-stu-id="018d4-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="018d4-127">Senden einer fragebaren E-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="018d4-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="018d4-128">Wählen Sie im Abschnitt **"Übermittlungstyp auswählen" die** Option **"E-Mail**" aus.</span><span class="sxs-lookup"><span data-stu-id="018d4-128">In the **Select the submission type** section, select **Email**.</span></span> <span data-ttu-id="018d4-129">Verwenden Sie im Abschnitt **"Netzwerknachrichten-ID hinzufügen" oder "E-Mail-Datei hochladen"** eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="018d4-129">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>

   - <span data-ttu-id="018d4-130">**Fügen Sie die E-Mail-Netzwerknachrichten-ID** hinzu: Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-Id-Header** in der Nachricht oder im **X-MS-Office365-Filtering-Correlation-Id-Header** in isolierten Nachrichten verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="018d4-130">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="018d4-131">**Hochladen die E-Mail-Datei:** Klicken Sie auf **"Dateien durchsuchen".**</span><span class="sxs-lookup"><span data-stu-id="018d4-131">**Upload the email file**: Click **Browse files**.</span></span> <span data-ttu-id="018d4-132">Suchen Sie im daraufhin geöffneten Dialogfeld die EML- oder MSG-Datei, und wählen Sie sie aus, und klicken Sie dann auf **"Öffnen".**</span><span class="sxs-lookup"><span data-stu-id="018d4-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="018d4-133">Die Möglichkeit, Nachrichten ab 30 Tagen zu übermitteln, wurde für Defender für Office 365 Kunden vorübergehend ausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="018d4-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="018d4-134">Administratoren können nur 7 Tage zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="018d4-134">Admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="018d4-135">Geben Sie im Abschnitt **"Empfänger auswählen, der ein Problem hatte"** den Empfänger an, für den Sie eine Richtlinienüberprüfung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="018d4-135">In the **Choose a recipient who had an issue** section, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="018d4-136">Die Richtlinienüberprüfung bestimmt, ob die Überprüfung durch die E-Mail aufgrund von Benutzer- oder Organisationsrichtlinien umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="018d4-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="018d4-137">Wählen Sie im Abschnitt **"Auswählen eines Grunds für die Übermittlung an Microsoft"** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="018d4-137">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>

   - <span data-ttu-id="018d4-138">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="018d4-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="018d4-139">**Sollte blockiert worden sein:** Wählen Sie **Spam,** **Phishing** oder **Schadsoftware** aus.</span><span class="sxs-lookup"><span data-stu-id="018d4-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="018d4-140">Wenn Sie nicht sicher sind, verwenden Sie Ihr bestes Ermessen.</span><span class="sxs-lookup"><span data-stu-id="018d4-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="018d4-141">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="018d4-141">When you're finished, click the **Submit** button.</span></span>

   ![Beispiel für neue URL-Übermittlung](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="018d4-143">Senden einer verdächtigen URL an Microsoft</span><span class="sxs-lookup"><span data-stu-id="018d4-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="018d4-144">Wählen Sie im Abschnitt **"Übermittlungstyp auswählen" die** **URL** aus.</span><span class="sxs-lookup"><span data-stu-id="018d4-144">In the **Select the submission type** section, select **URL**.</span></span> <span data-ttu-id="018d4-145">Geben Sie in das angezeigte Feld die vollständige URL ein (z. B. `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="018d4-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="018d4-146">Wählen Sie im Abschnitt **"Grund für Übermittlung"** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="018d4-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="018d4-147">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="018d4-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="018d4-148">Sollte blockiert worden sein: **Phishing** oder **Schadsoftware** auswählen. </span><span class="sxs-lookup"><span data-stu-id="018d4-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="018d4-149">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="018d4-149">When you're finished, click the **Submit** button.</span></span>

   ![Beispiel für neue E-Mail-Übermittlung](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="018d4-151">Übermitteln einer verdächtigen E-Mail-Anlage an Microsoft</span><span class="sxs-lookup"><span data-stu-id="018d4-151">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="018d4-152">Wählen Sie im Abschnitt **"Übermittlungstyp auswählen" die** Option **E-Mail-Anlage** aus.</span><span class="sxs-lookup"><span data-stu-id="018d4-152">In the **Select the submission type** section, select **Email attachment**.</span></span>

2. <span data-ttu-id="018d4-153">Klicken Sie auf **"Datei auswählen".**</span><span class="sxs-lookup"><span data-stu-id="018d4-153">Click **Choose File**.</span></span> <span data-ttu-id="018d4-154">Suchen Sie im daraufhin geöffneten Dialogfeld die Datei, wählen Sie sie aus, und klicken Sie dann auf **"Öffnen".**</span><span class="sxs-lookup"><span data-stu-id="018d4-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="018d4-155">Wählen Sie im Abschnitt **"Grund für Übermittlung"** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="018d4-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="018d4-156">**Sollte nicht blockiert worden sein**</span><span class="sxs-lookup"><span data-stu-id="018d4-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="018d4-157">**Sollte blockiert worden sein:** **Schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="018d4-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="018d4-158">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="018d4-158">When you're finished, click the **Submit** button.</span></span>

   ![Beispiel für die Übermittlung neuer Anlagen](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="018d4-160">Anzeigen von Elementen, die für die Analyse übermittelt wurden</span><span class="sxs-lookup"><span data-stu-id="018d4-160">View items Submitted for analysis</span></span>

<span data-ttu-id="018d4-161">Wechseln Sie im Microsoft 365 Security Center zu **Übermittlungen,** und vergewissern Sie sich, dass Sie sich auf der Registerkarte **"Zur Analyse übermittelt"** befinden.</span><span class="sxs-lookup"><span data-stu-id="018d4-161">In the Microsoft 365 security center, go to **Submissions**, and verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="018d4-162">In der Befehlsleiste in der Mitte der Seite können Sie ein Startdatum, ein Enddatum eingeben und (standardmäßig) sie können nach **Übermittlungs-ID** (einem GUID-Wert, der jeder Übermittlung zugewiesen ist) filtern, indem Sie einen Wert in das Feld eingeben und auf ![ die Schaltfläche "Aktualisieren" ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="018d4-162">In the command bar in the middle of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="018d4-163">Mehrere Werte können durch Kommata getrennt eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="018d4-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="018d4-164">Um die Filterkriterien zu ändern, klicken Sie auf die Schaltfläche **"Filter",** und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="018d4-164">To change the filter criteria, click the **Filter** button and choose one of the following values:</span></span>

- <span data-ttu-id="018d4-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="018d4-165">**Sender**</span></span>
- <span data-ttu-id="018d4-166">**Betreff/URL/Dateiname**</span><span class="sxs-lookup"><span data-stu-id="018d4-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="018d4-167">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="018d4-167">**Submitted by**</span></span>
- <span data-ttu-id="018d4-168">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="018d4-168">**Submission type**</span></span>
- <span data-ttu-id="018d4-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="018d4-169">**Status**</span></span>

![Neue Filteroptionen für Administratorübermittlungen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="018d4-171">Um die Ergebnisse zu exportieren, klicken Sie oben auf der Seite auf **"Exportieren",** und wählen Sie **Diagrammdaten** oder **Tabelle** aus.</span><span class="sxs-lookup"><span data-stu-id="018d4-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="018d4-172">Speichern Sie im daraufhin angezeigten Dialogfeld die .csv Datei.</span><span class="sxs-lookup"><span data-stu-id="018d4-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="018d4-173">Unterhalb des Diagramms befinden sich drei Registerkarten: **E-Mail** (Standard), **URL** und **E-Mail-Anlage.**</span><span class="sxs-lookup"><span data-stu-id="018d4-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Email attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="018d4-174">Anzeigen von Administrator-E-Mail-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="018d4-174">View admin email submissions</span></span>

<span data-ttu-id="018d4-175">Sie können auf die Schaltfläche **"Spalten anpassen"** am unteren Rand der Seite klicken, um Der Ansicht Spalten hinzuzufügen oder daraus zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="018d4-175">You can click the **Customize columns** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="018d4-176">**Date**</span><span class="sxs-lookup"><span data-stu-id="018d4-176">**Date**</span></span>
- <span data-ttu-id="018d4-177">**Übermittlungs-ID:** Ein GUID-Wert, der jeder Übermittlung zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="018d4-177">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="018d4-178">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-178">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="018d4-179">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-179">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="018d4-180">**Sender**</span><span class="sxs-lookup"><span data-stu-id="018d4-180">**Sender**</span></span>
- <span data-ttu-id="018d4-181">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-181">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="018d4-182">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="018d4-182">**Submission type**</span></span>
- <span data-ttu-id="018d4-183">**Übermittlungsgrund**</span><span class="sxs-lookup"><span data-stu-id="018d4-183">**Delivery reason**</span></span>
- <span data-ttu-id="018d4-184">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-184">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="018d4-185"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="018d4-185"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="018d4-186">Details zur erneuten Überprüfung der Administratorübermittlung</span><span class="sxs-lookup"><span data-stu-id="018d4-186">Admin submission rescan details</span></span>

<span data-ttu-id="018d4-187">Nachrichten, die in Administratorübermittlungen übermittelt werden, werden erneut überprüft, und die Ergebnisse werden im Flyout "Übermittlungsdetails" angezeigt:</span><span class="sxs-lookup"><span data-stu-id="018d4-187">Messages that are submitted in admin submissions are rescanned and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="018d4-188">Mögliche Fehler in der E-Mail-Authentifizierung des Absenders zum Zeitpunkt der Auslieferung.</span><span class="sxs-lookup"><span data-stu-id="018d4-188">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="018d4-189">Informationen zu Richtlinientreffern, welche die Bewertung über einer Nachricht beeinflusst oder überschrieben haben könnten.</span><span class="sxs-lookup"><span data-stu-id="018d4-189">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="018d4-190">Aktuelle Detonationsergebnisse, um festzustellen, ob die in der Nachricht enthaltenen URLs oder Dateien böswillig waren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="018d4-190">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="018d4-191">Feedback von Benotungsprüfern.</span><span class="sxs-lookup"><span data-stu-id="018d4-191">Feedback from graders.</span></span>

<span data-ttu-id="018d4-192">Wenn eine Überschreibung gefunden wurde, sollte der erneute Scan in einigen Minuten abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="018d4-192">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="018d4-193">Wenn es kein Problem bei der E-Mail-Authentifizierung gab oder die Zustellung nicht von einer Außerkraftsetzung betroffen war, kann das Feedback von Bewertern bis zu einem Tag dauern.</span><span class="sxs-lookup"><span data-stu-id="018d4-193">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="018d4-194">Anzeigen von Administrator-URL-Übermittlungen</span><span class="sxs-lookup"><span data-stu-id="018d4-194">View admin URL submissions</span></span>

<span data-ttu-id="018d4-195">Klicken Sie auf die **Registerkarte "URL".**</span><span class="sxs-lookup"><span data-stu-id="018d4-195">Click the **URL** tab.</span></span>

<span data-ttu-id="018d4-196">Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Der Ansicht Spalten hinzuzufügen oder daraus zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="018d4-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="018d4-197">**Date**</span><span class="sxs-lookup"><span data-stu-id="018d4-197">**Date**</span></span>
- <span data-ttu-id="018d4-198">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="018d4-198">**Submission ID**</span></span>
- <span data-ttu-id="018d4-199">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="018d4-200">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-200">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="018d4-201">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="018d4-201">**Submission type**</span></span>
- <span data-ttu-id="018d4-202">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="018d4-203"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="018d4-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-email-attachment-submissions"></a><span data-ttu-id="018d4-204">Anzeigen von Übermittlungen von E-Mail-Anlagen</span><span class="sxs-lookup"><span data-stu-id="018d4-204">View email attachment submissions</span></span>

<span data-ttu-id="018d4-205">Klicken Sie auf die Registerkarte **"Anlagen".**</span><span class="sxs-lookup"><span data-stu-id="018d4-205">Click the **Attachments** tab.</span></span>

<span data-ttu-id="018d4-206">Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Der Ansicht Spalten hinzuzufügen oder daraus zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="018d4-206">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="018d4-207">**Date**</span><span class="sxs-lookup"><span data-stu-id="018d4-207">**Date**</span></span>
- <span data-ttu-id="018d4-208">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="018d4-208">**Submission ID**</span></span>
- <span data-ttu-id="018d4-209">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-209">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="018d4-210">**Dateiname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-210">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="018d4-211">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="018d4-211">**Submission type**</span></span>
- <span data-ttu-id="018d4-212">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-212">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="018d4-213"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="018d4-213"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="018d4-214">Anzeigen von Benutzerübermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="018d4-214">View user submissions to Microsoft</span></span>

<span data-ttu-id="018d4-215">Wenn Sie das [Add-In "Nachricht melden",](enable-the-report-message-add-in.md)das [Add-In "Phishing melden"](enable-the-report-phish-add-in.md)bereitgestellt haben oder Personen die [integrierte Berichterstellung in Outlook im Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)verwenden, können Sie sehen, welche Benutzer auf der Registerkarte **"Benutzerübermittlungen"** Berichte erstellen.</span><span class="sxs-lookup"><span data-stu-id="018d4-215">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="018d4-216">Wechseln Sie im Security & Compliance  Center zu \> **Übermittlungen zur Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="018d4-216">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="018d4-217">Wählen Sie die Registerkarte **"Benutzerübermittlungen" aus,** und klicken Sie dann auf **"Neue Übermittlung".**</span><span class="sxs-lookup"><span data-stu-id="018d4-217">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="018d4-218">Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Der Ansicht Spalten hinzuzufügen oder daraus zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="018d4-218">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="018d4-219">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="018d4-219">**Submitted on**</span></span>
- <span data-ttu-id="018d4-220">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-220">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="018d4-221">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-221">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="018d4-222">**Sender**</span><span class="sxs-lookup"><span data-stu-id="018d4-222">**Sender**</span></span>
- <span data-ttu-id="018d4-223">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-223">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="018d4-224">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="018d4-224">**Submission type**</span></span>

<span data-ttu-id="018d4-225"><sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="018d4-225"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="018d4-226">Im oberen Bereich der Seite können Sie ein Startdatum, ein Enddatum eingeben und (standardmäßig) nach **Absender** filtern, indem Sie einen Wert in das Feld eingeben und auf die ![ Schaltfläche "Aktualisieren" ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="018d4-226">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="018d4-227">Mehrere Werte können durch Kommata getrennt eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="018d4-227">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="018d4-228">Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **"Absender",** und wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="018d4-228">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="018d4-229">**Absenderdomäne**</span><span class="sxs-lookup"><span data-stu-id="018d4-229">**Sender domain**</span></span>
- <span data-ttu-id="018d4-230">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="018d4-230">**Subject**</span></span>
- <span data-ttu-id="018d4-231">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="018d4-231">**Submitted by**</span></span>
- <span data-ttu-id="018d4-232">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="018d4-232">**Submission type**</span></span>
- <span data-ttu-id="018d4-233">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="018d4-233">**Sender IP**</span></span>

![Neue Filteroptionen für Benutzerübermittlungen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="018d4-235">Um die Ergebnisse zu exportieren, klicken Sie oben auf der Seite auf **"Exportieren",** und wählen Sie **Diagrammdaten** oder **Tabelle** aus.</span><span class="sxs-lookup"><span data-stu-id="018d4-235">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="018d4-236">Speichern Sie im daraufhin angezeigten Dialogfeld die .csv Datei.</span><span class="sxs-lookup"><span data-stu-id="018d4-236">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="018d4-237">Anzeigen von Benutzerübermittlungen an das benutzerdefinierte Postfach</span><span class="sxs-lookup"><span data-stu-id="018d4-237">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="018d4-238">**Wenn** Sie [ein benutzerdefiniertes Postfach für](user-submission.md) den Empfang von vom Benutzer gemeldeten Nachrichten konfiguriert haben, können Sie Nachrichten anzeigen und auch senden, die an das Berichtspostfach übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="018d4-238">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="018d4-239">Wechseln Sie im Security & Compliance  Center zu \> **Übermittlungen zur Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="018d4-239">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="018d4-240">Wählen Sie die Registerkarte **"Benutzerdefiniertes Postfach"** aus.</span><span class="sxs-lookup"><span data-stu-id="018d4-240">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="018d4-241">Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Der Ansicht Spalten hinzuzufügen oder daraus zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="018d4-241">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="018d4-242">**Übermittelt am**</span><span class="sxs-lookup"><span data-stu-id="018d4-242">**Submitted on**</span></span>
- <span data-ttu-id="018d4-243">**Übermittelt von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-243">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="018d4-244">**Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-244">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="018d4-245">**Sender**</span><span class="sxs-lookup"><span data-stu-id="018d4-245">**Sender**</span></span>
- <span data-ttu-id="018d4-246">**Sender-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="018d4-246">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="018d4-247">**Übermittlungstyp**</span><span class="sxs-lookup"><span data-stu-id="018d4-247">**Submission type**</span></span>

<span data-ttu-id="018d4-248">Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum eingeben und nach **"Übermittelt"** filtern, indem Sie einen Wert in das Feld eingeben und auf die ![ Schaltfläche "Aktualisieren" ](../../media/scc-quarantine-refresh.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="018d4-248">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="018d4-249">Mehrere Werte können durch Kommata getrennt eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="018d4-249">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="018d4-250">Um die Ergebnisse zu exportieren, klicken Sie oben auf der Seite auf **"Exportieren",** und wählen Sie **Diagrammdaten** oder **Tabelle** aus.</span><span class="sxs-lookup"><span data-stu-id="018d4-250">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="018d4-251">Speichern Sie im daraufhin angezeigten Dialogfeld die .csv Datei.</span><span class="sxs-lookup"><span data-stu-id="018d4-251">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="018d4-252">Wenn Organisationen so konfiguriert sind, dass sie nur an ein benutzerdefiniertes Postfach senden, werden gemeldete Nachrichten nicht zur erneuten Überprüfung gesendet, und die Ergebnisse im Portal für vom Benutzer gemeldete Nachrichten sind immer leer.</span><span class="sxs-lookup"><span data-stu-id="018d4-252">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="018d4-253">Rückgängigmachen von Benutzerübermittlungen</span><span class="sxs-lookup"><span data-stu-id="018d4-253">Undo user submissions</span></span>

<span data-ttu-id="018d4-254">Sobald ein Benutzer eine verdächtige E-Mail an das benutzerdefinierte Postfach sendet, haben der Benutzer und der Administrator keine Möglichkeit, die Übermittlung rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="018d4-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="018d4-255">Wenn der Benutzer die E-Mail wiederherstellen möchte, steht sie für die Wiederherstellung in den Ordnern "Gelöschte Elemente" oder "Junk-E-Mail" zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="018d4-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="018d4-256">Senden von Nachrichten aus dem benutzerdefinierten Postfach an Microsoft</span><span class="sxs-lookup"><span data-stu-id="018d4-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="018d4-257">Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass von Benutzern gemeldete Nachrichten abgefangen werden, ohne die Nachrichten an Microsoft zu senden, können Sie bestimmte Nachrichten suchen und zur Analyse an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="018d4-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="018d4-258">Dadurch wird eine Benutzerübermittlung effektiv an eine Administratorübermittlung verschoben.</span><span class="sxs-lookup"><span data-stu-id="018d4-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="018d4-259">Wählen Sie auf der Registerkarte **"Vom Benutzer gemeldete Nachrichten"** eine Nachricht in der Liste aus, klicken Sie auf die Schaltfläche **"Aktion",** und wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="018d4-259">On the **User reported messages** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="018d4-260">**Bericht sauber**</span><span class="sxs-lookup"><span data-stu-id="018d4-260">**Report clean**</span></span>
- <span data-ttu-id="018d4-261">**Melden von Phishing**</span><span class="sxs-lookup"><span data-stu-id="018d4-261">**Report phishing**</span></span>
- <span data-ttu-id="018d4-262">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="018d4-262">**Report malware**</span></span>
- <span data-ttu-id="018d4-263">**Melden von Spam**</span><span class="sxs-lookup"><span data-stu-id="018d4-263">**Report spam**</span></span>

![Neue Optionen auf der Schaltfläche "Aktion"](../../media/user-submission-custom-mailbox-action-button.png)

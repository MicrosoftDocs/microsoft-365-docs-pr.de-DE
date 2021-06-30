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
description: Administratoren können erfahren, wie Sie das Übermittlungsportal im Microsoft 365 Defender-Portal verwenden, um verdächtige E-Mails, verdächtige Phishing-E-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und E-Mail-Anlagen zur erneuten Überprüfung an Microsoft zu übermitteln.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eecb635972be85e1a1a4f95c2786f209ee249745
ms.sourcegitcommit: 99e67bfe1d677c2f51712b05dcc54908b343cf6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53203280"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="c352f-103">Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="c352f-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c352f-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="c352f-104">**Applies to**</span></span>
- [<span data-ttu-id="c352f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c352f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c352f-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="c352f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="c352f-107">In Microsoft 365 Organisationen mit Exchange Online Postfächern können Administratoren das Übermittlungsportal im Microsoft 365 Defender-Portal verwenden, um E-Mail-Nachrichten, URLs und Anlagen zur Überprüfung an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="c352f-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="c352f-108">Wenn Sie eine E-Mail-Nachricht übermitteln, erhalten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c352f-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="c352f-109">**E-Mail-Authentifizierungsprüfung:** Details dazu, ob die E-Mail-Authentifizierung bei der Zustellung erfolgreich war oder fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="c352f-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="c352f-110">**Richtlinientreffer:** Informationen zu allen Richtlinien, die eingehende E-Mails möglicherweise in Ihrem Mandanten zugelassen oder blockiert haben, und überschreiben unsere Dienstfilterbewertungen.</span><span class="sxs-lookup"><span data-stu-id="c352f-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="c352f-111">**Nutzlastreputation/-detonation:** Untersuchung aller URLs und Anlagen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="c352f-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="c352f-112">**Benotungsanalyse:** Überprüfung durch Benotungsprüfer, um zu überprüfen, ob Nachrichten bösartig sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="c352f-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c352f-113">Nutzlastreputation/-detonation und Bewertungsanalyse werden nicht in allen Mandanten durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="c352f-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="c352f-114">Informationen werden daran gehindert, sich außerhalb der Organisation zu befinden, wenn Daten die Mandantengrenze nicht zu Compliancezwecken verlassen sollen.</span><span class="sxs-lookup"><span data-stu-id="c352f-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="c352f-115">Weitere Möglichkeiten zum Übermitteln von E-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter "Melden von [Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="c352f-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c352f-116">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="c352f-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c352f-117">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="c352f-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="c352f-118">Um direkt zur Seite **"Übermittlungen"** zu wechseln, verwenden Sie <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="c352f-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="c352f-119">Um Nachrichten und Dateien an Microsoft zu übermitteln, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="c352f-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="c352f-120">**Organisationsverwaltung** oder **Sicherheitsleseberechtigter** im [Microsoft 365 Defender Portal.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="c352f-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  
    <span data-ttu-id="c352f-121">Beachten Sie, dass die Mitgliedschaft in dieser Rollengruppe erforderlich ist, um [Benutzerübermittlungen an das benutzerdefinierte Postfach anzuzeigen,](#view-user-submissions-to-microsoft) wie weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c352f-121">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="c352f-122">Weitere Informationen dazu, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter ["Melden von Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="c352f-122">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="c352f-123">Melden verdächtiger Inhalte an Microsoft</span><span class="sxs-lookup"><span data-stu-id="c352f-123">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="c352f-124">Wechseln Sie im Microsoft 365 Defender Portal zu **E-Mail-&** \> **Übermittlungen für** die Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="c352f-124">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="c352f-125">Überprüfen Sie auf der Seite **"Übermittlungen",** ob die Registerkarte **"Für Analyse übermittelt"** ausgewählt ist, und klicken Sie dann auf das ![ Symbol ](../../media/m365-cc-sc-create-icon.png) **"An Microsoft zur Analyse übermitteln".**</span><span class="sxs-lookup"><span data-stu-id="c352f-125">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="c352f-126">Verwenden Sie das Flyout **"An Microsoft übermitteln" zum Überprüfen** des Flyouts, das die Nachricht, URL oder E-Mail-Anlage wie in den folgenden Abschnitten beschrieben zu übermitteln scheint.</span><span class="sxs-lookup"><span data-stu-id="c352f-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="c352f-127">Senden einer fragebaren E-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="c352f-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="c352f-128">Überprüfen Sie im Feld **"Übermittlungstyp auswählen",** ob **"E-Mail"** in der Dropdownliste ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c352f-128">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="c352f-129">Verwenden Sie im Abschnitt **"Netzwerknachrichten-ID hinzufügen" oder "E-Mail-Datei hochladen"** eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="c352f-129">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="c352f-130">**Fügen Sie die E-Mail-Netzwerknachrichten-ID** hinzu: Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-Id-Header** in der Nachricht oder im **X-MS-Office365-Filtering-Correlation-Id-Header** in isolierten Nachrichten verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c352f-130">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="c352f-131">**Hochladen die E-Mail-Datei (MSG oder EML):** Klicken Sie auf **"Dateien durchsuchen".**</span><span class="sxs-lookup"><span data-stu-id="c352f-131">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="c352f-132">Suchen Sie im daraufhin geöffneten Dialogfeld die EML- oder MSG-Datei, und wählen Sie sie aus, und klicken Sie dann auf **"Öffnen".**</span><span class="sxs-lookup"><span data-stu-id="c352f-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c352f-133">Die Möglichkeit, Nachrichten ab 30 Tagen zu übermitteln, wurde für Defender für Office 365 Kunden vorübergehend ausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="c352f-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="c352f-134">Administratoren können nur 7 Tage zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="c352f-134">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="c352f-135">Geben Sie im Feld **"Empfänger auswählen, der ein Problem hatte"** den Empfänger an, für den Sie eine Richtlinienüberprüfung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="c352f-135">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="c352f-136">Die Richtlinienüberprüfung bestimmt, ob die Überprüfung durch die E-Mail aufgrund von Benutzer- oder Organisationsrichtlinien umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="c352f-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="c352f-137">Wählen Sie im Abschnitt **"Auswählen eines Grunds für die Übermittlung an Microsoft"** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="c352f-137">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="c352f-138">**Sollte nicht blockiert worden sein (falsch positiv)**</span><span class="sxs-lookup"><span data-stu-id="c352f-138">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="c352f-139">**Sollte blockiert worden sein:** In der **E-Mail sollte als angezeigter Abschnitt kategorisiert worden sein,** wählen Sie einen der folgenden Werte aus (wenn Sie nicht sicher sind, verwenden Sie Ihren besten Willen):</span><span class="sxs-lookup"><span data-stu-id="c352f-139">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="c352f-140">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="c352f-140">**Phish**</span></span>
     - <span data-ttu-id="c352f-141">**Spam**</span><span class="sxs-lookup"><span data-stu-id="c352f-141">**Spam**</span></span>
     - <span data-ttu-id="c352f-142">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="c352f-142">**Malware**</span></span>

5. <span data-ttu-id="c352f-143">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="c352f-143">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c352f-144">![Beispiel für neue URL-Übermittlung](../../media/submission-flyout-email.png)</span><span class="sxs-lookup"><span data-stu-id="c352f-144">![New URL submission example](../../media/submission-flyout-email.png)</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="c352f-145">Senden einer verdächtigen URL an Microsoft</span><span class="sxs-lookup"><span data-stu-id="c352f-145">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="c352f-146">Wählen Sie im Feld **"Übermittlungstyp auswählen"** die **URL** aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="c352f-146">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="c352f-147">Geben Sie in das angezeigte **URL-Feld** die vollständige URL ein (z. B. `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="c352f-147">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="c352f-148">Wählen Sie im Abschnitt **"Auswählen eines Grunds für die Übermittlung an Microsoft"** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="c352f-148">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="c352f-149">**Sollte nicht blockiert worden sein (falsch positiv)**</span><span class="sxs-lookup"><span data-stu-id="c352f-149">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="c352f-150">**Sollte blockiert worden sein:** In der URL sollte als angezeigter Abschnitt **kategorisiert worden sein,** wählen Sie **Phishing** oder **Schadsoftware** aus.</span><span class="sxs-lookup"><span data-stu-id="c352f-150">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="c352f-151">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="c352f-151">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c352f-152">![Beispiel für neue E-Mail-Übermittlung](../../media/submission-url-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="c352f-152">![New Email submission example](../../media/submission-url-flyout.png)</span></span>

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="c352f-153">Übermitteln einer verdächtigen E-Mail-Anlage an Microsoft</span><span class="sxs-lookup"><span data-stu-id="c352f-153">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="c352f-154">Wählen Sie im Feld **"Übermittlungstyp auswählen"** in der Dropdownliste die Option **"Datei"** aus.</span><span class="sxs-lookup"><span data-stu-id="c352f-154">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="c352f-155">Klicken Sie im angezeigten Abschnitt **"Datei"** auf **"Dateien durchsuchen".**</span><span class="sxs-lookup"><span data-stu-id="c352f-155">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="c352f-156">Suchen Sie im daraufhin geöffneten Dialogfeld die Datei, wählen Sie sie aus, und klicken Sie dann auf **"Öffnen".**</span><span class="sxs-lookup"><span data-stu-id="c352f-156">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="c352f-157">Wählen Sie im Abschnitt **"Auswählen eines Grunds für die Übermittlung an Microsoft"** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="c352f-157">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="c352f-158">**Sollte nicht blockiert worden sein (falsch positiv)**</span><span class="sxs-lookup"><span data-stu-id="c352f-158">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="c352f-159">**Sollte blockiert worden sein:** In der URL sollte als angezeigter Abschnitt **kategorisiert worden sein, schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt. </span><span class="sxs-lookup"><span data-stu-id="c352f-159">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="c352f-160">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="c352f-160">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c352f-161">![Beispiel für die Übermittlung neuer Anlagen](../../media/submission-file-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="c352f-161">![New Attachment submission example](../../media/submission-file-flyout.png)</span></span>

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="c352f-162">Anzeigen von Administratorübermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="c352f-162">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="c352f-163">Wechseln Sie im Microsoft 365 Defender Portal zu **E-Mail-&** \> **Übermittlungen für** die Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="c352f-163">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="c352f-164">Überprüfen Sie auf der Seite **"Übermittlungen",** ob die Registerkarte **"Für Analyse übermittelt"** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c352f-164">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="c352f-165">Sie können die Einträge sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="c352f-165">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="c352f-166">Klicken Sie auf **Spalten anpassen,** um maximal sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c352f-166">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="c352f-167">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="c352f-167">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="c352f-168">**Übermittlungsname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c352f-168">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="c352f-169">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c352f-169">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="c352f-170">**Übermitteltes Datum**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c352f-170">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="c352f-171">**Übermittlungstyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c352f-171">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="c352f-172">**Grund für die Übermittlung**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c352f-172">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="c352f-173">**Status des erneuten Scannens**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c352f-173">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="c352f-174">**Erneutes Scanergebnis**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c352f-174">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="c352f-175">**Filterbewertung**</span><span class="sxs-lookup"><span data-stu-id="c352f-175">**Filter verdict**</span></span>
     - <span data-ttu-id="c352f-176">**Grund für Übermittlung/Blockierung**</span><span class="sxs-lookup"><span data-stu-id="c352f-176">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="c352f-177">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="c352f-177">**Submission ID**</span></span>
     - <span data-ttu-id="c352f-178">**Netzwerknachrichten-ID/Objekt-ID**</span><span class="sxs-lookup"><span data-stu-id="c352f-178">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="c352f-179">**Direction**</span><span class="sxs-lookup"><span data-stu-id="c352f-179">**Direction**</span></span>
     - <span data-ttu-id="c352f-180">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="c352f-180">**Sender IP**</span></span>
     - <span data-ttu-id="c352f-181">**Massenkonforme Ebene (Bulk Compliant Level, BCL)**</span><span class="sxs-lookup"><span data-stu-id="c352f-181">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="c352f-182">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="c352f-182">**Destination**</span></span>
     - <span data-ttu-id="c352f-183">**Richtlinienaktion**</span><span class="sxs-lookup"><span data-stu-id="c352f-183">**Policy action**</span></span>
     - <span data-ttu-id="c352f-184">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="c352f-184">**Submitted by**</span></span>

     <span data-ttu-id="c352f-185">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="c352f-185">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="c352f-186">Klicken Sie zum Filtern der Einträge auf **"Filtern".**</span><span class="sxs-lookup"><span data-stu-id="c352f-186">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="c352f-187">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="c352f-187">The available filters are:</span></span>
     - <span data-ttu-id="c352f-188">**Übermitteltes Datum:** **Startdatum** und **Enddatum.**</span><span class="sxs-lookup"><span data-stu-id="c352f-188">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="c352f-189">**Übermittlungstyp:** **E-Mail,** **URL** oder **Datei.**</span><span class="sxs-lookup"><span data-stu-id="c352f-189">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="c352f-190">**Übermittlungs-ID:** Ein GUID-Wert, der jeder Übermittlung zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c352f-190">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="c352f-191">**Netzwerknachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="c352f-191">**Network Message ID**</span></span>
     - <span data-ttu-id="c352f-192">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c352f-192">**Sender**</span></span>

     <span data-ttu-id="c352f-193">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="c352f-193">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="c352f-194">![Neue Filteroptionen für Administratorübermittlungen](../../media/admin-submission-filters.png)</span><span class="sxs-lookup"><span data-stu-id="c352f-194">![New Filter options for admin submissions](../../media/admin-submission-filters.png)</span></span>

   - <span data-ttu-id="c352f-195">Klicken Sie zum Gruppieren der Einträge auf **"Gruppieren",** und wählen Sie einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="c352f-195">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="c352f-196">**Keine**</span><span class="sxs-lookup"><span data-stu-id="c352f-196">**None**</span></span>
     - <span data-ttu-id="c352f-197">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c352f-197">**Type**</span></span>
     - <span data-ttu-id="c352f-198">**Grund**</span><span class="sxs-lookup"><span data-stu-id="c352f-198">**Reason**</span></span>
     - <span data-ttu-id="c352f-199">**Status**</span><span class="sxs-lookup"><span data-stu-id="c352f-199">**Status**</span></span>
     - <span data-ttu-id="c352f-200">**Erneutes Scanergebnis**</span><span class="sxs-lookup"><span data-stu-id="c352f-200">**Rescan result**</span></span>

   - <span data-ttu-id="c352f-201">Klicken Sie zum Exportieren der Einträge auf **"Exportieren".**</span><span class="sxs-lookup"><span data-stu-id="c352f-201">To export the entries, click **Export**.</span></span> <span data-ttu-id="c352f-202">Speichern Sie im daraufhin angezeigten Dialogfeld die .csv Datei.</span><span class="sxs-lookup"><span data-stu-id="c352f-202">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="c352f-203">Details zur erneuten Überprüfung der Administratorübermittlung</span><span class="sxs-lookup"><span data-stu-id="c352f-203">Admin submission rescan details</span></span>

<span data-ttu-id="c352f-204">Nachrichten, die in Administratorübermittlungen übermittelt werden, werden überprüft, und die Ergebnisse werden im Flyout "Übermittlungsdetails" angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c352f-204">Messages that are submitted in admin submissions are reviewed and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="c352f-205">Mögliche Fehler in der E-Mail-Authentifizierung des Absenders zum Zeitpunkt der Auslieferung.</span><span class="sxs-lookup"><span data-stu-id="c352f-205">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="c352f-206">Informationen zu Richtlinientreffern, welche die Bewertung über einer Nachricht beeinflusst oder überschrieben haben könnten.</span><span class="sxs-lookup"><span data-stu-id="c352f-206">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="c352f-207">Aktuelle Detonationsergebnisse, um festzustellen, ob die in der Nachricht enthaltenen URLs oder Dateien böswillig waren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="c352f-207">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="c352f-208">Feedback von Benotungsprüfern.</span><span class="sxs-lookup"><span data-stu-id="c352f-208">Feedback from graders.</span></span>

<span data-ttu-id="c352f-209">Wenn eine Überschreibung gefunden wurde, sollte der erneute Scan in einigen Minuten abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="c352f-209">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="c352f-210">Wenn es kein Problem bei der E-Mail-Authentifizierung gab oder die Zustellung nicht von einer Außerkraftsetzung betroffen war, kann das Feedback von Bewertern bis zu einem Tag dauern.</span><span class="sxs-lookup"><span data-stu-id="c352f-210">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="c352f-211">Anzeigen von Benutzerübermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="c352f-211">View user submissions to Microsoft</span></span>

<span data-ttu-id="c352f-212">Wenn Sie das [Add-In "Nachricht melden",](enable-the-report-message-add-in.md)das [Add-In "Phishing melden"](enable-the-report-phish-add-in.md)bereitgestellt haben oder Benutzer die [integrierte Berichterstellung in Outlook im Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)verwenden, können Sie sehen, welche Benutzer auf der Registerkarte **"Benutzer gemeldete Nachrichten"** berichtigen.</span><span class="sxs-lookup"><span data-stu-id="c352f-212">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="c352f-213">Wechseln Sie im Microsoft 365 Defender Portal zu **E-Mail-&** \> **Übermittlungen für** die Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="c352f-213">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="c352f-214">Wählen Sie auf der Seite **"Übermittlungen"** die Registerkarte **"Vom Benutzer gemeldete Nachrichten"** aus.</span><span class="sxs-lookup"><span data-stu-id="c352f-214">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="c352f-215">Sie können die Einträge sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="c352f-215">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="c352f-216">Klicken Sie auf **Spalten anpassen,** um maximal sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c352f-216">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="c352f-217">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="c352f-217">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="c352f-218">**E-Mail-Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c352f-218">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="c352f-219">**Gemeldet von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c352f-219">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="c352f-220">**Gemeldetes Datum**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c352f-220">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="c352f-221">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c352f-221">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="c352f-222">**Gemeldeter Grund**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c352f-222">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="c352f-223">**Erneutes Scanergebnis**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c352f-223">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="c352f-224">**Gemeldete ID der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="c352f-224">**Message reported ID**</span></span>
     - <span data-ttu-id="c352f-225">**Netzwerknachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="c352f-225">**Network Message ID**</span></span>
     - <span data-ttu-id="c352f-226">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="c352f-226">**Sender IP**</span></span>
     - <span data-ttu-id="c352f-227">**Phishing-Simulation**</span><span class="sxs-lookup"><span data-stu-id="c352f-227">**Phish simulation**</span></span>

     <span data-ttu-id="c352f-228">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="c352f-228">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="c352f-229">Klicken Sie zum Filtern der Einträge auf **"Filtern".**</span><span class="sxs-lookup"><span data-stu-id="c352f-229">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="c352f-230">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="c352f-230">The available filters are:</span></span>
     - <span data-ttu-id="c352f-231">**Gemeldetes Datum**: **Startdatum** und **Enddatum.**</span><span class="sxs-lookup"><span data-stu-id="c352f-231">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="c352f-232">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="c352f-232">**Reported by**</span></span>
     - <span data-ttu-id="c352f-233">**E-Mail-Betreff**</span><span class="sxs-lookup"><span data-stu-id="c352f-233">**Email subject**</span></span>
     - <span data-ttu-id="c352f-234">**Gemeldete ID der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="c352f-234">**Message reported ID**</span></span>
     - <span data-ttu-id="c352f-235">**Netzwerknachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="c352f-235">**Network Message ID**</span></span>
     - <span data-ttu-id="c352f-236">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c352f-236">**Sender**</span></span>
     - <span data-ttu-id="c352f-237">**Gemeldeter Grund:** **keine Junk-,** **Phishing-** oder **Spam-Nachrichten.**</span><span class="sxs-lookup"><span data-stu-id="c352f-237">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="c352f-238">**Phishing-Simulation:** **Ja** oder **Nein**</span><span class="sxs-lookup"><span data-stu-id="c352f-238">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="c352f-239">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="c352f-239">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="c352f-240">![Neue Filteroptionen für Benutzerübermittlungen](../../media/admin-submission-reported-messages.png)</span><span class="sxs-lookup"><span data-stu-id="c352f-240">![New Filter options for user submissions](../../media/admin-submission-reported-messages.png)</span></span>

   - <span data-ttu-id="c352f-241">Klicken Sie zum Gruppieren der Einträge auf **"Gruppieren",** und wählen Sie einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="c352f-241">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="c352f-242">**Keine**</span><span class="sxs-lookup"><span data-stu-id="c352f-242">**None**</span></span>
     - <span data-ttu-id="c352f-243">**Grund**</span><span class="sxs-lookup"><span data-stu-id="c352f-243">**Reason**</span></span>
     - <span data-ttu-id="c352f-244">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c352f-244">**Sender**</span></span>
     - <span data-ttu-id="c352f-245">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="c352f-245">**Reported by**</span></span>
     - <span data-ttu-id="c352f-246">**Erneutes Scanergebnis**</span><span class="sxs-lookup"><span data-stu-id="c352f-246">**Rescan result**</span></span>
     - <span data-ttu-id="c352f-247">**Phishing-Simulation**</span><span class="sxs-lookup"><span data-stu-id="c352f-247">**Phish simulation**</span></span>

   - <span data-ttu-id="c352f-248">Klicken Sie zum Exportieren der Einträge auf **"Exportieren".**</span><span class="sxs-lookup"><span data-stu-id="c352f-248">To export the entries, click **Export**.</span></span> <span data-ttu-id="c352f-249">Speichern Sie im daraufhin angezeigten Dialogfeld die .csv Datei.</span><span class="sxs-lookup"><span data-stu-id="c352f-249">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="c352f-250">Wenn Organisationen so konfiguriert sind, dass von Benutzern gemeldete Nachrichten nur an das benutzerdefinierte Postfach gesendet werden, werden gemeldete Nachrichten nicht zur erneuten Überprüfung gesendet, und die Ergebnisse in **den vom Benutzer gemeldeten Nachrichten** sind immer leer.</span><span class="sxs-lookup"><span data-stu-id="c352f-250">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="c352f-251">Rückgängigmachen von Benutzerübermittlungen</span><span class="sxs-lookup"><span data-stu-id="c352f-251">Undo user submissions</span></span>

<span data-ttu-id="c352f-252">Sobald ein Benutzer eine verdächtige E-Mail an das benutzerdefinierte Postfach sendet, haben der Benutzer und der Administrator keine Möglichkeit, die Übermittlung rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="c352f-252">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="c352f-253">Wenn der Benutzer die E-Mail wiederherstellen möchte, steht sie für die Wiederherstellung in den Ordnern "Gelöschte Elemente" oder "Junk-E-Mail" zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c352f-253">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="c352f-254">Senden von Nachrichten aus dem benutzerdefinierten Postfach an Microsoft</span><span class="sxs-lookup"><span data-stu-id="c352f-254">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="c352f-255">Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass von Benutzern gemeldete Nachrichten abgefangen werden, ohne die Nachrichten an Microsoft zu senden, können Sie bestimmte Nachrichten zur Analyse suchen und an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="c352f-255">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="c352f-256">Dadurch wird eine Benutzerübermittlung effektiv an eine Administratorübermittlung verschoben.</span><span class="sxs-lookup"><span data-stu-id="c352f-256">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="c352f-257">Wählen Sie auf der Registerkarte **"Vom Benutzer gemeldete Nachrichten"** eine Nachricht in der Liste aus, klicken Sie auf **"Zur Analyse an Microsoft übermitteln",** und wählen Sie dann einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="c352f-257">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="c352f-258">**Bericht sauber**</span><span class="sxs-lookup"><span data-stu-id="c352f-258">**Report clean**</span></span>
- <span data-ttu-id="c352f-259">**Melden von Phishing**</span><span class="sxs-lookup"><span data-stu-id="c352f-259">**Report phishing**</span></span>
- <span data-ttu-id="c352f-260">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="c352f-260">**Report malware**</span></span>
- <span data-ttu-id="c352f-261">**Melden von Spam**</span><span class="sxs-lookup"><span data-stu-id="c352f-261">**Report spam**</span></span>
- <span data-ttu-id="c352f-262">**Untersuchung auslösen**</span><span class="sxs-lookup"><span data-stu-id="c352f-262">**Trigger investigation**</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c352f-263">![Neue Optionen auf der Schaltfläche "Aktion"](../../media/admin-submission-main-action-button.png)</span><span class="sxs-lookup"><span data-stu-id="c352f-263">![New Options on the Action button](../../media/admin-submission-main-action-button.png)</span></span>

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
description: Administratoren können erfahren, wie Sie das Übermittlungsportal im Microsoft 365 Defender Portal verwenden, um verdächtige E-Mails, verdächtige Phishing-E-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und E-Mail-Anlagen zur erneuten Überprüfung an Microsoft zu übermitteln.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2d18dd7f5dc702f08a722652394aeb0102f100ef
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409056"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="d01b6-103">Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="d01b6-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d01b6-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="d01b6-104">**Applies to**</span></span>
- [<span data-ttu-id="d01b6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d01b6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d01b6-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="d01b6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="d01b6-107">In Microsoft 365 Organisationen mit Exchange Online Postfächern können Administratoren das Übermittlungsportal im Microsoft 365 Defender-Portal verwenden, um E-Mail-Nachrichten, URLs und Anlagen zur Überprüfung an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="d01b6-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="d01b6-108">Wenn Sie eine E-Mail-Nachricht übermitteln, erhalten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d01b6-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="d01b6-109">**E-Mail-Authentifizierungsprüfung:** Details dazu, ob die E-Mail-Authentifizierung bei der Zustellung erfolgreich war oder fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="d01b6-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="d01b6-110">**Richtlinientreffer:** Informationen zu allen Richtlinien, die eingehende E-Mails in Ihrem Mandanten möglicherweise zugelassen oder blockiert haben, und überschreiben unsere Dienstfilterbewertungen.</span><span class="sxs-lookup"><span data-stu-id="d01b6-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="d01b6-111">**Nutzlastreputation/-detonation:** Untersuchung aller URLs und Anlagen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="d01b6-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="d01b6-112">**Benotungsanalyse:** Überprüfung durch Benotungsprüfer, um zu überprüfen, ob Nachrichten bösartig sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="d01b6-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d01b6-113">Nutzlastreputation/-detonation und Bewertungsanalyse werden nicht in allen Mandanten durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="d01b6-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="d01b6-114">Informationen werden daran gehindert, sich außerhalb der Organisation zu befinden, wenn Daten die Mandantengrenze nicht zu Compliancezwecken verlassen sollen.</span><span class="sxs-lookup"><span data-stu-id="d01b6-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="d01b6-115">Weitere Möglichkeiten zum Übermitteln von E-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter "Melden von [Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="d01b6-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d01b6-116">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="d01b6-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d01b6-117">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="d01b6-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="d01b6-118">Um direkt zur Seite **"Übermittlungen"** zu wechseln, verwenden Sie <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="d01b6-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="d01b6-119">Um Nachrichten und Dateien an Microsoft zu übermitteln, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="d01b6-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="d01b6-120">**Organisationsverwaltung** oder **Sicherheitsleseberechtigter** im [Microsoft 365 Defender Portal.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="d01b6-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  
    <span data-ttu-id="d01b6-121">Beachten Sie, dass die Mitgliedschaft in dieser Rollengruppe erforderlich ist, um [Benutzerübermittlungen an das benutzerdefinierte Postfach anzuzeigen,](#view-user-submissions-to-microsoft) wie weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d01b6-121">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="d01b6-122">Weitere Informationen dazu, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter ["Melden von Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="d01b6-122">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="d01b6-123">Melden verdächtiger Inhalte an Microsoft</span><span class="sxs-lookup"><span data-stu-id="d01b6-123">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="d01b6-124">Wechseln Sie im Microsoft 365 Defender Portal zu **E-Mail-&** \> **Übermittlungen für die** Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="d01b6-124">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="d01b6-125">Überprüfen Sie auf der Seite **"Übermittlungen",** ob die Registerkarte **"Für Analyse übermittelt"** ausgewählt ist, und klicken Sie dann auf das ![ Symbol ](../../media/m365-cc-sc-create-icon.png) **"An Microsoft zur Analyse übermitteln".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-125">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="d01b6-126">Verwenden Sie das Flyout **"An Microsoft übermitteln" zum Überprüfen** des Flyouts, das die Nachricht, URL oder E-Mail-Anlage wie in den folgenden Abschnitten beschrieben zu übermitteln scheint.</span><span class="sxs-lookup"><span data-stu-id="d01b6-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d01b6-127">Datei- und URL-Übermittlungen sind in den Clouds nicht verfügbar, die nicht zulassen, dass Daten die Umgebung verlassen.</span><span class="sxs-lookup"><span data-stu-id="d01b6-127">File and URL submissions are not available in the clouds that do not allow for data to leave the environment.</span></span> <span data-ttu-id="d01b6-128">Die Möglichkeit, Datei oder URL auszuwählen, ist abgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d01b6-128">The ability to select File or URL will be greyed out.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="d01b6-129">Senden einer fragebaren E-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="d01b6-129">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="d01b6-130">Überprüfen Sie im Feld **"Übermittlungstyp auswählen",** ob **"E-Mail"** in der Dropdownliste ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="d01b6-130">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="d01b6-131">Verwenden Sie im Abschnitt **"Netzwerknachrichten-ID hinzufügen" oder "E-Mail-Datei hochladen"** eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="d01b6-131">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="d01b6-132">**Fügen Sie die E-Mail-Netzwerknachrichten-ID** hinzu: Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-Id-Header** in der Nachricht oder im **X-MS-Office365-Filtering-Correlation-Id-Header** in isolierten Nachrichten verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d01b6-132">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="d01b6-133">**Hochladen die E-Mail-Datei (MSG oder EML):** Klicken Sie auf **"Dateien durchsuchen".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-133">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="d01b6-134">Suchen Sie im daraufhin geöffneten Dialogfeld die EML- oder MSG-Datei, und wählen Sie sie aus, und klicken Sie dann auf **"Öffnen".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-134">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d01b6-135">Die Möglichkeit, Nachrichten ab 30 Tagen zu übermitteln, wurde für Defender für Office 365 Kunden vorübergehend ausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="d01b6-135">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="d01b6-136">Administratoren können nur 7 Tage zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="d01b6-136">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="d01b6-137">Geben Sie im Feld **"Empfänger auswählen, der ein Problem hatte"** den Empfänger an, für den Sie eine Richtlinienüberprüfung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="d01b6-137">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="d01b6-138">Die Richtlinienüberprüfung bestimmt, ob die Überprüfung durch die E-Mail aufgrund von Benutzer- oder Organisationsrichtlinien umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="d01b6-138">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="d01b6-139">Wählen Sie im Abschnitt **"Auswählen eines Grunds für die Übermittlung an Microsoft"** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="d01b6-139">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="d01b6-140">**Sollte nicht blockiert worden sein (falsch positiv)**</span><span class="sxs-lookup"><span data-stu-id="d01b6-140">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="d01b6-141">**Sollte blockiert worden sein:** In der **E-Mail sollte als angezeigter Abschnitt kategorisiert worden sein,** wählen Sie einen der folgenden Werte aus (wenn Sie nicht sicher sind, verwenden Sie Ihren besten Willen):</span><span class="sxs-lookup"><span data-stu-id="d01b6-141">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="d01b6-142">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="d01b6-142">**Phish**</span></span>
     - <span data-ttu-id="d01b6-143">**Spam**</span><span class="sxs-lookup"><span data-stu-id="d01b6-143">**Spam**</span></span>
     - <span data-ttu-id="d01b6-144">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="d01b6-144">**Malware**</span></span>

5. <span data-ttu-id="d01b6-145">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-145">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d01b6-146">![Beispiel für neue URL-Übermittlung](../../media/submission-flyout-email.png)</span><span class="sxs-lookup"><span data-stu-id="d01b6-146">![New URL submission example](../../media/submission-flyout-email.png)</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="d01b6-147">Senden einer verdächtigen URL an Microsoft</span><span class="sxs-lookup"><span data-stu-id="d01b6-147">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="d01b6-148">Wählen Sie im Feld **"Übermittlungstyp auswählen"** die **URL** aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="d01b6-148">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="d01b6-149">Geben Sie in das angezeigte **URL-Feld** die vollständige URL ein (z. B. `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="d01b6-149">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="d01b6-150">Wählen Sie im Abschnitt **"Auswählen eines Grunds für die Übermittlung an Microsoft"** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="d01b6-150">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="d01b6-151">**Sollte nicht blockiert worden sein (falsch positiv)**</span><span class="sxs-lookup"><span data-stu-id="d01b6-151">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="d01b6-152">**Sollte blockiert worden sein:** In der URL sollte als angezeigter Abschnitt **kategorisiert worden sein,** wählen Sie **Phishing** oder **Schadsoftware** aus.</span><span class="sxs-lookup"><span data-stu-id="d01b6-152">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="d01b6-153">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-153">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d01b6-154">![Beispiel für neue E-Mail-Übermittlung](../../media/submission-url-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="d01b6-154">![New Email submission example](../../media/submission-url-flyout.png)</span></span>

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="d01b6-155">Übermitteln einer verdächtigen E-Mail-Anlage an Microsoft</span><span class="sxs-lookup"><span data-stu-id="d01b6-155">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="d01b6-156">Wählen Sie im Feld **"Übermittlungstyp auswählen"** in der Dropdownliste die Option **"Datei"** aus.</span><span class="sxs-lookup"><span data-stu-id="d01b6-156">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="d01b6-157">Klicken Sie im angezeigten Abschnitt **"Datei"** auf **"Dateien durchsuchen".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-157">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="d01b6-158">Suchen Sie im daraufhin geöffneten Dialogfeld die Datei, wählen Sie sie aus, und klicken Sie dann auf **"Öffnen".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-158">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="d01b6-159">Wählen Sie im Abschnitt **"Auswählen eines Grunds für die Übermittlung an Microsoft"** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="d01b6-159">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="d01b6-160">**Sollte nicht blockiert worden sein (falsch positiv)**</span><span class="sxs-lookup"><span data-stu-id="d01b6-160">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="d01b6-161">**Sollte blockiert worden sein:** In der URL sollte als angezeigter Abschnitt **kategorisiert worden sein, schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt. </span><span class="sxs-lookup"><span data-stu-id="d01b6-161">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="d01b6-162">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-162">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d01b6-163">![Beispiel für die Übermittlung neuer Anlagen](../../media/submission-file-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="d01b6-163">![New Attachment submission example](../../media/submission-file-flyout.png)</span></span>

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="d01b6-164">Anzeigen von Administratorübermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="d01b6-164">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="d01b6-165">Wechseln Sie im Microsoft 365 Defender Portal zu **E-Mail-&** \> **Übermittlungen für die** Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="d01b6-165">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="d01b6-166">Überprüfen Sie auf der Seite **"Übermittlungen",** ob die Registerkarte **"Für Analyse übermittelt"** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="d01b6-166">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="d01b6-167">Sie können die Einträge sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="d01b6-167">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="d01b6-168">Klicken Sie auf **Spalten anpassen,** um maximal sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d01b6-168">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="d01b6-169">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="d01b6-169">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="d01b6-170">**Übermittlungsname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d01b6-170">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="d01b6-171">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d01b6-171">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="d01b6-172">**Übermitteltes Datum**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d01b6-172">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="d01b6-173">**Übermittlungstyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d01b6-173">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="d01b6-174">**Grund für die Übermittlung**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d01b6-174">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="d01b6-175">**Status des erneuten Scannens**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d01b6-175">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="d01b6-176">**Erneutes Scanergebnis**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d01b6-176">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="d01b6-177">**Filterbewertung**</span><span class="sxs-lookup"><span data-stu-id="d01b6-177">**Filter verdict**</span></span>
     - <span data-ttu-id="d01b6-178">**Grund für Übermittlung/Blockierung**</span><span class="sxs-lookup"><span data-stu-id="d01b6-178">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="d01b6-179">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="d01b6-179">**Submission ID**</span></span>
     - <span data-ttu-id="d01b6-180">**Netzwerknachrichten-ID/Objekt-ID**</span><span class="sxs-lookup"><span data-stu-id="d01b6-180">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="d01b6-181">**Direction**</span><span class="sxs-lookup"><span data-stu-id="d01b6-181">**Direction**</span></span>
     - <span data-ttu-id="d01b6-182">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="d01b6-182">**Sender IP**</span></span>
     - <span data-ttu-id="d01b6-183">**Massenkonforme Ebene (Bulk Compliant Level, BCL)**</span><span class="sxs-lookup"><span data-stu-id="d01b6-183">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="d01b6-184">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="d01b6-184">**Destination**</span></span>
     - <span data-ttu-id="d01b6-185">**Richtlinienaktion**</span><span class="sxs-lookup"><span data-stu-id="d01b6-185">**Policy action**</span></span>
     - <span data-ttu-id="d01b6-186">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="d01b6-186">**Submitted by**</span></span>

     <span data-ttu-id="d01b6-187">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-187">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="d01b6-188">Klicken Sie zum Filtern der Einträge auf **"Filtern".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-188">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="d01b6-189">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="d01b6-189">The available filters are:</span></span>
     - <span data-ttu-id="d01b6-190">**Übermitteltes Datum:** **Startdatum** und **Enddatum.**</span><span class="sxs-lookup"><span data-stu-id="d01b6-190">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="d01b6-191">**Übermittlungstyp:** **E-Mail,** **URL** oder **Datei.**</span><span class="sxs-lookup"><span data-stu-id="d01b6-191">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="d01b6-192">**Übermittlungs-ID:** Ein GUID-Wert, der jeder Übermittlung zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d01b6-192">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="d01b6-193">**Netzwerknachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="d01b6-193">**Network Message ID**</span></span>
     - <span data-ttu-id="d01b6-194">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d01b6-194">**Sender**</span></span>

     <span data-ttu-id="d01b6-195">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-195">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="d01b6-196">![Neue Filteroptionen für Administratorübermittlungen](../../media/admin-submission-filters.png)</span><span class="sxs-lookup"><span data-stu-id="d01b6-196">![New Filter options for admin submissions](../../media/admin-submission-filters.png)</span></span>

   - <span data-ttu-id="d01b6-197">Klicken Sie zum Gruppieren der Einträge auf **"Gruppieren",** und wählen Sie einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="d01b6-197">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="d01b6-198">**Keine**</span><span class="sxs-lookup"><span data-stu-id="d01b6-198">**None**</span></span>
     - <span data-ttu-id="d01b6-199">**Type**</span><span class="sxs-lookup"><span data-stu-id="d01b6-199">**Type**</span></span>
     - <span data-ttu-id="d01b6-200">**Grund**</span><span class="sxs-lookup"><span data-stu-id="d01b6-200">**Reason**</span></span>
     - <span data-ttu-id="d01b6-201">**Status**</span><span class="sxs-lookup"><span data-stu-id="d01b6-201">**Status**</span></span>
     - <span data-ttu-id="d01b6-202">**Erneutes Scanergebnis**</span><span class="sxs-lookup"><span data-stu-id="d01b6-202">**Rescan result**</span></span>

   - <span data-ttu-id="d01b6-203">Klicken Sie zum Exportieren der Einträge auf **"Exportieren".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-203">To export the entries, click **Export**.</span></span> <span data-ttu-id="d01b6-204">Speichern Sie im daraufhin angezeigten Dialogfeld die .csv Datei.</span><span class="sxs-lookup"><span data-stu-id="d01b6-204">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="d01b6-205">Details zur erneuten Überprüfung der Administratorübermittlung</span><span class="sxs-lookup"><span data-stu-id="d01b6-205">Admin submission rescan details</span></span>

<span data-ttu-id="d01b6-206">Nachrichten, die in Administratorübermittlungen übermittelt werden, werden überprüft, und die Ergebnisse werden im Flyout "Übermittlungsdetails" angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d01b6-206">Messages that are submitted in admin submissions are reviewed and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="d01b6-207">Mögliche Fehler in der E-Mail-Authentifizierung des Absenders zum Zeitpunkt der Auslieferung.</span><span class="sxs-lookup"><span data-stu-id="d01b6-207">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="d01b6-208">Informationen zu Richtlinientreffern, welche die Bewertung über einer Nachricht beeinflusst oder überschrieben haben könnten.</span><span class="sxs-lookup"><span data-stu-id="d01b6-208">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="d01b6-209">Aktuelle Detonationsergebnisse, um festzustellen, ob die in der Nachricht enthaltenen URLs oder Dateien böswillig waren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="d01b6-209">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="d01b6-210">Feedback von Benotungsprüfern.</span><span class="sxs-lookup"><span data-stu-id="d01b6-210">Feedback from graders.</span></span>

<span data-ttu-id="d01b6-211">Wenn eine Überschreibung gefunden wurde, sollte der erneute Scan in einigen Minuten abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="d01b6-211">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="d01b6-212">Wenn es kein Problem bei der E-Mail-Authentifizierung gab oder die Zustellung nicht von einer Außerkraftsetzung betroffen war, kann das Feedback von Bewertern bis zu einem Tag dauern.</span><span class="sxs-lookup"><span data-stu-id="d01b6-212">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="d01b6-213">Anzeigen von Benutzerübermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="d01b6-213">View user submissions to Microsoft</span></span>

<span data-ttu-id="d01b6-214">Wenn Sie das [Add-In "Nachricht melden",](enable-the-report-message-add-in.md)das [Add-In "Phishing melden"](enable-the-report-phish-add-in.md)bereitgestellt haben oder Benutzer die [integrierte Berichterstellung in Outlook im Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)verwenden, können Sie sehen, welche Benutzer auf der Registerkarte **"Benutzer gemeldete Nachrichten"** berichtigen.</span><span class="sxs-lookup"><span data-stu-id="d01b6-214">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="d01b6-215">Wechseln Sie im Microsoft 365 Defender Portal zu **E-Mail-&** \> **Übermittlungen für** die Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="d01b6-215">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="d01b6-216">Wählen Sie auf der Seite **"Übermittlungen"** die Registerkarte **"Vom Benutzer gemeldete Nachrichten"** aus.</span><span class="sxs-lookup"><span data-stu-id="d01b6-216">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="d01b6-217">Sie können die Einträge sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="d01b6-217">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="d01b6-218">Klicken Sie auf **Spalten anpassen,** um maximal sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d01b6-218">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="d01b6-219">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="d01b6-219">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="d01b6-220">**E-Mail-Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d01b6-220">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="d01b6-221">**Gemeldet von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d01b6-221">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="d01b6-222">**Gemeldetes Datum**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d01b6-222">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="d01b6-223">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d01b6-223">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="d01b6-224">**Gemeldeter Grund**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d01b6-224">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="d01b6-225">**Erneutes Scanergebnis**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d01b6-225">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="d01b6-226">**Gemeldete ID der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="d01b6-226">**Message reported ID**</span></span>
     - <span data-ttu-id="d01b6-227">**Netzwerknachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="d01b6-227">**Network Message ID**</span></span>
     - <span data-ttu-id="d01b6-228">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="d01b6-228">**Sender IP**</span></span>
     - <span data-ttu-id="d01b6-229">**Phishing-Simulation**</span><span class="sxs-lookup"><span data-stu-id="d01b6-229">**Phish simulation**</span></span>

     <span data-ttu-id="d01b6-230">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-230">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="d01b6-231">Klicken Sie zum Filtern der Einträge auf **"Filtern".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-231">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="d01b6-232">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="d01b6-232">The available filters are:</span></span>
     - <span data-ttu-id="d01b6-233">**Gemeldetes Datum**: **Startdatum** und **Enddatum.**</span><span class="sxs-lookup"><span data-stu-id="d01b6-233">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="d01b6-234">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="d01b6-234">**Reported by**</span></span>
     - <span data-ttu-id="d01b6-235">**E-Mail-Betreff**</span><span class="sxs-lookup"><span data-stu-id="d01b6-235">**Email subject**</span></span>
     - <span data-ttu-id="d01b6-236">**Gemeldete ID der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="d01b6-236">**Message reported ID**</span></span>
     - <span data-ttu-id="d01b6-237">**Netzwerknachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="d01b6-237">**Network Message ID**</span></span>
     - <span data-ttu-id="d01b6-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d01b6-238">**Sender**</span></span>
     - <span data-ttu-id="d01b6-239">**Gemeldeter Grund:** **keine Junk-,** **Phishing-** oder **Spam-Nachrichten.**</span><span class="sxs-lookup"><span data-stu-id="d01b6-239">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="d01b6-240">**Phishing-Simulation:** **Ja** oder **Nein**</span><span class="sxs-lookup"><span data-stu-id="d01b6-240">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="d01b6-241">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-241">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="d01b6-242">![Neue Filteroptionen für Benutzerübermittlungen](../../media/admin-submission-reported-messages.png)</span><span class="sxs-lookup"><span data-stu-id="d01b6-242">![New Filter options for user submissions](../../media/admin-submission-reported-messages.png)</span></span>

   - <span data-ttu-id="d01b6-243">Klicken Sie zum Gruppieren der Einträge auf **"Gruppieren",** und wählen Sie einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="d01b6-243">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="d01b6-244">**Keine**</span><span class="sxs-lookup"><span data-stu-id="d01b6-244">**None**</span></span>
     - <span data-ttu-id="d01b6-245">**Grund**</span><span class="sxs-lookup"><span data-stu-id="d01b6-245">**Reason**</span></span>
     - <span data-ttu-id="d01b6-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d01b6-246">**Sender**</span></span>
     - <span data-ttu-id="d01b6-247">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="d01b6-247">**Reported by**</span></span>
     - <span data-ttu-id="d01b6-248">**Erneutes Scanergebnis**</span><span class="sxs-lookup"><span data-stu-id="d01b6-248">**Rescan result**</span></span>
     - <span data-ttu-id="d01b6-249">**Phishing-Simulation**</span><span class="sxs-lookup"><span data-stu-id="d01b6-249">**Phish simulation**</span></span>

   - <span data-ttu-id="d01b6-250">Klicken Sie zum Exportieren der Einträge auf **"Exportieren".**</span><span class="sxs-lookup"><span data-stu-id="d01b6-250">To export the entries, click **Export**.</span></span> <span data-ttu-id="d01b6-251">Speichern Sie im daraufhin angezeigten Dialogfeld die .csv Datei.</span><span class="sxs-lookup"><span data-stu-id="d01b6-251">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="d01b6-252">Wenn Organisationen so konfiguriert sind, dass von Benutzern gemeldete Nachrichten nur an das benutzerdefinierte Postfach gesendet werden, werden gemeldete Nachrichten nicht zur erneuten Überprüfung gesendet, und die Ergebnisse in **den vom Benutzer gemeldeten Nachrichten** sind immer leer.</span><span class="sxs-lookup"><span data-stu-id="d01b6-252">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="d01b6-253">Rückgängigmachen von Benutzerübermittlungen</span><span class="sxs-lookup"><span data-stu-id="d01b6-253">Undo user submissions</span></span>

<span data-ttu-id="d01b6-254">Sobald ein Benutzer eine verdächtige E-Mail an das benutzerdefinierte Postfach sendet, haben der Benutzer und der Administrator keine Möglichkeit, die Übermittlung rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="d01b6-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="d01b6-255">Wenn der Benutzer die E-Mail wiederherstellen möchte, steht sie für die Wiederherstellung in den Ordnern "Gelöschte Elemente" oder "Junk-E-Mail" zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d01b6-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="d01b6-256">Senden von Nachrichten aus dem benutzerdefinierten Postfach an Microsoft</span><span class="sxs-lookup"><span data-stu-id="d01b6-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="d01b6-257">Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass von Benutzern gemeldete Nachrichten abgefangen werden, ohne die Nachrichten an Microsoft zu senden, können Sie bestimmte Nachrichten suchen und zur Analyse an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="d01b6-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="d01b6-258">Dadurch wird eine Benutzerübermittlung effektiv an eine Administratorübermittlung verschoben.</span><span class="sxs-lookup"><span data-stu-id="d01b6-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="d01b6-259">Wählen Sie auf der Registerkarte **"Vom Benutzer gemeldete Nachrichten"** eine Nachricht in der Liste aus, klicken Sie auf **"Zur Analyse an Microsoft übermitteln",** und wählen Sie dann einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="d01b6-259">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="d01b6-260">**Bericht sauber**</span><span class="sxs-lookup"><span data-stu-id="d01b6-260">**Report clean**</span></span>
- <span data-ttu-id="d01b6-261">**Melden von Phishing**</span><span class="sxs-lookup"><span data-stu-id="d01b6-261">**Report phishing**</span></span>
- <span data-ttu-id="d01b6-262">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="d01b6-262">**Report malware**</span></span>
- <span data-ttu-id="d01b6-263">**Melden von Spam**</span><span class="sxs-lookup"><span data-stu-id="d01b6-263">**Report spam**</span></span>
- <span data-ttu-id="d01b6-264">**Untersuchung auslösen**</span><span class="sxs-lookup"><span data-stu-id="d01b6-264">**Trigger investigation**</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d01b6-265">![Neue Optionen auf der Schaltfläche "Aktion"](../../media/admin-submission-main-action-button.png)</span><span class="sxs-lookup"><span data-stu-id="d01b6-265">![New Options on the Action button](../../media/admin-submission-main-action-button.png)</span></span>

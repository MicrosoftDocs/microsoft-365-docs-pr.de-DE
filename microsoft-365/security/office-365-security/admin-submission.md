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
ms.openlocfilehash: ab25757c79b7978400e98fa36d48163e1681e7c1
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062035"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="23380-103">Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="23380-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="23380-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="23380-104">**Applies to**</span></span>
- [<span data-ttu-id="23380-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="23380-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="23380-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="23380-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="23380-107">In Microsoft 365 Organisationen mit Exchange Online Postfächern können Administratoren das Übermittlungsportal im Microsoft 365 Defender-Portal verwenden, um E-Mail-Nachrichten, URLs und Anlagen zur Überprüfung an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="23380-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="23380-108">Wenn Sie eine E-Mail-Nachricht übermitteln, erhalten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="23380-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="23380-109">**E-Mail-Authentifizierungsprüfung:** Details dazu, ob die E-Mail-Authentifizierung bei der Zustellung erfolgreich war oder fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="23380-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="23380-110">**Richtlinientreffer:** Informationen zu allen Richtlinien, die eingehende E-Mails in Ihrem Mandanten möglicherweise zugelassen oder blockiert haben, und überschreiben unsere Dienstfilterbewertungen.</span><span class="sxs-lookup"><span data-stu-id="23380-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="23380-111">**Nutzlastreputation/-detonation:** Untersuchung aller URLs und Anlagen in der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="23380-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="23380-112">**Benotungsanalyse:** Überprüfung durch Benotungsprüfer, um zu überprüfen, ob Nachrichten bösartig sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="23380-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23380-113">Nutzlastreputation/-detonation und Bewertungsanalyse werden nicht in allen Mandanten durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="23380-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="23380-114">Informationen werden daran gehindert, sich außerhalb der Organisation zu befinden, wenn Daten die Mandantengrenze nicht zu Compliancezwecken verlassen sollen.</span><span class="sxs-lookup"><span data-stu-id="23380-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="23380-115">Weitere Möglichkeiten zum Übermitteln von E-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter "Melden von [Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="23380-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="23380-116">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="23380-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="23380-117">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="23380-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="23380-118">Um direkt zur Seite **"Übermittlungen"** zu wechseln, verwenden Sie <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="23380-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="23380-119">Um Nachrichten und Dateien an Microsoft zu übermitteln, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="23380-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="23380-120">**Organisationsverwaltung** oder **Sicherheitsleseberechtigter** im [Microsoft 365 Defender Portal.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="23380-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="23380-121">**Organisationsverwaltung** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="23380-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="23380-122">Beachten Sie, dass die Mitgliedschaft in dieser Rollengruppe erforderlich ist, um [Benutzerübermittlungen an das benutzerdefinierte Postfach anzuzeigen,](#view-user-submissions-to-microsoft) wie weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="23380-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="23380-123">Weitere Informationen dazu, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter ["Melden von Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="23380-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="23380-124">Melden verdächtiger Inhalte an Microsoft</span><span class="sxs-lookup"><span data-stu-id="23380-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="23380-125">Wechseln Sie im Microsoft 365 Defender Portal zu **E-Mail-&** \> **Übermittlungen für** die Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="23380-125">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="23380-126">Überprüfen Sie auf der Seite **"Übermittlungen",** ob die Registerkarte **"Für Analyse übermittelt"** ausgewählt ist, und klicken Sie dann auf das ![ Symbol ](../../media/m365-cc-sc-create-icon.png) **"An Microsoft zur Analyse übermitteln".**</span><span class="sxs-lookup"><span data-stu-id="23380-126">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="23380-127">Verwenden Sie das Flyout **"An Microsoft übermitteln" zum Überprüfen** des Flyouts, das die Nachricht, URL oder E-Mail-Anlage wie in den folgenden Abschnitten beschrieben zu übermitteln scheint.</span><span class="sxs-lookup"><span data-stu-id="23380-127">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="23380-128">Senden einer fragebaren E-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="23380-128">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="23380-129">Überprüfen Sie im Feld **"Übermittlungstyp auswählen",** ob **"E-Mail"** in der Dropdownliste ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="23380-129">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="23380-130">Verwenden Sie im Abschnitt **"Netzwerknachrichten-ID hinzufügen" oder "E-Mail-Datei hochladen"** eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="23380-130">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="23380-131">**Fügen Sie die E-Mail-Netzwerknachrichten-ID** hinzu: Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-Id-Header** in der Nachricht oder im **X-MS-Office365-Filtering-Correlation-Id-Header** in isolierten Nachrichten verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="23380-131">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="23380-132">**Hochladen die E-Mail-Datei (MSG oder EML):** Klicken Sie auf **"Dateien durchsuchen".**</span><span class="sxs-lookup"><span data-stu-id="23380-132">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="23380-133">Suchen Sie im daraufhin geöffneten Dialogfeld die EML- oder MSG-Datei, und wählen Sie sie aus, und klicken Sie dann auf **"Öffnen".**</span><span class="sxs-lookup"><span data-stu-id="23380-133">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="23380-134">Die Möglichkeit, Nachrichten ab 30 Tagen zu übermitteln, wurde für Defender für Office 365 Kunden vorübergehend ausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="23380-134">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="23380-135">Administratoren können nur 7 Tage zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="23380-135">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="23380-136">Geben Sie im Feld **"Empfänger auswählen, der ein Problem hatte"** den Empfänger an, für den Sie eine Richtlinienüberprüfung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="23380-136">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="23380-137">Die Richtlinienüberprüfung bestimmt, ob die Überprüfung durch die E-Mail aufgrund von Benutzer- oder Organisationsrichtlinien umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="23380-137">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="23380-138">Wählen Sie im Abschnitt **"Auswählen eines Grunds für die Übermittlung an Microsoft"** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="23380-138">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="23380-139">**Sollte nicht blockiert worden sein (falsch positiv)**</span><span class="sxs-lookup"><span data-stu-id="23380-139">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="23380-140">**Sollte blockiert worden sein:** In der **E-Mail sollte als angezeigter Abschnitt kategorisiert worden sein,** wählen Sie einen der folgenden Werte aus (wenn Sie nicht sicher sind, verwenden Sie Ihren besten Willen):</span><span class="sxs-lookup"><span data-stu-id="23380-140">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="23380-141">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="23380-141">**Phish**</span></span>
     - <span data-ttu-id="23380-142">**Spam**</span><span class="sxs-lookup"><span data-stu-id="23380-142">**Spam**</span></span>
     - <span data-ttu-id="23380-143">**Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="23380-143">**Malware**</span></span>

5. <span data-ttu-id="23380-144">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="23380-144">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="23380-145">![Beispiel für neue URL-Übermittlung](../../media/submission-flyout-email.png)</span><span class="sxs-lookup"><span data-stu-id="23380-145">![New URL submission example](../../media/submission-flyout-email.png)</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="23380-146">Senden einer verdächtigen URL an Microsoft</span><span class="sxs-lookup"><span data-stu-id="23380-146">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="23380-147">Wählen Sie im Feld **"Übermittlungstyp auswählen"** die **URL** aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="23380-147">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="23380-148">Geben Sie in das angezeigte **URL-Feld** die vollständige URL ein (z. B. `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="23380-148">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="23380-149">Wählen Sie im Abschnitt **"Auswählen eines Grunds für die Übermittlung an Microsoft"** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="23380-149">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="23380-150">**Sollte nicht blockiert worden sein (falsch positiv)**</span><span class="sxs-lookup"><span data-stu-id="23380-150">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="23380-151">**Sollte blockiert worden sein:** In der URL sollte als angezeigter Abschnitt **kategorisiert worden sein,** wählen Sie **Phishing** oder **Schadsoftware** aus.</span><span class="sxs-lookup"><span data-stu-id="23380-151">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="23380-152">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="23380-152">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="23380-153">![Beispiel für neue E-Mail-Übermittlung](../../media/submission-url-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="23380-153">![New Email submission example](../../media/submission-url-flyout.png)</span></span>

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="23380-154">Übermitteln einer verdächtigen E-Mail-Anlage an Microsoft</span><span class="sxs-lookup"><span data-stu-id="23380-154">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="23380-155">Wählen Sie im Feld **"Übermittlungstyp auswählen"** in der Dropdownliste die Option **"Datei"** aus.</span><span class="sxs-lookup"><span data-stu-id="23380-155">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="23380-156">Klicken Sie im angezeigten Abschnitt **"Datei"** auf **"Dateien durchsuchen".**</span><span class="sxs-lookup"><span data-stu-id="23380-156">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="23380-157">Suchen Sie im daraufhin geöffneten Dialogfeld die Datei, wählen Sie sie aus, und klicken Sie dann auf **"Öffnen".**</span><span class="sxs-lookup"><span data-stu-id="23380-157">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="23380-158">Wählen Sie im Abschnitt **"Auswählen eines Grunds für die Übermittlung an Microsoft"** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="23380-158">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="23380-159">**Sollte nicht blockiert worden sein (falsch positiv)**</span><span class="sxs-lookup"><span data-stu-id="23380-159">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="23380-160">**Sollte blockiert worden sein:** In der URL sollte als angezeigter Abschnitt **kategorisiert worden sein, schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt. </span><span class="sxs-lookup"><span data-stu-id="23380-160">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="23380-161">Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="23380-161">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="23380-162">![Beispiel für die Übermittlung neuer Anlagen](../../media/submission-file-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="23380-162">![New Attachment submission example](../../media/submission-file-flyout.png)</span></span>

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="23380-163">Anzeigen von Administratorübermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="23380-163">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="23380-164">Wechseln Sie im Microsoft 365 Defender Portal zu **E-Mail-&** \> **Übermittlungen für** die Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="23380-164">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="23380-165">Überprüfen Sie auf der Seite **"Übermittlungen",** ob die Registerkarte **"Für Analyse übermittelt"** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="23380-165">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="23380-166">Sie können die Einträge sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="23380-166">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="23380-167">Klicken Sie auf **Spalten anpassen,** um maximal sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="23380-167">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="23380-168">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="23380-168">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="23380-169">**Übermittlungsname**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="23380-169">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="23380-170">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="23380-170">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="23380-171">**Übermitteltes Datum**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="23380-171">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="23380-172">**Übermittlungstyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="23380-172">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="23380-173">**Grund für die Übermittlung**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="23380-173">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="23380-174">**Status des erneuten Scannens**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="23380-174">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="23380-175">**Erneutes Scanergebnis**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="23380-175">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="23380-176">**Filterbewertung**</span><span class="sxs-lookup"><span data-stu-id="23380-176">**Filter verdict**</span></span>
     - <span data-ttu-id="23380-177">**Grund für Übermittlung/Blockierung**</span><span class="sxs-lookup"><span data-stu-id="23380-177">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="23380-178">**Übermittlungs-ID**</span><span class="sxs-lookup"><span data-stu-id="23380-178">**Submission ID**</span></span>
     - <span data-ttu-id="23380-179">**Netzwerknachrichten-ID/Objekt-ID**</span><span class="sxs-lookup"><span data-stu-id="23380-179">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="23380-180">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="23380-180">**Direction**</span></span>
     - <span data-ttu-id="23380-181">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="23380-181">**Sender IP**</span></span>
     - <span data-ttu-id="23380-182">**Massenkonforme Ebene (Bulk Compliant Level, BCL)**</span><span class="sxs-lookup"><span data-stu-id="23380-182">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="23380-183">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="23380-183">**Destination**</span></span>
     - <span data-ttu-id="23380-184">**Richtlinienaktion**</span><span class="sxs-lookup"><span data-stu-id="23380-184">**Policy action**</span></span>
     - <span data-ttu-id="23380-185">**Übermittelt von**</span><span class="sxs-lookup"><span data-stu-id="23380-185">**Submitted by**</span></span>

     <span data-ttu-id="23380-186">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="23380-186">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="23380-187">Klicken Sie zum Filtern der Einträge auf **"Filtern".**</span><span class="sxs-lookup"><span data-stu-id="23380-187">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="23380-188">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="23380-188">The available filters are:</span></span>
     - <span data-ttu-id="23380-189">**Übermitteltes Datum:** **Startdatum** und **Enddatum.**</span><span class="sxs-lookup"><span data-stu-id="23380-189">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="23380-190">**Übermittlungstyp:** **E-Mail,** **URL** oder **Datei.**</span><span class="sxs-lookup"><span data-stu-id="23380-190">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="23380-191">**Übermittlungs-ID:** Ein GUID-Wert, der jeder Übermittlung zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="23380-191">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="23380-192">**Netzwerknachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="23380-192">**Network Message ID**</span></span>
     - <span data-ttu-id="23380-193">**Sender**</span><span class="sxs-lookup"><span data-stu-id="23380-193">**Sender**</span></span>

     <span data-ttu-id="23380-194">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="23380-194">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="23380-195">![Neue Filteroptionen für Administratorübermittlungen](../../media/admin-submission-filters.png)</span><span class="sxs-lookup"><span data-stu-id="23380-195">![New Filter options for admin submissions](../../media/admin-submission-filters.png)</span></span>

   - <span data-ttu-id="23380-196">Klicken Sie zum Gruppieren der Einträge auf **"Gruppieren",** und wählen Sie einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="23380-196">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="23380-197">**Keine**</span><span class="sxs-lookup"><span data-stu-id="23380-197">**None**</span></span>
     - <span data-ttu-id="23380-198">**Typ**</span><span class="sxs-lookup"><span data-stu-id="23380-198">**Type**</span></span>
     - <span data-ttu-id="23380-199">**Grund**</span><span class="sxs-lookup"><span data-stu-id="23380-199">**Reason**</span></span>
     - <span data-ttu-id="23380-200">**Status**</span><span class="sxs-lookup"><span data-stu-id="23380-200">**Status**</span></span>
     - <span data-ttu-id="23380-201">**Erneutes Scanergebnis**</span><span class="sxs-lookup"><span data-stu-id="23380-201">**Rescan result**</span></span>

   - <span data-ttu-id="23380-202">Klicken Sie zum Exportieren der Einträge auf **"Exportieren".**</span><span class="sxs-lookup"><span data-stu-id="23380-202">To export the entries, click **Export**.</span></span> <span data-ttu-id="23380-203">Speichern Sie im daraufhin angezeigten Dialogfeld die .csv Datei.</span><span class="sxs-lookup"><span data-stu-id="23380-203">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="23380-204">Details zur erneuten Überprüfung der Administratorübermittlung</span><span class="sxs-lookup"><span data-stu-id="23380-204">Admin submission rescan details</span></span>

<span data-ttu-id="23380-205">Nachrichten, die in Administratorübermittlungen übermittelt werden, werden überprüft, und die Ergebnisse werden im Flyout "Übermittlungsdetails" angezeigt:</span><span class="sxs-lookup"><span data-stu-id="23380-205">Messages that are submitted in admin submissions are reviewed and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="23380-206">Mögliche Fehler in der E-Mail-Authentifizierung des Absenders zum Zeitpunkt der Auslieferung.</span><span class="sxs-lookup"><span data-stu-id="23380-206">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="23380-207">Informationen zu Richtlinientreffern, welche die Bewertung über einer Nachricht beeinflusst oder überschrieben haben könnten.</span><span class="sxs-lookup"><span data-stu-id="23380-207">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="23380-208">Aktuelle Detonationsergebnisse, um festzustellen, ob die in der Nachricht enthaltenen URLs oder Dateien böswillig waren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="23380-208">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="23380-209">Feedback von Benotungsprüfern.</span><span class="sxs-lookup"><span data-stu-id="23380-209">Feedback from graders.</span></span>

<span data-ttu-id="23380-210">Wenn eine Überschreibung gefunden wurde, sollte der erneute Scan in einigen Minuten abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="23380-210">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="23380-211">Wenn es kein Problem bei der E-Mail-Authentifizierung gab oder die Zustellung nicht von einer Außerkraftsetzung betroffen war, kann das Feedback von Bewertern bis zu einem Tag dauern.</span><span class="sxs-lookup"><span data-stu-id="23380-211">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="23380-212">Anzeigen von Benutzerübermittlungen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="23380-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="23380-213">Wenn Sie das [Add-In "Nachricht melden",](enable-the-report-message-add-in.md)das [Add-In "Phishing melden"](enable-the-report-phish-add-in.md)bereitgestellt haben oder Personen die [integrierte Berichterstellung in Outlook im Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)verwenden, können Sie sehen, welche Benutzer auf der Registerkarte **"Benutzer gemeldete Nachrichten"** berichtigen.</span><span class="sxs-lookup"><span data-stu-id="23380-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="23380-214">Wechseln Sie im Microsoft 365 Defender Portal zu **E-Mail-&** \> **Übermittlungen für** die Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="23380-214">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="23380-215">Wählen Sie auf der Seite **"Übermittlungen"** die Registerkarte **"Vom Benutzer gemeldete Nachrichten"** aus.</span><span class="sxs-lookup"><span data-stu-id="23380-215">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="23380-216">Sie können die Einträge sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.</span><span class="sxs-lookup"><span data-stu-id="23380-216">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="23380-217">Klicken Sie auf **Spalten anpassen,** um maximal sieben Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="23380-217">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="23380-218">Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="23380-218">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="23380-219">**E-Mail-Betreff**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="23380-219">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="23380-220">**Gemeldet von**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="23380-220">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="23380-221">**Gemeldetes Datum**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="23380-221">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="23380-222">**Absender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="23380-222">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="23380-223">**Gemeldeter Grund**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="23380-223">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="23380-224">**Erneutes Scanergebnis**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="23380-224">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="23380-225">**Gemeldete ID der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="23380-225">**Message reported ID**</span></span>
     - <span data-ttu-id="23380-226">**Netzwerknachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="23380-226">**Network Message ID**</span></span>
     - <span data-ttu-id="23380-227">**Sender-IP**</span><span class="sxs-lookup"><span data-stu-id="23380-227">**Sender IP**</span></span>
     - <span data-ttu-id="23380-228">**Phishing-Simulation**</span><span class="sxs-lookup"><span data-stu-id="23380-228">**Phish simulation**</span></span>

     <span data-ttu-id="23380-229">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="23380-229">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="23380-230">Klicken Sie zum Filtern der Einträge auf **"Filtern".**</span><span class="sxs-lookup"><span data-stu-id="23380-230">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="23380-231">Die verfügbaren Filter sind:</span><span class="sxs-lookup"><span data-stu-id="23380-231">The available filters are:</span></span>
     - <span data-ttu-id="23380-232">**Gemeldetes Datum**: **Startdatum** und **Enddatum.**</span><span class="sxs-lookup"><span data-stu-id="23380-232">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="23380-233">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="23380-233">**Reported by**</span></span>
     - <span data-ttu-id="23380-234">**E-Mail-Betreff**</span><span class="sxs-lookup"><span data-stu-id="23380-234">**Email subject**</span></span>
     - <span data-ttu-id="23380-235">**Gemeldete ID der Nachricht**</span><span class="sxs-lookup"><span data-stu-id="23380-235">**Message reported ID**</span></span>
     - <span data-ttu-id="23380-236">**Netzwerknachrichten-ID**</span><span class="sxs-lookup"><span data-stu-id="23380-236">**Network Message ID**</span></span>
     - <span data-ttu-id="23380-237">**Sender**</span><span class="sxs-lookup"><span data-stu-id="23380-237">**Sender**</span></span>
     - <span data-ttu-id="23380-238">**Gemeldeter Grund:** **keine Junk-,** **Phishing-** oder **Spam-Nachrichten.**</span><span class="sxs-lookup"><span data-stu-id="23380-238">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="23380-239">**Phishing-Simulation:** **Ja** oder **Nein**</span><span class="sxs-lookup"><span data-stu-id="23380-239">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="23380-240">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="23380-240">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="23380-241">![Neue Filteroptionen für Benutzerübermittlungen](../../media/admin-submission-reported-messages.png)</span><span class="sxs-lookup"><span data-stu-id="23380-241">![New Filter options for user submissions](../../media/admin-submission-reported-messages.png)</span></span>

   - <span data-ttu-id="23380-242">Klicken Sie zum Gruppieren der Einträge auf **"Gruppieren",** und wählen Sie einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="23380-242">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="23380-243">**Keine**</span><span class="sxs-lookup"><span data-stu-id="23380-243">**None**</span></span>
     - <span data-ttu-id="23380-244">**Grund**</span><span class="sxs-lookup"><span data-stu-id="23380-244">**Reason**</span></span>
     - <span data-ttu-id="23380-245">**Sender**</span><span class="sxs-lookup"><span data-stu-id="23380-245">**Sender**</span></span>
     - <span data-ttu-id="23380-246">**Berichtet von**</span><span class="sxs-lookup"><span data-stu-id="23380-246">**Reported by**</span></span>
     - <span data-ttu-id="23380-247">**Erneutes Scanergebnis**</span><span class="sxs-lookup"><span data-stu-id="23380-247">**Rescan result**</span></span>
     - <span data-ttu-id="23380-248">**Phishing-Simulation**</span><span class="sxs-lookup"><span data-stu-id="23380-248">**Phish simulation**</span></span>

   - <span data-ttu-id="23380-249">Klicken Sie zum Exportieren der Einträge auf **"Exportieren".**</span><span class="sxs-lookup"><span data-stu-id="23380-249">To export the entries, click **Export**.</span></span> <span data-ttu-id="23380-250">Speichern Sie im daraufhin angezeigten Dialogfeld die .csv Datei.</span><span class="sxs-lookup"><span data-stu-id="23380-250">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="23380-251">Wenn Organisationen so konfiguriert sind, dass von Benutzern gemeldete Nachrichten nur an das benutzerdefinierte Postfach gesendet werden, werden gemeldete Nachrichten nicht zur erneuten Überprüfung gesendet, und die Ergebnisse in **den vom Benutzer gemeldeten Nachrichten** sind immer leer.</span><span class="sxs-lookup"><span data-stu-id="23380-251">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="23380-252">Rückgängigmachen von Benutzerübermittlungen</span><span class="sxs-lookup"><span data-stu-id="23380-252">Undo user submissions</span></span>

<span data-ttu-id="23380-253">Sobald ein Benutzer eine verdächtige E-Mail an das benutzerdefinierte Postfach sendet, haben der Benutzer und der Administrator keine Möglichkeit, die Übermittlung rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="23380-253">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="23380-254">Wenn der Benutzer die E-Mail wiederherstellen möchte, steht sie für die Wiederherstellung in den Ordnern "Gelöschte Elemente" oder "Junk-E-Mail" zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="23380-254">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="23380-255">Senden von Nachrichten aus dem benutzerdefinierten Postfach an Microsoft</span><span class="sxs-lookup"><span data-stu-id="23380-255">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="23380-256">Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass von Benutzern gemeldete Nachrichten abgefangen werden, ohne die Nachrichten an Microsoft zu senden, können Sie bestimmte Nachrichten suchen und zur Analyse an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="23380-256">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="23380-257">Dadurch wird eine Benutzerübermittlung effektiv an eine Administratorübermittlung verschoben.</span><span class="sxs-lookup"><span data-stu-id="23380-257">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="23380-258">Wählen Sie auf der Registerkarte **"Vom Benutzer gemeldete Nachrichten"** eine Nachricht in der Liste aus, klicken Sie auf **"Zur Analyse an Microsoft übermitteln",** und wählen Sie dann einen der folgenden Werte aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="23380-258">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="23380-259">**Bericht sauber**</span><span class="sxs-lookup"><span data-stu-id="23380-259">**Report clean**</span></span>
- <span data-ttu-id="23380-260">**Melden von Phishing**</span><span class="sxs-lookup"><span data-stu-id="23380-260">**Report phishing**</span></span>
- <span data-ttu-id="23380-261">**Melden von Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="23380-261">**Report malware**</span></span>
- <span data-ttu-id="23380-262">**Melden von Spam**</span><span class="sxs-lookup"><span data-stu-id="23380-262">**Report spam**</span></span>
- <span data-ttu-id="23380-263">**Untersuchung auslösen**</span><span class="sxs-lookup"><span data-stu-id="23380-263">**Trigger investigation**</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="23380-264">![Neue Optionen auf der Schaltfläche "Aktion"](../../media/admin-submission-main-action-button.png)</span><span class="sxs-lookup"><span data-stu-id="23380-264">![New Options on the Action button](../../media/admin-submission-main-action-button.png)</span></span>

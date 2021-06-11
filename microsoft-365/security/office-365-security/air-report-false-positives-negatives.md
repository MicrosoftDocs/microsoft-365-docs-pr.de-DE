---
title: So melden Sie falsch positive oder falsch negative Ergebnisse nach einer automatisierten Untersuchung in Microsoft Defender für Office 365
description: Wurde etwas von AIR in Microsoft Defender für Office 365 übersehen oder fälschlicherweise erkannt? Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Auslösen, Aktion, Korrektur, falsch positiv, falsch negativ
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 287bd9cd4dda6ccb152e93908a409e036eab9cc7
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878880"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="088ff-105">So melden Sie falsch positive/negative Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="088ff-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="088ff-106">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="088ff-106">**Applies to**</span></span>
- [<span data-ttu-id="088ff-107">Microsoft Defender für Office 365 – Plan 2</span><span class="sxs-lookup"><span data-stu-id="088ff-107">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="088ff-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="088ff-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="088ff-109">Wenn [air-Funktionen (Automatisierte Untersuchung und Reaktion) in Office 365](automated-investigation-response-office.md) etwas verpasst oder falsch erkannt haben, gibt es Schritte, die Ihr Sicherheitsteam ausführen kann, um es zu beheben.</span><span class="sxs-lookup"><span data-stu-id="088ff-109">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="088ff-110">Zu diesen Aktionen gehören:</span><span class="sxs-lookup"><span data-stu-id="088ff-110">Such actions include:</span></span>

- <span data-ttu-id="088ff-111">[Melden eines falsch positiven/negativen Ergebnisses an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="088ff-111">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="088ff-112">[Anpassen von Warnungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (falls erforderlich); Und</span><span class="sxs-lookup"><span data-stu-id="088ff-112">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="088ff-113">[Rückgängigmachen von Abhilfemaßnahmen, die ausgeführt wurden.](#undo-a-remediation-action)</span><span class="sxs-lookup"><span data-stu-id="088ff-113">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="088ff-114">Verwenden Sie diesen Artikel als Leitfaden.</span><span class="sxs-lookup"><span data-stu-id="088ff-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="088ff-115">Melden eines falsch positiven/negativen Ergebnisses an Microsoft zur Analyse</span><span class="sxs-lookup"><span data-stu-id="088ff-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="088ff-116">Wenn AIR in Microsoft Defender für Office 365 eine E-Mail-Nachricht, eine E-Mail-Anlage, eine URL in einer E-Mail-Nachricht oder eine URL in einer Office-Datei verpasst hat, können Sie [verdächtige Spam-, Phishing-, URLs und Dateien zur Office 365 Überprüfung an Microsoft übermitteln.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="088ff-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="088ff-117">Sie können auch [eine Datei zur Schadsoftwareanalyse an Microsoft übermitteln.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="088ff-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="088ff-118">Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden</span><span class="sxs-lookup"><span data-stu-id="088ff-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="088ff-119">Wenn eine Warnung durch legitime Verwendung ausgelöst wird oder die Warnung ungenau ist, können Sie [Warnungen im Cloud App Security Portal verwalten.](/cloud-app-security/managing-alerts)</span><span class="sxs-lookup"><span data-stu-id="088ff-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="088ff-120">Wenn Ihre Organisation zusätzlich zu Office 365 [Microsoft Defender für Endpunkt](/windows/security/threat-protection) verwendet und eine Datei, IP-Adresse, URL oder Domäne als Schadsoftware auf einem Gerät behandelt wird, obwohl es sicher ist, können Sie einen [benutzerdefinierten Indikator mit einer "Zulassen"-Aktion für Ihr Gerät erstellen.](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="088ff-120">If your organization is using [Microsoft Defender for Endpoint](/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="088ff-121">Rückgängigmachen einer Korrekturaktion</span><span class="sxs-lookup"><span data-stu-id="088ff-121">Undo a remediation action</span></span>

<span data-ttu-id="088ff-122">Wenn in den meisten Fällen eine Korrekturmaßnahme für eine E-Mail-Nachricht, eine E-Mail-Anlage oder eine URL ausgeführt wurde und das Element tatsächlich keine Bedrohung ist, kann Ihr Sicherheitsteam die Korrekturaktion rückgängig machen und Maßnahmen ergreifen, um zu verhindern, dass das falsch positive Ergebnis wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="088ff-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="088ff-123">Sie können entweder den [Bedrohungs-Explorer](#undo-an-action-using-threat-explorer) oder die [Registerkarte "Aktionen" für eine Untersuchung](#undo-an-action-in-the-action-center) verwenden, um eine Aktion rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="088ff-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="088ff-124">Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen, bevor Sie versuchen, die folgenden Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="088ff-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="088ff-125">Rückgängigmachen einer Aktion mithilfe des Bedrohungs-Explorers</span><span class="sxs-lookup"><span data-stu-id="088ff-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="088ff-126">Mit dem Bedrohungs-Explorer kann Ihr Sicherheitsteam eine E-Mail finden, die von einer Aktion betroffen ist, und die Aktion möglicherweise rückgängigmachen.</span><span class="sxs-lookup"><span data-stu-id="088ff-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

<br>

****

|<span data-ttu-id="088ff-127">Szenario</span><span class="sxs-lookup"><span data-stu-id="088ff-127">Scenario</span></span>|<span data-ttu-id="088ff-128">Rückgängig-Optionen</span><span class="sxs-lookup"><span data-stu-id="088ff-128">Undo Options</span></span>|<span data-ttu-id="088ff-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="088ff-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="088ff-130">Eine E-Mail-Nachricht wurde an den Junk-E-Mail-Ordner eines Benutzers weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="088ff-130">An email message was routed to a user's Junk Email folder</span></span>|<ul><li><span data-ttu-id="088ff-131">Verschieben der Nachricht in den Ordner "Gelöschte Elemente" des Benutzers</span><span class="sxs-lookup"><span data-stu-id="088ff-131">Move the message to the user's Deleted Items folder</span></span></li><li><span data-ttu-id="088ff-132">Verschieben der Nachricht in den Posteingang des Benutzers</span><span class="sxs-lookup"><span data-stu-id="088ff-132">Move the message to the user's Inbox</span></span></li><li><span data-ttu-id="088ff-133">Die Nachricht wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="088ff-133">Delete the message</span></span></li></ul>|[<span data-ttu-id="088ff-134">Suchen und Untersuchen bösartiger E-Mails, die in Office 365</span><span class="sxs-lookup"><span data-stu-id="088ff-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="088ff-135">Eine E-Mail-Nachricht oder eine Datei wurde unter Quarantäne gestellt</span><span class="sxs-lookup"><span data-stu-id="088ff-135">An email message or a file was quarantined</span></span>|<ul><li><span data-ttu-id="088ff-136">Freigeben der E-Mail oder Datei</span><span class="sxs-lookup"><span data-stu-id="088ff-136">Release the email or file</span></span></li><li> <span data-ttu-id="088ff-137">Löschen der E-Mail oder Datei</span><span class="sxs-lookup"><span data-stu-id="088ff-137">Delete the email or file</span></span></li></ul>|[<span data-ttu-id="088ff-138">Verwalten von isolierten Nachrichten als Administrator</span><span class="sxs-lookup"><span data-stu-id="088ff-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="088ff-139">Rückgängigmachen einer Aktion im Info-Center</span><span class="sxs-lookup"><span data-stu-id="088ff-139">Undo an action in the Action center</span></span>

<span data-ttu-id="088ff-140">Im Info-Center können Sie Abhilfemaßnahmen sehen, die ausgeführt wurden, und die Aktion möglicherweise rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="088ff-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="088ff-141">Wechseln Sie zum Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ).</span><span class="sxs-lookup"><span data-stu-id="088ff-141">Go to the Microsoft 365 Defender portal (<https://security.microsoft.com>).</span></span>
2. <span data-ttu-id="088ff-142">Wählen Sie im Navigationsbereich **das Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="088ff-142">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="088ff-143">Wählen Sie die Registerkarte **"Verlauf",** um die Liste der abgeschlossenen Aktionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="088ff-143">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="088ff-144">Wählen Sie ein Element aus.</span><span class="sxs-lookup"><span data-stu-id="088ff-144">Select an item.</span></span> <span data-ttu-id="088ff-145">Der Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="088ff-145">Its flyout pane opens.</span></span>
5. <span data-ttu-id="088ff-146">Wählen Sie im Flyoutbereich **"Rückgängig"** aus.</span><span class="sxs-lookup"><span data-stu-id="088ff-146">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="088ff-147">(Nur Aktionen, die rückgängig machen können, verfügen über eine Schaltfläche **"Rückgängig".)**</span><span class="sxs-lookup"><span data-stu-id="088ff-147">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="088ff-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="088ff-148">See also</span></span>

- [<span data-ttu-id="088ff-149">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="088ff-149">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="088ff-150">Automatisierte Untersuchungen in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="088ff-150">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)

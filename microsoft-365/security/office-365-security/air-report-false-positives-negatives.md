---
title: Melden falsch positiver oder falsch negativer Ergebnisse nach automatisierter Untersuchung in Microsoft Defender für Office 365
description: Wurde etwas verpasst oder falsch von AIR in Microsoft Defender für die Office 365? Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Trigger, Aktion, Korrektur, falsch positiv, falsch negativ
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
ms.openlocfilehash: 036ef1c97788f310c5b906ae5f80076ca2359cdb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275084"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="d8847-105">Melden falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="d8847-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d8847-106">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="d8847-106">**Applies to**</span></span>
- [<span data-ttu-id="d8847-107">Microsoft Defender für Office 365 – Plan 2</span><span class="sxs-lookup"><span data-stu-id="d8847-107">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d8847-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8847-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d8847-109">Wenn automatisierte Untersuchungs- und Reaktionsfunktionen [(AIR) in](automated-investigation-response-office.md) Office 365 etwas verpasst oder falsch erkannt wurden, gibt es Schritte, die Ihr Sicherheitsbetriebsteam unternehmen kann, um dies zu beheben.</span><span class="sxs-lookup"><span data-stu-id="d8847-109">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="d8847-110">Zu diesen Aktionen gehören:</span><span class="sxs-lookup"><span data-stu-id="d8847-110">Such actions include:</span></span>

- <span data-ttu-id="d8847-111">[Melden eines falsch positiven/negativen Werts an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="d8847-111">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="d8847-112">[Anpassen von Warnungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (falls erforderlich); und</span><span class="sxs-lookup"><span data-stu-id="d8847-112">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="d8847-113">[Rückgängig machen von Korrekturaktionen, die ergriffen wurden.](#undo-a-remediation-action)</span><span class="sxs-lookup"><span data-stu-id="d8847-113">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="d8847-114">Verwenden Sie diesen Artikel als Leitfaden.</span><span class="sxs-lookup"><span data-stu-id="d8847-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="d8847-115">Melden eines falsch positiven/negativen Werts an Microsoft zur Analyse</span><span class="sxs-lookup"><span data-stu-id="d8847-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="d8847-116">Wenn AIR in Microsoft Defender für Office 365 eine E-Mail-Nachricht, eine E-Mail-Anlage, eine URL in einer E-Mail-Nachricht oder eine URL in einer Office-Datei verpasst hat, können Sie mutmaßliche [Spam-, Phishing-, URLs-](admin-submission.md)und Dateien zur überprüfung an Microsoft Office 365 senden.</span><span class="sxs-lookup"><span data-stu-id="d8847-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="d8847-117">Sie können auch [eine Datei zur Schadsoftwareanalyse an Microsoft übermitteln.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="d8847-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="d8847-118">Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden</span><span class="sxs-lookup"><span data-stu-id="d8847-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="d8847-119">Wenn eine Warnung durch legitime Verwendung ausgelöst wird oder die Warnung ungenau ist, können Sie Warnungen im Cloud App Security [verwalten.](/cloud-app-security/managing-alerts)</span><span class="sxs-lookup"><span data-stu-id="d8847-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="d8847-120">Wenn Ihre Organisation [microsoft Defender for Endpoint](/windows/security/threat-protection) zusätzlich zu Office 365 verwendet und eine Datei, EINE IP-Adresse, URL oder Domäne als Schadsoftware auf einem Gerät behandelt wird, obwohl es sicher ist, können Sie einen benutzerdefinierten Indikator mit einer Aktion ["Zulassen"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)für Ihr Gerät erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8847-120">If your organization is using [Microsoft Defender for Endpoint](/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="d8847-121">Rückgängig machen einer Korrekturaktion</span><span class="sxs-lookup"><span data-stu-id="d8847-121">Undo a remediation action</span></span>

<span data-ttu-id="d8847-122">Wenn in den meisten Fällen eine Korrekturaktion für eine E-Mail-Nachricht, E-Mail-Anlage oder URL ergriffen wurde und das Element tatsächlich keine Bedrohung darstellt, kann Ihr Sicherheitsteam die Korrekturaktion rückgängig machen und Schritte ergreifen, um zu verhindern, dass sich das falsch positive Ergebnis wiederholt.</span><span class="sxs-lookup"><span data-stu-id="d8847-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="d8847-123">Sie können entweder den [Bedrohungs-Explorer](#undo-an-action-using-threat-explorer) oder die [Registerkarte Aktionen für](#undo-an-action-in-the-action-center) eine Untersuchung verwenden, um eine Aktion rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="d8847-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8847-124">Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen, bevor Sie versuchen, die folgenden Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d8847-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="d8847-125">Rückgängig machen einer Aktion mithilfe des Bedrohungs-Explorers</span><span class="sxs-lookup"><span data-stu-id="d8847-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="d8847-126">Mit dem Bedrohungs-Explorer kann Ihr Sicherheitsteam eine E-Mail finden, die von einer Aktion betroffen ist, und die Aktion möglicherweise rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="d8847-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="d8847-127">Szenario</span><span class="sxs-lookup"><span data-stu-id="d8847-127">Scenario</span></span>|<span data-ttu-id="d8847-128">Rückgängig-Optionen</span><span class="sxs-lookup"><span data-stu-id="d8847-128">Undo Options</span></span>|<span data-ttu-id="d8847-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8847-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="d8847-130">Eine E-Mail-Nachricht wurde an den Junk-E-Mail-Ordner eines Benutzers geroutet.</span><span class="sxs-lookup"><span data-stu-id="d8847-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="d8847-131">- Verschieben der Nachricht in den Ordner "Gelöschte Elemente" des Benutzers</span><span class="sxs-lookup"><span data-stu-id="d8847-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="d8847-132">- Verschieben der Nachricht in den Posteingang des Benutzers</span><span class="sxs-lookup"><span data-stu-id="d8847-132">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="d8847-133">- Löschen der Nachricht</span><span class="sxs-lookup"><span data-stu-id="d8847-133">- Delete the message</span></span>|[<span data-ttu-id="d8847-134">Suchen und untersuchen Sie schädliche E-Mails, die in diesem Office 365</span><span class="sxs-lookup"><span data-stu-id="d8847-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="d8847-135">Eine E-Mail-Nachricht oder eine Datei wurde unter Quarantäne gestellt</span><span class="sxs-lookup"><span data-stu-id="d8847-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="d8847-136">– Lassen Sie die E-Mail oder Datei frei</span><span class="sxs-lookup"><span data-stu-id="d8847-136">- Release the email or file</span></span><br/><span data-ttu-id="d8847-137">– Löschen der E-Mail oder Datei</span><span class="sxs-lookup"><span data-stu-id="d8847-137">- Delete the email or file</span></span>|[<span data-ttu-id="d8847-138">Verwalten isolierter Nachrichten als Administrator</span><span class="sxs-lookup"><span data-stu-id="d8847-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="d8847-139">Rückgängig machen einer Aktion im Aktionscenter</span><span class="sxs-lookup"><span data-stu-id="d8847-139">Undo an action in the Action center</span></span>

<span data-ttu-id="d8847-140">Im Aktionscenter können Sie Korrekturaktionen sehen, die ergriffen wurden, und die Aktion potenziell rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="d8847-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="d8847-141">Wechseln Sie zum Microsoft 365 Security Center ( <https://security.microsoft.com> ).</span><span class="sxs-lookup"><span data-stu-id="d8847-141">Go to the Microsoft 365 security center (<https://security.microsoft.com>).</span></span>
2. <span data-ttu-id="d8847-142">Wählen Sie im Navigationsbereich **Aktionscenter aus.**</span><span class="sxs-lookup"><span data-stu-id="d8847-142">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="d8847-143">Wählen Sie die **Registerkarte Verlauf** aus, um die Liste der abgeschlossenen Aktionen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="d8847-143">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="d8847-144">Wählen Sie ein Element aus.</span><span class="sxs-lookup"><span data-stu-id="d8847-144">Select an item.</span></span> <span data-ttu-id="d8847-145">Der Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d8847-145">Its flyout pane opens.</span></span>
5. <span data-ttu-id="d8847-146">Wählen Sie im Flyoutbereich **Rückgängig aus.**</span><span class="sxs-lookup"><span data-stu-id="d8847-146">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="d8847-147">(Nur Aktionen, die rückgängig gemacht werden können, verfügen über eine **Schaltfläche Rückgängig.)**</span><span class="sxs-lookup"><span data-stu-id="d8847-147">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="d8847-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8847-148">See also</span></span>

- [<span data-ttu-id="d8847-149">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="d8847-149">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d8847-150">Automatisierte Untersuchungen in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="d8847-150">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)

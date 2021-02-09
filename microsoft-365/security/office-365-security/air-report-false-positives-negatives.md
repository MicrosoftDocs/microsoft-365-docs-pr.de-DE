---
title: Melden falsch positiver oder falsch negativer Ergebnisse nach einer automatisierten Untersuchung in Microsoft Defender für Office 365
description: Wurde etwas von AIR in Microsoft Defender für Office 365 verpasst oder falsch erkannt? Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Trigger, Aktion, Korrektur, falsch positiv, falsch negativ
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 4ccc023a72ca450b1f0a433410206ccce59cb5f1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142975"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="d7b56-105">So melden Sie falsch positive/negative Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="d7b56-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="d7b56-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d7b56-106">**Applies to:**</span></span>
- <span data-ttu-id="d7b56-107">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="d7b56-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="d7b56-108">Wenn funktionen für die automatische Untersuchung und Reaktion [(AIR) in Office 365](automated-investigation-response-office.md) etwas übersehen oder falsch erkannt haben, gibt es Schritte, die Ihr Sicherheitsteam unternehmen kann, um dies zu beheben.</span><span class="sxs-lookup"><span data-stu-id="d7b56-108">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="d7b56-109">Zu diesen Aktionen gehören:</span><span class="sxs-lookup"><span data-stu-id="d7b56-109">Such actions include:</span></span>

- <span data-ttu-id="d7b56-110">[Melden eines falsch positiven/negativen Ergebnisses an Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="d7b56-110">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="d7b56-111">[Anpassen von Warnungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (falls erforderlich); und</span><span class="sxs-lookup"><span data-stu-id="d7b56-111">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="d7b56-112">[Rückgängig machen von Korrekturaktionen, die ergriffen wurden.](#undo-a-remediation-action)</span><span class="sxs-lookup"><span data-stu-id="d7b56-112">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="d7b56-113">Verwenden Sie diesen Artikel als Leitfaden.</span><span class="sxs-lookup"><span data-stu-id="d7b56-113">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="d7b56-114">Melden eines falsch positiven/negativen Ergebnisses zur Analyse an Microsoft</span><span class="sxs-lookup"><span data-stu-id="d7b56-114">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="d7b56-115">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="d7b56-115">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="d7b56-116">Sie können eine [Datei auch zur Schadsoftwareanalyse an Microsoft übermitteln.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="d7b56-116">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="d7b56-117">Anpassen einer Warnung, um zu verhindern, dass sich falsch positive Ergebnisse wiederholen</span><span class="sxs-lookup"><span data-stu-id="d7b56-117">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="d7b56-118">Wenn eine Warnung durch legitime Verwendung ausgelöst wird oder die Warnung ungenau ist, können Sie Warnungen im [Cloud App Security-Portal verwalten.](https://docs.microsoft.com/cloud-app-security/managing-alerts)</span><span class="sxs-lookup"><span data-stu-id="d7b56-118">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="d7b56-119">Wenn Ihre Organisation [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) zusätzlich zu Office 365 verwendet und eine Datei, EINE IP-Adresse, URL oder Domäne als Schadsoftware auf einem Gerät behandelt wird, können Sie einen benutzerdefinierten Indikator mit der Aktion ["Zulassen"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)für Ihr Gerät erstellen.</span><span class="sxs-lookup"><span data-stu-id="d7b56-119">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="d7b56-120">Rückgängig machen einer Wartungsaktion</span><span class="sxs-lookup"><span data-stu-id="d7b56-120">Undo a remediation action</span></span>

<span data-ttu-id="d7b56-121">Wenn in den meisten Fällen eine Korrekturaktion für eine E-Mail-Nachricht, E-Mail-Anlage oder URL ergriffen wurde und das Element tatsächlich keine Bedrohung darstellt, kann Ihr Sicherheitsteam die Korrekturmaßnahmen rückgängig machen und Maßnahmen ergreifen, um zu verhindern, dass sich falsch positive Ergebnisse wiederholen.</span><span class="sxs-lookup"><span data-stu-id="d7b56-121">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="d7b56-122">Sie können entweder den [Bedrohungs-Explorer](#undo-an-action-using-threat-explorer) oder die Registerkarte "Aktionen" [für eine Untersuchung](#undo-an-action-in-the-action-center) verwenden, um eine Aktion rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="d7b56-122">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7b56-123">Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen, bevor Sie versuchen, die folgenden Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d7b56-123">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="d7b56-124">Rückgängig machen einer Aktion mit dem Bedrohungs-Explorer</span><span class="sxs-lookup"><span data-stu-id="d7b56-124">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="d7b56-125">Mit dem Bedrohungs-Explorer kann Ihr Sicherheitsteam eine E-Mail finden, die von einer Aktion betroffen ist, und die Aktion potenziell rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="d7b56-125">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="d7b56-126">Szenario</span><span class="sxs-lookup"><span data-stu-id="d7b56-126">Scenario</span></span>|<span data-ttu-id="d7b56-127">Rückgängig-Optionen</span><span class="sxs-lookup"><span data-stu-id="d7b56-127">Undo Options</span></span>|<span data-ttu-id="d7b56-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7b56-128">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="d7b56-129">Eine E-Mail-Nachricht wurde an den Junk-E-Mail-Ordner eines Benutzers geroutet.</span><span class="sxs-lookup"><span data-stu-id="d7b56-129">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="d7b56-130">- Verschieben der Nachricht in den Ordner "Gelöschte Elemente" des Benutzers</span><span class="sxs-lookup"><span data-stu-id="d7b56-130">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="d7b56-131">- Verschieben der Nachricht in den Posteingang des Benutzers</span><span class="sxs-lookup"><span data-stu-id="d7b56-131">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="d7b56-132">– Nachricht löschen</span><span class="sxs-lookup"><span data-stu-id="d7b56-132">- Delete the message</span></span>|[<span data-ttu-id="d7b56-133">Suchen und Untersuchen bösartiger E-Mails, die in Office 365 zugestellt wurden</span><span class="sxs-lookup"><span data-stu-id="d7b56-133">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="d7b56-134">Eine E-Mail-Nachricht oder eine Datei wurde unter Quarantäne gestellt.</span><span class="sxs-lookup"><span data-stu-id="d7b56-134">An email message or a file was quarantined</span></span>|<span data-ttu-id="d7b56-135">– Freigabe der E-Mail oder Datei</span><span class="sxs-lookup"><span data-stu-id="d7b56-135">- Release the email or file</span></span><br/><span data-ttu-id="d7b56-136">– Löschen der E-Mail oder Datei</span><span class="sxs-lookup"><span data-stu-id="d7b56-136">- Delete the email or file</span></span>|[<span data-ttu-id="d7b56-137">Verwalten von Nachrichten in Quarantäne als Administrator</span><span class="sxs-lookup"><span data-stu-id="d7b56-137">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="d7b56-138">Rückgängig machen einer Aktion im Aktionscenter</span><span class="sxs-lookup"><span data-stu-id="d7b56-138">Undo an action in the Action center</span></span>

<span data-ttu-id="d7b56-139">Im Action Center können Sie Korrekturaktionen sehen, die ergriffen wurden, und die Aktion möglicherweise rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="d7b56-139">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="d7b56-140">Wechseln Sie zum Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ).</span><span class="sxs-lookup"><span data-stu-id="d7b56-140">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span>
2. <span data-ttu-id="d7b56-141">Wählen Sie im Navigationsbereich **"Aktionscenter" aus.**</span><span class="sxs-lookup"><span data-stu-id="d7b56-141">In the navigation pane, select **Action center**.</span></span> 
3. <span data-ttu-id="d7b56-142">Wählen Sie die **Registerkarte "Verlauf"** aus, um die Liste der abgeschlossenen Aktionen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d7b56-142">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="d7b56-143">Wählen Sie ein Element aus.</span><span class="sxs-lookup"><span data-stu-id="d7b56-143">Select an item.</span></span> <span data-ttu-id="d7b56-144">Der Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d7b56-144">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="d7b56-145">Wählen Sie im Flyoutbereich **"Rückgängig" aus.**</span><span class="sxs-lookup"><span data-stu-id="d7b56-145">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="d7b56-146">(Nur Aktionen, die rückgängig gemacht werden können, verfügen über eine **Schaltfläche "Rückgängig".)**</span><span class="sxs-lookup"><span data-stu-id="d7b56-146">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="d7b56-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7b56-147">See also</span></span>

- [<span data-ttu-id="d7b56-148">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="d7b56-148">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="d7b56-149">Automatisierte Untersuchungen in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="d7b56-149">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)

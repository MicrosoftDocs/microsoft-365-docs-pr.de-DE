---
title: Behandeln falsch positiver oder falsch negativer Ergebnisse in AIR in Microsoft 365 Defender
description: Wurde etwas von AIR in Microsoft 365 Defender verpasst oder falsch erkannt? Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse zur Analyse an Microsoft übermitteln.
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
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930354"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="53b16-105">Behandeln falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="53b16-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="53b16-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="53b16-106">**Applies to:**</span></span>
- <span data-ttu-id="53b16-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="53b16-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="53b16-108">Haben [automatisierte Untersuchungs- und Reaktionsfunktionen](mtp-autoir.md) in Microsoft 365 Defender etwas übersehen oder falsch erkannt?</span><span class="sxs-lookup"><span data-stu-id="53b16-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender miss or wrongly detect something?</span></span> <span data-ttu-id="53b16-109">Es gibt Schritte, die Sie ausführen können, um sie zu beheben.</span><span class="sxs-lookup"><span data-stu-id="53b16-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="53b16-110">Sie können:</span><span class="sxs-lookup"><span data-stu-id="53b16-110">You can:</span></span>

- <span data-ttu-id="53b16-111">[Melden eines falsch positiven/negativen Ergebnisses an Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="53b16-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="53b16-112">[Anpassen der Warnungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (falls erforderlich); und</span><span class="sxs-lookup"><span data-stu-id="53b16-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="53b16-113">[Rückgängig gemachte Wiederherstellungsaktionen, die auf Geräten ergriffen wurden.](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="53b16-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="53b16-114">Verwenden Sie diesen Artikel als Leitfaden.</span><span class="sxs-lookup"><span data-stu-id="53b16-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="53b16-115">Melden eines falsch positiven/negativen Ergebnisses zur Analyse an Microsoft</span><span class="sxs-lookup"><span data-stu-id="53b16-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="53b16-116">Element wurde verpasst oder falsch erkannt</span><span class="sxs-lookup"><span data-stu-id="53b16-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="53b16-117">Dienst</span><span class="sxs-lookup"><span data-stu-id="53b16-117">Service</span></span>  |<span data-ttu-id="53b16-118">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="53b16-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="53b16-119">– E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="53b16-119">- Email message</span></span> <br/><span data-ttu-id="53b16-120">- E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="53b16-120">- Email attachment</span></span> <br/><span data-ttu-id="53b16-121">- URL in einer E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="53b16-121">- URL in an email message</span></span><br/><span data-ttu-id="53b16-122">– URL in einer Office-Datei</span><span class="sxs-lookup"><span data-stu-id="53b16-122">- URL in an Office file</span></span>      |[<span data-ttu-id="53b16-123">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="53b16-123">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="53b16-124">Übermitteln von verdächtigen Spam-, Phishing-, URLs und Dateien zur Überprüfung an Microsoft</span><span class="sxs-lookup"><span data-stu-id="53b16-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="53b16-125">Datei oder App auf einem Gerät</span><span class="sxs-lookup"><span data-stu-id="53b16-125">File or app on a device</span></span>    |[<span data-ttu-id="53b16-126">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="53b16-126">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="53b16-127">Übermitteln einer Datei zur Schadsoftwareanalyse an Microsoft</span><span class="sxs-lookup"><span data-stu-id="53b16-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="53b16-128">Anpassen einer Warnung, um zu verhindern, dass sich falsch positive Ergebnisse wiederholen</span><span class="sxs-lookup"><span data-stu-id="53b16-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="53b16-129">Szenario</span><span class="sxs-lookup"><span data-stu-id="53b16-129">Scenario</span></span> |<span data-ttu-id="53b16-130">Dienst</span><span class="sxs-lookup"><span data-stu-id="53b16-130">Service</span></span> |<span data-ttu-id="53b16-131">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="53b16-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="53b16-132">– Eine Warnung wird durch legitime Verwendung ausgelöst</span><span class="sxs-lookup"><span data-stu-id="53b16-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="53b16-133">– Eine Warnung ist ungenau</span><span class="sxs-lookup"><span data-stu-id="53b16-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="53b16-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="53b16-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="53b16-135">oder</span><span class="sxs-lookup"><span data-stu-id="53b16-135">or</span></span> <br/>[<span data-ttu-id="53b16-136">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="53b16-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="53b16-137">Verwalten von Warnungen im Cloud App Security-Portal</span><span class="sxs-lookup"><span data-stu-id="53b16-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="53b16-138">Eine Datei, IP-Adresse, URL oder Domäne wird auf einem Gerät als Schadsoftware behandelt, obwohl sie sicher ist.</span><span class="sxs-lookup"><span data-stu-id="53b16-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="53b16-139">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="53b16-139">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="53b16-140">Erstellen eines benutzerdefinierten Indikators mit der Aktion "Zulassen"</span><span class="sxs-lookup"><span data-stu-id="53b16-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="53b16-141">Rückgängig machen einer Korrekturaktion, die auf einem Gerät ergriffen wurde</span><span class="sxs-lookup"><span data-stu-id="53b16-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="53b16-142">Wenn eine Korrekturaktion auf einem Gerät (z. B. einem Windows 10-Gerät) ausgeführt wurde und das Element tatsächlich keine Bedrohung darstellt, kann Ihr Sicherheitsteam die Korrekturaktion im Action Center rückgängig [machen.](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="53b16-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53b16-143">Stellen Sie sicher, dass Sie über [die erforderlichen Berechtigungen verfügen,](mtp-action-center.md#required-permissions-for-action-center-tasks) bevor Sie die folgende Aufgabe ausführen.</span><span class="sxs-lookup"><span data-stu-id="53b16-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="53b16-144">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="53b16-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="53b16-145">Wählen Sie im Navigationsbereich **Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="53b16-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="53b16-146">Wählen Sie **auf der** Registerkarte "Verlauf" eine Aktion aus, die Rückgängig gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="53b16-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="53b16-147">Dadurch wird ein Flyout geöffnet.</span><span class="sxs-lookup"><span data-stu-id="53b16-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="53b16-148">Verwenden Sie Filter, um die Liste der Ergebnisse einengt.</span><span class="sxs-lookup"><span data-stu-id="53b16-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="53b16-149">Wählen Sie im Flyout für das ausgewählte Element die Seite **"Untersuchung öffnen" aus.**</span><span class="sxs-lookup"><span data-stu-id="53b16-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="53b16-150">Wählen Sie in der Ansicht "Untersuchungsdetails" die Registerkarte **"Aktionen"** aus.</span><span class="sxs-lookup"><span data-stu-id="53b16-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="53b16-151">Wählen Sie ein Element mit dem Status **"Abgeschlossen"** aus, und suchen Sie in der Spalte "Entscheidungen" nach einem Link wie  **"Genehmigt".**</span><span class="sxs-lookup"><span data-stu-id="53b16-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="53b16-152">Dadurch wird ein Flyout mit weiteren Details zur Aktion geöffnet.</span><span class="sxs-lookup"><span data-stu-id="53b16-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="53b16-153">Um die Aktion rückgängig zu machen, wählen **Sie "Problembehebung löschen" aus.**</span><span class="sxs-lookup"><span data-stu-id="53b16-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="53b16-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53b16-154">See also</span></span>

- [<span data-ttu-id="53b16-155">Anzeigen der Details und Ergebnisse einer automatischen Untersuchung</span><span class="sxs-lookup"><span data-stu-id="53b16-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="53b16-156">Proaktive Suche nach Bedrohungen mit erweiterter Suche in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="53b16-156">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)

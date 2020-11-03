---
title: Behandeln falsch positiver oder falscher negativer Ergebnisse in der Luft in Microsoft 365 Defender
description: Wurde etwas verpasst oder fälschlicherweise von Air in Microsoft 365 Defender erkannt? Hier erfahren Sie, wie Sie falsch positive Ergebnisse oder falsch negative Informationen zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Auslöser, Aktion, Korrektur, falsch positiv, falsch negativ
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 92ad4a96665a5355bce7e3546f8c52779f770927
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843732"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="047f6-105">Behandeln von falsch positiven/negativen Ergebnissen in automatisierten Ermittlungs-und Antwortfunktionen</span><span class="sxs-lookup"><span data-stu-id="047f6-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="047f6-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="047f6-106">**Applies to:**</span></span>
- <span data-ttu-id="047f6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="047f6-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="047f6-108">Haben [automatisierte Ermittlungs-und Antwortfunktionen](mtp-autoir.md) in Microsoft 365 Defender das Erkennen von Fehlern vermissen oder etwas falsch erkannt?</span><span class="sxs-lookup"><span data-stu-id="047f6-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender miss or wrongly detect something?</span></span> <span data-ttu-id="047f6-109">Es gibt Schritte, die Sie ausführen können, um es zu beheben.</span><span class="sxs-lookup"><span data-stu-id="047f6-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="047f6-110">Sie können:</span><span class="sxs-lookup"><span data-stu-id="047f6-110">You can:</span></span>

- <span data-ttu-id="047f6-111">[Melden einer falsch positiven/negativen Meldung an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="047f6-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="047f6-112">[Passen Sie Ihre Benachrichtigungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) an (falls erforderlich); und</span><span class="sxs-lookup"><span data-stu-id="047f6-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="047f6-113">[Rückgängigmachen von auf Geräten ausgeführten Korrekturaktionen](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="047f6-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="047f6-114">Verwenden Sie diesen Artikel als Leitfaden.</span><span class="sxs-lookup"><span data-stu-id="047f6-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="047f6-115">Melden einer falsch positiven/negativen Meldung an Microsoft zur Analyse</span><span class="sxs-lookup"><span data-stu-id="047f6-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="047f6-116">Element verpasst oder falsch erkannt</span><span class="sxs-lookup"><span data-stu-id="047f6-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="047f6-117">Dienst</span><span class="sxs-lookup"><span data-stu-id="047f6-117">Service</span></span>  |<span data-ttu-id="047f6-118">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="047f6-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="047f6-119">-E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="047f6-119">- Email message</span></span> <br/><span data-ttu-id="047f6-120">-E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="047f6-120">- Email attachment</span></span> <br/><span data-ttu-id="047f6-121">-URL in einer e-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="047f6-121">- URL in an email message</span></span><br/><span data-ttu-id="047f6-122">-URL in einer Office-Datei</span><span class="sxs-lookup"><span data-stu-id="047f6-122">- URL in an Office file</span></span>      |[<span data-ttu-id="047f6-123">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="047f6-123">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="047f6-124">Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="047f6-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="047f6-125">Datei oder App auf einem Gerät</span><span class="sxs-lookup"><span data-stu-id="047f6-125">File or app on a device</span></span>    |[<span data-ttu-id="047f6-126">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="047f6-126">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="047f6-127">Übermitteln einer Datei an Microsoft zur Analyse von Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="047f6-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="047f6-128">Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden</span><span class="sxs-lookup"><span data-stu-id="047f6-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="047f6-129">Szenario</span><span class="sxs-lookup"><span data-stu-id="047f6-129">Scenario</span></span> |<span data-ttu-id="047f6-130">Dienst</span><span class="sxs-lookup"><span data-stu-id="047f6-130">Service</span></span> |<span data-ttu-id="047f6-131">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="047f6-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="047f6-132">-Eine Warnung wird durch eine legitime Verwendung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="047f6-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="047f6-133">-Eine Warnung ist falsch</span><span class="sxs-lookup"><span data-stu-id="047f6-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="047f6-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="047f6-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="047f6-135">oder</span><span class="sxs-lookup"><span data-stu-id="047f6-135">or</span></span> <br/>[<span data-ttu-id="047f6-136">Erkennung erweiterter Azure-Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="047f6-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="047f6-137">Verwalten von Benachrichtigungen im Cloud-App-Sicherheitsportal</span><span class="sxs-lookup"><span data-stu-id="047f6-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="047f6-138">Eine Datei, IP-Adresse, URL oder Domäne wird auf einem Gerät als Schadsoftware behandelt, auch wenn Sie sicher ist.</span><span class="sxs-lookup"><span data-stu-id="047f6-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="047f6-139">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="047f6-139">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="047f6-140">Erstellen eines benutzerdefinierten Indikators mit einer Aktion "zulassen"</span><span class="sxs-lookup"><span data-stu-id="047f6-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="047f6-141">Rückgängigmachen einer auf einem Gerät ausgeführten Korrekturaktion</span><span class="sxs-lookup"><span data-stu-id="047f6-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="047f6-142">Wenn eine Korrekturaktion auf einem Gerät (beispielsweise einem Windows 10-Gerät) ausgeführt wurde und das Element tatsächlich keine Bedrohung darstellt, kann Ihr Sicherheits Betriebsteam die Korrekturaktion im [Aktionscenter](mtp-action-center.md)rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="047f6-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="047f6-143">Stellen Sie sicher, dass Sie über die [erforderlichen Berechtigungen](mtp-action-center.md#required-permissions-for-action-center-tasks) verfügen, bevor Sie versuchen, die folgende Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="047f6-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="047f6-144">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="047f6-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="047f6-145">Wählen Sie im Navigationsbereich **Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="047f6-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="047f6-146">Wählen Sie auf der Registerkarte **Verlauf** eine Aktion aus, die Sie rückgängig machen möchten.</span><span class="sxs-lookup"><span data-stu-id="047f6-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="047f6-147">Dadurch wird ein Flyout geöffnet.</span><span class="sxs-lookup"><span data-stu-id="047f6-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="047f6-148">Verwenden Sie Filter, um die Ergebnisliste einzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="047f6-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="047f6-149">Wählen Sie im Flyout für das ausgewählte Element die Option **Untersuchungs Seite öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="047f6-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="047f6-150">Wählen Sie in der Ansicht Details der Untersuchung die Registerkarte **Aktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="047f6-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="047f6-151">Wählen Sie ein Element mit dem Status **abgeschlossen** aus, und suchen Sie in der Spalte **Decisions** nach einem Link, beispielsweise **genehmigt**.</span><span class="sxs-lookup"><span data-stu-id="047f6-151">Select an item that has status of **Completed** , and look for a link, such as **Approved** , in the **Decisions** column.</span></span> <span data-ttu-id="047f6-152">Dadurch wird ein Flyout mit weiteren Details zur Aktion geöffnet.</span><span class="sxs-lookup"><span data-stu-id="047f6-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="047f6-153">Um die Aktion rückgängig zu machen, wählen Sie **Korrektur löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="047f6-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="047f6-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="047f6-154">See also</span></span>

- [<span data-ttu-id="047f6-155">Anzeigen der Details und Ergebnisse einer automatischen Untersuchung</span><span class="sxs-lookup"><span data-stu-id="047f6-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="047f6-156">Proaktive Suche nach Bedrohungen durch erweiterte Jagd in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="047f6-156">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
